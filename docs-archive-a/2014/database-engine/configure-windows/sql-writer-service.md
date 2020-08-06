---
title: SQL Writer-Dienst | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- VDI [SQL Server]
- restoring [SQL Server], SQL Writer Service
- backups [SQL Server], while SQL Server running
- Volume Shadow Copy Service
- volume backups while running [SQL Server]
- Virtual Backup Device Interface [SQL Server]
- SQL Writer Service
- services [SQL Server], SQL Writer
- MSDE Writer
- VSS
ms.assetid: 0f299867-f499-4c2a-ad6f-b2ef1869381d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 310722c6617c7a2c9e0f384ec23ae371ab230536
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608836"
---
# <a name="sql-writer-service"></a><span data-ttu-id="b81f3-102">SQL Writer-Dienst</span><span class="sxs-lookup"><span data-stu-id="b81f3-102">SQL Writer Service</span></span>
  <span data-ttu-id="b81f3-103">Der SQL Writer-Dienst bietet zusätzliche Funktionalität zum Sichern und Wiederherstellen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] über dass VSS-Framework (Volume Shadow Copy Service, Volumeschattenkopie-Dienst).</span><span class="sxs-lookup"><span data-stu-id="b81f3-103">The SQL Writer Service provides added functionality for backup and restore of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] through the Volume Shadow Copy Service framework.</span></span>  
  
 <span data-ttu-id="b81f3-104">Der SQL Writer Service wird automatisch installiert.</span><span class="sxs-lookup"><span data-stu-id="b81f3-104">The SQL Writer Service is installed automatically.</span></span> <span data-ttu-id="b81f3-105">Er muss ausgeführt werden, wenn die Anwendung des Volumenschattenkopie-Diensts (VSS, Volume Shadow Copy Service) eine Sicherung oder Wiederherstellung anfordert.</span><span class="sxs-lookup"><span data-stu-id="b81f3-105">It must be running when the Volume Shadow Copy Service (VSS) application requests a backup or restore.</span></span> <span data-ttu-id="b81f3-106">Verwenden Sie das [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Services-Applet, um den Dienst zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b81f3-106">To configure the service, use the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Services applet.</span></span> <span data-ttu-id="b81f3-107">Der SQL Writer-Dienst kann auf allen Betriebssystemen installiert werden.</span><span class="sxs-lookup"><span data-stu-id="b81f3-107">The SQL Writer Service installs on all operating systems.</span></span>  
  
## <a name="purpose"></a><span data-ttu-id="b81f3-108">Zweck</span><span class="sxs-lookup"><span data-stu-id="b81f3-108">Purpose</span></span>  
 <span data-ttu-id="b81f3-109">Beim Ausführen errichtet [!INCLUDE[ssDE](../../includes/ssde-md.md)] eine Sperre und verfügt somit über den alleinigen Zugriff auf die Datendateien.</span><span class="sxs-lookup"><span data-stu-id="b81f3-109">When running, [!INCLUDE[ssDE](../../includes/ssde-md.md)] locks and has exclusive access to the data files.</span></span> <span data-ttu-id="b81f3-110">Wenn der SQL Writer Service nicht ausgeführt wird, haben unter Windows ausgeführte Sicherungsprogramme keinen Zugriff auf die Datendateien, und die Sicherung muss mithilfe der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Sicherung erfolgen.</span><span class="sxs-lookup"><span data-stu-id="b81f3-110">When the SQL Writer Service is not running, backup programs running in Windows do not have access to the data files, and backups must be performed using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup.</span></span>  
  
 <span data-ttu-id="b81f3-111">Verwenden Sie den SQL Writer Service, um Windows-Sicherungsprogrammen das Kopieren von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datendateien zu ermöglichen, während [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b81f3-111">Use the SQL Writer Service to permit Windows backup programs to copy [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data files while [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running.</span></span>  
  
## <a name="volume-shadow-copy-service"></a><span data-ttu-id="b81f3-112">Volumenschattenkopie-Dienst</span><span class="sxs-lookup"><span data-stu-id="b81f3-112">Volume Shadow Copy Service</span></span>  
 <span data-ttu-id="b81f3-113">Die in VSS bereitgestellte Gruppe von COM APIs implementiert ein Framework, das die Sicherung von Volumes ermöglicht, während die auf dem System ausgeführten Anwendungen weiter Daten auf die betreffenden Datenträger schreiben.</span><span class="sxs-lookup"><span data-stu-id="b81f3-113">The VSS is a set of COM APIs that implements a framework to allow volume backups to be performed while applications on a system continue to write to the volumes.</span></span> <span data-ttu-id="b81f3-114">Der VSS stellt eine konsistente Oberfläche bereit, mit der die Benutzeranwendungen, die Daten auf dem Datenträger aktualisieren (Verfasser), und die Benutzeranwendungen zum Sichern der Anwendungen (Anforderer) koordiniert werden können.</span><span class="sxs-lookup"><span data-stu-id="b81f3-114">The VSS provides a consistent interface that allows coordination between user applications that update data on disk (writers) and those that back up applications (requestors).</span></span>  
  
 <span data-ttu-id="b81f3-115">Der VSS kopiert und zeichnet dauerhafte Bilder zur Sicherung der laufenden Systeme, insbesondere der Server, auf, ohne dass dadurch Leistung und Stabilität der bereitgestellten Dienste übermäßig beeinträchtigt werden.</span><span class="sxs-lookup"><span data-stu-id="b81f3-115">The VSS captures and copies stable images for backup on running systems, particularly servers, without unduly degrading the performance and stability of the services they provide.</span></span> <span data-ttu-id="b81f3-116">Weitere Informationen zum VSS finden Sie in der Windows-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="b81f3-116">For more information on the VSS, see your Windows documentation.</span></span>  
  
## <a name="virtual-backup-device-interface-vdi"></a><span data-ttu-id="b81f3-117">VDI (Virtual Backup Device Interface)</span><span class="sxs-lookup"><span data-stu-id="b81f3-117">Virtual Backup Device Interface (VDI)</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b81f3-118">stellt ein API namens VDI (Virtual Backup Device Interface) bereit, mit dem unabhängige Softwarehersteller [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in ihre Produkte integrieren können, um so Unterstützung für Sicherungs- und Wiederherstellungsvorgänge bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="b81f3-118">provides an API called Virtual Backup Device Interface (VDI) that enables independent software vendors to integrate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] into their products for providing support for backup and restore operations.</span></span> <span data-ttu-id="b81f3-119">Diese APIs wurden mit dem Ziel der maximalen Zuverlässigkeit und Leistung entworfen und unterstützen das gesamte Spektrum der in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] bereitgestellten Sicherungs- und Wiederherstellungsfunktionen, einschließlich aller Funktionen von Hotbackups und Momentaufnahmesicherungen.</span><span class="sxs-lookup"><span data-stu-id="b81f3-119">These APIs are engineered to provide maximum reliability and performance, and support the full range of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup and restore functionality, including the full range of hot and snapshot backup capabilities.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="b81f3-120">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="b81f3-120">Permissions</span></span>  
 <span data-ttu-id="b81f3-121">Der SQL Writer-Dienst muss unter dem Konto **Lokales System** ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b81f3-121">The SQL Writer service must run under the **Local System** account.</span></span> <span data-ttu-id="b81f3-122">Der SQL Writer-Dienst verwendet die Anmeldung für **NT-Dienst\SQLWriter** , um eine Verbindung mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]herzustellen.</span><span class="sxs-lookup"><span data-stu-id="b81f3-122">The SQL Writer service uses the **NT Service\SQLWriter** login to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b81f3-123">Mithilfe der Anmeldung für **NT-Dienst\SQLWriter** kann der SQL Writer-Prozess mit einer niedrigeren Berechtigungsstufe unter einem Konto ausgeführt werden, das **nicht als Anmeldekonto**geführt wird. Auf diese Weise wird das Sicherheitsrisiko verringert.</span><span class="sxs-lookup"><span data-stu-id="b81f3-123">Using the **NT Service\SQLWriter** login allows the SQL Writer process to run at a lower privilege level in an account designated as **no login**, which limits vulnerability.</span></span> <span data-ttu-id="b81f3-124">Wenn der SQL Writer-Dienst deaktiviert ist, werden Hilfsprogramme, die auf VSS-Momentaufnahmen basieren, z. B. System Center Data Protection Manager sowie einige andere Drittanbieterprodukte, funktionsunfähig. Im schlimmsten Fall besteht die Gefahr, dass Sicherungen von inkonsistenten Datenbanken erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="b81f3-124">If the SQL Writer service is disabled, then any utility which in relies on VSS snapshots, such as System Center Data Protection Manager, as well as some other 3rd-party products, would be broken, or worse, at risk of taking backups of databases which were not consistent.</span></span> <span data-ttu-id="b81f3-125">Wenn [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], das System, auf dem die Software ausgeführt wird, und das Hostsystem (im Falle eines virtuellen Computers) keine anderen Komponenten als die [!INCLUDE[tsql](../../includes/tsql-md.md)] -Sicherung erfordern, kann der SQL Writer-Dienst gefahrlos deaktiviert und die Anmeldung entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="b81f3-125">If neither [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the system it runs on, nor the host system (in the event of a virtual machine), need to use anything besides [!INCLUDE[tsql](../../includes/tsql-md.md)] backup, then the SQL Writer service can be safely disabled and the login removed.</span></span>  <span data-ttu-id="b81f3-126">Beachten Sie, dass der SQL Writer-Dienst durch eine Sicherung auf Volume- oder Systemebene initiiert werden kann, unabhängig davon, ob die Sicherung direkt auf einer Momentaufnahme basiert oder nicht.</span><span class="sxs-lookup"><span data-stu-id="b81f3-126">Note that the SQL Writer service may be invoked by a system or volume level backup, whether the backup is directly snapshot-based or not.</span></span> <span data-ttu-id="b81f3-127">Einige Systemsicherungsprodukte verwenden VSS, um Blockierungen durch geöffnete oder gesperrte Dateien zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="b81f3-127">Some system backup products use VSS to avoid being blocked by open or locked files.</span></span> <span data-ttu-id="b81f3-128">Der SQL Writer-Dienst erfordert erhöhte Berechtigungen in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , da im Verlauf der Dienstaktivitäten sämtliche E/A-Vorgänge für die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]kurzzeitig eingefroren werden.</span><span class="sxs-lookup"><span data-stu-id="b81f3-128">The SQL Writer service needs elevated permissions in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] because in the course of its activities it briefly freezes all I/O for the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="features"></a><span data-ttu-id="b81f3-129">Features</span><span class="sxs-lookup"><span data-stu-id="b81f3-129">Features</span></span>  
 <span data-ttu-id="b81f3-130">SQL Writer unterstützt:</span><span class="sxs-lookup"><span data-stu-id="b81f3-130">SQL Writer supports:</span></span>  
  
-   <span data-ttu-id="b81f3-131">Vollständige Sicherung und Wiederherstellung von Datenbanken, einschließlich der Volltextkataloge</span><span class="sxs-lookup"><span data-stu-id="b81f3-131">Full database backup and restore including full-text catalogs</span></span>  
  
-   <span data-ttu-id="b81f3-132">Differenzielle Sicherung und Wiederherstellung</span><span class="sxs-lookup"><span data-stu-id="b81f3-132">Differential backup and restore</span></span>  
  
-   <span data-ttu-id="b81f3-133">Wiederherstellung mit MOVE-Klausel</span><span class="sxs-lookup"><span data-stu-id="b81f3-133">Restore with move</span></span>  
  
-   <span data-ttu-id="b81f3-134">Datenbankumbenennung</span><span class="sxs-lookup"><span data-stu-id="b81f3-134">Database rename</span></span>  
  
-   <span data-ttu-id="b81f3-135">Kopiesicherung</span><span class="sxs-lookup"><span data-stu-id="b81f3-135">Copy-only backup</span></span>  
  
-   <span data-ttu-id="b81f3-136">Automatische Wiederherstellung einer Datenbankmomentaufnahme</span><span class="sxs-lookup"><span data-stu-id="b81f3-136">Auto-recovery of database snapshot</span></span>  
  
 <span data-ttu-id="b81f3-137">SQL Writer unterstützt nicht:</span><span class="sxs-lookup"><span data-stu-id="b81f3-137">SQL Writer does not support:</span></span>  
  
-   <span data-ttu-id="b81f3-138">Protokollsicherungen</span><span class="sxs-lookup"><span data-stu-id="b81f3-138">Log backups</span></span>  
  
-   <span data-ttu-id="b81f3-139">Datei- und Dateigruppensicherung</span><span class="sxs-lookup"><span data-stu-id="b81f3-139">File and filegroup backup</span></span>  
  
-   <span data-ttu-id="b81f3-140">Seitenwiederherstellung</span><span class="sxs-lookup"><span data-stu-id="b81f3-140">Page restore</span></span>  
  
  
