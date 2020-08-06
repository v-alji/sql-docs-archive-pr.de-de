---
title: Implementieren der voll Text Suche | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- full-text search [SMO]
ms.assetid: 9ce9ad9c-f671-4760-90b5-e0c8ca051473
author: stevestein
ms.author: sstein
ms.openlocfilehash: f8b797e2a38c9136c34b7058b539fca522e03229
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695518"
---
# <a name="implementing-full-text-search"></a><span data-ttu-id="20a13-102">Einbinden einer Volltextsuche</span><span class="sxs-lookup"><span data-stu-id="20a13-102">Implementing Full-Text Search</span></span>
  <span data-ttu-id="20a13-103">Volltextsuche ist pro Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] verfügbar und wird durch das <xref:Microsoft.SqlServer.Management.Smo.Server.FullTextService%2A>-Objekt in SMO dargestellt.</span><span class="sxs-lookup"><span data-stu-id="20a13-103">Full-text search is available per instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and is represented in SMO by the <xref:Microsoft.SqlServer.Management.Smo.Server.FullTextService%2A> object.</span></span> <span data-ttu-id="20a13-104">Das <xref:Microsoft.SqlServer.Management.Smo.FullTextService>-Objekt befindet sich unter dem `Server`-Objekt.</span><span class="sxs-lookup"><span data-stu-id="20a13-104">The <xref:Microsoft.SqlServer.Management.Smo.FullTextService> object resides under the `Server` object.</span></span> <span data-ttu-id="20a13-105">Es wird verwendet, um die Konfigurationsoptionen für den Dienst [!INCLUDE[msCoName](../../../includes/msconame-md.md)] -Volltextsuche zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="20a13-105">It is used to manage the configuration options for [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Full Text Search service.</span></span> <span data-ttu-id="20a13-106">Das <xref:Microsoft.SqlServer.Management.Smo.FullTextCatalogCollection>-Objekt gehört zum <xref:Microsoft.SqlServer.Management.Smo.Database>-Objekt und ist eine Auflistung von <xref:Microsoft.SqlServer.Management.Smo.FullTextCatalog>-Objekten, die Volltextkataloge darstellen, die für die Datenbank definiert sind.</span><span class="sxs-lookup"><span data-stu-id="20a13-106">The <xref:Microsoft.SqlServer.Management.Smo.FullTextCatalogCollection> object belongs to the <xref:Microsoft.SqlServer.Management.Smo.Database> object and it is a collection of <xref:Microsoft.SqlServer.Management.Smo.FullTextCatalog> objects that represent full-text catalogs defined for the database.</span></span> <span data-ttu-id="20a13-107">Im Gegensatz zu normalen Indizes kann nur ein Volltextindex für jede Tabelle definiert sein.</span><span class="sxs-lookup"><span data-stu-id="20a13-107">You can only have one full-text index defined for each table, unlike normal indexes.</span></span> <span data-ttu-id="20a13-108">Dies wird durch ein <xref:Microsoft.SqlServer.Management.Smo.FullTextIndexColumn>-Objekt im <xref:Microsoft.SqlServer.Management.Smo.Table>-Objekt dargestellt.</span><span class="sxs-lookup"><span data-stu-id="20a13-108">This is represented by a <xref:Microsoft.SqlServer.Management.Smo.FullTextIndexColumn> object in the <xref:Microsoft.SqlServer.Management.Smo.Table> object.</span></span>  
  
 <span data-ttu-id="20a13-109">Um einen Volltextsuchdienst zu erstellen, muss auf der Datenbank ein Volltextkatalog und in einer der Tabellen in der Datenbank ein Index für die Volltextsuche definiert sein.</span><span class="sxs-lookup"><span data-stu-id="20a13-109">To create a full-text search service, you must have a full-text catalog defined on the database and a full-text search index defined on one of the tables in the database.</span></span>  
  
 <span data-ttu-id="20a13-110">Erstellen Sie zunächst einen Volltextkatalog auf der Datenbank, indem Sie den <xref:Microsoft.SqlServer.Management.Smo.FullTextCatalog>-Konstruktor aufrufen und einen Katalognamen angeben.</span><span class="sxs-lookup"><span data-stu-id="20a13-110">First, create a full-text catalog on the database by calling the <xref:Microsoft.SqlServer.Management.Smo.FullTextCatalog> constructor and specifying the catalog name.</span></span> <span data-ttu-id="20a13-111">Erstellen Sie dann den Volltextindex, indem Sie den Konstruktor aufrufen und die Tabelle angeben, in der dieser erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="20a13-111">Then, create the full-text index by calling the constructor and specifying the table on which it is to be created.</span></span> <span data-ttu-id="20a13-112">Daraufhin können Sie Indexspalten für die Volltextsuche hinzufügen, indem Sie das <xref:Microsoft.SqlServer.Management.Smo.FullTextIndexColumn>-Objekt verwenden und den Namen der Spalte in der Tabelle angeben.</span><span class="sxs-lookup"><span data-stu-id="20a13-112">You can then add index columns for the full-text index, by using the <xref:Microsoft.SqlServer.Management.Smo.FullTextIndexColumn> object and providing the name of the column within the table.</span></span> <span data-ttu-id="20a13-113">Legen Sie dann die <xref:Microsoft.SqlServer.Management.Smo.FullTextIndex.CatalogName%2A>-Eigenschaft auf den Katalog fest, den Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="20a13-113">Then, set the <xref:Microsoft.SqlServer.Management.Smo.FullTextIndex.CatalogName%2A> property to the catalog you have created.</span></span> <span data-ttu-id="20a13-114">Rufen Sie zum Schluss die <xref:Microsoft.SqlServer.Management.Smo.FullTextIndex.Create%2A>-Methode auf, und erstellen Sie den Volltextindex auf der Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="20a13-114">Finally, call the <xref:Microsoft.SqlServer.Management.Smo.FullTextIndex.Create%2A> method and create the full-text index on the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="20a13-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="20a13-115">Example</span></span>  
 <span data-ttu-id="20a13-116">Zum Verwenden eines angegebenen Codebeispiels müssen Sie die Programmierumgebung, Programmiervorlage und die zu verwendende Programmiersprache auswählen, um Ihre Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="20a13-116">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="20a13-117">Weitere Informationen finden Sie unter [Erstellen eines Visual Basic SMO-Projekts in Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) oder [Erstellen eines Visual C&#35; SMO-Projekts in Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="20a13-117">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) or [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-a-full-text-search-service-in-visual-basic"></a><span data-ttu-id="20a13-118">Erstellen eines Volltextsuchdiensts in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="20a13-118">Creating a Full-Text Search Service in Visual Basic</span></span>  
 <span data-ttu-id="20a13-119">In diesem Codebeispiel wird ein Volltextsuchkatalog für die `ProductCategory` -Tabelle in der Beispieldatenbank [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] erstellt.</span><span class="sxs-lookup"><span data-stu-id="20a13-119">This code example creates a full-text search catalog for the `ProductCategory` table in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] sample database.</span></span> <span data-ttu-id="20a13-120">Anschließend wird für die Name-Spalte in der `ProductCategory` -Tabelle ein Index für die Volltextsuche erstellt.</span><span class="sxs-lookup"><span data-stu-id="20a13-120">It then creates a full-text search index on the Name column in the `ProductCategory` table.</span></span> <span data-ttu-id="20a13-121">Der Index für die Volltextsuche erfordert, dass bereits ein eindeutiger Index für die Spalte definiert ist.</span><span class="sxs-lookup"><span data-stu-id="20a13-121">The full-text search index requires that there is a unique index already defined on the column.</span></span>  
  
```vb
' compile with:   
' /r:Microsoft.SqlServer.SqlEnum.dll   
' /r:Microsoft.SqlServer.Smo.dll   
' /r:Microsoft.SqlServer.ConnectionInfo.dll   
' /r:Microsoft.SqlServer.Management.Sdk.Sfc.dll  
  
Imports Microsoft.SqlServer.Management.Smo  
Imports Microsoft.SqlServer.Management.Sdk.Sfc  
Imports Microsoft.SqlServer.Management.Common  
  
Public Class A  
   Public Shared Sub Main()  
      ' Connect to the local, default instance of SQL Server.  
      Dim srv As Server = Nothing  
      srv = New Server()  
  
      ' Reference the AdventureWorks database.  
      Dim db As Database = Nothing  
      db = srv.Databases("AdventureWorks")  
  
      ' Reference the ProductCategory table.  
      Dim tb As Table = Nothing  
      tb = db.Tables("ProductCategory", "Production")  
  
      ' Define a FullTextCatalog object variable by specifying the parent database and name arguments in the constructor.  
      Dim ftc As FullTextCatalog = Nothing  
      ftc = New FullTextCatalog(db, "Test_Catalog")  
      ftc.IsDefault = True  
  
      ' Create the Full-Text Search catalog on the instance of SQL Server.  
      ftc.Create()  
  
      ' Define a FullTextIndex object varaible by supplying the parent table argument in the constructor.  
      Dim fti As FullTextIndex = Nothing  
      fti = New FullTextIndex(tb)  
  
      ' Define a FullTextIndexColumn object variable by supplying the parent index and column name arguments in the constructor.  
      Dim ftic As FullTextIndexColumn = Nothing  
      ftic = New FullTextIndexColumn(fti, "Name")  
  
      ' Add the indexed column to the index.  
      fti.IndexedColumns.Add(ftic)  
      fti.ChangeTracking = ChangeTracking.Automatic  
  
      ' Specify the unique index on the table that is required by the Full Text Search index.  
      fti.UniqueIndexName = "AK_ProductCategory_Name"  
  
      ' Specify the catalog associated with the index.  
      fti.CatalogName = "Test_Catalog"  
  
      ' Create the Full Text Search index on the instance of SQL Server.  
      fti.Create()  
   End Sub  
End Class  
```  
  
## <a name="creating-a-full-text-search-service-in-visual-c"></a><span data-ttu-id="20a13-122">Erstellen eines Volltextsuchdiensts in Visual C#</span><span class="sxs-lookup"><span data-stu-id="20a13-122">Creating a Full-Text Search Service in Visual C#</span></span>  
 <span data-ttu-id="20a13-123">In diesem Codebeispiel wird ein Volltextsuchkatalog für die `ProductCategory` -Tabelle in der Beispieldatenbank [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] erstellt.</span><span class="sxs-lookup"><span data-stu-id="20a13-123">This code example creates a full-text search catalog for the `ProductCategory` table in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] sample database.</span></span> <span data-ttu-id="20a13-124">Anschließend wird für die Name-Spalte in der `ProductCategory` -Tabelle ein Index für die Volltextsuche erstellt.</span><span class="sxs-lookup"><span data-stu-id="20a13-124">It then creates a full-text search index on the Name column in the `ProductCategory` table.</span></span> <span data-ttu-id="20a13-125">Der Index für die Volltextsuche erfordert, dass bereits ein eindeutiger Index für die Spalte definiert ist.</span><span class="sxs-lookup"><span data-stu-id="20a13-125">The full-text search index requires that there is a unique index already defined on the column.</span></span>  
  
