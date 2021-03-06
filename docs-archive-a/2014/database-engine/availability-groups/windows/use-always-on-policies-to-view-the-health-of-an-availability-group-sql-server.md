---
title: Usare i criteri AlwaysOn per visualizzare l'integrità di un gruppo di disponibilità (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 6f1bcbc3-1220-4071-8e53-4b957f5d3089
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5c4444afc2348b2407dc19c1c12761ef0251631e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724943"
---
# <a name="use-alwayson-policies-to-view-the-health-of-an-availability-group-sql-server"></a>Utilizzare i criteri AlwaysOn per visualizzare l'integrità di un gruppo di disponibilità (SQL Server)
  In questo argomento viene illustrato come determinare l'integrità operativa di un gruppo di disponibilità AlwaysOn utilizzando i criteri AlwaysOn in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] o PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]. Per informazioni sulla gestione basata su criteri AlwaysOn, vedere [criteri AlwaysOn per problemi operativi con gruppi di disponibilità AlwaysOn (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md).  
  
> [!IMPORTANT]  
>  Per i criteri AlwaysOn, i nomi delle categorie vengono utilizzati come ID. La modifica del nome di una categoria AlwaysOn causa l'interruzione della funzionalità di valutazione dell'integrità. Pertanto, i nomi di categoria AlwaysOn non devono mai essere modificati.  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> Prima di iniziare  
  
###  <a name="security"></a><a name="Security"></a> Sicurezza  
  
####  <a name="permissions"></a><a name="Permissions"></a> Autorizzazioni  
 È necessario disporre delle autorizzazioni CONNECT, VIEW SERVER STATE e VIEW ANY DEFINITION.  
  
##  <a name="using-the-alwayson-dashboard"></a><a name="SSMSProcedure"></a>Uso del dashboard AlwaysOn  
 **Per aprire il Dashboard AlwaysOn**  
  
1.  In Esplora oggetti connettersi all'istanza del server che ospita una delle repliche di disponibilità. Per visualizzare informazioni su tutte le repliche di disponibilità di un determinato gruppo, connettersi all'istanza del server che ospita la replica primaria.  
  
2.  Fare clic sul nome del server per espandere il relativo albero.  
  
3.  Espandere il nodo **Disponibilità elevata AlwaysOn** .  
  
     Fare clic con il pulsante destro del mouse sul nodo **Gruppi di disponibilità** o espandere il nodo e fare clic con il pulsante destro del mouse su un gruppo di disponibilità specifico.  
  
