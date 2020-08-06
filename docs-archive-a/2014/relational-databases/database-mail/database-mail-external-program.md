---
title: Externes Datenbank-E-Mail-Programm | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- external programs [Database Mail]
- DatabaseMail90.exe
- Database Mail [SQL Server], external programs
ms.assetid: bc124164-eb6e-4b7f-bf66-98a3113d02f7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 698fc8d97a565b4181552691a0260486c9c43bfd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725949"
---
# <a name="database-mail-external-program"></a><span data-ttu-id="2c620-102">Externes Datenbank-E-Mail-Programm</span><span class="sxs-lookup"><span data-stu-id="2c620-102">Database Mail External Program</span></span>
  <span data-ttu-id="2c620-103">Die ausführbare Datei für das externe Datenbank-E-Mail-Programm ist **DatabaseMail.exe**und ist im Verzeichnis **MSSQL\Binn** der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Installation gespeichert.</span><span class="sxs-lookup"><span data-stu-id="2c620-103">The Database Mail external executable is **DatabaseMail.exe**, located in the **MSSQL\Binn directory** of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation.</span></span> <span data-ttu-id="2c620-104">Datenbank-E-Mail verwendet die Service Broker-Aktivierung, um das externe Programm zu starten, wenn E-Mail-Nachrichten zur Verarbeitung vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="2c620-104">Database Mail uses Service Broker activation to start the external program when there are e-mail messages to be processed.</span></span> <span data-ttu-id="2c620-105">Datenbank-E-Mail startet eine Instanz des externen Programms.</span><span class="sxs-lookup"><span data-stu-id="2c620-105">Database Mail starts one instance of the external program.</span></span> <span data-ttu-id="2c620-106">Das externe Programm wird im Sicherheitskontext des Dienstkontos für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2c620-106">The external program runs in the security context of the service account for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="2c620-107">**In diesem Thema:**</span><span class="sxs-lookup"><span data-stu-id="2c620-107">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="2c620-108">Konzepte des externen Datenbank-E-Mail-Programms</span><span class="sxs-lookup"><span data-stu-id="2c620-108">Database Mail External Program Concepts</span></span>](#ComponentsAndConcepts)  
  
