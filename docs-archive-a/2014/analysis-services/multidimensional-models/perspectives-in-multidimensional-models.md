---
title: Perspektiven in mehrdimensionalen Modellen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- default members
- hiding objects from perspective
- renaming perspectives
- attributes [Analysis Services], default members
- removing perspectives
- perspectives [Analysis Services]
- names [Analysis Services], perspectives
- cubes [Analysis Services], perspectives
- deleting perspectives
ms.assetid: 5a3d6577-6833-4c24-820c-b65bb856157b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2d4be87ddbd691710b361d8b07d225bce37659fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615650"
---
# <a name="perspectives-in-multidimensional-models"></a><span data-ttu-id="84a94-102">Perspektiven in mehrdimensionalen Modellen</span><span class="sxs-lookup"><span data-stu-id="84a94-102">Perspectives in Multidimensional Models</span></span>
  <span data-ttu-id="84a94-103">Bei einer Perspektive handelt es sich um eine für eine bestimmte Anwendung oder Benutzergruppe erstellte Teilmenge eines Cubes.</span><span class="sxs-lookup"><span data-stu-id="84a94-103">A perspective is a subset of a cube created for a particular application or group of users.</span></span> <span data-ttu-id="84a94-104">Der Cube selbst stellt die Standardperspektive dar.</span><span class="sxs-lookup"><span data-stu-id="84a94-104">The cube itself is the default perspective.</span></span> <span data-ttu-id="84a94-105">Eine Perspektive wird auf einem Client als Cube verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="84a94-105">A perspective is exposed to a client as a cube.</span></span> <span data-ttu-id="84a94-106">Wenn ein Benutzer eine Perspektive anzeigt, wird diese wie ein weiterer Cube angezeigt.</span><span class="sxs-lookup"><span data-stu-id="84a94-106">When a user views a perspective, it appears like another cube.</span></span> <span data-ttu-id="84a94-107">Alle Änderungen, die an den Cubedaten durch Rückschreibevorgänge in der Perspektive vorgenommen wurden, erfolgen am Originalcube.</span><span class="sxs-lookup"><span data-stu-id="84a94-107">Any changes made to cube data through writeback in the perspective are to the original cube.</span></span> <span data-ttu-id="84a94-108">Weitere Informationen zu den in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]enthaltenen Sichten finden Sie unter [Perspektiven](../multidimensional-models-olap-logical-cube-objects/perspectives.md).</span><span class="sxs-lookup"><span data-stu-id="84a94-108">For more information about the views in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], see [Perspectives](../multidimensional-models-olap-logical-cube-objects/perspectives.md).</span></span>  
  
 <span data-ttu-id="84a94-109">Verwenden Sie im Cube-Designer die Registerkarte **Perspektiven** , um Perspektiven in einem Cube zu erstellen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="84a94-109">Use the **Perspectives** tab in Cube Designer to create or modify perspectives in a cube.</span></span> <span data-ttu-id="84a94-110">Die erste Spalte der Registerkarte **Perspektiven** ist die Spalte **Cubeobjekte** , in der alle Objekte des Cubes aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="84a94-110">The first column of the **Perspectives** tab is the **Cube Objects** column, which lists all the objects in the cube.</span></span> <span data-ttu-id="84a94-111">Diese Spalte entspricht der Standardperspektive des Cubes, mit der der Cube selbst dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="84a94-111">This corresponds to the default perspective for the cube, which is the cube itself.</span></span>  
  
## <a name="creating-or-deleting-perspectives"></a><span data-ttu-id="84a94-112">Erstellen oder Löschen von Perspektiven</span><span class="sxs-lookup"><span data-stu-id="84a94-112">Creating or Deleting Perspectives</span></span>  
 <span data-ttu-id="84a94-113">Sie können der Registerkarte **Perspektiven** eine Perspektive hinzufügen, indem Sie im Menü **Cube** auf **Neue Perspektive** klicken.</span><span class="sxs-lookup"><span data-stu-id="84a94-113">You can add a perspective to the **Perspectives** tab by clicking **New Perspective** on the **Cube** menu.</span></span> <span data-ttu-id="84a94-114">Klicken Sie alternativ auf der Symbolleiste auf die Schaltfläche **Neue Perspektive** oder mit der rechten Maustaste auf eine beliebige Stelle im Bereich und dann im Kontextmenü auf **Neue Perspektive** .</span><span class="sxs-lookup"><span data-stu-id="84a94-114">You can also click the **New Perspective** button on the toolbar, or right-click anywhere in the pane and click **New Perspective** on the shortcut menu.</span></span> <span data-ttu-id="84a94-115">Sie können einem Cube eine beliebige Anzahl von Perspektiven hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="84a94-115">You can add any number of perspectives to a cube.</span></span>  
  
 <span data-ttu-id="84a94-116">Klicken Sie zum Entfernen einer Perspektive zunächst auf eine beliebige Zelle in der Spalte der zu löschenden Perspektive.</span><span class="sxs-lookup"><span data-stu-id="84a94-116">To remove a perspective, first click any cell in the column for the perspective that you want to delete.</span></span> <span data-ttu-id="84a94-117">Klicken Sie dann im Menü **Cube** auf **Perspektive löschen**.</span><span class="sxs-lookup"><span data-stu-id="84a94-117">Then, on the **Cube** menu, click **Delete Perspective**.</span></span> <span data-ttu-id="84a94-118">Klicken Sie alternativ auf der Symbolleiste auf die Schaltfläche **Perspektive löschen** oder mit der rechten Maustaste auf eine beliebige Zelle der zu löschenden Perspektive und dann im Kontextmenü auf **Perspektive löschen** .</span><span class="sxs-lookup"><span data-stu-id="84a94-118">You can also click the **Delete Perspective** button on the toolbar, or right-click any cell in the perspective you want to delete, and then click **Delete Perspective** on the shortcut menu.</span></span>  
  
