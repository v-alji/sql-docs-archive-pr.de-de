---
title: Kopieren von Datenbanken auf andere Server | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- servers [SQL Server], copying databases between
- bulk exporting [SQL Server], between servers
- database copying [SQL Server]
- migrating databases [SQL Server]
- moving databases
- copying databases
- bulk importing [SQL Server], between servers
ms.assetid: 978406d6-a3c8-4902-b1f4-4ced75234be5
author: stevestein
ms.author: sstein
ms.openlocfilehash: bcde6185f25129596b4be7a150d4ee230c54c1a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699770"
---
# <a name="copy-databases-to-other-servers"></a><span data-ttu-id="4ea10-102">Kopieren von Datenbanken auf andere Server</span><span class="sxs-lookup"><span data-stu-id="4ea10-102">Copy Databases to Other Servers</span></span>
  <span data-ttu-id="4ea10-103">Es ist manchmal hilfreich, eine Datenbank von einem Computer zum anderen zu kopieren, z. B. für Tests, das Überprüfen von Konsistenz, das Entwickeln von Software, das Ausführen von Berichten, das Erstellen einer Spiegeldatenbank oder eventuell zum Verfügbarmachen der Datenbank für externe Niederlassungen.</span><span class="sxs-lookup"><span data-stu-id="4ea10-103">It is sometimes useful to copy a database from one computer to another, whether for testing, checking consistency, developing software, running reports, creating a mirror database, or, possibly, to make the database available to remote-branch operations.</span></span>  
  
 <span data-ttu-id="4ea10-104">Es gibt mehrere Möglichkeiten, eine Datenbank zu kopieren:</span><span class="sxs-lookup"><span data-stu-id="4ea10-104">There are several ways to copy a database:</span></span>  
  
-   <span data-ttu-id="4ea10-105">Verwenden des Assistenten zum Kopieren von Datenbanken</span><span class="sxs-lookup"><span data-stu-id="4ea10-105">Using the Copy Database Wizard</span></span>  
  
     <span data-ttu-id="4ea10-106">Sie können den Assistenten zum Kopieren von Datenbanken verwenden, um Datenbanken zwischen Servern zu kopieren oder zu verschieben oder um eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbank auf eine höhere Version zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="4ea10-106">You can use the Copy Database Wizard to copy or move databases between servers or to upgrade a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database to a later version.</span></span> <span data-ttu-id="4ea10-107">Weitere Informationen finden Sie unter [Use the Copy Database Wizard](use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="4ea10-107">For more information, see [Use the Copy Database Wizard](use-the-copy-database-wizard.md).</span></span>  
  
-   <span data-ttu-id="4ea10-108">Wiederherstellen einer Datenbanksicherung</span><span class="sxs-lookup"><span data-stu-id="4ea10-108">Restoring a database backup</span></span>  
  
     <span data-ttu-id="4ea10-109">Mit den [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen BACKUP und RESTORE können Sie eine ganze Datenbank kopieren.</span><span class="sxs-lookup"><span data-stu-id="4ea10-109">To copy an entire database, you can use the BACKUP and RESTORE [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="4ea10-110">Typischerweise wird das Wiederherstellen einer vollständigen Datenbanksicherung aus vielen Gründen zum Kopieren einer Datenbank von einem Computer auf einen anderen verwendet.</span><span class="sxs-lookup"><span data-stu-id="4ea10-110">Typically, restoring a full backup of a database is used to copy the database from one computer to another for a variety of reasons.</span></span> <span data-ttu-id="4ea10-111">Weitere Informationen zum Sichern und Wiederherstellen zum Zweck des Kopierens einer Datenbank finden Sie unter [Kopieren von Datenbanken durch Sichern und Wiederherstellen](copy-databases-with-backup-and-restore.md).</span><span class="sxs-lookup"><span data-stu-id="4ea10-111">For information on using backup and restore to copy a database, see [Copy Databases with Backup and Restore](copy-databases-with-backup-and-restore.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4ea10-112">Zum Einrichten einer Spiegeldatenbank für die Datenbankspiegelung müssen Sie die Datenbank mithilfe von RESTORE DATABASE *<Datenbankname>* WITH NORECOVERY auf dem Spiegelserver wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="4ea10-112">To set up a mirror database for database mirroring, you must restore the database onto the mirror server by using RESTORE DATABASE *<database_name>* WITH NORECOVERY.</span></span> <span data-ttu-id="4ea10-113">Weitere Informationen finden Sie unter [Vorbereiten einer Spiegeldatenbank auf die Spiegelung &#40;SQL Server&#41;](../../database-engine/database-mirroring/prepare-a-mirror-database-for-mirroring-sql-server.md)verwendet.</span><span class="sxs-lookup"><span data-stu-id="4ea10-113">For more information, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
-   <span data-ttu-id="4ea10-114">Verwenden des Assistenten zum Generieren von Skripts, um Datenbanken zu veröffentlichen</span><span class="sxs-lookup"><span data-stu-id="4ea10-114">Using the Generate Scripts Wizard to publish databases</span></span>  
  
     <span data-ttu-id="4ea10-115">Sie können mit dem Assistenten zum Generieren von Skripts eine Datenbank von einem lokalen Computer auf einen Webhostinganbieter übertragen.</span><span class="sxs-lookup"><span data-stu-id="4ea10-115">You can use the Generate Scripts Wizard to transfer a database from a local computer to a Web hosting provider.</span></span> <span data-ttu-id="4ea10-116">Weitere Informationen finden Sie unter [Assistent zum Generieren und Veröffentlichen von Skripts](../scripting/generate-and-publish-scripts-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="4ea10-116">For more information, see [Generate and Publish Scripts Wizard](../scripting/generate-and-publish-scripts-wizard.md).</span></span>  
  
  
