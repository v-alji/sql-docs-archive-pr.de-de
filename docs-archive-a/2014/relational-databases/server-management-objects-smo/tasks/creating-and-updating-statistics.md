---
title: Erstellen und Aktualisieren von Statistiken | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- statistical information [SMO]
ms.assetid: 47a0a172-a969-4deb-bca9-dd04401a0fe1
author: stevestein
ms.author: sstein
ms.openlocfilehash: 48c61bb1b213e4b57c7fbae0b0ec7294c9401a0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621977"
---
# <a name="creating-and-updating-statistics"></a><span data-ttu-id="caf39-102">Erstellen und Aktualisieren von Statistiken</span><span class="sxs-lookup"><span data-stu-id="caf39-102">Creating and Updating Statistics</span></span>
  <span data-ttu-id="caf39-103">In SMO können statistische Informationen über die Verarbeitung von Abfragen in der Datenbank mithilfe des  <xref:Microsoft.SqlServer.Management.Smo.Statistic>-Objekts gesammelt werden.</span><span class="sxs-lookup"><span data-stu-id="caf39-103">In SMO, statistical information about processing queries in the database can be collected by using the <xref:Microsoft.SqlServer.Management.Smo.Statistic> object.</span></span>  
  
 <span data-ttu-id="caf39-104">Über das <xref:Microsoft.SqlServer.Management.Smo.Statistic>- und das <xref:Microsoft.SqlServer.Management.Smo.StatisticColumn>-Objekt ist es möglich, für jede beliebige Spalte Statistiken zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="caf39-104">It is possible to create statistics for any column by using the <xref:Microsoft.SqlServer.Management.Smo.Statistic> and <xref:Microsoft.SqlServer.Management.Smo.StatisticColumn> object.</span></span> <span data-ttu-id="caf39-105">Die <xref:Microsoft.SqlServer.Management.Smo.Statistic.Update%2A>-Methode kann ausgeführt werden, um die Statistik im <xref:Microsoft.SqlServer.Management.Smo.Statistic>-Objekt zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="caf39-105">The <xref:Microsoft.SqlServer.Management.Smo.Statistic.Update%2A> method can be run to update the statistics in the <xref:Microsoft.SqlServer.Management.Smo.Statistic> object.</span></span> <span data-ttu-id="caf39-106">Die Ergebnisse können im Abfrageoptimierer angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="caf39-106">The results can be viewed in the Query Optimizer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="caf39-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="caf39-107">Example</span></span>  
 <span data-ttu-id="caf39-108">Zum Verwenden eines angegebenen Codebeispiels müssen Sie die Programmierumgebung, Programmiervorlage und die zu verwendende Programmiersprache auswählen, um Ihre Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="caf39-108">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="caf39-109">Weitere Informationen finden Sie unter [Erstellen eines Visual Basic SMO-Projekts in Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) oder [Erstellen eines Visual C&#35; SMO-Projekts in Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="caf39-109">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) or [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-and-update-statistics-in-visual-basic"></a><span data-ttu-id="caf39-110">Erstellen und Aktualisieren von Statistiken in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="caf39-110">Creating and Update Statistics in Visual Basic</span></span>  
 <span data-ttu-id="caf39-111">In diesem Codebeispiel wird eine neue Tabelle für eine vorhandene Datenbank erstellt, für die das <xref:Microsoft.SqlServer.Management.Smo.Statistic>-Objekt und das <xref:Microsoft.SqlServer.Management.Smo.StatisticColumn>-Objekt erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="caf39-111">This code example creates a new table on an existing database for which the <xref:Microsoft.SqlServer.Management.Smo.Statistic> object and the <xref:Microsoft.SqlServer.Management.Smo.StatisticColumn> object are created.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBStatistics1](SMO How to#SMO_VBStatistics1)]  -->  
  
## <a name="creating-and-update-statistics-in-visual-c"></a><span data-ttu-id="caf39-112">Erstellen und Aktualisieren von Statistiken in Visual C#</span><span class="sxs-lookup"><span data-stu-id="caf39-112">Creating and Update Statistics in Visual C#</span></span>  
 <span data-ttu-id="caf39-113">In diesem Codebeispiel wird eine neue Tabelle für eine vorhandene Datenbank erstellt, für die das <xref:Microsoft.SqlServer.Management.Smo.Statistic>-Objekt und das <xref:Microsoft.SqlServer.Management.Smo.StatisticColumn>-Objekt erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="caf39-113">This code example creates a new table on an existing database for which the <xref:Microsoft.SqlServer.Management.Smo.Statistic> object and the <xref:Microsoft.SqlServer.Management.Smo.StatisticColumn> object are created.</span></span>  
  
```csharp
{  
            //Connect to the local, default instance of SQL Server.  
            Server srv = new Server();  
            //Reference the AdventureWorks2012 database.   
            Database db = default(Database);  
            db = srv.Databases["AdventureWorks2012"];  
            //Reference the CreditCard table.   
  
           Table tb = db.Tables["CreditCard", "Sales"];  
            //Define a Statistic object by supplying the parent table and name   
            //arguments in the constructor.   
            Statistic stat = default(Statistic);  
            stat = new Statistic(tb, "Test_Statistics");  
            //Define a StatisticColumn object variable for the CardType column   
            //and add to the Statistic object variable.   
            StatisticColumn statcol = default(StatisticColumn);  
            statcol = new StatisticColumn(stat, "CardType");  
            stat.StatisticColumns.Add(statcol);  
            //Create the statistic counter on the instance of SQL Server.   
            stat.Create();  
        }  
```  
  
## <a name="creating-and-update-statistics-in-powershell"></a><span data-ttu-id="caf39-114">Erstellen und Aktualisieren von Statistiken in PowerShell</span><span class="sxs-lookup"><span data-stu-id="caf39-114">Creating and Update Statistics in PowerShell</span></span>  
 <span data-ttu-id="caf39-115">In diesem Codebeispiel wird eine neue Tabelle für eine vorhandene Datenbank erstellt, für die das <xref:Microsoft.SqlServer.Management.Smo.Statistic>-Objekt und das <xref:Microsoft.SqlServer.Management.Smo.StatisticColumn>-Objekt erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="caf39-115">This code example creates a new table on an existing database for which the <xref:Microsoft.SqlServer.Management.Smo.Statistic> object and the <xref:Microsoft.SqlServer.Management.Smo.StatisticColumn> object are created.</span></span>  
  
```powershell
# Example of implementing a full text search on the default instance.  
# Set the path context to the local, default instance of SQL Server and database tables  
  
CD \sql\localhost\default\databases  
$db = get-item AdventureWorks2012  
  
CD AdventureWorks2012\tables  
  
#Get a reference to the table  
$tb = get-item Production.ProductCategory  
  
# Define a FullTextCatalog object variable by specifying the parent database and name arguments in the constructor.  
  
$ftc = New-Object -TypeName Microsoft.SqlServer.Management.SMO.FullTextCatalog -argumentlist $db, "Test_Catalog2"  
$ftc.IsDefault = $true  
  
# Create the Full Text Search catalog on the instance of SQL Server.  
$ftc.Create()  
  
# Define a FullTextIndex object variable by supplying the parent table argument in the constructor.  
$fti = New-Object -TypeName Microsoft.SqlServer.Management.SMO.FullTextIndex -argumentlist $tb  
  
#  Define a FullTextIndexColumn object variable by supplying the parent index   
#  and column name arguments in the constructor.  
  
$ftic = New-Object -TypeName Microsoft.SqlServer.Management.SMO.FullTextIndexColumn -argumentlist $fti, "Name"  
  
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
