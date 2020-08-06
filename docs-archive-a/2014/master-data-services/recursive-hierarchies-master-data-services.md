---
title: Rekursive Hierarchien (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- recursive hierarchies [Master Data Services]
- hierarchies [Master Data Services], recursive hierarchies
ms.assetid: 9408c6ea-d9c4-4a0b-8a1b-1457fb6944af
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 3c149d500ce1499ad36247d5e32bb6f2d55b4250
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621537"
---
# <a name="recursive-hierarchies-master-data-services"></a><span data-ttu-id="4518e-102">Rekursive Hierarchien (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="4518e-102">Recursive Hierarchies (Master Data Services)</span></span>
  <span data-ttu-id="4518e-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]ist eine rekursive Hierarchie ist eine abgeleitete Hierarchie, die eine rekursive Beziehung einschließt.</span><span class="sxs-lookup"><span data-stu-id="4518e-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], a recursive hierarchy is a derived hierarchy that includes a recursive relationship.</span></span> <span data-ttu-id="4518e-104">Eine rekursive Beziehung ist vorhanden, wenn eine Entität über ein domänenbasiertes Attribut auf Grundlage der Entität selbst verfügt.</span><span class="sxs-lookup"><span data-stu-id="4518e-104">A recursive relationship exists when an entity has a domain-based attribute based on the entity itself.</span></span>

## <a name="recursive-hierarchy-example"></a><span data-ttu-id="4518e-105">Beispiel für eine rekursive Hierarchie</span><span class="sxs-lookup"><span data-stu-id="4518e-105">Recursive Hierarchy Example</span></span>
 <span data-ttu-id="4518e-106">Ein typisches Beispiel für eine rekursive Hierarchie ist eine Organisationsstruktur.</span><span class="sxs-lookup"><span data-stu-id="4518e-106">A typical recursive hierarchy example is an organizational structure.</span></span> <span data-ttu-id="4518e-107">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]erstellen Sie dazu eine Entität "Employee" mit einem domänenbasierten Attribut "Manager".</span><span class="sxs-lookup"><span data-stu-id="4518e-107">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], you would do this by creating an Employee entity with a domain-based attribute called Manager.</span></span> <span data-ttu-id="4518e-108">Das Manager-Attribut wird aus der Liste der Mitarbeiter aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="4518e-108">The Manager attribute is populated from the list of employees.</span></span> <span data-ttu-id="4518e-109">In dieser Beispielorganisation können alle Mitarbeiter Manager sein.</span><span class="sxs-lookup"><span data-stu-id="4518e-109">In this sample organization, all employees can be managers.</span></span>

 <span data-ttu-id="4518e-110">![mds_conc_recursive_table_w_data](../../2014/master-data-services/media/mds-conc-recursive-table-w-data.gif "mds_conc_recursive_table_w_data")</span><span class="sxs-lookup"><span data-stu-id="4518e-110">![mds_conc_recursive_table_w_data](../../2014/master-data-services/media/mds-conc-recursive-table-w-data.gif "mds_conc_recursive_table_w_data")</span></span>

 <span data-ttu-id="4518e-111">Sie können eine abgeleitete Hierarchie erstellen, die die Beziehung zwischen der Employee-Entität und dem domänenbasierten Attribut "Manager" hervorhebt.</span><span class="sxs-lookup"><span data-stu-id="4518e-111">You can create a derived hierarchy that highlights the relationship between the Employee entity and the Manager domain-based attribute.</span></span>

 <span data-ttu-id="4518e-112">![mds_conc_recursive_UI_structure](../../2014/master-data-services/media/mds-conc-recursive-ui-structure.gif "mds_conc_recursive_UI_structure")</span><span class="sxs-lookup"><span data-stu-id="4518e-112">![mds_conc_recursive_UI_structure](../../2014/master-data-services/media/mds-conc-recursive-ui-structure.gif "mds_conc_recursive_UI_structure")</span></span>

 <span data-ttu-id="4518e-113">Um jedes Element nur einmal in die Hierarchie einzuschließen, können Sie NULL-Beziehungen verankern.</span><span class="sxs-lookup"><span data-stu-id="4518e-113">To include each member in the hierarchy only once, you can anchor null relationships.</span></span> <span data-ttu-id="4518e-114">Wenn Sie dies tun, werden Elemente mit leeren domänenbasierten Attributwerten auf der obersten Ebene der Hierarchie angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4518e-114">When you do, members with blank domain-based attribute values are displayed at the top level of the hierarchy.</span></span>

 <span data-ttu-id="4518e-115">![mds_conc_recursive_UI_example_anchored](../../2014/master-data-services/media/mds-conc-recursive-ui-example-anchored.gif "mds_conc_recursive_UI_example_anchored")</span><span class="sxs-lookup"><span data-stu-id="4518e-115">![mds_conc_recursive_UI_example_anchored](../../2014/master-data-services/media/mds-conc-recursive-ui-example-anchored.gif "mds_conc_recursive_UI_example_anchored")</span></span>

 <span data-ttu-id="4518e-116">Wenn Sie keine NULL-Beziehungen verankern, werden Elemente mehrmals eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="4518e-116">If you do not anchor null relationships, members are included multiple times.</span></span> <span data-ttu-id="4518e-117">Alle Elemente werden auf der obersten Ebene angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4518e-117">All members are displayed at the top level.</span></span> <span data-ttu-id="4518e-118">Sie werden auch unter den Elementen angezeigt, deren Attribute sie sind.</span><span class="sxs-lookup"><span data-stu-id="4518e-118">They are also displayed under members of which they are attributes.</span></span>

 <span data-ttu-id="4518e-119">![mds_conc_recursive_UI_example_nonanchored](../../2014/master-data-services/media/mds-conc-recursive-ui-example-nonanchored.gif "mds_conc_recursive_UI_example_nonanchored")</span><span class="sxs-lookup"><span data-stu-id="4518e-119">![mds_conc_recursive_UI_example_nonanchored](../../2014/master-data-services/media/mds-conc-recursive-ui-example-nonanchored.gif "mds_conc_recursive_UI_example_nonanchored")</span></span>

 <span data-ttu-id="4518e-120">In diesem Beispiel befindet sich Marcia auf der obersten Ebene.</span><span class="sxs-lookup"><span data-stu-id="4518e-120">In this example, Marcia is at the top level.</span></span> <span data-ttu-id="4518e-121">Sie ist kein Manager von Mitarbeitern, da sie nicht als domänenbasierter Attributwert für andere Employee-Elemente verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4518e-121">She is not the manager of any employees because she is not used as a domain-based attribute value for any other Employee members.</span></span> <span data-ttu-id="4518e-122">Robert dagegen hat unter sich eine Ebene, da Marcia Robert als Managerattributwert hat.</span><span class="sxs-lookup"><span data-stu-id="4518e-122">Robert, in contrast, has a level beneath him because Marcia has Robert as her Manager attribute value.</span></span>

