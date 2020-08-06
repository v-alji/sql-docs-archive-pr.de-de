---
title: Sicherungsdateien müssen sich auf separaten Geräten aus den Datenbankdateien befinden | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 7039bebb-1f25-4cf3-81f1-393dfb78da12
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: d5eff9cb3139e1e1043f99ba63d11160b1010c27
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701900"
---
# <a name="backup-files-must-be-on-separate-devices-from-the-database-files"></a><span data-ttu-id="c8736-102">Sicherungsdateien und Datenbankdateien müssen auf separaten Medien gespeichert sein</span><span class="sxs-lookup"><span data-stu-id="c8736-102">Backup Files Must Be on Separate Devices from the Database Files</span></span>
  <span data-ttu-id="c8736-103">Diese Regel überprüft, ob Datenbankdateien und Sicherungsdateien auf separaten Medien gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="c8736-103">This rule checks whether database files are on devices separate from the backup files.</span></span> <span data-ttu-id="c8736-104">Wenn sich Datenbankdateien und Sicherungsdateien auf demselben Medium befinden und ein Fehler auftritt, stehen die Datenbank und die Sicherungen nicht mehr zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="c8736-104">If database files and backup files are on the same device and the device fails, the database and backups will be unavailable.</span></span> <span data-ttu-id="c8736-105">Wenn Sie die Daten und die Sicherungen auf separaten Medien speichern, wird auch die E/A-Leistung für die produktive Nutzung der Datenbank sowie für das Schreiben von Sicherungen optimiert.</span><span class="sxs-lookup"><span data-stu-id="c8736-105">Also, putting the database and backup files on the separate devices optimizes the I/O performance for both the production use of the database and the writing of backups.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="c8736-106">Empfehlungen zu Best Practices</span><span class="sxs-lookup"><span data-stu-id="c8736-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="c8736-107">Es empfiehlt sich dringend, Datenbank und Sicherungen auf separaten Sicherungsmedien zu speichern.</span><span class="sxs-lookup"><span data-stu-id="c8736-107">We strongly recommend that you put the database and backups on separate backup devices.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c8736-108">Diese Richtlinie kann separate physische Geräte nicht durch Einbindungspunkte erkennen.</span><span class="sxs-lookup"><span data-stu-id="c8736-108">This policy cannot detect separate physical devices through mount points.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="c8736-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c8736-109">For More Information</span></span>  
 [<span data-ttu-id="c8736-110">Sicherungsmedien &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c8736-110">Backup Devices &#40;SQL Server&#41;</span></span>](../relational-databases/backup-restore/backup-devices-sql-server.md)  
  
 [<span data-ttu-id="c8736-111">Sichern und Wiederherstellen von SQL Server-Datenbanken</span><span class="sxs-lookup"><span data-stu-id="c8736-111">Back Up and Restore of SQL Server Databases</span></span>](../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md)  
  
## <a name="see-also"></a><span data-ttu-id="c8736-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c8736-112">See Also</span></span>  
 [<span data-ttu-id="c8736-113">Überwachen und Erzwingen von Best Practices mit der richtlinienbasierten Verwaltung</span><span class="sxs-lookup"><span data-stu-id="c8736-113">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](../relational-databases/policy-based-management/monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