4.  Selezionare il comando **Mostra dashboard** .  
  
 Per informazioni su come usare il dashboard AlwaysOn, vedere [Utilizzare il Dashboard AlwaysOn &#40;SQL Server Management Studio&#41;](use-the-always-on-dashboard-sql-server-management-studio.md).  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> Uso di PowerShell  
 **Usare i criteri AlwaysOn per visualizzare l'integrità di un gruppo di disponibilità**  
  
1.  Spostarsi sulla directory (`cd`) dell'istanza del server che ospita una delle repliche di disponibilità. Per visualizzare informazioni su tutte le repliche di disponibilità di un determinato gruppo, connettersi all'istanza del server che ospita la replica primaria.  
  
2.  Usare i cmdlet seguenti:  
  
     `Test-SqlAvailabilityGroup`  
     Valuta l'integrità di un gruppo di disponibilità valutando i criteri della gestione basata su criteri di SQL Server. È necessario disporre delle autorizzazioni CONNECT, VIEW SERVER STATE e VIEW ANY DEFINITION per eseguire questo cmdlet.  
  
     Ad esempio, il comando seguente mostra tutti i gruppi di disponibilità con stato di integrità "Error" nell'istanza del server `Computer\Instance`.  
  
    ```powershell
    Get-ChildItem SQLSERVER:\Sql\Computer\Instance\AvailabilityGroups |
        Test-SqlAvailabilityGroup |
        Where-Object { $_.HealthState -eq "Error" }  
    ```  
  
     `Test-SqlAvailabilityReplica`  
     Valuta l'integrità delle repliche di disponibilità valutando i criteri della gestione basata su criteri di SQL Server. È necessario disporre delle autorizzazioni CONNECT, VIEW SERVER STATE e VIEW ANY DEFINITION per eseguire questo cmdlet.  
  
     Ad esempio, il seguente comando valuta l'integrità della replica di disponibilità denominata `MyReplica` nel gruppo di disponibilità `MyAg` e restituisce un breve riepilogo.  
  
    ```powershell
    Test-SqlAvailabilityReplica -Path SQLSERVER:\Sql\Computer\Instance\AvailabilityGroups\MyAg\AvailabilityReplicas\MyReplica  
    ```  
  
     `Test-SqlDatabaseReplicaState`  
     Valuta l'integrità di un database di disponibilità su tutte le repliche di disponibilità aggiunte valutando i criteri della gestione basata su criteri di SQL Server.  
  
     Ad esempio, il seguente comando valuta l'integrità di tutte i database di disponibilità nel gruppo di disponibilità `MyAg` e restituisce un breve riepilogo per ognuno di essi.  
  
    ```powershell
    Get-ChildItem SQLSERVER:\Sql\Computer\Instance\AvailabilityGroups\MyAg\DatabaseReplicaStates |
        Test-SqlDatabaseReplicaState  
    ```  
  
     Questi cmdlet accettano le opzioni seguenti:  
  
    |Opzione|Descrizione|  
    |------------|-----------------|  
    |`AllowUserPolicies`|Esegue i criteri utente trovati nelle categorie dei criteri AlwaysOn.|  
    |`InputObject`|Raccolta di oggetti che rappresentano gruppi di disponibilità, repliche di disponibilità o stati dei database di disponibilità. Il cmdlet calcolerà l'integrità degli oggetti specificati.|  
    |`NoRefresh`|Quando questo parametro viene impostato, il cmdlet non aggiorna manualmente gli oggetti specificati dal parametro `-Path` o `-InputObject`.|  
    |`Path`|Percorso del gruppo di disponibilità, una o più repliche di disponibilità o stato del cluster della replica di database del database di disponibilità (a seconda del cmdlet utilizzato). Questo parametro è facoltativo. Se non specificato, il valore predefinito di questo parametro sarà il percorso di lavoro corrente.|  
    |`ShowPolicyDetails`|Mostra il risultato di ogni valutazione dei criteri eseguita da questo cmdlet. Il cmdlet restituisce un oggetto per ogni valutazione dei criteri e questo oggetto contiene campi che descrivono i risultati della valutazione, ovvero se i criteri sono stati soddisfatti, il nome e la categoria dei criteri e così via.|  
  
     Ad esempio, il seguente comando `Test-SqlAvailabilityGroup` specifica il parametro `-ShowPolicyDetails` per mostrare i risultati della valutazione per ciascun criterio eseguita da questo cmdlet per ciascun criterio della gestione basata su criteri eseguito sul gruppo di disponibilità `MyAg`.  
  
    ```powershell
    Test-SqlAvailabilityGroup -Path SQLSERVER:\Sql\Computer\Instance\AvailabilityGroups\AgName -ShowPolicyDetails  
    ```  
  
    > [!NOTE]  
    >  Per visualizzare la sintassi di un cmdlet, utilizzare il cmdlet `Get-Help` nell'ambiente [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell. Per altre informazioni, vedere [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).  
  
 **Per impostare e utilizzare il provider PowerShell per SQL Server**  
  
-   [Provider PowerShell per SQL Server](../../../powershell/sql-server-powershell-provider.md)  
  
-   [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> Contenuto correlato  
 **SQL Server Blog del team AlwaysOn-monitoraggio dell'integrità AlwaysOn con PowerShell:**  
  
-   [Pagina relativa alla prima parte riguardante la panoramica su cmdlet di base](https://docs.microsoft.com/archive/blogs/sqlalwayson/monitoring-alwayson-health-with-powershell-part-1-basic-cmdlet-overview)  
  
-   [Pagina relativa alla seconda parte riguardante l'utilizzo avanzato di cmdlet](https://docs.microsoft.com/archive/blogs/sqlalwayson/the-alwayson-health-model-part-2-extending-the-health-model)  
  
-   [Pagina relativa alla terza parte riguardante un'applicazione di monitoraggio semplice](https://docs.microsoft.com/archive/blogs/sqlalwayson/monitoring-alwayson-health-with-powershell-part-3-a-simple-monitoring-application)  
  
-   [Pagina relativa alla quarta parte riguardante l'integrazione con SQL Server Agent](https://docs.microsoft.com/archive/blogs/sqlalwayson/monitoring-alwayson-health-with-powershell-part-4-integration-with-sql-server-agent)  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md)   
 [Amministrazione di un gruppo di disponibilità &#40;SQL Server&#41;](administration-of-an-availability-group-sql-server.md)   
 [Monitoraggio di Gruppi di disponibilità &#40;SQL Server&#41;](monitoring-of-availability-groups-sql-server.md)   
 [Criteri AlwaysOn per problemi operativi con gruppi di disponibilità AlwaysOn (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md) 
