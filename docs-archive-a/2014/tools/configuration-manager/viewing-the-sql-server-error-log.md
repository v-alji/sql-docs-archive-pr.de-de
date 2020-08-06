---
title: Anzeigen des SQL Server Fehler Protokolls | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- cycling SQL Server error log
- viewing SQL Server error log
- errors [SQL Server], logs
- SQL Server error log
- displaying SQL Server error log
- logs [SQL Server], SQL Server error logs
ms.assetid: 6908c21a-65e3-458f-a272-fee256d86448
author: stevestein
ms.author: sstein
ms.openlocfilehash: 822ae4fba589f005aaee41857a9db3388a309254
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607474"
---
# <a name="viewing-the-sql-server-error-log"></a><span data-ttu-id="6da04-102">Anzeigen des SQL Server-Fehlerprotokolls</span><span class="sxs-lookup"><span data-stu-id="6da04-102">Viewing the SQL Server Error Log</span></span>
  <span data-ttu-id="6da04-103">Zeigen Sie das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Fehlerprotokoll an, um sicherzustellen, dass bestimmte Prozesse erfolgreich abgeschlossen wurden (z.B. Sicherungs- und Wiederherstellungsvorgänge, Batchbefehle oder andere Skripts und Prozesse).</span><span class="sxs-lookup"><span data-stu-id="6da04-103">View the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to ensure that processes have completed successfully (for example, backup and restore operations, batch commands, or other scripts and processes).</span></span> <span data-ttu-id="6da04-104">Dies ist hilfreich, um aktuelle oder potenzielle Problembereiche zu ermitteln, einschließlich automatischer Wiederherstellungsmeldungen (insbesondere, wenn eine Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] angehalten und neu gestartet wurde), Kernelmeldungen oder anderer Fehlermeldungen auf Serverebene.</span><span class="sxs-lookup"><span data-stu-id="6da04-104">This can be helpful to detect any current or potential problem areas, including automatic recovery messages (particularly if an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has been stopped and restarted), kernel messages, or other server-level error messages.</span></span>  
  
 <span data-ttu-id="6da04-105">Um das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Fehlerprotokoll anzuzeigen, können Sie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder einen beliebigen Text-Editor verwenden.</span><span class="sxs-lookup"><span data-stu-id="6da04-105">View the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or any text editor.</span></span> <span data-ttu-id="6da04-106">Weitere Informationen zum Anzeigen des Fehlerprotokolls finden Sie unter [Open Log File Viewer](../../relational-databases/logs/log-file-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="6da04-106">For more information about how to view the error log, see [Open Log File Viewer](../../relational-databases/logs/log-file-viewer.md).</span></span> <span data-ttu-id="6da04-107">Standardmäßig befindet sich das Fehlerprotokoll unter `Program Files\Microsoft SQL Server\MSSQL.`*n*`\MSSQL\LOG\ERRORLOG` und `ERRORLOG.`*n* .</span><span class="sxs-lookup"><span data-stu-id="6da04-107">By default, the error log is located at `Program Files\Microsoft SQL Server\MSSQL.`*n*`\MSSQL\LOG\ERRORLOG` and `ERRORLOG.`*n* files.</span></span>  
  
 <span data-ttu-id="6da04-108">Es wird immer dann ein neues Fehlerprotokoll erstellt, wenn eine Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gestartet wird, obwohl die gespeicherte Systemprozedur [sp_cycle_errorlog](/sql/relational-databases/system-stored-procedures/sp-cycle-errorlog-transact-sql) zum Durchlaufen der Fehlerprotokolldateien verwendet werden kann, ohne dass die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]neu gestartet werden muss.</span><span class="sxs-lookup"><span data-stu-id="6da04-108">A new error log is created each time an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is started, although the [sp_cycle_errorlog](/sql/relational-databases/system-stored-procedures/sp-cycle-errorlog-transact-sql) system stored procedure can be used to cycle the error log files without having to restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6da04-109">In der Regel behält [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Sicherungen der letzten sechs Protokolle bei. Dabei erhält die letzte Sicherung die Erweiterung .1, die zweitletzte Sicherung die Erweiterung .2 usw.</span><span class="sxs-lookup"><span data-stu-id="6da04-109">Typically, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] retains backups of the previous six logs and gives the most recent log backup the extension .1, the second most recent the extension .2, and so on.</span></span> <span data-ttu-id="6da04-110">Das aktuelle Fehlerprotokoll hat keine Erweiterung.</span><span class="sxs-lookup"><span data-stu-id="6da04-110">The current error log has no extension.</span></span>  
  
 <span data-ttu-id="6da04-111">Beachten Sie, dass Sie auch das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Fehlerprotokoll zu Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] anzeigen können, die offline sind oder nicht gestartet werden können.</span><span class="sxs-lookup"><span data-stu-id="6da04-111">Be aware that you can also view the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log on instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are offline or cannot start.</span></span> <span data-ttu-id="6da04-112">Weitere Informationen finden Sie unter [Anzeigen von Offlineprotokolldateien](../../relational-databases/logs/view-offline-log-files.md).</span><span class="sxs-lookup"><span data-stu-id="6da04-112">For more information, see [View Offline Log Files](../../relational-databases/logs/view-offline-log-files.md).</span></span>  
  
  
