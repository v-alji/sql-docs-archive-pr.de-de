---
title: Erfordern von Attributwerten (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- business rules [Master Data Services], requiring attribute values
- attributes [Master Data Services], requiring values
ms.assetid: a360ef13-0c34-43b8-a87e-2f5d8732d30e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 42b412fc42138c5e186c6c7ad42373f20e35f3cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615420"
---
# <a name="require-attribute-values-master-data-services"></a><span data-ttu-id="3b37f-102">Erfordern von Attributwerten (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="3b37f-102">Require Attribute Values (Master Data Services)</span></span>
  <span data-ttu-id="3b37f-103">Erfordern Sie in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]Attributwerte, wenn Sie sicherstellen möchten, dass die Masterdaten vollständig sind.</span><span class="sxs-lookup"><span data-stu-id="3b37f-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], require attribute values when you want to ensure your master data is complete.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3b37f-104">Elemente, denen domänenbasierte Attributwerte fehlen, werden nicht in abgeleiteten Hierarchien angezeigt, die auf diesen Beziehungen basieren.</span><span class="sxs-lookup"><span data-stu-id="3b37f-104">Members that are missing domain-based attribute values are not displayed in derived hierarchies that are based on those relationships.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3b37f-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="3b37f-105">Prerequisites</span></span>  
 <span data-ttu-id="3b37f-106">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="3b37f-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="3b37f-107">Sie müssen über die Berechtigung verfügen, auf den Funktionsbereich **System Verwaltung** zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="3b37f-107">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="3b37f-108">Sie müssen ein Modelladministrator sein.</span><span class="sxs-lookup"><span data-stu-id="3b37f-108">You must be a model administrator.</span></span> <span data-ttu-id="3b37f-109">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="3b37f-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-require-attribute-values"></a><span data-ttu-id="3b37f-110">So erfordern Sie Attributwerte</span><span class="sxs-lookup"><span data-stu-id="3b37f-110">To require attribute values</span></span>  
  
1.  <span data-ttu-id="3b37f-111">Klicken Sie in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]auf **Systemverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="3b37f-111">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="3b37f-112">Zeigen Sie auf der Menüleiste auf **Verwalten** , und klicken Sie auf **Geschäftsregeln**.</span><span class="sxs-lookup"><span data-stu-id="3b37f-112">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="3b37f-113">Wählen Sie auf der Seite **Verwaltung von Geschäftsregeln** aus der Liste **Modell** ein Modell aus.</span><span class="sxs-lookup"><span data-stu-id="3b37f-113">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="3b37f-114">Wählen Sie aus der Liste **Entität** eine Entität aus.</span><span class="sxs-lookup"><span data-stu-id="3b37f-114">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="3b37f-115">Wählen Sie aus der Liste **Elementtyp** einen Typ des Elements aus, auf das die Geschäftsregel angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3b37f-115">From the **Member Type** list, select a type of member for the business rule to apply to.</span></span>  
  
6.  <span data-ttu-id="3b37f-116">Wählen Sie aus der Liste **Attribut** ein Attribut aus, oder behalten Sie die Standardeinstellung **Alle**bei.</span><span class="sxs-lookup"><span data-stu-id="3b37f-116">From the **Attribute** list, select an attribute or leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="3b37f-117">Klicken Sie auf **Geschäftsregel hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="3b37f-117">Click **Add business rule**.</span></span>  
  
8.  <span data-ttu-id="3b37f-118">Klicken Sie auf **Ausgewählte Geschäftsregel bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="3b37f-118">Click **Edit selected business rule**.</span></span>  
  
9. <span data-ttu-id="3b37f-119">Erweitern Sie im Bereich **Komponenten** den Knoten **Aktionen** .</span><span class="sxs-lookup"><span data-stu-id="3b37f-119">In the **Components** pane, expand the **Actions** node.</span></span>  
  
10. <span data-ttu-id="3b37f-120">Klicken Sie auf **ist erforderlich** , und ziehen Sie Sie auf die Bezeichnung **Aktion** des Bereichs **Then** .</span><span class="sxs-lookup"><span data-stu-id="3b37f-120">Click **is required** and drag it to the **THEN** pane's **Action** label.</span></span>  
  
11. <span data-ttu-id="3b37f-121">Klicken Sie im Bereich **Attribute** auf ein Attribut, und ziehen Sie es im Bereich **Aktion bearbeiten** auf die Bezeichnung **Attribut auswählen** .</span><span class="sxs-lookup"><span data-stu-id="3b37f-121">In the **Attributes** pane, click an attribute and drag it to the **Edit Action** pane's **Select attribute** label.</span></span>  
  
12. <span data-ttu-id="3b37f-122">Klicken Sie im Bereich **Aktion bearbeiten** auf **Element speichern**.</span><span class="sxs-lookup"><span data-stu-id="3b37f-122">In the **Edit Action** pane, click **Save item**.</span></span>  
  
13. <span data-ttu-id="3b37f-123">Klicken Sie auf **Zurück**.</span><span class="sxs-lookup"><span data-stu-id="3b37f-123">Click **Back**.</span></span>  
  
14. <span data-ttu-id="3b37f-124">Optional können Sie auf der Seite **Verwaltung von Geschäftsregeln** für die Zeile, die die Geschäftsregel enthält, auf eine Zelle in den Spalten **Name**, **Beschreibung**oder **Benachrichtigung** doppelklicken, um den Wert zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="3b37f-124">Optionally, on the **Business Rules Maintenance** page, for the row that contains your business rule, double-click a cell in the **Name**, **Description**, or **Notification** column to update the value.</span></span>  
  
15. <span data-ttu-id="3b37f-125">Klicken Sie auf **Geschäftsregeln veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="3b37f-125">Click **Publish business rules**.</span></span>  
  
16. <span data-ttu-id="3b37f-126">Klicken Sie im Bestätigungsdialogfeld auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3b37f-126">On the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="3b37f-127">Der Status der Regel ändert sich zu **Aktiv**.</span><span class="sxs-lookup"><span data-stu-id="3b37f-127">The rule's status changes to **Active**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="3b37f-128">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="3b37f-128">Next Steps</span></span>  
  
-   <span data-ttu-id="3b37f-129">Führen Sie zum Anwenden von Geschäftsregeln auf Daten eine der folgenden Prozeduren aus:</span><span class="sxs-lookup"><span data-stu-id="3b37f-129">Apply business rules to data by following one of these procedures:</span></span>  
  
    -   [<span data-ttu-id="3b37f-130">Überprüfen von bestimmten Elementen auf Geschäftsregeln &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="3b37f-130">Validate Specific Members against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-specific-members-against-business-rules-master-data-services.md)  
  
    -   [<span data-ttu-id="3b37f-131">Überprüfen einer Version anhand von Geschäftsregeln &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="3b37f-131">Validate a Version against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-a-version-against-business-rules-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="3b37f-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3b37f-132">See Also</span></span>  
 <span data-ttu-id="3b37f-133">[Master Data Services von Geschäftsregeln &#40;&#41;](../../2014/master-data-services/business-rules-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="3b37f-133">[Business Rules &#40;Master Data Services&#41;](../../2014/master-data-services/business-rules-master-data-services.md) </span></span>  
 [<span data-ttu-id="3b37f-134">Abgeleitete Hierarchien &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="3b37f-134">Derived Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/derived-hierarchies-master-data-services.md)  
  
  
