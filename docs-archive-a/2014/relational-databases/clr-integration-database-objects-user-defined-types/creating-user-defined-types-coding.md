---
title: Codieren von benutzerdefinierten Typen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- validation [CLR integration]
- UDTs [CLR integration], coding
- UserDefined serialization format [CLR integration]
- Point UDT
- Parse method
- null values [CLR integration]
- ToString method
- ValidatePoint method
- attributes [CLR integration]
- coding user-defined types [CLR integration]
- Read method
- Write method
- nullability [CLR integration]
- user-defined types [CLR integration], coding
- Currency UDT
- validating UDT values
- exposing UDT properties [CLR integration]
ms.assetid: 1e5b43b3-4971-45ee-a591-3f535e2ac722
author: rothja
ms.author: jroth
ms.openlocfilehash: 4e88c4d8162e5c7c921f5c5062f5b3c23df40a2b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609919"
---
# <a name="coding-user-defined-types"></a><span data-ttu-id="8c6fd-102">Programmieren benutzerdefinierter Typen</span><span class="sxs-lookup"><span data-stu-id="8c6fd-102">Coding User-Defined Types</span></span>
  <span data-ttu-id="8c6fd-103">Wenn Sie die Definition eines benutzerdefinierten Typs (UDT) schreiben, müssen Sie verschiedene Funktionen implementieren, abhängig davon, ob Sie den UDT als Klasse oder als Struktur implementieren, sowie abhängig von den von Ihnen gewählten Format- und Serialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-103">When coding your user-defined type (UDT) definition, you must implement various features, depending on whether you are implementing the UDT as a class or a structure, as well as on the format and serialization options you have chosen.</span></span>  
  
 <span data-ttu-id="8c6fd-104">Das Codebeispiel in diesem Abschnitt veranschaulicht die Implementierung eines UDT namens `Point` als `struct` (bzw. `Structure` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="8c6fd-104">The example in this section illustrates implementing a `Point` UDT as a `struct` (or `Structure` in Visual Basic).</span></span> <span data-ttu-id="8c6fd-105">Der UDT `Point` besteht aus X- und Y-Koordinaten, die als Eigenschaftenprozeduren implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-105">The `Point` UDT consists of X and Y coordinates implemented as property procedures.</span></span>  
  
 <span data-ttu-id="8c6fd-106">Beim Definieren eines UDTs sind die folgenden Namespaces erforderlich:</span><span class="sxs-lookup"><span data-stu-id="8c6fd-106">The following namespaces are required when defining a UDT:</span></span>  
  
```vb  
Imports System  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
```  
  
```csharp  
using System;  
using System.Data.SqlTypes;  
using Microsoft.SqlServer.Server;  
```  
  
 <span data-ttu-id="8c6fd-107">Der `Microsoft.SqlServer.Server`-Namespace enthält die Objekte, die für verschiedene Attribute des UDT erforderlich sind, und der `System.Data.SqlTypes`-Namespace enthält die Klassen, die systemeigenen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datentypen, die für die Assembly verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-107">The `Microsoft.SqlServer.Server` namespace contains the objects required for various attributes of your UDT, and the `System.Data.SqlTypes` namespace contains the classes that represent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native data types available to the assembly.</span></span> <span data-ttu-id="8c6fd-108">Es kann natürlich zusätzliche Namespaces geben, die eine Assembly erfordert, um ordnungsgemäß zu funktionieren.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-108">There may of course be additional namespaces that your assembly requires in order to function correctly.</span></span> <span data-ttu-id="8c6fd-109">Der `Point`-UDT verwendet überdies den `System.Text`-Namespace zum Arbeiten mit Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-109">The `Point` UDT also uses the `System.Text` namespace for working with strings.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8c6fd-110">Visual C++-Datenbankobjekte wie UDTs, die mit `/clr:pure` kompiliert wurden, werden nicht für die Ausführung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-110">Visual C++ database objects, such as UDTs, compiled with `/clr:pure` are not supported for execution.</span></span>  
  
## <a name="specifying-attributes"></a><span data-ttu-id="8c6fd-111">Angeben von Attributen</span><span class="sxs-lookup"><span data-stu-id="8c6fd-111">Specifying Attributes</span></span>  
 <span data-ttu-id="8c6fd-112">Attribute bestimmen, wie die Serialisierung verwendet wird, um die Speicherdarstellung von UDTs zu erstellen und um UDTs durch Werte an den Client zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-112">Attributes determine how serialization is used to construct the storage representation of UDTs and to transmit UDTs by value to the client.</span></span>  
  
 <span data-ttu-id="8c6fd-113">Die `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute` ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-113">The `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute` is required.</span></span> <span data-ttu-id="8c6fd-114">Das `Serializable`-Attribut ist optional.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-114">The `Serializable` attribute is optional.</span></span> <span data-ttu-id="8c6fd-115">Sie können auch das `Microsoft.SqlServer.Server.SqlFacetAttribute`-Attribut angeben, um Informationen über den Rückgabetyp eines UDTs bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-115">You can also specify the `Microsoft.SqlServer.Server.SqlFacetAttribute` to provide information about the return type of a UDT.</span></span> <span data-ttu-id="8c6fd-116">Weitere Informationen finden Sie unter [Benutzerdefinierte Attribute für CLR-Routinen](../clr-integration/database-objects/clr-integration-custom-attributes-for-clr-routines.md).</span><span class="sxs-lookup"><span data-stu-id="8c6fd-116">For more information, see [Custom Attributes for CLR Routines](../clr-integration/database-objects/clr-integration-custom-attributes-for-clr-routines.md).</span></span>  
  
### <a name="point-udt-attributes"></a><span data-ttu-id="8c6fd-117">Attribute des Point-UDT</span><span class="sxs-lookup"><span data-stu-id="8c6fd-117">Point UDT Attributes</span></span>  
 <span data-ttu-id="8c6fd-118">`Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute` legt das Speicherformat für den `Point`-UDT auf `Native` fest.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-118">The `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute` sets the storage format for the `Point` UDT to `Native`.</span></span> <span data-ttu-id="8c6fd-119">`IsByteOrdered` wird auf `true` festgelegt. Dies garantiert, dass Vergleiche in SQL Server dieselben Ergebnisse liefern wie Vergleiche in verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-119">`IsByteOrdered` is set to `true`, which guarantees that the results of comparisons are the same in SQL Server as if the same comparison had taken place in managed code.</span></span> <span data-ttu-id="8c6fd-120">Der UDT implementiert die `System.Data.SqlTypes.INullable`-Schnittstelle, damit der UDT NULL erkennt.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-120">The UDT implements the `System.Data.SqlTypes.INullable` interface to make the UDT null aware.</span></span>  
  
 <span data-ttu-id="8c6fd-121">Das folgende Codefragment zeigt die Attribute für den `Point`-UDT.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-121">The following code fragment shows the attributes for the `Point` UDT.</span></span>  
  
```vb  
<Serializable(), SqlUserDefinedTypeAttribute(Format.Native, _  
  IsByteOrdered:=True)> _  
  Public Structure Point  
    Implements INullable  
```  
  
```csharp  
[Serializable]  
[Microsoft.SqlServer.Server.SqlUserDefinedType(Format.Native,  
  IsByteOrdered=true)]  
public struct Point : INullable  
{  
```  
  
## <a name="implementing-nullability"></a><span data-ttu-id="8c6fd-122">Implementieren von NULL-Zulässigkeit</span><span class="sxs-lookup"><span data-stu-id="8c6fd-122">Implementing Nullability</span></span>  
 <span data-ttu-id="8c6fd-123">Zusätzlich zum ordnungsgemäßen Angeben der Attribute für die Assemblys muss der UDT auch die NULL-Zulässigkeit unterstützen.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-123">In addition to specifying the attributes for your assemblies correctly, your UDT must also support nullability.</span></span> <span data-ttu-id="8c6fd-124">UDTs, die in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] geladen werden, erkennen Nullwerte, aber damit der UDT einen Nullwert erkennt, muss der UDT die `System.Data.SqlTypes.INullable`-Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-124">UDTs loaded into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are null-aware, but in order for the UDT to recognize a null value, the UDT must implement the `System.Data.SqlTypes.INullable` interface.</span></span>  
  
 <span data-ttu-id="8c6fd-125">Sie müssen eine Eigenschaft namens `IsNull` erstellen, mit der im CLR-Code bestimmt werden kann, ob ein Wert NULL ist.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-125">You must create a property named `IsNull`, which is needed to determine whether a value is null from within CLR code.</span></span> <span data-ttu-id="8c6fd-126">Wenn [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] eine NULL-Instanz eines UDTs findet, wird der UDT mit normalen Behandlungsmethoden für NULL-Werte persistent gespeichert.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-126">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] finds a null instance of a UDT, the UDT is persisted using normal null-handling methods.</span></span> <span data-ttu-id="8c6fd-127">Der Server vergeudet keine Zeit mit dem Serialisieren oder Deserialisieren des UDTs, wenn dies nicht erforderlich ist, und er verschwendet keinen Platz zum Speichern des NULL-UDTs.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-127">The server does not waste time serializing or deserializing the UDT if it does not have to, and it does not waste space to store a null UDT.</span></span> <span data-ttu-id="8c6fd-128">Diese Überprüfung auf NULL wird jedes Mal durchgeführt, wenn ein UDT von der CLR übernommen wird. Das heißt, dass mit dem [!INCLUDE[tsql](../../includes/tsql-md.md)]-Konstrukt immer überprüft werden kann, ob UDTs NULL sind.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-128">This check for nulls is performed every time a UDT is brought over from the CLR, which means that using the [!INCLUDE[tsql](../../includes/tsql-md.md)] IS NULL construct to check for null UDTs should always work.</span></span> <span data-ttu-id="8c6fd-129">Die `IsNull`-Eigenschaft wird auch vom Server verwendet, um zu testen, ob eine Instanz NULL ist.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-129">The `IsNull` property is also used by the server to test whether an instance is null.</span></span> <span data-ttu-id="8c6fd-130">Sobald der Server bestimmt, dass der UDT NULL ist, kann er seine systemeigene NULL-Behandlung verwenden.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-130">Once the server determines that the UDT is null, it can use its native null handling.</span></span>  
  
 <span data-ttu-id="8c6fd-131">Die `get()`-Methode von `IsNull` stellt in keiner Weise einen Sonderfall dar.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-131">The `get()` method of `IsNull` is not special-cased in any way.</span></span> <span data-ttu-id="8c6fd-132">Wenn eine `Point`-Variable `@p` gleich `Null` ist, dann ergibt `@p.IsNull` standardmäßig "NULL", nicht "1".</span><span class="sxs-lookup"><span data-stu-id="8c6fd-132">If a `Point` variable `@p` is `Null`, then `@p.IsNull` will, by default, evaluate to "NULL", not "1".</span></span> <span data-ttu-id="8c6fd-133">Dies ist so, weil das `SqlMethod(OnNullCall)`-Attribut der `IsNull get()`-Methode den Standardwert false hat.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-133">This is because the `SqlMethod(OnNullCall)` attribute of the `IsNull get()` method defaults to false.</span></span> <span data-ttu-id="8c6fd-134">Weil das Objekt `Null` ist, wird es nicht deserialisiert, wenn die Eigenschaft angefordert wird, die Methode wird nicht aufgerufen, und der Standardwert "NULL" wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-134">Because the object is `Null`, when the property is requested the object is not deserialized, the method is not called, and a default value of "NULL" is returned.</span></span>  
  
