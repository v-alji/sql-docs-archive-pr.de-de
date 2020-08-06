---
title: Datenbank-E-Mail-Protokoll und -Überwachung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- auditing [SQL Server]
- Database Mail [SQL Server], auditing
- logs [Database Mail]
- audits [SQL Server], Database Mail
- Database Mail [SQL Server], logging
ms.assetid: 846589ee-5fe5-4ab3-b335-0c253e569f99
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6267389f187b955982ec1c18c411f703b4562f3c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725933"
---
# <a name="database-mail-log-and-audits"></a><span data-ttu-id="68d52-102">Datenbank-E-Mail-Protokoll und -Überwachung</span><span class="sxs-lookup"><span data-stu-id="68d52-102">Database Mail Log and Audits</span></span>
  <span data-ttu-id="68d52-103">Die Protokollierungsfunktionalität für Datenbank-E-Mail stellt eine Möglichkeit zum Isolieren und Beheben von Problemen dar.</span><span class="sxs-lookup"><span data-stu-id="68d52-103">The Database Mail logging functionality is designed to provide a way to isolate and correct problems.</span></span> <span data-ttu-id="68d52-104">Datenbank-E-Mail speichert die Protokollinformationen in der **msdb** -Datenbank.</span><span class="sxs-lookup"><span data-stu-id="68d52-104">Database Mail stores the log information in the **msdb** database.</span></span> <span data-ttu-id="68d52-105">Informationen zum E-Mail-Inhalt, E-Mail-Status und zu empfangenen Nachrichten, z. B. Fehler, in Datenbank-E-Mail werden von Datenbank-E-Mail protokolliert und können zur Problembehebung und Überwachung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="68d52-105">Information about Database Mail e-mail content, status of e-mails, and any messages received, such as errors  are logged by Database Mail and can be used for troubleshooting and auditing purposes.</span></span>  
  
## <a name="database-mail-logs"></a><span data-ttu-id="68d52-106">Protokolle zu Datenbank-E-Mail</span><span class="sxs-lookup"><span data-stu-id="68d52-106">Database Mail Logs</span></span>  
 <span data-ttu-id="68d52-107">In den Protokollinformationen der **msdb** -Datenbank von [Database Mail External Program](database-mail-external-program.md)vorhandene Tabellen.</span><span class="sxs-lookup"><span data-stu-id="68d52-107">Tables in the **msdb** database log information from the [Database Mail External Program](database-mail-external-program.md).</span></span> <span data-ttu-id="68d52-108">[Datenbank-E-Mail-Sichten &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/database-mail-views-transact-sql) machen die Tabellen für die Problembehandlung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="68d52-108">[Database Mail Views &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/database-mail-views-transact-sql) expose the tables for troubleshooting purposes.</span></span> <span data-ttu-id="68d52-109">Fehler werden in der Sicht [sysmail_event_log &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sysmail-event-log-transact-sql) aufgeführt, wenn der Service Broker das externe Programm nicht aktivieren kann, wenn im externen Programm Netzwerkfehler auftreten, oder wenn der SMTP-Server (Simple Mail Transport Protocol) eine E-Mail-Nachricht verweigert.</span><span class="sxs-lookup"><span data-stu-id="68d52-109">Errors appear in the [sysmail_event_log &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sysmail-event-log-transact-sql) view if Service Broker cannot activate the external program, if the external program encounters networking errors or if the Simple Mail Transport Protocol (SMTP) server refuses an e-mail message.</span></span> <span data-ttu-id="68d52-110">Wenn sich das externe Programm nicht bei der **msdb** -Tabelle anmelden kann, werden vom Programm Fehler im Windows-Anwendungsereignisprotokoll protokolliert.</span><span class="sxs-lookup"><span data-stu-id="68d52-110">In the event that the external program cannot log to the **msdb** tables, the program logs errors to the Windows application event log.</span></span>  
  
 <span data-ttu-id="68d52-111">Interne Tabellen der **msdb** -Datenbank enthalten die E-Mail-Nachrichten aus der Datenbank-E-Mail sowie den aktuellen Status der einzelnen Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="68d52-111">Internal tables in the **msdb** database contain the e-mail messages and attachments sent from Database Mail, together with the current status of each message.</span></span> <span data-ttu-id="68d52-112">Datenbank-E-Mail aktualisiert diese Tabellen bei der Verarbeitung jeder Meldung.</span><span class="sxs-lookup"><span data-stu-id="68d52-112">Database Mail updates these tables as each message is processed.</span></span>  
  
## <a name="database-mail-auditing-tasks"></a><span data-ttu-id="68d52-113">Überwachungstasks von Datenbank-E-Mail</span><span class="sxs-lookup"><span data-stu-id="68d52-113">Database Mail Auditing tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="68d52-114">**Überprüfen und Verwalten von Protokollen zu Datenbank-E-Mail**</span><span class="sxs-lookup"><span data-stu-id="68d52-114">**Reviewing and managing Database Mail logs**</span></span>|<span data-ttu-id="68d52-115">**Link zum Thema**</span><span class="sxs-lookup"><span data-stu-id="68d52-115">**Link to Topic**</span></span>|  
|<span data-ttu-id="68d52-116">Überprüfen des Übermittlungsstatus einer einzelnen Nachricht</span><span class="sxs-lookup"><span data-stu-id="68d52-116">Check the delivery status of an individual message</span></span>|[<span data-ttu-id="68d52-117">Überprüfen des Status von mit Datenbank-E-Mail gesendeten E-Mail-Nachrichten</span><span class="sxs-lookup"><span data-stu-id="68d52-117">Check the Status of E-Mail Messages Sent With Database Mail</span></span>](check-the-status-of-e-mail-messages-sent-with-database-mail.md)|  
|<span data-ttu-id="68d52-118">Bereinigen von Nachrichten, Anlagen und Protokolleinträgen in Datenbank-E-Mail</span><span class="sxs-lookup"><span data-stu-id="68d52-118">Clean up Database Mail messages, attachments, and log entries</span></span>|[<span data-ttu-id="68d52-119">sysmail_delete_mailitems_sp &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="68d52-119">sysmail_delete_mailitems_sp &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sysmail-delete-mailitems-sp-transact-sql)<br /><br /> [<span data-ttu-id="68d52-120">sysmail_delete_log_sp &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="68d52-120">sysmail_delete_log_sp &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sysmail-delete-log-sp-transact-sql)|  
|<span data-ttu-id="68d52-121">Archivieren der Nachrichten und Protokolle in Datenbank-E-Mail</span><span class="sxs-lookup"><span data-stu-id="68d52-121">Archive the Database Email Messages and Logs</span></span>|[<span data-ttu-id="68d52-122">Erstellen eines Auftrags des SQL Server-Agents zum Archivieren von Datenbank-E-Mail-Nachrichten und Ereignisprotokollen</span><span class="sxs-lookup"><span data-stu-id="68d52-122">Create a SQL Server Agent Job to Archive Database Mail Messages and Event Logs</span></span>](create-a-sql-server-agent-job-to-archive-database-mail-messages-and-event-logs.md)|  
  
## <a name="see-also"></a><span data-ttu-id="68d52-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="68d52-123">See Also</span></span>  
 [<span data-ttu-id="68d52-124">Überwachen der Ressourcenverwendung &#40;Systemmonitor&#41;</span><span class="sxs-lookup"><span data-stu-id="68d52-124">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](../performance-monitor/monitor-resource-usage-system-monitor.md)  
  
  
