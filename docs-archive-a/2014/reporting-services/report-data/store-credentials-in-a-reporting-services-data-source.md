---
title: Archiviare le credenziali in un'origine dati di Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 09/23/2015
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- credentials [Reporting Services]
- security [Analysis Services], data sources
- stored credentials [Reporting Services]
- data sources [Reporting Services], stored credentials
ms.assetid: dc700922-97fa-4b30-9547-05bbbec4f09c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fccf8669d1f39d19a26b443ffcead8e86db66a34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635436"
---
# <a name="store-credentials-in-a-reporting-services-data-source"></a>Store Credentials in a Reporting Services Data Source
  È possibile configurare le credenziali archiviate usate da un server di report di [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] per accedere ai dati esterni di un report. Le credenziali archiviate vengono usate se il report viene eseguito in modo automatico, ad esempio una sottoscrizione di [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] che pubblica un report come messaggio di posta elettronica. Il server di report recupera e usa le credenziali quando viene pianificata o attivata l'elaborazione del report. Questo argomento illustra la configurazione delle credenziali archiviate per i server di report sia in modalità nativa che in modalità SharePoint.

||
|-|
|**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Modalità nativa &#124; [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] modalità SharePoint|

 **Contenuto dell'argomento:**

-   [Configurare le credenziali archiviate per un'origine dati specifica del report (modalità nativa)](#bkmk_stored_credentials_data_source_native)

-   [Configurare le credenziali archiviate per un'origine dati specifica del report (modalità SharePoint)](#bkmk_stored_credentials_data_source_sharepoint)

-   [Configurare le credenziali archiviate per un'origine dati condivisa (modalità nativa)](#bkmk_stored_credentials_shared_data_source_native)

-   [Configurare le credenziali archiviate per un'origine dati condivisa (modalità SharePoint)](#bkmk_stored_credentials_shared_data_source_sharepoint)

##  <a name="security-policy-requirements-for-stored-credentials"></a><a name="bkmk_top"></a> Requisiti dei criteri di sicurezza per le credenziali archiviate
 ![as_powerpivot_refresh_sss_set_key](../../analysis-services/media/as-powerpivot-refresh-sss-set-key.gif "as_powerpivot_refresh_sss_set_key") È necessario che l'account usato per le credenziali archiviate sia configurato per uno dei criteri di sicurezza seguenti nel server di report. È consigliabile selezionare i criteri con il livello minimo di autorizzazioni per l'ambiente.

1.  **Consenti accesso locale**. Per altre informazioni, vedere [Consenti accesso locale](https://technet.microsoft.com/library/cc756809\(v=WS.10\).aspx).

2.  **Accesso come processo batch**. Per altre informazioni, vedere [Accesso come processo batch](https://technet.microsoft.com/library/cc755659\(v=ws.10\).aspx).

3.  Per informazioni generali sui criteri, vedere [Modificare un'impostazione di sicurezza in un oggetto Criteri di gruppo](https://technet.microsoft.com/library/cc736516\(v=ws.10\).aspx).

##  <a name="configure-stored-credentials-for-a-report-specific-data-source-native-mode"></a><a name="bkmk_stored_credentials_data_source_native"></a> Configurare le credenziali archiviate per un'origine dati specifica del report (modalità nativa)

1.  In Gestione report in modalità nativa passare alla cartella che contiene il report. Fare clic sul menu di scelta rapida elemento del menu di scelta rapida ![in Gestione report per gli elementi SSRS](../media/ssrs-report-manager-item-context-menu.png "menu di scelta rapida in Gestione report per gli elementi ssrs").

2.  Fare clic su **Gestisci** , quindi su **Origini dati**.

3.  Fare clic su **Origine dei dati personalizzata**.

4.  Nell'elenco **Tipo di origine dati** selezionare l'estensione per l'elaborazione dati usata per elaborare i dati dell'origine dati.

5.  Per **stringa di connessione**specificare la stringa di connessione utilizzata dal server di report per la connessione all'origine dati. Nell'esempio seguente viene illustrata una stringa di connessione utilizzata per la connessione al [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database:

    ```
    data source=<servername>;initial catalog=AdventureWorks2012
    ```

6.  Per **Connetti tramite**selezionare **Credenziali archiviate in modo protetto nel server di report**.

7.  Digitare un nome utente e una password.

    -   Se l'account è un account utente di dominio di Windows, specificarlo nel formato: \<domain> \\<account \> , quindi selezionare **Usa come credenziali di Windows per la connessione all'origine dati.**

    -   Se il nome utente e la password sono credenziali del database, non selezionare **Usa come credenziali di Windows per la connessione all'origine dei dati**. Se il server di database supporta la rappresentazione o la delega, selezionare **Rappresenta l'utente autenticato dopo che è stata stabilita una connessione all'origine dei dati**.

8.  Fare clic su **Applica**.

     ![Icona freccia usata con il collegamento Torna all'inizio](../../2014-toc/media/uparrow16x16.gif "Icona freccia usata con il collegamento Torna all'inizio") [Requisiti dei criteri di sicurezza per le credenziali archiviate](#bkmk_top)

##  <a name="configure-stored-credentials-for-a-report-specific-data-source-sharepoint-mode"></a><a name="bkmk_stored_credentials_data_source_sharepoint"></a>Configurare le credenziali archiviate per un'origine dati specifica del report (modalità SharePoint)

1.  Passare alla raccolta documenti che contiene il report, quindi fare clic sul menu Apri ![menu di scelta rapida della raccolta documenti per gli elementi ssrs](../media/ssrs-sharepoint-item-context-menu.png "menu di scelta rapida della raccolta documenti per gli elementi ssrs").

2.  Fare clic sul secondo menu Apri ![menu di scelta rapida della raccolta documenti per gli elementi ssrs](../media/ssrs-sharepoint-item-context-menu.png "menu di scelta rapida della raccolta documenti per gli elementi ssrs") e quindi su **Gestisci origini dati**.

3.  Fare clic sul nome dell'origine dati **personalizzata** da configurare con le credenziali archiviate.

4.  Nell'elenco **Tipo di origine dati** selezionare l'estensione per l'elaborazione dati usata per elaborare i dati dell'origine dati.

5.  Per **stringa di connessione**specificare la stringa di connessione utilizzata dal server di report per la connessione all'origine dati. Nell'esempio seguente viene illustrata una stringa di connessione utilizzata per la connessione al [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database:

    ```
    data source=<servername>;initial catalog=AdventureWorks2012
    ```

6.  Per **Credenziali**selezionare **Credenziali archiviate**.

7.  Digitare un **nome utente** e una **password**.

    -   Se l'account è un account utente di dominio di Windows, specificarlo nel formato: \<domain> \\<account \> , quindi selezionare **Usa come credenziali di Windows per la connessione all'origine dati.**

    -   Se il nome utente e la password sono credenziali del database, non selezionare **Usa come credenziali di Windows**. Se il server di database supporta la rappresentazione o la delega, è possibile selezionare **Imposta contesto di esecuzione su questo account**.

8.  Fare clic su **OK**.

     ![Icona freccia usata con il collegamento Torna all'inizio](../../2014-toc/media/uparrow16x16.gif "Icona freccia usata con il collegamento Torna all'inizio") [Requisiti dei criteri di sicurezza per le credenziali archiviate](#bkmk_top)

##  <a name="configure-stored-credentials-for-a-shared-data-source-native-mode"></a><a name="bkmk_stored_credentials_shared_data_source_native"></a> Configurare le credenziali archiviate per un'origine dati condivisa (modalità nativa)

1.  In Gestione report in modalità nativa passare all'origine dati condivisa. ![Icona Origine dati condivisa](../media/hlp-16datasource.png "Icona Origine dati condivisa")

2.  Fare clic sul menu di scelta rapida menu di scelta rapida ![in Gestione report per gli elementi SSRS](../media/ssrs-report-manager-item-context-menu.png "menu di scelta rapida in Gestione report per gli elementi ssrs") e quindi fare clic su **Gestisci**.

3.  Nell'elenco **Tipo di origine dati** specificare l'estensione per l'elaborazione dati usata per elaborare i dati dell'origine dati.

4.  Per **stringa di connessione**specificare la stringa di connessione utilizzata dal server di report per la connessione all'origine dati. [!INCLUDE[msCoName](../../../includes/msconame-md.md)] consiglia di evitare di specificare credenziali nella stringa di connessione.

     Nell'esempio seguente viene illustrata una stringa di connessione utilizzata per connettersi al [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database locale:

    ```
    data source=<localservername>; initial catalog=AdventureWorks2012
    ```

5.  Digitare un nome utente e una password.

    -   Se l'account è un account utente di dominio di Windows, specificarlo nel formato: \<domain> \\<account \> , quindi selezionare **Usa come credenziali di Windows per la connessione all'origine dati.**

    -   Se il nome utente e la password sono credenziali del database, non selezionare **Usa come credenziali di Windows per la connessione all'origine dei dati**. Se il server di database supporta la rappresentazione o la delega, selezionare **Rappresenta l'utente autenticato dopo che è stata stabilita una connessione all'origine dei dati**.

6.  Fare clic su **Applica**.

     ![Icona freccia usata con il collegamento Torna all'inizio](../../2014-toc/media/uparrow16x16.gif "Icona freccia usata con il collegamento Torna all'inizio") [Requisiti dei criteri di sicurezza per le credenziali archiviate](#bkmk_top)

##  <a name="configure-stored-credentials-for-a-shared-data-source-sharepoint-mode"></a><a name="bkmk_stored_credentials_shared_data_source_sharepoint"></a>Configurare le credenziali archiviate per un'origine dati condivisa (modalità SharePoint)

1.  Nella raccolta documenti passare all'origine dei dati condivisa.![Icona dell'origine dei dati condivisa](../media/hlp-16datasource.png "Icona Origine dati condivisa")

2.  Fare clic sul menu di scelta rapida ![menu di scelta rapida della raccolta documenti per gli elementi ssrs](../media/ssrs-sharepoint-item-context-menu.png "menu di scelta rapida della raccolta documenti per gli elementi ssrs") e quindi sul secondo menu di scelta rapida ![menu di scelta rapida della raccolta documenti per gli elementi ssrs](../media/ssrs-sharepoint-item-context-menu.png "menu di scelta rapida della raccolta documenti per gli elementi ssrs").

3.  Fare clic su **Modifica definizione origine dati**.

4.  Nell'elenco **Tipo di origine dati** specificare l'estensione per l'elaborazione dati usata per elaborare i dati dell'origine dati.

5.  Per **stringa di connessione**specificare la stringa di connessione utilizzata dal server di report per la connessione all'origine dati. [!INCLUDE[msCoName](../../../includes/msconame-md.md)] consiglia di evitare di specificare credenziali nella stringa di connessione.

     Nell'esempio seguente viene illustrata una stringa di connessione utilizzata per connettersi al [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database locale:

    ```
    data source=<localservername>; initial catalog=AdventureWorks2012
    ```

6.  Digitare un nome utente e una password.

    -   Se l'account è un account utente di dominio di Windows, specificarlo nel formato: \<domain> \\<account \> , quindi selezionare **Usa come credenziali di Windows.**

    -   Se il nome utente e la password sono credenziali del database, non selezionare **Usa come credenziali di Windows**. Se il server di database supporta la rappresentazione o la delega, è possibile selezionare **Imposta contesto di esecuzione sull'account seguente**.

7.  Fare clic su **OK**.

     ![Icona freccia usata con il collegamento Torna all'inizio](../../2014-toc/media/uparrow16x16.gif "Icona freccia usata con il collegamento Torna all'inizio") [Requisiti dei criteri di sicurezza per le credenziali archiviate](#bkmk_top)

## <a name="see-also"></a>Vedere anche
 [Specificare le credenziali e le informazioni di connessione per le origini dei dati del report configurare le](../../integration-services/connection-manager/data-sources.md) [proprietà delle origini dati per un report &#40;Gestione report&#41;](configure-data-source-properties-for-a-report-report-manager.md) [creare, eliminare o modificare un'origine dati condivisa &#40;Gestione report&#41;&#40;](../create-delete-or-modify-a-shared-data-source-report-manager.md) [pagina delle proprietà delle origini](../data-sources-properties-page-report-manager.md) dati gestione report&#41;&#40;[nuova pagina origine dati](../new-data-source-page-report-manager.md) Gestione report&#41;


