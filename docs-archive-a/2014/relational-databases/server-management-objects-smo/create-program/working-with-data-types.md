---
title: Arbeiten mit Datentypen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- DataType object
- SQL Server Management Objects, data types
- data types [SMO]
- SMO [SQL Server], data types
ms.assetid: 1e0e736a-c709-4d89-aeb2-b32dcfd641fa
author: stevestein
ms.author: sstein
ms.openlocfilehash: cbffc1c59eb12fa0f448a7fcb26157d5e18dba3f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609758"
---
# <a name="working-with-data-types"></a><span data-ttu-id="7bf05-102">Arbeiten mit Datentypen</span><span class="sxs-lookup"><span data-stu-id="7bf05-102">Working with Data Types</span></span>
  <span data-ttu-id="7bf05-103">Daten sind in vielen Typen und Größen verfügbar, beispielsweise als Zeichenfolge mit einer definierten Länge, als Zahl mit einer bestimmten Genauigkeit oder als benutzerdefinierter Datentyp, bei dem es sich um ein anderes Objekt mit einem eigenen Satz an Regeln handelt.</span><span class="sxs-lookup"><span data-stu-id="7bf05-103">Data comes in many types and sizes, such as a string that has a defined length, a number that has specific accuracy, or a user-defined data type that is another object that has its own set of rules.</span></span> <span data-ttu-id="7bf05-104">Das- <xref:Microsoft.SqlServer.Management.Smo.DataType> Objekt klassifiziert den Typ der Daten, sodass er von ordnungsgemäß verarbeitet werden kann [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bf05-104">The <xref:Microsoft.SqlServer.Management.Smo.DataType> object classifies the type of data so that it can be handled correctly by [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7bf05-105">Das <xref:Microsoft.SqlServer.Management.Smo.DataType>-Objekt ist Objekten zugeordnet, die Daten akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="7bf05-105">The <xref:Microsoft.SqlServer.Management.Smo.DataType> object is associated with objects that accept data.</span></span> <span data-ttu-id="7bf05-106">Die folgenden [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects (SMO)-Objekte akzeptieren Daten, die durch eine <xref:Microsoft.SqlServer.Management.Smo.DataType>-Objekteigenschaft definiert sein müssen:</span><span class="sxs-lookup"><span data-stu-id="7bf05-106">The following [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects (SMO) objects accept data that must be defined by a <xref:Microsoft.SqlServer.Management.Smo.DataType> object property:</span></span>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.Column>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunctionParameter>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.StoredProcedureParameter>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunctionParameter>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.UserDefinedAggregateParameter>  
  
 <span data-ttu-id="7bf05-107">Die `DataType`-Eigenschaft für Objekte, die Daten akzeptieren, kann auf unterschiedliche Weise festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="7bf05-107">The `DataType` property for objects that accept data can be set in several ways.</span></span>  
  
-   <span data-ttu-id="7bf05-108">Verwenden Sie den Standardkonstruktor und geben Sie die <xref:Microsoft.SqlServer.Management.Smo.DataType>-Objekteigenschaften explizit an.</span><span class="sxs-lookup"><span data-stu-id="7bf05-108">Use the default constructor and specify <xref:Microsoft.SqlServer.Management.Smo.DataType> object properties explicitly</span></span>  
  
-   <span data-ttu-id="7bf05-109">Verwenden Sie einen überladenen Konstruktor, und geben Sie die <xref:Microsoft.SqlServer.Management.Smo.DataType>-Eigenschaften als Parameter an.</span><span class="sxs-lookup"><span data-stu-id="7bf05-109">Use an overloaded constructor and specify the <xref:Microsoft.SqlServer.Management.Smo.DataType> properties as parameters.</span></span>  
  
-   <span data-ttu-id="7bf05-110">Geben Sie <xref:Microsoft.SqlServer.Management.Smo.DataType> inline im Objektkonstruktor an.</span><span class="sxs-lookup"><span data-stu-id="7bf05-110">Specify the <xref:Microsoft.SqlServer.Management.Smo.DataType> inline in the object constructor.</span></span>  
  
-   <span data-ttu-id="7bf05-111">Verwenden Sie eines der statischen Elemente der <xref:Microsoft.SqlServer.Management.Smo.DataType>-Klasse, zum Beispiel `Int`.</span><span class="sxs-lookup"><span data-stu-id="7bf05-111">Use one of the static members of the <xref:Microsoft.SqlServer.Management.Smo.DataType> class, for example `Int`.</span></span> <span data-ttu-id="7bf05-112">In diesem Fall wird eine Instanz eines <xref:Microsoft.SqlServer.Management.Smo.DataType>-Objekts zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7bf05-112">This will in fact return an instance of a <xref:Microsoft.SqlServer.Management.Smo.DataType> object.</span></span>  
  
 <span data-ttu-id="7bf05-113">Das <xref:Microsoft.SqlServer.Management.Smo.DataType>-Objekt verfügt über einige Eigenschaften, die den Datentyp definieren.</span><span class="sxs-lookup"><span data-stu-id="7bf05-113">The <xref:Microsoft.SqlServer.Management.Smo.DataType> object has several properties that define the type of data.</span></span> <span data-ttu-id="7bf05-114">Beispielsweise gibt die <xref:Microsoft.SqlServer.Management.Smo.SqlDataType>-Eigenschaft den [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Datentyp an.</span><span class="sxs-lookup"><span data-stu-id="7bf05-114">For example, the <xref:Microsoft.SqlServer.Management.Smo.SqlDataType> property specifies the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data type.</span></span> <span data-ttu-id="7bf05-115">Die konstanten Werte, die [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Datentypen darstellen, werden in der <xref:Microsoft.SqlServer.Management.Smo.SqlDataType>-Enumeration aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="7bf05-115">The constant values that represent [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data types are listed in the <xref:Microsoft.SqlServer.Management.Smo.SqlDataType> enumeration.</span></span> <span data-ttu-id="7bf05-116">Dies gilt für Datentypen wie `varchar`, `nchar`, `currency`, `integer`, `float` und `datetime`.</span><span class="sxs-lookup"><span data-stu-id="7bf05-116">This refers to data types such as `varchar`, `nchar`, `currency`, `integer`, `float`, and `datetime`.</span></span>  
  
 <span data-ttu-id="7bf05-117">Nachdem der Datentyp definiert wurde, müssen bestimmte Eigenschaften für die Daten festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="7bf05-117">When the data type is established, specific properties must be set for the data.</span></span> <span data-ttu-id="7bf05-118">Beispielsweise muss bei einem `nchar`-Typ die Länge der Zeichenfolgenddaten mit der `Length`-Eigenschaft angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7bf05-118">For example, if it is an `nchar` type, the length of the string data must be set in the `Length` property.</span></span> <span data-ttu-id="7bf05-119">Das Gleiche gilt für numerische Werte, für die Genauigkeit und Dezimalstellenanzahl angegeben werden muss.</span><span class="sxs-lookup"><span data-stu-id="7bf05-119">The same applies for numeric values, where you would have to specify precision and scale.</span></span>  
  
 <span data-ttu-id="7bf05-120">Der <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType>-Datentyp und der <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>-Datentyp beziehen sich auf Objekte, die die Definition des vom Benutzer definierten Datentyps enthalten.</span><span class="sxs-lookup"><span data-stu-id="7bf05-120"><xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> and <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType> data types refer to objects that contain the definition of the type of data defined by the user.</span></span> <span data-ttu-id="7bf05-121"><xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> basiert auf den [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Datentypen aus der <xref:Microsoft.SqlServer.Management.Smo.SqlDataType>-Enumeration.</span><span class="sxs-lookup"><span data-stu-id="7bf05-121">The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> is based on [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data types from the <xref:Microsoft.SqlServer.Management.Smo.SqlDataType> enumeration.</span></span> <span data-ttu-id="7bf05-122"><xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>Basiert auf .net- [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Datentypen.</span><span class="sxs-lookup"><span data-stu-id="7bf05-122">The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType> is based on [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET data types.</span></span> <span data-ttu-id="7bf05-123">In der Regel würden diese Daten eines bestimmten Typs darstellen, der wegen der von der Organisation definierten Geschäftsregeln in der Datenbank häufig verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7bf05-123">Typically, these would represent data of a specific type that is frequently reused by the database because of business rules defined by the organization.</span></span> <span data-ttu-id="7bf05-124">Beispielsweise wäre ein Datentyp, mit dem ein Währungsbetrag und ein Währungsbezeichner gespeichert wird, für eine Firma hilfreich, die mit mehreren Währungen arbeitet.</span><span class="sxs-lookup"><span data-stu-id="7bf05-124">For example, a data type that stores an amount of money and a currency denominator would be helpful in a company that deals in multiple currencies.</span></span>  
  
 <span data-ttu-id="7bf05-125">Die <xref:Microsoft.SqlServer.Management.Smo.SqlDataType>-Enumeration enthält eine Liste aller von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]- unterstützten Datentypen.</span><span class="sxs-lookup"><span data-stu-id="7bf05-125">The <xref:Microsoft.SqlServer.Management.Smo.SqlDataType> enumeration contains a list of all the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-supported data types.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="7bf05-126">Beispiele</span><span class="sxs-lookup"><span data-stu-id="7bf05-126">Examples</span></span>  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="constructing-a-datatype-object-with-the-specification-in-the-constructor-in-visual-basic"></a><span data-ttu-id="7bf05-127">Konstruktion eines DataType-Objekts mit der Spezifikation im Konstruktor in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7bf05-127">Constructing a DataType Object with the Specification in the Constructor in Visual Basic</span></span>  
 <span data-ttu-id="7bf05-128">Im folgenden Codebeispiel wird gezeigt, wie mit dem Konstruktor Instanzen von Datentypen erstellt werden, die auf verschiedenen [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Datentypen basieren.</span><span class="sxs-lookup"><span data-stu-id="7bf05-128">This code example shows how to use the constructor to create instances of data types that are based on different [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7bf05-129"><xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> und die XML-Typen erfordern einen Namenswert zur Identifizierung des Objekts.</span><span class="sxs-lookup"><span data-stu-id="7bf05-129">The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType>, and XML types all require a name value to identify the object.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBDataTypes1](SMO How to#SMO_VBDataTypes1)]  -->  
  
## <a name="constructing-a-datatype-object-with-the-specification-in-the-constructor-in-visual-c"></a><span data-ttu-id="7bf05-130">Konstruktion eines DataType-Objekts mit der Spezifikation im Konstruktor in Visual C#</span><span class="sxs-lookup"><span data-stu-id="7bf05-130">Constructing a DataType Object with the Specification in the Constructor in Visual C#</span></span>  
 <span data-ttu-id="7bf05-131">Im folgenden Codebeispiel wird gezeigt, wie mit dem Konstruktor Instanzen von Datentypen erstellt werden, die auf verschiedenen [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Datentypen basieren.</span><span class="sxs-lookup"><span data-stu-id="7bf05-131">This code example shows how to use the constructor to create instances of data types that are based on different [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7bf05-132"><xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> und die XML-Typen erfordern einen Namenswert zur Identifizierung des Objekts.</span><span class="sxs-lookup"><span data-stu-id="7bf05-132">The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType>, and XML types all require a name value to identify the object.</span></span>  
  
```  
{   
//Declare a DataType object variable and define the data type in the constructor.   
DataType dt;   
//For the decimal data type the following two arguments specify precision, and scale.   
dt = new DataType(SqlDataType.Decimal, 10, 2);   
}  
```  
  
## <a name="constructing-a-datatype-object-by-using-the-default-constructor-in-visual-basic"></a><span data-ttu-id="7bf05-133">Konstruktion eines DataType-Objekts mithilfe des Standardkonstruktors in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7bf05-133">Constructing a DataType Object by Using the Default Constructor in Visual Basic</span></span>  
 <span data-ttu-id="7bf05-134">Im folgenden Codebeispiel wird gezeigt, wie mit dem Standardkonstruktor Instanzen von Datentypen erstellt werden, die auf verschiedenen [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Datentypen basieren.</span><span class="sxs-lookup"><span data-stu-id="7bf05-134">This code example shows how to use the default constructor to create instances of data types that are based on different [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data types.</span></span> <span data-ttu-id="7bf05-135">Mithilfe der Eigenschaften wird der Datentyp dann angegeben.</span><span class="sxs-lookup"><span data-stu-id="7bf05-135">The properties are then used to specify the data type.</span></span>  
  
 <span data-ttu-id="7bf05-136">**Hinweis** Die <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType> <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> XML-Typen, und erfordern einen namens Wert zur Identifizierung des Objekts.</span><span class="sxs-lookup"><span data-stu-id="7bf05-136">**Note** The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType>, and XML types all require a name value to identify the object.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBDataTypes2](SMO How to#SMO_VBDataTypes2)]  -->  
  
## <a name="constructing-a-datatype-object-by-using-the-default-constructor-in-visual-c"></a><span data-ttu-id="7bf05-137">Konstruktion eines DataType-Objekts mithilfe des Standardkonstruktors in Visual C#</span><span class="sxs-lookup"><span data-stu-id="7bf05-137">Constructing a DataType Object by Using the Default Constructor in Visual C#</span></span>  
 <span data-ttu-id="7bf05-138">Im folgenden Codebeispiel wird gezeigt, wie mit dem Standardkonstruktor Instanzen von Datentypen erstellt werden, die auf verschiedenen [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Datentypen basieren.</span><span class="sxs-lookup"><span data-stu-id="7bf05-138">This code example shows how to use the default constructor to create instances of data types that are based on different [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data types.</span></span> <span data-ttu-id="7bf05-139">Mithilfe der Eigenschaften wird der Datentyp dann angegeben.</span><span class="sxs-lookup"><span data-stu-id="7bf05-139">The properties are then used to specify the data type.</span></span>  
  
 <span data-ttu-id="7bf05-140">**Hinweis** Die <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType> <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> XML-Typen, und erfordern einen namens Wert zur Identifizierung des Objekts.</span><span class="sxs-lookup"><span data-stu-id="7bf05-140">**Note** The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType>, and XML types all require a name value to identify the object.</span></span>  
  
```  
{   
//Declare and create a DataType object variable.   
DataType dt;   
dt = new DataType();   
//Define the data type by setting the SqlDataType property.   
dt.SqlDataType = SqlDataType.VarChar;   
//The VarChar data type requires a value for the MaximumLength property.   
dt.MaximumLength = 100;   
}  
```  
  
  
