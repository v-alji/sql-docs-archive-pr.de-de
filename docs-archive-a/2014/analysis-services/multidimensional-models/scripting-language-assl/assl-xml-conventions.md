---
title: ASSL-XML-Konventionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- whitespace [Analysis Services Scripting Language]
- trailing whitespace
- XSD data types [Analysis Services Scripting Language]
- inheritance [Analysis Services Scripting Language]
- cardinality [Analysis Services Scripting Language]
- white space [Analysis Services Scripting Language]
- ASSL, XML conventions
- defaults [Analysis Services Scripting Language]
- leading whitespace
- Analysis Services Scripting Language, XML conventions
- XML [Analysis Services Scripting Language]
- hierarchies [Analysis Services Scripting Language]
- inherited defaults [Analysis Services Scripting Language]
ms.assetid: bce4edad-4420-41ce-9672-8c00c5c0dec6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9b70742b07fd6450b01cf205147a05f40c4b6121
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721877"
---
# <a name="assl-xml-conventions"></a><span data-ttu-id="054c5-102">XML-Konventionen in ASSL</span><span class="sxs-lookup"><span data-stu-id="054c5-102">ASSL XML Conventions</span></span>
  <span data-ttu-id="054c5-103">Die Analysis Services Scripting Language (ASSL) stellt die Hierarchie von Objekten als Satz von Elementtypen dar, die jeweils die untergeordneten Elemente definieren, die sie enthalten können.</span><span class="sxs-lookup"><span data-stu-id="054c5-103">Analysis Services Scripting Language (ASSL) represents the hierarchy of objects as a set of element types, each of which defines the child elements they can contain.</span></span>  
  
 <span data-ttu-id="054c5-104">Für die Darstellung der Objekthierarchie verwendet ASSL folgende XML-Konventionen:</span><span class="sxs-lookup"><span data-stu-id="054c5-104">To represent the object hierarchy, ASSL uses the following XML conventions:</span></span>  
  
-   <span data-ttu-id="054c5-105">Alle Objekte und Eigenschaften werden als Elemente dargestellt, mit Ausnahme von XML-Standard Attributen wie "XML: lang".</span><span class="sxs-lookup"><span data-stu-id="054c5-105">All objects and properties are represented as elements, except for standard XML attributes such as 'xml:lang'.</span></span>  
  
-   <span data-ttu-id="054c5-106">Sowohl Elementnamen als auch Enumerationswerte befolgen die Microsoft .NET Framework-Benennungskonvention der Schreibweise von Pascal ohne Unterstriche.</span><span class="sxs-lookup"><span data-stu-id="054c5-106">Both element names and enumeration values follow the Microsoft .NET Framework naming convention of Pascal casing with no underscores.</span></span>  
  
-   <span data-ttu-id="054c5-107">Die Groß-/Kleinschreibung aller Werte wird beibehalten.</span><span class="sxs-lookup"><span data-stu-id="054c5-107">The case of all values is preserved.</span></span> <span data-ttu-id="054c5-108">Bei Werten für Enumerationen wird ebenfalls die Groß-/Kleinschreibung unterschieden.</span><span class="sxs-lookup"><span data-stu-id="054c5-108">Values for enumerations are also case-sensitive.</span></span>  
  
 <span data-ttu-id="054c5-109">Zusätzlich zu dieser Konventionsliste werden in Analysis Services bestimmte Konventionen in Bezug auf Kardinalität, Vererbung, Leerzeichen, Datentypen und Standardwerte befolgt.</span><span class="sxs-lookup"><span data-stu-id="054c5-109">In addition to this list of conventions, Analysis Services also follows certain conventions regarding cardinality, inheritance, whitespace, data types, and default values.</span></span>  
  
