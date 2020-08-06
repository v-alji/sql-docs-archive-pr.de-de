---
title: Verwenden von Sammlungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQL Server Management Objects, collections
- SMO [SQL Server], collections
- collections [SMO]
ms.assetid: 209eb175-2514-4de1-bc32-b2e6a469d945
author: stevestein
ms.author: sstein
ms.openlocfilehash: 288f2110952a85d2aab610c0f1da40d433882400
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609757"
---
# <a name="using-collections"></a><span data-ttu-id="7e68e-102">Verwenden von Auflistungen</span><span class="sxs-lookup"><span data-stu-id="7e68e-102">Using Collections</span></span>
  <span data-ttu-id="7e68e-103">Eine Auflistung ist eine Liste von Objekten, die aus der gleichen Objektklasse gebildet wurden und über dasselbe übergeordnete Objekt verfügen.</span><span class="sxs-lookup"><span data-stu-id="7e68e-103">A collection is a list of objects that have been constructed from the same object class and that share the same parent object.</span></span> <span data-ttu-id="7e68e-104">Das Auflistungsobjekt enthält immer den Namen des Objekttyps mit dem Suffix „Collection“.</span><span class="sxs-lookup"><span data-stu-id="7e68e-104">The collection object always contains the name of the object type with the Collection suffix.</span></span> <span data-ttu-id="7e68e-105">Um beispielsweise auf die Spalten einer gegebenen Tabelle zuzugreifen, verwenden Sie den <xref:Microsoft.SqlServer.Management.Smo.ColumnCollection>-Objekttyp.</span><span class="sxs-lookup"><span data-stu-id="7e68e-105">For example, to access the columns in a specified table, use the <xref:Microsoft.SqlServer.Management.Smo.ColumnCollection> object type.</span></span> <span data-ttu-id="7e68e-106">Er enthält alle <xref:Microsoft.SqlServer.Management.Smo.Column>-Objekte, die zum gleichen <xref:Microsoft.SqlServer.Management.Smo.Table>-Objekt gehören.</span><span class="sxs-lookup"><span data-stu-id="7e68e-106">It contains all the <xref:Microsoft.SqlServer.Management.Smo.Column> objects that belong to the same <xref:Microsoft.SqlServer.Management.Smo.Table> object.</span></span>  
  
 <span data-ttu-id="7e68e-107">Die- [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] `For...Each` Anweisung oder die- [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[csprcs](../../../includes/csprcs-md.md)] `foreach` Anweisung kann verwendet werden, um die einzelnen Member der Auflistung zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="7e68e-107">The [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] `For...Each` statement or the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[csprcs](../../../includes/csprcs-md.md)] `foreach` statement can be used to iterate through each member of the collection.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="7e68e-108">Beispiele</span><span class="sxs-lookup"><span data-stu-id="7e68e-108">Examples</span></span>  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="referencing-an-object-by-using-a-collection-in-visual-basic"></a><span data-ttu-id="7e68e-109">Verweisen auf ein Objekt mithilfe einer Auflistung in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7e68e-109">Referencing an Object by Using a Collection in Visual Basic</span></span>  
 <span data-ttu-id="7e68e-110">Dieses Codebeispiel zeigt, wie eine Spalteneigenschaft mithilfe der Eigenschaften <xref:Microsoft.SqlServer.Management.Smo.TableViewTableTypeBase.Columns%2A>, <xref:Microsoft.SqlServer.Management.Smo.Database.Tables%2A> und <xref:Microsoft.SqlServer.Management.Smo.Server.Databases%2A> festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="7e68e-110">This code example shows how to set a column property by using the <xref:Microsoft.SqlServer.Management.Smo.TableViewTableTypeBase.Columns%2A>, <xref:Microsoft.SqlServer.Management.Smo.Database.Tables%2A>, and <xref:Microsoft.SqlServer.Management.Smo.Server.Databases%2A> properties.</span></span> <span data-ttu-id="7e68e-111">Diese Eigenschaften repräsentieren Auflistungen, mit denen ein bestimmtes Objekt identifiziert werden kann, wenn sie mit einem Parameter verwendet werden, der den Namen des Objekts angibt.</span><span class="sxs-lookup"><span data-stu-id="7e68e-111">These properties represent collections, which can be used to identify a particular object when they are used with a parameter that specifies the name of the object.</span></span> <span data-ttu-id="7e68e-112">Der Name und das Schema sind für die <xref:Microsoft.SqlServer.Management.Smo.Database.Tables%2A> Auflistungsobjekteigenschaft erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7e68e-112">The name and the schema are required for the <xref:Microsoft.SqlServer.Management.Smo.Database.Tables%2A> collection object property.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBCollections1](SMO How to#SMO_VBCollections1)]  -->  
  
