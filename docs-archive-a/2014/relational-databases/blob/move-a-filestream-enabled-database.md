---
title: Verschieben einer FILESTREAM-aktivierten Datenbank | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], moving a FILESTREAM-enabled database
ms.assetid: dd4d270d-9283-431a-aa6b-e571fced1893
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 79740ee86a89566113650865e3fd6ec54c7cb918
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695730"
---
# <a name="move-a-filestream-enabled-database"></a><span data-ttu-id="cbcc3-102">Verschieben einer FILESTREAM-aktivierten Datenbank</span><span class="sxs-lookup"><span data-stu-id="cbcc3-102">Move a FILESTREAM-Enabled Database</span></span>
  <span data-ttu-id="cbcc3-103">In diesem Thema wird das Verschieben einer FILESTREAM-aktivierten Datenbank veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="cbcc3-103">This topic shows how to move a FILESTREAM-enabled database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cbcc3-104">Für die Beispiele in diesem Thema benötigen Sie die Datenbank „Archive“, die unter [Erstellen einer FILESTREAM-aktivierten Datenbank](create-a-filestream-enabled-database.md)erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="cbcc3-104">The examples in this topic require the Archive database that is created in [Create a FILESTREAM-Enabled Database](create-a-filestream-enabled-database.md).</span></span>  
  
### <a name="to-move-a-filestream-enabled-database"></a><span data-ttu-id="cbcc3-105">So verschieben Sie eine FILESTREAM-aktivierte Datenbank</span><span class="sxs-lookup"><span data-stu-id="cbcc3-105">To move a FILESTREAM-enabled database</span></span>  
  
1.  <span data-ttu-id="cbcc3-106">Klicken Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]auf **Neue Abfrage** , um den Abfrage-Editor zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="cbcc3-106">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], click **New Query** to open the Query Editor.</span></span>  
  
2.  <span data-ttu-id="cbcc3-107">Kopieren Sie das folgende [!INCLUDE[tsql](../../includes/tsql-md.md)] -Skript in den Abfrage-Editor, und klicken Sie dann auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="cbcc3-107">Copy the following [!INCLUDE[tsql](../../includes/tsql-md.md)] script into the Query Editor, and then click **Execute**.</span></span> <span data-ttu-id="cbcc3-108">Mit diesem Skript wird der Speicherort der physischen Datenbankdateien angezeigt, die von der FILESTREAM-Datenbank verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cbcc3-108">This script displays the location of the physical database files that the FILESTREAM database uses.</span></span>  
  
    ```sql  
    USE Archive  
    GO  
    SELECT type_desc, name, physical_name from sys.database_files  
    ```  
  
3.  <span data-ttu-id="cbcc3-109">Kopieren Sie das folgende [!INCLUDE[tsql](../../includes/tsql-md.md)] -Skript in den Abfrage-Editor, und klicken Sie dann auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="cbcc3-109">Copy the following [!INCLUDE[tsql](../../includes/tsql-md.md)] script into the Query Editor, and then click **Execute**.</span></span> <span data-ttu-id="cbcc3-110">Mit diesem Code wird die `Archive` -Datenbank offline geschaltet.</span><span class="sxs-lookup"><span data-stu-id="cbcc3-110">This code takes the `Archive` database offline.</span></span>  
  
    ```sql  
    USE master  
    EXEC sp_detach_db Archive  
    GO  
    ```  
  
4.  <span data-ttu-id="cbcc3-111">Erstellen Sie den Ordner `C:\moved_location`, und verschieben Sie dann die in Schritt 2 aufgeführten Dateien und Ordner in diesen Ordner.</span><span class="sxs-lookup"><span data-stu-id="cbcc3-111">Create the folder `C:\moved_location`, and then move the files and folders that are listed in step 2 into it.</span></span>  
  
5.  <span data-ttu-id="cbcc3-112">Kopieren Sie das folgende [!INCLUDE[tsql](../../includes/tsql-md.md)] -Skript in den Abfrage-Editor, und klicken Sie dann auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="cbcc3-112">Copy the following [!INCLUDE[tsql](../../includes/tsql-md.md)] script into the Query Editor, and then click **Execute**.</span></span> <span data-ttu-id="cbcc3-113">Mit diesem Skript wird die `Archive` -Datenbank online geschaltet.</span><span class="sxs-lookup"><span data-stu-id="cbcc3-113">This script sets the `Archive` database online.</span></span>  
  
    ```sql  
    CREATE DATABASE Archive ON  
    PRIMARY ( NAME = Arch1,  
        FILENAME = 'c:\moved_location\archdat1.mdf'),  
    FILEGROUP FileStreamGroup1 CONTAINS FILESTREAM( NAME = Arch3,  
        FILENAME = 'c:\moved_location\filestream1')  
    LOG ON  ( NAME = Archlog1,  
        FILENAME = 'c:\moved_location\archlog1.ldf')  
    FOR ATTACH  
    GO  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="cbcc3-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cbcc3-114">See Also</span></span>  
 [<span data-ttu-id="cbcc3-115">sp_detach_db &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cbcc3-115">sp_detach_db &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-detach-db-transact-sql)  
  
  
