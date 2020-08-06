---
title: Erstellen und Veröffentlichen einer Geschäftsregel (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- business rules [Master Data Services], creating
- creating business rules [Master Data Services]
ms.assetid: 6961d636-4d69-468e-81f7-8d0be6a4a039
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 4dfca5613a1f328e02b3fd2c7337885a23889207
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621040"
---
# <a name="create-and-publish-a-business-rule-master-data-services"></a><span data-ttu-id="ed313-102">Erstellen und Veröffentlichen einer Geschäftsregel (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="ed313-102">Create and Publish a Business Rule (Master Data Services)</span></span>
  <span data-ttu-id="ed313-103">Erstellen Sie in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]eine Geschäftsregel, um die Genauigkeit der Masterdaten sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="ed313-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a business rule to ensure the accuracy of your master data.</span></span> <span data-ttu-id="ed313-104">Nachdem Sie eine Regel erstellt haben, müssen Sie diese veröffentlichen, damit Sie sie auf Daten anwenden können.</span><span class="sxs-lookup"><span data-stu-id="ed313-104">After you create a rule, you must publish it before you can apply it to data.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ed313-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="ed313-105">Prerequisites</span></span>  
 <span data-ttu-id="ed313-106">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="ed313-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="ed313-107">Sie müssen über die Berechtigung verfügen, auf den Funktionsbereich **System Verwaltung** zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="ed313-107">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="ed313-108">Sie müssen ein Modelladministrator sein.</span><span class="sxs-lookup"><span data-stu-id="ed313-108">You must be a model administrator.</span></span> <span data-ttu-id="ed313-109">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ed313-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-create-and-publish-a-business-rule"></a><span data-ttu-id="ed313-110">So erstellen und veröffentlichen Sie eine Geschäftsregel</span><span class="sxs-lookup"><span data-stu-id="ed313-110">To create and publish a business rule</span></span>  
  
1.  <span data-ttu-id="ed313-111">Klicken Sie in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]auf **Systemverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="ed313-111">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="ed313-112">Zeigen Sie auf der Menüleiste auf **Verwalten** , und klicken Sie auf **Geschäftsregeln**.</span><span class="sxs-lookup"><span data-stu-id="ed313-112">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="ed313-113">Wählen Sie auf der Seite **Verwaltung von Geschäftsregeln** aus der Liste **Modell** ein Modell aus.</span><span class="sxs-lookup"><span data-stu-id="ed313-113">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="ed313-114">Wählen Sie aus der Liste **Entität** eine Entität aus.</span><span class="sxs-lookup"><span data-stu-id="ed313-114">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="ed313-115">Wählen Sie aus der Liste **Elementtyp** einen Typ des Elements aus, auf das die Geschäftsregel angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ed313-115">From the **Member Type** list, select a type of member for the business rule to apply to.</span></span>  
  
6.  <span data-ttu-id="ed313-116">Wählen Sie aus der Liste **Attribut** ein Attribut aus, oder behalten Sie die Standardeinstellung **Alle**bei.</span><span class="sxs-lookup"><span data-stu-id="ed313-116">From the **Attribute** list, select an attribute or leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="ed313-117">Klicken Sie auf **Geschäftsregel hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ed313-117">Click **Add business rule**.</span></span>  
  
8.  <span data-ttu-id="ed313-118">Klicken Sie auf **Ausgewählte Geschäftsregel bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="ed313-118">Click **Edit selected business rule**.</span></span>  
  
9. <span data-ttu-id="ed313-119">Erweitern Sie im Bereich **Komponenten** den Knoten **Bedingungen** .</span><span class="sxs-lookup"><span data-stu-id="ed313-119">In the **Components** pane, expand the **Conditions** node.</span></span>  
  
10. <span data-ttu-id="ed313-120">Klicken Sie auf eine Bedingung, und ziehen Sie Sie auf die Bezeichnung **Bedingungen** des Bereichs **if** .</span><span class="sxs-lookup"><span data-stu-id="ed313-120">Click a condition and drag it to the **IF** pane's **Conditions** label.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="ed313-121">Sie können Elemente aus ihrer Geschäftsregel löschen, indem Sie mit der rechten Maustaste klicken und **Löschen**auswählen.</span><span class="sxs-lookup"><span data-stu-id="ed313-121">You can delete items from your business rule by right-clicking and choosing **Delete**.</span></span>  
  
11. <span data-ttu-id="ed313-122">Klicken Sie im Bereich **Attribute** auf ein Attribut, und ziehen Sie es im Bereich **Bedingung bearbeiten** auf die Bezeichnung **Attribut auswählen** .</span><span class="sxs-lookup"><span data-stu-id="ed313-122">In the **Attributes** pane, click an attribute and drag it to the **Edit Condition** pane's **Select attribute** label.</span></span>  
  
12. <span data-ttu-id="ed313-123">Vervollständigen Sie im Bereich **Bedingung bearbeiten** alle erforderlichen Felder.</span><span class="sxs-lookup"><span data-stu-id="ed313-123">In the **Edit Condition** pane, complete any required fields.</span></span>  
  
13. <span data-ttu-id="ed313-124">Klicken Sie im Bereich **Bedingung bearbeiten** auf **Element speichern**.</span><span class="sxs-lookup"><span data-stu-id="ed313-124">In the **Edit Condition** pane, click **Save item**.</span></span>  
  
14. <span data-ttu-id="ed313-125">Erweitern Sie im Bereich **Komponenten** den Knoten **Aktionen** .</span><span class="sxs-lookup"><span data-stu-id="ed313-125">In the **Components** pane, expand the **Actions** node.</span></span>  
  