### <a name="example"></a><span data-ttu-id="8c6fd-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8c6fd-135">Example</span></span>  
 <span data-ttu-id="8c6fd-136">Im folgenden Beispiel ist die `is_Null`-Variable privat und enthält für die Instanz des UDT den Status NULL.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-136">In the following example, the `is_Null` variable is private and holds the state of null for the instance of the UDT.</span></span> <span data-ttu-id="8c6fd-137">Im Code muss ein entsprechender Wert für `is_Null` verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-137">Your code must maintain an appropriate value for `is_Null`.</span></span> <span data-ttu-id="8c6fd-138">Der UDT muss auch über eine statische Eigenschaft namens `Null` verfügen, welche die NULL-Wertinstanz des UDTs zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-138">The UDT must also have a static property named `Null` that returns a null value instance of the UDT.</span></span> <span data-ttu-id="8c6fd-139">Dadurch kann der UDT einen NULL-Wert zurückgeben, wenn die Instanz auch in der Datenbank tatsächlich NULL ist.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-139">This allows the UDT to return a null value if the instance is indeed null in the database.</span></span>  
  
```vb  
Private is_Null As Boolean  
  
Public ReadOnly Property IsNull() As Boolean _  
   Implements INullable.IsNull  
    Get  
        Return (is_Null)  
    End Get  
End Property  
  
Public Shared ReadOnly Property Null() As Point  
    Get  
        Dim pt As New Point  
        pt.is_Null = True  
        Return (pt)  
    End Get  
End Property  
```  
  
```csharp  
private bool is_Null;  
  
public bool IsNull  
{  
    get  
    {  
        return (is_Null);  
    }  
}  
  
public static Point Null  
{  
    get  
    {  
        Point pt = new Point();  
        pt.is_Null = true;  
        return pt;  
    }  
}  
```  
  
### <a name="is-null-vs-isnull"></a><span data-ttu-id="8c6fd-140">IS NULL und IsNull</span><span class="sxs-lookup"><span data-stu-id="8c6fd-140">IS NULL vs. IsNull</span></span>  
 <span data-ttu-id="8c6fd-141">Betrachten Sie eine Tabelle, die das Schema Points(id int, location Point), wobei `Point` ein CLR UDT ist, und die folgenden Abfragen enthält:</span><span class="sxs-lookup"><span data-stu-id="8c6fd-141">Consider a table that contains the schema Points(id int, location Point), where `Point` is a CLR UDT, and the following queries:</span></span>  
  
```  
--Query 1  
SELECT ID  
FROM Points  
WHERE NOT (location IS NULL) -- Or, WHERE location IS NOT NULL;  
```  
  
```  
--Query 2:  
SELECT ID  
FROM Points  
WHERE location.IsNull = 0;  
```  
  
 <span data-ttu-id="8c6fd-142">Beide Abfragen geben die IDs von Punkten mit Positionen ungleich `Null` zurück.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-142">Both queries return the IDs of points with non-`Null` locations.</span></span> <span data-ttu-id="8c6fd-143">In Abfrage 1 wird die normale NULL-Behandlung verwendet, und dort ist keine Deserialisierung von UDTs erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-143">In Query 1, normal null-handling is used, and there no deserialization of UDTs is required.</span></span> <span data-ttu-id="8c6fd-144">In Abfrage 2 dagegen muss jedes Objekt, das nicht `Null` ist, deserialisiert und die CLR aufgerufen werden, um den Wert der `IsNull`-Eigenschaft zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-144">Query 2, on the other hand, has to deserialize each non-`Null` object and call into the CLR to obtain the value of the `IsNull` property.</span></span> <span data-ttu-id="8c6fd-145">Der Einsatz von `IS NULL` zeigt eindeutig ein besseres Leistungsverhalten, und es sollte nie notwendig sein, die `IsNull`-Eigenschaft eines UDT über [!INCLUDE[tsql](../../includes/tsql-md.md)]-Code abzurufen.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-145">Clearly, using `IS NULL` will exhibit better performance and there should never be a reason to read the `IsNull` property of a UDT from [!INCLUDE[tsql](../../includes/tsql-md.md)] code.</span></span>  
  
 <span data-ttu-id="8c6fd-146">Wozu dient also die `IsNull`-Eigenschaft?</span><span class="sxs-lookup"><span data-stu-id="8c6fd-146">So, what is the use of the `IsNull` property?</span></span> <span data-ttu-id="8c6fd-147">Erstens wird sie benötigt, damit im CLR-Code bestimmt werden kann, ob ein Wert `Null` ist.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-147">First, it is needed to determine whether a value is `Null` from within CLR code.</span></span> <span data-ttu-id="8c6fd-148">Zweitens muss der Server prüfen können, ob eine Instanz `Null` ist, und hierzu wird diese Eigenschaft vom Server verwendet.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-148">Second, the server needs a way to test whether an instance is `Null`, so this property is used by the server.</span></span> <span data-ttu-id="8c6fd-149">Sobald der Server bestimmt hat, dass die Instanz UDT `Null` ist, kann er seine systemeigene NULL-Behandlung verwenden.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-149">After it determines it is `Null`, then it can use its native null handling to handle it.</span></span>  
  
