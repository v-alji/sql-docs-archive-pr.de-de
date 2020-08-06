---
title: Verwenden der Tabellen-und Index Partitionierung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- partitions [SMO]
- storing data [SMO]
- partitioned tables [SQL Server], SMO
- partitioned indexes [SQL Server], SMO
ms.assetid: 0e682d7e-86c3-4d73-950d-aa692d46cb62
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8e05087f63da163b8fa339befae039eb5e7e8245
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615331"
---
# <a name="using-table-and-index-partitioning"></a><span data-ttu-id="f673b-102">Verwenden von Tabellen- und Indexpartitionierung</span><span class="sxs-lookup"><span data-stu-id="f673b-102">Using Table and Index Partitioning</span></span>
  <span data-ttu-id="f673b-103">Daten können mit den von [Partitioned Tables and Indexes](../../partitions/partitioned-tables-and-indexes.md)bereitgestellten Speicheralgorithmen gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="f673b-103">Data can be stored by using the storage algorithms provided by [Partitioned Tables and Indexes](../../partitions/partitioned-tables-and-indexes.md).</span></span> <span data-ttu-id="f673b-104">Die Partitionierung kann bewirken, dass sich große Tabellen und Indizes besser verwalten und skalieren lassen.</span><span class="sxs-lookup"><span data-stu-id="f673b-104">Partitioning can make large tables and indexes more manageable and scalable.</span></span>  
  
