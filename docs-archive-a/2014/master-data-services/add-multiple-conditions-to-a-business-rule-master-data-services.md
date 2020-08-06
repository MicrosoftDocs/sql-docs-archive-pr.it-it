---
title: Aggiungere più condizioni a una regola di business (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- business rules [Master Data Services], multiple conditions
ms.assetid: 5f0f6958-6cf2-444b-bdcd-05b887637a0b
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c62b8dfa4f459958d12bd384b85aa74bef382b21
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635105"
---
# <a name="add-multiple-conditions-to-a-business-rule-master-data-services"></a><span data-ttu-id="a013f-102">Aggiungere più condizioni a una regola business (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="a013f-102">Add Multiple Conditions to a Business Rule (Master Data Services)</span></span>
  <span data-ttu-id="a013f-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]aggiungere più condizioni **AND** o **OR** a una regola di business quando si vuole creare una regola più complessa.</span><span class="sxs-lookup"><span data-stu-id="a013f-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], add multiple **AND** or **OR** conditions to a business rule when you want a more complex rule.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a013f-104">Se si crea una regola di business che usa l'operatore **OR** , considerare la possibilità di creare una regola separata per ogni istruzione condizionale che può essere valutata indipendentemente.</span><span class="sxs-lookup"><span data-stu-id="a013f-104">If you create a business rule that uses the **OR** operator, consider creating a separate rule for each conditional statement that can be evaluated independently.</span></span> <span data-ttu-id="a013f-105">È quindi possibile escludere regole in base alle esigenze, offrendo maggiore flessibilità e una più facile risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="a013f-105">You can then exclude rules as needed, providing more flexibility and easier troubleshooting.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a013f-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="a013f-106">Prerequisites</span></span>  
 <span data-ttu-id="a013f-107">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="a013f-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="a013f-108">È necessario disporre di autorizzazione per accedere all'area funzionale **Amministrazione sistema** .</span><span class="sxs-lookup"><span data-stu-id="a013f-108">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="a013f-109">È necessario essere un amministratore del modello.</span><span class="sxs-lookup"><span data-stu-id="a013f-109">You must be a model administrator.</span></span> <span data-ttu-id="a013f-110">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="a013f-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="a013f-111">È necessario che sia presente una regola business.</span><span class="sxs-lookup"><span data-stu-id="a013f-111">A business rule must exist.</span></span> <span data-ttu-id="a013f-112">Per altre informazioni, vedere [Creare e pubblicare una regola di business &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="a013f-112">For more information, see [Create and Publish a Business Rule &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md).</span></span>  
  
### <a name="to-add-multiple-conditions-to-a-business-rule"></a><span data-ttu-id="a013f-113">Per aggiungere più condizioni a una regola business</span><span class="sxs-lookup"><span data-stu-id="a013f-113">To add multiple conditions to a business rule</span></span>  
  
1.  <span data-ttu-id="a013f-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], fare clic su **Amministrazione sistema**.</span><span class="sxs-lookup"><span data-stu-id="a013f-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="a013f-115">Dalla barra dei menu scegliere **Gestisci** e fare clic su **Regole business**.</span><span class="sxs-lookup"><span data-stu-id="a013f-115">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="a013f-116">Nella pagina **Manutenzione regola business** selezionare un modello dall'elenco **Modello** .</span><span class="sxs-lookup"><span data-stu-id="a013f-116">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="a013f-117">Dall'elenco **Entità** selezionare un'entità.</span><span class="sxs-lookup"><span data-stu-id="a013f-117">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="a013f-118">Dall'elenco **tipo di membro** selezionare un tipo di membro.</span><span class="sxs-lookup"><span data-stu-id="a013f-118">From the **Member Type** list, select a type of member.</span></span>  
  
6.  <span data-ttu-id="a013f-119">Dall'elenco **Attributo** selezionare un attributo o lasciare inalterata l'impostazione predefinita **Tutti**.</span><span class="sxs-lookup"><span data-stu-id="a013f-119">From the **Attribute** list, select an attribute or leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="a013f-120">Fare clic sulla riga della regola business che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="a013f-120">Click the row for the business rule you want to edit.</span></span>  
  
8.  <span data-ttu-id="a013f-121">Fare clic su **Modifica regola business selezionata**.</span><span class="sxs-lookup"><span data-stu-id="a013f-121">Click **Edit selected business rule**.</span></span>  
  
9. <span data-ttu-id="a013f-122">Nel riquadro **componenti** espandere il nodo **operatori logici** .</span><span class="sxs-lookup"><span data-stu-id="a013f-122">In the **Components** pane, expand the **Logical Operators** node.</span></span>  
  
10. <span data-ttu-id="a013f-123">Fare clic su **and** o **or** e trascinarlo sull'etichetta **e** del riquadro **if** .</span><span class="sxs-lookup"><span data-stu-id="a013f-123">Click **AND** or **OR** and drag it to the **IF** pane's **AND** label.</span></span>  
  
11. <span data-ttu-id="a013f-124">Nel riquadro **Componenti** espandere il nodo **Condizioni** .</span><span class="sxs-lookup"><span data-stu-id="a013f-124">In the **Components** pane, expand the **Conditions** node.</span></span>  
  
12. <span data-ttu-id="a013f-125">Fare clic su una condizione e trascinarla nel riquadro **if** , nell'etichetta **and** o **or** del passaggio 10.</span><span class="sxs-lookup"><span data-stu-id="a013f-125">Click a condition and drag it to **IF** pane, to the **AND** or **OR** label from step 10.</span></span>  
  
13. <span data-ttu-id="a013f-126">Nel riquadro **attributi** fare clic su un attributo e trascinarlo sull'etichetta **Seleziona attributo** del riquadro **Modifica condizione** .</span><span class="sxs-lookup"><span data-stu-id="a013f-126">In the **Attributes** pane, click an attribute and drag it to the **Edit Condition** pane's **Select attribute** label.</span></span>  
  
14. <span data-ttu-id="a013f-127">Nel riquadro **Modifica condizione** completare tutti i campi obbligatori.</span><span class="sxs-lookup"><span data-stu-id="a013f-127">In the **Edit Condition** pane, complete any required fields.</span></span>  
  
15. <span data-ttu-id="a013f-128">Nel riquadro **Modifica condizione** fare clic su **Salva elemento**.</span><span class="sxs-lookup"><span data-stu-id="a013f-128">In the **Edit Condition** pane, click **Save item**.</span></span>  
  
16. <span data-ttu-id="a013f-129">Facoltativamente, per aggiungere altre condizioni, dal riquadro **componenti** trascinare **and** o **or su any** **and** o or nel **riquadro** **if** .</span><span class="sxs-lookup"><span data-stu-id="a013f-129">Optionally, to add more conditions, from the **Components** pane, drag **AND** or **OR** to any **AND** or **OR** in the **IF** pane.</span></span> <span data-ttu-id="a013f-130">Seguire quindi i passaggi da 13 a 15.</span><span class="sxs-lookup"><span data-stu-id="a013f-130">Then follow steps 13-15.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="a013f-131">Per eliminare una condizione, fare clic sul nome della condizione e nel riquadro **Modifica condizione** fare clic su **Elimina elemento**.</span><span class="sxs-lookup"><span data-stu-id="a013f-131">To delete a condition, click the name of the condition and in the **Edit Condition** pane, click **Delete item**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a013f-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a013f-132">See Also</span></span>  
 <span data-ttu-id="a013f-133">[Regole business &#40;Master Data Services&#41;](../../2014/master-data-services/business-rules-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="a013f-133">[Business Rules &#40;Master Data Services&#41;](../../2014/master-data-services/business-rules-master-data-services.md) </span></span>  
 <span data-ttu-id="a013f-134">[Modificare il nome di una regola business &#40;Master Data Services&#41;](../../2014/master-data-services/change-a-business-rule-name-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="a013f-134">[Change a Business Rule Name &#40;Master Data Services&#41;](../../2014/master-data-services/change-a-business-rule-name-master-data-services.md) </span></span>  
 [<span data-ttu-id="a013f-135">Configurare le regole di business per l'invio di notifiche &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="a013f-135">Configure Business Rules to Send Notifications &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/configure-business-rules-to-send-notifications-master-data-services.md)  
  
  