## <a name="cardinality"></a><span data-ttu-id="054c5-110">Kardinalität</span><span class="sxs-lookup"><span data-stu-id="054c5-110">Cardinality</span></span>  
 <span data-ttu-id="054c5-111">Wenn ein Element eine Kardinalität besitzt, die größer als 1 ist, wird dieses Element von einer XML-Elementauflistung gekapselt.</span><span class="sxs-lookup"><span data-stu-id="054c5-111">When an element has a cardinality that is greater than 1, there is an XML element collection that encapsulates this element.</span></span> <span data-ttu-id="054c5-112">Der Name der Auflistung verwendet die Pluralform der in der Auflistung enthaltenen Elemente.</span><span class="sxs-lookup"><span data-stu-id="054c5-112">The name of collection uses the plural form of the elements contained in the collection.</span></span> <span data-ttu-id="054c5-113">Das folgenden XML-Fragment stellt beispielsweise die `Dimensions`-Auflistung innerhalb eines `Database`-Elements dar:</span><span class="sxs-lookup"><span data-stu-id="054c5-113">For example, the following XML fragment represents the `Dimensions` collection within a `Database` element:</span></span>  
  
 `<Database>`  
  
 `...`  
  
 `<Dimensions>`  
  
 `<Dimension>`  
  
 `...`  
  
 `</Dimension>`  
  
 `<Dimension>`  
  
 `...`  
  
 `</Dimension>`  
  
 `</Dimensions>`  
  
 `</Database>`  
  
 ``  
  
 <span data-ttu-id="054c5-114">Die Reihenfolge der Elemente ist bedeutungslos.</span><span class="sxs-lookup"><span data-stu-id="054c5-114">The order in which elements appear is unimportant.</span></span>  
  
## <a name="inheritance"></a><span data-ttu-id="054c5-115">Vererbung</span><span class="sxs-lookup"><span data-stu-id="054c5-115">Inheritance</span></span>  
 <span data-ttu-id="054c5-116">Die Vererbung wird bei unterschiedlichen Objekten verwendet, die über überlappende, jedoch deutlich unterschiedliche Sätze von Eigenschaften verfügen.</span><span class="sxs-lookup"><span data-stu-id="054c5-116">Inheritance is used when there are distinct objects that have overlapping but significantly different sets of properties.</span></span> <span data-ttu-id="054c5-117">Beispiele für derartige überlappende, jedoch unterschiedliche Objekte sind virtuelle Cubes, verknüpfte Cubes und reguläre Cubes.</span><span class="sxs-lookup"><span data-stu-id="054c5-117">Examples of such overlapping but distinct objects are virtual cubes, linked cubes, and regular cubes.</span></span> <span data-ttu-id="054c5-118">Für überlappende, jedoch unterschiedliche Objekte wird in Analysis Services das `type`-Standardattribut aus dem XML-Instanzennamespace verwendet, um die Vererbung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="054c5-118">For overlapping but distinct object, Analysis Services uses the standard `type` attribute from the XML Instance Namespace to indicate the inheritance.</span></span> <span data-ttu-id="054c5-119">Das folgende XML-Fragment zeigt, wie das `type`-Attribut ermittelt, ob ein `Cube`-Element von einem regulären Cube oder von einem virtuellen Cube erbt:</span><span class="sxs-lookup"><span data-stu-id="054c5-119">For example, the following XML fragment shows how the `type` attribute identifies whether a `Cube` element inherits from a regular cube or from a virtual cube:</span></span>  
  
 `<Cubes>`  
  
 `<Cube xsi:type="RegularCube">`  
  
 `<Name>Sales</Name>`  
  
 `...`  
  
 `</Cube>`  
  
 `<Cube xsi:type="VirtualCube">`  
  
 `<Name>SalesAndInventory</Name>`  
  
 `...`  
  
 `</Cube>`  
  
 `</Cubes>`  
  
 ``  
  
 <span data-ttu-id="054c5-120">Die Vererbung wird im Allgemeinen nicht verwendet, wenn mehrere Typen eine Eigenschaft mit dem gleichen Namen besitzen.</span><span class="sxs-lookup"><span data-stu-id="054c5-120">Inheritance is generally not used when multiple types have a property of the same name.</span></span> <span data-ttu-id="054c5-121">Die `Name`- und die `ID`-Eigenschaft sind beispielsweise auf zahlreichen Elementen vorhanden, diese Eigenschaften wurden jedoch nicht zu einem abstrakten Typ heraufgestuft.</span><span class="sxs-lookup"><span data-stu-id="054c5-121">For example, the `Name` and `ID` properties appear on many elements, but these properties have not been promoted to an abstract type.</span></span>  
  
