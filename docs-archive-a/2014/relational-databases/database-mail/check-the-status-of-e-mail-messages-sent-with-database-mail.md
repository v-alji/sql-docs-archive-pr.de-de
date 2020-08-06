---
title: Prüfen des Status von mit Datenbank-E-Mail gesendeten E-Mail-Nachrichten | Microsoft- Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- e-mail [SQL Server], status information
- mail [SQL Server], status information
- Database Mail [SQL Server], message status
- status information [Database Mail]
ms.assetid: eb290f24-b52f-46bc-84eb-595afee6a5f3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1642c456cd64484dede64f8127ff2f979f2242e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622671"
---
# <a name="check-the-status-of-e-mail-messages-sent-with-database-mail"></a><span data-ttu-id="05ec1-102">Überprüfen des Status von mit Datenbank-E-Mail gesendeten E-Mail-Nachrichten</span><span class="sxs-lookup"><span data-stu-id="05ec1-102">Check the Status of E-Mail Messages Sent With Database Mail</span></span>
  <span data-ttu-id="05ec1-103">In diesem Thema wird beschrieben, wie der Status der mittels Datenbank-E-Mail in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] gesendeten E-Mail durch das Verwenden von [!INCLUDE[tsql](../../includes/tsql-md.md)]überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="05ec1-103">This topic describes how to check the status of the e-mail message sent using Database Mail  in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
-   <span data-ttu-id="05ec1-104">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="05ec1-104">**Before you begin:**</span></span>  
  
