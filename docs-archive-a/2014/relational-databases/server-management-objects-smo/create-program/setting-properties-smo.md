---
title: Festlegen von Eigenschaften | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SMO [SQL Server], properties
- SQL Server Management Objects, properties
- properties [SMO]
ms.assetid: 342569ba-d2f7-44d2-8f3f-ae9c701c7f0f
author: stevestein
ms.author: sstein
ms.openlocfilehash: de381f8e4e9dfe9f6590638742e988f866ccabdc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719801"
---
# <a name="setting-properties"></a><span data-ttu-id="39aff-102">Festlegen von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="39aff-102">Setting Properties</span></span>
  <span data-ttu-id="39aff-103">Eigenschaften sind Werte, die aussagekräftige Informationen über das Objekt speichern.</span><span class="sxs-lookup"><span data-stu-id="39aff-103">Properties are values that store descriptive information about the object.</span></span> <span data-ttu-id="39aff-104">Beispielsweise [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] werden Konfigurationsoptionen durch die Eigenschaften des <xref:Microsoft.SqlServer.Management.Smo.Server.Configuration%2A> -Objekts dargestellt.</span><span class="sxs-lookup"><span data-stu-id="39aff-104">For example, [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] configuration options are represented by the <xref:Microsoft.SqlServer.Management.Smo.Server.Configuration%2A> object's properties.</span></span> <span data-ttu-id="39aff-105">Auf Eigenschaften kann mit der Eigenschaftsauflistung entweder direkt oder indirekt zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="39aff-105">Properties can be accessed either directly or indirectly by using the property collection.</span></span> <span data-ttu-id="39aff-106">Für den direkten Zugriff auf Eigenschaften wird die folgende Syntax verwendet:</span><span class="sxs-lookup"><span data-stu-id="39aff-106">Accessing properties directly uses the following syntax:</span></span>  
  
 `objInstance.PropertyName`  
  
 <span data-ttu-id="39aff-107">Ein Eigenschaftswert kann geändert oder abgerufen werden. Dies hängt davon ab, ob die Eigenschaft Lese-/Schreibzugriff hat oder schreibgeschützt ist.</span><span class="sxs-lookup"><span data-stu-id="39aff-107">A property value can be modified or retrieved depending on whether the property has read/write access or read-only access.</span></span> <span data-ttu-id="39aff-108">Bevor ein Objekt erstellt wird, müssen bestimmte Eigenschaften festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="39aff-108">It is also necessary to set certain properties before an object can be created.</span></span> <span data-ttu-id="39aff-109">Weitere Informationen finden Sie in der SMO-Referenz für das entsprechende Objekt.</span><span class="sxs-lookup"><span data-stu-id="39aff-109">For more information, see the SMO reference for the particular object.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="39aff-110">Auflistungen von untergeordneten Objekten werden als Eigenschaft eines Objekts angezeigt.</span><span class="sxs-lookup"><span data-stu-id="39aff-110">Collections of child objects appear as the property of an object.</span></span> <span data-ttu-id="39aff-111">Die `Tables`-Auflistung ist beispielsweise eine Eigenschaft eines `Server`-Objekts.</span><span class="sxs-lookup"><span data-stu-id="39aff-111">For example, the `Tables` collection is a property of a `Server` object.</span></span> <span data-ttu-id="39aff-112">Weitere Informationen finden Sie unter [Using Collections](using-collections.md).</span><span class="sxs-lookup"><span data-stu-id="39aff-112">For more information, see [Using Collections](using-collections.md).</span></span>  
  
 <span data-ttu-id="39aff-113">Die Eigenschaften eines Objekts sind Mitglieder einer Eigenschaftsauflistung.</span><span class="sxs-lookup"><span data-stu-id="39aff-113">The properties of an object are members of the Properties collection.</span></span> <span data-ttu-id="39aff-114">Mithilfe der Eigenschaftsauflistung kann jede Eigenschaft eines Objekts durchlaufen werden.</span><span class="sxs-lookup"><span data-stu-id="39aff-114">The Properties collection can be used to iterate through every property of an object.</span></span>  
  
 <span data-ttu-id="39aff-115">Mitunter ist eine Eigenschaft aus den folgenden Gründen nicht verfügbar:</span><span class="sxs-lookup"><span data-stu-id="39aff-115">Sometimes a property is not available for the following reasons:</span></span>  
  
