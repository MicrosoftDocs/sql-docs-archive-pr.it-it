---
title: Proprietà del progetto (SSAS tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.depservconfig.f1
- sql12.asvs.bidtoolset.semmodelprojprop.f1
ms.assetid: 333c1fc0-361c-415a-bd68-4e057f67bcb7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 115946cca94da7ad73c540bbfabc0c5a2c44c48f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712431"
---
# <a name="project-properties-ssas-tabular"></a>Project Properties (SSAS Tabular)
  In questo argomento vengono descritte le proprietà dei progetti di modelli. Ogni progetto di modello tabulare dispone di proprietà relative alle opzioni e al server di distribuzione che consentono di specificare come vengono distribuiti il progetto e il modello, ad esempio il server in cui verrà distribuito il modello e il nome del database modello distribuito. Queste impostazioni differiscono dalle proprietà dei modelli che interessano invece il database dell'area di lavoro modello. Le proprietà del progetto descritte in questo argomento si trovano nella finestra di dialogo delle proprietà modali, diversa dalla finestra delle proprietà utilizzata per visualizzare altri tipi di proprietà. Per visualizzare queste proprietà, in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]Esplora soluzioni **di**fare clic con il pulsante destro del mouse sul progetto, quindi scegliere **Proprietà**.  
  
 Sezioni dell'argomento:  
  
-   [Proprietà progetto](#bkmk_proj_properties)  
  
-   [Per configurare le impostazioni delle proprietà Opzioni di distribuzione e Server di distribuzione](#bkmk_conf_proj_settings)  
  
##  <a name="project-properties"></a><a name="bkmk_proj_properties"></a>Proprietà progetto  
 **Opzioni di distribuzione**  
  
|Proprietà|Impostazione predefinita|Descrizione|  
|--------------|---------------------|-----------------|  
|**Opzione di elaborazione**|**Default**|Per impostazione predefinita, in Analysis Services verrà determinato il tipo di elaborazione necessario quando vengono distribuite le modifiche agli oggetti. Ciò garantisce in genere tempi di distribuzione più rapidi. È inoltre possibile, tuttavia, scegliere di eseguire con ogni distribuzione l'elaborazione completa o nessuna elaborazione.|  
|**Distribuzione transazionale**|**False**|Consente di specificare se la distribuzione del modello sia o meno transazionale. Per impostazione predefinita, la distribuzione di tutti gli oggetti o di quelli modificati non è transazionale con l'elaborazione di tali oggetti distribuiti. La distribuzione può avere esito positivo ed essere persistente anche in caso di esito negativo dell'elaborazione. Questa impostazione può essere modificata in modo da incorporare la distribuzione e l'elaborazione in una singola transazione.|  
|**Modalità query**|**In memoria**|Consente di specificare l'origine da cui vengono restituiti i risultati della query. Per altre informazioni, vedere [Modalità DirectQuery &#40;SSAS tabulare&#41;](directquery-mode-ssas-tabular.md).|  
  
 **Server di distribuzione**  
  
|Proprietà|Impostazione predefinita|Descrizione|  
|--------------|---------------------|-----------------|  
|**Server**|**localhost**|Consente di specificare un'istanza di Analysis Services. Per impostazione predefinita, i modelli vengono distribuiti nell'istanza predefinita di Analysis Services nel computer locale. Questa impostazione può essere modificata per specificare un'istanza denominata sul computer locale o qualsiasi istanza su qualsiasi computer remoto per cui si dispone dell'autorizzazione necessaria per creare oggetti di Analysis Services. In genere, si tratta delle autorizzazioni di amministratore.<br /><br /> L'impostazione predefinita per questa proprietà può essere modificata utilizzando la proprietà Server di distribuzione predefinito nella pagina Distribuzione delle impostazioni di Analysis Server in Strumenti\finestra di dialogo Opzioni. Per altre informazioni, vedere [Configurare la modellazione dei dati e le proprietà di distribuzione predefinite &#40;SSAS tabulare&#41;](properties-ssas-tabular.md).|  
|**Edizione**|**Developer**|Consente di specificare l'edizione del server Analysis Services in cui verrà distribuito il modello. L'edizione del server consente di definire le varie funzionalità che possono essere incorporate nel progetto.|  
|**Database**|**Modello**|Consente di specificare il nome del database di Analysis Services in cui verrà creata un'istanza degli oggetti modello durante la distribuzione. Questo nome verrà specificato in una connessione dati o in un file di connessione dati con estensione rsds. È consigliabile che il nome rifletta il tipo di analisi che verrà eseguito utilizzando il modello, ad esempio AdventureWorksSalesModel.<br /><br /> ** \* \* Importante \* per \* ** evitare nomi duplicati per i modelli distribuiti, è necessario modificare l'impostazione del nome della proprietà del **database** in modo da riflettere lo scopo del modello. Tale nome sarà quello visualizzato dagli utenti quando si connettono al modello come origine dati.|  
|**Nome cubo**|**Modello**|Consente di specificare il nome del cubo del database come mostrato in una connessione ai dati dello strumento client di creazione report.|  
|**Version**|**11,0**|Versione dell'istanza di Analysis Services in cui verrà distribuito il progetto.|  
  
 **Opzioni di DirectQuery**  
  
|Proprietà|Impostazione predefinita|Descrizione|  
|--------------|---------------------|-----------------|  
|**Impostazioni di rappresentazione**|**Default**|Consente di specificare le credenziali utilizzate per connettersi alle origini dati per un modello in esecuzione in modalità DirectQuery. Queste credenziali sono diverse da quelle della rappresentazione utilizzate nella modalità In memoria predefinita. Per altre informazioni, vedere [Rappresentazione &#40;SSAS tabulare&#41;](impersonation-ssas-tabular.md).|  
  
###  <a name="to-configure-deployment-options-and-deployment-server-property-settings"></a><a name="bkmk_conf_proj_settings"></a>Per configurare le impostazioni delle proprietà opzioni di distribuzione e server di distribuzione  
  
1.  In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]Esplora soluzioni **di**fare clic con il pulsante destro del mouse sul progetto, quindi selezionare **Proprietà**.  
  
2.  Nella finestra **Proprietà** fare clic su una proprietà, quindi digitare un valore o fare clic sulla freccia GIÙ per selezionare un'opzione di impostazione.  
  
## <a name="see-also"></a>Vedere anche  
 [Configurare la modellazione dei dati e le proprietà di distribuzione predefinite &#40;SSAS tabulare&#41;](properties-ssas-tabular.md)   
 [Proprietà del modello &#40;SSAS tabulare&#41;](model-properties-ssas-tabular.md)   
 [Distribuzione di una soluzione del modello tabulare &#40;SSAS tabulare&#41;](tabular-model-solution-deployment-ssas-tabular.md)  
  
  
