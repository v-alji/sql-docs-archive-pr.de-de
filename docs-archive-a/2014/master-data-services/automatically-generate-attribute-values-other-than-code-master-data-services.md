---
title: Automatisches Generieren von anderen Attributwerten als Code (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: b82f6f81-6e9c-4918-9ea9-4ab5f5d11b15
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 8db6c89bdce2a11a5a54ed3a763a7bc41bd7f1be
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621048"
---
# <a name="automatically-generate-attribute-values-other-than-code-master-data-services"></a><span data-ttu-id="c263c-102">Automatisches Generieren von anderen Attributwerten als Code (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="c263c-102">Automatically Generate Attribute Values Other Than Code (Master Data Services)</span></span>
  <span data-ttu-id="c263c-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] können Sie Werte für die Attributwerte einer Entität automatisch generieren, wenn Sie möchten, dass eine ganze Zahl jedes Mal automatisch als Wert zugewiesen werden soll, wenn Geschäftsregeln angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="c263c-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], automatically generate values for an entity's attribute values when you want an integer to be automatically assigned as the value each time business rules are applied.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c263c-104">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="c263c-104">Prerequisites</span></span>  
 <span data-ttu-id="c263c-105">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="c263c-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="c263c-106">Sie müssen über die Berechtigung verfügen, auf den Funktionsbereich **System Verwaltung** zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="c263c-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="c263c-107">Sie müssen ein Modelladministrator sein.</span><span class="sxs-lookup"><span data-stu-id="c263c-107">You must be a model administrator.</span></span> <span data-ttu-id="c263c-108">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="c263c-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="c263c-109">Ein numerisches Attribut muss vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="c263c-109">A numeric attribute must exist.</span></span> <span data-ttu-id="c263c-110">Weitere Informationen finden Sie unter [Erstellen eines numerischen Attributs &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-numeric-attribute-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="c263c-110">For more information, see [Create a Numeric Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-numeric-attribute-master-data-services.md).</span></span>  
  
### <a name="to-automatically-generate-an-attribute-value"></a><span data-ttu-id="c263c-111">So generieren Sie automatisch einen Attributwert</span><span class="sxs-lookup"><span data-stu-id="c263c-111">To automatically generate an attribute value</span></span>  
  
1.  <span data-ttu-id="c263c-112">Klicken Sie in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]auf **Systemverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="c263c-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="c263c-113">Zeigen Sie auf der Menüleiste auf **Verwalten** , und klicken Sie auf **Geschäftsregeln**.</span><span class="sxs-lookup"><span data-stu-id="c263c-113">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="c263c-114">Wählen Sie auf der Seite **Verwaltung von Geschäftsregeln** aus der Liste **Modell** ein Modell aus.</span><span class="sxs-lookup"><span data-stu-id="c263c-114">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="c263c-115">Wählen Sie aus der Liste **Entität** eine Entität aus.</span><span class="sxs-lookup"><span data-stu-id="c263c-115">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="c263c-116">Wählen Sie aus der Liste **Elementtyp** einen Typ des Elements aus, auf das die Geschäftsregel angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c263c-116">From the **Member Type** list, select a type of member for the business rule to apply to.</span></span>  
  
6.  <span data-ttu-id="c263c-117">Behalten Sie in der Liste **Attribut** die Standardeinstellung **Alle**bei.</span><span class="sxs-lookup"><span data-stu-id="c263c-117">From the **Attribute** list, leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="c263c-118">Klicken Sie auf **Geschäftsregel hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="c263c-118">Click **Add business rule**.</span></span>  
  
8.  <span data-ttu-id="c263c-119">Klicken Sie auf **Ausgewählte Geschäftsregel bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="c263c-119">Click **Edit selected business rule**.</span></span>  
  
9. <span data-ttu-id="c263c-120">Erweitern Sie im Bereich **Komponenten** den Knoten **Aktionen** .</span><span class="sxs-lookup"><span data-stu-id="c263c-120">In the **Components** pane, expand the **Actions** node.</span></span>  
  
10. <span data-ttu-id="c263c-121">Klicken Sie im Knoten „Standardwert“ auf **entspricht standardmäßig generiertem Wert**, und ziehen Sie ihn auf die Beschriftung **Aktionen** des Bereichs **THEN**.</span><span class="sxs-lookup"><span data-stu-id="c263c-121">In the Default Value node, click **defaults to a generated value** and drag it to the **THEN** pane's **Actions** label.</span></span>  
  
