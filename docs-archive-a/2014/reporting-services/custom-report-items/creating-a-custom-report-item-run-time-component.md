---
title: Creazione di un componente runtime dell'elemento del report personalizzato | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- custom report items, creating
ms.assetid: b3e15a4a-98f8-4dbb-b847-bbcb20327051
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 50c5c0211bc5cd1359af9d1493782bd9d96c2b3a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623917"
---
# <a name="creating-a-custom-report-item-run-time-component"></a>Creazione di un componente runtime dell'elemento del report personalizzato
  Il componente runtime dell'elemento del report personalizzato viene implementato come [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] componente utilizzando qualsiasi linguaggio conforme a CLS e viene chiamato da elaborazione report in fase di esecuzione. Le proprietà del componente runtime vengono definite nell'ambiente di progettazione modificando il componente della modalità progettazione corrispondente dell'elemento del report personalizzato.  

<!--
Replacing the following multiValue.....

ms.technology: 
  - "docset-sql-devref"
  - "reporting-services-native"

.....with the following single value.....

ms.technology: reporting-services
.

(GeneMi = MightyPen  ,  2019-04-20  ,  DevO= 1515083)
-->

 Per un esempio di elemento del report personalizzato completamente implementato, vedere [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889) (Esempi del prodotto SQL Server Reporting Services).  
  
## <a name="definition-and-instance-objects"></a>Oggetti definizione e oggetti istanza  
 Prima di implementare un elemento del report personalizzato, è importante sottolineare la differenza tra *oggetti definizione* e *oggetti istanza*. Gli oggetti definizione forniscono la rappresentazione RDL dell'elemento del report personalizzato mentre gli oggetti istanza sono le versioni valutate degli oggetti definizione. È presente un solo oggetto definizione per ogni elemento nel report. Quando si accede alle proprietà in un oggetto definizione che contiene espressioni, si otterrà la stringa dell'espressione non valutata. Gli oggetti istanza contengono le versioni valutate degli oggetti definizione e possono avere una relazione uno-a-molti con l'oggetto definizione di un elemento. Ad esempio, se un report presenta un'area dati <xref:Microsoft.ReportingServices.OnDemandReportRendering.Tablix> contenente un <xref:Microsoft.ReportingServices.OnDemandReportRendering.CustomReportItem> in una riga dettaglio, saranno presenti un solo oggetto definizione e un oggetto istanza per ogni riga nell'area dati.  
  
## <a name="implementing-the-icustomreportitem-interface"></a>Implementazione dell'interfaccia ICustomReportItem  
 Per creare un componente runtime `CustomReportItem` sarà necessario implementare l'interfaccia <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem> definita in Microsoft.ReportingServices.ProcessingCore.dll:  
  
```csharp  
namespace Microsoft.ReportingServices.OnDemandReportRendering  
{  
    public interface ICustomReportItem  
    {  
        void GenerateReportItemDefinition(CustomReportItem customReportItem);  
void EvaluateReportItemInstance(CustomReportItem customReportItem);  
    }  
}  
```  
  
 Dopo avere implementato l'interfaccia <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem>, verranno generati due stub del metodo: <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem.GenerateReportItemDefinition%2A> e <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem.EvaluateReportItemInstance%2A>. Il metodo <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem.GenerateReportItemDefinition%2A> viene chiamato per primo e utilizzato per impostare le proprietà di definizione e creare l'oggetto <xref:Microsoft.ReportingServices.OnDemandReportRendering.Image> che conterrà le proprietà di definizione e di istanza utilizzate per il rendering dell'elemento. Il metodo <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem.EvaluateReportItemInstance%2A> viene chiamato dopo la valutazione degli oggetti definizione e fornisce gli oggetti istanza che verranno utilizzati per il rendering dell'elemento.  
  
 Di seguito è riportato un esempio di implementazione di un elemento del report personalizzato che esegue il rendering del nome del controllo come immagine.  
  
```csharp  
namespace Microsoft.Samples.ReportingServices  
{  
    using System;  
    using System.Collections.Generic;  
    using System.Collections.Specialized;  
    using System.Drawing.Imaging;  
    using System.IO;  
    using System.Text;  
    using Microsoft.ReportingServices.OnDemandReportRendering;  
  
    public class PolygonsCustomReportItem : ICustomReportItem  
    {  
        #region ICustomReportItem Members  
  
        public void GenerateReportItemDefinition(CustomReportItem cri)  
        {  
            // Create the Image object that will be   
            // used to render the custom report item  
            cri.CreateCriImageDefinition();  
            Image polygonImage = (Image)cri.GeneratedReportItem;  
        }  
  
        public void EvaluateReportItemInstance(CustomReportItem cri)  
        {  
            // Get the Image definition  
            Image polygonImage = (Image)cri.GeneratedReportItem;  
  
            // Create the image for the custom report item  
            polygonImage.ImageInstance.ImageData = DrawImage(cri);  
        }  
  
        #endregion  
  
        /// <summary>  
        /// Creates an image of the CustomReportItem's name  
        /// </summary>  
        private byte[] DrawImage(CustomReportItem customReportItem)  
        {  
            int width = 1;          // pixels  
            int height = 1;         // pixels  
            int resolution = 75;    // dpi  
  
            System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap(width, height);  
            bitmap.SetResolution(resolution, resolution);  
  
            System.Drawing.Graphics graphics = System.Drawing.Graphics.FromImage(bitmap);  
            graphics.PageUnit = System.Drawing.GraphicsUnit.Pixel;  
  
            // Get the Font for the Text  
            System.Drawing.Font font = new System.Drawing.Font(System.Drawing.FontFamily.GenericMonospace,  
                12, System.Drawing.FontStyle.Regular);  
  
            // Get the Brush for drawing the Text  
            System.Drawing.Brush brush = new System.Drawing.SolidBrush(System.Drawing.Color.LightGreen);  
  
            // Get the measurements for the image  
            System.Drawing.SizeF maxStringSize = graphics.MeasureString(customReportItem.Name, font);  
            width = (int)(maxStringSize.Width + 2 * font.GetHeight(resolution));  
            height = (int)(maxStringSize.Height + 2 * font.GetHeight(resolution));  
  
            bitmap.Dispose();  
            bitmap = new System.Drawing.Bitmap(width, height);  
            bitmap.SetResolution(resolution, resolution);  
  
            graphics.Dispose();  
            graphics = System.Drawing.Graphics.FromImage(bitmap);  
            graphics.PageUnit = System.Drawing.GraphicsUnit.Pixel;  
  
            // Draw the text  
            graphics.DrawString(customReportItem.Name, font, brush, font.GetHeight(resolution),   
                font.GetHeight(resolution));  
  
            // Create the byte array of the image data  
            MemoryStream memoryStream = new MemoryStream();  
            bitmap.Save(memoryStream, ImageFormat.Bmp);  
            memoryStream.Position = 0;  
            byte[] imageData = new byte[memoryStream.Length];  
            memoryStream.Read(imageData, 0, imageData.Length);  
  
            return imageData;  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Architettura dell'elemento del report personalizzato](custom-report-item-architecture.md)   
 [Creazione di un componente della fase di progettazione di un elemento del report personalizzato](creating-a-custom-report-item-design-time-component.md)   
 [Librerie di classi dell'elemento del report personalizzato](custom-report-item-class-libraries.md)   
 [Procedura: Distribuire un elemento del report personalizzato](how-to-deploy-a-custom-report-item.md)  
  
  