## <a name="whitespace"></a><span data-ttu-id="054c5-122">Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="054c5-122">Whitespace</span></span>  
 <span data-ttu-id="054c5-123">Leerzeichen innerhalb eines Elementwerts werden beibehalten.</span><span class="sxs-lookup"><span data-stu-id="054c5-123">Whitespace within an element value is preserved.</span></span> <span data-ttu-id="054c5-124">Führende und nachfolgende Leerzeichen werden jedoch immer entfernt.</span><span class="sxs-lookup"><span data-stu-id="054c5-124">However, leading and trailing whitespace is always trimmed.</span></span> <span data-ttu-id="054c5-125">Die folgenden Elemente besitzen beispielsweise den gleichen Text, jedoch eine unterschiedliche Anzahl von Leerzeichen innerhalb dieses Texts, daher werden sie behandelt, als besäßen sie unterschiedliche Werte:</span><span class="sxs-lookup"><span data-stu-id="054c5-125">For example, the following elements have the same text but differing amounts of whitespace within that text, and are therefore treated as if they have different values:</span></span>  
  
 `<Description>My text<Description>`  
  
 `<Description>My  text<Description>`  
  
 ``  
  
 <span data-ttu-id="054c5-126">Die folgenden Elemente unterscheiden sich jedoch nur durch führende und nachfolgende Leerzeichen, daher werden sie behandelt, als besäßen sie die gleichen Werte.</span><span class="sxs-lookup"><span data-stu-id="054c5-126">However, the following elements vary only in leading and trailing whitespace, and are therefore treated as if they have equivalent values:</span></span>  
  
 `<Description>My text<Description>`  
  
 `<Description>  My text  <Description>`  
  
 ``  
  
## <a name="data-types"></a><span data-ttu-id="054c5-127">Datentypen</span><span class="sxs-lookup"><span data-stu-id="054c5-127">Data Types</span></span>  
 <span data-ttu-id="054c5-128">In Analysis Services werden die folgenden XSD-Standarddatentypen (XML Schema Definition Language) verwendet:</span><span class="sxs-lookup"><span data-stu-id="054c5-128">Analysis Services uses the following standard XML Schema definition language (XSD) data types:</span></span>  
  
 `Int`  
 <span data-ttu-id="054c5-129">Ein ganzzahliger Wert im Bereich von-231 bis 231-1.</span><span class="sxs-lookup"><span data-stu-id="054c5-129">An integer value in the range of -231 to 231 - 1.</span></span>  
  
 `Long`  
 <span data-ttu-id="054c5-130">Ein ganzzahliger Wert im Bereich von-263 bis 263-1.</span><span class="sxs-lookup"><span data-stu-id="054c5-130">An integer value in range of -263 to 263 - 1.</span></span>  
  
 `String`  
 <span data-ttu-id="054c5-131">Ein Zeichenfolgenwert, der den folgenden allgemeinen Regeln entspricht:</span><span class="sxs-lookup"><span data-stu-id="054c5-131">A string value that conforms to the following global rules:</span></span>  
  
-   <span data-ttu-id="054c5-132">Steuerzeichen werden entfernt.</span><span class="sxs-lookup"><span data-stu-id="054c5-132">Control characters are stripped out.</span></span>  
  
-   <span data-ttu-id="054c5-133">Führende und nachfolgende Leerzeichen werden entfernt.</span><span class="sxs-lookup"><span data-stu-id="054c5-133">Leading and trailing white space is trimmed.</span></span>  
  
