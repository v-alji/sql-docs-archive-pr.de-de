---
title: Aufrufen gespeicherter Prozeduren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- calling stored procedures
- stored procedures [Analysis Services], calling
- MDX queries [Analysis Services]
- CALL statement
ms.assetid: 96a9660d-875b-4ee4-b339-90020b1d9895
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5c9da6edef576a6ab25c183cbc87ff95cc056845
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700442"
---
# <a name="calling-stored-procedures"></a><span data-ttu-id="b5cae-102">Aufrufen gespeicherter Prozeduren</span><span class="sxs-lookup"><span data-stu-id="b5cae-102">Calling Stored Procedures</span></span>
  <span data-ttu-id="b5cae-103">Gespeicherte Prozeduren können auf dem Server oder aus einer Clientanwendung aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="b5cae-103">Stored procedures can be called on the server or from client application.</span></span> <span data-ttu-id="b5cae-104">In beiden Fällen werden gespeicherte Prozeduren immer auf dem Server ausgeführt, entweder im Kontext des Servers oder einer Datenbank.</span><span class="sxs-lookup"><span data-stu-id="b5cae-104">In either case, stored procedures always run on the server, either the context of the server or of a database.</span></span> <span data-ttu-id="b5cae-105">Zum Ausführen einer gespeicherten Prozedur sind keine besonderen Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b5cae-105">There are no special permissions required to execute a stored procedure.</span></span> <span data-ttu-id="b5cae-106">Nach dem Hinzufügen einer gespeicherten Prozedur von einer Assembly zum Server- oder Datenbankkontext kann diese gespeicherte Prozedur von jedem Benutzer ausgeführt werden, sofern die Rolle des Benutzers die von der gespeicherten Prozedur durchgeführten Aktionen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="b5cae-106">Once a stored procedure is added by an assembly to the server or database context, any user can execute the stored procedure as long as the role for the user permits the actions performed by the stored procedure.</span></span>  
  
 <span data-ttu-id="b5cae-107">Eine gespeicherte Prozedur wird in MDX auf dieselbe Weise wie eine systeminterne MDX-Funktion aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="b5cae-107">Calling a stored procedure in MDX is done in the same manner as calling an intrinsic MDX function.</span></span> <span data-ttu-id="b5cae-108">Für eine gespeicherte Prozedur ohne Parameter wird der Name der Prozedur und ein leeres Paar Klammern verwendet, wie im Folgenden gezeigt:</span><span class="sxs-lookup"><span data-stu-id="b5cae-108">For a stored procedure that takes no parameters, the name of the procedure and an empty pair of parentheses are used, as shown here:</span></span>  
  
```  
MyStoredProcedure()  
```  
  
 <span data-ttu-id="b5cae-109">Falls die gespeicherte Prozedur Parameter hat, werden diese in der richtigen Reihenfolge, durch Kommas getrennt, angegeben.</span><span class="sxs-lookup"><span data-stu-id="b5cae-109">If the stored procedure takes one or more parameters, then the parameters are supplied, in order, separated by commas.</span></span> <span data-ttu-id="b5cae-110">Das folgende Beispiel zeigt eine gespeicherte Beispielprozedur mit drei Parametern:</span><span class="sxs-lookup"><span data-stu-id="b5cae-110">The following example demonstrates a sample stored procedure with three parameters:</span></span>  
  
```  
MyStoredProcedure("Parameter1", 2, 800)  
```  
  
## <a name="calling-stored-procedures-in-mdx-queries"></a><span data-ttu-id="b5cae-111">Aufrufen von gespeicherten Prozeduren in MDX-Abfragen</span><span class="sxs-lookup"><span data-stu-id="b5cae-111">Calling Stored Procedures in MDX Queries</span></span>  
 <span data-ttu-id="b5cae-112">In allen MDX-Abfragen muss die gespeicherte Prozedur den für einen MDX-Ausdruck erforderlichen, syntaktisch richtigen Typ zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="b5cae-112">In all MDX queries, the stored procedure must return the syntactically correct type required by an MDX expression.</span></span> <span data-ttu-id="b5cae-113">Wenn die gespeicherte Prozedur nicht den richtigen Typ zurückgibt, tritt ein MDX-Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="b5cae-113">If a stored procedure does not return the correct type, an MDX error occurs.</span></span> <span data-ttu-id="b5cae-114">Die folgenden Beispiele zeigen gespeicherte Prozeduren, die eine Menge, ein Element und das Ergebnis einer mathematischen Operation zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="b5cae-114">The following examples demonstrate stored procedures that return a set, a member, and the result of a mathematical operation.</span></span>  
  
