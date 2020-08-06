---
title: Verwenden von Drillthrough zum Abrufen von Quelldaten (MDX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- DRILLTHROUGH statement
- retrieving data
- queries [MDX], DRILLTHROUGH statement
- data retrieval [MDX]
ms.assetid: fe0ab170-25a9-45a8-a377-f71a67f77018
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5601a3ddfa7075ed53330e12c260af88648db990
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618356"
---
# <a name="using-drillthrough-to-retrieve-source-data-mdx"></a><span data-ttu-id="56529-102">Verwenden von DRILLTHROUGH zum Abrufen von Quelldaten (MDX)</span><span class="sxs-lookup"><span data-stu-id="56529-102">Using DRILLTHROUGH to Retrieve Source Data (MDX)</span></span>
  <span data-ttu-id="56529-103">Die [DRILLTHROUGH](/sql/mdx/mdx-data-manipulation-drillthrough)-Anweisung wird in MDX (Multidimensional Expressions) dazu verwendet, ein Rowset aus den Quelldaten für eine Cubezelle abzurufen.</span><span class="sxs-lookup"><span data-stu-id="56529-103">Multidimensional Expressions (MDX) uses the [DRILLTHROUGH](/sql/mdx/mdx-data-manipulation-drillthrough)statement to retrieve a rowset from the source data for a cube cell.</span></span>  
  
 <span data-ttu-id="56529-104">Damit eine `DRILLTHROUGH`-Anweisung für einen Cube ausgeführt werden kann, muss für diesen Cube eine Drillthroughaktion definiert sein.</span><span class="sxs-lookup"><span data-stu-id="56529-104">In order to run a `DRILLTHROUGH` statement on a cube, a drillthrough action must be defined for that cube.</span></span> <span data-ttu-id="56529-105">Um eine Drillthroughaktion zu definieren, klicken Sie in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)]im Cube-Designer im **Aktionsbereich** auf der Symbolleiste auf **Neue Drillthroughaktion**.</span><span class="sxs-lookup"><span data-stu-id="56529-105">To define a drillthrough action, in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], in Cube Designer, on the **Actions** pane, on the toolbar, click **New Drillthrough Action**.</span></span> <span data-ttu-id="56529-106">In der neuen Drillthroughaktion geben Sie den Aktionsnamen, das Ziel, die Bedingung und die Spalten an, die von der `DRILLTHROUGH`-Anweisung zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="56529-106">In the new drillthrough action, specify the action name, target, condition, and the columns that are returned by a `DRILLTHROUGH` statement.</span></span>  
  
## <a name="drillthrough-statement-syntax"></a><span data-ttu-id="56529-107">Syntax der DRILLTHROUGH-Anweisung</span><span class="sxs-lookup"><span data-stu-id="56529-107">DRILLTHROUGH Statement Syntax</span></span>  
 <span data-ttu-id="56529-108">Die `DRILLTHROUGH`-Anweisung hat folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="56529-108">The `DRILLTHROUGH` statement uses the following syntax:</span></span>  
  
```  
<drillthrough> ::= DRILLTHROUGH [<Max_Rows>] [<First_Rowset>] <MDX select> [<Return_Columns>]  
   < Max_Rows> ::= MAXROWS <positive number>  
   <First_Rowset> ::= FIRSTROWSET <positive number>  
   <Return_Columns> ::= RETURN <member or attribute> [, <member or attribute>]  
```  
  
 <span data-ttu-id="56529-109">Die `SELECT`-Klausel kennzeichnet die Cubezelle, die die Quelldaten enthält, die abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="56529-109">The `SELECT` clause identifies the cube cell that contains the source data to be retrieved.</span></span> <span data-ttu-id="56529-110">Diese `SELECT`-Klausel ist mit einer normalen MDX-`SELECT`-Anweisung identisch, mit dem einen Unterschied, dass in der `SELECT`-Klausel nur ein Element auf jeder Achse angegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="56529-110">This `SELECT` clause is the same to an ordinary MDX `SELECT` statement, except that in the `SELECT` clause only one member can be specified on each axis.</span></span> <span data-ttu-id="56529-111">Wenn mehr als ein Element auf einer Achse angegeben wird, tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="56529-111">If more than one member is specified on an axis, an error occurs.</span></span>  
  
 <span data-ttu-id="56529-112">Die `<Max_Rows>` -Syntax gibt die maximale Anzahl der Zeilen in jedem zurückgegebenen Rowset an.</span><span class="sxs-lookup"><span data-stu-id="56529-112">The `<Max_Rows>` syntax specifies the maximum number of the rows in each returned rowset.</span></span> <span data-ttu-id="56529-113">Wenn der OLE DB-Anbieter, der für die Verbindung mit der Datenquelle verwendet wird, `DBPROP_MAXROWS` nicht unterstützt, wird die `<Max_Rows>`-Einstellung ignoriert.</span><span class="sxs-lookup"><span data-stu-id="56529-113">If the OLE DB provider that is used to connect to the data source does not support `DBPROP_MAXROWS`, the `<Max_Rows>` setting is ignored.</span></span>  
  
 <span data-ttu-id="56529-114">Die `<First_Rowset>` -Syntax identifiziert die Partition, deren Rowset zuerst zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="56529-114">The `<First_Rowset>` syntax identifies the partition whose rowset is returned first.</span></span>  
  
 <span data-ttu-id="56529-115">Die `<Return_Columns>` -Syntax identifiziert die zugrunde liegenden Datenbankspalten, die zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="56529-115">The `<Return_Columns>` syntax identifies the underlying database columns to be returned.</span></span>  
  
## <a name="drillthrough-statement-example"></a><span data-ttu-id="56529-116">Beispiel für die DRILLTHROUGH-Anweisung</span><span class="sxs-lookup"><span data-stu-id="56529-116">DRILLTHROUGH Statement Example</span></span>  
 <span data-ttu-id="56529-117">Das folgende Beispiel zeigt die Verwendung der `DRILLTHROUGH`-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="56529-117">The following example demonstrates the use of the `DRILLTHROUGH` statement.</span></span> <span data-ttu-id="56529-118">In diesem Beispiel fragt die DRILLTHROUGH-Anweisung die Blätter der Dimensionen Store, Product und Time entlang der Stores-Dimension (die Slicerachse) ab und gibt dann die Department-Measuregruppe, die Abteilungs-ID (Department ID) und den Vornamen der/des Angestellten zurück.</span><span class="sxs-lookup"><span data-stu-id="56529-118">In this example, the DRILLTHROUGH statement queries the leaves of the Store, Product, and Time dimensions along the Stores dimension (the slicer axis), and then returns the department measure group, department ID, and employee's first name.</span></span>  
  
```  
DRILLTHROUGH  
Select {Leaves(Store), Leaves(Product), Leaves(Time),*} on 0  
From Stores  
RETURN [Department MeasureGroup].[Department Id], [Employee].[First Name]  
```  
  
## <a name="see-also"></a><span data-ttu-id="56529-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="56529-119">See Also</span></span>  
 [<span data-ttu-id="56529-120">Bearbeiten von Daten &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="56529-120">Manipulating Data &#40;MDX&#41;</span></span>](mdx-data-manipulation-manipulating-data.md)  
  
  