-   <span data-ttu-id="39aff-116">Die Serverversion unterstützt die Eigenschaft nicht, z. B. wenn Sie versuchen auf eine Eigenschaft, die eine neue [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Funktion darstellt, in einer älteren Version von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="39aff-116">The server version does not support the property, such as if you try to access a property that represents a new [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] feature on an older version of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="39aff-117">Der Server stellt keine Daten für die Eigenschaft zur Verfügung, z. B. wenn Sie versuchen auf eine Eigenschaft zuzugreifen, die eine [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Komponente darstellt, die nicht installiert ist.</span><span class="sxs-lookup"><span data-stu-id="39aff-117">The server does not provide data for the property, such as if you try to access a property that represents a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] component that is not installed.</span></span>  
  
 <span data-ttu-id="39aff-118">Sie können diese Situationen bewältigen, indem Sie die <xref:Microsoft.SqlServer.Management.Smo.UnknownPropertyException>- und die <xref:Microsoft.SqlServer.Management.Smo.PropertyCannotBeRetrievedException> SMO-Ausnahmen abfangen.</span><span class="sxs-lookup"><span data-stu-id="39aff-118">You can handle these circumstances by catching the <xref:Microsoft.SqlServer.Management.Smo.UnknownPropertyException> and the <xref:Microsoft.SqlServer.Management.Smo.PropertyCannotBeRetrievedException> SMO exceptions.</span></span>  
  
## <a name="setting-default-initialization-fields"></a><span data-ttu-id="39aff-119">Festlegen von Standardinitialisierungsfeldern</span><span class="sxs-lookup"><span data-stu-id="39aff-119">Setting Default Initialization Fields</span></span>  
 <span data-ttu-id="39aff-120">Beim Abrufen von Objekten führt SMO eine Optimierung aus.</span><span class="sxs-lookup"><span data-stu-id="39aff-120">SMO performs an optimization when retrieving objects.</span></span> <span data-ttu-id="39aff-121">Die Optimierung minimiert die Anzahl von Eigenschaften, die durch automatisches Skalieren zwischen den folgenden Status geladen werden:</span><span class="sxs-lookup"><span data-stu-id="39aff-121">The optimization minimizes the number of properties loaded by automatically scaling between the following states:</span></span>  
  
1.  <span data-ttu-id="39aff-122">Teilweise geladen.</span><span class="sxs-lookup"><span data-stu-id="39aff-122">Partially loaded.</span></span> <span data-ttu-id="39aff-123">Wenn auf ein Objekt erstmalig verwiesen wird, steht ein Minimum an Eigenschaften zur Verfügung (z. B. Name und Schema).</span><span class="sxs-lookup"><span data-stu-id="39aff-123">When an object is first referenced it has a minimum of properties available (such as Name and Schema).</span></span>  
  
2.  <span data-ttu-id="39aff-124">Vollständig geladen.</span><span class="sxs-lookup"><span data-stu-id="39aff-124">Fully loaded.</span></span> <span data-ttu-id="39aff-125">Wenn auf eine Eigenschaft verwiesen wird, werden die übrigen Eigenschaften, die schnell geladen werden können, initialisiert und zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="39aff-125">When any property is referenced, the remaining properties that are quick to load, are initialized and are made available.</span></span>  
  
3.  <span data-ttu-id="39aff-126">Eigenschaften, die viel Arbeitsspeicher in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="39aff-126">Properties that use lots of memory.</span></span> <span data-ttu-id="39aff-127">Die übrigen nicht verfügbaren Eigenschaften nehmen viel Arbeitsspeicher in Anspruch und haben den <xref:Microsoft.SqlServer.Management.Smo.Property.Expensive%2A>-Eigenschaftswert TRUE (z. B. <xref:Microsoft.SqlServer.Management.Smo.Database.DataSpaceUsage%2A>).</span><span class="sxs-lookup"><span data-stu-id="39aff-127">The remaining unavailable properties use lots of memory and have an <xref:Microsoft.SqlServer.Management.Smo.Property.Expensive%2A> property value of true (such as <xref:Microsoft.SqlServer.Management.Smo.Database.DataSpaceUsage%2A>).</span></span> <span data-ttu-id="39aff-128">Diese Eigenschaften werden nur geladen, wenn auf sie ausdrücklich verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="39aff-128">These properties are loaded only when specifically referenced.</span></span>  
  
 <span data-ttu-id="39aff-129">Wenn Ihre Anwendung zusätzliche Eigenschaften zu den im teilweise geladenen Status verfügbaren Eigenschaften abruft, übermittelt sie eine Abfrage zum Abrufen dieser zusätzlichen Eigenschaften und wechselt in den vollständig geladenen Status.</span><span class="sxs-lookup"><span data-stu-id="39aff-129">If your application does fetch extra properties, besides the ones provided in the partially loaded state, it submits a query to retrieve these extra properties and scales up to the fully loaded state.</span></span> <span data-ttu-id="39aff-130">Dies kann unnötigen Datenverkehr zwischen dem Client und dem Server verursachen.</span><span class="sxs-lookup"><span data-stu-id="39aff-130">This can cause unnecessary traffic between the client and server.</span></span> <span data-ttu-id="39aff-131">Eine weitere Optimierung kann durch Aufrufen der <xref:Microsoft.SqlServer.Management.Smo.Server.SetDefaultInitFields%2A>-Methode erzielt werden.</span><span class="sxs-lookup"><span data-stu-id="39aff-131">More optimization can be achieved by calling the <xref:Microsoft.SqlServer.Management.Smo.Server.SetDefaultInitFields%2A> method.</span></span> <span data-ttu-id="39aff-132">Die <xref:Microsoft.SqlServer.Management.Smo.Server.SetDefaultInitFields%2A>-Methode ermöglicht die Angabe der Eigenschaften, die beim Initialisieren des Objekts geladen werden.</span><span class="sxs-lookup"><span data-stu-id="39aff-132">The <xref:Microsoft.SqlServer.Management.Smo.Server.SetDefaultInitFields%2A> method allows specification of the properties that are loaded when the object is initialized.</span></span>  
  
 <span data-ttu-id="39aff-133">Die <xref:Microsoft.SqlServer.Management.Smo.Server.SetDefaultInitFields%2A>-Methode legt das Verhalten zum Laden von Eigenschaften für die restliche Anwendung oder bis zum Zurücksetzen der Anwendung fest.</span><span class="sxs-lookup"><span data-stu-id="39aff-133">The <xref:Microsoft.SqlServer.Management.Smo.Server.SetDefaultInitFields%2A> method sets the property loading behavior for the rest of application or until it is reset.</span></span> <span data-ttu-id="39aff-134">Sie können das ursprüngliche Verhalten mit der <xref:Microsoft.SqlServer.Management.Smo.Server.GetDefaultInitFields%2A>-Methode speichern und es nach Bedarf wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="39aff-134">You can save the original behavior by using the <xref:Microsoft.SqlServer.Management.Smo.Server.GetDefaultInitFields%2A> method and restore it as required.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="39aff-135">Beispiele</span><span class="sxs-lookup"><span data-stu-id="39aff-135">Examples</span></span>  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="getting-and-setting-a-property-in-visual-basic"></a><span data-ttu-id="39aff-136">Abrufen und Festlegen einer Eigenschaft in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="39aff-136">Getting and Setting a Property in Visual Basic</span></span>  
 <span data-ttu-id="39aff-137">Dieses Codebeispiel zeigt, wie die <xref:Microsoft.SqlServer.Management.Smo.Information.Edition%2A>-Eigenschaft des <xref:Microsoft.SqlServer.Management.Smo.Information>-Objekts abgerufen wird und wie die <xref:Microsoft.SqlServer.Management.Common.ServerConnection.SqlExecutionModes%2A>-Eigenschaft der <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A>-Eigenschaft auf das `ExecuteSql`-Element des <xref:Microsoft.SqlServer.Management.Common.SqlExecutionModes>-Aufzählungstyps festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="39aff-137">This code example shows how to get the <xref:Microsoft.SqlServer.Management.Smo.Information.Edition%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Information> object and how to set the <xref:Microsoft.SqlServer.Management.Common.ServerConnection.SqlExecutionModes%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A> property to the `ExecuteSql` member of the <xref:Microsoft.SqlServer.Management.Common.SqlExecutionModes> enumerated type.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBProperties1](SMO How to#SMO_VBProperties1)]  -->  
  
## <a name="getting-and-setting-a-property-in-visual-c"></a><span data-ttu-id="39aff-138">Abrufen und Festlegen einer Eigenschaft in Visual C#</span><span class="sxs-lookup"><span data-stu-id="39aff-138">Getting and Setting a Property in Visual C#</span></span>  
 <span data-ttu-id="39aff-139">Dieses Codebeispiel zeigt, wie die <xref:Microsoft.SqlServer.Management.Smo.Information.Edition%2A>-Eigenschaft des <xref:Microsoft.SqlServer.Management.Smo.Information>-Objekts abgerufen wird und wie die <xref:Microsoft.SqlServer.Management.Common.ServerConnection.SqlExecutionModes%2A>-Eigenschaft der <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A>-Eigenschaft auf das `ExecuteSql`-Element des <xref:Microsoft.SqlServer.Management.Common.SqlExecutionModes>-Aufzählungstyps festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="39aff-139">This code example shows how to get the <xref:Microsoft.SqlServer.Management.Smo.Information.Edition%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Information> object and how to set the <xref:Microsoft.SqlServer.Management.Common.ServerConnection.SqlExecutionModes%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A> property to the `ExecuteSql` member of the <xref:Microsoft.SqlServer.Management.Common.SqlExecutionModes> enumerated type.</span></span>  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Get a property.   
Console.WriteLine(srv.Information.Version);   
//Set a property.   
srv.ConnectionContext.SqlExecutionModes = SqlExecutionModes.ExecuteSql;   
}  
```  
  
## <a name="setting-various-properties-before-an-object-is-created-in-visual-basic"></a><span data-ttu-id="39aff-140">Festlegen von verschiedenen Eigenschaften vor dem Erstellen eines Objekts in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="39aff-140">Setting Various Properties Before an Object is Created in Visual Basic</span></span>  
 <span data-ttu-id="39aff-141">Dieses Codebeispiel zeigt, wie die <xref:Microsoft.SqlServer.Management.Smo.Table.AnsiNullsStatus%2A>-Eigenschaft des <xref:Microsoft.SqlServer.Management.Smo.Table>-Objekts direkt festgelegt wird und wie Spalten erstellt und hinzugefügt werden, bevor Sie das <xref:Microsoft.SqlServer.Management.Smo.Table>-Objekt erstellen.</span><span class="sxs-lookup"><span data-stu-id="39aff-141">This code example shows how to directly set the <xref:Microsoft.SqlServer.Management.Smo.Table.AnsiNullsStatus%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Table> object, and how to create and add columns before you create the <xref:Microsoft.SqlServer.Management.Smo.Table> object.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBProperties2](SMO How to#SMO_VBProperties2)]  -->  
  
## <a name="setting-various-properties-before-an-object-is-created-in-visual-c"></a><span data-ttu-id="39aff-142">Festlegen von verschiedenen Eigenschaften vor dem Erstellen eines Objekts in Visual C#</span><span class="sxs-lookup"><span data-stu-id="39aff-142">Setting Various Properties Before an Object is Created in Visual C#</span></span>  
 <span data-ttu-id="39aff-143">Dieses Codebeispiel zeigt, wie die <xref:Microsoft.SqlServer.Management.Smo.Table.AnsiNullsStatus%2A>-Eigenschaft des <xref:Microsoft.SqlServer.Management.Smo.Table>-Objekts direkt festgelegt wird und wie Spalten erstellt und hinzugefügt werden, bevor Sie das <xref:Microsoft.SqlServer.Management.Smo.Table>-Objekt erstellen.</span><span class="sxs-lookup"><span data-stu-id="39aff-143">This code example shows how to directly set the <xref:Microsoft.SqlServer.Management.Smo.Table.AnsiNullsStatus%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Table> object, and how to create and add columns before you create the <xref:Microsoft.SqlServer.Management.Smo.Table> object.</span></span>  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Create a new table in the AdventureWorks2012 database.   
Database db;   
db = srv.Databases("AdventureWorks2012");   
Table tb;   
//Specify the parent database, table schema, and the table name in the constructor.   
tb = new Table(db, "Test_Table", "HumanResources");   
//Add columns because the table requires columns before it can be created.   
Column c1;   
//Specify the parent table, the column name, and data type in the constructor.   
c1 = new Column(tb, "ID", DataType.Int);   
tb.Columns.Add(c1);   
c1.Nullable = false;   
c1.Identity = true;   
c1.IdentityIncrement = 1;   
c1.IdentitySeed = 0;   
Column c2;   
c2 = new Column(tb, "Name", DataType.NVarChar(100));   
c2.Nullable = false;   
tb.Columns.Add(c2);   
tb.AnsiNullsStatus = true;   
//Create the table on the instance of SQL Server.   
tb.Create();   
}  
```  
  
