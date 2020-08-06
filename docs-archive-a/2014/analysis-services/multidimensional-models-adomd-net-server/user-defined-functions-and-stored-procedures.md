---
title: Benutzerdefinierte Funktionen und gespeicherte Prozeduren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- stored procedures [ADOMD.NET]
- ADOMD.NET, user defined functions
- user defined functions [ADOMD.NET]
- ADOMD.NET, UDFs
- ADOMD.NET, stored procedures
ms.assetid: 07e8aa47-37d4-4bbc-8bff-49e422d12897
author: minewiskan
ms.author: owend
ms.openlocfilehash: a49aa41d158bf2c9fd1ebb1a711d6ff35c0df98b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694802"
---
# <a name="user-defined-functions-and-stored-procedures"></a><span data-ttu-id="cc1e4-102">Benutzerdefinierte Funktionen und gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="cc1e4-102">User Defined Functions and Stored Procedures</span></span>
  <span data-ttu-id="cc1e4-103">Mit ADOMD.NET-Server Objekten können Sie benutzerdefinierte Funktionen (User Defined Function, UDF) oder gespeicherte Prozeduren für erstellen [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , die mit Metadaten und Daten vom Server interagieren.</span><span class="sxs-lookup"><span data-stu-id="cc1e4-103">With ADOMD.NET server objects, you can create user defined function (UDF) or stored procedures for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] that interact with metadata and data from the server.</span></span> <span data-ttu-id="cc1e4-104">Diese prozessinternen Methoden werden durch Multidimensional Expressions (MDX)- oder Data Mining Extensions (DMX)-Anweisungen aufgerufen, um zusätzliche Funktionen bereitzustellen, die nicht den Wartezeiten eines Netzwerks unterworfen sind.</span><span class="sxs-lookup"><span data-stu-id="cc1e4-104">These in-process methods are called through Multidimensional Expressions (MDX) or Data Mining Extensions (DMX) statements to provide added functionality without the latencies associated with network communications.</span></span>  
  
## <a name="udf-examples"></a><span data-ttu-id="cc1e4-105">UDF-Beispiele</span><span class="sxs-lookup"><span data-stu-id="cc1e4-105">UDF Examples</span></span>  
 <span data-ttu-id="cc1e4-106">Eine benutzerdefinierte Funktion (UDF) ist eine Methode, die im Zusammenhang mit einer MDX- oder DMX-Anweisung aufgerufen wird, eine beliebige Anzahl an Parametern unterstützt und jede Art von Daten zurückgeben kann.</span><span class="sxs-lookup"><span data-stu-id="cc1e4-106">A UDF is a method that can be called in the context of an MDX or DMX statement, can take any number of parameters, and can return any type of data.</span></span>  
  
 <span data-ttu-id="cc1e4-107">Eine mit MDX erstellte benutzerdefinierte Funktion ist mit einer für DMX erstellten vergleichbar.</span><span class="sxs-lookup"><span data-stu-id="cc1e4-107">A UDF created using MDX is similar to one created for DMX.</span></span> <span data-ttu-id="cc1e4-108">Der Hauptunterschied besteht darin, dass bestimmte Eigenschaften von [Microsoft. das AnalysisServices. AdomdServer. Context](/previous-versions/sql/sql-server-2014/ms143353(v=sql.120)) -Objekt, z. b. die Eigenschaften [Microsoft. AnalysisServices. AdomdServer. Context. CURRENTCUBE \*](/previous-versions/sql/sql-server-2014/ms137081(v=sql.120)) und [Microsoft. AnalysisServices. AdomdServer. Context. CurrentMiningModel \*](/previous-versions/sql/sql-server-2014/ms137178(v=sql.120)) , ist nur für eine Skriptsprache oder die andere verfügbar.</span><span class="sxs-lookup"><span data-stu-id="cc1e4-108">The main difference is that certain properties of the [Microsoft.AnalysisServices.AdomdServer.Context](/previous-versions/sql/sql-server-2014/ms143353(v=sql.120)) object, such as the [Microsoft.AnalysisServices.AdomdServer.Context.CurrentCube\*](/previous-versions/sql/sql-server-2014/ms137081(v=sql.120)) and [Microsoft.AnalysisServices.AdomdServer.Context.CurrentMiningModel\*](/previous-versions/sql/sql-server-2014/ms137178(v=sql.120)) properties, are available only for one scripting language or the other.</span></span>  
  
 <span data-ttu-id="cc1e4-109">Die folgenden Beispiele zeigen, wie man mit einer benutzerdefinierten Funktion eine Knotenbeschreibung zurückgibt, Tupeln filtert und einen Filter auf ein Tupel anwendet.</span><span class="sxs-lookup"><span data-stu-id="cc1e4-109">The following examples show how to use a UDF to return a node description, filter tuples, and apply a filter to a tuple.</span></span>  
  
