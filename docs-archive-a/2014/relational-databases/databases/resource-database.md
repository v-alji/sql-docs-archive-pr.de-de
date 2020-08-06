---
title: Ressourcendatenbank | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- system objects [SQL Server]
- read-only databases
- mssqlsystemresource.mdf file
- Resource database [SQL Server]
ms.assetid: d592b2b4-bc36-4eb9-9385-8fe4dff0dced
author: stevestein
ms.author: sstein
ms.openlocfilehash: cca2f9e1ff6069a608beb1df1880b37e15f4e869
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617094"
---
# <a name="resource-database"></a><span data-ttu-id="37bdc-102">Ressourcendatenbank</span><span class="sxs-lookup"><span data-stu-id="37bdc-102">Resource Database</span></span>
  <span data-ttu-id="37bdc-103">Die Ressourcendatenbank ist eine schreibgeschützte Datenbank, die alle Systemobjekte enthält, die in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="37bdc-103">The Resource database is a read-only database that contains all the system objects that are included with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="37bdc-104">-Systemobjekte, z.B. sys.objects, werden physisch in der Ressourcendatenbank persistent gespeichert, logisch jedoch im sys-Schema jeder Datenbank angezeigt.</span><span class="sxs-lookup"><span data-stu-id="37bdc-104">system objects, such as sys.objects, are physically persisted in the Resource database, but they logically appear in the sys schema of every database.</span></span> <span data-ttu-id="37bdc-105">Die Ressourcendatenbank enthält keine Benutzerdaten oder Benutzermetadaten.</span><span class="sxs-lookup"><span data-stu-id="37bdc-105">The Resource database does not contain user data or user metadata.</span></span>  
  
 <span data-ttu-id="37bdc-106">Durch die Ressourcendatenbank wird das Upgrade auf eine neue Version von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] zu einem einfacheren und schnelleren Vorgang.</span><span class="sxs-lookup"><span data-stu-id="37bdc-106">The Resource database makes upgrading to a new version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] an easier and faster procedure.</span></span> <span data-ttu-id="37bdc-107">In früheren Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]mussten zum Aktualisieren Systemobjekte gelöscht und erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="37bdc-107">In earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], upgrading required dropping and creating system objects.</span></span> <span data-ttu-id="37bdc-108">Da die Ressourcendatenbankdatei alle Systemobjekte enthält, wird ein Upgrade nun durch Kopieren der Ressourcendatenbankdatei auf den lokalen Server durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="37bdc-108">Because the Resource database file contains all system objects, an upgrade is now accomplished simply by copying the single Resource database file to the local server.</span></span>  
  
## <a name="physical-properties-of-resource"></a><span data-ttu-id="37bdc-109">Physische Eigenschaften der Resource-Datenbank</span><span class="sxs-lookup"><span data-stu-id="37bdc-109">Physical Properties of Resource</span></span>  
 <span data-ttu-id="37bdc-110">Die physischen Dateinamen der Ressourcendatenbank sind mssqlsystemresource.mdf und mssqlsystemresource.ldf.</span><span class="sxs-lookup"><span data-stu-id="37bdc-110">The physical file names of the Resource database are mssqlsystemresource.mdf and mssqlsystemresource.ldf.</span></span> <span data-ttu-id="37bdc-111">Diese Dateien befinden sich unter \<*drive*>:\Programme\Microsoft SQL Server\MSSQL\<version>.\<*instance_name*>\MSSQL\Binn\ und dürfen nicht verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="37bdc-111">These files are located in \<*drive*>:\Program Files\Microsoft SQL Server\MSSQL\<version>.\<*instance_name*>\MSSQL\Binn\ and should not be moved.</span></span> <span data-ttu-id="37bdc-112">Jede Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] besitzt eine und nur genau eine zugeordnete Datei "mssqlsystemresource.mdf"; diese Datei wird für Instanzen nicht freigegeben.</span><span class="sxs-lookup"><span data-stu-id="37bdc-112">Each instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has one and only one associated mssqlsystemresource.mdf file, and instances do not share this file.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="37bdc-113">Upgrades und Servicepacks bieten manchmal auch eine neue Ressourcendatenbank, die im Ordner BINN installiert wird.</span><span class="sxs-lookup"><span data-stu-id="37bdc-113">Upgrades and service packs sometimes provide a new resource database which is installed to the BINN folder.</span></span> <span data-ttu-id="37bdc-114">Ändern des Speicherorts der Ressourcendatenbank wird nicht unterstützt oder empfohlen.</span><span class="sxs-lookup"><span data-stu-id="37bdc-114">Changing the location of the resource database is not supported or recommended.</span></span>  
  
