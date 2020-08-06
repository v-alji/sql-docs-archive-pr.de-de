---
title: Erstellen einer Entität (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- entities [Master Data Services], creating
- creating entities [Master Data Services]
ms.assetid: d9a6a51e-7b53-4785-a118-3baeb7ca2d48
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 7cefdedd07ee248f12b3b17337878934a2b1aa84
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622188"
---
# <a name="create-an-entity-master-data-services"></a><span data-ttu-id="12475-102">Erstellen einer Entität (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="12475-102">Create an Entity (Master Data Services)</span></span>
  <span data-ttu-id="12475-103">Erstellen Sie in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]eine Entität, die Elemente und ihre Attribute enthält.</span><span class="sxs-lookup"><span data-stu-id="12475-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create an entity to contain members and their attributes.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="12475-104">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="12475-104">Prerequisites</span></span>  
 <span data-ttu-id="12475-105">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="12475-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="12475-106">Sie müssen über die Berechtigung verfügen, auf den Funktionsbereich **System Verwaltung** zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="12475-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="12475-107">Sie müssen ein Modelladministrator sein.</span><span class="sxs-lookup"><span data-stu-id="12475-107">You must be a model administrator.</span></span> <span data-ttu-id="12475-108">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="12475-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="12475-109">Es muss ein Modell vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="12475-109">A model must exist.</span></span> <span data-ttu-id="12475-110">Weitere Informationen finden Sie unter [Erstellen eines Modells &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-model-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="12475-110">For more information, see [Create a Model &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-model-master-data-services.md).</span></span>  
  
### <a name="to-create-an-entity"></a><span data-ttu-id="12475-111">So erstellen Sie eine Entität</span><span class="sxs-lookup"><span data-stu-id="12475-111">To create an entity</span></span>  
  
1.  <span data-ttu-id="12475-112">Klicken Sie in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]auf **Systemverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="12475-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="12475-113">Zeigen Sie auf der Seite **Modellansicht** auf der Menüleiste auf **Verwalten** , und klicken Sie auf **Entitäten**.</span><span class="sxs-lookup"><span data-stu-id="12475-113">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="12475-114">Wählen Sie auf der Seite **Entitätsverwaltung** aus der Liste **Modell** ein Modell aus.</span><span class="sxs-lookup"><span data-stu-id="12475-114">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="12475-115">Klicken Sie auf **Entität hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="12475-115">Click **Add entity**.</span></span>  
  
5.  <span data-ttu-id="12475-116">Geben Sie im Feld **Entitäts Name** den Namen der Entität ein.</span><span class="sxs-lookup"><span data-stu-id="12475-116">In the **Entity name** box, type the name of the entity.</span></span>  
  