-   <span data-ttu-id="054c5-134">Interne Leerzeichen werden beibehalten.</span><span class="sxs-lookup"><span data-stu-id="054c5-134">Internal white space is preserved.</span></span>  
  
 <span data-ttu-id="054c5-135">`Name`die-Eigenschaft und die-Eigenschaft weisen `ID` besondere Einschränkungen in Form von Zeichen folgen Elementen auf.</span><span class="sxs-lookup"><span data-stu-id="054c5-135">`Name` and `ID` properties have special limitations on valid characters in string elements.</span></span> <span data-ttu-id="054c5-136">Weitere Informationen zu `Name` und `ID` Konventionen finden Sie unter [ASSL-Objekte und Objektmerkmale](assl-objects-and-object-characteristics.md).</span><span class="sxs-lookup"><span data-stu-id="054c5-136">For additional information about `Name` and `ID` conventions, see [ASSL Objects and Object Characteristics](assl-objects-and-object-characteristics.md).</span></span>  
  
 `DateTime`  
 <span data-ttu-id="054c5-137">Eine- `DateTime` Struktur aus der .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="054c5-137">A `DateTime` structure from the .NET Framework.</span></span> <span data-ttu-id="054c5-138">Ein `DateTime`-Wert darf nicht NULL sein.</span><span class="sxs-lookup"><span data-stu-id="054c5-138">A `DateTime` value cannot be NULL.</span></span> <span data-ttu-id="054c5-139">Das früheste von dem `DataTime`-Datentyp unterstützte Datum ist der 1. Januar 1601, das für Programmierer als `DateTime.MinValue` zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="054c5-139">The lowest date supported by the `DataTime` data type is January 1, 1601, which is available to programmers as `DateTime.MinValue`.</span></span> <span data-ttu-id="054c5-140">Das früheste unterstützte Datum gibt an, dass ein `DateTime`-Wert fehlt.</span><span class="sxs-lookup"><span data-stu-id="054c5-140">The lowest supported date indicates that a `DateTime` value is missing.</span></span>  
  
 `Boolean`  
 <span data-ttu-id="054c5-141">Eine Enumeration mit nur zwei Werten wie {true, false} oder {0, 1}.</span><span class="sxs-lookup"><span data-stu-id="054c5-141">An enumeration with only two values, such as {true, false} or {0, 1}.</span></span>  
  
## <a name="default-values"></a><span data-ttu-id="054c5-142">Standardwerte</span><span class="sxs-lookup"><span data-stu-id="054c5-142">Default Values</span></span>  
 <span data-ttu-id="054c5-143">Analysis Services verwendet die in der folgenden Tabelle aufgelisteten Standardwerte:</span><span class="sxs-lookup"><span data-stu-id="054c5-143">Analysis Services uses the defaults listed in the following table.</span></span>  
  