### <a name="returning-a-node-description"></a><span data-ttu-id="cc1e4-110">Zurückgeben einer Knotenbeschreibung</span><span class="sxs-lookup"><span data-stu-id="cc1e4-110">Returning a Node Description</span></span>  
 <span data-ttu-id="cc1e4-111">Im folgenden Beispiel wird eine benutzerdefinierte Funktion erstellt, mit der die Knotenbeschreibung für einen bestimmten Knoten zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="cc1e4-111">The following example creates a UDF that returns the node description for a specified node.</span></span> <span data-ttu-id="cc1e4-112">Die benutzerdefinierte Funktion verwendet den derzeitigen Kontext, in dem sie ausgeführt wird, und ruft den Knoten mithilfe einer DMX FROM-Klausel aus dem aktuellen Miningmodell ab.</span><span class="sxs-lookup"><span data-stu-id="cc1e4-112">The UDF uses the current context in which it is being run, and uses a DMX FROM clause to retrieve the node from the current mining model.</span></span>  
  
```  
public string GetNodeDescription(string nodeUniqueName)  
{  
   return Context.CurrentMiningModel.GetNodeFromUniqueName(nodeUniqueName).Description;  
}  
```  
  
 <span data-ttu-id="cc1e4-113">Nach der Bereitstellung kann das vorherige UDF-Beispiel durch folgenden DMX-Ausdruck, der den wahrscheinlichsten Vorhersageknoten abruft, aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="cc1e4-113">Once deployed, the previous UDF example can be called by the following DMX expression, which retrieves the most-likely prediction node.</span></span> <span data-ttu-id="cc1e4-114">Die Beschreibung enthält Informationen, in denen die Bedingungen beschrieben werden, die den Vorhersageknoten bilden.</span><span class="sxs-lookup"><span data-stu-id="cc1e4-114">The description contains information that describes the conditions that make up the prediction node.</span></span>  
  
```  
select Cluster(), SampleAssembly.GetNodeDescription( PredictNodeId(Cluster()) ) FROM [Customer Clusters]  
```  
  
### <a name="returning-tuples"></a><span data-ttu-id="cc1e4-115">Zurückgeben von Tupeln</span><span class="sxs-lookup"><span data-stu-id="cc1e4-115">Returning Tuples</span></span>  
 <span data-ttu-id="cc1e4-116">Im folgenden Beispiel werden mit einem Satz und einer Rückgabezahl Tupeln nach dem Zufallsprinzip aus dem Satz abgerufen, wodurch schließlich eine Teilmenge zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="cc1e4-116">The following example takes a set and a return count, and randomly retrieves tuples from the set, returning a final subset:</span></span>  
  
