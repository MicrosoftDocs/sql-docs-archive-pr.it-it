---
title: URL nei file di configurazione (Gestione configurazione SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- URL configuration [Reporting Services]
ms.assetid: 4f5e7fe0-b5b1-4665-93d4-80dce12d6b14
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 19b4c49d8a02d07797ea4b97a4eb4f9981343226
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623891"
---
# <a name="urls-in-configuration-files--ssrs-configuration-manager"></a>URL nei file di configurazione (Gestione configurazione SSRS)
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] archivia le impostazioni delle applicazioni in un file RSReportServer.config. All'interno di questo file sono incluse le impostazioni di configurazione per gli URL e le prenotazioni URL. Tali impostazioni di configurazione hanno regole di modifica e scopi molto diversi. Se si è soliti modificare i file di configurazione per ottimizzare una distribuzione, questo argomento può risultare utile per comprendere il modo in cui viene utilizzata ogni impostazione URL.  
  
## <a name="url-settings-in-rsreportserverconfig-file"></a>Impostazioni URL nel file RSReportServer.config  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] archivia gli URL per l'accesso alle applicazioni e ai report e per connettere componenti front-end Web a un server di report back-end.  
  
#### <a name="urls-for-application-access"></a>URL per l'accesso alle applicazioni  
 Gli URL vengono utilizzati per accedere al servizio Web ReportServer e a Gestione report. Per configurare gli URL, è necessario utilizzare lo strumento di configurazione di Reporting Services. Lo strumento crea le prenotazioni URL per ogni applicazione in HTTP.SYS e aggiunge voci per gli URL nella sezione `URLReservations` di RSReportServer.config.  
  
-   Per visualizzare le descrizioni di ogni elemento della `URLReservations` sezione, vedere [file di configurazione RSReportServer](../report-server/rsreportserver-config-configuration-file.md) nella [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] documentazione online di.  
  
-   Per ulteriori informazioni sulla sintassi dell' `UrlString` elemento, vedere [sintassi di prenotazione URL &#40;SSRS Configuration Manager&#41;](url-reservation-syntax-ssrs-configuration-manager.md).  
  
-   Per indicazioni su come configurare gli URL per l'accesso alle applicazioni, vedere [Configurare un URL &#40;Gestione configurazione SSRS&#41;](configure-a-url-ssrs-configuration-manager.md).  
  
#### <a name="urls-for-report-access"></a>URL per l'accesso ai report  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] include un'estensione per il recapito tramite posta elettronica del server di report che è possibile usare per inviare collegamenti o allegati dei report. Quando viene recapitato un report, viene creato un collegamento al report. L'estensione per il recapito tramite posta elettronica del server di report utilizza l'impostazione `UrlRoot` nel file di configurazione per creare il collegamento. `UrlRoot` viene inoltre utilizzato per risolvere collegamenti in un report visualizzabile generato tramite l'elaborazione automatica di report.  
  
 L'elemento `UrlRoot` viene specificato automaticamente nel file RSReportServer.config quando si configurano gli URL per l'accesso alle applicazioni. Se si modifica tale valore nel file di configurazione, è necessario specificare un indirizzo URL valido di un servizio Web ReportServer connesso a un database del server di report contenente i report che si desidera recapitare. È possibile specificare solo un elemento `UrlRoot` per una singola istanza del server di report, in quanto nel file RSReportServer.config può essere presente solo una voce `UrlRoot` per ogni istanza del server di report specifica. Se si dispone di più URL riservati per il servizio Web ReportServer, è necessario scegliere uno dei valori disponibili per `UrlRoot`.  
  
 Nella maggior parte dei casi non è necessario modificare `UrlRoot`. Tuttavia, se si accede al server di report tramite un URL completo e non è stato configurato un URL che utilizza un'intestazione host per il nome del sito completo, è necessario modificare manualmente il RSReportServer.config per impostare l'URL del `UrlRoot` server di report completo che verrà utilizzato per il rendering del report, ad esempio `https://www.adventure-works.com/mywebapp/reportserver` .  
  
#### <a name="urls-connecting-report-manager-and-web-parts-to-the-report-server-web-service"></a>URL per la connessione di Gestione report e delle web part al servizio Web ReportServer  
 Gestione report e le web part di SharePoint 2.0 per Reporting Services sono componenti front-end Web che si connettono a un server di report. Gli URL utilizzati per la connessione a un server di report back-end includono gli elementi seguenti:  
  
-   `ReportServerUrl` (utilizzato da Gestione report)  
  
-   `ReportServerExternalUrl` (utilizzato dalle web part)  
  