```csharp
// compile with:   
// /r:Microsoft.SqlServer.SqlEnum.dll   
// /r:Microsoft.SqlServer.Smo.dll   
// /r:Microsoft.SqlServer.ConnectionInfo.dll   
// /r:Microsoft.SqlServer.Management.Sdk.Sfc.dll   
  
using Microsoft.SqlServer.Management.Smo;  
using Microsoft.SqlServer.Management.Sdk.Sfc;  
using Microsoft.SqlServer.Management.Common;  
  
public class A {  
   public static void Main() {  
      // Connect to the local, default instance of SQL Server.  
      Server srv = default(Server);  
      srv = new Server();  
  
      // Reference the AdventureWorks database.  
      Database db = default(Database);  
      db = srv.Databases ["AdventureWorks"];  
  
      // Reference the ProductCategory table.  
      Table tb = default(Table);  
      tb = db.Tables["ProductCategory", "Production"];  
  
      // Define a FullTextCatalog object variable by specifying the parent database and name arguments in the constructor.  
      FullTextCatalog ftc = default(FullTextCatalog);  
      ftc = new FullTextCatalog(db, "Test_Catalog");  
      ftc.IsDefault = true;  
  
      // Create the Full-Text Search catalog on the instance of SQL Server.  
      ftc.Create();  
  
      // Define a FullTextIndex object varaible by supplying the parent table argument in the constructor.  
      FullTextIndex fti = default(FullTextIndex);  
      fti = new FullTextIndex(tb);  
  
      // Define a FullTextIndexColumn object variable by supplying the parent index and column name arguments in the constructor.  
      FullTextIndexColumn ftic = default(FullTextIndexColumn);  
      ftic = new FullTextIndexColumn(fti, "Name");  
  
      // Add the indexed column to the index.  
      fti.IndexedColumns.Add(ftic);  
      fti.ChangeTracking = ChangeTracking.Automatic;  
  
      // Specify the unique index on the table that is required by the Full Text Search index.  
      fti.UniqueIndexName = "AK_ProductCategory_Name";  
  
      // Specify the catalog associated with the index.  
      fti.CatalogName = "Test_Catalog";  
  
      // Create the Full Text Search index on the instance of SQL Server.  
      fti.Create();  
   }  
}  
```  
  
