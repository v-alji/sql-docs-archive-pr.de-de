---
title: Erstellen eines domänenbasierten Attributs (MDS-Add-In für Excel) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 7b3e30dc-8f41-4a5d-8009-ae5a4426a64b
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: bda0c7f63ad380aaea5d980d2e729822ec9a3d22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607875"
---
# <a name="create-a-domain-based-attribute-mds-add-in-for-excel"></a><span data-ttu-id="d3a06-102">Erstellen eines domänenbasierten Attributs (MDS-Add-In für Excel)</span><span class="sxs-lookup"><span data-stu-id="d3a06-102">Create a Domain-based Attribute (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="d3a06-103">Im [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]können Administratoren ein domänenbasiertes Attribut erstellen, wenn sie die Werte in einer Spalte auf einen bestimmten Satz von Werten beschränken möchten.</span><span class="sxs-lookup"><span data-stu-id="d3a06-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], administrators can create a domain-based attribute when they want to constrain the values in a column to a specific set of values.</span></span>  
  
 <span data-ttu-id="d3a06-104">Die Werte können sich bereits im Arbeitsblatt befinden oder aus einer vorhandenen Entität stammen.</span><span class="sxs-lookup"><span data-stu-id="d3a06-104">The values can already be in the worksheet or they can come from an existing entity.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d3a06-105">Wenn Benutzer einen Wert in die eingeschränkte Spalte eingeben, anstatt diesen in der Liste auszuwählen, werden Fehler nach der Veröffentlichung in der Spalte **$InputStatus$** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d3a06-105">If users type a value in the constrained column, rather than selecting from the list, errors are displayed in the **$InputStatus$** column when they publish.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d3a06-106">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="d3a06-106">Prerequisites</span></span>  
 <span data-ttu-id="d3a06-107">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="d3a06-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="d3a06-108">Sie müssen über die Berechtigung verfügen, auf die Funktionsbereiche **Systemverwaltung** und **Explorer** zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="d3a06-108">You must have permission to access the **System Administration** and **Explorer** functional areas.</span></span>  
  