> [!NOTE]  
>  Nelle versioni precedenti di Reporting Services è incluso l'elemento `ReportServerVirtualDirectory`. Questo valore è obsoleto in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] e versioni successive. Se è stata aggiornata un'installazione esistente e si utilizza un file di configurazione che contiene questa impostazione, il server di report non sarà più in grado di leggere tale valore.  
  
 Nella tabella seguente viene fornito un riepilogo di tutti gli URL che è possibile specificare in un file di configurazione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .  
  
|Impostazione|Uso|Descrizione|  
|-------------|-----------|-----------------|  
|`ReportServerUrl`|Facoltativa. Questo elemento non è incluso nel file RSReportServer.config a meno che non lo si aggiunga manualmente. Impostare questo elemento solo per configurare uno degli scenari seguenti:<br /><br /> Gestione report fornisce accesso front-end Web a un servizio Web ReportServer in esecuzione in un computer diverso o in un'istanza diversa nello stesso computer.<br /><br /> Si dispone di più URL per un server di report e si desidera che Gestione report utilizzi un URL specifico.<br /><br /> Si dispone di un URL specifico per il server di report che si desidera venga utilizzato da tutte le connessioni di Gestione report.<br /><br /> È possibile, ad esempio, abilitare l'accesso di Gestione report per tutti i computer in rete, ma fare comunque in modo che Gestione report si connetta al report tramite una connessione locale. In questo caso, è possibile configurare `ReportServerUrl` su " http://localhost/reportserver ".<br /><br /> <br /><br /> Per istruzioni su come implementare questi scenari, vedere [configurare Gestione report &#40;modalità nativa&#41;](../report-server/configure-web-portal.md) nella [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] documentazione online di.|Questo valore specifica un URL del servizio Web ReportServer e viene letto dall'applicazione Gestione report all'avvio. Se tale valore è impostato, Gestione report si connetterà al server di report specificato nell'URL.<br /><br /> Per impostazione predefinita, Gestione report fornisce accesso front-end Web al servizio Web ReportServer eseguito nella stessa istanza del server di report di Gestione report. Se, tuttavia, si desidera utilizzare Gestione report con un servizio Web ReportServer che fa parte di un'altra istanza o che viene eseguito in un'istanza in un computer diverso, è possibile impostare l'URL per fare in modo che Gestione report si connetta al servizio Web ReportServer esterno.<br /><br /> Se nel server di report a cui si esegue la connessione è installato un certificato SSL (Secure Sockets Layer), il valore di `ReportServerUrl` deve essere impostato sul nome del server registrato per il certificato. Se viene visualizzato il messaggio di errore "Connessione sottostante chiusa: Impossibile stabilire una relazione di trust per il canale sicuro SSL/TLS", impostare `ReportServerUrl` sul nome di dominio completo del server per cui è stato emesso il certificato SSL. Se ad esempio il certificato è registrato per **https:\//adventure-works.com.onlinesales**, l'URL del server di report sarà **https:\//adventure-works.com.onlinesales/reportserver**.|  
|`ReportServerExternalUrl`|Facoltativa. Questo elemento non è incluso nel file RSReportServer.config a meno che non lo si aggiunga manualmente.<br /><br /> Impostare questo elemento solo se si utilizzano le web part di SharePoint 2.0 e si desidera che gli utenti siano in grado di recuperare un report e aprirlo in una nuova finestra del browser.<br /><br /> Aggiungere <`ReportServerExternalUrl`> sotto l' `ReportServerUrl` elemento <>, quindi impostarlo su un nome di server di report completo che viene risolto in un'istanza del server di report quando si accede in una finestra del browser distinta. Non eliminare <`ReportServerUrl`>.<br /><br /> Nell'esempio seguente viene illustrata la sintassi:<br /><br /> `<ReportServerExternalUrl>http://myserver/reportserver</ReportServerExternalUrl>`|Questo valore viene utilizzato dalle web part di SharePoint 2.0.<br /><br /> Nelle versioni precedenti è consigliabile impostare questo valore per distribuire Generatore report in un server di report che si interfaccia a Internet. Si tratta di un scenario di distribuzione non testato. Se questa impostazione è stata utilizzata in passato per supportare l'accesso a Generatore report tramite Internet, è consigliabile valutare una strategia alternativa.|  
  
## <a name="see-also"></a>Vedere anche  
 [Configurare gli URL del server di report &#40;Gestione configurazione SSRS&#41;](configure-report-server-urls-ssrs-configuration-manager.md)   
 [Configurare un URL &#40;Gestione configurazione SSRS&#41;](configure-a-url-ssrs-configuration-manager.md)  
  
  
