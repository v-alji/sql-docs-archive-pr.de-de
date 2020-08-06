---
title: Anzeigen des Windows-Anwendungsprotokolls | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- application logs [SQL Server]
- Windows application logs [SQL Server]
- viewing Windows application logs
- errors [SQL Server], logs
- system logs [SQL Server]
- security logs [SQL Server]
- displaying Windows application logs
- logs [SQL Server], Windows application logs
ms.assetid: f9853b74-7db7-47cc-b957-e49ed5bc0a1a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 22f900a0b203e652bbc9cc6e9638711d138756c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617328"
---
# <a name="viewing-the-windows-application-log"></a><span data-ttu-id="c35ff-102">Anzeigen des Windows-Anwendungsprotokolls</span><span class="sxs-lookup"><span data-stu-id="c35ff-102">Viewing the Windows Application Log</span></span>
  <span data-ttu-id="c35ff-103">Wenn [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] so konfiguriert wurde, dass das Microsoft Windows-Anwendungsprotokoll verwendet wird, schreibt jede [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Sitzung neue Ereignisse in dieses Protokoll.</span><span class="sxs-lookup"><span data-stu-id="c35ff-103">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured to use the Microsoft Windows application log, each [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] session writes new events to that log.</span></span> <span data-ttu-id="c35ff-104">Im Gegensatz zum Fehlerprotokoll von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] wird beim Starten einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Instanz nicht jedes Mal ein neues Anwendungsprotokoll erstellt.</span><span class="sxs-lookup"><span data-stu-id="c35ff-104">Unlike the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log, a new application log is not created each time you start an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="c35ff-105">Das Windows-Anwendungsprotokoll können Sie mit der Windows-Ereignisanzeige oder dem Protokoll-Viewer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]anzeigen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="c35ff-105">View and manage the Windows application log by using Windows Event Viewer or the Log Viewer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="c35ff-106">Es gibt drei Protokolle, die mit der Ereignisanzeige angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="c35ff-106">There are three logs that can be viewed with Event Viewer.</span></span>  
  
|<span data-ttu-id="c35ff-107">Windows-Protokolltyp</span><span class="sxs-lookup"><span data-stu-id="c35ff-107">Windows log type</span></span>|<span data-ttu-id="c35ff-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c35ff-108">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="c35ff-109">Systemprotokoll</span><span class="sxs-lookup"><span data-stu-id="c35ff-109">System log</span></span>|<span data-ttu-id="c35ff-110">Zeichnet Ereignisse auf, die von den Windows-Betriebssystemkomponenten protokolliert werden.</span><span class="sxs-lookup"><span data-stu-id="c35ff-110">Records events logged by the Windows operating system components.</span></span> <span data-ttu-id="c35ff-111">Wenn beispielsweise ein Treiber oder eine andere Systemkomponente beim Starten nicht geladen wird, wird dies im Systemprotokoll aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="c35ff-111">For example, the failure of a driver or other system component to load during startup is recorded in the system log.</span></span>|  
|<span data-ttu-id="c35ff-112">Sicherheitsprotokoll</span><span class="sxs-lookup"><span data-stu-id="c35ff-112">Security log</span></span>|<span data-ttu-id="c35ff-113">Zeichnet Sicherheitsereignisse auf, wie z. B. fehlgeschlagene Anmeldeversuche.</span><span class="sxs-lookup"><span data-stu-id="c35ff-113">Records security events, such as failed login attempts.</span></span> <span data-ttu-id="c35ff-114">Dadurch können Änderungen am Sicherheitssystem nachverfolgt und mögliche Verstöße gegen die Sicherheit erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="c35ff-114">This helps track changes to the security system and identify possible breaches to security.</span></span> <span data-ttu-id="c35ff-115">So können z. B. Versuche einer Anmeldung am System im Sicherheitsprotokoll aufgezeichnet werden, je nach Überwachungseinstellungen im Benutzer-Manager.</span><span class="sxs-lookup"><span data-stu-id="c35ff-115">For example, attempts to log on to the system may be recorded in the security log, depending on the audit settings in the User Manager.</span></span><br /><br /> <span data-ttu-id="c35ff-116">Ausschließlich Mitglieder der festen Serverrolle **sysadmin** können das Sicherheitsprotokoll anzeigen.</span><span class="sxs-lookup"><span data-stu-id="c35ff-116">Only members of the **sysadmin** fixed server role can view the security log.</span></span>|  
|<span data-ttu-id="c35ff-117">Anwendungsprotokoll</span><span class="sxs-lookup"><span data-stu-id="c35ff-117">Application log</span></span>|<span data-ttu-id="c35ff-118">Zeichnet Ereignisse auf, die von Anwendungen protokolliert werden.</span><span class="sxs-lookup"><span data-stu-id="c35ff-118">Records events that are logged by applications.</span></span> <span data-ttu-id="c35ff-119">So kann eine Datenbankanwendung beispielsweise einen Dateifehler im Anwendungsprotokoll aufzeichnen.</span><span class="sxs-lookup"><span data-stu-id="c35ff-119">For example, a database application might record a file error in the application log.</span></span>|  
  
 <span data-ttu-id="c35ff-120">Weitere Informationen zum Verwenden der Ereignisanzeige und zum Verwalten des Anwendungsprotokolls sowie Erklärungen zu den angezeigten Informationen finden Sie in der Windows-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="c35ff-120">For more information about using Event Viewer, managing the application log, and understanding the information it presents, see the Windows documentation.</span></span>  
  
 <span data-ttu-id="c35ff-121">**So zeigen Sie das Anwendungsprotokoll von Windows an**</span><span class="sxs-lookup"><span data-stu-id="c35ff-121">**To view the Windows application log**</span></span>  
  
 [<span data-ttu-id="c35ff-122">Anzeigen des Anwendungsprotokolls von Windows &#40;Windows&#41;</span><span class="sxs-lookup"><span data-stu-id="c35ff-122">View the Windows Application Log &#40;Windows&#41;</span></span>](../../relational-databases/performance/view-the-windows-application-log-windows-10.md)  
  
  