## <a name="renaming-perspectives"></a><span data-ttu-id="84a94-119">Umbenennen von Perspektiven</span><span class="sxs-lookup"><span data-stu-id="84a94-119">Renaming Perspectives</span></span>  
 <span data-ttu-id="84a94-120">In der ersten Zeile der jeweiligen Perspektive wird der Name der Perspektive angezeigt.</span><span class="sxs-lookup"><span data-stu-id="84a94-120">The first row of each perspective shows its name.</span></span> <span data-ttu-id="84a94-121">Beim Erstellen einer Perspektive lautet der Name zunächst Perspektive (gefolgt von der Ordnungszahl, beginnend mit 1, falls eine Perspektive mit dem Namen Perspektive bereits vorhanden ist).</span><span class="sxs-lookup"><span data-stu-id="84a94-121">When you create a perspective, the name is initially Perspective (followed by an ordinal number, starting with 1, if there is already a perspective called Perspective).</span></span> <span data-ttu-id="84a94-122">Sie können auf den Namen klicken, um ihn zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="84a94-122">You can click the name to edit it.</span></span>  
  
## <a name="hiding-objects-from-a-perspective"></a><span data-ttu-id="84a94-123">Ausblenden von Objekten aus einer Perspektive</span><span class="sxs-lookup"><span data-stu-id="84a94-123">Hiding Objects from a Perspective</span></span>  
 <span data-ttu-id="84a94-124">Deaktivieren Sie zum Ausblenden eines Objekts aus einer Perspektive das Kontrollkästchen in der Zeile, die dem Objekt in der Spalte der Perspektive entspricht.</span><span class="sxs-lookup"><span data-stu-id="84a94-124">To hide an object from a perspective, clear the check box in the row that corresponds to the object in the column for the perspective.</span></span> <span data-ttu-id="84a94-125">Die Cubeobjekte, die aus einer Perspektive ausgeblendet werden können, sind die folgenden:</span><span class="sxs-lookup"><span data-stu-id="84a94-125">The cube objects that can be hidden from a perspective are:</span></span>  
  
-   <span data-ttu-id="84a94-126">Measuregruppen</span><span class="sxs-lookup"><span data-stu-id="84a94-126">Measure groups</span></span>  
  
-   <span data-ttu-id="84a94-127">Measures</span><span class="sxs-lookup"><span data-stu-id="84a94-127">Measures</span></span>  
  
-   <span data-ttu-id="84a94-128">Dimensionen</span><span class="sxs-lookup"><span data-stu-id="84a94-128">Dimensions</span></span>  
  
-   <span data-ttu-id="84a94-129">Hierarchien</span><span class="sxs-lookup"><span data-stu-id="84a94-129">Hierarchies</span></span>  
  
-   <span data-ttu-id="84a94-130">Benannte Mengen</span><span class="sxs-lookup"><span data-stu-id="84a94-130">Named sets</span></span>  
  
-   <span data-ttu-id="84a94-131">KPIs</span><span class="sxs-lookup"><span data-stu-id="84a94-131">KPIs</span></span>  
  
-   <span data-ttu-id="84a94-132">Aktionen</span><span class="sxs-lookup"><span data-stu-id="84a94-132">Actions</span></span>  
  
-   <span data-ttu-id="84a94-133">Berechnete Elemente</span><span class="sxs-lookup"><span data-stu-id="84a94-133">Calculated members</span></span>  
  
 <span data-ttu-id="84a94-134">Erweitern Sie zum Anzeigen eines Objekts die Kategorie (**Measuregruppen**, **Dimensionen**, **KPIs**, **Berechnungen**oder **Aktionen**) für einen beliebigen Objekttyp unter **Cubeobjekte**.</span><span class="sxs-lookup"><span data-stu-id="84a94-134">To view any object, expand the category (**Measure Groups**, **Dimensions**, **KPIs**, **Calculations**, or **Actions**) for any object type under **Cube Objects**.</span></span> <span data-ttu-id="84a94-135">Erweitern Sie zunächst eine Dimension, und erweitern Sie dann die Zeile **Hierarchien** , um die Hierarchien einer Dimension anzuzeigen, oder die Zeile **Attribute** , um die Attribute einer Dimension anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="84a94-135">To view hierarchies or attributes in a dimension, first expand a dimension, and then expand the **Hierarchies** or **Attributes** row.</span></span> <span data-ttu-id="84a94-136">Erweitern Sie die Measuregruppe, um die in einer Measuregruppe enthaltenen Measures anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="84a94-136">To view measures in a measure group, expand the measure group.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84a94-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="84a94-137">See Also</span></span>  
 [<span data-ttu-id="84a94-138">Cubes in mehrdimensionalen Modellen</span><span class="sxs-lookup"><span data-stu-id="84a94-138">Cubes in Multidimensional Models</span></span>](cubes-in-multidimensional-models.md)  
  
  
