---
title: Erstellen von Variablen und Spalten des XML-Datentyps | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- xml data type [SQL Server], variables
- xml data type [SQL Server], columns
ms.assetid: 8994ab6e-5519-4ba2-97a1-fac8af6f72db
author: rothja
ms.author: jroth
ms.openlocfilehash: 08b79888eb47634deaccc910b2ea3c93800b7c78
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722610"
---
# <a name="create-xml-data-type-variables-and-columns"></a><span data-ttu-id="71973-102">Erstellen von Variablen und Spalten des XML-Datentyps</span><span class="sxs-lookup"><span data-stu-id="71973-102">Create XML Data Type Variables and Columns</span></span>
  <span data-ttu-id="71973-103">Der `xml` -Datentyp ist ein integrierter Datentyp in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] und ähnelt in gewisser Weise anderen integrierten Typen wie `int` und `varchar` .</span><span class="sxs-lookup"><span data-stu-id="71973-103">The `xml` data type is a built-in data type in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and is somewhat similar to other built-in types such as `int` and `varchar`.</span></span> <span data-ttu-id="71973-104">Wie andere integrierte Typen können Sie den- `xml` Datentyp als Spaltentyp verwenden, wenn Sie eine Tabelle als Variablentyp, als Parametertyp, als Funktions Rückgabetyp oder in [Cast und Convert](/sql/t-sql/functions/cast-and-convert-transact-sql)erstellen.</span><span class="sxs-lookup"><span data-stu-id="71973-104">As with other built-in types, you can use the `xml` data type as a column type when you create a table as a variable type, a parameter type, a function-return type, or in [CAST and CONVERT](/sql/t-sql/functions/cast-and-convert-transact-sql).</span></span>  
  
## <a name="creating-columns-and-variables"></a><span data-ttu-id="71973-105">Erstellen von Variablen und Spalten</span><span class="sxs-lookup"><span data-stu-id="71973-105">Creating Columns and Variables</span></span>  
 <span data-ttu-id="71973-106">Verwenden Sie zur Erstellung einer Spalte des `xml` -Typs als Teil einer Tabelle eine `CREATE TABLE` -Anweisung, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="71973-106">To create an `xml` type column as part of a table, use a `CREATE TABLE` statement, as shown in the following example:</span></span>  
  
```  
CREATE TABLE T1(Col1 int primary key, Col2 xml)   
```  
  
 <span data-ttu-id="71973-107">Sie können eine `DECLARE statement` verwenden, um eine Variable des `xml` -Typs zu erstellen, wie das folgende Beispiel zeigt.</span><span class="sxs-lookup"><span data-stu-id="71973-107">You can use a `DECLARE statement` to create a variable of `xml` type, as the following example shows.</span></span>  
  
```  
DECLARE @x xml   
```  
  
 <span data-ttu-id="71973-108">Erstellen Sie eine typisierte `xml` -Variable, indem Sie eine XML-Schemaauflistung angeben, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="71973-108">Create a typed `xml` variable by specifying an XML schema collection, as shown in the following example.</span></span>  
  
```  
DECLARE @x xml (Sales.StoreSurveySchemaCollection)  
```  
  
 <span data-ttu-id="71973-109">Verwenden Sie zum Übergeben eines Parameters des `xml` -Typs an eine gespeicherte Prozedur eine `CREATE PROCEDURE` -Anweisung, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="71973-109">To pass an `xml` type parameter to a stored procedure, use a `CREATE PROCEDURE` statement, as shown in the following example.</span></span>  
  