## <a name="implementing-the-parse-method"></a><span data-ttu-id="8c6fd-150">Implementieren der Parse-Methode</span><span class="sxs-lookup"><span data-stu-id="8c6fd-150">Implementing the Parse Method</span></span>  
 <span data-ttu-id="8c6fd-151">Die `Parse`-Methode und die `ToString`-Methode ermöglichen die Konvertierung des UDT in Zeichenfolgendarstellungen und umgekehrt von Zeichenfolgen in den UDT.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-151">The `Parse` and `ToString` methods allow for conversions to and from string representations of the UDT.</span></span> <span data-ttu-id="8c6fd-152">Die `Parse`-Methode lässt das Konvertieren einer Zeichenfolge in einen UDT zu.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-152">The `Parse` method allows a string to be converted into a UDT.</span></span> <span data-ttu-id="8c6fd-153">Die Zeichenfolge muss als `static` (oder `Shared` in Visual Basic) deklariert werden und einen Parameter vom Typ `System.Data.SqlTypes.SqlString` verwenden.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-153">It must be declared as `static` (or `Shared` in Visual Basic), and take a parameter of type `System.Data.SqlTypes.SqlString`.</span></span>  
  
 <span data-ttu-id="8c6fd-154">Im folgenden Code wird die `Parse`-Methode für den `Point`-UDT implementiert, welche die X- und Y-Koordinaten einer Instanz einzeln ausgibt.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-154">The following code implements the `Parse` method for the `Point` UDT, which separates out the X and Y coordinates.</span></span> <span data-ttu-id="8c6fd-155">Die `Parse`-Methode verfügt über nur ein Argument des Typs `System.Data.SqlTypes.SqlString` und setzt voraus, dass die X- und Y-Werte in einer durch Komma begrenzten Zeichenfolge übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-155">The `Parse` method has a single argument of type `System.Data.SqlTypes.SqlString`, and assumes that X and Y values are supplied as a comma-delimited string.</span></span> <span data-ttu-id="8c6fd-156">Durch die Festlegung des `Microsoft.SqlServer.Server.SqlMethodAttribute.OnNullCall`-Attributs auf `false` wird verhindert, dass die `Parse`-Methode für eine NULL-Instanz von Point aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-156">Setting the `Microsoft.SqlServer.Server.SqlMethodAttribute.OnNullCall` attribute to `false` prevents the `Parse` method from being called from a null instance of Point.</span></span>  
  
```vb  
<SqlMethod(OnNullCall:=False)> _  
Public Shared Function Parse(ByVal s As SqlString) As Point  
    If s.IsNull Then  
        Return Null  
    End If  
  
    ' Parse input string here to separate out points.  
    Dim pt As New Point()  
    Dim xy() As String = s.Value.Split(",".ToCharArray())  
    pt.X = Int32.Parse(xy(0))  
    pt.Y = Int32.Parse(xy(1))  
    Return pt  
End Function  
```  
  
```csharp  
[SqlMethod(OnNullCall = false)]  
public static Point Parse(SqlString s)  
{  
    if (s.IsNull)  
        return Null;  
  
    // Parse input string to separate out points.  
    Point pt = new Point();  
    string[] xy = s.Value.Split(",".ToCharArray());  
    pt.X = Int32.Parse(xy[0]);  
    pt.Y = Int32.Parse(xy[1]);  
    return pt;  
}  
```  
  
## <a name="implementing-the-tostring-method"></a><span data-ttu-id="8c6fd-157">Implementieren der ToString-Methode</span><span class="sxs-lookup"><span data-stu-id="8c6fd-157">Implementing the ToString Method</span></span>  
 <span data-ttu-id="8c6fd-158">Die `ToString`-Methode konvertiert den `Point`-UDT in einen Zeichenfolgenwert.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-158">The `ToString` method converts the `Point` UDT to a string value.</span></span> <span data-ttu-id="8c6fd-159">In diesem Fall wird die Zeichenfolge "NULL" für eine NULL-Instanz des `Point`-Typs zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-159">In this case, the string "NULL" is returned for a Null instance of the `Point` type.</span></span> <span data-ttu-id="8c6fd-160">Die `ToString`-Methode kehrt das Ergebnis der `Parse`-Methode mithilfe eines `System.Text.StringBuilder` um und gibt eine durch Kommas begrenzte `System.String`-Instanz zurück, die aus den Koordinatenwerten X und Y besteht.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-160">The `ToString` method reverses the `Parse` method by using a `System.Text.StringBuilder` to return a comma-delimited `System.String` consisting of the X and Y coordinate values.</span></span> <span data-ttu-id="8c6fd-161">Da **InvokeIfReceiverIsNull** standardmäßig auf false festgelegt ist, ist die Überprüfung auf eine NULL-Instanz nicht `Point` erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-161">Because **InvokeIfReceiverIsNull** defaults to false, the check for a null instance of `Point` is unnecessary.</span></span>  
  
```vb  
Private _x As Int32  
Private _y As Int32  
  
Public Overrides Function ToString() As String  
    If Me.IsNull Then  
        Return "NULL"  
    Else  
        Dim builder As StringBuilder = New StringBuilder  
        builder.Append(_x)  
        builder.Append(",")  
        builder.Append(_y)  
        Return builder.ToString  
    End If  
End Function  
```  
  
```csharp  
private Int32 _x;  
private Int32 _y;  
  
public override string ToString()  
{  
    if (this.IsNull)  
        return "NULL";  
    else  
    {  
        StringBuilder builder = new StringBuilder();  
        builder.Append(_x);  
        builder.Append(",");  
        builder.Append(_y);  
        return builder.ToString();  
    }  
}  
```  
  
## <a name="exposing-udt-properties"></a><span data-ttu-id="8c6fd-162">Bereitstellen der UDT-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="8c6fd-162">Exposing UDT Properties</span></span>  
 <span data-ttu-id="8c6fd-163">Der UDT `Point` macht die X- und Y-Koordinaten verfügbar, die als öffentliche Eigenschaften des `System.Int32`-Typs mit Lese-/Schreibzugriff implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-163">The `Point` UDT exposes X and Y coordinates that are implemented as public read-write properties of type `System.Int32`.</span></span>  
  
```vb  
Public Property X() As Int32  
    Get  
        Return (Me._x)  
    End Get  
  
    Set(ByVal Value As Int32)  
        _x = Value  
    End Set  
End Property  
  
Public Property Y() As Int32  
    Get  
        Return (Me._y)  
    End Get  
  
    Set(ByVal Value As Int32)  
        _y = Value  
    End Set  
End Property  
```  
  
```csharp  
public Int32 X  
{  
    get  
    {  
        return this._x;  
    }  
    set   
    {  
        _x = value;  
    }  
}  
  
public Int32 Y  
{  
    get  
    {  
        return this._y;  
    }  
    set  
    {  
        _y = value;  
    }  
}  
```  
  