## <a name="creating-a-full-text-search-service-in-powershell"></a><span data-ttu-id="20a13-126">Erstellen eines Volltextsuchdiensts in PowerShell</span><span class="sxs-lookup"><span data-stu-id="20a13-126">Creating a Full-Text Search Service in PowerShell</span></span>  
 <span data-ttu-id="20a13-127">In diesem Codebeispiel wird ein Volltextsuchkatalog für die `ProductCategory` -Tabelle in der Beispieldatenbank [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] erstellt.</span><span class="sxs-lookup"><span data-stu-id="20a13-127">This code example creates a full-text search catalog for the `ProductCategory` table in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] sample database.</span></span> <span data-ttu-id="20a13-128">Anschließend wird für die Name-Spalte in der `ProductCategory` -Tabelle ein Index für die Volltextsuche erstellt.</span><span class="sxs-lookup"><span data-stu-id="20a13-128">It then creates a full-text search index on the Name column in the `ProductCategory` table.</span></span> <span data-ttu-id="20a13-129">Der Index für die Volltextsuche erfordert, dass bereits ein eindeutiger Index für die Spalte definiert ist.</span><span class="sxs-lookup"><span data-stu-id="20a13-129">The full-text search index requires that there is a unique index already defined on the column.</span></span>  
  
