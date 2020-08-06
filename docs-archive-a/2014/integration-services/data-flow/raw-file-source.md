---
title: Origine file non elaborato | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.rawfilesource.f1
helpviewer_keywords:
- sources [Integration Services], Raw File
- raw data [Integration Services]
- Raw File source
ms.assetid: 5b4daea5-7f76-4674-aa77-0a79f9f97f7d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4cbc5800c4fb2b90b74e66b6ff161118b2b550f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626167"
---
# <a name="raw-file-source"></a><span data-ttu-id="7bc86-102">origine file non elaborato</span><span class="sxs-lookup"><span data-stu-id="7bc86-102">Raw File Source</span></span>
  <span data-ttu-id="7bc86-103">L'origine file non elaborato legge i dati non elaborati da un file.</span><span class="sxs-lookup"><span data-stu-id="7bc86-103">The Raw File source reads raw data from a file.</span></span> <span data-ttu-id="7bc86-104">Poiché la rappresentazione dei dati è nativa per l'origine, non è necessaria alcuna conversione e quasi nessuna analisi dei dati.</span><span class="sxs-lookup"><span data-stu-id="7bc86-104">Because the representation of the data is native to the source, the data requires no translation and almost no parsing.</span></span> <span data-ttu-id="7bc86-105">Ciò significa che l'origine file non elaborato è in grado di leggere i dati più rapidamente rispetto ad altre origini, ad esempio l'origine file flat e l'origine OLE DB.</span><span class="sxs-lookup"><span data-stu-id="7bc86-105">This means that the Raw File source can read data more quickly than other sources such as the Flat File and the OLE DB sources.</span></span>  
  
 <span data-ttu-id="7bc86-106">L'origine file non elaborato consente di recuperare dati non elaborati scritti in precedenza dalla destinazione file non elaborato.</span><span class="sxs-lookup"><span data-stu-id="7bc86-106">The Raw File source is used to retrieve raw data that was previously written by the Raw File destination.</span></span> <span data-ttu-id="7bc86-107">È anche possibile puntare l'origine file non elaborato a un file non elaborato vuoto in cui sono contenute solo le colonne (file di soli metadati).</span><span class="sxs-lookup"><span data-stu-id="7bc86-107">You can also point the Raw File source to an empty raw file that contains only the columns (metadata-only file).</span></span> <span data-ttu-id="7bc86-108">Si utilizza la destinazione file non elaborato per generare il file di soli metadati senza dover eseguire il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="7bc86-108">You use the Raw File destination to generate the metadata-only file without having to run the package.</span></span> <span data-ttu-id="7bc86-109">Per altre informazioni, vedere [Destinazione file non elaborato](raw-file-destination.md).</span><span class="sxs-lookup"><span data-stu-id="7bc86-109">For more information, see [Raw File Destination](raw-file-destination.md).</span></span>  
  
 <span data-ttu-id="7bc86-110">Nel formato di file non elaborato sono contenute informazioni di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="7bc86-110">The raw file format contains sort information.</span></span> <span data-ttu-id="7bc86-111">Con la destinazione file non elaborato è possibile salvare tutte le informazioni di ordinamento in cui sono inclusi i flag di confronto per le colonne stringa.</span><span class="sxs-lookup"><span data-stu-id="7bc86-111">The Raw File Destination saves all the sort information including the comparison flags for string columns.</span></span> <span data-ttu-id="7bc86-112">Con l'origine file non elaborato è possibile leggere e riconoscere le informazioni di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="7bc86-112">The Raw File source reads and honors the sort information.</span></span> <span data-ttu-id="7bc86-113">È possibile configurare l'origine file non elaborato in modo da ignorare i flag di ordinamento nel file utilizzando l'editor avanzato.</span><span class="sxs-lookup"><span data-stu-id="7bc86-113">You do have the option of configuring the Raw File Source to ignore the sort flags in the file, using the Advanced Editor.</span></span> <span data-ttu-id="7bc86-114">Per altre informazioni sui flag di confronto, vedere [Confronto di dati stringa](comparing-string-data.md).</span><span class="sxs-lookup"><span data-stu-id="7bc86-114">For more information about comparison flags, see [Comparing String Data](comparing-string-data.md).</span></span>  
  
 <span data-ttu-id="7bc86-115">Per configurare il file non elaborato è necessario specificare il nome del file che deve essere letto dall'origine file non elaborato.</span><span class="sxs-lookup"><span data-stu-id="7bc86-115">You configure the Raw File by specifying the name of the name of the file that the Raw File source reads.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7bc86-116">Questa origine non utilizza alcuna gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="7bc86-116">This source does not use a connection manager.</span></span>  
  
 <span data-ttu-id="7bc86-117">Questa origine include un solo output.</span><span class="sxs-lookup"><span data-stu-id="7bc86-117">This source has one output.</span></span> <span data-ttu-id="7bc86-118">Non supporta un output degli errori.</span><span class="sxs-lookup"><span data-stu-id="7bc86-118">It does not support an error output.</span></span>  
  
## <a name="configuration-of-the-raw-file-source"></a><span data-ttu-id="7bc86-119">Configurazione dell'origine file non elaborato</span><span class="sxs-lookup"><span data-stu-id="7bc86-119">Configuration of the Raw File Source</span></span>  
 <span data-ttu-id="7bc86-120">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="7bc86-120">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="7bc86-121">Nella finestra di dialogo **Editor avanzato** sono disponibili le proprietà che è possibile impostare a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="7bc86-121">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="7bc86-122">Per ulteriori informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor avanzato** o a livello di codice, fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="7bc86-122">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="7bc86-123">Proprietà comuni</span><span class="sxs-lookup"><span data-stu-id="7bc86-123">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="7bc86-124">Proprietà personalizzate del file non elaborato</span><span class="sxs-lookup"><span data-stu-id="7bc86-124">Raw File Custom Properties</span></span>](raw-file-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="7bc86-125">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="7bc86-125">Related Tasks</span></span>  
 <span data-ttu-id="7bc86-126">Per informazioni su come impostare le proprietà del componente, vedere [Impostare le proprietà di un componente del flusso di dati](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="7bc86-126">For information about how to set the properties of the component, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="7bc86-127">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="7bc86-127">Related Content</span></span>  
  
-   <span data-ttu-id="7bc86-128">Post di blog sugli [aspetti positivi dei file non elaborati](https://www.sqlservercentral.com/blogs/31-days-of-ssis-%e2%80%93-raw-files-are-awesome-131)nel sito Web sqlservercentral.com.</span><span class="sxs-lookup"><span data-stu-id="7bc86-128">Blog entry, [Raw Files Are Awesome](https://www.sqlservercentral.com/blogs/31-days-of-ssis-%e2%80%93-raw-files-are-awesome-131), on sqlservercentral.com</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bc86-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7bc86-129">See Also</span></span>  
 <span data-ttu-id="7bc86-130">[Destinazione file non elaborato](raw-file-destination.md) </span><span class="sxs-lookup"><span data-stu-id="7bc86-130">[Raw File Destination](raw-file-destination.md) </span></span>  
 [<span data-ttu-id="7bc86-131">Flusso di dati</span><span class="sxs-lookup"><span data-stu-id="7bc86-131">Data Flow</span></span>](data-flow.md)  
  
  