## <a name="index-and-table-partitioning"></a><span data-ttu-id="f673b-105">Index- und Tabellenpartitionierung</span><span class="sxs-lookup"><span data-stu-id="f673b-105">Index and Table Partitioning</span></span>  
 <span data-ttu-id="f673b-106">Die Funktion aktiviert Index- und Tabellendaten, die auf mehrere Dateigruppen in Partitionen verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="f673b-106">The feature enables index and table data to be spread across multiple file groups in partitions.</span></span> <span data-ttu-id="f673b-107">Eine Partitionsfunktion definiert, wie die Zeilen einer Tabelle oder eines Index basierend auf den Werten bestimmter Spalten, den so genannten Partitionierungsspalten, einem Satz von Partitionen zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="f673b-107">A partition function defines how the rows of a table or index are mapped to a set of partitions based on the values of certain columns, referred to as partitioning columns.</span></span> <span data-ttu-id="f673b-108">Ein Partitionierungsschema ordnet die durch die Partitionsfunktion angegebenen Partitionen jeweils einer Dateigruppe zu.</span><span class="sxs-lookup"><span data-stu-id="f673b-108">A partition scheme maps each partition specified by the partition function to a file group.</span></span> <span data-ttu-id="f673b-109">Hierdurch können Sie Archivierungsstrategien entwickeln, die es ermöglichen, dass Tabellen, und damit physische Medien, dateigruppenübergreifend skaliert werden können.</span><span class="sxs-lookup"><span data-stu-id="f673b-109">This lets you develop archiving strategies that enable tables to be scaled across file groups, and therefore physical devices.</span></span>  
  
 <span data-ttu-id="f673b-110">Das <xref:Microsoft.SqlServer.Management.Smo.Database>-Objekt enthält eine Auflistung von <xref:Microsoft.SqlServer.Management.Smo.PartitionFunction>-Objekten, die die implementierten Partitionsfunktionen darstellen, und eine Auflistung von <xref:Microsoft.SqlServer.Management.Smo.PartitionScheme>-Objekten, die beschreiben, wie Daten Dateigruppen zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="f673b-110">The <xref:Microsoft.SqlServer.Management.Smo.Database> object contains a collection of <xref:Microsoft.SqlServer.Management.Smo.PartitionFunction> objects that represent the implemented partition functions and a collection of <xref:Microsoft.SqlServer.Management.Smo.PartitionScheme> objects that describe how data is mapped to file groups.</span></span>  
  
 <span data-ttu-id="f673b-111">Jedes <xref:Microsoft.SqlServer.Management.Smo.Table>- und <xref:Microsoft.SqlServer.Management.Smo.Index>-Objekt legt fest, welches Partitionsschema es in der <xref:Microsoft.SqlServer.Management.Smo.PartitionScheme>-Eigenschaft verwendet, und legt die Spalten in <xref:Microsoft.SqlServer.Management.Smo.PartitionSchemeParameterCollection> fest.</span><span class="sxs-lookup"><span data-stu-id="f673b-111">Each <xref:Microsoft.SqlServer.Management.Smo.Table> and <xref:Microsoft.SqlServer.Management.Smo.Index> object specifies which partition scheme it uses in the <xref:Microsoft.SqlServer.Management.Smo.PartitionScheme> property and specifies the columns in the <xref:Microsoft.SqlServer.Management.Smo.PartitionSchemeParameterCollection>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f673b-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f673b-112">Example</span></span>  
 <span data-ttu-id="f673b-113">Für das folgende Codebeispiel müssen Sie die Programmierungsumgebung, die Programmiervorlage und die Programmiersprache auswählen, um Ihre Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f673b-113">For the following code example, you will have to select the programming environment, programming template and the programming language to create your application.</span></span> <span data-ttu-id="f673b-114">Weitere Informationen finden Sie unter [Erstellen eines Visual Basic SMO-Projekts in Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) und [Erstellen eines Visual C&#35; SMO-Projekts in Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="f673b-114">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) and [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="setting-up-a-partition-scheme-for-a-table-in-visual-basic"></a><span data-ttu-id="f673b-115">Einrichten eines Partitionsschemas für eine Tabelle in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f673b-115">Setting Up a Partition Scheme for a Table in Visual Basic</span></span>  
 <span data-ttu-id="f673b-116">Das Codebeispiel veranschaulicht, wie eine Partitionsfunktion und ein Partitionsschema für die `TransactionHistory` -Tabelle in der Beispieldatenbank [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="f673b-116">The code example shows how to create a partition function and a partition scheme for the `TransactionHistory` table in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] sample database.</span></span> <span data-ttu-id="f673b-117">Die Partitionen sind nach Datum aufgeteilt, um alte Datensätze in die `TransactionHistoryArchive` -Tabelle auszugliedern.</span><span class="sxs-lookup"><span data-stu-id="f673b-117">The partitions are divided by date with the intention of separating out old records into the `TransactionHistoryArchive` table.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBPartition1](SMO How to#SMO_VBPartition1)]  -->  
  
## <a name="setting-up-a-partition-scheme-for-a-table-in-visual-c"></a><span data-ttu-id="f673b-118">Einrichten eines Partitionsschemas für eine Tabelle in Visual C#</span><span class="sxs-lookup"><span data-stu-id="f673b-118">Setting Up a Partition Scheme for a Table in Visual C#</span></span>  
 <span data-ttu-id="f673b-119">Das Codebeispiel veranschaulicht, wie eine Partitionsfunktion und ein Partitionsschema für die `TransactionHistory` -Tabelle in der Beispieldatenbank [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="f673b-119">The code example shows how to create a partition function and a partition scheme for the `TransactionHistory` table in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] sample database.</span></span> <span data-ttu-id="f673b-120">Die Partitionen sind nach Datum aufgeteilt, um alte Datensätze in die `TransactionHistoryArchive` -Tabelle auszugliedern.</span><span class="sxs-lookup"><span data-stu-id="f673b-120">The partitions are divided by date with the intention of separating out old records into the `TransactionHistoryArchive` table.</span></span>  
  
```csharp
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Reference the AdventureWorks2012 database.   
Database db;   
db = srv.Databases("AdventureWorks2012");   
//Define and create three new file groups on the database.   
FileGroup fg2;   
fg2 = new FileGroup(db, "Second");   
fg2.Create();   
FileGroup fg3;   
fg3 = new FileGroup(db, "Third");   
fg3.Create();   
FileGroup fg4;   
fg4 = new FileGroup(db, "Fourth");   
fg4.Create();   
//Define a partition function by supplying the parent database and name arguments in the constructor.   
PartitionFunction pf;   
pf = new PartitionFunction(db, "TransHistPF");   
//Add a partition function parameter that specifies the function uses a DateTime range type.   
PartitionFunctionParameter pfp;   
pfp = new PartitionFunctionParameter(pf, DataType.DateTime);   
pf.PartitionFunctionParameters.Add(pfp);   
//Specify the three dates that divide the data into four partitions.   
object[] val;   
val = new object[] {"1/1/2003", "1/1/2004", "1/1/2005"};   
pf.RangeValues = val;   
//Create the partition function.   
pf.Create();   
//Define a partition scheme by supplying the parent database and name arguments in the constructor.   
PartitionScheme ps;   
ps = new PartitionScheme(db, "TransHistPS");   
//Specify the partition function and the filegroups required by the partition scheme.   
ps.PartitionFunction = "TransHistPF";   
ps.FileGroups.Add("PRIMARY");   
ps.FileGroups.Add("second");   
ps.FileGroups.Add("Third");   
ps.FileGroups.Add("Fourth");   
//Create the partition scheme.   
ps.Create();   
}   
```  
  
## <a name="setting-up-a-partition-scheme-for-a-table-in-powershell"></a><span data-ttu-id="f673b-121">Einrichten eines Partitionsschemas für eine Tabelle in PowerShell</span><span class="sxs-lookup"><span data-stu-id="f673b-121">Setting Up a Partition Scheme for a Table in PowerShell</span></span>  
 <span data-ttu-id="f673b-122">Das Codebeispiel veranschaulicht, wie eine Partitionsfunktion und ein Partitionsschema für die `TransactionHistory` -Tabelle in der Beispieldatenbank [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="f673b-122">The code example shows how to create a partition function and a partition scheme for the `TransactionHistory` table in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] sample database.</span></span> <span data-ttu-id="f673b-123">Die Partitionen sind nach Datum aufgeteilt, um alte Datensätze in die `TransactionHistoryArchive` -Tabelle auszugliedern.</span><span class="sxs-lookup"><span data-stu-id="f673b-123">The partitions are divided by date with the intention of separating out old records into the `TransactionHistoryArchive` table.</span></span>  
  
```powershell  
# Set the path context to the local, default instance of SQL Server.  
CD \sql\localhost\default  
  
#Get a server object which corresponds to the default instance  
$srv = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Server  
$db = $srv.Databases["AdventureWorks"]  
#Create four filegroups  
$fg1 = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Filegroup -argumentlist $db, "First"  
$fg2 = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Filegroup -argumentlist $db, "Second"  
$fg3 = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Filegroup -argumentlist $db, "Third"  
$fg4 = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Filegroup -argumentlist $db, "Fourth"  
  
#Define a partition function by supplying the parent database and name arguments in the constructor.  
$pf =  New-Object -TypeName Microsoft.SqlServer.Management.SMO.PartitionFunction -argumentlist $db, "TransHistPF"  
$T = [Microsoft.SqlServer.Management.SMO.DataType]::DateTime  
$T  
$T.GetType()  
#Add a partition function parameter that specifies the function uses a DateTime range type.  
$pfp =  New-Object -TypeName Microsoft.SqlServer.Management.SMO.PartitionFunctionParameter -argumentlist $pf, $T  
  
#Specify the three dates that divide the data into four partitions.
#Create an array of type object to hold the partition data  
$val = "1/1/2003"."1/1/2004","1/1/2005"  
$pf.RangeValues = $val  
$pf  
#Create the partition function  
$pf.Create()  
  
#Create partition scheme  
$ps = New-Object -TypeName Microsoft.SqlServer.Management.SMO.PartitionScheme -argumentlist $db, "TransHistPS"  
$ps.PartitionFunction = "TransHistPF"  
  
#add the filegroups to the scheme
$ps.FileGroups.Add("PRIMARY")  
$ps.FileGroups.Add("Second")  
$ps.FileGroups.Add("Third")  
$ps.FileGroups.Add("Fourth")  
  
#Create it at the server  
$ps.Create()  
```  
  
## <a name="see-also"></a><span data-ttu-id="f673b-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f673b-124">See Also</span></span>  
 [<span data-ttu-id="f673b-125">Partitionierte Tabellen und Indizes</span><span class="sxs-lookup"><span data-stu-id="f673b-125">Partitioned Tables and Indexes</span></span>](../../partitions/partitioned-tables-and-indexes.md)  
