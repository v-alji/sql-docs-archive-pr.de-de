---
title: Erstellen einer FILESTREAM-aktivierten Datenbank | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], FILESTREAM-enabled databases
ms.assetid: 0fc16356-76f7-44b8-a58b-f0b7c43694ec
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 0fe6e5bc6e4f60bc0703482f3bf4d761104b3c5f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701235"
---
# <a name="create-a-filestream-enabled-database"></a><span data-ttu-id="19249-102">Erstellen einer FILESTREAM-aktivierten Datenbank</span><span class="sxs-lookup"><span data-stu-id="19249-102">Create a FILESTREAM-Enabled Database</span></span>
  <span data-ttu-id="19249-103">In diesem Thema erfahren Sie, wie Sie eine Datenbank erstellen, die FILESTREAM unterstützt.</span><span class="sxs-lookup"><span data-stu-id="19249-103">This topic shows how to create a database that supports FILESTREAM.</span></span> <span data-ttu-id="19249-104">Da für FILESTREAM eine besondere Art von Dateigruppe verwendet wird, müssen Sie beim Erstellen der Datenbank die CONTAINS FILESTREAM-Klausel für mindestens eine Dateigruppe angeben.</span><span class="sxs-lookup"><span data-stu-id="19249-104">Because FILESTREAM uses a special type of filegroup, when you create the database, you must specify the CONTAINS FILESTREAM clause for at least one filegroup.</span></span>  
  
 <span data-ttu-id="19249-105">Eine FILESTREAM-Dateigruppe kann mehrere Dateien enthalten.</span><span class="sxs-lookup"><span data-stu-id="19249-105">A FILESTREAM filegroup can contain more than one file.</span></span> <span data-ttu-id="19249-106">Ein Codebeispiel, in dem veranschaulicht wird, wie eine FILESTREAM-Dateigruppe erstellt wird, die mehrere Dateien enthält, finden Sie unter [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="19249-106">For a code example that demonstrates how to create a FILESTREAM filegroup that contains multiple files, see [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span></span>  
  
### <a name="to-create-a-filestream-enabled-database"></a><span data-ttu-id="19249-107">So erstellen Sie eine FILESTREAM-aktivierte Datenbank</span><span class="sxs-lookup"><span data-stu-id="19249-107">To create a FILESTREAM-enabled database</span></span>  
  
1.  <span data-ttu-id="19249-108">Klicken Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]auf **Neue Abfrage** , um den Abfrage-Editor zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="19249-108">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], click **New Query** to display the Query Editor.</span></span>  
  
2.  <span data-ttu-id="19249-109">Kopieren des [!INCLUDE[tsql](../../includes/tsql-md.md)] Codes erstellt eine FILESTREAM-aktivierte Datenbank mit dem Namen Archive.</span><span class="sxs-lookup"><span data-stu-id="19249-109">Copy the [!INCLUDE[tsql](../../includes/tsql-md.md)] code creates a FILESTREAM-enabled database called Archive.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="19249-110">Für dieses Skript muss das Verzeichnis "C:\Data" vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="19249-110">For this script, the directory C:\Data must exist.</span></span>  
  
3.  <span data-ttu-id="19249-111">Klicken Sie auf **Ausführen**, um die Datenbank zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="19249-111">To build the database, click **Execute**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19249-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="19249-112">Example</span></span>  
 <span data-ttu-id="19249-113">Im folgenden Codebeispiel wird eine Datenbank mit dem Namen `Archive`erstellt.</span><span class="sxs-lookup"><span data-stu-id="19249-113">The following code example creates a database that is named `Archive`.</span></span> <span data-ttu-id="19249-114">Die Datenbank enthält drei Dateigruppen: `PRIMARY`, `Arch1`und `FileStreamGroup1`.</span><span class="sxs-lookup"><span data-stu-id="19249-114">The database contains three filegroups: `PRIMARY`, `Arch1`, and `FileStreamGroup1`.</span></span> <span data-ttu-id="19249-115">`PRIMARY` und `Arch1` sind normale Dateigruppen, die keine FILESTREAM-Daten enthalten können.</span><span class="sxs-lookup"><span data-stu-id="19249-115">`PRIMARY` and `Arch1` are regular filegroups that cannot contain FILESTREAM data.</span></span> <span data-ttu-id="19249-116">`FileStreamGroup1` ist die `FILESTREAM` -Dateigruppe.</span><span class="sxs-lookup"><span data-stu-id="19249-116">`FileStreamGroup1` is the `FILESTREAM` filegroup.</span></span>  
  