## <a name="validating-udt-values"></a><span data-ttu-id="8c6fd-164">Überprüfen von UDT-Werten</span><span class="sxs-lookup"><span data-stu-id="8c6fd-164">Validating UDT Values</span></span>  
 <span data-ttu-id="8c6fd-165">Beim Verarbeiten von UDT-Daten konvertiert [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] automatisch Binärwerte in UDT-Werte.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-165">When working with UDT data, [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] automatically converts binary values to UDT values.</span></span> <span data-ttu-id="8c6fd-166">Im Rahmen dieses Konvertierungsprozesses muss überprüft werden, ob sich die Werte für das Serialisierungsformat des Typs eignen, und sichergestellt werden, dass die Werte ordnungsgemäß deserialisiert werden können.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-166">This conversion process involves checking that values are appropriate for the serialization format of the type and ensuring that the value can be deserialized correctly.</span></span> <span data-ttu-id="8c6fd-167">Damit wird sichergestellt, dass der Wert in das binäre Format zurückkonvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-167">This ensures that the value can be converted back to binary form.</span></span> <span data-ttu-id="8c6fd-168">Bei UDTs, deren Sortierreihenfolge eine Bytereihenfolge ist, wird dadurch auch sichergestellt, dass der resultierende Binärwert dem ursprünglichen Binärwert entspricht.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-168">In the case of byte-ordered UDTs, this also ensures that the resulting binary value matches the original binary value.</span></span> <span data-ttu-id="8c6fd-169">So wird verhindert, dass ungültige Werte in der Datenbank persistent gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-169">This prevents invalid values from being persisted in the database.</span></span> <span data-ttu-id="8c6fd-170">In einigen Fällen ist diese Art der Überprüfung möglicherweise unzulänglich.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-170">In some cases, this level of checking may be inadequate.</span></span> <span data-ttu-id="8c6fd-171">Eine zusätzliche Überprüfung kann erforderlich sein, wenn UDT-Werte in einer bestimmten Domäne oder einem Bereich liegen müssen.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-171">Additional validation may be required when UDT values are required to be in an expected domain or range.</span></span> <span data-ttu-id="8c6fd-172">Ein UDT beispielsweise, der ein Datum implementiert, kann erfordern, dass der Wert für den Tag eine positive Zahl ist, die in einem bestimmten zulässigen Wertebereich liegt.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-172">For example, a UDT that implements a date might require the day value to be a positive number that falls within a certain range of valid values.</span></span>  
  
 <span data-ttu-id="8c6fd-173">In der `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute.ValidationMethodName`-Eigenschaft von `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute` können Sie den Namen einer Überprüfungsmethode angeben, die der Server ausführt, wenn Daten einem UDT zugewiesen oder in einen UDT konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-173">The `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute.ValidationMethodName` property of the `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute` allows you to supply the name of a validation method that the server runs when data is assigned to a UDT or converted to a UDT.</span></span> <span data-ttu-id="8c6fd-174">`ValidationMethodName` wird auch beim Ausführen des bcp-Hilfsprogramms, bei BULK INSERT, DBCC CHECKDB, DBCC CHECKFILEGROUP, DBCC CHECKTABLE und verteilten Abfragen sowie bei TDS-Vorgängen (Tabular Data Stream) und Remoteprozeduraufrufen (Remote Procedure Call, RPC) aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-174">`ValidationMethodName` is also called during the running of the bcp utility, BULK INSERT, DBCC CHECKDB, DBCC CHECKFILEGROUP, DBCC CHECKTABLE, distributed query, and tabular data stream (TDS) remote procedure call (RPC) operations.</span></span> <span data-ttu-id="8c6fd-175">Der Standardwert für `ValidationMethodName` lautet NULL, womit angegeben wird, dass keine Validierungsmethode festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-175">The default value for `ValidationMethodName` is null, indicating that there is no validation method.</span></span>  
  
### <a name="example"></a><span data-ttu-id="8c6fd-176">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8c6fd-176">Example</span></span>  
 <span data-ttu-id="8c6fd-177">Das folgende Codefragment zeigt die Deklaration für die `Point`-Klasse, die mit `ValidationMethodName` als Validierungsmethode `ValidatePoint` angibt.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-177">The following code fragment shows the declaration for the `Point` class, which specifies a `ValidationMethodName` of `ValidatePoint`.</span></span>  
  
```vb  
<Serializable(), SqlUserDefinedTypeAttribute(Format.Native, _  
  IsByteOrdered:=True, _  
  ValidationMethodName:="ValidatePoint")> _  
  Public Structure Point  
```  
  
```csharp  
[Serializable]  
[Microsoft.SqlServer.Server.SqlUserDefinedType(Format.Native,  
  IsByteOrdered=true,   
  ValidationMethodName = "ValidatePoint")]  
public struct Point : INullable  
{  
```  
  
 <span data-ttu-id="8c6fd-178">Wenn eine Validierungsmethode angegeben wird, muss diese eine Signatur aufweisen, die etwa folgendem Codefragment entspricht:</span><span class="sxs-lookup"><span data-stu-id="8c6fd-178">If a validation method is specified, it must have a signature that looks like the following code fragment.</span></span>  
  
```vb  
Private Function ValidationFunction() As Boolean  
    If (validation logic here) Then  
        Return True  
    Else  
        Return False  
    End If  
End Function  
```  
  
```csharp  
private bool ValidationFunction()  
{  
    if (validation logic here)  
    {  
        return true;  
    }  
    else  
    {  
        return false;  
    }  
}  
```  
  
 <span data-ttu-id="8c6fd-179">Die Validierungsmethode kann einen beliebigen Gültigkeitsbereich haben und sollte `true` zurückgeben, wenn der Wert zulässig ist, und andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-179">The validation method can have any scope and should return `true` if the value is valid, and `false` otherwise.</span></span> <span data-ttu-id="8c6fd-180">Wenn die Methode `false` zurückgibt oder eine Ausnahme auslöst, wird der Wert als nicht zulässig behandelt, und es wird ein Fehler generiert.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-180">If the method returns `false` or throws an exception, the value is treated as not valid and an error is raised.</span></span>  
  
 <span data-ttu-id="8c6fd-181">Im nachstehenden Beispiel lässt der Code für die X- und Y-Koordinaten nur Werte zu, die größer oder gleich Null sind.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-181">In the example below, the code allows only values of zero or greater the X and Y coordinates.</span></span>  
  
```vb  
Private Function ValidatePoint() As Boolean  
    If (_x >= 0) And (_y >= 0) Then  
        Return True  
    Else  
        Return False  
    End If  
End Function  
```  
  
```csharp  
private bool ValidatePoint()  
{  
    if ((_x >= 0) && (_y >= 0))  
    {  
        return true;  
    }  
    else  
    {  
        return false;  
    }  
}  
```  
  
