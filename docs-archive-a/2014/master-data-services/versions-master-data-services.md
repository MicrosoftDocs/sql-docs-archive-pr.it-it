---
title: Versioni (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- version flags [Master Data Services], about version flags
- versions [Master Data Services]
- version flags [Master Data Services]
- versions [Master Data Services], version flags
ms.assetid: 752ec96d-53d7-4160-8ed2-92e0324645f3
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 6f8b55a32cdf2a5aabad38ee3d0d4154c2ad6a6f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624256"
---
# <a name="versions-master-data-services"></a>Versioni (Master Data Services)
  In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]è possibile creare più versioni dei dati master all'interno di un modello. È possibile bloccare le versioni mentre si convalidano i dati ed è possibile eseguire il commit dopo la convalida dei dati. Le versioni di cui si è eseguito il commit costituiscono un record controllabile di modifiche. Ogni versione creata contiene tutti i membri, i valori di attributo, i membri della gerarchia, le relazioni della gerarchia e le raccolte per il modello.  
  
## <a name="when-to-use-versions"></a>Situazioni in cui utilizzare le versioni  
 Utilizzare le versioni per gli scopi seguenti:  
  
-   Gestire un record controllabile dei dati master man mano che vengono modificati nel tempo.  
  
-   Impedire agli utenti di apportare modifiche garantendo al contempo la validità di tutti i dati rispetto alle regole business.  
  
-   Bloccare l'utilizzo di un modello da parte dei sistemi di sottoscrizione.  
  
-   Testare gerarchie diverse senza implementarle immediatamente.  
  
> [!NOTE]  
>  Quando si modifica la struttura del modello, ad esempio quando si crea una nuova entità o un nuovo attributo basato su dominio, la modifica apportata si applica a tutte le versioni. Se si visualizza una versione precedente del modello, l'entità o l'attributo viene visualizzato, ma i dati non sono presenti.  
  
## <a name="version-flags"></a>Flag di versione  
 Quando una versione è pronta per gli utenti o per un sistema di sottoscrizione, è possibile impostare un flag per identificare la versione. È possibile spostare tale flag da una versione all'altra in base alle necessità. I flag consentono a utenti e sistemi di sottoscrizione di identificare la versione di un modello da utilizzare.  
  
## <a name="workflow-for-version-management"></a>Flusso di lavoro per la gestione versioni  
 Usare il flusso di lavoro seguente per la gestione delle versioni:  
  
1.  Una versione iniziale viene creata automaticamente quando si crea un modello e si popola il database [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] con i dati master dell'azienda. In base alle autorizzazioni, gli utenti hanno la possibilità di apportare modifiche a tale versione, se necessario.  
  
2.  Quando si desidera eseguire il commit di una versione di un modello, bloccare la versione in modo che solo gli amministratori di modelli siano in grado di aggiornare i dati. Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](administrators-master-data-services.md). Se vengono configurate notifiche, verrà inviata una notifica tramite posta elettronica agli amministratori di modelli ogni volta che lo stato della versione viene modificato. Per altre informazioni, vedere [Configurare notifiche di posta elettronica &#40;Master Data Services&#41;](../../2014/master-data-services/configure-email-notifications-master-data-services.md).  
  
3.  Applicare regole business ai dati della versione bloccata ed esaminare gli eventuali problemi di convalida. Se necessario, è possibile immettere le informazioni mancanti o ripristinare la transazione che ha causato il problema. È inoltre possibile sbloccare la versione per consentire agli utenti di apportare modifiche.  
  
4.  Al termine della convalida di tutti i dati, eseguire il commit della versione e contrassegnarla per l'utilizzo da parte dei sistemi di sottoscrizione. Non è possibile apportare modifiche a una versione di cui è stato eseguito il commit.  
  
5.  Copiare la versione di cui è stato eseguito il commit e avvisare gli utenti della possibilità di iniziare a lavorare in una nuova versione del modello.  
  
## <a name="sequential-or-simultaneous-versions"></a>Versioni sequenziali o simultanee  
 È possibile creare versioni sequenziali o simultanee del modello.  
  
-   **Versioni sequenziali.** Ogni volta che si esegue il commit di una versione, è possibile creare una nuova copia e assegnare alla versione il successivo numero sequenziale. È ad esempio possibile copiare la **Versione 7** del modello e assegnare alla copia il nome **Versione 8**.  
  
-   **Versioni simultanee.** Creare versioni simultanee del modello quando si desidera utilizzare due o più versioni dei dati contemporaneamente. Questa possibilità è utile quando si verificano riorganizzazioni o fusioni aziendali che coincidono con il normale svolgimento delle attività e si desidera determinare se i nuovi dati master si integrano nelle strutture esistenti.  
  
    > [!NOTE]  
    >  Un'impostazione in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] determina se è possibile copiare tutte le versioni o solo quelle di cui è stato eseguito il commit. Per creare versioni simultanee è necessario configurare [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] per consentire all'utente di copiare tutte le versioni. Questa impostazione è disponibile anche nella tabella Impostazioni sistema. Per altre informazioni, vedere [Impostazioni di sistema &#40;Master Data Services&#41;](../../2014/master-data-services/system-settings-master-data-services.md).  
  
## <a name="related-tasks"></a>Attività correlate  
  
|Descrizione dell'attività|Argomento|  
|----------------------|-----------|  
|Modificare il nome di una versione esistente.|[Modificare il nome di una versione &#40;Master Data Services&#41;](../../2014/master-data-services/change-a-version-name-master-data-services.md)|  
|Bloccare una versione così solo gli amministratori possono modificare i dati.|[Bloccare una versione &#40;Master Data Services&#41;](../../2014/master-data-services/lock-a-version-master-data-services.md)|  
|Sbloccare una versione così solo gli amministratori possono modificare i dati.|[Sbloccare una versione &#40;Master Data Services&#41;](../../2014/master-data-services/unlock-a-version-master-data-services.md)|  
|Eseguire il commit di una versione dopo la convalida di tutti i dati.|[Eseguire il commit di una versione &#40;Master Data Services&#41;](../../2014/master-data-services/commit-a-version-master-data-services.md)|  
|Creare un nuovo flag per contrassegnare una versione.|[Creare un flag di versione &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-version-flag-master-data-services.md)|  
|Modificare il nome di un flag di versione esistente.|[Modificare il nome di un flag di versione &#40;Master Data Services&#41;](../../2014/master-data-services/change-a-version-flag-name-master-data-services.md)|  
|Assegnare un flag esistente a una versione.|[Assegnare un flag a una versione &#40;Master Data Services&#41;](../../2014/master-data-services/assign-a-flag-to-a-version-master-data-services.md)|  
|Creare una nuova copia di una versione esistente|[Copiare una versione &#40;Master Data Services&#41;](../../2014/master-data-services/copy-a-version-master-data-services.md)|  
|Eliminare una versione esistente.|[Eliminare una versione &#40;Master Data Services&#41;](../../2014/master-data-services/delete-a-version-master-data-services.md)|  
  
## <a name="related-content"></a>Contenuto correlato  
  
-   [Invertire una transazione &#40;Master Data Services&#41;](../../2014/master-data-services/reverse-a-transaction-master-data-services.md)  
  
-   [Notifiche &#40;Master Data Services&#41;](../../2014/master-data-services/notifications-master-data-services.md)  
  
-   [Regole di business &#40;Master Data Services&#41;](../../2014/master-data-services/business-rules-master-data-services.md)  
  
  