```  
CREATE PROCEDURE SampleProc(@XmlDoc xml) AS ...   
```  
  
 <span data-ttu-id="71973-110">Zum Abfragen von den in Spalten, Variablen oder Parametern gespeicherten XML-Instanzen können Sie XQuery verwenden.</span><span class="sxs-lookup"><span data-stu-id="71973-110">You can use XQuery to query XML instances stored in columns, parameters, or variables.</span></span> <span data-ttu-id="71973-111">Sie können auch die XML-Datenbearbeitungssprache (XML DML, Data Manipulation Language) verwenden, um Updates an den XML-Instanzen vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="71973-111">You can also use the XML Data Manipulation Language (XML DML) to apply updates to the XML instances.</span></span> <span data-ttu-id="71973-112">Da der XQuery-Standard zum Zeitpunkt der Entwicklung keine Definition der XQuery-DML enthielt, führt [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Erweiterungen der [XML Data Modification Language (XML DML)](/sql/t-sql/xml/xml-data-modification-language-xml-dml) für XQuery ein.</span><span class="sxs-lookup"><span data-stu-id="71973-112">Because the XQuery standard did not define XQuery DML at the time of development, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] introduces [XML Data Modification Language](/sql/t-sql/xml/xml-data-modification-language-xml-dml) extensions to XQuery.</span></span> <span data-ttu-id="71973-113">Diese Erweiterungen ermöglichen Einfügungs-, Update- und Löschvorgänge.</span><span class="sxs-lookup"><span data-stu-id="71973-113">These extensions allow you to perform insert, update, and delete operations.</span></span>  
  
## <a name="assigning-defaults"></a><span data-ttu-id="71973-114">Zuweisen von Standardeinstellungen</span><span class="sxs-lookup"><span data-stu-id="71973-114">Assigning Defaults</span></span>  
 <span data-ttu-id="71973-115">Sie können einer Spalte vom Typ `xml` in einer Tabelle eine standardmäßige XML-Instanz zuweisen.</span><span class="sxs-lookup"><span data-stu-id="71973-115">In a table, you can assign a default XML instance to a column of `xml` type.</span></span> <span data-ttu-id="71973-116">Sie können das Standard-XML auf zweierlei Weise bereitstellen: durch Verwenden einer XML-Konstante oder durch Verwenden einer expliziten Umwandlung in den `xml`-Typ.</span><span class="sxs-lookup"><span data-stu-id="71973-116">You can provide the default XML in one of two ways: by using an XML constant, or by using an explicit cast to the `xml` type.</span></span>  
  
 <span data-ttu-id="71973-117">Um das Standard-XML als XML-Konstante bereitzustellen, verwenden Sie die im folgenden Beispiel gezeigte Syntax.</span><span class="sxs-lookup"><span data-stu-id="71973-117">To provide the default XML as an XML constant, use syntax as shown in the following example.</span></span> <span data-ttu-id="71973-118">Beachten Sie, dass die Zeichenfolge implizit in den `xml`-Typ umgewandelt wird (durch CAST).</span><span class="sxs-lookup"><span data-stu-id="71973-118">Note that the string is implicitly CAST to `xml` type.</span></span>  
  
```  
CREATE TABLE T (XmlColumn xml default N'<element1/><element2/>')  
```  
  
 <span data-ttu-id="71973-119">Um das Standard-XML als explizites `CAST` in `xml`bereitzustellen, verwenden Sie die im folgenden Beispiel gezeigte Syntax.</span><span class="sxs-lookup"><span data-stu-id="71973-119">To provide the default XML as an explicit `CAST` to `xml`, use syntax as shown in the following example.</span></span>  
  
```  
CREATE TABLE T (XmlColumn xml   
                  default CAST(N'<element1/><element2/>' AS xml))  
```  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="71973-120">unterstützt auch NULL- und NOT NULL-Einschränkungen für Spalten vom Typ `xml`.</span><span class="sxs-lookup"><span data-stu-id="71973-120">also supports NULL and NOT NULL constraints on columns of `xml` type.</span></span> <span data-ttu-id="71973-121">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="71973-121">For example:</span></span>  
  
```  
CREATE TABLE T (XmlColumn xml NOT NULL)  
```  
  
