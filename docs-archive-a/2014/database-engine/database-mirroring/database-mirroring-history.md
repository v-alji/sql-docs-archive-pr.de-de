---
title: Datenbankspiegelungsverlauf | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.dbmmonitor.databasemirroringhistory.f1
ms.assetid: 1d6e4b10-4a23-47d7-9918-c417992f09d3
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3e32ad9bfdce15413d89fbd5ba3d79a5ef14f7a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620510"
---
# <a name="database-mirroring-history"></a><span data-ttu-id="85e00-102">Datenbankspiegelungsverlauf</span><span class="sxs-lookup"><span data-stu-id="85e00-102">Database Mirroring History</span></span>
  <span data-ttu-id="85e00-103">Verwenden Sie dieses Dialogfeld, um den Verlauf des Spiegelungsstatus für eine gespiegelte Datenbank auf einer angegebenen Serverinstanz anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="85e00-103">Use this dialog box to view the history of mirroring status for a mirrored database on a specified server instance.</span></span>  
  
 <span data-ttu-id="85e00-104">**So verwenden Sie SQL Server Management Studio zum Überwachen der Datenbankspiegelung**</span><span class="sxs-lookup"><span data-stu-id="85e00-104">**To use SQL Server Management Studio to monitor database mirroring**</span></span>  
  
