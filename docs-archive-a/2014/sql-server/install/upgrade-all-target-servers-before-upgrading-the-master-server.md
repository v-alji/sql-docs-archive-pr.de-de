---
title: Aktualisieren aller Zielserver vor dem Upgrade des Master Servers | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- TSX [SQL Server Agent]
- target servers [SQL Server Agent]
- MSX [SQL Server Agent]
- master servers [SQL Server Agent]
ms.assetid: 2c231793-3878-4a5e-a425-1fa0d787ba84
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 031fedc4af4b058704cef1da8df846397b235305
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609020"
---
# <a name="upgrade-all-target-servers-before-upgrading-the-master-server"></a><span data-ttu-id="2f057-102">Durchführen eines Upgrades aller Zielserver vor dem Upgrade des Masterservers</span><span class="sxs-lookup"><span data-stu-id="2f057-102">Upgrade all target servers before upgrading the master server</span></span>
  <span data-ttu-id="2f057-103">Führen Sie vor dem Upgrade des Masterservers ein Upgrade aller Computer aus, die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ausführen und als Zielserver konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="2f057-103">Before you upgrade the master server, upgrade all computers that are running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are configured as target servers.</span></span>  
  
## <a name="component"></a><span data-ttu-id="2f057-104">Komponente</span><span class="sxs-lookup"><span data-stu-id="2f057-104">Component</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="2f057-105">-Agent</span><span class="sxs-lookup"><span data-stu-id="2f057-105">Agent</span></span>  
  
## <a name="description"></a><span data-ttu-id="2f057-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2f057-106">Description</span></span>  
 <span data-ttu-id="2f057-107">Um die Verwaltung in Multiserverumgebungen zu automatisieren, benötigen Sie mindestens einen Masterserver und mindestens einen Zielserver.</span><span class="sxs-lookup"><span data-stu-id="2f057-107">To automate administration in multiserver environments, you must have at least one master server and at least one target server.</span></span> <span data-ttu-id="2f057-108">Ein Masterserver verteilt Aufträge an die Zielserver und empfängt Ereignisse von ihnen.</span><span class="sxs-lookup"><span data-stu-id="2f057-108">A master server distributes jobs to, and receives events from, target servers.</span></span> <span data-ttu-id="2f057-109">Auf dem Masterserver ist zudem die zentrale Kopie der Auftragsdefinitionen für Aufträge gespeichert, die auf Zielservern ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2f057-109">A master server also stores the central copy of job definitions for jobs that are run on target servers.</span></span>  
  
 <span data-ttu-id="2f057-110">Wenn der aktuelle Server als Masterserver konfiguriert ist, führen Sie zuerst ein Upgrade aller Zielserver durch, bevor Sie den Masterserver aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="2f057-110">If the current server is configured as a master server, upgrade all of your target servers first before you upgrade the master server.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="2f057-111">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="2f057-111">Corrective Action</span></span>  
 <span data-ttu-id="2f057-112">Wenn Sie vor dem Upgrade des Masterservers nicht alle Zielserver aktualisieren können, müssen Sie alle Zielserver austragen und nach dem Upgrade wieder eintragen.</span><span class="sxs-lookup"><span data-stu-id="2f057-112">If you cannot upgrade all target servers before you upgrade the master server, you must defect all target servers and reenlist them after you upgrade.</span></span>  
  
 <span data-ttu-id="2f057-113">Weitere Informationen finden Sie in den Themen "Automatisieren der Verwaltung in einem Unternehmen", "Vorgehensweise: Austragen eines Zielservers bei einem Masterserver", und "Vorgehensweise: Eintragen eines Zielservers als Masterserver" in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="2f057-113">For more information, see the topics "Automating Administration across an Enterprise," "How to: Defect a Target Server from a Master Server," and "How to: Enlist a Target Server to a Master" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f057-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2f057-114">See Also</span></span>  
 <span data-ttu-id="2f057-115">[SQL Server-Agent Upgradeprobleme](../../../2014/sql-server/install/sql-server-agent-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="2f057-115">[SQL Server Agent Upgrade Issues](../../../2014/sql-server/install/sql-server-agent-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="2f057-116">Probleme beim Aktualisieren des SQL Server-Agents</span><span class="sxs-lookup"><span data-stu-id="2f057-116">SQL Server Agent Upgrade Issues</span></span>](../../../2014/sql-server/install/sql-server-agent-upgrade-issues.md)  
  
  