### <a name="validation-method-limitations"></a><span data-ttu-id="8c6fd-182">Einschränkungen von Validierungsmethoden</span><span class="sxs-lookup"><span data-stu-id="8c6fd-182">Validation Method Limitations</span></span>  
 <span data-ttu-id="8c6fd-183">Der Server ruft die Validierungsmethode auf, wenn er Konvertierungen durchführt, nicht wenn Daten durch das Festlegen einzelner Eigenschaften oder mithilfe der [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisung INSERT eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-183">The server calls the validation method when the server is performing conversions, not when data is inserted by setting individual properties or when data is inserted using a [!INCLUDE[tsql](../../includes/tsql-md.md)] INSERT statement.</span></span>  
  
 <span data-ttu-id="8c6fd-184">Sie müssen die Validierungsmethode explizit aus den Eigenschaften Settern und der-Methode aufzurufen `Parse` , wenn Sie die Validierungsmethode in allen Situationen ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-184">You must explicitly call the validation method from property setters and the `Parse` method if you want the validation method to execute in all situations.</span></span> <span data-ttu-id="8c6fd-185">Dies ist keine Voraussetzung, und in einigen Fällen ist es möglicherweise nicht einmal wünschenswert.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-185">This is not a requirement, and in some cases may not even be desirable.</span></span>  
  
### <a name="parse-validation-example"></a><span data-ttu-id="8c6fd-186">Beispiel für die Validierung in der Parse-Methode</span><span class="sxs-lookup"><span data-stu-id="8c6fd-186">Parse Validation Example</span></span>  
 <span data-ttu-id="8c6fd-187">Um sicherzustellen, dass die- `ValidatePoint` Methode in der `Point` -Klasse aufgerufen wird, müssen Sie Sie aus der `Parse` -Methode und aus den-Eigenschaften Prozeduren aufrufen, die die X-und Y-Koordinaten Werte festlegen.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-187">To ensure that the `ValidatePoint` method is invoked in the `Point` class, you must call it from the `Parse` method and from the property procedures that set the X and Y coordinate values.</span></span> <span data-ttu-id="8c6fd-188">Das folgende Code Fragment zeigt, wie die `ValidatePoint` Validierungsmethode von der- `Parse` Funktion aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-188">The following code fragment shows how to call the `ValidatePoint` validation method from the `Parse` function.</span></span>  
  
```vb  
<SqlMethod(OnNullCall:=False)> _  
Public Shared Function Parse(ByVal s As SqlString) As Point  
    If s.IsNull Then  
        Return Null  
    End If  
  
    ' Parse input string here to separate out points.  
    Dim pt As New Point()  
    Dim xy() As String = s.Value.Split(",".ToCharArray())  
    pt.X = Int32.Parse(xy(0))  
    pt.Y = Int32.Parse(xy(1))  
  
    ' Call ValidatePoint to enforce validation  
    ' for string conversions.  
    If Not pt.ValidatePoint() Then  
        Throw New ArgumentException("Invalid XY coordinate values.")  
    End If  
    Return pt  
End Function  
```  
  
```csharp  
[SqlMethod(OnNullCall = false)]  
public static Point Parse(SqlString s)  
{  
    if (s.IsNull)  
        return Null;  
  
    // Parse input string to separate out points.  
    Point pt = new Point();  
    string[] xy = s.Value.Split(",".ToCharArray());  
    pt.X = Int32.Parse(xy[0]);  
    pt.Y = Int32.Parse(xy[1]);  
  
    // Call ValidatePoint to enforce validation  
    // for string conversions.  
    if (!pt.ValidatePoint())   
        throw new ArgumentException("Invalid XY coordinate values.");  
    return pt;  
}  
```  
  
### <a name="property-validation-example"></a><span data-ttu-id="8c6fd-189">Beispiel für die Validierung von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="8c6fd-189">Property Validation Example</span></span>  
 <span data-ttu-id="8c6fd-190">Das folgende Code Fragment zeigt, wie die `ValidatePoint` Validierungsmethode aus den Eigenschaften Prozeduren aufgerufen wird, die die X-und Y-Koordinaten festlegen.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-190">The following code fragment shows how to call the `ValidatePoint` validation method from the property procedures that set the X and Y coordinates.</span></span>  
  
```vb  
Public Property X() As Int32  
    Get  
        Return (Me._x)  
    End Get  
  
    Set(ByVal Value As Int32)  
        Dim temp As Int32 = _x  
        _x = Value  
        If Not ValidatePoint() Then  
            _x = temp  
            Throw New ArgumentException("Invalid X coordinate value.")  
        End If  
    End Set  
End Property  
  
Public Property Y() As Int32  
    Get  
        Return (Me._y)  
    End Get  
  
    Set(ByVal Value As Int32)  
        Dim temp As Int32 = _y  
        _y = Value  
        If Not ValidatePoint() Then  
            _y = temp  
            Throw New ArgumentException("Invalid Y coordinate value.")  
        End If  
    End Set  
End Property  
```  
  
```csharp  
    public Int32 X  
{  
    get  
    {  
        return this._x;  
    }  
    // Call ValidatePoint to ensure valid range of Point values.  
    set   
    {  
        Int32 temp = _x;  
        _x = value;  
        if (!ValidatePoint())  
        {  
            _x = temp;  
            throw new ArgumentException("Invalid X coordinate value.");  
        }  
    }  
}  
  
public Int32 Y  
{  
    get  
    {  
        return this._y;  
    }  
    set  
    {  
        Int32 temp = _y;  
        _y = value;  
        if (!ValidatePoint())  
        {  
            _y = temp;  
            throw new ArgumentException("Invalid Y coordinate value.");  
        }  
    }  
}  
```  
  
## <a name="coding-udt-methods"></a><span data-ttu-id="8c6fd-191">Codieren von UDT-Methoden</span><span class="sxs-lookup"><span data-stu-id="8c6fd-191">Coding UDT Methods</span></span>  
 <span data-ttu-id="8c6fd-192">Bei Codieren von UDT-Methoden müssen Sie berücksichtigen, ob sich der verwendete Algorithmus möglicherweise im Lauf der Zeit ändern könnte.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-192">When coding UDT methods, consider whether the algorithm used could possibly change over time.</span></span> <span data-ttu-id="8c6fd-193">Wenn dem so ist, sollten Sie erwägen, eine separate Klasse für die vom UDT verwendeten Methoden zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-193">If so, you may want to consider creating a separate class for the methods your UDT uses.</span></span> <span data-ttu-id="8c6fd-194">Wenn sich der Algorithmus ändert, können Sie die Klasse mit dem neuen Code erneut kompilieren und die Assembly in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] laden, ohne den UDT dadurch zu beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-194">If the algorithm changes, you can recompile the class with the new code and load the assembly into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] without affecting the UDT.</span></span> <span data-ttu-id="8c6fd-195">In vielen Fälle können UDTs mithilfe der [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisung ALTER ASSEMBLY erneut geladen werden, dies könnte jedoch potenziell zu Problemen mit vorhandenen Daten führen.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-195">In many cases UDTs can be reloaded using the [!INCLUDE[tsql](../../includes/tsql-md.md)] ALTER ASSEMBLY statement, but that could potentially cause problems with existing data.</span></span> <span data-ttu-id="8c6fd-196">Beispielsweise verwendet der `Currency` UDT, der in der **AdventureWorks** -Beispieldatenbank enthalten ist, eine **ConvertCurrency** -Funktion zum Konvertieren von Währungswerten, die in einer separaten Klasse implementiert sind.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-196">For example, the `Currency` UDT included with the **AdventureWorks** sample database uses a **ConvertCurrency** function to convert currency values, which is implemented in a separate class.</span></span> <span data-ttu-id="8c6fd-197">Es ist möglich, dass sich die Konvertierungsalgorithmen in der Zukunft auf unvorhersehbare Weise ändern oder dass eine neue Funktionalität erforderlich wird.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-197">It is possible that conversion algorithms may change in unpredictable ways in the future, or that new functionality may be required.</span></span> <span data-ttu-id="8c6fd-198">Das Trennen der **ConvertCurrency** -Funktion von der `Currency` UDT-Implementierung bietet mehr Flexibilität bei der Planung zukünftiger Änderungen.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-198">Separating the **ConvertCurrency** function from the `Currency` UDT implementation provides greater flexibility when planning for future changes.</span></span>  
  
### <a name="example"></a><span data-ttu-id="8c6fd-199">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8c6fd-199">Example</span></span>  
 <span data-ttu-id="8c6fd-200">Die- `Point` Klasse enthält drei einfache Methoden zum Berechnen der Entfernung: **Distance**, **DistanceFrom** und **DistanceFromXY**.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-200">The `Point` class contains three simple methods for calculating distance: **Distance**, **DistanceFrom** and **DistanceFromXY**.</span></span> <span data-ttu-id="8c6fd-201">Jede dieser Methoden gibt einen Wert vom Typ `double` zurück, wobei die Entfernung von `Point` zum Nullpunkt, die Entfernung von einem angegebenen Punkt zu `Point` und die Entfernung von den angegebenen X- und Y-Koordinaten zu `Point` berechnet wird</span><span class="sxs-lookup"><span data-stu-id="8c6fd-201">Each returns a `double` calculating the distance from `Point` to zero, the distance from a specified point to `Point`, and the distance from specified X and Y coordinates to `Point`.</span></span> <span data-ttu-id="8c6fd-202">**Distance** und **DistanceFrom** alle Aufrufe von **DistanceFromXY**und veranschaulichen, wie für jede Methode verschiedene Argumente verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-202">**Distance** and **DistanceFrom** each call **DistanceFromXY**, and demonstrate how to use different arguments for each method.</span></span>  
  