-   [<span data-ttu-id="2c620-109">Tasks, die sich auf die Konfiguration des externe Datenbank-E-Mail-Programms beziehen</span><span class="sxs-lookup"><span data-stu-id="2c620-109">Tasks Related to Configuring Database Mail External Program</span></span>](#RelatedTasks)  
  
##  <a name="database-mail-external-program-concepts"></a><a name="ComponentsAndConcepts"></a> <span data-ttu-id="2c620-110">Konzepte des externen Datenbank-E-Mail-Programms</span><span class="sxs-lookup"><span data-stu-id="2c620-110">Database Mail External Program Concepts</span></span>  
 <span data-ttu-id="2c620-111">Wenn das externe Programm gestartet wird, stellt das Programm mithilfe der Windows-Authentifizierung eine Verbindung mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] her und beginnt mit der Verarbeitung von E-Mail-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="2c620-111">When the external program starts, the program connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using Windows Authentication and begins processing e-mail messages.</span></span> <span data-ttu-id="2c620-112">Wenn keine zu sendenden Nachrichten für den angegebenen Timeoutzeitraum vorhanden sind, wird das Programm beendet.</span><span class="sxs-lookup"><span data-stu-id="2c620-112">When there have been no messages to send for the specified time-out period, the program exits.</span></span> <span data-ttu-id="2c620-113">Mithilfe des Assistenten zum Konfigurieren von Datenbank-E-Mail oder der gespeicherten Prozeduren von Datenbank-E-Mail können Sie konfigurieren, nach welcher Wartezeit das Programm beendet wird.</span><span class="sxs-lookup"><span data-stu-id="2c620-113">You can configure the amount of time that the program waits before exiting by using either Database Mail Configuration Wizard or the Database Mail stored procedures.</span></span> <span data-ttu-id="2c620-114">Weitere Informationen finden Sie unter [sysmail_configure_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-configure-sp-transact-sql)ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2c620-114">For more information, see [sysmail_configure_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-configure-sp-transact-sql).</span></span>  
  
 <span data-ttu-id="2c620-115">Das externe Programm speichert Informationen in Systemtabellen in der **msdb** -Datenbank.</span><span class="sxs-lookup"><span data-stu-id="2c620-115">The external program stores information in system tables in the **msdb** database.</span></span> <span data-ttu-id="2c620-116">Falls das externe Programm nicht mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]kommunizieren kann, protokolliert das Programm Fehler im Microsoft Windows-Anwendungsereignisprotokoll.</span><span class="sxs-lookup"><span data-stu-id="2c620-116">If the external program cannot communicate with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the program logs errors to the Microsoft Windows application event log.</span></span> <span data-ttu-id="2c620-117">Eine zusätzliche Meldungsprotokollierung ist verfügbar, wenn der Protokolliergrad im Dialogfeld **Systemparameter konfigurieren** des **Assistenten zum Konfigurieren von Datenbank-E-Mail** auf **Ausführlich**festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="2c620-117">Additional message logging is provided when the logging level is set to **Verbose** in the **Configure System Parameters** dialog box of the **Database Mail Configuration Wizard**.</span></span>  
  
 <span data-ttu-id="2c620-118">Beachten Sie, dass das externe Programm aus Gründen der Effizienz Konto- und Profilinformationen zwischenspeichert.</span><span class="sxs-lookup"><span data-stu-id="2c620-118">Notice that, for efficiency, the external program caches account and profile information.</span></span> <span data-ttu-id="2c620-119">Deshalb kann es sein, dass Konfigurationsänderungen an Konten und Profilen erst nach ein paar Minuten im externen Programm angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="2c620-119">Therefore, configuration changes to accounts and profiles may not be reflected in the external program for a few minutes.</span></span>  
  
##  <a name="tasks-related-to-configuring-database-mail-external-program"></a><a name="RelatedTasks"></a> <span data-ttu-id="2c620-120">Tasks, die sich auf die Konfiguration des externe Datenbank-E-Mail-Programms beziehen</span><span class="sxs-lookup"><span data-stu-id="2c620-120">Tasks Related to Configuring Database Mail External Program</span></span>  
  
|<span data-ttu-id="2c620-121">Konfigurationstask</span><span class="sxs-lookup"><span data-stu-id="2c620-121">Configuration Task</span></span>|<span data-ttu-id="2c620-122">Themenlink</span><span class="sxs-lookup"><span data-stu-id="2c620-122">Topic Link</span></span>|  
|------------------------|----------------|  
|<span data-ttu-id="2c620-123">Geben Sie die Zeit für das externe Programm vor dem Beenden an.</span><span class="sxs-lookup"><span data-stu-id="2c620-123">Specify the time that the External Program before exiting.</span></span>|[<span data-ttu-id="2c620-124">sysmail_configure_sp &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2c620-124">sysmail_configure_sp &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sysmail-configure-sp-transact-sql)|  
  
## <a name="see-also"></a><span data-ttu-id="2c620-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2c620-125">See Also</span></span>  
 <span data-ttu-id="2c620-126">[SQL Server Service Broker](../../database-engine/configure-windows/sql-server-service-broker.md) </span><span class="sxs-lookup"><span data-stu-id="2c620-126">[SQL Server Service Broker](../../database-engine/configure-windows/sql-server-service-broker.md) </span></span>  
 <span data-ttu-id="2c620-127">[Datenbank-E-Mail-Protokoll und -Überwachung](database-mail-log-and-audits.md) </span><span class="sxs-lookup"><span data-stu-id="2c620-127">[Database Mail Log and Audits](database-mail-log-and-audits.md) </span></span>  
 [<span data-ttu-id="2c620-128">Datenbank-E-Mail</span><span class="sxs-lookup"><span data-stu-id="2c620-128">Database Mail</span></span>](database-mail.md)  
  
  