```powershell
# Example of implementing a full text search on the default instance.  
# Set the path context to the local, default instance of SQL Server and database tables  
  
CD \sql\localhost\default\databases  
$db = Get-Item AdventureWorks2012  
  
CD AdventureWorks\tables  
  
#Get a reference to the table  
$tb = Get-Item Production.ProductCategory  
  
# Define a FullTextCatalog object variable by specifying the parent database and name arguments in the constructor.  
  
$ftc = New-Object -TypeName Microsoft.SqlServer.Management.SMO.FullTextCatalog -ArgumentList $db, "Test_Catalog2"  
$ftc.IsDefault = $true  
  
# Create the Full Text Search catalog on the instance of SQL Server.  
$ftc.Create()  
  
# Define a FullTextIndex object variable by supplying the parent table argument in the constructor.  
$fti = New-Object -TypeName Microsoft.SqlServer.Management.SMO.FullTextIndex -ArgumentList $tb  
  
#  Define a FullTextIndexColumn object variable by supplying the parent index
#  and column name arguments in the constructor.  
  
$ftic = New-Object -TypeName Microsoft.SqlServer.Management.SMO.FullTextIndexColumn -ArgumentList $fti, "Name"  
  
# Add the indexed column to the index.  
$fti.IndexedColumns.Add($ftic)  
  
# Set change tracking  
$fti.ChangeTracking = [Microsoft.SqlServer.Management.SMO.ChangeTracking]::Automatic  
  
# Specify the unique index on the table that is required by the Full Text Search index.  
$fti.UniqueIndexName = "AK_ProductCategory_Name"  
  
# Specify the catalog associated with the index.  
$fti.CatalogName = "Test_Catalog2"  
  
# Create the Full Text Search Index  
$fti.Create()  
```  