## <a name="referencing-an-object-by-using-a-collection-in-visual-c"></a><span data-ttu-id="7e68e-113">Verweisen auf ein Objekt mithilfe einer Auflistung in Visual C#</span><span class="sxs-lookup"><span data-stu-id="7e68e-113">Referencing an Object by Using a Collection in Visual C#</span></span>  
 <span data-ttu-id="7e68e-114">Dieses Codebeispiel zeigt, wie eine Spalteneigenschaft mithilfe der Eigenschaften <xref:Microsoft.SqlServer.Management.Smo.TableViewTableTypeBase.Columns%2A>, <xref:Microsoft.SqlServer.Management.Smo.Database.Tables%2A> und <xref:Microsoft.SqlServer.Management.Smo.Server.Databases%2A> festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="7e68e-114">This code example shows how to set a column property by using the <xref:Microsoft.SqlServer.Management.Smo.TableViewTableTypeBase.Columns%2A>, <xref:Microsoft.SqlServer.Management.Smo.Database.Tables%2A>, and <xref:Microsoft.SqlServer.Management.Smo.Server.Databases%2A> properties.</span></span> <span data-ttu-id="7e68e-115">Diese Eigenschaften repräsentieren Auflistungen, mit denen ein bestimmtes Objekt identifiziert werden kann, wenn sie mit einem Parameter verwendet werden, der den Namen des Objekts angibt.</span><span class="sxs-lookup"><span data-stu-id="7e68e-115">These properties represent collections, which can be used to identify a particular object when they are used with a parameter that specifies the name of the object.</span></span> <span data-ttu-id="7e68e-116">Der Name und das Schema sind für die <xref:Microsoft.SqlServer.Management.Smo.Database.Tables%2A> Auflistungsobjekteigenschaft erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7e68e-116">The name and the schema are required for the <xref:Microsoft.SqlServer.Management.Smo.Database.Tables%2A> collection object property.</span></span>  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Modify a property using the Databases, Tables, and Columns collections to reference a column.   
srv.Databases("AdventureWorks2012").Tables("Person", "Person").Columns("LastName").Nullable = true;   
//Call the Alter method to make the change on the instance of SQL Server.   
srv.Databases("AdventureWorks2012").Tables("Person", "Person").Columns("LastName").Alter();   
}  
```  
  
## <a name="iterating-through-the-members-of-a-collection-in-visual-basic"></a><span data-ttu-id="7e68e-117">Durchlaufen der Elemente einer Auflistung in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7e68e-117">Iterating Through the Members of a Collection in Visual Basic</span></span>  
 <span data-ttu-id="7e68e-118">In diesem Codebeispiel wird die <xref:Microsoft.AnalysisServices.Server.Databases%2A>-Auflistungseigenschaft durchlaufen, und anschließend werden alle Datenbankverbindungen mit der Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7e68e-118">This code example iterates through the <xref:Microsoft.AnalysisServices.Server.Databases%2A> collection property and displays all database connections to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBCollections2](SMO How to#SMO_VBCollections2)]  -->  
  
## <a name="iterating-through-the-members-of-a-collection-in-visual-c"></a><span data-ttu-id="7e68e-119">Durchlaufen der Elemente einer Auflistung in Visual C#</span><span class="sxs-lookup"><span data-stu-id="7e68e-119">Iterating Through the Members of a Collection in Visual C#</span></span>  
 <span data-ttu-id="7e68e-120">In diesem Codebeispiel wird die <xref:Microsoft.AnalysisServices.Server.Databases%2A>-Auflistungseigenschaft durchlaufen, und anschließend werden alle Datenbankverbindungen mit der Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7e68e-120">This code example iterates through the <xref:Microsoft.AnalysisServices.Server.Databases%2A> collection property and displays all database connections to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
```  
//Connect to the local, default instance of SQL Server.   
{   
Server srv = default(Server);   
srv = new Server();   
int count = 0;   
int total = 0;   
//Iterate through the databases and call the GetActiveDBConnectionCount method.   
Database db = default(Database);   
foreach ( db in srv.Databases) {   
  count = srv.GetActiveDBConnectionCount(db.Name);   
  total = total + count;   
  //Display the number of connections for each database.   
  Console.WriteLine(count + " connections on " + db.Name);   
}   
//Display the total number of connections on the instance of SQL Server.   
Console.WriteLine("Total connections =" + total);   
}   
```  
  
  