## <a name="rules"></a><span data-ttu-id="4518e-123">Regeln</span><span class="sxs-lookup"><span data-stu-id="4518e-123">Rules</span></span>

-   <span data-ttu-id="4518e-124">Eine abgeleitete Hierarchie kann höchstens eine rekursive Beziehung aufweisen.</span><span class="sxs-lookup"><span data-stu-id="4518e-124">A derived hierarchy cannot contain more than one recursive relationship.</span></span> <span data-ttu-id="4518e-125">Sie kann jedoch andere abgeleitete Beziehungen aufweisen (z. B. eine abgeleitete Hierarchie, die eine rekursive Beziehung zwischen Manager und Mitarbeiter aufweist, kann ebenso Beziehungen zwischen Land und Manager und zwischen Mitarbeiter und Store aufweisen).</span><span class="sxs-lookup"><span data-stu-id="4518e-125">It can, however, have other derived relationships (for example, a derived hierarchy that contains a recursive Manager to Employee relationship can also have Country to Manager and Employee to Store relationships).</span></span>

-   <span data-ttu-id="4518e-126">Sie können Elementen in einer rekursiven Hierarchie (auf der Registerkarte **Hierarchieelemente** ) keine Elementberechtigungen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="4518e-126">You cannot assign member permissions (on the **Hierarchy Members** tab) to members in a recursive hierarchy.</span></span>

-   <span data-ttu-id="4518e-127">Rekursive Hierarchien können keine kreisförmigen Beziehungen einschließen.</span><span class="sxs-lookup"><span data-stu-id="4518e-127">Recursive hierarchies cannot include circular relationships.</span></span> <span data-ttu-id="4518e-128">Katherine kann z. B. nicht Sandeeps Managerin sein, wenn Sandeep ihr Manager ist.</span><span class="sxs-lookup"><span data-stu-id="4518e-128">For example, Katherine cannot be Sandeep's manager if Sandeep is her manager.</span></span> <span data-ttu-id="4518e-129">Auch kann Katherine nicht ihre eigener Managerin sein.</span><span class="sxs-lookup"><span data-stu-id="4518e-129">Also, Katherine cannot manage herself.</span></span>

## <a name="related-tasks"></a><span data-ttu-id="4518e-130">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="4518e-130">Related Tasks</span></span>

|<span data-ttu-id="4518e-131">Taskbeschreibung</span><span class="sxs-lookup"><span data-stu-id="4518e-131">Task Description</span></span>|<span data-ttu-id="4518e-132">Thema</span><span class="sxs-lookup"><span data-stu-id="4518e-132">Topic</span></span>|
|----------------------|-----------|
|<span data-ttu-id="4518e-133">Erstellen Sie eine abgeleitete Hierarchie.</span><span class="sxs-lookup"><span data-stu-id="4518e-133">Create a derived hierarchy.</span></span>|[<span data-ttu-id="4518e-134">Erstellen einer abgeleiteten Hierarchie &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="4518e-134">Create a Derived Hierarchy &#40;Master Data Services&#41;</span></span>](create-a-derived-hierarchy-master-data-services.md)|
|<span data-ttu-id="4518e-135">Ändern Sie den Namen einer vorhandenen abgeleiteten Hierarchie.</span><span class="sxs-lookup"><span data-stu-id="4518e-135">Change the name of an existing derived hierarchy.</span></span>|[<span data-ttu-id="4518e-136">Ändern des Namens einer abgeleiteten Hierarchie &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="4518e-136">Change a Derived Hierarchy Name &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/change-a-derived-hierarchy-name-master-data-services.md)|
|<span data-ttu-id="4518e-137">Löschen Sie eine vorhandene abgeleitete Hierarchie.</span><span class="sxs-lookup"><span data-stu-id="4518e-137">Delete an existing derived hierarchy.</span></span>|[<span data-ttu-id="4518e-138">Löschen einer abgeleiteten Hierarchie &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="4518e-138">Delete a Derived Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-a-derived-hierarchy-master-data-services.md)|

## <a name="related-content"></a><span data-ttu-id="4518e-139">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="4518e-139">Related Content</span></span>

-   [<span data-ttu-id="4518e-140">Domänenbasierte Attribute &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="4518e-140">Domain-Based Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/domain-based-attributes-master-data-services.md)

-   [<span data-ttu-id="4518e-141">Abgeleitete Hierarchien &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="4518e-141">Derived Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/derived-hierarchies-master-data-services.md)