```vb  
' Distance from 0 to Point.  
<SqlMethod(OnNullCall:=False)> _  
Public Function Distance() As Double  
    Return DistanceFromXY(0, 0)  
End Function  
  
' Distance from Point to the specified point.  
<SqlMethod(OnNullCall:=False)> _  
Public Function DistanceFrom(ByVal pFrom As Point) As Double  
    Return DistanceFromXY(pFrom.X, pFrom.Y)  
End Function  
  
' Distance from Point to the specified x and y values.  
<SqlMethod(OnNullCall:=False)> _  
Public Function DistanceFromXY(ByVal ix As Int32, ByVal iy As Int32) _  
    As Double  
    Return Math.Sqrt(Math.Pow(ix - _x, 2.0) + Math.Pow(iy - _y, 2.0))  
End Function  
```  
  
```csharp  
// Distance from 0 to Point.  
[SqlMethod(OnNullCall = false)]  
public Double Distance()  
{  
    return DistanceFromXY(0, 0);  
}  
  
// Distance from Point to the specified point.  
[SqlMethod(OnNullCall = false)]  
public Double DistanceFrom(Point pFrom)  
{  
    return DistanceFromXY(pFrom.X, pFrom.Y);  
}  
  
// Distance from Point to the specified x and y values.  
[SqlMethod(OnNullCall = false)]  
public Double DistanceFromXY(Int32 iX, Int32 iY)  
{  
    return Math.Sqrt(Math.Pow(iX - _x, 2.0) + Math.Pow(iY - _y, 2.0));  
}  
```  
  
### <a name="using-sqlmethod-attributes"></a><span data-ttu-id="8c6fd-203">Verwenden von SqlMethod-Attributen</span><span class="sxs-lookup"><span data-stu-id="8c6fd-203">Using SqlMethod Attributes</span></span>  
 <span data-ttu-id="8c6fd-204">Die `Microsoft.SqlServer.Server.SqlMethodAttribute`-Klasse stellt benutzerdefinierte Attribute zur Verfügung, mit denen Methodendefinitionen markiert werden können, um einen Determinismus anzugeben, das Verhalten beim Aufruf für NULL-Werte festzulegen und anzugeben, ob eine Methode eine Mutatormethode ist.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-204">The `Microsoft.SqlServer.Server.SqlMethodAttribute` class provides custom attributes that can be used to mark method definitions in order to specify determinism, on null call behavior, and to specify whether a method is a mutator.</span></span> <span data-ttu-id="8c6fd-205">Bei diesen Eigenschaften werden die Standardwerte vorausgesetzt, und das benutzerdefinierte Attribut wird nur verwendet, wenn ein anderer Wert als der Standardwert erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-205">Default values for these properties are assumed, and the custom attribute is only used when a non-default value is needed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8c6fd-206">Die `SqlMethodAttribute`-Klasse erbt von der `SqlFunctionAttribute`-Klasse, daher erbt die `SqlMethodAttribute`-Klasse die Felder `FillRowMethodName` und `TableDefinition` von `SqlFunctionAttribute`.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-206">The `SqlMethodAttribute` class inherits from the `SqlFunctionAttribute` class, so `SqlMethodAttribute` inherits the `FillRowMethodName` and `TableDefinition` fields from `SqlFunctionAttribute`.</span></span> <span data-ttu-id="8c6fd-207">Dies impliziert, dass es möglich ist, eine Tabellenwertmethode zu schreiben. Dies ist jedoch nicht der Fall.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-207">This implies that it is possible to write a table-valued method, which is not the case.</span></span> <span data-ttu-id="8c6fd-208">Die-Methode wird kompiliert, und die Assembly wird bereitgestellt, aber ein Fehler des `IEnumerable` Rückgabe Typs wird zur Laufzeit mit der folgenden Meldung ausgelöst: "die Methode, die Eigenschaft oder das Feld" \<name> "in der Klasse" " \<class> in der Assembly" \<assembly> "weist einen ungültigen Rückgabetyp auf."</span><span class="sxs-lookup"><span data-stu-id="8c6fd-208">The method compiles and the assembly deploys, but an error about the `IEnumerable` return type is raised at runtime with the following message: "Method, property, or field '\<name>' in class '\<class>' in assembly '\<assembly>' has invalid return type."</span></span>  
  
 <span data-ttu-id="8c6fd-209">In der folgenden Tabelle werden einige der relevanten `Microsoft.SqlServer.Server.SqlMethodAttribute`-Eigenschaften beschrieben, die in UDT-Methoden verwendet werden können, und die zugehörigen Standardwerte aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-209">The following table describes some of the relevant `Microsoft.SqlServer.Server.SqlMethodAttribute` properties that can be used in UDT methods, and lists their default values.</span></span>  
  
 <span data-ttu-id="8c6fd-210">DataAccess</span><span class="sxs-lookup"><span data-stu-id="8c6fd-210">DataAccess</span></span>  
 <span data-ttu-id="8c6fd-211">Gibt an, ob die Funktion auf die in der lokalen Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gespeicherten Benutzerdaten zugreift.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-211">Indicates whether the function involves access to user data stored in the local instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="8c6fd-212">Der Standardwert lautet `DataAccessKind``None`.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-212">Default is `DataAccessKind`.`None`.</span></span>  
  
 <span data-ttu-id="8c6fd-213">IsDeterministic</span><span class="sxs-lookup"><span data-stu-id="8c6fd-213">IsDeterministic</span></span>  
 <span data-ttu-id="8c6fd-214">Gibt an, ob die Funktion bei denselben Eingabewerten und demselben Datenbankzustand auch immer dieselben Ausgabewerte erzeugt.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-214">Indicates whether the function produces the same output values given the same input values and the same database state.</span></span> <span data-ttu-id="8c6fd-215">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-215">Default is `false`.</span></span>  
  
 <span data-ttu-id="8c6fd-216">IsMutator</span><span class="sxs-lookup"><span data-stu-id="8c6fd-216">IsMutator</span></span>  
 <span data-ttu-id="8c6fd-217">Gibt an, ob die Methode eine Statusänderung in der UDT-Instanz verursacht.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-217">Indicates whether the method causes a state change in the UDT instance.</span></span> <span data-ttu-id="8c6fd-218">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-218">Default is `false`.</span></span>  
  
 <span data-ttu-id="8c6fd-219">IsPrecise</span><span class="sxs-lookup"><span data-stu-id="8c6fd-219">IsPrecise</span></span>  
 <span data-ttu-id="8c6fd-220">Gibt an, ob die Funktion ungenaue Berechnungen beinhaltet, z. B. Gleitkommaoperationen.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-220">Indicates whether the function involves imprecise computations, such as floating point operations.</span></span> <span data-ttu-id="8c6fd-221">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-221">Default is `false`.</span></span>  
  
 <span data-ttu-id="8c6fd-222">OnNullCall</span><span class="sxs-lookup"><span data-stu-id="8c6fd-222">OnNullCall</span></span>  
 <span data-ttu-id="8c6fd-223">Gibt an, ob die Methode aufgerufen wird, wenn als Eingabeargumente NULL-Verweise angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-223">Indicates whether the method is called when null reference input arguments are specified.</span></span> <span data-ttu-id="8c6fd-224">Der Standardwert ist `true`.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-224">Default is `true`.</span></span>  
  