-   [<span data-ttu-id="85e00-105">Starten des Datenbankspiegelungs-Monitors &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="85e00-105">Start Database Mirroring Monitor &#40;SQL Server Management Studio&#41;</span></span>](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md)  
  
## <a name="options"></a><span data-ttu-id="85e00-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="85e00-106">Options</span></span>  
 <span data-ttu-id="85e00-107">**Serverinstanz**</span><span class="sxs-lookup"><span data-stu-id="85e00-107">**Server instance**</span></span>  
 <span data-ttu-id="85e00-108">Der Name der Serverinstanz, von der der Verlauf gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="85e00-108">Name of the server instance from which the history is being reported.</span></span>  
  
 <span data-ttu-id="85e00-109">**Datenbank**</span><span class="sxs-lookup"><span data-stu-id="85e00-109">**Database**</span></span>  
 <span data-ttu-id="85e00-110">Der Name der Datenbank, deren Verlauf angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="85e00-110">Name of the database whose history is being reported.</span></span>  
  
 <span data-ttu-id="85e00-111">**Liste filtern nach**</span><span class="sxs-lookup"><span data-stu-id="85e00-111">**Filter list by**</span></span>  
 <span data-ttu-id="85e00-112">Listet Filterwerte auf.</span><span class="sxs-lookup"><span data-stu-id="85e00-112">Lists filter values.</span></span> <span data-ttu-id="85e00-113">Durch Auswählen eines neuen Werts wird das Raster automatisch aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="85e00-113">Choosing a new value refreshes the grid automatically.</span></span>  
  
 <span data-ttu-id="85e00-114">Die folgenden Filterwerte sind möglich:</span><span class="sxs-lookup"><span data-stu-id="85e00-114">The possible filter values are:</span></span>  
  
-   <span data-ttu-id="85e00-115">Letzten zwei Stunden</span><span class="sxs-lookup"><span data-stu-id="85e00-115">Last two hours</span></span>  
  
-   <span data-ttu-id="85e00-116">Letzten vier Stunden</span><span class="sxs-lookup"><span data-stu-id="85e00-116">Last four hours</span></span>  
  
-   <span data-ttu-id="85e00-117">Letzten acht Stunden</span><span class="sxs-lookup"><span data-stu-id="85e00-117">Last eight hours</span></span>  
  
-   <span data-ttu-id="85e00-118">Letzter Tag</span><span class="sxs-lookup"><span data-stu-id="85e00-118">Last day</span></span>  
  
-   <span data-ttu-id="85e00-119">Letzten zwei Tage</span><span class="sxs-lookup"><span data-stu-id="85e00-119">Last two days</span></span>  
  
-   <span data-ttu-id="85e00-120">Letzten 100 Datensätze</span><span class="sxs-lookup"><span data-stu-id="85e00-120">Last 100 records</span></span>  
  
-   <span data-ttu-id="85e00-121">Letzten 500 Datensätze</span><span class="sxs-lookup"><span data-stu-id="85e00-121">Last 500 records</span></span>  
  
-   <span data-ttu-id="85e00-122">Letzten 1000 Datensätze</span><span class="sxs-lookup"><span data-stu-id="85e00-122">Last 1000 records</span></span>  
  
-   <span data-ttu-id="85e00-123">Alle Datensätze</span><span class="sxs-lookup"><span data-stu-id="85e00-123">All records</span></span>  
  
 <span data-ttu-id="85e00-124">**Aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="85e00-124">**Refresh**</span></span>  
 <span data-ttu-id="85e00-125">Klicken Sie auf diese Schaltfläche, um die Verlaufsliste zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="85e00-125">Click to refresh the history list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="85e00-126">Die Verlaufsliste in diesem Dialogfeld wird nicht automatisch aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="85e00-126">This dialog box does not automatically refresh the history list.</span></span> <span data-ttu-id="85e00-127">Klicken Sie entweder auf **Aktualisieren** , oder wählen Sie eine andere Filteroption aus, um die Liste zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="85e00-127">To refresh the list, either click **Refresh** or choose another filter option.</span></span> <span data-ttu-id="85e00-128">Nur Mitglieder der festen Serverrolle **sysadmin** können den Spiegelungsverlauf aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="85e00-128">Only members of the **sysadmin** fixed server role can update the mirroring history.</span></span>  
  
 <span data-ttu-id="85e00-129">**History**</span><span class="sxs-lookup"><span data-stu-id="85e00-129">**History**</span></span>  
 <span data-ttu-id="85e00-130">Zeigt die Verlaufsliste an.</span><span class="sxs-lookup"><span data-stu-id="85e00-130">Displays the history list.</span></span> <span data-ttu-id="85e00-131">Wenn Sie auf einen Spaltenheader klicken, wird das Raster nach der entsprechenden Spalte sortiert.</span><span class="sxs-lookup"><span data-stu-id="85e00-131">Clicking on a column header sorts the grid by that column.</span></span> <span data-ttu-id="85e00-132">Die Liste enthält folgende Spalten:</span><span class="sxs-lookup"><span data-stu-id="85e00-132">The list contains the following columns:</span></span>  
  
|<span data-ttu-id="85e00-133">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="85e00-133">Column name</span></span>|<span data-ttu-id="85e00-134">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="85e00-134">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="85e00-135">**Aufgezeichnete Zeit**</span><span class="sxs-lookup"><span data-stu-id="85e00-135">**Time Recorded**</span></span>|<span data-ttu-id="85e00-136">Timestamp der Verlaufszeile.</span><span class="sxs-lookup"><span data-stu-id="85e00-136">Timestamp of the history row.</span></span>|  
|<span data-ttu-id="85e00-137">**Rolle**</span><span class="sxs-lookup"><span data-stu-id="85e00-137">**Role**</span></span>|<span data-ttu-id="85e00-138">Die aktuelle Spiegelungsrolle der Serverinstanz für diese Datenbank: Prinzipal oder Spiegel.</span><span class="sxs-lookup"><span data-stu-id="85e00-138">Current mirroring role of the server instance for this database, either Principal or Mirror.</span></span>|  
|<span data-ttu-id="85e00-139">**Spiegelungsstatus**</span><span class="sxs-lookup"><span data-stu-id="85e00-139">**Mirroring State**</span></span>|<span data-ttu-id="85e00-140">Status der Datenbank:</span><span class="sxs-lookup"><span data-stu-id="85e00-140">State of the database:</span></span><br /><br /> <span data-ttu-id="85e00-141">Getrennt</span><span class="sxs-lookup"><span data-stu-id="85e00-141">Disconnected</span></span><br /><br /> <span data-ttu-id="85e00-142">Ausstehendes Failover</span><span class="sxs-lookup"><span data-stu-id="85e00-142">Pending Failover</span></span><br /><br /> <span data-ttu-id="85e00-143">Ausgesetzt</span><span class="sxs-lookup"><span data-stu-id="85e00-143">Suspended</span></span><br /><br /> <span data-ttu-id="85e00-144">Synchronisiert</span><span class="sxs-lookup"><span data-stu-id="85e00-144">Synchronized</span></span><br /><br /> <span data-ttu-id="85e00-145">Wird synchronisiert</span><span class="sxs-lookup"><span data-stu-id="85e00-145">Synchronizing</span></span><br /><br /> <span data-ttu-id="85e00-146">Unknown</span><span class="sxs-lookup"><span data-stu-id="85e00-146">Unknown</span></span>|  
|<span data-ttu-id="85e00-147">**Zeugenverbindung**</span><span class="sxs-lookup"><span data-stu-id="85e00-147">**Witness Connection**</span></span>|<span data-ttu-id="85e00-148">Status der Zeugenverbindung in der Spiegelungssitzung der Datenbank: Verbunden oder Getrennt.</span><span class="sxs-lookup"><span data-stu-id="85e00-148">State of the witness connection in the mirroring session of the database, either Connected or Disconnected.</span></span> <span data-ttu-id="85e00-149">Wenn kein Zeuge vorhanden ist, ist der Wert NULL.</span><span class="sxs-lookup"><span data-stu-id="85e00-149">If there is no witness, the value is NULL.</span></span>|  
|<span data-ttu-id="85e00-150">**Nicht gesendetes Protokoll**</span><span class="sxs-lookup"><span data-stu-id="85e00-150">**Unsent Log**</span></span>|<span data-ttu-id="85e00-151">Größe, in Kilobyte (KB), des nicht gesendeten Protokolls in der Sendewarteschlange auf der Prinzipalserverinstanz.</span><span class="sxs-lookup"><span data-stu-id="85e00-151">Size, in kilobytes (KB), of the unsent log in the send queue on the principal server instance.</span></span>|  
|<span data-ttu-id="85e00-152">**Sendezeit**</span><span class="sxs-lookup"><span data-stu-id="85e00-152">**Time to Send**</span></span>|<span data-ttu-id="85e00-153">Die ungefähre Dauer der Zeit, die die Prinzipalserverinstanz benötigt, um das derzeit in der Sendewarteschlange befindliche Protokoll an die Spiegelserverinstanz zu senden (die *Senderate*).</span><span class="sxs-lookup"><span data-stu-id="85e00-153">Approximate amount of time the principal server instance will require to send the log that is currently in the send queue to the mirror server instance (the *send rate*).</span></span> <span data-ttu-id="85e00-154">Da die Rate der eingehenden Transaktionen erheblich schwanken kann, handelt es sich bei der Protokollsendezeit um einen Schätzwert.</span><span class="sxs-lookup"><span data-stu-id="85e00-154">Because the rate of incoming transactions can vary significantly, the time to send log is an estimate.</span></span> <span data-ttu-id="85e00-155">Die Senderate kann jedoch nützlich sein, um die für ein manuelles Failover erforderliche Zeit grob zu schätzen.</span><span class="sxs-lookup"><span data-stu-id="85e00-155">However, the send rate can be useful for roughly estimating the time required for a manual failover.</span></span>|  
|<span data-ttu-id="85e00-156">**Send Rate**</span><span class="sxs-lookup"><span data-stu-id="85e00-156">**Send Rate**</span></span>|<span data-ttu-id="85e00-157">Rate, in KB pro Sekunde, mit der Transaktionen an die Spiegelserverinstanz gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="85e00-157">Rate at which transactions are being sent to the mirror server instance, in KB per second.</span></span>|  
|<span data-ttu-id="85e00-158">**Neue Transaktionsrate**</span><span class="sxs-lookup"><span data-stu-id="85e00-158">**New Transaction Rate**</span></span>|<span data-ttu-id="85e00-159">Rate, in KB pro Sekunde, mit der eingehende Transaktionen in das Protokoll des Prinzipals eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="85e00-159">Rate at which incoming transactions are being entered into the principal's log, in KB per second.</span></span> <span data-ttu-id="85e00-160">Vergleichen Sie diesen Wert mit dem Wert **Sendezeit** , um zu bestimmen, ob die Spiegelung im Rückstand ist, einen Vorsprung hat oder auf dem aktuellen Stand ist.</span><span class="sxs-lookup"><span data-stu-id="85e00-160">To determine whether mirroring is falling behind, staying up, or catching up, compare this value to the **Time to Send** value.</span></span>|  
|<span data-ttu-id="85e00-161">**Älteste, nicht gesendete Transaktion**</span><span class="sxs-lookup"><span data-stu-id="85e00-161">**Oldest Unsent Transaction**</span></span>|<span data-ttu-id="85e00-162">Alter der ältesten, nicht gesendeten Transaktion in der Sendewarteschlange.</span><span class="sxs-lookup"><span data-stu-id="85e00-162">Age of the oldest unsent transaction in the send queue.</span></span> <span data-ttu-id="85e00-163">Das Alter dieser Transaktion gibt an, wie viele Minuten an Transaktionen noch nicht an die Spiegelserverinstanz gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="85e00-163">The age of this transaction indicates how many minutes of transactions have not yet been sent to the mirror server instance.</span></span> <span data-ttu-id="85e00-164">Dieser Wert hilft, das Datenverlustrisiko in Bezug auf die Zeit zu messen.</span><span class="sxs-lookup"><span data-stu-id="85e00-164">This value helps measure the potential for data loss in terms of time.</span></span>|  
|<span data-ttu-id="85e00-165">**Nicht wiederhergestelltes Protokoll**</span><span class="sxs-lookup"><span data-stu-id="85e00-165">**Unrestored Log**</span></span>|<span data-ttu-id="85e00-166">Die Menge der Protokolldaten in KB, die sich in der Wiederholungswarteschlange befinden.</span><span class="sxs-lookup"><span data-stu-id="85e00-166">The amount of log waiting in the redo queue, in KB.</span></span>|  
|<span data-ttu-id="85e00-167">**Wiederherstellungszeit**</span><span class="sxs-lookup"><span data-stu-id="85e00-167">**Time to Restore**</span></span>|<span data-ttu-id="85e00-168">Die geschätzte Anzahl von Minuten, die erforderlich ist, um das Protokoll, das sich derzeit in der Wiederholungswarteschlange befindet, auf die Spiegeldatenbank anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="85e00-168">Approximate number of minutes required for the log currently in the redo queue to be applied to the mirror database.</span></span>|  
|<span data-ttu-id="85e00-169">**Wiederherstellungsrate**</span><span class="sxs-lookup"><span data-stu-id="85e00-169">**Restore Rate**</span></span>|<span data-ttu-id="85e00-170">Rate, in KB pro Sekunde, mit der Transaktionen in der Spiegeldatenbank wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="85e00-170">Rate at which transactions are being restored into the mirror database, in KB per second.</span></span>|  
|<span data-ttu-id="85e00-171">**Spiegelungscommitaufwand**</span><span class="sxs-lookup"><span data-stu-id="85e00-171">**Mirror Commit Overhead**</span></span>|<span data-ttu-id="85e00-172">Durchschnittliche Verzögerung pro Transaktion in Millisekunden (nur im synchronen Modi).</span><span class="sxs-lookup"><span data-stu-id="85e00-172">Average delay per transaction in milliseconds (only in synchronous modes).</span></span> <span data-ttu-id="85e00-173">Hierbei handelt es sich um die Verzögerung, die entsteht, während die Prinzipalserverinstanz darauf wartet, dass die Spiegelserverinstanz den Transaktionsprotokolldatensatz in die Wiederholungswarteschlange schreibt.</span><span class="sxs-lookup"><span data-stu-id="85e00-173">This delay is the amount of overhead incurred while the principal server instance waits for the mirror server instance to write the transaction's log record into the redo queue.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="85e00-174">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="85e00-174">See Also</span></span>  
 <span data-ttu-id="85e00-175">[Starten des Datenbankspiegelungs-Monitors &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="85e00-175">[Start Database Mirroring Monitor &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span></span>  
 <span data-ttu-id="85e00-176">[Überwachen der Datenbankspiegelung &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="85e00-176">[Monitoring Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="85e00-177">Starten des Assistenten zum Konfigurieren der Sicherheit für die Datenbankspiegelung &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="85e00-177">Start the Configuring Database Mirroring Security Wizard &#40;SQL Server Management Studio&#41;</span></span>](start-the-configuring-database-mirroring-security-wizard.md)  
  
  