### <a name="returning-a-set"></a><span data-ttu-id="b5cae-115">Zurückgeben einer Menge</span><span class="sxs-lookup"><span data-stu-id="b5cae-115">Returning a Set</span></span>  
 <span data-ttu-id="b5cae-116">In den folgenden Beispielen wird die gespeicherte Prozedur MySproc implementiert, die eine Menge zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="b5cae-116">The following examples implement a stored procedure, called MySproc, that returns a set.</span></span> <span data-ttu-id="b5cae-117">Im ersten Beispiel gibt MySproc die Menge direkt an den SELECT-Ausdruck zurück.</span><span class="sxs-lookup"><span data-stu-id="b5cae-117">In the first example, MySproc returns the set directly in the SELECT expression.</span></span> <span data-ttu-id="b5cae-118">In den nächsten beiden Beispielen gibt MySproc die Menge als Argument für die Funktionen Crossjoin und DrilldownLevel zurück.</span><span class="sxs-lookup"><span data-stu-id="b5cae-118">In the second two examples, MySproc returns the set as an argument for the Crossjoin and DrilldownLevel functions.</span></span>  
  
```  
SELECT MySetProcedure(a,b,c) ON 0 FROM Sales  
SELECT Crossjoin(MySetProcedure(a,b,c)) ON 0 FROM Sales  
SELECT DrilldownLevel(MySetProcedure(a,b,c)) ON 0 FROM Sales  
```  
  
### <a name="returning-a-member"></a><span data-ttu-id="b5cae-119">Zurückgeben eines Elements</span><span class="sxs-lookup"><span data-stu-id="b5cae-119">Returning a Member</span></span>  
 <span data-ttu-id="b5cae-120">Das folgende Beispiel zeigt die Funktion MySproc, die ein Element zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="b5cae-120">The following example shows a function MySproc function that returns a member:</span></span>  
  
```  
SELECT Descendants(MySproc(a,b,c),3) ON 0 FROM Sales  
```  
  
### <a name="returning-the-result-of-a-math-operation"></a><span data-ttu-id="b5cae-121">Zurückgeben des Ergebnisses einer mathematischen Operation</span><span class="sxs-lookup"><span data-stu-id="b5cae-121">Returning the Result of a Math Operation</span></span>  
  
```  
SELECT Country.Members on 0, MySproc(Measures.Sales) ON 1 FROM Sales  
```  
  
## <a name="calling-stored-procedures-with-the-call-statement"></a><span data-ttu-id="b5cae-122">Aufrufen von gespeicherten Prozeduren mit der CALL-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b5cae-122">Calling Stored Procedures with the Call Statement</span></span>  
 <span data-ttu-id="b5cae-123">Gespeicherte Prozeduren können mithilfe der MDX-Anweisung `Call` außerhalb des Kontexts einer MDX-Abfrage aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="b5cae-123">Stored procedures can be called outside of the context of an MDX query using the MDX `Call` statement.</span></span>  
  
 <span data-ttu-id="b5cae-124">Sie können diese Methode verwenden, um entweder die Nebeneffekte einer gespeicherten Abfrage zu instanziieren, oder damit die Anwendung die Ergebnisse einer gespeicherten Abfrage erhält.</span><span class="sxs-lookup"><span data-stu-id="b5cae-124">You can use this method to either instantiate the side effects of a stored query or for the application to get the results of a stored query.</span></span> <span data-ttu-id="b5cae-125">Die `Call`-Anweisung wird häufig verwendet, um mithilfe von Analysis Management Objects (AMO) administrative Funktionen auszuführen, die kein Ergebnis zurückzugeben brauchen.</span><span class="sxs-lookup"><span data-stu-id="b5cae-125">A common use of the `Call` statement would be to use Analysis Management Objects (AMO) to perform administrative functions that do not have a return result.</span></span> <span data-ttu-id="b5cae-126">Der folgende Befehl ruft beispielsweise eine gespeicherte Prozedur auf:</span><span class="sxs-lookup"><span data-stu-id="b5cae-126">For example, the following command calls a stored procedure:</span></span>  
  
