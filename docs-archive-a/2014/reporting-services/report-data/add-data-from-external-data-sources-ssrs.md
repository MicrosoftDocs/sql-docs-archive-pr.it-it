---
title: Aggiungere dati da origini dati esterne (SSRS)
ms.prod: sql-server-2014
ms.technology: reporting-services
ms.topic: conceptual
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
ms.custom: ''
ms.date: 04/27/2017
ms.openlocfilehash: 1f1df02d99ebbf21ba7e769f3704aebdbb29cc40
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623846"
---
# <a name="add-data-from-external-data-sources-ssrs"></a>Aggiungere dati da origini dati esterne (SSRS)

Per recuperare dati da un'origine dati esterna, utilizzare una connessione dati. Le informazioni di connessione dati vengono in genere fornite dal proprietario dell'origine dati esterna che è responsabile della concessione delle autorizzazioni e di specificare i tipi di credenziali da utilizzare. Le informazioni di connessione dati vengono salvate come un'origine dati del report. Il tipo di origine dati consente di specificare quale estensione per i dati utilizzare per recuperare i dati.  

##  <a name="understanding-data-access-technology"></a><a name="DataAccess"></a> Informazioni sulla tecnologia di accesso ai dati  

Per recuperare dati per un set di dati del report sono necessari più livelli di software per l'accesso ai dati. Nell'elenco seguente viene fornita una semplice descrizione del funzionamento dei report con tecnologie di accesso ai dati:  

-   **Applicazione e interfaccia utente** Applicazione Generatore report che consente di creare un'origine dati, aggiungere un riferimento a un'origine dati condivisa, aggiungere un set di dati condiviso o aggiungere una parte del report che include le origini dati e i set di dati da cui dipende.  

-   **Elementi della definizione del report** Le origini dati e i set di dati fanno parte della definizione del report. Dopo la pubblicazione di un report in un server di report, le origini dati e i set di dati condivisi vengono gestiti in modo indipendente dalla definizione del report.  

  -   **Origine dati e origine dati condivisa** Parte di una definizione del report che include le informazioni sul tipo di estensione per l'elaborazione dati, le informazioni di connessione e l'autenticazione.  

  -   **Set di dati e raccolta campi** Parte di una definizione del report che include la query, la raccolta campi e i tipi di dati dei campi.  

-   **Estensioni per i dati Reporting Services** Estensioni per i dati incorporate installate con Generatore report. Un'estensione per i dati fornisce la funzionalità che gestisce l'autenticazione, le aggregazioni server e i parametri multivalore.  

-   **Provider di dati** Software che gestisce la connessione e il recupero di dati dall'origine dati esterna. Il provider di dati definisce la sintassi della stringa di connessione. La maggior parte delle estensioni per i dati viene compilata su un livello provider di dati.  

-   **Origine dati esterna** Posizione da cui vengono recuperati i dati del report, ad esempio un database, un file, un cubo o un servizio Web.  

> [!NOTE]  
>  Quando non si è connessi a un server di report, è possibile scegliere tra le estensioni per i dati installate con Generatore report. Si accede ai dati come utente singolo utilizzando le credenziali del computer. Quando si è connessi a un server di report, è possibile scegliere tra le estensioni per i dati installate nel server di report. Si accede ai dati come uno degli utenti che eseguono il report e si utilizzano le credenziali nel server di report. Per altre informazioni, vedere [Specifica di credenziali in Generatore report](../specify-credentials-in-report-builder.md).  

##  <a name="understanding-report-data"></a><a name="ReportData"></a> Informazioni sui dati del report  
Nella sua forma più semplice, un report visualizza i dati di un set di dati in un'area dati nella pagina del report, ovvero in una singola tabella, in un grafico, in una matrice o in un altro tipo di area dati del report. I dati di un set di dati del report provengono dal primo set di risultati restituito da un singolo comando di query eseguito dall'accesso in sola lettura a un'origine dati esterna. Ogni area dati può essere espansa in base alle esigenze per visualizzare tutti i dati del set di dati.  

I dati di un set di dati sono soprattutto tabulari. Le colonne sono date dai campi della query del set di dati. Le righe corrispondono alle righe del set di risultati. È possibile utilizzare i tipi di dati generalizzati seguenti in un report:  

-   Dati rettangolari. Dati di un set di risultati che dispongono dello stesso numero di colonne in ogni riga.  

-   I dati gerarchici sono supportati come un set di righe bidimensionale.  

  -   Le gerarchie incomplete, dove esiste un numero diverso di colonne per ogni riga di dati, non sono supportate. Per alcune estensioni per i dati, questo fatto ha alcune implicazioni.  

  -   Le estensioni per i dati che vengono utilizzate con origini dati multidimensionali utilizzano il protocollo XML for Analysis e recuperano i dati come set di righe bidimensionale e non come set di celle.  

  -   L'estensione per i dati XML rende automaticamente bidimensionali i dati XML da utilizzare in un report. Se la prima istanza di un elemento XML non include tutti gli attributi o tutti i sottoelementi, i dati potrebbero non essere disponibili come dati del report.  

-   I dati ricorsivi sono supportati. Un set di risultati che contiene una gerarchia di dati ricorsivi include tutte le informazioni sulla struttura della gerarchia in un set di risultati rettangolare. Ad esempio, la struttura di relazioni tra i dipendenti di una società può essere rappresentata da una tabella che include due colonne: un dipendente e un responsabile. Ogni responsabile è anch'egli un dipendente con un responsabile. Il massimo dirigente contiene in genere un identificatore Null o di altro tipo a indicare che questo dipendente non ha un responsabile.  