-   <span data-ttu-id="05ec1-105">**So zeigen Sie den Status der E-Mail an, die mittels Datenbank-E-Mail gesendet wurde:**  [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="05ec1-105">**To view the status of the e-mail sent using Database Mail, using:**  [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="05ec1-106">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="05ec1-106">Before You Begin</span></span>  
 <span data-ttu-id="05ec1-107">Datenbank-E-Mail speichert Kopien ausgehender E-Mail-Nachrichten in den Sichten **sysmail_allitems**, **sysmail_sentitems**, **sysmail_unsentitems**und **sysmail_faileditems** der **msdb** -Datenbank.</span><span class="sxs-lookup"><span data-stu-id="05ec1-107">Database Mail keeps copies of outgoing e-mail messages and displays them in the **sysmail_allitems**, **sysmail_sentitems**, **sysmail_unsentitems**, **sysmail_faileditems** views of the **msdb** database.</span></span> <span data-ttu-id="05ec1-108">Das externe Programm Datenbank-E-Mail protokolliert die Aktivität und zeigt das Protokoll über das Windows-Anwendungsereignisprotokoll und die **sysmail_event_log** -Sicht der **msdb** -Datenbank an.</span><span class="sxs-lookup"><span data-stu-id="05ec1-108">The Database Mail external program logs activity and displays the log through the Windows Application Event Log and the **sysmail_event_log** view in the **msdb** database.</span></span> <span data-ttu-id="05ec1-109">Führen Sie zum Prüfen des Status einer E-Mail-Nachricht eine Abfrage für diese Sicht aus.</span><span class="sxs-lookup"><span data-stu-id="05ec1-109">To check the status of an e-mail message, run a query against this view.</span></span> <span data-ttu-id="05ec1-110">Für E-Mail-Nachrichten gibt es vier Statusmöglichkeiten: **sent**, **unsent**, **retrying**und **failed**.</span><span class="sxs-lookup"><span data-stu-id="05ec1-110">E-mail messages have one of four possible statuses: **sent**, **unsent**, **retrying**, and **failed**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="05ec1-111">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="05ec1-111">Using Transact-SQL</span></span>  
 <span data-ttu-id="05ec1-112">**So zeigen Sie den Status der E-Mail an, die mittels Datenbank-E-Mail gesendet wurde**</span><span class="sxs-lookup"><span data-stu-id="05ec1-112">**To view the status of the e-mail sent using Database Mail**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="05ec1-113">Ein Beispiel für diese Prozedur finden Sie weiter unten in diesem Abschnitt unter [Beispiel (Transact-SQL)](#TsqlExample).</span><span class="sxs-lookup"><span data-stu-id="05ec1-113">For an example of this procedure, see [Example (Transact-SQL)](#TsqlExample), later in this section.</span></span>  
  
1.  <span data-ttu-id="05ec1-114">Wählen Sie aus der **sysmail_allitems** -Tabelle aus, und geben Sie dabei die zu prüfenden Nachrichten nach **mailitem_id** oder **sent_status**an.</span><span class="sxs-lookup"><span data-stu-id="05ec1-114">Select from the **sysmail_allitems** table, specifying the messages of interest by **mailitem_id** or **sent_status**.</span></span>  
  
2.  <span data-ttu-id="05ec1-115">Um den von dem externen Programm zurückgegebenen Status für die E-Mail-Nachricht zu prüfen, verknüpfen Sie die **sysmail_allitems** -Sicht mit der **sysmail_event_log** -Sicht auf der **mailitem_id** -Spalte, wie im folgenden Abschnitt gezeigt.</span><span class="sxs-lookup"><span data-stu-id="05ec1-115">To check the status returned from the external program for the e-mail messages, join **sysmail_allitems** to **sysmail_event_log** view on the **mailitem_id** column, as shown in the following section.</span></span>  
  
     <span data-ttu-id="05ec1-116">Standardmäßig protokolliert das externe Programm keine Informationen zu Nachrichten, die erfolgreich gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="05ec1-116">By default, the external program does not log information about messages that were successfully sent.</span></span> <span data-ttu-id="05ec1-117">Um alle Nachrichten zu protokollieren, legen Sie die Protokolliergrad auf der Seite **Systemparameter konfigurieren** des **Assistenten zum Konfigurieren von Datenbank-E-Mail**auf 'Ausführlich' fest.</span><span class="sxs-lookup"><span data-stu-id="05ec1-117">To log all messages, set the logging level to verbose using the **Configure System Parameters** page of the **Database Mail Configuration Wizard.**</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="05ec1-118">Beispiel (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="05ec1-118">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="05ec1-119">Im folgenden Beispiel werden Informationen zu allen an `danw` gesendeten E-Mail-Nachrichten aufgelistet, die das externe Programm nicht erfolgreich senden konnte.</span><span class="sxs-lookup"><span data-stu-id="05ec1-119">The following example lists information about any e-mail messages sent to `danw` that the external program could not send successfully.</span></span> <span data-ttu-id="05ec1-120">Die Anweisung listet den Betreff, Datum und Uhrzeit, zu denen das Senden der Nachricht durch das externe Programm fehlgeschlagen ist, und die Fehlermeldung des Datenbank-E-Mail-Protokolls.</span><span class="sxs-lookup"><span data-stu-id="05ec1-120">The statement lists the subject, the date and time that the external program failed to send the message, and the error message from the Database Mail log.</span></span>  
  
```  
USE msdb ;  
GO  
  
-- Show the subject, the time that the mail item row was last  
-- modified, and the log information.  
-- Join sysmail_faileditems to sysmail_event_log   
-- on the mailitem_id column.  
-- In the WHERE clause list items where danw was in the recipients,  
-- copy_recipients, or blind_copy_recipients.  
-- These are the items that would have been sent  
-- to danw.  
  
SELECT items.subject,  
    items.last_mod_date  
    ,l.description FROM dbo.sysmail_faileditems as items  
INNER JOIN dbo.sysmail_event_log AS l  
    ON items.mailitem_id = l.mailitem_id  
WHERE items.recipients LIKE '%danw%'    
    OR items.copy_recipients LIKE '%danw%'   
    OR items.blind_copy_recipients LIKE '%danw%'  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="05ec1-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="05ec1-121">See Also</span></span>  
 [<span data-ttu-id="05ec1-122">Datenbank-E-Mail-Protokoll und -Überwachung</span><span class="sxs-lookup"><span data-stu-id="05ec1-122">Database Mail Log and Audits</span></span>](database-mail-log-and-audits.md)  
  
  