6.  <span data-ttu-id="12475-117">Geben Sie im Feld **Name für Stagingtabellen** einen Namen für die Stagingtabelle ein.</span><span class="sxs-lookup"><span data-stu-id="12475-117">In the **Name for staging tables** box, type a name for the staging table.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="12475-118">Verwenden Sie den Modellnamen als einen Teil des Stagingtabellennamens, z.B. *Modelname_Entityname*.</span><span class="sxs-lookup"><span data-stu-id="12475-118">Use the model name as part of the staging table name, for example *Modelname_Entityname*.</span></span> <span data-ttu-id="12475-119">Dies erleichtert die Suche nach den Tabellen in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="12475-119">This makes the tables easier to find in the database.</span></span> <span data-ttu-id="12475-120">Weitere Informationen zu den Stagingtabellen finden Sie unter [Data Import &#40;Master Data Services&#41;](overview-importing-data-from-tables-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="12475-120">For more information about the staging tables, see [Data Import &#40;Master Data Services&#41;](overview-importing-data-from-tables-master-data-services.md).</span></span>  
  
7.  <span data-ttu-id="12475-121">Optional.</span><span class="sxs-lookup"><span data-stu-id="12475-121">Optional.</span></span> <span data-ttu-id="12475-122">Aktivieren Sie das Kontrollkästchen **Codewerte automatisch erstellen** .</span><span class="sxs-lookup"><span data-stu-id="12475-122">Select the **Create Code values automatically** check box.</span></span> <span data-ttu-id="12475-123">Weitere Informationen finden Sie unter [automatische Code Erstellung &#40;Master Data Services&#41;](../../2014/master-data-services/automatic-code-creation-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="12475-123">For more information, see [Automatic Code Creation &#40;Master Data Services&#41;](../../2014/master-data-services/automatic-code-creation-master-data-services.md).</span></span>  
  
8.  <span data-ttu-id="12475-124">Wählen Sie in der Liste **explizite Hierarchien und Sammlungen aktivieren** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="12475-124">From the **Enable explicit hierarchies and collections** list, select one of the following options:</span></span>  
  
    -   <span data-ttu-id="12475-125">**Nein**.</span><span class="sxs-lookup"><span data-stu-id="12475-125">**No**.</span></span> <span data-ttu-id="12475-126">Wählen Sie diese Option aus, wenn Sie die Entität für explizite Hierarchien und Auflistungen nicht aktivieren müssen.</span><span class="sxs-lookup"><span data-stu-id="12475-126">Select this option if you do not need to enable the entity for explicit hierarchies and collections.</span></span> <span data-ttu-id="12475-127">Sie können dies später nach Bedarf ändern.</span><span class="sxs-lookup"><span data-stu-id="12475-127">You can change this later if needed.</span></span>  
  
    -   <span data-ttu-id="12475-128">**Ja**.</span><span class="sxs-lookup"><span data-stu-id="12475-128">**Yes**.</span></span> <span data-ttu-id="12475-129">Wählen Sie diese Option aus, wenn Sie die Entität für explizite Hierarchien und Auflistungen aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="12475-129">Select this option when you want to enable the entity for explicit hierarchies and collections.</span></span> <span data-ttu-id="12475-130">Geben Sie im Feld **Name der expliziten Hierarchie** einen Namen ein.</span><span class="sxs-lookup"><span data-stu-id="12475-130">In the **Explicit hierarchy name** box, type a name.</span></span> <span data-ttu-id="12475-131">Wählen Sie optional erforderliche **Hierarchie aus (alle Blatt Elemente werden eingeschlossen** , um die explizite Hierarchie als erforderliche Hierarchie zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="12475-131">Optionally, select **Mandatory hierarchy (all leaf members are included** to make the explicit hierarchy a mandatory hierarchy.</span></span>  
  
9. <span data-ttu-id="12475-132">Klicken Sie auf **Entität speichern**.</span><span class="sxs-lookup"><span data-stu-id="12475-132">Click **Save entity**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="12475-133">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="12475-133">Next Steps</span></span>  
  
-   [<span data-ttu-id="12475-134">Erstellen eines Textattributs &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="12475-134">Create a Text Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-text-attribute-master-data-services.md)  
  
-   [<span data-ttu-id="12475-135">Erstellen eines domänenbasierten Attributs &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="12475-135">Create a Domain-Based Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md)  
  
-   [<span data-ttu-id="12475-136">Erstellen eines Dateiattributs &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="12475-136">Create a File Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-file-attribute-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="12475-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="12475-137">See Also</span></span>  
 <span data-ttu-id="12475-138">[Entitäten &#40;Master Data Services&#41;](../../2014/master-data-services/entities-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="12475-138">[Entities &#40;Master Data Services&#41;](../../2014/master-data-services/entities-master-data-services.md) </span></span>  
 <span data-ttu-id="12475-139">[Explizite Hierarchien &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="12475-139">[Explicit Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md) </span></span>  
 <span data-ttu-id="12475-140">[Ändern eines Entitäts namens &#40;Master Data Services&#41;](edit-an-entity-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="12475-140">[Change an Entity Name &#40;Master Data Services&#41;](edit-an-entity-master-data-services.md) </span></span>  
 [<span data-ttu-id="12475-141">Löschen einer Entität &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="12475-141">Delete an Entity &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-an-entity-master-data-services.md)  
  
  