## <a name="specifying-constraints"></a><span data-ttu-id="71973-122">Angeben von Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="71973-122">Specifying Constraints</span></span>  
 <span data-ttu-id="71973-123">Beim Erstellen von Spalten vom Typ `xml` können Sie auf Spalten- oder Tabellenebene Einschränkungen definieren.</span><span class="sxs-lookup"><span data-stu-id="71973-123">When you create columns of `xml` type, you can define column-level or table-level constraints.</span></span> <span data-ttu-id="71973-124">Verwenden Sie Einschränkungen in den folgenden Situationen:</span><span class="sxs-lookup"><span data-stu-id="71973-124">Use constraints in the following situations:</span></span>  
  
-   <span data-ttu-id="71973-125">Ihre Geschäftsrichtlinien können nicht in XML-Schemas ausgedrückt werden.</span><span class="sxs-lookup"><span data-stu-id="71973-125">Your business rules cannot be expressed in XML schemas.</span></span> <span data-ttu-id="71973-126">Beispielsweise muss sich die Lieferadresse eines Blumenladens in einem Umkreis von 50 Kilometern zum Ladenstandort befinden.</span><span class="sxs-lookup"><span data-stu-id="71973-126">For example, the delivery address of a flower shop must be within 50 miles of its business location.</span></span> <span data-ttu-id="71973-127">Dies kann in Form einer Einschränkung für die XML-Spalte formuliert werden.</span><span class="sxs-lookup"><span data-stu-id="71973-127">This can be written as a constraint on the XML column.</span></span> <span data-ttu-id="71973-128">Die Einschränkung kann `xml`-Datentypmethoden einbeziehen.</span><span class="sxs-lookup"><span data-stu-id="71973-128">The constraint may involve `xml` data type methods.</span></span>  
  
-   <span data-ttu-id="71973-129">Ihre Einschränkung bezieht andere XML- oder Nicht-XML-Spalten in der Tabelle ein.</span><span class="sxs-lookup"><span data-stu-id="71973-129">Your constraint involves other XML or non-XML columns in the table.</span></span> <span data-ttu-id="71973-130">Beispielsweise, wenn die Übereinstimmung der ID eines in einer XML-Instanz gefundenen Kunden (`/Customer/@CustId`) mit dem Wert in einer relationalen CustomerID-Spalte erzwungen werden soll.</span><span class="sxs-lookup"><span data-stu-id="71973-130">An example is the enforcement of the ID of a Customer (`/Customer/@CustId`) found in an XML instance to match the value in a relational CustomerID column.</span></span>  
  
 <span data-ttu-id="71973-131">Sie können Einschränkungen für typisierte oder nicht typisierte Spalten des `xml`-Datentyps eingegeben.</span><span class="sxs-lookup"><span data-stu-id="71973-131">You can specify constraints for typed or untyped `xml` data type columns.</span></span> <span data-ttu-id="71973-132">Die [XML-Datentypmethoden](/sql/t-sql/xml/xml-data-type-methods) können jedoch beim Angeben von Einschränkungen nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="71973-132">However, you cannot use the [XML data type methods](/sql/t-sql/xml/xml-data-type-methods) when you specify constraints.</span></span> <span data-ttu-id="71973-133">Beachten Sie zudem, dass der `xml`-Datentyp die folgenden Spalten- und Tabelleneinschränkungen nicht unterstützt:</span><span class="sxs-lookup"><span data-stu-id="71973-133">Also, note that the `xml` data type does not support the following column and table constraints:</span></span>  
  
-   <span data-ttu-id="71973-134">PRIMARY KEY/ FOREIGN KEY</span><span class="sxs-lookup"><span data-stu-id="71973-134">PRIMARY KEY/ FOREIGN KEY</span></span>  
  
-   <span data-ttu-id="71973-135">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="71973-135">UNIQUE</span></span>  
  