### <a name="example"></a><span data-ttu-id="8c6fd-225">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8c6fd-225">Example</span></span>  
 <span data-ttu-id="8c6fd-226">Mit der `Microsoft.SqlServer.Server.SqlMethodAttribute.IsMutator`-Eigenschaft können Sie eine Methode markieren, die eine Änderung des Status einer Instanz eines UDTs gestattet.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-226">The `Microsoft.SqlServer.Server.SqlMethodAttribute.IsMutator` property allows you to mark a method that allows a change in the state of an instance of a UDT.</span></span> <span data-ttu-id="8c6fd-227">Mit [!INCLUDE[tsql](../../includes/tsql-md.md)] ist es nicht möglich, zwei UDT-Eigenschaften in der SET-Klausel einer UPDATE-Anweisung festzulegen.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-227">[!INCLUDE[tsql](../../includes/tsql-md.md)] does not allow you to set two UDT properties in the SET clause of one UPDATE statement.</span></span> <span data-ttu-id="8c6fd-228">Sie können jedoch eine Methode als Mutator markieren, die zwei Elemente ändert.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-228">However, you can have a method marked as a mutator that changes the two members.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8c6fd-229">In Abfragen sind Mutatormethoden nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-229">Mutator methods are not allowed in queries.</span></span> <span data-ttu-id="8c6fd-230">Sie können nur in Zuweisungsanweisungen oder Datenänderungsanweisungen aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-230">They can be called only in assignment statements or data modification statements.</span></span> <span data-ttu-id="8c6fd-231">Wenn eine als Mutatormethode gekennzeichnete Methode nicht `void` zurückgibt (oder kein `Sub` in Visual Basic ist), führt CREATE TYPE zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-231">If a method marked as mutator does not return `void` (or is not a `Sub` in Visual Basic), CREATE TYPE fails with an error.</span></span>  
  
 <span data-ttu-id="8c6fd-232">Die folgende Anweisung setzt die Existenz des UDTs `Triangles` voraus, der über die `Rotate`-Methode verfügt.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-232">The following statement assumes the existence of a `Triangles` UDT that has a `Rotate` method.</span></span> <span data-ttu-id="8c6fd-233">In der folgenden [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisung UPDATE wird die `Rotate`-Methode aufgerufen:</span><span class="sxs-lookup"><span data-stu-id="8c6fd-233">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] update statement invokes the `Rotate` method:</span></span>  
  
```  
UPDATE Triangles SET t.RotateY(0.6) WHERE id=5  
```  
  
 <span data-ttu-id="8c6fd-234">Die `Rotate`-Methode ist mit dem `SqlMethod`-Attribut ausgezeichnet, mit dem `IsMutator` auf `true` festgelegt wird, sodass [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] die Methode als Mutatormethode markieren kann.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-234">The `Rotate` method is decorated with the `SqlMethod` attribute setting `IsMutator` to `true` so that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can mark the method as a mutator method.</span></span> <span data-ttu-id="8c6fd-235">Im Code wird zudem `OnNullCall` auf `false` festgelegt. Dem Server wird damit angegeben, dass die Methode einen NULL-Verweis (`Nothing` in Visual Basic) zurückgibt, wenn einer der Eingabeparameter einen NULL-Verweis enthält.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-235">The code also sets `OnNullCall` to `false`, which indicates to the server that the method returns a null reference (`Nothing` in Visual Basic) if any of the input parameters are null references.</span></span>  
  
```vb  
<SqlMethod(IsMutator:=True, OnNullCall:=False)> _  
Public Sub Rotate(ByVal anglex as Double, _  
  ByVal angley as Double, ByVal anglez As Double)   
   RotateX(anglex)  
   RotateY(angley)  
   RotateZ(anglez)  
End Sub  
```  
  
```csharp  
[SqlMethod(IsMutator = true, OnNullCall = false)]  
public void Rotate(double anglex, double angley, double anglez)   
{  
   RotateX(anglex);  
   RotateY(angley);  
   RotateZ(anglez);  
}  
```  
  
## <a name="implementing-a-udt-with-a-user-defined-format"></a><span data-ttu-id="8c6fd-236">Implementieren eines UDTs mit einem benutzerdefinierten Format</span><span class="sxs-lookup"><span data-stu-id="8c6fd-236">Implementing a UDT with a User-Defined Format</span></span>  
 <span data-ttu-id="8c6fd-237">Zur Implementierung eines UDTs mit einem benutzerdefinierten Format müssen Sie die `Read`-Methode und die `Write`-Methode implementieren. Diese Methoden implementieren die Microsoft.SqlServer.Server.IBinarySerialize-Schnittstelle zur Serialisierung und Deserialisierung der UDT-Daten.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-237">When implementing a UDT with a user-defined format, you must implement `Read` and `Write` methods that implement the Microsoft.SqlServer.Server.IBinarySerialize interface to handle serializing and deserializing UDT data.</span></span> <span data-ttu-id="8c6fd-238">Sie müssen zudem die `MaxByteSize`-Eigenschaft des `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute`-Attributs angeben.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-238">You must also specify the `MaxByteSize` property of the `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute`.</span></span>  
  
### <a name="the-currency-udt"></a><span data-ttu-id="8c6fd-239">Der UDT Currency</span><span class="sxs-lookup"><span data-stu-id="8c6fd-239">The Currency UDT</span></span>  
 <span data-ttu-id="8c6fd-240">Der UDT `Currency` ist seit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in den CLR-Beispielen enthalten, die zusammen mit [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] installiert werden können.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-240">The `Currency` UDT is included with the CLR samples that can be installed with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
 <span data-ttu-id="8c6fd-241">Der UDT `Currency` kann Währungsbeträge im Währungssystem eines bestimmten Lands verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-241">The `Currency` UDT supports handling amounts of money in the monetary system of a particular culture.</span></span> <span data-ttu-id="8c6fd-242">Sie müssen zwei Felder definieren: ein `string`-Feld für `CultureInfo`, das angibt, welches Land die Währung ausgegeben hat (beispielsweise en-us) und ein `decimal`-Feld für `CurrencyValue`, den Währungsbetrag.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-242">You must define two fields: a `string` for `CultureInfo`, which specifies who issued the currency (en-us, for example) and a `decimal` for `CurrencyValue`, the amount of money.</span></span>  
  
 <span data-ttu-id="8c6fd-243">Obwohl sie vom Server nicht zum Durchführen von Vergleichen verwendet wird, implementiert der UDT `Currency` die `System.IComparable`-Schnittstelle, die nur eine Methode namens `System.IComparable.CompareTo` bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-243">Although it is not used by the server for performing comparisons, the `Currency` UDT implements the `System.IComparable` interface, which exposes a single method, `System.IComparable.CompareTo`.</span></span> <span data-ttu-id="8c6fd-244">Diese Methode wird auf Clientseite in Situationen verwendet, in denen Currency-Werte genau verglichen oder geordnet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-244">This is used on the client side in situations where it is desirable to accurately compare or order currency values within cultures.</span></span>  
  
 <span data-ttu-id="8c6fd-245">Im Code, der in der CLR ausgeführt wird, wird die Länderangabe getrennt vom Währungswert verglichen.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-245">Code running in the CLR compares the culture separately from the currency value.</span></span> <span data-ttu-id="8c6fd-246">Im [!INCLUDE[tsql](../../includes/tsql-md.md)]-Code bestimmen die folgenden Aktionen den Vergleich:</span><span class="sxs-lookup"><span data-stu-id="8c6fd-246">For [!INCLUDE[tsql](../../includes/tsql-md.md)] code, the following actions determine the comparison:</span></span>  
  
1.  <span data-ttu-id="8c6fd-247">Legen Sie das `IsByteOrdered`-Attribut auf true fest, um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] anzuweisen, die auf dem Datenträger persistent gespeicherte binäre Darstellung für Vergleiche zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-247">Set the `IsByteOrdered` attribute to true, which tells [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to use the persisted binary representation on disk for comparisons.</span></span>  
  
2.  <span data-ttu-id="8c6fd-248">Bestimmen Sie mithilfe der `Write`-Methode für den UDT `Currency`, wie der UDT auf dem Datenträger persistent gespeichert wird und wie die UDT-Werte infolgedessen in [!INCLUDE[tsql](../../includes/tsql-md.md)]-Vorgängen verglichen und angeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-248">Use the `Write` method for the `Currency` UDT to determine how the UDT is persisted on disk and therefore how UDT values are compared and ordered for [!INCLUDE[tsql](../../includes/tsql-md.md)] operations.</span></span>  
  
