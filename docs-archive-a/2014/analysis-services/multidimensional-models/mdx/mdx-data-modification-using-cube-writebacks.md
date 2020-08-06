---
title: Verwenden von Cube-Rück schreiben (MDX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- writeback [Analysis Services], cubes
- cubes [Analysis Services], modifying
- modifying cubes
- UPDATE CUBE statement
- cubes [Analysis Services], writeback
ms.assetid: ae2385fc-7fa0-4f8e-98d7-dcb0a5f0eeea
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3ac43e9206619117c1fc090a594ca32ccbeeeb31
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616735"
---
# <a name="using-cube-writebacks-mdx"></a><span data-ttu-id="d7d2e-102">Verwenden von Cuberückschreiben (MDX)</span><span class="sxs-lookup"><span data-stu-id="d7d2e-102">Using Cube Writebacks (MDX)</span></span>
  <span data-ttu-id="d7d2e-103">Sie aktualisieren einen Cube, indem Sie die [UPDATE CUBE](/sql/mdx/mdx-data-manipulation-update-cube) -Anweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="d7d2e-103">You update a cube by using the [UPDATE CUBE](/sql/mdx/mdx-data-manipulation-update-cube) statement.</span></span> <span data-ttu-id="d7d2e-104">Mit dieser Anweisung können Sie ein Tupel mit einem bestimmten Wert aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="d7d2e-104">This statement lets you update a tuple with a specific value.</span></span> <span data-ttu-id="d7d2e-105">Damit Sie einen Cube mit der UPDATE CUBE-Anweisung effizient aktualisieren können, müssen Sie die Syntax der Anweisung, die Fehlerbedingungen, die auftreten können, und die Auswirkungen kennen, die Updates auf einen Cube haben können.</span><span class="sxs-lookup"><span data-stu-id="d7d2e-105">To effectively use the UPDATE CUBE statement to update a cube, you have to understand the syntax for the statement, the error conditions that can occur, and the affect that updates can have on a cube.</span></span>  
  
## <a name="update-cube-statement-syntax"></a><span data-ttu-id="d7d2e-106">Syntax der UPDATE CUBE-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d7d2e-106">UPDATE CUBE Statement Syntax</span></span>  
 <span data-ttu-id="d7d2e-107">Die folgende Syntax beschreibt die UPDATE CUBE-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="d7d2e-107">The following syntax describes the UPDATE CUBE statement:</span></span>  
  
```  
UPDATE [CUBE] <Cube_Name> SET <tuple>.VALUE = <value> [,<tuple>.VALUE = <value>...]  
 [ USE_EQUAL_ALLOCATION | USE_EQUAL_INCREMENT |  
  USE_WEIGHTED_ALLOCATION [BY <weight value_expression>] |  
  USE_WEIGHTED_INCREMENT [BY <weight value_expression>] ]   
```  
  
 <span data-ttu-id="d7d2e-108">Sind die Koordinaten für das Tupel nicht vollständig angegeben, wird für die nicht angegebenen Koordinaten das Standardelement der Hierarchie verwendet.</span><span class="sxs-lookup"><span data-stu-id="d7d2e-108">If a full set of coordinates is not specified for the tuple, the unspecified coordinates will use the default member of the hierarchy.</span></span> <span data-ttu-id="d7d2e-109">Das identifizierte Tupel muss auf eine Zelle verweisen, die mit der [Sum](/sql/mdx/sum-mdx) -Funktion aggregiert ist, und darf kein berechnetes Element als eine der Koordinaten der Zelle verwenden.</span><span class="sxs-lookup"><span data-stu-id="d7d2e-109">The tuple identified must reference a cell that is aggregated with the [Sum](/sql/mdx/sum-mdx) function, and must not use a calculated member as one of the cell's coordinates.</span></span>  
  
 <span data-ttu-id="d7d2e-110">Sie können sich die UPDATE CUBE-Anweisung als Unterroutine vorstellen, die eine Reihe einzelner Rückschreibvorgänge für atomare Zellen generiert.</span><span class="sxs-lookup"><span data-stu-id="d7d2e-110">You can think of the UPDATE CUBE statement as a subroutine that generates a series of individual writeback operations to atomic cells.</span></span> <span data-ttu-id="d7d2e-111">Diese einzelnen Rückschreibvorgänge ergeben dann als Rollup die angegebene Summe.</span><span class="sxs-lookup"><span data-stu-id="d7d2e-111">All these individual writeback operations then roll up into the specified sum.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d7d2e-112">Wenn sich die aktualisierten Zellen nicht überlagern, kann mithilfe der `Update Isolation Level`-Eigenschaft der Verbindungszeichenfolge das Leistungsverhalten in Bezug auf UPDATE CUBE verbessert werden.</span><span class="sxs-lookup"><span data-stu-id="d7d2e-112">When updated cells do not overlap, the `Update Isolation Level` connection string property can be used to enhance performance for UPDATE CUBE.</span></span> <span data-ttu-id="d7d2e-113">Weitere Informationen finden Sie unter <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection.ConnectionString%2A>.</span><span class="sxs-lookup"><span data-stu-id="d7d2e-113">For more information, see <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection.ConnectionString%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7d2e-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d7d2e-114">Example</span></span>  
 <span data-ttu-id="d7d2e-115">Sie können UPDATE CUBE mithilfe der Sales Targets-Measuregruppe im Adventure Works-Cube testen.</span><span class="sxs-lookup"><span data-stu-id="d7d2e-115">You can test UPDATE CUBE using the Sales Targets measure group in the Adventure Works cube.</span></span> <span data-ttu-id="d7d2e-116">Die Measuregruppe enthält mithilfe von SUM aggregierte Measures, da dies eine Voraussetzung für UPDATE CUBE ist.</span><span class="sxs-lookup"><span data-stu-id="d7d2e-116">This measure group consists of measures aggregated by SUM, which is a requirement for UPDATE CUBE.</span></span>  
  
1.  <span data-ttu-id="d7d2e-117">Aktivieren Sie das Rückschreiben für die Sales Targets-Measuregruppe in der Adventure Works-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="d7d2e-117">Enable writeback for the Sales Targets measure group in the Adventure Works database.</span></span> <span data-ttu-id="d7d2e-118">Klicken Sie in Management Studio mit der rechten Maustaste auf eine Measuregruppe, zeigen Sie auf **Rückschreibeoptionen**, und wählen Sie **Rückschreiben aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="d7d2e-118">In Management Studio, right-click a measure group, point to **Write Back Options**, choose **Enable Writeback**.</span></span>  
  
     <span data-ttu-id="d7d2e-119">Im Ordner Rückschreiben sollte eine neue Rückschreibetabelle angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d7d2e-119">You should see a new writeback table in the Writeback folder.</span></span> <span data-ttu-id="d7d2e-120">Der Tabellenname lautet "WriteTable_Fact Sales Quota".</span><span class="sxs-lookup"><span data-stu-id="d7d2e-120">The table name is WriteTable_Fact Sales Quota.</span></span>  
  
2.  <span data-ttu-id="d7d2e-121">Öffnen Sie ein MDX-Abfragefenster.</span><span class="sxs-lookup"><span data-stu-id="d7d2e-121">Open an MDX query window.</span></span> <span data-ttu-id="d7d2e-122">Führen Sie die folgende SELECT-Anweisung aus, um den ursprünglichen Wert anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="d7d2e-122">Run the following select statement to view the original value:</span></span>  
  
    ```  
    SELECT [Measures].[Sales Amount Quota] on 0 ,  
    [Employee].[Employee Department].[Title].&[Sales Representative].children on 1  
    FROM [Adventure Works]  
  
    ```  
  
     <span data-ttu-id="d7d2e-123">Für jeden Vertriebsmitarbeiter sollten Sollvorgaben angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d7d2e-123">You should see sales amount quotas for each representative.</span></span>  
  
3.  <span data-ttu-id="d7d2e-124">Führen Sie die UPDATE CUBE-Anweisung aus, um einen neuen Wert zurückzuschreiben.</span><span class="sxs-lookup"><span data-stu-id="d7d2e-124">Run the update cube statement to write back a new value.</span></span> <span data-ttu-id="d7d2e-125">In diesem Beispiel wird die Sollvorgabe auf 0 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d7d2e-125">In this example, we are setting the sales amount quota to 0.</span></span> <span data-ttu-id="d7d2e-126">Weil der neue Wert 0 beträgt, geben Sie keine Zuordnungsmethode an.</span><span class="sxs-lookup"><span data-stu-id="d7d2e-126">Because the new value is 0, do not specify an allocation method.</span></span>  
  
    ```  
    UPDATE CUBE [Adventure Works]   
    SET ([Measures].[Sales Amount Quota], [Employee].[Employee Department].[Department].&[Sales]) = 0  
  
    ```  
  
4.  <span data-ttu-id="d7d2e-127">Führen Sie die SELECT-Anweisung erneut aus.</span><span class="sxs-lookup"><span data-stu-id="d7d2e-127">Re-run the SELECT statement.</span></span> <span data-ttu-id="d7d2e-128">Jetzt sollte für die Vorgaben der Wert 0 angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d7d2e-128">You should now see zero for the quotas.</span></span>  
  
 <span data-ttu-id="d7d2e-129">Der Rückschreibewert ist auf die aktuelle Sitzung beschränkt.</span><span class="sxs-lookup"><span data-stu-id="d7d2e-129">The writeback value is constrained to the current session.</span></span> <span data-ttu-id="d7d2e-130">Um den Wert benutzer- und sitzungsübergreifend beizubehalten, verarbeiten Sie die Rückschreibetabelle.</span><span class="sxs-lookup"><span data-stu-id="d7d2e-130">To persist the value across users and sessions, process the writeback table.</span></span> <span data-ttu-id="d7d2e-131">Klicken Sie in Management Studio mit der rechten Maustaste auf WriteTable_Fact Sales Quota, und wählen Sie **Verarbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="d7d2e-131">In Management Studio, right-click WriteTable_Fact Sales Quota and choose **Process**.</span></span>  
  
 <span data-ttu-id="d7d2e-132">Damit eine Zuordnungsmethode angegeben werden kann, muss der neue Wert größer als 0 sein.</span><span class="sxs-lookup"><span data-stu-id="d7d2e-132">To specify an allocation method, the new value must be greater than zero.</span></span> <span data-ttu-id="d7d2e-133">In diesem Beispiel beträgt der neue Wert für Sales Amount Quota zwei Millionen und wird durch die Zuordnungsmethode auf alle Vertriebsmitarbeiter verteilt.</span><span class="sxs-lookup"><span data-stu-id="d7d2e-133">In this example, the new value for Sales Amount Quota is two million and the allocation method distributes the amount across all sales representatives.</span></span>  
  
```  
UPDATE CUBE [Adventure Works]   
SET ([Measures].[Sales Amount Quota], [Employee].[Employee Department].[Department].&[Sales]) = 2000000   
USE_EQUAL_ALLOCATION  
```  
  
## <a name="error-conditions"></a><span data-ttu-id="d7d2e-134">Fehlerbedingungen</span><span class="sxs-lookup"><span data-stu-id="d7d2e-134">Error Conditions</span></span>  
 <span data-ttu-id="d7d2e-135">In der folgenden Tabelle sind sowohl die möglichen Ursachen für Fehler bei Rückschreibvorgängen als auch die Ergebnisse solcher Fehler beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d7d2e-135">The following table describes both what can cause writebacks to fail and the result of those errors.</span></span>  
  
|<span data-ttu-id="d7d2e-136">Fehlerbedingung</span><span class="sxs-lookup"><span data-stu-id="d7d2e-136">Error Condition</span></span>|<span data-ttu-id="d7d2e-137">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="d7d2e-137">Result</span></span>|  
|---------------------|------------|  
|<span data-ttu-id="d7d2e-138">Das Update beinhaltet Elemente aus derselben Dimension, die es nicht gemeinsam gibt.</span><span class="sxs-lookup"><span data-stu-id="d7d2e-138">Update includes members from the same dimension that do not exist with one another.</span></span>|<span data-ttu-id="d7d2e-139">Das Update erzeugt einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="d7d2e-139">Update will fail.</span></span> <span data-ttu-id="d7d2e-140">Der Cuberaum enthält nicht die Zelle, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="d7d2e-140">The cube space will not contain the referenced cell.</span></span>|  
|<span data-ttu-id="d7d2e-141">Das Update beinhaltet ein Measure, dessen Quelle ein Measure mit einem Datentyp ohne Vorzeichen ist.</span><span class="sxs-lookup"><span data-stu-id="d7d2e-141">Update includes a measure sourced to a measure of an unsigned type.</span></span>|<span data-ttu-id="d7d2e-142">Das Update erzeugt einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="d7d2e-142">Update will fail.</span></span> <span data-ttu-id="d7d2e-143">Für Inkremente ist es erforderlich, dass das Measure einen negativen Wert annehmen kann.</span><span class="sxs-lookup"><span data-stu-id="d7d2e-143">Increments require that the measure be able to take a negative value.</span></span>|  
|<span data-ttu-id="d7d2e-144">Das Update beinhaltet ein Measure, das nicht als Summe aggregiert wird.</span><span class="sxs-lookup"><span data-stu-id="d7d2e-144">Update includes a measure that aggregates other than sum.</span></span>|<span data-ttu-id="d7d2e-145">Ein Fehler wird ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="d7d2e-145">An error is raised.</span></span>|  
|<span data-ttu-id="d7d2e-146">Das Update wurde für einen Teilcube versucht.</span><span class="sxs-lookup"><span data-stu-id="d7d2e-146">Update was tried on a subcube.</span></span>|<span data-ttu-id="d7d2e-147">Ein Fehler wird ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="d7d2e-147">An error is raised.</span></span>|  
  
## <a name="affect-of-cube-changes"></a><span data-ttu-id="d7d2e-148">Auswirkungen von Cubeänderungen</span><span class="sxs-lookup"><span data-stu-id="d7d2e-148">Affect of Cube Changes</span></span>  
 <span data-ttu-id="d7d2e-149">Die folgenden Änderungen wirken sich nicht auf ein Rückschreiben aus:</span><span class="sxs-lookup"><span data-stu-id="d7d2e-149">The following changes will not have an effect on a writeback:</span></span>  
  
-   <span data-ttu-id="d7d2e-150">Verarbeiten eines Cubes, der Measuregruppen des Cubes oder der Dimensionen des Cubes.</span><span class="sxs-lookup"><span data-stu-id="d7d2e-150">Processing of a cube, the cube's measure groups, or the cube's dimensions.</span></span>  
  
-   <span data-ttu-id="d7d2e-151">Hinzufügen von Attributen zu einer Dimension.</span><span class="sxs-lookup"><span data-stu-id="d7d2e-151">Adding attributes to any dimension.</span></span>  
  
-   <span data-ttu-id="d7d2e-152">Hinzufügen einer neuen Dimension.</span><span class="sxs-lookup"><span data-stu-id="d7d2e-152">Adding a new dimension.</span></span>  
  
-   <span data-ttu-id="d7d2e-153">Löschen einer Dimension, in der das Rückschreiben nicht enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="d7d2e-153">Deleting a dimension that does not include the writeback.</span></span>  
  
-   <span data-ttu-id="d7d2e-154">Hinzufügen, Ändern oder Entfernen einer Hierarchie.</span><span class="sxs-lookup"><span data-stu-id="d7d2e-154">Adding, modifying, or removing a hierarchy.</span></span>  
  
-   <span data-ttu-id="d7d2e-155">Hinzufügen eines neues Measures.</span><span class="sxs-lookup"><span data-stu-id="d7d2e-155">Adding a new measure.</span></span>  
  
 <span data-ttu-id="d7d2e-156">Die folgenden Änderungen können nicht vorgenommen werden, ohne die Rückschreibedaten zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="d7d2e-156">The following changes cannot be made without removing the writeback data:</span></span>  
  
-   <span data-ttu-id="d7d2e-157">Löschen eines Attributs oder der Hierarchie des Attributs, wenn das Attribut im Rückschreiben enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="d7d2e-157">Deleting an attribute, or its attribute hierarchy, if the attribute is included in the writeback.</span></span> <span data-ttu-id="d7d2e-158">Dazu gehören explizit das Entfernen des Attributs oder seiner Hierarchie sowie das Entfernen der übergeordneten Dimension des Attributs.</span><span class="sxs-lookup"><span data-stu-id="d7d2e-158">This includes explicitly removing the attribute, or its attribute hierarchy, or removing the attribute's parent dimension.</span></span>  
  
-   <span data-ttu-id="d7d2e-159">Löschen eines Measures, das im Rückschreiben enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="d7d2e-159">Deleting a measure included in the writeback.</span></span>  
  
-   <span data-ttu-id="d7d2e-160">Hinzufügen eines Attributs ohne eine `(All)`-Ebene zu einer Dimension, die im Rückschreiben enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="d7d2e-160">Adding an attribute without an `(All)` level to a dimension included in the writeback.</span></span>  
  
-   <span data-ttu-id="d7d2e-161">Ändern der Dimensionsgranularität für eine Dimension, die im Rückschreiben enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="d7d2e-161">Changing the dimension granularity for a dimension included in the writeback.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7d2e-162">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d7d2e-162">See Also</span></span>  
 [<span data-ttu-id="d7d2e-163">Ändern von Daten &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="d7d2e-163">Modifying Data &#40;MDX&#41;</span></span>](mdx-data-modification-modifying-data.md)  
  
  