11. <span data-ttu-id="c263c-122">Klicken Sie im Bereich **Attribute** auf das Attribut mit dem zu generierenden Wert, und ziehen Sie es in die Beschriftung **Attribut auswählen** des Bereichs **Aktion bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="c263c-122">In the **Attributes** pane, click the attribute with the value you want to generated and drag it to the **Edit Action** pane's **Select attribute** label.</span></span>  
  
12. <span data-ttu-id="c263c-123">Geben Sie in den Feldern **Start bei** und **Erhöhen um** einen Wert ein.</span><span class="sxs-lookup"><span data-stu-id="c263c-123">Type a value in the **Start with** and **Increment by** boxes.</span></span> <span data-ttu-id="c263c-124">Wenn Elemente bereits vorhanden sind, wird der Wert auf Grundlage des höchsten vorhandenen Werts festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c263c-124">If members already exist, the value will be set based on the highest existing value.</span></span> <span data-ttu-id="c263c-125">Wenn der höchste vorhandene Wert zum Beispiel 299 beträgt und Sie **Erhöhen um** auf **1**festgelegt haben, wird der Wert des nächsten Elements auf 300 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c263c-125">For example, if the highest existing value is 299 and you set **Increment by** to **1**, the next member's value will be set to 300.</span></span>  
  
13. <span data-ttu-id="c263c-126">Klicken Sie im Bereich **Aktion bearbeiten** auf **Element speichern**.</span><span class="sxs-lookup"><span data-stu-id="c263c-126">In the **Edit Action** pane, click **Save item**.</span></span>  
  
14. <span data-ttu-id="c263c-127">Klicken Sie auf **Zurück**.</span><span class="sxs-lookup"><span data-stu-id="c263c-127">Click **Back**.</span></span>  
  
15. <span data-ttu-id="c263c-128">Optional können Sie auf der Seite **Verwaltung von Geschäftsregeln** für die Zeile, die die Geschäftsregel enthält, auf eine Zelle in den Spalten **Name**, **Beschreibung**oder **Benachrichtigung** doppelklicken, um den Wert zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="c263c-128">Optionally, on the **Business Rules Maintenance** page, for the row that contains your business rule, double-click a cell in the **Name**, **Description**, or **Notification** column to update the value.</span></span>  
  
16. <span data-ttu-id="c263c-129">Klicken Sie auf **Geschäftsregeln veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="c263c-129">Click **Publish business rules**.</span></span>  
  
17. <span data-ttu-id="c263c-130">Klicken Sie im Bestätigungsdialogfeld auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c263c-130">On the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="c263c-131">Der Status der Regel ändert sich zu **Aktiv**.</span><span class="sxs-lookup"><span data-stu-id="c263c-131">The rule's status changes to **Active**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="c263c-132">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="c263c-132">Next Steps</span></span>  
  
-   [<span data-ttu-id="c263c-133">Überprüfen von bestimmten Elementen auf Geschäftsregeln &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c263c-133">Validate Specific Members against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-specific-members-against-business-rules-master-data-services.md)  
  
-   [<span data-ttu-id="c263c-134">Überprüfen einer Version anhand von Geschäftsregeln &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c263c-134">Validate a Version against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-a-version-against-business-rules-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="c263c-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c263c-135">See Also</span></span>  
 <span data-ttu-id="c263c-136">[Automatische Code Erstellung &#40;Master Data Services&#41;](../../2014/master-data-services/automatic-code-creation-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="c263c-136">[Automatic Code Creation &#40;Master Data Services&#41;](../../2014/master-data-services/automatic-code-creation-master-data-services.md) </span></span>  
 <span data-ttu-id="c263c-137">[Master Data Services von Geschäftsregeln &#40;&#41;](../../2014/master-data-services/business-rules-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="c263c-137">[Business Rules &#40;Master Data Services&#41;](../../2014/master-data-services/business-rules-master-data-services.md) </span></span>  
 [<span data-ttu-id="c263c-138">Überprüfung &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c263c-138">Validation &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validation-master-data-services.md)  
  
  
