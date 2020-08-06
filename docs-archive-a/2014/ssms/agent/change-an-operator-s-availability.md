---
title: Modificare la disponibilità di un operatore | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, operators
- canceling operators
- reactivating operators
- removing operators
- deleting operators
- available operators [SQL Server]
- dropping operators
- jobs [SQL Server Agent], operators
- notifications [SQL Server], job status
- disabling operators
- operators (users) [Database Engine], changing availability with Management Studio
ms.assetid: 10d58b92-b67b-47e2-af9c-9f9fd6968bba
author: stevestein
ms.author: sstein
ms.openlocfilehash: fb369ea6a2d1edf1ed8f4377b627fb1ba7339a03
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637599"
---
# <a name="change-an-operator39s-availability"></a><span data-ttu-id="2493d-102">Modificare la disponibilità di un operatore</span><span class="sxs-lookup"><span data-stu-id="2493d-102">Change an Operator&#39;s Availability</span></span>
  <span data-ttu-id="2493d-103">In questo argomento viene descritto come modificare la pianificazione di un operatore relativa alla ricezione di notifiche degli avvisi in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2493d-103">This topic describes how to change an operator's schedule for receiving alert notifications in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="2493d-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="2493d-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2493d-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="2493d-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2493d-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="2493d-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2493d-107">**Per modificare la disponibilità di un operatore utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="2493d-107">**To change an operator's availability, using:**</span></span>  
  
     [<span data-ttu-id="2493d-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2493d-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2493d-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2493d-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2493d-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="2493d-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2493d-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="2493d-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2493d-112">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="2493d-112">Permissions</span></span>  
 <span data-ttu-id="2493d-113">Solo i membri del ruolo predefinito del server **sysadmin** possono modificare gli operatori.</span><span class="sxs-lookup"><span data-stu-id="2493d-113">Only members of the **sysadmin** fixed server role can edit operators.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2493d-114">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2493d-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-change-an-operators-availability"></a><span data-ttu-id="2493d-115">Per modificare la disponibilità di un operatore</span><span class="sxs-lookup"><span data-stu-id="2493d-115">To change an operator's availability</span></span>  
  
1.  <span data-ttu-id="2493d-116">In **Esplora oggetti**fare clic sul segno più per espandere il server che contiene l'operatore da abilitare o disabilitare.</span><span class="sxs-lookup"><span data-stu-id="2493d-116">In **Object Explorer**, click the plus sign to expand server that contains the operator that you want to enable or disable.</span></span>  
  
2.  <span data-ttu-id="2493d-117">Fare clic sul segno più per espandere **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="2493d-117">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="2493d-118">Fare clic sul segno più per espandere la cartella **Operatori** .</span><span class="sxs-lookup"><span data-stu-id="2493d-118">Click the plus sign to expand the **Operators** folder.</span></span>  
  
4.  <span data-ttu-id="2493d-119">Fare clic con il pulsante destro del mouse sull'operatore che si vuole abilitare o disabilitare, selezionare **Proprietà**e fare clic sulla scheda **Generale** .</span><span class="sxs-lookup"><span data-stu-id="2493d-119">Right-click the operator that you want to enable or disable and select **Properties**, then click the **General** tab.</span></span>  
  
5.  <span data-ttu-id="2493d-120">Nella finestra di dialogo**proprietà** _operator_name_selezionare o deselezionare la casella di controllo **abilitato** .</span><span class="sxs-lookup"><span data-stu-id="2493d-120">In the _operator_name_**Properties** dialog box, select or clear the **Enabled** check box.</span></span>  
  
6.  <span data-ttu-id="2493d-121">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="2493d-121">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2493d-122">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2493d-122">Using Transact-SQL</span></span>  
  
#### <a name="to-change-an-operators-availability"></a><span data-ttu-id="2493d-123">Per modificare la disponibilità di un operatore</span><span class="sxs-lookup"><span data-stu-id="2493d-123">To change an operator's availability</span></span>  
  
1.  <span data-ttu-id="2493d-124">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2493d-124">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2493d-125">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="2493d-125">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2493d-126">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="2493d-126">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- disables the 'Fran??ois Ajenstat' operator  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_update_operator   
        @name = N'Fran??ois Ajenstat',  
        @enabled = 0;  
    GO  
    ```  
  
 <span data-ttu-id="2493d-127">Per ulteriori informazioni, vedere [sp_update_operator &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-update-operator-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2493d-127">For more information, see [sp_update_operator &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-operator-transact-sql).</span></span>  
  
  
