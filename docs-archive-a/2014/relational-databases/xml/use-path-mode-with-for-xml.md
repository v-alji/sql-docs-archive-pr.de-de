---
title: Verwenden des PATH-Modus mit FOR XML | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- PATH FOR XML mode
- characters [SQL Server], XML
- aliases [SQL Server], XML
- FOR XML clause, PATH mode
- FOR XML PATH mode
- column names [SQL Server]
- XPath queries [SQL Server]
ms.assetid: a685a9ad-3d28-4596-aa72-119202df3976
author: rothja
ms.author: jroth
ms.openlocfilehash: ce0cf811f1e610d14a94993b54c51ea079f613e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618558"
---
# <a name="use-path-mode-with-for-xml"></a><span data-ttu-id="cd605-102">Verwenden des PATH-Modus mit FOR XML</span><span class="sxs-lookup"><span data-stu-id="cd605-102">Use PATH Mode with FOR XML</span></span>
  <span data-ttu-id="cd605-103">Wie unter [Erstellen von XML mithilfe von FOR XML](for-xml-sql-server.md)beschrieben, bietet der PATH-Modus ein vereinfachtes Verfahren zum Mischen von Elementen und Attributen.</span><span class="sxs-lookup"><span data-stu-id="cd605-103">As described in [Constructing XML Using FOR XML](for-xml-sql-server.md), the PATH mode provides a simpler way to mix elements and attributes.</span></span> <span data-ttu-id="cd605-104">Außerdem eignet sich der PATH-Modus auch dazu, auf einfache Weise zusätzliche Schachtelungen zum Darstellen komplexer Eigenschaften einzuführen.</span><span class="sxs-lookup"><span data-stu-id="cd605-104">PATH mode is also a simpler way to introduce additional nesting for representing complex properties.</span></span> <span data-ttu-id="cd605-105">Sie können Abfragen im FOR XML EXPLICIT-Modus verwenden, um einen solchen XML-Code aus einem Rowset zu konstruieren; der PATH-Modus stellt jedoch eine einfachere Alternative zu den potenziell aufwendigen Abfragen im EXPLICIT-Modus bereit.</span><span class="sxs-lookup"><span data-stu-id="cd605-105">You can use FOR XML EXPLICIT mode queries to construct such XML from a rowset, but the PATH mode provides a simpler alternative to the potentially cumbersome EXPLICIT mode queries.</span></span> <span data-ttu-id="cd605-106">Der PATH-Modus ermöglicht in Kombination mit der Möglichkeit, verschachtelte FOR XML-Abfragen zu schreiben und die TYPE-Direktive zum Zurückgeben von Instanzen des Typs **xml** zu verwenden, das Schreiben von Abfragen mit geringerer Komplexität.</span><span class="sxs-lookup"><span data-stu-id="cd605-106">PATH mode, together with the ability to write nested FOR XML queries and the TYPE directive to return **xml** type instances, allows you to write queries with less complexity.</span></span>  
  
 <span data-ttu-id="cd605-107">Im PATH-Modus werden Spaltennamen und Spaltenaliasse als XPath-Ausdrücke behandelt.</span><span class="sxs-lookup"><span data-stu-id="cd605-107">In PATH mode, column names or column aliases are treated as XPath expressions.</span></span> <span data-ttu-id="cd605-108">Diese Ausdrücke zeigen an, wie die Werte dem XML-Code zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="cd605-108">These expressions indicate how the values are being mapped to XML.</span></span> <span data-ttu-id="cd605-109">Jeder XPath-Ausdruck ist ein relativer XPath, der den Typ des Elements bereitstellt, wie z. B. das Attribut, das Element, den skalaren Wert sowie den Namen und die Hierarchie des Knotens, der in Zusammenhang mit dem Zeilenelement generiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="cd605-109">Each XPath expression is a relative XPath that provides the item type., such as the attribute, element, and scalar value, and the name and hierarchy of the node that will be generated relative to the row element.</span></span>  
  
 <span data-ttu-id="cd605-110">In diesem Abschnitt wird das Zuordnen von Spalten in einem Rowset unter verschiedenen Bedingungen beschrieben. Zudem werden Beispiele gegeben.</span><span class="sxs-lookup"><span data-stu-id="cd605-110">This section describes mapping columns in a rowset under various conditions, and provides examples.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cd605-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="cd605-111">In This Section</span></span>  
  
-   [<span data-ttu-id="cd605-112">Spalten ohne Namen</span><span class="sxs-lookup"><span data-stu-id="cd605-112">Columns without a Name</span></span>](columns-without-a-name.md)  
  
-   [<span data-ttu-id="cd605-113">Spalten mit Namen</span><span class="sxs-lookup"><span data-stu-id="cd605-113">Columns with a Name</span></span>](columns-with-a-name.md)  
  
-   [<span data-ttu-id="cd605-114">Spalten mit als Platzhalterzeichen angegebenen Namen</span><span class="sxs-lookup"><span data-stu-id="cd605-114">Columns with a Name Specified as a Wildcard Character</span></span>](columns-with-a-name-specified-as-a-wildcard-character.md)  
  
-   [<span data-ttu-id="cd605-115">Spalten mit Namen von XPath-Knotentests</span><span class="sxs-lookup"><span data-stu-id="cd605-115">Columns with the Name of an XPath Node Test</span></span>](columns-with-the-name-of-an-xpath-node-test.md)  
  
-   [<span data-ttu-id="cd605-116">Spaltennamen, deren Pfad als „data&#40;&#41;“ angegeben ist</span><span class="sxs-lookup"><span data-stu-id="cd605-116">Column Names with the Path Specified as data&#40;&#41;</span></span>](column-names-with-the-path-specified-as-data.md)  
  
-   [<span data-ttu-id="cd605-117">Spalten, die standardmäßig einen NULL-Wert enthalten</span><span class="sxs-lookup"><span data-stu-id="cd605-117">Columns that Contain a Null Value By Default</span></span>](columns-that-contain-a-null-value-by-default.md)  
  
-   [<span data-ttu-id="cd605-118">Namespaceunterstützung im PATH-Modus</span><span class="sxs-lookup"><span data-stu-id="cd605-118">Namespace Support in PATH Mode</span></span>](namespace-support-in-path-mode.md)  
  
-   [<span data-ttu-id="cd605-119">Beispiele: Verwenden des PATH-Modus</span><span class="sxs-lookup"><span data-stu-id="cd605-119">Examples: Using PATH Mode</span></span>](examples-using-path-mode.md)  
  
## <a name="see-also"></a><span data-ttu-id="cd605-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cd605-120">See Also</span></span>  
 <span data-ttu-id="cd605-121">[Hinzufügen von Namespaces zu Abfragen mit WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md) </span><span class="sxs-lookup"><span data-stu-id="cd605-121">[Add Namespaces to Queries with WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md) </span></span>  
 <span data-ttu-id="cd605-122">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cd605-122">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 [<span data-ttu-id="cd605-123">FOR XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cd605-123">FOR XML &#40;SQL Server&#41;</span></span>](for-xml-sql-server.md)  
  
  
