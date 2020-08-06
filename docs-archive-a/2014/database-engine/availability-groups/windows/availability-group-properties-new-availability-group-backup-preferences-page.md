---
title: 'Eigenschaften der Verfügbarkeits Gruppe: neue Verfügbarkeits Gruppe (Seite Sicherungs Einstellungen) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroupproperties.backuppreferences.f1
helpviewer_keywords:
- read-only routing
ms.assetid: 65fff22d-5963-4a8c-8b31-fe9ab247a03e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7914d4b1d7af06bcaf4f3fd05a260138e3edf5fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608866"
---
# <a name="availability-group-properties-new-availability-group-backup-preferences-page"></a><span data-ttu-id="b8a4c-102">Eigenschaften von Verfügbarkeitsgruppen: Neue Verfügbarkeitsgruppe (Seite Sicherungseinstellungen)</span><span class="sxs-lookup"><span data-stu-id="b8a4c-102">Availability Group Properties: New Availability Group (Backup Preferences Page)</span></span>
  <span data-ttu-id="b8a4c-103">Verwenden Sie dieses Dialogfeld, um die Sicherungseinstellungen der ausgewählten Verfügbarkeitsgruppe anzuzeigen und zu ändern.</span><span class="sxs-lookup"><span data-stu-id="b8a4c-103">Use this dialog box to view and change the backup preferences of the selected availability group.</span></span>  
  
 <span data-ttu-id="b8a4c-104">**So zeigen Sie Verfügbarkeitsgruppeneigenschaften an**</span><span class="sxs-lookup"><span data-stu-id="b8a4c-104">**To view availability group properties**</span></span>  
  