|<span data-ttu-id="054c5-144">XML-Datentyp</span><span class="sxs-lookup"><span data-stu-id="054c5-144">XML data type</span></span>|<span data-ttu-id="054c5-145">Standardwert</span><span class="sxs-lookup"><span data-stu-id="054c5-145">Default value</span></span>|  
|-------------------|-------------------|  
|`Boolean`|<span data-ttu-id="054c5-146">False</span><span class="sxs-lookup"><span data-stu-id="054c5-146">False</span></span>|  
|`String`|<span data-ttu-id="054c5-147">"" (leere Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="054c5-147">"" (empty string)</span></span>|  
|<span data-ttu-id="054c5-148">`Integer` oder `Long`</span><span class="sxs-lookup"><span data-stu-id="054c5-148">`Integer` or `Long`</span></span>|<span data-ttu-id="054c5-149">0 (Null)</span><span class="sxs-lookup"><span data-stu-id="054c5-149">0 (zero)</span></span>|  
|`Timestamp`|<span data-ttu-id="054c5-150">12:00:00 Uhr, 1/1/0001 (entspricht einem .NET Frameworks `System.DateTime` mit 0 Ticks)</span><span class="sxs-lookup"><span data-stu-id="054c5-150">12:00:00 AM, 1/1/0001 (corresponding to a the .NET Frameworks `System.DateTime` with 0 ticks)</span></span>|  
  
 <span data-ttu-id="054c5-151">Eine Element, das vorhanden, jedoch leer ist, wird interpretiert, als hätte es den Wert einer NULL-Zeichenfolge, nicht den Standardwert.</span><span class="sxs-lookup"><span data-stu-id="054c5-151">An element that is present but empty is interpreted as having a value of a null string, not the default value.</span></span>  
  
### <a name="inherited-defaults"></a><span data-ttu-id="054c5-152">Geerbte Standards</span><span class="sxs-lookup"><span data-stu-id="054c5-152">Inherited Defaults</span></span>  
 <span data-ttu-id="054c5-153">Einige auf einem Objekt angegebene Eigenschaften stellen Standardwerte für die gleiche Eigenschaft auf untergeordneten oder nachfolgenden Objekten bereit.</span><span class="sxs-lookup"><span data-stu-id="054c5-153">Some properties that are specified on an object provide default values for the same property on child or descendant objects.</span></span> <span data-ttu-id="054c5-154">Beispielsweise stellt `Cube.StorageMode` den Standardwert für `Partition.StorageMode` bereit.</span><span class="sxs-lookup"><span data-stu-id="054c5-154">For example, `Cube.StorageMode` provides the default value for `Partition.StorageMode`.</span></span> <span data-ttu-id="054c5-155">Folgende Regeln werden von Analysis Services auf geerbte Standardwerte angewendet:</span><span class="sxs-lookup"><span data-stu-id="054c5-155">The rules that Analysis Services applies for inherited default values are as follows:</span></span>  
  
-   <span data-ttu-id="054c5-156">Wenn die Eigenschaft für das untergeordnete Objekt in XML NULL ist, nimmt ihr Wert standardmäßig den geerbten Wert an.</span><span class="sxs-lookup"><span data-stu-id="054c5-156">When the property for the child object is null in the XML, its value defaults to the inherited value.</span></span> <span data-ttu-id="054c5-157">Wenn Sie den Wert jedoch vom Server abfragen, gibt der Server den NULL-Wert des XML-Elements zurück.</span><span class="sxs-lookup"><span data-stu-id="054c5-157">However, if you query the value from the server, the server returns the null value of the XML element.</span></span>  
  
-   <span data-ttu-id="054c5-158">Es ist nicht möglich, programmgesteuert festzustellen, ob die Eigenschaft eines untergeordneten Objekts direkt auf dem untergeordneten Objekt festgelegt oder geerbt wurde.</span><span class="sxs-lookup"><span data-stu-id="054c5-158">It is not possible to determine programmatically whether the property of a child object has been set directly on the child object or inherited.</span></span>  
  
 <span data-ttu-id="054c5-159">Einige Elemente besitzen definierte Standards, die gelten, wenn das Element fehlt.</span><span class="sxs-lookup"><span data-stu-id="054c5-159">Some elements have defined defaults that apply when the element is missing.</span></span> <span data-ttu-id="054c5-160">Beispielsweise entsprechen sich die `Dimension`-Elemente in den folgenden XML-Fragmenten, obwohl ein `Dimension`-Element ein `Visible`-Element enthält, das andere `Dimension`-Element jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="054c5-160">For example, the `Dimension` elements in the following XML fragment are equivalent even though one `Dimension` element contains a `Visible` element, but the other `Dimension` element does not.</span></span>  
  
 `<Dimension>`  
  
 `<Name>Product</Name>`  
  
 `</Dimension>`  
  
 `<Dimension>`  
  
 `<Name>Product</ Name>`  
  
 `<Visible>true</Visible>`  
  
 `</Dimension>`  
  
 <span data-ttu-id="054c5-161">Weitere Informationen zu geerbten Standardwerten finden Sie unter [ASSL-Objekte und Objektmerkmale](assl-objects-and-object-characteristics.md).</span><span class="sxs-lookup"><span data-stu-id="054c5-161">For more information on inherited defaults, see [ASSL Objects and Object Characteristics](assl-objects-and-object-characteristics.md).</span></span>  
  
  
