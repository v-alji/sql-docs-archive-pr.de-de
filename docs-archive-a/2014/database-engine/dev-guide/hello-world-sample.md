---
title: Hallo Welt Beispiel | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
ms.assetid: fed6c358-f5ee-4d4c-9ad6-089778383ba7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0d5616c1d4ef6428a011c8e36be3757931039c9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726185"
---
# <a name="hello-world-sample"></a><span data-ttu-id="e576b-102">Beispiel "Hello World"</span><span class="sxs-lookup"><span data-stu-id="e576b-102">Hello World Sample</span></span>
  <span data-ttu-id="e576b-103">Das Hello World-Beispiel veranschaulicht die grundlegenden Vorgänge, die beim Erstellen, Bereitstellen und Testen einer einfachen gespeicherten Prozedur, die auf einer CLR (Common Language Runtime)-Integration basiert, ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="e576b-103">The Hello World sample demonstrates the basic operations that are involved in creating, deploying, and testing a simple common language runtime (CLR) integration-based stored procedure.</span></span> <span data-ttu-id="e576b-104">Diese Beispiel zeigt außerdem, wie Sie Daten über einen Datensatz, der dynamisch von der gespeicherten Prozedur erstellt und an den Aufrufer zurückgegeben wird, zurückgeben können.</span><span class="sxs-lookup"><span data-stu-id="e576b-104">This sample also demonstrates how to return data through a record, which is dynamically constructed by the stored procedure and returned to the caller.</span></span>  
  
 <span data-ttu-id="e576b-105">Die `HelloWorld` gespeicherte Prozedur gibt die Zeichenfolge "Hello World!" zurück.</span><span class="sxs-lookup"><span data-stu-id="e576b-105">The `HelloWorld` stored procedure returns the string "Hello world!"</span></span> <span data-ttu-id="e576b-106">in einem Resultset, das aus einer Zeile besteht.</span><span class="sxs-lookup"><span data-stu-id="e576b-106">in a result set consisting of one row.</span></span> <span data-ttu-id="e576b-107">In diesem Beispiel werden einige Verwendungsmöglichkeiten für die-Klassen [Microsoft. SqlServer. Server. SqlMetaData](https://go.microsoft.com/fwlink/?LinkID=193572), [Microsoft. SqlServer. Server. SqlDataRecord](https://go.microsoft.com/fwlink/?LinkID=193573) und [Microsoft. SqlServer. Server. Pipe](https://go.microsoft.com/fwlink/?LinkID=193571)veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="e576b-107">This example illustrates some uses for the classes [Microsoft.SqlServer.Server.SqlMetaData](https://go.microsoft.com/fwlink/?LinkID=193572), [Microsoft.SqlServer.Server.SqlDataRecord](https://go.microsoft.com/fwlink/?LinkID=193573) and [Microsoft.SqlServer.Server.Pipe](https://go.microsoft.com/fwlink/?LinkID=193571).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e576b-108">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="e576b-108">Prerequisites</span></span>  
 <span data-ttu-id="e576b-109">Zum Erstellen und Ausführen dieses Projekts muss die folgende Software installiert sein:</span><span class="sxs-lookup"><span data-stu-id="e576b-109">To create and run this project the following the following software must be installed:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e576b-110">oder [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express.</span><span class="sxs-lookup"><span data-stu-id="e576b-110">or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express.</span></span> <span data-ttu-id="e576b-111">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express erhalten Sie kostenlos auf der [Website](https://www.microsoft.com/sql-server/sql-server-editions-express) mit der Dokumentation und den Beispielen für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express.</span><span class="sxs-lookup"><span data-stu-id="e576b-111">You can obtain [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express free of charge from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express Documentation and Samples [Web site](https://www.microsoft.com/sql-server/sql-server-editions-express)</span></span>  
  
-   <span data-ttu-id="e576b-112">Die AdventureWorks-Datenbank, die auf der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Developer-[Website](https://go.microsoft.com/fwlink/?linkid=62796) zur Verfügung gestellt wird.</span><span class="sxs-lookup"><span data-stu-id="e576b-112">The AdventureWorks database that is available at the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Developer [Web site](https://go.microsoft.com/fwlink/?linkid=62796)</span></span>  
  
-   <span data-ttu-id="e576b-113">.NET Framework SDK 2.0 oder höher oder Microsoft Visual Studio 2005 oder höher.</span><span class="sxs-lookup"><span data-stu-id="e576b-113">.NET Framework SDK 2.0 or later or Microsoft Visual Studio 2005 or later.</span></span> <span data-ttu-id="e576b-114">Das .NET Framework SDK ist kostenlos erhältlich.</span><span class="sxs-lookup"><span data-stu-id="e576b-114">You can obtain .NET Framework SDK free of charge.</span></span>  
  
-   <span data-ttu-id="e576b-115">Außerdem müssen die folgenden Bedingungen erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="e576b-115">In addition, the following conditions must be met:</span></span>  
  
-   <span data-ttu-id="e576b-116">In der von Ihnen verwendeten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Instanz muss die CLR-Integration aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="e576b-116">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using must have CLR integration enabled.</span></span>  
  
-   <span data-ttu-id="e576b-117">Führen Sie zum Aktivieren der CLR-Integration die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="e576b-117">In order to enable CLR integration, perform the following steps:</span></span>  
  
    #### <a name="enabling-clr-integration"></a><span data-ttu-id="e576b-118">Aktivieren der CLR-Integration</span><span class="sxs-lookup"><span data-stu-id="e576b-118">Enabling CLR Integration</span></span>  
  
    -   <span data-ttu-id="e576b-119">Führen Sie die folgenden [!INCLUDE[tsql](../../includes/tsql-md.md)]-Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="e576b-119">Execute the following [!INCLUDE[tsql](../../includes/tsql-md.md)] commands:</span></span>  
  
     `sp_configure 'clr enabled', 1`  
  
     `GO`  
  
     `RECONFIGURE`  
  
     `GO`  
  
    > [!NOTE]  
    >  <span data-ttu-id="e576b-120">Um CLR zu aktivieren, benötigen Sie die `ALTER SETTINGS`-Serverberechtigung, die Mitglieder der festen Serverrollen `sysadmin` und `serveradmin` implizit erhalten.</span><span class="sxs-lookup"><span data-stu-id="e576b-120">To enable CLR, you must have `ALTER SETTINGS` server level permission, which is implicitly held by members of the `sysadmin` and `serveradmin` fixed server roles.</span></span>  
  
-   <span data-ttu-id="e576b-121">Die AdventureWorks-Datenbank muss in der von Ihnen verwendeten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Instanz installiert sein.</span><span class="sxs-lookup"><span data-stu-id="e576b-121">The AdventureWorks database must be installed on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using.</span></span>  
  
-   <span data-ttu-id="e576b-122">Wenn Sie kein Administrator für die verwendete- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Instanz sind, müssen Sie über einen Administrator verfügen, der Ihnen **CreateAssembly** die Berechtigung zum Abschluss der Installation erteilt.</span><span class="sxs-lookup"><span data-stu-id="e576b-122">If you are not an administrator for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using, you must have an administrator grant you **CreateAssembly** permission to complete the installation.</span></span>  
  
## <a name="building-the-sample"></a><span data-ttu-id="e576b-123">Erstellen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="e576b-123">Building the Sample</span></span>  
  
#### <a name="create-and-run-the-sample-by-using-the-following-instructions"></a><span data-ttu-id="e576b-124">Verwenden Sie die folgenden Anweisungen, um das Beispiel zu erstellen und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="e576b-124">Create and run the sample by using the following instructions:</span></span>  
  
1.  <span data-ttu-id="e576b-125">Wechseln Sie zu einer Visual Studio- oder .NET Framework-Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="e576b-125">Open a Visual Studio or .NET Framework command prompt.</span></span>  
  
2.  <span data-ttu-id="e576b-126">Erstellen Sie ggf. ein Verzeichnis für das Beispiel.</span><span class="sxs-lookup"><span data-stu-id="e576b-126">If necessary, create a directory for your sample.</span></span> <span data-ttu-id="e576b-127">Für dieses Beispiel wird C:\MySample verwendet.</span><span class="sxs-lookup"><span data-stu-id="e576b-127">For this example, we will use C:\MySample.</span></span>  
  
3.  <span data-ttu-id="e576b-128">Erstellen Sie in c:\MySample die Datei `HelloWorld.vb` (für das Visual Basic-Beispiel) oder `HelloWorld.cs` (für das C#-Beispiel), und kopieren Sie den entsprechenden Visual Basic- oder C#-Beispielcode (unten) in die Datei.</span><span class="sxs-lookup"><span data-stu-id="e576b-128">In c:\MySample, create `HelloWorld.vb` (for the Visual Basic sample) or `HelloWorld.cs` (for the C# sample) and copy the appropriate Visual Basic or C# sample code (below) into the file.</span></span>  
  
4.  <span data-ttu-id="e576b-129">Kompilieren Sie an der Eingabeaufforderung den Beispielcode, indem Sie je nach gewählter Sprache eine der folgenden Anweisungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="e576b-129">Compile the sample code from the command line prompt by executing one of the following, depending on your choice of language.</span></span>  
  
    -   `vbc C:HelloWorld.vb /target:library`  
  
    -   `csc /target:library HelloWorld.cs`  
  
5.  <span data-ttu-id="e576b-130">Kopieren Sie den [!INCLUDE[tsql](../../includes/tsql-md.md)]-Installationscode in eine Datei, und speichern Sie sie als `Install.sql` im Beispielverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="e576b-130">Copy the [!INCLUDE[tsql](../../includes/tsql-md.md)] installation code into a file and save it as `Install.sql` in the sample directory.</span></span>  
  
6.  <span data-ttu-id="e576b-131">Stellen Sie die Assembly und die gespeicherte Prozedur bereit, indem Sie die folgende Anweisung ausführen:</span><span class="sxs-lookup"><span data-stu-id="e576b-131">Deploy the assembly and stored procedure by executing</span></span>  
  
    -   `sqlcmd -E -I -i install.sql -v root = "C:\MySample\"`  
  
7.  <span data-ttu-id="e576b-132">Kopieren [!INCLUDE[tsql](../../includes/tsql-md.md)] Sie das Test Befehls Skript in eine Datei, und speichern Sie Sie als `test.sql` im Beispiel Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="e576b-132">Copy [!INCLUDE[tsql](../../includes/tsql-md.md)] test command script into a file and save it as `test.sql` in the sample directory.</span></span>  
  
8.  <span data-ttu-id="e576b-133">Führen Sie das Testskript mit dem folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="e576b-133">Execute the test script with the following command</span></span>  
  
    -   `sqlcmd -E -I -i test.sql`  
  
9. <span data-ttu-id="e576b-134">Kopieren Sie das [!INCLUDE[tsql](../../includes/tsql-md.md)]-Bereinigungsskript in eine Datei, und speichern Sie diese als `cleanup.sql` im Beispielverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="e576b-134">Copy the [!INCLUDE[tsql](../../includes/tsql-md.md)] cleanup script into a file and save it as `cleanup.sql` in the sample directory.</span></span>  
  
10. <span data-ttu-id="e576b-135">Führen Sie das Skript mit dem folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="e576b-135">Execute the script with the  following command</span></span>  
  
    -   `sqlcmd -E -I -i cleanup.sql`  
  
## <a name="sample-code"></a><span data-ttu-id="e576b-136">Beispielcode</span><span class="sxs-lookup"><span data-stu-id="e576b-136">Sample Code</span></span>  
 <span data-ttu-id="e576b-137">Die Codelistings für dieses Beispiel lauten wie folgt.</span><span class="sxs-lookup"><span data-stu-id="e576b-137">The following are the code listings for this sample.</span></span>  
  
 <span data-ttu-id="e576b-138">C#</span><span class="sxs-lookup"><span data-stu-id="e576b-138">C#</span></span>  
  
```  
using System;  
using System.Data;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using Microsoft.SqlServer.Server;  
public partial class StoredProcedures  
{  
    [Microsoft.SqlServer.Server.SqlProcedure]  
    public static void HelloWorld()  
    {  
        Microsoft.SqlServer.Server.SqlMetaData columnInfo  
                = new Microsoft.SqlServer.Server.SqlMetaData("Column1", SqlDbType.NVarChar, 12);  
        SqlDataRecord greetingRecord  
            = new SqlDataRecord(new Microsoft.SqlServer.Server.SqlMetaData[] { columnInfo });  
        greetingRecord.SetString(0, "Hello world!");  
        SqlContext.Pipe.Send(greetingRecord);  
    }  
};  
  
```  
  
 <span data-ttu-id="e576b-139">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e576b-139">Visual Basic</span></span>  
  
```  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
  
Partial Public NotInheritable Class StoredProcedures  
    <Microsoft.SqlServer.Server.SqlProcedure()> _  
    Public Shared Sub HelloWorld()  
        Dim columnInfo As New Microsoft.SqlServer.Server.SqlMetaData("Column1", _  
            SqlDbType.NVarChar, 12)  
        Dim greetingRecord As New SqlDataRecord(New  _  
            Microsoft.SqlServer.Server.SqlMetaData() {columnInfo})  
        greetingRecord.SetString(0, "Hello World!")  
        SqlContext.Pipe.Send(greetingRecord)  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="e576b-140">Dies ist das [!INCLUDE[tsql](../../includes/tsql-md.md)]-Installationsskript (`Install.sql`), das die Assembly bereitstellt und die gespeicherte Prozedur in der Datenbank erstellt.</span><span class="sxs-lookup"><span data-stu-id="e576b-140">This is the [!INCLUDE[tsql](../../includes/tsql-md.md)] installation script (`Install.sql`), which deploys the assembly and creates the stored procedure in the database.</span></span>  
  
```  
USE AdventureWorks  
GO  
IF EXISTS (SELECT * FROM sys.procedures WHERE [name] = 'usp_HelloWorld')  
DROP PROCEDURE usp_HelloWorld;  
GO  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorld')  
DROP ASSEMBLY HelloWorld;  
GO  
DECLARE @SamplesPath nvarchar(1024)  
set @SamplesPath = '$(root)'  
CREATE ASSEMBLY HelloWorld   
FROM @SamplesPath + 'HelloWorld.dll'  
WITH permission_set = Safe;  
GO  
  
CREATE PROCEDURE usp_HelloWorld  
--(  
--    @Greeting nvarchar(12) OUTPUT  
--)  
AS EXTERNAL NAME HelloWorld.[StoredProcedures].HelloWorld;  
GO  
```  
  
 <span data-ttu-id="e576b-141">Dies ist die Datei `test.sql`, die das Beispiel durch das Ausführen der gespeicherten Prozedur testet.</span><span class="sxs-lookup"><span data-stu-id="e576b-141">This is `test.sql`, which tests the sample by executing the stored procedure.</span></span>  
  
```  
use AdventureWorks  
go  
execute usp_HelloWorld  
  
USE AdventureWorks;  
GO  
IF EXISTS (SELECT * FROM sys.procedures WHERE [name] = 'usp_HelloWorld')  
DROP PROCEDURE usp_HelloWorld;  
GO  
```  
  
 <span data-ttu-id="e576b-142">Im folgenden [!INCLUDE[tsql](../../includes/tsql-md.md)]-Code werden die Assembly und die gespeicherte Prozedur aus der Datenbank entfernt.</span><span class="sxs-lookup"><span data-stu-id="e576b-142">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] removes the assembly and stored procedure from the database.</span></span>  
  
```  
USE AdventureWorks  
GO  
  
IF EXISTS (SELECT * FROM sys.procedures WHERE [name] = 'usp_HelloWorld')  
DROP PROCEDURE usp_HelloWorld;  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorld')  
DROP ASSEMBLY HelloWorld;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="e576b-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e576b-143">See Also</span></span>  
 [<span data-ttu-id="e576b-144">Verwendungsszenarios und Beispiele für Common Language Runtime-Integration &#40;CLR&#41;</span><span class="sxs-lookup"><span data-stu-id="e576b-144">Usage Scenarios and Examples for Common Language Runtime &#40;CLR&#41; Integration</span></span>](../../../2014/database-engine/dev-guide/usage-scenarios-and-examples-for-common-language-runtime-clr-integration.md)  
  
  