```  
Call MyStoredProcedure(a,b,c)  
```  
  
 <span data-ttu-id="b5cae-127">Rowset ist der einzige unterstützte Typ, der von einer gespeicherten Prozedur in einer `Call`-Anweisung zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b5cae-127">The only supported type returned from stored procedure in a `Call` statement is a rowset.</span></span> <span data-ttu-id="b5cae-128">Die Serialisierung für ein Rowset wird durch XML for Analysis definiert.</span><span class="sxs-lookup"><span data-stu-id="b5cae-128">The serialization for a rowset is defined by XML for Analysis.</span></span> <span data-ttu-id="b5cae-129">Wenn eine gespeicherte Prozedur in einer `Call`-Anweisung einen anderen Typ zurückgibt, wird dieser ignoriert und nicht in XML an die aufrufende Anwendung zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b5cae-129">If a stored procedure in a `Call` statement returns any other type, it is ignored and not returned in XML to the calling application.</span></span> <span data-ttu-id="b5cae-130">Weitere Informationen zu XMLA-Rowsets (XML for Analysis) finden Sie unter XMLA-Schemarowsets.</span><span class="sxs-lookup"><span data-stu-id="b5cae-130">For more information about XML for Analysis rowsets, see, XML for Analysis Schema Rowsets.</span></span>  
  
 <span data-ttu-id="b5cae-131">Wenn eine gespeicherte Prozedur ein .NET-Rowset zurückgibt, konvertiert [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] das Ergebnis auf dem Server in ein XMLA-Rowset.</span><span class="sxs-lookup"><span data-stu-id="b5cae-131">If a stored procedure returns a .NET rowset, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] converts the result on the server to an XML for Analysis rowset.</span></span> <span data-ttu-id="b5cae-132">Das XMLA-Rowset wird immer von einer gespeicherten Prozedur in der `Call`-Funktion zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b5cae-132">The XML for Analysis rowset is always returned by a stored procedure in the `Call` function.</span></span> <span data-ttu-id="b5cae-133">Wenn ein Dataset Funktionen enthält, die nicht in einem XMLA-Rowset ausgedrückt werden können, tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="b5cae-133">If a dataset contains features that cannot be expressed in the XML for Analysis rowset, a failure results.</span></span>  
  
 <span data-ttu-id="b5cae-134">Prozeduren, die void zurückgeben (wie z. B. Unterroutinen in Visual Basic), können ebenfalls mit dem CALL-Schlüsselwort verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b5cae-134">Procedures that return void values (for example, subroutines in Visual Basic) can also be employed with the CALL keyword.</span></span> <span data-ttu-id="b5cae-135">Beispielsweise wird die MyVoidFunction()-Funktion in einer MDX-Anweisung mit folgender Syntax verwendet:</span><span class="sxs-lookup"><span data-stu-id="b5cae-135">If, for example, you wanted to use the function MyVoidFunction() in an MDX statement, the following syntax would be employed:</span></span>  
  
```  
CALL(MyVoidFunction)  
```  
  
## <a name="see-also"></a><span data-ttu-id="b5cae-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b5cae-136">See Also</span></span>  
 <span data-ttu-id="b5cae-137">[Verwaltung von mehrdimensionalen Modellen](../multidimensional-models/multidimensional-model-assemblies-management.md) </span><span class="sxs-lookup"><span data-stu-id="b5cae-137">[Multidimensional Model Assemblies Management](../multidimensional-models/multidimensional-model-assemblies-management.md) </span></span>  
 [<span data-ttu-id="b5cae-138">Definieren von gespeicherten Proze</span><span class="sxs-lookup"><span data-stu-id="b5cae-138">Defining Stored Procedures</span></span>](../multidimensional-models-extending-olap-stored-procedures/defining-stored-procedures.md)  
  
  