##  <a name="working-with-data-types"></a><a name="DataTypes"></a>Utilizzo dei tipi di dati  
Quando si crea un set di dati, per i tipi di dati dei campi viene eseguito il mapping a un subset di tipi di dati CLR (Common Language Runtime) da [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]. I tipi di dati di cui non è possibile eseguire il mapping in modo chiaro vengono restituiti come stringhe. Per altre informazioni sull'uso dei tipi dei dati dei campi, vedere [Raccolta di campi del set di dati &#40;Generatore report e SSRS&#41;](dataset-fields-collection-report-builder-and-ssrs.md). Quando si crea un parametro, il tipo di dati deve essere supportato dalla definizione del report. Per altre informazioni sull'esecuzione del mapping dei tipi di dati dal provider di dati a un parametro del report, vedere [Tipi di dati nelle espressioni &#40;Generatore report e SSRS&#41;](../report-design/expressions-report-builder-and-ssrs.md).  



##  <a name="how-to-topics"></a><a name="HowTo"></a>Procedure  
In questa sezione sono contenute istruzioni dettagliate per l'utilizzo di connessioni dati, origini dati e set di dati.  

[Aggiungere e verificare una connessione dati o un'origine dati &#40;Generatore report e SSRS&#41;](add-and-verify-a-data-connection-report-builder-and-ssrs.md)  

[Creare un set di dati condiviso o un set di dati incorporato &#40;Generatore report e SSRS&#41;](create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md)  

[Aggiungere un filtro a un set di dati &#40;Generatore report e SSRS&#41;](add-a-filter-to-a-dataset-report-builder-and-ssrs.md)  

## <a name="in-this-section"></a><a name="InThisSection"></a> Contenuto della sezione  

Negli argomenti seguenti vengono fornite informazioni su ogni estensione per i dati predefinita.  

|Argomento|Tipo di origine dati|  
|-----------|----------------------|  
|[Tipo di connessione SQL Server &#40;SSRS&#41;](sql-server-connection-type-ssrs.md)|[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|[Tipo di connessione Analysis Services per MDX &#40;SSRS&#41;](analysis-services-connection-type-for-mdx-ssrs.md)|[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]|  
|[Tipo di connessione PowerPivot &#40;&#41;SSRS](power-pivot-connection-type-ssrs.md)|[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]|  
|[Tipo di connessione Elenco Microsoft SharePoint &#40;SSRS&#41;](sharepoint-list-connection-type-ssrs.md)|[!INCLUDE[msCoName](../../includes/msconame-md.md)] Elenco SharePoint|  
|[Tipo di connessione SQL Azure &#40;SSRS&#41;](sql-azure-connection-type-ssrs.md)|[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssSDS](../../includes/sssds-md.md)]|  
|[Tipo di connessione SQL Server Parallel Data Warehouse &#40;SSRS&#41;](sql-server-parallel-data-warehouse-connection-type-ssrs.md)|[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDWfull](../../includes/ssdwfull-md.md)]|  
|[Tipo di connessione SAP NetWeaver BI &#40;SSRS&#41;](sap-netweaver-bi-connection-type-ssrs.md)|SAP NetWeaver BI|  
|[Tipo di connessione Hyperion Essbase &#40;SSRS&#41;](hyperion-essbase-connection-type-ssrs.md)|Hyperion Essbase|  
|[Tipo di connessione OLE DB &#40;SSRS&#41;](ole-db-connection-type-ssrs.md)|OLE DB|  
|[Tipo di connessione ODBC &#40;SSRS&#41;](odbc-connection-type-ssrs.md)|ODBC|  
|[Tipo di connessione XML &#40;SSRS&#41;](xml-connection-type-ssrs.md)|XML|  

## <a name="related-sections"></a><a name="Related"></a>Sezioni correlate  

In queste sezioni della documentazione sono incluse informazioni concettuali approfondite sui dati dei report, nonché le informazioni necessarie sulle procedure per definire, personalizzare e usare parti di un report correlate ai dati.  

|Argomento|Descrizione|  
|-----------|-----------------|  
|[Aggiungere dati a un report &#40;Generatore report e SSRS&#41;](report-datasets-ssrs.md)|Viene fornita una panoramica sull'accesso ai dati del report.|  
|[Connessioni dati, origini dati e stringhe di connessione in Generatore report](../data-connections-data-sources-and-connection-strings-in-report-builder.md)|Vengono fornite informazioni sulle connessioni dati e sulle origini dati.|  
|[Set di dati condivisi e incorporati del report &#40;Generatore report e SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md)|Vengono fornite informazioni sui set di dati incorporati e condivisi.|  
|[Raccolta di campi del set di dati &#40;Generatore report e SSRS&#41;](dataset-fields-collection-report-builder-and-ssrs.md)|Vengono fornite informazioni sulla raccolta di campi di set di dati generata dalla query.|  
|[Origini dati supportate da Reporting Services &#40;SSRS&#41;](../create-deploy-and-manage-mobile-and-paginated-reports.md) nella documentazione relativa a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] inclusa nella [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [documentazione online](https://go.microsoft.com/fwlink/?linkid=121312) di .|Vengono fornite informazioni dettagliate sul supporto delle piattaforme e delle versioni per ogni estensione per i dati.|  
|[Cenni preliminari sulle estensioni per l'elaborazione dati](../extensions/data-processing/data-processing-extensions-overview.md) nella documentazione relativa a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] inclusa nella [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [di](https://go.microsoft.com/fwlink/?linkid=121312).|Vengono fornite informazioni dettagliate destinate agli utenti avanzati sulle estensioni per i dati.|  

## <a name="see-also"></a>Vedere anche  

- [Aggiungere dati a un report &#40;Generatore report e SSRS&#41;](report-datasets-ssrs.md)
- [Finestre di progettazione query &#40;Generatore report&#41;](../query-designers-report-builder.md)