3.  <span data-ttu-id="8c6fd-249">Speichern Sie den UDT `Currency` im folgenden binären Format:</span><span class="sxs-lookup"><span data-stu-id="8c6fd-249">Save the `Currency` UDT using the following binary format:</span></span>  
  
    1.  <span data-ttu-id="8c6fd-250">Speichern Sie die Länderangabe als UTF-16-codierte Zeichenfolge für die Bytes 0 bis 19, wobei die Zeichenfolge rechts mit NULL-Zeichen aufgefüllt werden soll.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-250">Save the culture as a UTF-16 encoded string for bytes 0-19 with padding to the right with null characters.</span></span>  
  
    2.  <span data-ttu-id="8c6fd-251">Verwenden Sie Bytes 20 und nachfolgende Bytes zum Speichern des Dezimalwerts der Währungsbetrags.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-251">Use bytes 20 and above to contain the decimal value of the currency.</span></span>  
  
 <span data-ttu-id="8c6fd-252">Durch die Auffüllung wird gewährleistet, dass die Länderangabe vollständig vom Währungsbetrag getrennt ist, sodass beim Vergleich zweier UDT-Werte im [!INCLUDE[tsql](../../includes/tsql-md.md)]-Code jeweils die Bytes mit den Länderangaben und die Bytes mit den Währungsbeträgen miteinander verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-252">The purpose of the padding is to ensure that the culture is completely separated from the currency value, so that when one UDT is compared against another in [!INCLUDE[tsql](../../includes/tsql-md.md)] code, culture bytes are compared against culture bytes, and currency byte values are compared against currency byte values.</span></span>  
  
 <span data-ttu-id="8c6fd-253">Die komplette Code Auflistung für den `Currency` UDT finden Sie in den Anweisungen zum Installieren der CLR-Beispiele in [SQL Server Datenbank-Engine Beispiele](https://msftengprodsamples.codeplex.com/).</span><span class="sxs-lookup"><span data-stu-id="8c6fd-253">For the complete code listing for the `Currency` UDT, follow the directions for installing the CLR samples in [SQL Server Database Engine Samples](https://msftengprodsamples.codeplex.com/).</span></span>  
  
### <a name="currency-attributes"></a><span data-ttu-id="8c6fd-254">Currency-Attribute</span><span class="sxs-lookup"><span data-stu-id="8c6fd-254">Currency Attributes</span></span>  
 <span data-ttu-id="8c6fd-255">Der UDT `Currency` wurde mit den folgenden Attributen definiert.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-255">The `Currency` UDT is defined with the following attributes.</span></span>  
  
```vb  
<Serializable(), Microsoft.SqlServer.Server.SqlUserDefinedType( _  
    Microsoft.SqlServer.Server.Format.UserDefined, _  
    IsByteOrdered:=True, MaxByteSize:=32), _  
    CLSCompliant(False)> _  
Public Structure Currency  
Implements INullable, IComparable, _  
Microsoft.SqlServer.Server.IBinarySerialize  
```  
  
```csharp  
[Serializable]  
[SqlUserDefinedType(Format.UserDefined,   
    IsByteOrdered = true, MaxByteSize = 32)]  
    [CLSCompliant(false)]  
    public struct Currency : INullable, IComparable, IBinarySerialize  
    {  
```  
  
## <a name="creating-read-and-write-methods-with-ibinaryserialize"></a><span data-ttu-id="8c6fd-256">Erstellen von Read- und Write-Methoden mit IBinarySerialize</span><span class="sxs-lookup"><span data-stu-id="8c6fd-256">Creating Read and Write Methods with IBinarySerialize</span></span>  
 <span data-ttu-id="8c6fd-257">Wenn Sie das Serialisierungsformat `UserDefined` wählen, müssen Sie auch die `IBinarySerialize`-Schnittstelle implementieren und eigene `Read`- und `Write`-Methoden schreiben.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-257">When you choose `UserDefined` serialization format, you also must implement the `IBinarySerialize` interface and create your own `Read` and `Write` methods.</span></span> <span data-ttu-id="8c6fd-258">In den folgenden Prozeduren aus dem UDT `Currency` werden `System.IO.BinaryReader` und `System.IO.BinaryWriter` zum Lesen bzw. zum Schreiben von UDT-Werten verwendet.</span><span class="sxs-lookup"><span data-stu-id="8c6fd-258">The following procedures from the `Currency` UDT use the `System.IO.BinaryReader` and `System.IO.BinaryWriter` to read from and write to the UDT.</span></span>  
  
```vb  
' IBinarySerialize methods  
' The binary layout is as follow:  
'    Bytes 0 - 19: Culture name, padded to the right with null  
'    characters, UTF-16 encoded  
'    Bytes 20+: Decimal value of money  
' If the culture name is empty, the currency is null.  
Public Sub Write(ByVal w As System.IO.BinaryWriter) _  
  Implements Microsoft.SqlServer.Server.IBinarySerialize.Write  
    If Me.IsNull Then  
        w.Write(nullMarker)  
        w.Write(System.Convert.ToDecimal(0))  
        Return  
    End If  
  
    If cultureName.Length > cultureNameMaxSize Then  
        Throw New ApplicationException(String.Format(CultureInfo.CurrentUICulture, _  
           "{0} is an invalid culture name for currency as it is too long.", cultureNameMaxSize))  
    End If  
  
    Dim paddedName As String = cultureName.PadRight(cultureNameMaxSize, CChar(vbNullChar))  
  
    For i As Integer = 0 To cultureNameMaxSize - 1  
        w.Write(paddedName(i))  
    Next i  
  
    ' Normalize decimal value to two places  
    currencyVal = Decimal.Floor(currencyVal * 100) / 100  
    w.Write(currencyVal)  
End Sub  
  
Public Sub Read(ByVal r As System.IO.BinaryReader) _  
  Implements Microsoft.SqlServer.Server.IBinarySerialize.Read  
    Dim name As Char() = r.ReadChars(cultureNameMaxSize)  
    Dim stringEnd As Integer = Array.IndexOf(name, CChar(vbNullChar))  
  
    If stringEnd = 0 Then  
        cultureName = Nothing  
        Return  
    End If  
  
    cultureName = New String(name, 0, stringEnd)  
    currencyVal = r.ReadDecimal()  
End Sub  
  
```  
  
```csharp  
// IBinarySerialize methods  
// The binary layout is as follow:  
//    Bytes 0 - 19:Culture name, padded to the right   
//    with null characters, UTF-16 encoded  
//    Bytes 20+:Decimal value of money  
// If the culture name is empty, the currency is null.  
public void Write(System.IO.BinaryWriter w)  
{  
    if (this.IsNull)  
    {  
        w.Write(nullMarker);  
        w.Write((decimal)0);  
        return;  
    }  
  
    if (cultureName.Length > cultureNameMaxSize)  
    {  
        throw new ApplicationException(string.Format(  
            CultureInfo.InvariantCulture,   
            "{0} is an invalid culture name for currency as it is too long.",   
            cultureNameMaxSize));  
    }  
  
    String paddedName = cultureName.PadRight(cultureNameMaxSize, '\0');  
    for (int i = 0; i < cultureNameMaxSize; i++)  
    {  
        w.Write(paddedName[i]);  
    }  
  
    // Normalize decimal value to two places  
    currencyValue = Decimal.Floor(currencyValue * 100) / 100;  
    w.Write(currencyValue);  
}  
public void Read(System.IO.BinaryReader r)  
{  
    char[] name = r.ReadChars(cultureNameMaxSize);  
    int stringEnd = Array.IndexOf(name, '\0');  
  
    if (stringEnd == 0)  
    {  
        cultureName = null;  
        return;  
    }  
  
    cultureName = new String(name, 0, stringEnd);  
    currencyValue = r.ReadDecimal();  
}  
```  
  
 <span data-ttu-id="8c6fd-259">Das komplette Codelisting für den `Currency` UDT finden Sie unter [SQL Server Datenbank-Engine Beispiele](https://msftengprodsamples.codeplex.com/).</span><span class="sxs-lookup"><span data-stu-id="8c6fd-259">For the complete code listing for the `Currency` UDT, see [SQL Server Database Engine Samples](https://msftengprodsamples.codeplex.com/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c6fd-260">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8c6fd-260">See Also</span></span>  
 [<span data-ttu-id="8c6fd-261">Erstellen eines benutzerdefinierten Typs</span><span class="sxs-lookup"><span data-stu-id="8c6fd-261">Creating a User-Defined Type</span></span>](creating-user-defined-types.md)  
  