-   [<span data-ttu-id="b8a4c-105">Anzeigen von Verfügbarkeitsgruppeneigenschaften &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b8a4c-105">View Availability Group Properties &#40;SQL Server&#41;</span></span>](view-availability-group-properties-sql-server.md)  
  
-   [<span data-ttu-id="b8a4c-106">Verwenden des AlwaysOn-Dashboards &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="b8a4c-106">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
## <a name="where-should-backups-occur"></a><span data-ttu-id="b8a4c-107">Wo sollten Sicherungen erfolgen?</span><span class="sxs-lookup"><span data-stu-id="b8a4c-107">Where should backups occur?</span></span>  
 <span data-ttu-id="b8a4c-108">**Sekundär bevorzugen**</span><span class="sxs-lookup"><span data-stu-id="b8a4c-108">**Prefer Secondary**</span></span>  
 <span data-ttu-id="b8a4c-109">Gibt an, dass Sicherungen auf einem sekundären Replikat erfolgen müssen, außer wenn es sich beim primären Replikat um das einzige Onlinereplikat handelt.</span><span class="sxs-lookup"><span data-stu-id="b8a4c-109">Specifies that backups should occur on a secondary replica except when the primary replica is the only replica online.</span></span> <span data-ttu-id="b8a4c-110">In diesem Fall muss die Sicherung auf dem primären Replikat erfolgen.</span><span class="sxs-lookup"><span data-stu-id="b8a4c-110">In that case, the backup should occur on the primary replica.</span></span> <span data-ttu-id="b8a4c-111">Dies ist die Standardoption.</span><span class="sxs-lookup"><span data-stu-id="b8a4c-111">This is the default option.</span></span>  
  
 <span data-ttu-id="b8a4c-112">**Nur sekundär**</span><span class="sxs-lookup"><span data-stu-id="b8a4c-112">**Secondary only**</span></span>  
 <span data-ttu-id="b8a4c-113">Gibt an, dass Sicherungen nie auf dem primären Replikat ausgeführt werden dürfen.</span><span class="sxs-lookup"><span data-stu-id="b8a4c-113">Specifies that backups should never be performed on the primary replica.</span></span> <span data-ttu-id="b8a4c-114">Wenn es sich beim primären Replikat um das einzige Onlinereplikat handelt, darf keine Sicherung erfolgen.</span><span class="sxs-lookup"><span data-stu-id="b8a4c-114">If the primary replica is the only replica online, the backup should not occur.</span></span>  
  
 <span data-ttu-id="b8a4c-115">**Primärer Server/verwaltete Instanz**</span><span class="sxs-lookup"><span data-stu-id="b8a4c-115">**Primary**</span></span>  
 <span data-ttu-id="b8a4c-116">Gibt an, dass die Sicherungen immer auf dem primären Replikat erfolgen müssen.</span><span class="sxs-lookup"><span data-stu-id="b8a4c-116">Specifies that the backups should always occur on the primary replica.</span></span> <span data-ttu-id="b8a4c-117">Diese Option ist hilfreich, wenn Sie Sicherungsfunktionen benötigen, z. B. das Erstellen differenzieller Sicherungen, die nicht unterstützt werden, wenn die Sicherung auf einem sekundären Replikat ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b8a4c-117">This option is useful if you need backup features, such as creating differential backups, that are not supported when backup is run on a secondary replica.</span></span>  
  
 <span data-ttu-id="b8a4c-118">**Beliebiges Replikat**</span><span class="sxs-lookup"><span data-stu-id="b8a4c-118">**Any Replica**</span></span>  
 <span data-ttu-id="b8a4c-119">Gibt an, dass Sicherungsaufträge die Rolle der Verfügbarkeitsreplikate ignorieren sollen, wenn sie das Replikat zum Durchführen der Sicherungen auswählen.</span><span class="sxs-lookup"><span data-stu-id="b8a4c-119">Specifies that you prefer that backup jobs ignore the role of the availability replicas when choosing the replica to perform backups.</span></span> <span data-ttu-id="b8a4c-120">Sicherungsaufträge können andere Faktoren auswerten, wie z. B. die Sicherungspriorität jedes Verfügbarkeitsreplikats in Verbindung mit seinem Betriebszustand und Verbindungsstatus.</span><span class="sxs-lookup"><span data-stu-id="b8a4c-120">Note backup jobs might evaluate other factors such as backup priority of each availability replica in combination with its operational state and connected state.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b8a4c-121">Die Einstellung "backup-preference" wird nicht erzwungen.</span><span class="sxs-lookup"><span data-stu-id="b8a4c-121">There is no enforcement of the backup-preference setting.</span></span> <span data-ttu-id="b8a4c-122">Die Interpretation dieser Einstellung hängt von der Logik ab, die Sie ggf. per Skript in Sicherungsaufträge für die Datenbanken in einer angegebenen Verfügbarkeitsgruppe integriert haben.</span><span class="sxs-lookup"><span data-stu-id="b8a4c-122">The interpretation of this preference depends on the logic, if any, that you script into back jobs for the databases in a given availability group.</span></span> <span data-ttu-id="b8a4c-123">Weitere Informationen finden Sie unter [aktive sekundäre Replikate: Sicherung auf sekundären Replikaten (AlwaysOn-Verfügbarkeitsgruppen)](active-secondaries-backup-on-secondary-replicas-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="b8a4c-123">For more information, see [Active Secondaries: Backup on Secondary Replicas (AlwaysOn Availability Groups)](active-secondaries-backup-on-secondary-replicas-always-on-availability-groups.md).</span></span>  
  
## <a name="replica-backup-priorities"></a><span data-ttu-id="b8a4c-124">Replikatssicherungsprioritäten</span><span class="sxs-lookup"><span data-stu-id="b8a4c-124">Replica backup priorities</span></span>  
 <span data-ttu-id="b8a4c-125">Dieses Raster enthält die aktuelle Sicherungspriorität aller Serverinstanzen, die ein Replikat für die Verfügbarkeitsgruppe hosten.</span><span class="sxs-lookup"><span data-stu-id="b8a4c-125">This grid displays the current backup priority of each server instance that hosts a replica for the availability group.</span></span> <span data-ttu-id="b8a4c-126">Verwenden Sie dieses Raster, um die Sicherungspriorität von Verfügbarkeitsreplikaten zu ändern.</span><span class="sxs-lookup"><span data-stu-id="b8a4c-126">Use this grid to change the backup priority of one or more availability replicas.</span></span>  
  
 <span data-ttu-id="b8a4c-127">**Serverinstanz**</span><span class="sxs-lookup"><span data-stu-id="b8a4c-127">**Server Instance**</span></span>  
 <span data-ttu-id="b8a4c-128">Der Name der Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , die das Verfügbarkeitsreplikat hostet.</span><span class="sxs-lookup"><span data-stu-id="b8a4c-128">The name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosts the availability replica.</span></span>  
  
 <span data-ttu-id="b8a4c-129">**Sicherungspriorität (niedrigste = 1, höchste = 100)**</span><span class="sxs-lookup"><span data-stu-id="b8a4c-129">**Backup Priority (Lowest=1, Highest=100)**</span></span>  
 <span data-ttu-id="b8a4c-130">Gibt die Priorität für die Ausführung von Sicherungen auf diesem Replikat in Relation zu den anderen Replikaten in derselben Verfügbarkeitsgruppe an.</span><span class="sxs-lookup"><span data-stu-id="b8a4c-130">Specifies your priority for performing backups on this replica relative to the other replicas in the same availability group.</span></span> <span data-ttu-id="b8a4c-131">Der Wert liegt im Bereich von 0 bis 100 und ist eine ganze Zahl.</span><span class="sxs-lookup"><span data-stu-id="b8a4c-131">The value is an integer in the range of 0..100.</span></span> <span data-ttu-id="b8a4c-132">1 gibt die niedrigste Priorität und 100 die höchste Priorität an.</span><span class="sxs-lookup"><span data-stu-id="b8a4c-132">1 indicates the lowest priority, and 100 indicates the highest priority.</span></span> <span data-ttu-id="b8a4c-133">Wenn **BACKUP_PRIORITY** 1 ist, würde das Verfügbarkeitsreplikat nur zum Ausführen von Sicherungen ausgewählt werden, wenn gerade keine höheren Prioritätsverfügbarkeitsreplikate verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="b8a4c-133">If **Backup Priority** = 1, the availability replica would be chosen for performing backups only if no higher priority availability replicas are currently available.</span></span>  
  
 <span data-ttu-id="b8a4c-134">**Replikat ausschließen**</span><span class="sxs-lookup"><span data-stu-id="b8a4c-134">**Exclude Replica**</span></span>  
 <span data-ttu-id="b8a4c-135">Wählen Sie diese Option, wenn dieses Verfügbarkeitsreplikat nie zum Ausführen von Sicherungen ausgewählt werden soll.</span><span class="sxs-lookup"><span data-stu-id="b8a4c-135">Select if you never want this availability replica to be chosen for performing backups.</span></span> <span data-ttu-id="b8a4c-136">Dies ist zum Beispiel für ein Remoteverfügbarkeitsreplikat hilfreich, für das keine Failover bei Sicherungen auftreten sollen.</span><span class="sxs-lookup"><span data-stu-id="b8a4c-136">This is useful, for example, for a remote availability replica to which you never want backups to fail over.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8a4c-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b8a4c-137">See Also</span></span>  
 <span data-ttu-id="b8a4c-138">[Aktive sekundäre Replikate: Sicherung auf sekundären Replikaten (AlwaysOn-Verfügbarkeitsgruppen)](active-secondaries-backup-on-secondary-replicas-always-on-availability-groups.md) </span><span class="sxs-lookup"><span data-stu-id="b8a4c-138">[Active Secondaries: Backup on Secondary Replicas (AlwaysOn Availability Groups)](active-secondaries-backup-on-secondary-replicas-always-on-availability-groups.md) </span></span>  
 [<span data-ttu-id="b8a4c-139">ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b8a4c-139">ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-availability-group-transact-sql)  
  
  