-   <span data-ttu-id="71973-136">COLLATE</span><span class="sxs-lookup"><span data-stu-id="71973-136">COLLATE</span></span>  
  
     <span data-ttu-id="71973-137">XML stellt eine eigene Codierung bereit.</span><span class="sxs-lookup"><span data-stu-id="71973-137">XML provides its own encoding.</span></span> <span data-ttu-id="71973-138">Sortierungen gelten nur für Zeichenfolgentypen.</span><span class="sxs-lookup"><span data-stu-id="71973-138">Collations apply to string types only.</span></span> <span data-ttu-id="71973-139">Der `xml`-Datentyp stellt keinen Zeichenfolgentyp dar.</span><span class="sxs-lookup"><span data-stu-id="71973-139">The `xml` data type is not a string type.</span></span> <span data-ttu-id="71973-140">Er besitzt jedoch die Zeichenfolgendarstellung und ermöglicht das Umwandeln in und aus Zeichenfolgen-Datentypen.</span><span class="sxs-lookup"><span data-stu-id="71973-140">However, it does have string representation and allows casting to and from string data types.</span></span>  
  
-   <span data-ttu-id="71973-141">RULE</span><span class="sxs-lookup"><span data-stu-id="71973-141">RULE</span></span>  
  
 <span data-ttu-id="71973-142">Eine Alternative zur Verwendung von Einschränkungen ist die Erstellung eines Wrappers, einer benutzerdefinierten Funktion, um die Methode des `xml`-Datentyps einzubinden und die benutzerdefinierte Funktion in der CHECK-Einschränkung anzugeben, wie im folgenden Beispiel zu sehen ist.</span><span class="sxs-lookup"><span data-stu-id="71973-142">An alternative to using constraints is to create a wrapper, user-defined function to wrap the `xml` data type method and specify user-defined function in the check constraint as shown in the following example.</span></span>  
  
 <span data-ttu-id="71973-143">Im folgenden Beispiel gibt die Einschränkung für `Col2` an, dass jede der in dieser Spalte gespeicherten XML-Instanzen ein `<ProductDescription>` -Element aufweisen muss, das ein `ProductID` -Attribut enthält.</span><span class="sxs-lookup"><span data-stu-id="71973-143">In the following example, the constraint on `Col2` specifies that each XML instance stored in this column must have a `<ProductDescription>` element that contains a `ProductID` attribute.</span></span> <span data-ttu-id="71973-144">Diese Einschränkung wird durch folgende benutzerdefinierte Funktion erzwungen:</span><span class="sxs-lookup"><span data-stu-id="71973-144">This constraint is enforced by this user-defined function:</span></span>  
  
```  
CREATE FUNCTION my_udf(@var xml) returns bit  
AS BEGIN   
RETURN @var.exist('/ProductDescription/@ProductID')  
END  
GO  
```  
  
 <span data-ttu-id="71973-145">Beachten Sie, dass die `exist()` -Methode des `xml` -Datentyps `1` zurückgibt, wenn das `<ProductDescription>` -Element der Instanz das `ProductID` -Attribut enthält.</span><span class="sxs-lookup"><span data-stu-id="71973-145">Note that the `exist()` method of the `xml` data type returns `1` if the `<ProductDescription>` element in the instance contains the `ProductID` attribute.</span></span> <span data-ttu-id="71973-146">Andernfalls wird `0`zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="71973-146">Otherwise, it returns `0`.</span></span>  
  
 <span data-ttu-id="71973-147">Jetzt können Sie eine Tabelle mit einer Einschränkung auf Spaltenebene erstellen, wie im Folgenden gezeigt:</span><span class="sxs-lookup"><span data-stu-id="71973-147">Now, you can create a table with a column-level constraint as follows:</span></span>  
  
```  
CREATE TABLE T (  
    Col1 int primary key,   
    Col2 xml check(dbo.my_udf(Col2)=1))  
GO  
```  
  
 <span data-ttu-id="71973-148">Die folgende Einfügung wird erfolgreich ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="71973-148">The following insert succeeds:</span></span>  
  
```  
INSERT INTO T values(1,'<ProductDescription ProductID="1" />')  
```  
  
 <span data-ttu-id="71973-149">Aufgrund der Einschränkung erzeugt die folgende Einfügung einen Fehler:</span><span class="sxs-lookup"><span data-stu-id="71973-149">Because of the constraint, the following insert fails:</span></span>  
  