## <a name="iterating-through-all-properties-of-an-object-in-visual-basic"></a><span data-ttu-id="39aff-144">Durchlaufen aller Eigenschaften eines Objekts in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="39aff-144">Iterating Through All Properties of an Object in Visual Basic</span></span>  
 <span data-ttu-id="39aff-145">Dieses Codebeispiel durchläuft die `Properties`-Auflistung des <xref:Microsoft.SqlServer.Management.Smo.StoredProcedure>-Objekts und zeigt die Werte im Ausgabefenster von [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] an.</span><span class="sxs-lookup"><span data-stu-id="39aff-145">This code example iterates through the `Properties` collection of the <xref:Microsoft.SqlServer.Management.Smo.StoredProcedure> object and displays them on the [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] Output screen.</span></span>  
  
 <span data-ttu-id="39aff-146">In dem Beispiel wurde das <xref:Microsoft.SqlServer.Management.Smo.Property>-Objekt in eckige Klammern gesetzt, da es auch ein [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]-Schlüsselwort ist.</span><span class="sxs-lookup"><span data-stu-id="39aff-146">In the example, the <xref:Microsoft.SqlServer.Management.Smo.Property> object has been put in square parentheses because it is also a [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] keyword.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBProperties3](SMO How to#SMO_VBProperties3)]  -->  
  
## <a name="iterating-through-all-properties-of-an-object-in-visual-c"></a><span data-ttu-id="39aff-147">Durchlaufen aller Eigenschaften eines Objekts in Visual C#</span><span class="sxs-lookup"><span data-stu-id="39aff-147">Iterating Through All Properties of an Object in Visual C#</span></span>  
 <span data-ttu-id="39aff-148">Dieses Codebeispiel durchläuft die `Properties`-Auflistung des <xref:Microsoft.SqlServer.Management.Smo.StoredProcedure>-Objekts und zeigt die Werte im Ausgabefenster von [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] an.</span><span class="sxs-lookup"><span data-stu-id="39aff-148">This code example iterates through the `Properties` collection of the <xref:Microsoft.SqlServer.Management.Smo.StoredProcedure> object and displays them on the [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] Output screen.</span></span>  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Set properties on the uspGetEmployeedManagers stored procedure on the AdventureWorks2012 database.   
Database db;   
db = srv.Databases("AdventureWorks2012");   
StoredProcedure sp;   
sp = db.StoredProcedures("uspGetEmployeeManagers");   
sp.AnsiNullsStatus = false;   
sp.QuotedIdentifierStatus = false;   
//Iterate through the properties of the stored procedure and display.   
  Property p;   
  foreach ( p in sp.Properties) {   
    Console.WriteLine(p.Name + p.Value);   
  }   
}  
```  
  
## <a name="setting-default-initialization-fields-in-visual-basic"></a><span data-ttu-id="39aff-149">Festlegen von Standardinitialisierungsfeldern in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="39aff-149">Setting Default Initialization Fields in Visual Basic</span></span>  
 <span data-ttu-id="39aff-150">In diesem Codebeispiel wird gezeigt, wie die Anzahl der in einem SMO-Programm initialisierten Objekteigenschaften minimiert wird.</span><span class="sxs-lookup"><span data-stu-id="39aff-150">This code example shows how to minimize the number of object properties initialized in an SMO program.</span></span> <span data-ttu-id="39aff-151">Sie müssen die `using System.Collections.Specialized`-Anweisung einschließen, um das <xref:System.Collections.Specialized.StringCollection>-Objekt zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="39aff-151">You have to include the `using System.Collections.Specialized`; statement to use the <xref:System.Collections.Specialized.StringCollection> object.</span></span>  
  
 [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] <span data-ttu-id="39aff-152">kann verwendet werden, um die mit dieser Optimierung an die Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] gesendeten Zahlenanweisungen zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="39aff-152">can be used to compare the number statements sent to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] with this optimization.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBDefaultInitFields1](SMO How to#SMO_VBDefaultInitFields1)]  -->  
  
## <a name="setting-default-initialization-fields-in-visual-c"></a><span data-ttu-id="39aff-153">Festlegen von Standardinitialisierungsfeldern in Visual C#</span><span class="sxs-lookup"><span data-stu-id="39aff-153">Setting Default Initialization Fields in Visual C#</span></span>  
 <span data-ttu-id="39aff-154">In diesem Codebeispiel wird gezeigt, wie die Anzahl der in einem SMO-Programm initialisierten Objekteigenschaften minimiert wird.</span><span class="sxs-lookup"><span data-stu-id="39aff-154">This code example shows how to minimize the number of object properties initialized in an SMO program.</span></span> <span data-ttu-id="39aff-155">Sie müssen die `using System.Collections.Specialized`-Anweisung einschließen, um das <xref:System.Collections.Specialized.StringCollection>-Objekt zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="39aff-155">You have to include the `using System.Collections.Specialized`; statement to use the <xref:System.Collections.Specialized.StringCollection> object.</span></span>  
  
 [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] <span data-ttu-id="39aff-156">kann verwendet werden, um die mit dieser Optimierung an die Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] gesendeten Zahlenanweisungen zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="39aff-156">can be used to compare the number statements sent to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] with this optimization.</span></span>  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Reference the AdventureWorks2012 database.   
Database db;   
db = srv.Databases("AdventureWorks2012");   
//Assign the Table object type to a System.Type object variable.   
Table tb;   
Type typ;   
tb = new Table();   
typ = tb.GetType;   
//Assign the current default initialization fields for the Table object type to a   
//StringCollection object variable.   
StringCollection sc;   
sc = srv.GetDefaultInitFields(typ);   
//Set the default initialization fields for the Table object type to the CreateDate property.   
srv.SetDefaultInitFields(typ, "CreateDate");   
//Retrieve the Schema, Name, and CreateDate properties for every table in AdventureWorks2012.   
   //Note that the improvement in performance can be viewed in SQL Server Profiler.   
foreach ( tb in db.Tables) {   
   Console.WriteLine(tb.Schema + "." + tb.Name + " " + tb.CreateDate);   
}   
//Set the default initialization fields for the Table object type back to the original settings.   
srv.SetDefaultInitFields(typ, sc);   
}  
```  
  
  