15. <span data-ttu-id="ed313-126">Klicken Sie auf eine Aktion, und ziehen Sie sie auf die Bezeichnung **Aktion** des Bereichs **THEN** .</span><span class="sxs-lookup"><span data-stu-id="ed313-126">Click an action and drag it to the **THEN** pane's **Action** label.</span></span>  
  
16. <span data-ttu-id="ed313-127">Klicken Sie im Bereich **Attribute** auf ein Attribut, und ziehen Sie es im Bereich **Aktion bearbeiten** auf die Bezeichnung **Attribut auswählen** .</span><span class="sxs-lookup"><span data-stu-id="ed313-127">In the **Attributes** pane, click an attribute and drag it to the **Edit Action** pane's **Select attribute** label.</span></span>  
  
17. <span data-ttu-id="ed313-128">Vervollständigen Sie im Bereich **Aktion bearbeiten** alle Pflichtfelder.</span><span class="sxs-lookup"><span data-stu-id="ed313-128">In the **Edit Action** pane, complete any required fields.</span></span>  
  
18. <span data-ttu-id="ed313-129">Klicken Sie im Bereich **Aktion bearbeiten** auf **Element speichern**.</span><span class="sxs-lookup"><span data-stu-id="ed313-129">In the **Edit Action** pane, click **Save item**.</span></span>  
  
19. <span data-ttu-id="ed313-130">Fügen Sie der Regel option mehrere Bedingungen hinzu.</span><span class="sxs-lookup"><span data-stu-id="ed313-130">Optionally, add multiple conditions to the rule.</span></span> <span data-ttu-id="ed313-131">Weitere Informationen finden Sie unter [Hinzufügen mehrerer Bedingungen zu einer Geschäftsregel &#40;Master Data Services&#41;](../../2014/master-data-services/add-multiple-conditions-to-a-business-rule-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ed313-131">For more information, see [Add Multiple Conditions to a Business Rule &#40;Master Data Services&#41;](../../2014/master-data-services/add-multiple-conditions-to-a-business-rule-master-data-services.md).</span></span>  
  
20. <span data-ttu-id="ed313-132">Klicken Sie auf **Zurück**.</span><span class="sxs-lookup"><span data-stu-id="ed313-132">Click **Back**.</span></span>  
  
21. <span data-ttu-id="ed313-133">Optional können Sie auf der Seite **Verwaltung von Geschäftsregeln** für die Zeile, die die Geschäftsregel enthält, auf eine Zelle in den Spalten **Name**, **Beschreibung**oder **Benachrichtigung** doppelklicken, um den Wert zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="ed313-133">Optionally, on the **Business Rules Maintenance** page, for the row that contains your business rule, double-click a cell in the **Name**, **Description**, or **Notification** column to update the value.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ed313-134">Benachrichtigungen werden nur für Regeln gesendet, die eine Überprüfungsaktion einschließen.</span><span class="sxs-lookup"><span data-stu-id="ed313-134">Notifications are sent only for rules that include a validation action.</span></span>  
  
22. <span data-ttu-id="ed313-135">Klicken Sie auf **Geschäftsregeln veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="ed313-135">Click **Publish business rules**.</span></span>  
  
23. <span data-ttu-id="ed313-136">Klicken Sie im Bestätigungsdialogfeld auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ed313-136">On the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="ed313-137">Der Status der Regel ändert sich zu **Aktiv**.</span><span class="sxs-lookup"><span data-stu-id="ed313-137">The rule's status changes to **Active**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="ed313-138">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="ed313-138">Next Steps</span></span>  
  
-   <span data-ttu-id="ed313-139">Führen Sie zum Anwenden von Geschäftsregeln auf Daten eine der folgenden Prozeduren aus:</span><span class="sxs-lookup"><span data-stu-id="ed313-139">Apply business rules to data by following one of these procedures:</span></span>  
  
    -   [<span data-ttu-id="ed313-140">Überprüfen von bestimmten Elementen auf Geschäftsregeln &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="ed313-140">Validate Specific Members against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-specific-members-against-business-rules-master-data-services.md)  
  
    -   [<span data-ttu-id="ed313-141">Überprüfen einer Version anhand von Geschäftsregeln &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="ed313-141">Validate a Version against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-a-version-against-business-rules-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="ed313-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ed313-142">See Also</span></span>  
 <span data-ttu-id="ed313-143">[Konfigurieren von Geschäftsregeln für das Senden von Benachrichtigungen &#40;Master Data Services&#41;](../../2014/master-data-services/configure-business-rules-to-send-notifications-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="ed313-143">[Configure Business Rules to Send Notifications &#40;Master Data Services&#41;](../../2014/master-data-services/configure-business-rules-to-send-notifications-master-data-services.md) </span></span>  
 <span data-ttu-id="ed313-144">[Ändern Sie den Namen einer Geschäftsregel &#40;Master Data Services&#41;](../../2014/master-data-services/change-a-business-rule-name-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="ed313-144">[Change a Business Rule Name &#40;Master Data Services&#41;](../../2014/master-data-services/change-a-business-rule-name-master-data-services.md) </span></span>  
 [<span data-ttu-id="ed313-145">Hinzufügen mehrerer Bedingungen zu einer Geschäftsregel &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="ed313-145">Add Multiple Conditions to a Business Rule &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/add-multiple-conditions-to-a-business-rule-master-data-services.md)  
  
  