## <a name="backing-up-and-restoring-the-resource-database"></a><span data-ttu-id="37bdc-115">Sichern und Wiederherstellen der Resource-Datenbank</span><span class="sxs-lookup"><span data-stu-id="37bdc-115">Backing Up and Restoring the Resource Database</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="37bdc-116">kann die Ressourcendatenbank nicht sichern.</span><span class="sxs-lookup"><span data-stu-id="37bdc-116">cannot back up the Resource database.</span></span> <span data-ttu-id="37bdc-117">Sie können eine eigene dateigestützte oder datenträgergestützte Sicherung der Datei erstellen, indem Sie die Datei mssqlsystemresource.mdf als Binärdatei (EXE) anstatt als Datenbankdatei behandeln. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] kann jedoch nicht zum Wiederherstellen der Sicherungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="37bdc-117">You can perform your own file-based or a disk-based backup by treating the mssqlsystemresource.mdf file as if it were a binary (.EXE) file, rather than a database file, but you cannot use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to restore your backups.</span></span> <span data-ttu-id="37bdc-118">Die Wiederherstellung einer Sicherungskopie von mssqlsystemresource.mdf kann nur manuell erfolgen. Achten Sie darauf, die aktuelle Ressourcendatenbank nicht durch eine veraltete oder potenziell unsichere Version zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="37bdc-118">Restoring a backup copy of mssqlsystemresource.mdf can only be done manually, and you must be careful not to overwrite the current Resource database with an out-of-date or potentially insecure version.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="37bdc-119">Nach dem Wiederherstellen einer Sicherung von mssqlsystemresource.mdf müssen Sie alle nachfolgenden Aktualisierungen erneut anwenden.</span><span class="sxs-lookup"><span data-stu-id="37bdc-119">After restoring a backup of mssqlsystemresource.mdf, you must reapply any subsequent updates.</span></span>  
  
## <a name="accessing-the-resource-database"></a><span data-ttu-id="37bdc-120">Zugriff auf die Resource-Datenbank</span><span class="sxs-lookup"><span data-stu-id="37bdc-120">Accessing the Resource Database</span></span>  
 <span data-ttu-id="37bdc-121">Die Ressourcendatenbank sollte nur von einem Microsoft Support Services-Experten oder unter dessen Anleitung geändert werden.</span><span class="sxs-lookup"><span data-stu-id="37bdc-121">The Resource database should only be modified by or at the direction of a Microsoft Customer Support Services (CSS) specialist.</span></span> <span data-ttu-id="37bdc-122">Die ID der Ressourcendatenbank ist immer 32767.</span><span class="sxs-lookup"><span data-stu-id="37bdc-122">The ID of the Resource database is always 32767.</span></span> <span data-ttu-id="37bdc-123">Andere wichtige Werte, die der Ressourcendatenbank zugeordnet sind, sind die Versionsnummer und der Zeitpunkt der letzten Aktualisierung der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="37bdc-123">Other important values associated with the Resource database are the version number and the last time that the database was updated.</span></span>  
  
 <span data-ttu-id="37bdc-124">**Verwenden Sie zum Ermitteln der Versionsnummer der** Resource **-Datenbank die folgende Anweisung**:</span><span class="sxs-lookup"><span data-stu-id="37bdc-124">**To determine the version number of the** Resource **database, use**:</span></span>  
  
```  
SELECT SERVERPROPERTY('ResourceVersion');  
GO  
```  
  
 <span data-ttu-id="37bdc-125">**Verwenden Sie zum Ermitteln, wann die** Resource **-Datenbank zuletzt aktualisiert wurde, die folgende Anweisung**:</span><span class="sxs-lookup"><span data-stu-id="37bdc-125">**To determine when the** Resource **database was last updated, use**:</span></span>  
  
```  
SELECT SERVERPROPERTY('ResourceLastUpdateDateTime');  
GO  
```  
  
 <span data-ttu-id="37bdc-126">**Wenn Sie auf die SQL-Definitionen von Systemobjekten zugreifen möchten, verwenden Sie die OBJECT_DEFINITION-Funktion:**</span><span class="sxs-lookup"><span data-stu-id="37bdc-126">**To access SQL definitions of system objects, use the OBJECT_DEFINITION function:**</span></span>  
  
```  
SELECT OBJECT_DEFINITION(OBJECT_ID('sys.objects'));  
GO  
```  
  
## <a name="related-content"></a><span data-ttu-id="37bdc-127">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="37bdc-127">Related Content</span></span>  
 [<span data-ttu-id="37bdc-128">Systemdatenbanken</span><span class="sxs-lookup"><span data-stu-id="37bdc-128">System Databases</span></span>](system-databases.md)  
  
 [<span data-ttu-id="37bdc-129">Diagnoseverbindung für Datenbankadministratoren</span><span class="sxs-lookup"><span data-stu-id="37bdc-129">Diagnostic Connection for Database Administrators</span></span>](../../database-engine/configure-windows/diagnostic-connection-for-database-administrators.md)  
  
 [<span data-ttu-id="37bdc-130">OBJECT_DEFINITION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="37bdc-130">OBJECT_DEFINITION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/object-definition-transact-sql)  
  
 [<span data-ttu-id="37bdc-131">SERVERPROPERTY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="37bdc-131">SERVERPROPERTY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/serverproperty-transact-sql)  
  
 [<span data-ttu-id="37bdc-132">Starten von SQL Server im Einzelbenutzermodus</span><span class="sxs-lookup"><span data-stu-id="37bdc-132">Start SQL Server in Single-User Mode</span></span>](../../database-engine/configure-windows/start-sql-server-in-single-user-mode.md)  
  
  
