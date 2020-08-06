---
title: Veraltete Sicherung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 307a4ad0-675a-4f97-9a3c-cedd61bdfae5
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c6a944b08b15d591a9bbce47a0c0c6a8de3eb54a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619772"
---
# <a name="outdated-backup"></a><span data-ttu-id="a8a4d-102">Obsolete Sicherung</span><span class="sxs-lookup"><span data-stu-id="a8a4d-102">Outdated Backup</span></span>
  <span data-ttu-id="a8a4d-103">Diese Regel überprüft, ob aktuelle Sicherungen einer Datenbank existieren.</span><span class="sxs-lookup"><span data-stu-id="a8a4d-103">This rule checks that a database has recent backups.</span></span> <span data-ttu-id="a8a4d-104">Die Planung regelmäßiger Sicherungen ist wichtig, um die Datenbanken vor Datenverlust aufgrund vieler verschiedener Fehler zu schützen.</span><span class="sxs-lookup"><span data-stu-id="a8a4d-104">Scheduling regular backups is important for protecting your databases against data loss from many different failures.</span></span> <span data-ttu-id="a8a4d-105">Die geeignete Häufigkeit der Datensicherung hängt vom Wiederherstellungsmodell der Datenbank und von den Unternehmensrichtlinien hinsichtlich potenziellen Datenverlusts ab sowie davon, wie oft die Datenbank aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="a8a4d-105">The appropriate frequency for backing up data depends on the recovery model of the database, on business requirements about potential data loss, and on how frequently the database is updated.</span></span> <span data-ttu-id="a8a4d-106">Wird die Datenbank häufig aktualisiert, steigt die Gefahr des Datenverlusts zwischen den Sicherungsvorgängen stark an.</span><span class="sxs-lookup"><span data-stu-id="a8a4d-106">In a frequently updated database, the work-loss exposure increases fairly quickly between backups.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="a8a4d-107">Empfehlungen zu Best Practices</span><span class="sxs-lookup"><span data-stu-id="a8a4d-107">Best Practices Recommendations</span></span>  
 <span data-ttu-id="a8a4d-108">Wir empfehlen, dass Sie Sicherungen häufig genug ausführen, um Datenbanken vor Datenverlust zu schützen.</span><span class="sxs-lookup"><span data-stu-id="a8a4d-108">We recommend that you perform backups frequently enough to protect databases against data loss.</span></span>  
  
 <span data-ttu-id="a8a4d-109">Sowohl das einfache als auch das vollständige Wiederherstellungsmodell erfordern Datensicherungen.</span><span class="sxs-lookup"><span data-stu-id="a8a4d-109">The simple recovery model and full recovery model both require data backups.</span></span> <span data-ttu-id="a8a4d-110">In beiden Wiederherstellungsmodellen können Sie jede vollständige Sicherung mit differenziellen Sicherungen ergänzen, um das Risiko eines Datenverlusts zu verringern.</span><span class="sxs-lookup"><span data-stu-id="a8a4d-110">For either recovery model, you can supplement your full backups with differential backups to efficiently reduce the risk of data loss.</span></span>  
  
 <span data-ttu-id="a8a4d-111">Für Datenbanken, die das vollständige Wiederherstellungsmodell verwenden, empfehlen wir häufige Protokollsicherungen.</span><span class="sxs-lookup"><span data-stu-id="a8a4d-111">For a database that uses the full recovery model, we recommend that you take frequent log backups.</span></span> <span data-ttu-id="a8a4d-112">Von einer Produktionsdatenbank mit sehr wichtigen Daten sollten Protokollsicherungen in der Regel alle 1 bis 15 Minuten erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="a8a4d-112">For a production database that contains very important data, log backups would typically be taken every one to fifteen minutes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a8a4d-113">Die empfohlene Methode zur Planung von Sicherungen ist ein Datenbankwartungsplan.</span><span class="sxs-lookup"><span data-stu-id="a8a4d-113">The recommended method for scheduling backups is a database maintenance plan.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="a8a4d-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a8a4d-114">For More Information</span></span>  
 [<span data-ttu-id="a8a4d-115">Sichern und Wiederherstellen von Systemdatenbanken &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a8a4d-115">Back Up and Restore of System Databases &#40;SQL Server&#41;</span></span>](../backup-restore/back-up-and-restore-of-system-databases-sql-server.md)  
  
 [<span data-ttu-id="a8a4d-116">Wiederherstellungsmodelle &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a8a4d-116">Recovery Models &#40;SQL Server&#41;</span></span>](../backup-restore/recovery-models-sql-server.md)  
  
 [<span data-ttu-id="a8a4d-117">Erstellen einer differenziellen Datenbanksicherung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a8a4d-117">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](../backup-restore/create-a-differential-database-backup-sql-server.md)  
  
 [<span data-ttu-id="a8a4d-118">Erstellen einer vollständigen Datenbanksicherung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a8a4d-118">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](../backup-restore/create-a-full-database-backup-sql-server.md)  
  
 [<span data-ttu-id="a8a4d-119">Wartungspläne</span><span class="sxs-lookup"><span data-stu-id="a8a4d-119">Maintenance Plans</span></span>](../maintenance-plans/maintenance-plans.md)  
  
 [<span data-ttu-id="a8a4d-120">Transaktionsprotokollsicherungen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a8a4d-120">Transaction Log Backups &#40;SQL Server&#41;</span></span>](../backup-restore/transaction-log-backups-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="a8a4d-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a8a4d-121">See Also</span></span>  
 [<span data-ttu-id="a8a4d-122">Überwachen und Erzwingen von Best Practices mit der richtlinienbasierten Verwaltung</span><span class="sxs-lookup"><span data-stu-id="a8a4d-122">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