```  
public Set RandomSample(Set set, int returnCount)  
{  
   //Return the original set if there are fewer tuples  
   //in the set than the number requested.  
   if (set.Tuples.Count <= returnCount)  
      return set;  
  
   System.Random r = new System.Random();  
   SetBuilder returnSet = new SetBuilder();  
  
   //Retrieve random tuples until the return set is filled.  
   int i = set.Tuples.Count;  
   foreach (Tuple t in set.Tuples)  
   {  
      if (r.Next(i) < returnCount)  
      {  
         returnCount--;  
         returnSet.Add(t);  
      }  
      i--;  
      //Stop the loop if we have enough tuples.  
      if (returnCount == 0)  
         break;  
   }  
   return returnSet.ToSet();  
}  
```  
  
 <span data-ttu-id="cc1e4-117">Das vorherige Beispiel wird in folgendem MDX-Beispiel aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="cc1e4-117">The previous example is called in the following MDX example.</span></span> <span data-ttu-id="cc1e4-118">In diesem MDX-Beispiel werden fünf Zufalls Zustände oder Provinzen aus der **Adventure Works** -Datenbank abgerufen.</span><span class="sxs-lookup"><span data-stu-id="cc1e4-118">In this MDX example, five random states or provinces are retrieved from the **Adventure Works** database.</span></span>  
  
```  
SELECT SampleAssembly.RandomSample([Geography].[State-Province].Members, 5) on ROWS,   
[Date].[Calendar].[Calendar Year] on COLUMNS  
FROM [Adventure Works]  
WHERE [Measures].[Reseller Freight Cost]  
```  
  
### <a name="applying-a-filter-to-a-tuple"></a><span data-ttu-id="cc1e4-119">Anwenden eines Filters auf ein Tupel</span><span class="sxs-lookup"><span data-stu-id="cc1e4-119">Applying a Filter to a Tuple</span></span>  
 <span data-ttu-id="cc1e4-120">In folgendem Beispiel wird eine benutzerdefinierte Funktion definiert, mit der in einem Satz unter Verwendung des Expression-Objekts ein Filter auf jedes Tupel in dem Satz angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="cc1e4-120">In the following example, a UDF is defined that takes a set, and applies a filter to each tuple in the set, using the Expression object.</span></span> <span data-ttu-id="cc1e4-121">Alle Tupel, die dem Filter entsprechen, werden einem zurückgegebenen Satz hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="cc1e4-121">Any tuples that conform to the filter will be added to a set that is returned.</span></span>  
  
 [!code-csharp[Adomd.NetServer#FilterSet](../../snippets/csharp/SQL14/adomd.net/adomd.netserver/cs/class1.cs#filterset)]  
  
 <span data-ttu-id="cc1e4-122">Das vorangegangene Beispiel wird in folgendem MDX-Beispiel aufgerufen, bei dem der Satz auf mit 'A' beginnende Städte gefiltert wird.</span><span class="sxs-lookup"><span data-stu-id="cc1e4-122">The previous example is called in the following MDX example, which filters the set to cities with names beginning with 'A'.</span></span>  
  
```  
Select Measures.Members on Rows,  
SampleAssembly.FilterSet([Customer].[Customer Geography].[City], "[Customer].[Customer Geography].[City].CurrentMember.Name < 'B'") on Columns  
From [Adventure Works]  
```  
  
## <a name="stored-procedure-example"></a><span data-ttu-id="cc1e4-123">Beispiel für gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="cc1e4-123">Stored Procedure Example</span></span>  
 <span data-ttu-id="cc1e4-124">In folgendem Beispiel verwendet eine MDX-basierte, gespeicherte Prozedur AMO, um bei Bedarf Partitionen für Internet Sales zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="cc1e4-124">In the following example, an MDX-based stored procedure uses AMO to create partitions, if needed, for Internet Sales.</span></span>  
  
 [!code-csharp[Adomd.NetServer#CreateInternetSalesMeasureGroupPartitions](../../snippets/csharp/SQL14/adomd.net/adomd.netserver/cs/class1.cs#createinternetsalesmeasuregrouppartitions)]  
  
  
