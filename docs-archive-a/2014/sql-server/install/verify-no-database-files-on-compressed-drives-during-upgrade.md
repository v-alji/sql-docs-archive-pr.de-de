---
title: Überprüfen, ob während des Upgradevorgangs keine Datenbankdateien auf komprimierten Laufwerken Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- compressed drives [SQL Server]
ms.assetid: 63be6853-c54a-42b2-ae1a-db2175f1d28e
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 9c04f7890ba8d8efe64afaf11b922af156c5de46
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609019"
---
# <a name="verify-that-no-database-files-are-on-compressed-drives-during-the-upgrade-process"></a><span data-ttu-id="1d610-102">Vergewissern Sie sich, dass sich während des Upgradevorgangs keine Datenbankdateien auf komprimierten Laufwerken befinden</span><span class="sxs-lookup"><span data-stu-id="1d610-102">Verify that no database files are on compressed drives during the upgrade process</span></span>
  <span data-ttu-id="1d610-103">Der Upgrade Advisor hat Datenbankdateien auf einem komprimierten Laufwerk erkannt.</span><span class="sxs-lookup"><span data-stu-id="1d610-103">Upgrade Advisor detected database files on a compressed drive.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="1d610-104">kann Datenbanken auf komprimierten Laufwerken nicht erstellen oder aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="1d610-104">cannot create or upgrade databases on compressed drives.</span></span>  
  
## <a name="component"></a><span data-ttu-id="1d610-105">Komponente</span><span class="sxs-lookup"><span data-stu-id="1d610-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="1d610-106">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="1d610-106">Corrective Action</span></span>  
 <span data-ttu-id="1d610-107">Wenn Sie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installieren, wählen Sie ein unkomprimiertes Laufwerk für Systemdatenbanken aus, und stellen Sie sicher, dass sich die zu aktualisierenden Datenbanken nicht auf komprimierten Laufwerken befinden.</span><span class="sxs-lookup"><span data-stu-id="1d610-107">When you install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], select an uncompressed drive for system databases and verify that databases to be upgraded are not on compressed drives.</span></span> <span data-ttu-id="1d610-108">Sie müssen allerdings beachten, dass Sie nach dem Aktualisieren der Datenbank schreibgeschützte Datenbanken und schreibgeschützte sekundäre Dateigruppen in einem komprimierten NTFS-Dateisystem speichern können.</span><span class="sxs-lookup"><span data-stu-id="1d610-108">However, note that after the database has been upgraded, you can put read-only databases and read-only secondary filegroups on an NTFS compressed file system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d610-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1d610-109">See Also</span></span>  
 <span data-ttu-id="1d610-110">[Datenbank-Engine Upgradeprobleme](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="1d610-110">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="1d610-111">SQL Server 2014 Upgrade Advisor &#91;neuen&#93;</span><span class="sxs-lookup"><span data-stu-id="1d610-111">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