```sql  
CREATE DATABASE Archive   
ON  
PRIMARY ( NAME = Arch1,  
    FILENAME = 'c:\data\archdat1.mdf'),  
FILEGROUP FileStreamGroup1 CONTAINS FILESTREAM( NAME = Arch3,  
    FILENAME = 'c:\data\filestream1')  
LOG ON  ( NAME = Archlog1,  
    FILENAME = 'c:\data\archlog1.ldf')  
GO  
```  
  
 <span data-ttu-id="19249-117">Bei einer `FILESTREAM` -Dateigruppe verweist `FILENAME` auf einen Pfad.</span><span class="sxs-lookup"><span data-stu-id="19249-117">For a `FILESTREAM` filegroup, `FILENAME` refers to a path.</span></span> <span data-ttu-id="19249-118">Der Pfad muss bis zum letzten Ordner vorhanden sein, und der letzte Ordner darf nicht vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="19249-118">The path up to the last folder must exist, and the last folder must not exist.</span></span> <span data-ttu-id="19249-119">In diesem Beispiel muss `c:\data` vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="19249-119">In this example, `c:\data` must exist.</span></span> <span data-ttu-id="19249-120">Der Unterordner `filestream1` darf beim Ausführen der `CREATE DATABASE` -Anweisung jedoch nicht vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="19249-120">However, the `filestream1` subfolder cannot exist when you execute the `CREATE DATABASE` statement.</span></span> <span data-ttu-id="19249-121">Weitere Informationen über diese Syntax finden Sie unter [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="19249-121">For more information about the syntax, see [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span></span>  
  
 <span data-ttu-id="19249-122">Nach der Ausführung des oben stehenden Beispiels sollten die Datei "filestream.hdr" und der Ordner "$FSLOG" im Ordner "c:\Data\filestream1" angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="19249-122">After you run the previous example, a filestream.hdr file and an $FSLOG folder appears in the c:\Data\filestream1 folder.</span></span> <span data-ttu-id="19249-123">Die Datei "filestream.hdr" ist eine FILESTREAM-Container-Headerdatei.</span><span class="sxs-lookup"><span data-stu-id="19249-123">The filestream.hdr file is a header file for the FILESTREAM container.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="19249-124">Die Datei "filestream.hdr" ist eine wichtige Systemdatei.</span><span class="sxs-lookup"><span data-stu-id="19249-124">The filestream.hdr file is an important system file.</span></span> <span data-ttu-id="19249-125">Sie enthält FILESTREAM-Headerinformationen.</span><span class="sxs-lookup"><span data-stu-id="19249-125">It contains FILESTREAM header information.</span></span> <span data-ttu-id="19249-126">Diese Datei darf nicht entfernt oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="19249-126">Do not remove or modify this file.</span></span>  
  
 <span data-ttu-id="19249-127">Bei vorhandenen Datenbanken können Sie eine FILESTREAM-Dateigruppe mit der [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) -Anweisung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="19249-127">For existing databases, you can use the [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) statement to add a FILESTREAM filegroup.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19249-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="19249-128">See Also</span></span>  
 <span data-ttu-id="19249-129">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="19249-129">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 [<span data-ttu-id="19249-130">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="19249-130">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
  
