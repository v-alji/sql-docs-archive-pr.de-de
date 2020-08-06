---
title: Abfrageausdrücke und eindeutige Ressourcennamen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
helpviewer_keywords:
- query expressions
- unique resource names
- URN
ms.assetid: e0d30dbe-7daf-47eb-8412-1b96792b6fb9
author: stevestein
ms.author: sstein
ms.openlocfilehash: db6e311dd7d8a824b0e2f22e538e15eefa9fd9ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617155"
---
# <a name="query-expressions-and-uniform-resource-names"></a><span data-ttu-id="e0c70-102">Abfrageausdrücke und eindeutige Ressourcennamen</span><span class="sxs-lookup"><span data-stu-id="e0c70-102">Query Expressions and Uniform Resource Names</span></span>
  <span data-ttu-id="e0c70-103">Die SMO-Modelle ( [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Management Object) und [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell-Snap-Ins verwenden zwei Typen von Ausdruckszeichenfolgen, die XPath-Ausdrücken ähneln.</span><span class="sxs-lookup"><span data-stu-id="e0c70-103">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Management Object (SMO) models and [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell snap-ins use two types of expression strings that are similar to XPath expressions.</span></span> <span data-ttu-id="e0c70-104">Bei Abfrageausdrücken handelt es sich um Zeichenfolgen, die eine Gruppe von Kriterien angeben, mit der ein oder mehrere Objekte in einer Objektmodellhierarchie aufgezählt werden.</span><span class="sxs-lookup"><span data-stu-id="e0c70-104">Query expressions are strings that specify a set of criteria used to enumerate one or more objects in an object model hierarchy.</span></span> <span data-ttu-id="e0c70-105">Ein eindeutiger Ressourcenname (Uniform Resource Name, URN) ist ein spezieller Typ einer Abfrageausdrucks-Zeichenfolge, der ein einzelnes Objekt eindeutig kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="e0c70-105">A Uniform Resource Name (URN) is a specific type of query expression string that uniquely identifies a single object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0c70-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="e0c70-106">Syntax</span></span>  
  
```
      Object1  
      [<FilterExpression1>]/ ... /ObjectN[<FilterExpressionN>]<FilterExpression>::=  
<PropertyExpression> [and <PropertyExpression>][...n]  
  
<PropertyExpression>::=@BooleanPropertyName=true()  
 | @BooleanPropertyName=false()  
 | contains(@StringPropertyName, 'PatternString')  
  | @StringPropertyName='String'  
 | @DatePropertyName=datetime('DateString')  
 | is_null(@PropertyName)  
 | not(<PropertyExpression>)  
```  
  
## <a name="arguments"></a><span data-ttu-id="e0c70-107">Argumente</span><span class="sxs-lookup"><span data-stu-id="e0c70-107">Arguments</span></span>  
 <span data-ttu-id="e0c70-108">*Object*</span><span class="sxs-lookup"><span data-stu-id="e0c70-108">*Object*</span></span>  
 <span data-ttu-id="e0c70-109">Gibt den Typ des Objekts an, der an diesem Knoten der Ausdruckszeichenfolge dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="e0c70-109">Specifies the type of object that is represented at that node of the expression string.</span></span> <span data-ttu-id="e0c70-110">Jedes Objekt stellt eine Auflistungsklasse von diesen SMO-Objektmodellnamespaces dar:</span><span class="sxs-lookup"><span data-stu-id="e0c70-110">Each object represents a collection class from these SMO object model namespaces:</span></span>  
  
 <xref:Microsoft.SqlServer.Management.Smo>  
  
 <xref:Microsoft.SqlServer.Management.Smo.Agent>  
  
 <xref:Microsoft.SqlServer.Management.Smo.Broker>  
  
 <xref:Microsoft.SqlServer.Management.Smo.Mail>  
  
 <xref:Microsoft.SqlServer.Management.Dmf>  
  
 <xref:Microsoft.SqlServer.Management.Facets>  
  
 <xref:Microsoft.SqlServer.Management.RegisteredServers>  
  
 <xref:Microsoft.SqlServer.Management.Smo.RegSvrEnum>  
  
 <span data-ttu-id="e0c70-111">Geben Sie z.B. „Server“ für die **ServerCollection** -Klasse und „Database“ für die **DatabaseCollection** -Klasse an.</span><span class="sxs-lookup"><span data-stu-id="e0c70-111">For example, specify Server for the **ServerCollection** class, Database for the **DatabaseCollection** class.</span></span>  
  
 <span data-ttu-id="e0c70-112">\@*PropertyName*</span><span class="sxs-lookup"><span data-stu-id="e0c70-112">\@*PropertyName*</span></span>  
 <span data-ttu-id="e0c70-113">Gibt den Namen einer Eigenschaft der Klasse an, die mit dem in *Object*angegebenen Objekt verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="e0c70-113">Specifies the name of one of the properties of the class that is associated with the object specified in *Object*.</span></span> <span data-ttu-id="e0c70-114">Dem Namen der Eigenschaft muss das Zeichen \@ vorangestellt werden.</span><span class="sxs-lookup"><span data-stu-id="e0c70-114">The name of the property must be prefixed with the \@ character.</span></span> <span data-ttu-id="e0c70-115">Geben Sie z \@ . b. isansinull für die **Datenbank** -Klassen Eigenschaft **isansinull**an.</span><span class="sxs-lookup"><span data-stu-id="e0c70-115">For example, specify \@IsAnsiNull for the **Database** class property **IsAnsiNull**.</span></span>  
  
 <span data-ttu-id="e0c70-116">\@*Booleanpropertyname*= true ()</span><span class="sxs-lookup"><span data-stu-id="e0c70-116">\@*BooleanPropertyName*=true()</span></span>  
 <span data-ttu-id="e0c70-117">Listet alle Objekte auf, bei denen die angegebene boolesche Eigenschaft auf TRUE gesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="e0c70-117">Enumerates all objects where the specified Boolean property is set to TRUE.</span></span>  
  
 <span data-ttu-id="e0c70-118">\@*Booleanpropertyname*= false ()</span><span class="sxs-lookup"><span data-stu-id="e0c70-118">\@*BooleanPropertyName*=false()</span></span>  
 <span data-ttu-id="e0c70-119">Listet alle Objekte auf, bei denen die angegebene boolesche Eigenschaft auf FALSE gesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="e0c70-119">Enumerates all objects where the specified Boolean property is set to FALSE.</span></span>  
  
 <span data-ttu-id="e0c70-120">contains(\@*StringPropertyName*, '*PatternString*')</span><span class="sxs-lookup"><span data-stu-id="e0c70-120">contains(\@*StringPropertyName*, '*PatternString*')</span></span>  
 <span data-ttu-id="e0c70-121">Listet alle Objekte auf, bei denen die angegebene Zeichenfolgeneigenschaft mindestens ein Vorkommen des Zeichensatzes enthält, der in '*PatternString*' angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="e0c70-121">Enumerates all objects where the specified string property contains at least one occurrence of the set of characters that is specified in '*PatternString*'.</span></span>  
  
 <span data-ttu-id="e0c70-122">\@*Stringpropertyname*= '*patternstring*'</span><span class="sxs-lookup"><span data-stu-id="e0c70-122">\@*StringPropertyName*='*PatternString*'</span></span>  
 <span data-ttu-id="e0c70-123">Listet alle Objekte auf, bei denen der Wert der angegebenen Zeichenfolgeneigenschaft mit dem Zeichenmuster identisch ist, das in '*PatternString*' angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="e0c70-123">Enumerates all objects where the value of the specified string property is exactly the same as the character pattern that is specified in '*PatternString*'.</span></span>  
  
 <span data-ttu-id="e0c70-124">\@*Datepropertyname*= DateTime ('*DateString*')</span><span class="sxs-lookup"><span data-stu-id="e0c70-124">\@*DatePropertyName*= datetime('*DateString*')</span></span>  
 <span data-ttu-id="e0c70-125">Listet alle Objekte auf, bei denen der Wert der angegebenen Datumseigenschaft mit dem in '*DateString*' angegebenen Datum übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="e0c70-125">Enumerates all objects where the value of the specified date property matches the date that is specified in '*DateString*'.</span></span> <span data-ttu-id="e0c70-126">*DateString* muss dem Format „yyyy-mm-dd hh:mi:ss.mmm“ entsprechen.</span><span class="sxs-lookup"><span data-stu-id="e0c70-126">*DateString* must follow the format yyyy-mm-dd hh:mi:ss.mmm</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e0c70-127">yyyy</span><span class="sxs-lookup"><span data-stu-id="e0c70-127">yyyy</span></span>|<span data-ttu-id="e0c70-128">Vierstellige Jahreszahl</span><span class="sxs-lookup"><span data-stu-id="e0c70-128">Four digit year.</span></span>|  
|<span data-ttu-id="e0c70-129">MM</span><span class="sxs-lookup"><span data-stu-id="e0c70-129">mm</span></span>|<span data-ttu-id="e0c70-130">Zweistellige Monatsangabe (01 bis 12)</span><span class="sxs-lookup"><span data-stu-id="e0c70-130">Two digit month (01 through 12).</span></span>|  
|<span data-ttu-id="e0c70-131">dd</span><span class="sxs-lookup"><span data-stu-id="e0c70-131">dd</span></span>|<span data-ttu-id="e0c70-132">Zweistellige Tagesangabe (01 bis 31)</span><span class="sxs-lookup"><span data-stu-id="e0c70-132">Two digit date (01 through 31).</span></span>|  
|<span data-ttu-id="e0c70-133">hh</span><span class="sxs-lookup"><span data-stu-id="e0c70-133">hh</span></span>|<span data-ttu-id="e0c70-134">Zweistellige Angabe der Stunde im 24-Stunden-Format (01 bis 23)</span><span class="sxs-lookup"><span data-stu-id="e0c70-134">Two digit hour using a 24 hour clock (01 through 23).</span></span>|  
|<span data-ttu-id="e0c70-135">mi</span><span class="sxs-lookup"><span data-stu-id="e0c70-135">mi</span></span>|<span data-ttu-id="e0c70-136">Zweistellige Minutenangabe (01 bis 59)</span><span class="sxs-lookup"><span data-stu-id="e0c70-136">Two digit minutes (01 through 59).</span></span>|  
|<span data-ttu-id="e0c70-137">ss</span><span class="sxs-lookup"><span data-stu-id="e0c70-137">ss</span></span>|<span data-ttu-id="e0c70-138">Zweistellige Sekundenangabe (01 bis 59)</span><span class="sxs-lookup"><span data-stu-id="e0c70-138">Two digit seconds (01 through 59).</span></span>|  
|<span data-ttu-id="e0c70-139">mmm</span><span class="sxs-lookup"><span data-stu-id="e0c70-139">mmm</span></span>|<span data-ttu-id="e0c70-140">Anzahl der Millisekunden (001 bis 999)</span><span class="sxs-lookup"><span data-stu-id="e0c70-140">Number of milliseconds (001 through 999).</span></span>|  
  
 <span data-ttu-id="e0c70-141">Die in diesem Format angegebenen Daten können mit einem beliebigen Datumsformat, das in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]gespeichert ist, verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="e0c70-141">The dates that are specified in this format can be evaluated against any date format that is stored in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="e0c70-142">is_null(\@*PropertyName*)</span><span class="sxs-lookup"><span data-stu-id="e0c70-142">is_null(\@*PropertyName*)</span></span>  
 <span data-ttu-id="e0c70-143">Listet alle Objekte auf, bei denen die angegebene Eigenschaft den Wert NULL hat.</span><span class="sxs-lookup"><span data-stu-id="e0c70-143">Enumerates all objects where the specified property has a value of NULL.</span></span>  
  
 <span data-ttu-id="e0c70-144">nicht ( \<*PropertyExpression*> )</span><span class="sxs-lookup"><span data-stu-id="e0c70-144">not(\<*PropertyExpression*>)</span></span>  
 <span data-ttu-id="e0c70-145">Negiert den Evaluierungswert von *PropertyExpression*und listet alle Objekte auf, die nicht der in *PropertyExpression*angegebenen Bedingung entsprechen.</span><span class="sxs-lookup"><span data-stu-id="e0c70-145">Negates the evaluation value of the *PropertyExpression*, enumerating all objects that do not match the condition specified in *PropertyExpression*.</span></span> <span data-ttu-id="e0c70-146">Zum Beispiel listet „not(contains(\@Name, 'xyz'))“ alle Objekte auf, deren Name nicht die Zeichenfolge xyz aufweist.</span><span class="sxs-lookup"><span data-stu-id="e0c70-146">For example, not(contains(\@Name, 'xyz')) enumerates all objects that do not have the string xyz in their names.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0c70-147">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e0c70-147">Remarks</span></span>  
 <span data-ttu-id="e0c70-148">Abfrageausdrücke sind Zeichenfolgen, die die Knoten in einer SMO-Modellhierarchie auflisten.</span><span class="sxs-lookup"><span data-stu-id="e0c70-148">Query expressions are strings that enumerate the nodes in an SMO model hierarchy.</span></span> <span data-ttu-id="e0c70-149">Jeder Knoten besitzt einen Filterausdruck, der die Kriterien angibt, mit denen bestimmt werden kann, welche Objekte an diesem Knoten aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="e0c70-149">Each node has a filter expression that specifies the criteria for determining which objects at that node are enumerated.</span></span> <span data-ttu-id="e0c70-150">Abfrageausdrücke werden anhand der XPath-Ausdruckssprache modelliert.</span><span class="sxs-lookup"><span data-stu-id="e0c70-150">Query expressions are modeled on the XPath expression language.</span></span> <span data-ttu-id="e0c70-151">Abfrageausdrücke implementieren eine kleine Teilmenge von Ausdrücken, die von XPath unterstützt werden, und weisen zudem einige Erweiterungen auf, die nicht in XPath zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="e0c70-151">Query expressions implement a small subset of the expressions that are supported by XPath, and also have some extensions that are not found in XPath.</span></span> <span data-ttu-id="e0c70-152">Bei XPath-Ausdrücken handelt es sich um Zeichenfolgen, die eine Gruppe von Kriterien angeben, mit der ein oder mehrere Tags in einem XML-Dokument aufgezählt werden.</span><span class="sxs-lookup"><span data-stu-id="e0c70-152">XPath expressions are strings that specify a set of criteria that are used to enumerate one or more of the tags in an XML document.</span></span> <span data-ttu-id="e0c70-153">Weitere Informationen zu XPath finden Sie unter [W3C XPath Language](http://www.w3.org/TR/xpath20/).</span><span class="sxs-lookup"><span data-stu-id="e0c70-153">For more information about XPath, see [W3C XPath Language](http://www.w3.org/TR/xpath20/).</span></span>  
  
 <span data-ttu-id="e0c70-154">Abfrageausdrücke müssen mit einem absoluten Verweis auf das Serverobjekt beginnen.</span><span class="sxs-lookup"><span data-stu-id="e0c70-154">Query expressions must start with an absolute reference to the Server object.</span></span> <span data-ttu-id="e0c70-155">Relative Ausdrücke mit einem vorangestellten Schrägstrich (/) sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="e0c70-155">Relative expressions with a leading / are not allowed.</span></span> <span data-ttu-id="e0c70-156">Die Sequenz der Objekte, die in einem Abfrageausdruck angegeben sind, muss der Hierarchie der Auflistungsobjekte im zugeordneten Objektmodell entsprechen.</span><span class="sxs-lookup"><span data-stu-id="e0c70-156">The sequence of objects that are specified in a query expression must follow the hierarchy of collection objects in the associated object model.</span></span> <span data-ttu-id="e0c70-157">Ein Abfrageausdruck beispielsweise, der auf Objekte im Microsoft.SqlServer.Management.Smo-Namespace verweist, muss mit einem Serverknoten beginnen, gefolgt von einem Datenbankknoten usw.</span><span class="sxs-lookup"><span data-stu-id="e0c70-157">For example, a query expression that references objects in the Microsoft.SqlServer.Management.Smo namespace must start with a Server node followed by a Database node, and so on.</span></span>  
  
 <span data-ttu-id="e0c70-158">Wenn kein *\<FilterExpression>* für ein Objekt angegeben wird, werden alle Objekte an diesem Knoten aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="e0c70-158">If a *\<FilterExpression>* is not specified for an object, all the objects at that node are enumerated.</span></span>  
  
## <a name="uniform-resource-names-urn"></a><span data-ttu-id="e0c70-159">Uniform Resource Name (URN)</span><span class="sxs-lookup"><span data-stu-id="e0c70-159">Uniform Resource Names (URN)</span></span>  
 <span data-ttu-id="e0c70-160">URNs sind eine Teilmenge von Abfrageausdrücken.</span><span class="sxs-lookup"><span data-stu-id="e0c70-160">URNs are a subset of query expressions.</span></span> <span data-ttu-id="e0c70-161">Jeder URN bildet einen voll qualifizierten Verweis auf ein einzelnes Objekt.</span><span class="sxs-lookup"><span data-stu-id="e0c70-161">Each URN forms a fully-qualified reference to a single object.</span></span> <span data-ttu-id="e0c70-162">Ein typischer URN verwendet die Eigenschaft Name, um ein einzelnes Objekt an jedem Knoten zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="e0c70-162">A typical URN uses the Name property to identify a single object at each node.</span></span> <span data-ttu-id="e0c70-163">Zum Beispiel verweist dieser URN auf eine bestimmte Spalte:</span><span class="sxs-lookup"><span data-stu-id="e0c70-163">For example, this URN refers to a specific column:</span></span>  
  
```  
Server[@Name='MYCOMPUTER']/Database[@Name='AdventureWorks2012']/Table[@Name='SalesPerson' and @Schema='Sales']/Column[@Name='SalesPersonID']  
```  
  
## <a name="examples"></a><span data-ttu-id="e0c70-164">Beispiele</span><span class="sxs-lookup"><span data-stu-id="e0c70-164">Examples</span></span>  
  
### <a name="a-enumerating-objects-using-false"></a><span data-ttu-id="e0c70-165">A.</span><span class="sxs-lookup"><span data-stu-id="e0c70-165">A.</span></span> <span data-ttu-id="e0c70-166">Auflisten von Objekten mit „false()“</span><span class="sxs-lookup"><span data-stu-id="e0c70-166">Enumerating objects using false()</span></span>  
 <span data-ttu-id="e0c70-167">Dieser Abfrageausdruck listet alle Datenbanken auf, für die das Attribut **AutoClose** in der Standardinstanz unter **MyComputer**auf "false" gesetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="e0c70-167">This query expression enumerates all the databases that have the **AutoClose** attribute set to false in the default instance on **MyComputer**.</span></span>  
  
```  
Server[@Name='MYCOMPUTER']/Database[@AutoClose=false()]  
```  
  
### <a name="b-enumerating-objects-using-contains"></a><span data-ttu-id="e0c70-168">B.</span><span class="sxs-lookup"><span data-stu-id="e0c70-168">B.</span></span> <span data-ttu-id="e0c70-169">Auflisten von Objekten mit „contains“</span><span class="sxs-lookup"><span data-stu-id="e0c70-169">Enumerating objects using contains</span></span>  
 <span data-ttu-id="e0c70-170">Dieser Abfrageausdruck listet alle Datenbanken auf, bei denen die Groß-/Kleinschreibung nicht beachtet werden muss und deren Namen den Buchstaben „m“ enthalten.</span><span class="sxs-lookup"><span data-stu-id="e0c70-170">This query expression enumerates all the databases that are case-insensitive and have the character 'm' in their name.</span></span>  
  
```  
Server[@Name='MYCOMPUTER']/Database[@CaseSensitive=false() and contains(@Name, 'm')]   
```  
  
### <a name="c-enumerating-objects-using-not"></a><span data-ttu-id="e0c70-171">C.</span><span class="sxs-lookup"><span data-stu-id="e0c70-171">C.</span></span> <span data-ttu-id="e0c70-172">Auflisten von Objekten mit „not“</span><span class="sxs-lookup"><span data-stu-id="e0c70-172">Enumerating objects using not</span></span>  
 <span data-ttu-id="e0c70-173">Dieser Abfrageausdruck listet alle [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] -Tabellen auf, die nicht Bestandteil des **Production** -Schemas sind und deren Name das Wort „History“ enthält:</span><span class="sxs-lookup"><span data-stu-id="e0c70-173">This query expression enumerates all of [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] tables that are not in the **Production** schema and contain the word History in the table name:</span></span>  
  
```  
Server[@Name='MYCOMPUTER']/Database[@Name='AdventureWorks2012']/Table[not(@Schema='Production') and contains(@Name, 'History')]  
```  
  
### <a name="d-not-supplying-a-filter-expression-for-the-final-node"></a><span data-ttu-id="e0c70-174">D:</span><span class="sxs-lookup"><span data-stu-id="e0c70-174">D.</span></span> <span data-ttu-id="e0c70-175">Keine Angabe eines Filterausdrucks für den abschließenden Knoten</span><span class="sxs-lookup"><span data-stu-id="e0c70-175">Not supplying a filter expression for the final node</span></span>  
 <span data-ttu-id="e0c70-176">Dieser Abfrageausdruck listet alle Spalten in der **AdventureWorks2012.Sales.SalesPerson** -Tabelle auf:</span><span class="sxs-lookup"><span data-stu-id="e0c70-176">This query expression enumerates all the columns in the **AdventureWorks2012.Sales.SalesPerson** table:</span></span>  
  
```  
Server[@Name='MYCOMPUTER']/Database[@Name='AdventureWorks2012"]/Table[@Schema='Sales' and @Name='SalesPerson']/Columns  
```  
  
### <a name="e-enumerating-objects-using-datetime"></a><span data-ttu-id="e0c70-177">E.</span><span class="sxs-lookup"><span data-stu-id="e0c70-177">E.</span></span> <span data-ttu-id="e0c70-178">Auflisten von Objekten mit „datetime“</span><span class="sxs-lookup"><span data-stu-id="e0c70-178">Enumerating objects using datetime</span></span>  
 <span data-ttu-id="e0c70-179">Dieser Abfrageausdruck listet alle Tabellen auf, die in der [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] -Datenbank zu einem bestimmten Zeitpunkt erstellt wurden:</span><span class="sxs-lookup"><span data-stu-id="e0c70-179">This query expression enumerates all the tables that are created in the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database at a specific time:</span></span>  
  
```  
Server[@Name='MYCOMPUTER']/Database[@Name='AdventureWorks2012"]/Table[@CreateDate=datetime('2008-03-21 19:49:32.647')]  
```  
  
### <a name="f-enumerating-objects-using-is_null"></a><span data-ttu-id="e0c70-180">F.</span><span class="sxs-lookup"><span data-stu-id="e0c70-180">F.</span></span> <span data-ttu-id="e0c70-181">Auflisten von Objekten mit „is_null“</span><span class="sxs-lookup"><span data-stu-id="e0c70-181">Enumerating objects using is_null</span></span>  
 <span data-ttu-id="e0c70-182">Dieser Abfrageausdruck listet alle Tabellen in der [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] -Datenbank auf, deren Eigenschaft für das Datum der letzten Änderung nicht NULL ist:</span><span class="sxs-lookup"><span data-stu-id="e0c70-182">This query expression enumerates all the tables in the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database that do not have NULL for their date last modified property:</span></span>  
  
```  
Server[@Name='MYCOMPUTER']/Database[@Name='AdventureWorks2012"]/Table[Not(is_null(@DateLastModified))]  
```  
  
## <a name="see-also"></a><span data-ttu-id="e0c70-183">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e0c70-183">See Also</span></span>  
 <span data-ttu-id="e0c70-184">[Cmdlet "Aufruf-PolicyEvaluation"](../database-engine/invoke-policyevaluation-cmdlet.md) </span><span class="sxs-lookup"><span data-stu-id="e0c70-184">[Invoke-PolicyEvaluation cmdlet](../database-engine/invoke-policyevaluation-cmdlet.md) </span></span>  
 [<span data-ttu-id="e0c70-185">SQL Server Audit &#40;Datenbank-Engine&#41;</span><span class="sxs-lookup"><span data-stu-id="e0c70-185">SQL Server Audit &#40;Database Engine&#41;</span></span>](../relational-databases/security/auditing/sql-server-audit-database-engine.md)  
