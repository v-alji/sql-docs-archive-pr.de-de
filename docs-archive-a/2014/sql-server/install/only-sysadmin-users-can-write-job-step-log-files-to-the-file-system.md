---
title: Nur sysadmin-Benutzer können Auftrags Schritt-Protokolldateien in das Dateisystem schreiben. Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- job step log files [SQL Server Agent]
- log files [SQL Server Agent]
- writing job step log files
ms.assetid: d26a7cef-1a60-4c95-b9df-f8b4fec59f9b
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 9e2bf5095ac1e6b67f6c6f3f87444879913916e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618448"
---
# <a name="only-sysadmin-users-can-write-job-step-log-files-to-the-file-system"></a><span data-ttu-id="22e40-102">Nur Benutzer mit Systemadministratorberechtigungen können Protokolldateien für Auftragsschritte in das Dateisystem schreiben</span><span class="sxs-lookup"><span data-stu-id="22e40-102">Only sysadmin users can write job step log files to the file system</span></span>
  [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="22e40-103">erstellt optional ein Protokoll für jeden Auftragsschritt.</span><span class="sxs-lookup"><span data-stu-id="22e40-103">optionally writes a log for each job step.</span></span>  
  
## <a name="component"></a><span data-ttu-id="22e40-104">Komponente</span><span class="sxs-lookup"><span data-stu-id="22e40-104">Component</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="22e40-105">-Agent</span><span class="sxs-lookup"><span data-stu-id="22e40-105">Agent</span></span>  
  
## <a name="description"></a><span data-ttu-id="22e40-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="22e40-106">Description</span></span>  
 <span data-ttu-id="22e40-107">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] kann der-Agent Protokolle in das Dateisystem für Aufträge schreiben, die Mitglieder der festen Server Rolle **sysadmin** sind.</span><span class="sxs-lookup"><span data-stu-id="22e40-107">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent can write logs to the file system for jobs that are owned by members of the **sysadmin** fixed server role.</span></span> <span data-ttu-id="22e40-108">Wenn der Besitzer des Auftrags kein Mitglied der **sysadmin** -Rolle ist und das Proxy Konto aktiviert ist, kann der- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Protokolle in das Dateisystem schreiben, indem er die Anmelde Informationen des Proxy Kontos verwendet.</span><span class="sxs-lookup"><span data-stu-id="22e40-108">If the job owner is not a member of the **sysadmin** role and if the proxy account is enabled, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent can write logs to the file system by using the credentials of the proxy account.</span></span>  
  
 <span data-ttu-id="22e40-109">Nachdem Sie das Upgrade ausgeführt haben, können Aufträge im Besitz von Benutzern, die keine Mitglieder der festen Server Rolle **sysadmin** sind, keine Protokolle mehr in das Dateisystem schreiben.</span><span class="sxs-lookup"><span data-stu-id="22e40-109">After you upgrade, jobs that are owned by users who are not members of the **sysadmin** fixed server role can no longer write logs to the file system.</span></span> <span data-ttu-id="22e40-110">Stattdessen können diese Benutzer die Option auswählen, um Ihre Protokolle in eine Tabelle in der **msdb** -Datenbank zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="22e40-110">Instead, these users can select the option to write their logs to a table in the **msdb** database.</span></span> <span data-ttu-id="22e40-111">Mitglieder der **sysadmin** -Rolle können weiterhin Protokolldateien in das Dateisystem schreiben.</span><span class="sxs-lookup"><span data-stu-id="22e40-111">Members of the **sysadmin** role can still write log files to the file system.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="22e40-112">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="22e40-112">Corrective Action</span></span>  
 <span data-ttu-id="22e40-113">Nach dem Upgrade werden Aufträge, die sich im Besitz von Benutzern befinden, die nicht Mitglied der **sysadmin** -Rolle sind, weiterhin ausgeführt, aber es werden keine Protokolle erstellt.</span><span class="sxs-lookup"><span data-stu-id="22e40-113">After you upgrade, jobs that are owned by users who are not members of the **sysadmin** role will continue to run, but logs will not be created.</span></span> <span data-ttu-id="22e40-114">Zum Protokollieren von Auftrags Schritten in einer Tabelle müssen Benutzer, die nicht Mitglied der **sysadmin** -Rolle sind, Ihre Aufträge manuell aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="22e40-114">To log job steps to a table, users who are not members of the **sysadmin** role must manually update their jobs.</span></span>  
  
 <span data-ttu-id="22e40-115">Weitere Informationen finden Sie in den Themen "Erstellen von Aufträgen", "Erstellen von Auftragsschritten" und "Handhaben mehrerer Auftragsschritte" in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="22e40-115">For more information, see the topics "Creating Jobs," "Creating Job Steps," and "Handling Multiple Job Steps" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22e40-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="22e40-116">See Also</span></span>  
 [<span data-ttu-id="22e40-117">Probleme beim Aktualisieren des SQL Server-Agents</span><span class="sxs-lookup"><span data-stu-id="22e40-117">SQL Server Agent Upgrade Issues</span></span>](../../../2014/sql-server/install/sql-server-agent-upgrade-issues.md)  
  
  