-   <span data-ttu-id="d3a06-109">Sie müssen ein Modelladministrator sein.</span><span class="sxs-lookup"><span data-stu-id="d3a06-109">You must be a model administrator.</span></span> <span data-ttu-id="d3a06-110">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](../administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d3a06-110">For more information, see [Administrators &#40;Master Data Services&#41;](../administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="d3a06-111">Das Modell und die Entität müssen bereits vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="d3a06-111">The model and entity must already exist.</span></span>  
  
### <a name="to-perform-this-procedure"></a><span data-ttu-id="d3a06-112">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="d3a06-112">To perform this procedure:</span></span>  
  
1.  <span data-ttu-id="d3a06-113">Laden Sie in Excel die Entität, in der die Spalte (Attribut) enthalten ist, die Sie einschränken möchten.</span><span class="sxs-lookup"><span data-stu-id="d3a06-113">In Excel, load the entity that contains the column (attribute) you want to constrain.</span></span> <span data-ttu-id="d3a06-114">Weitere Informationen finden Sie unter [Laden von Daten aus MDS in Excel](export-data-to-excel-from-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d3a06-114">For more information, see [Load Data from MDS into Excel](export-data-to-excel-from-master-data-services.md).</span></span>  
  
2.  <span data-ttu-id="d3a06-115">Klicken Sie in der Spalte, die Sie einschränken möchten, auf eine beliebige Zelle.</span><span class="sxs-lookup"><span data-stu-id="d3a06-115">Click any cell in the column you want to constrain.</span></span>  
  
3.  <span data-ttu-id="d3a06-116">Klicken Sie in der Gruppe **Modell erstellen** auf **Attributeigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="d3a06-116">In the **Build Model** group, click **Attribute Properties**.</span></span>  
  
4.  <span data-ttu-id="d3a06-117">Wählen Sie im Dialogfeld **Attributeigenschaften** in der Liste **Attributtyp** die Option **Eingeschränkte Liste (domänenbasiert)**.</span><span class="sxs-lookup"><span data-stu-id="d3a06-117">In the **Attribute Properties** dialog box, in the **Attribute type** list, choose **Constrained list (domain-based)**.</span></span>  
  
5.  <span data-ttu-id="d3a06-118">In der Liste **Attribut mit Werten auffüllen aus** :</span><span class="sxs-lookup"><span data-stu-id="d3a06-118">In the **Populate the attribute with values from** list:</span></span>  
  
    -   <span data-ttu-id="d3a06-119">Um Werte aus dem Arbeitsblatt zu verwenden, wählen Sie **die ausgewählte Spalte**aus.</span><span class="sxs-lookup"><span data-stu-id="d3a06-119">To use values from the worksheet, choose **the selected column**.</span></span> <span data-ttu-id="d3a06-120">Mit den Werten der ausgewählten Spalte wird eine neue Entität und eine neue Stagingtabelle erstellt.</span><span class="sxs-lookup"><span data-stu-id="d3a06-120">A new entity and new staging table will be created with the values from the selected column.</span></span>  
  
    -   <span data-ttu-id="d3a06-121">Wählen Sie den Namen der Entität aus, um Werte einer vorhandenen Entität zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d3a06-121">To use values from an existing entity, choose the name of the entity.</span></span>  
  
6.  <span data-ttu-id="d3a06-122">Wenn Sie im vorherigen Schritt **die ausgewählte Spalte** gewählt haben, geben Sie im Feld **Neuer Entitätsname** einen Namen für die neue Entität ein.</span><span class="sxs-lookup"><span data-stu-id="d3a06-122">If you chose **the selected column** in the previous step, in the **New entity name** box, type a name for the new entity.</span></span> <span data-ttu-id="d3a06-123">Dies kann der gleiche Name wie der Spaltenname (Attribut) sein.</span><span class="sxs-lookup"><span data-stu-id="d3a06-123">This can be the same as the column (attribute) name.</span></span>  
  
7.  <span data-ttu-id="d3a06-124">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d3a06-124">Click **OK**.</span></span> <span data-ttu-id="d3a06-125">Jede Zelle in der Spalte verfügt jetzt über eine Liste mit Werten, unter denen Benutzer wählen können.</span><span class="sxs-lookup"><span data-stu-id="d3a06-125">Each cell in the column now has a list of values for users to choose from.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="d3a06-126">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="d3a06-126">Next Steps</span></span>  
  
-   <span data-ttu-id="d3a06-127">Um Werte der eingeschränkten Liste hinzuzufügen und daraus zu löschen, laden Sie die Entität, auf der das Attribut basiert.</span><span class="sxs-lookup"><span data-stu-id="d3a06-127">To add and delete values in the constrained list, load the entity that the attribute is based on.</span></span> <span data-ttu-id="d3a06-128">Weitere Informationen zum Laden von Entitäten finden Sie unter [Laden von Daten aus MDS in Excel](export-data-to-excel-from-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d3a06-128">For more information on loading entities, see [Load Data from MDS into Excel](export-data-to-excel-from-master-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3a06-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d3a06-129">See Also</span></span>  
 <span data-ttu-id="d3a06-130">[Domänen basierte Attribute &#40;Master Data Services&#41;](../domain-based-attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="d3a06-130">[Domain-Based Attributes &#40;Master Data Services&#41;](../domain-based-attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="d3a06-131">[Erstellen Sie eine Entität &#40;MDS-Add-in für Excel&#41;](create-an-entity-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="d3a06-131">[Create an Entity &#40;MDS Add-in for Excel&#41;](create-an-entity-mds-add-in-for-excel.md) </span></span>  
 [<span data-ttu-id="d3a06-132">Erstellen eines Modells &#40;MDS-Add-In für Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="d3a06-132">Building a Model &#40;MDS Add-in for Excel&#41;</span></span>](building-a-model-mds-add-in-for-excel.md)  
  
  