```  
INSERT INTO T values(1,'<Product />')  
```  
  
## <a name="same-or-different-table"></a><span data-ttu-id="71973-150">Gleiche oder unterschiedliche Tabelle</span><span class="sxs-lookup"><span data-stu-id="71973-150">Same or Different Table</span></span>  
 <span data-ttu-id="71973-151">Eine- `xml` Datentyp Spalte kann in einer Tabelle erstellt werden, die andere relationale Spalten enthält, oder in einer separaten Tabelle mit einer Fremdschlüssel Beziehung zu einer Haupttabelle.</span><span class="sxs-lookup"><span data-stu-id="71973-151">An `xml` data type column can be created in a table that contains other relational columns, or in a separate table with a foreign key relationship to a main table.</span></span>  
  
 <span data-ttu-id="71973-152">Erstellen Sie eine- `xml` Datentyp Spalte in derselben Tabelle, wenn eine der folgenden Bedingungen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="71973-152">Create an `xml` data type column in the same table when one of the following conditions is true:</span></span>  
  
-   <span data-ttu-id="71973-153">Ihre Anwendung führt einen Datenabruf für die XML-Spalte durch und benötigt keinen XML-Index für die XML-Spalte.</span><span class="sxs-lookup"><span data-stu-id="71973-153">Your application performs data retrieval on the XML column and does not require an XML index on the XML column.</span></span>  
  
-   <span data-ttu-id="71973-154">Sie möchten einen XML-Index für die `xml`-Datentypspalte erstellen, und der Primärschlüssel der Haupttabelle ist derselbe wie ihr Gruppierungsschlüssel.</span><span class="sxs-lookup"><span data-stu-id="71973-154">You want to build an XML index on the `xml` data type column and the primary key of the main table is the same as its clustering key.</span></span> <span data-ttu-id="71973-155">Weitere Informationen finden Sie unter [XML-Indizes &#40;SQL Server&#41;](xml-indexes-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="71973-155">For more information, see [XML Indexes &#40;SQL Server&#41;](xml-indexes-sql-server.md).</span></span>  
  
 <span data-ttu-id="71973-156">Erstellen Sie die `xml`-Datentypspalte in einer getrennten Tabelle, wenn die folgenden Bedingungen zutreffen:</span><span class="sxs-lookup"><span data-stu-id="71973-156">Create the `xml` data type column in a separate table if the following conditions are true:</span></span>  
  
-   <span data-ttu-id="71973-157">Sie möchten einen XML-Index für die `xml`-Datentypspalte erstellen, der Primärschlüssel der Haupttabelle unterscheidet sich jedoch von ihrem Gruppierungsschlüssel, oder die Haupttabelle besitzt keinen Primärschlüssel, oder die Haupttabelle ist ein Heap (kein Gruppierungsschlüssel).</span><span class="sxs-lookup"><span data-stu-id="71973-157">You want to build an XML index on the `xml` data type column, but the primary key of the main table is different from its clustering key, or the main table does not have a primary key, or the main table is a heap (no clustering key).</span></span> <span data-ttu-id="71973-158">Das kann der Fall sein, wenn die Haupttabelle bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="71973-158">This may be true if the main table already exists.</span></span>  
  
-   <span data-ttu-id="71973-159">Sie wollen vermeiden, dass Tabellenscans verlangsamt werden, weil die XML-Spalte in der Tabelle vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="71973-159">You do not want table scans to slow down because of the presence of the XML column in the table.</span></span> <span data-ttu-id="71973-160">Dies beansprucht Speicherplatz, unabhängig davon, ob die Speicherung innerhalb oder außerhalb der Zeile erfolgt.</span><span class="sxs-lookup"><span data-stu-id="71973-160">This uses space whether it is stored in-row or out-of-row.</span></span>  
  
  
