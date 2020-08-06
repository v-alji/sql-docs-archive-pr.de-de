---
title: Informationen zum Protokollversand (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- secondary servers [SQL Server]
- log shipping [SQL Server], jobs
- copy jobs [SQL Server]
- primary databases [SQL Server]
- log shipping [SQL Server], monitoring
- log shipping [SQL Server], about log shipping
- alert jobs [SQL Server]
- availability [SQL Server]
- jobs [SQL Server], log shipping
- monitor servers [SQL Server]
- restore jobs [SQL Server]
- log shipping [SQL Server]
- backup jobs [SQL Server]
- primary servers [SQL Server]
ms.assetid: 55da6b94-3a4b-4bae-850f-4bf7f6e918ca
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cbf36e0ddd94ec0ab0a40a448e50602decfc0645
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698493"
---
# <a name="about-log-shipping-sql-server"></a><span data-ttu-id="2de29-102">Informationen zum Protokollversand (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="2de29-102">About Log Shipping (SQL Server)</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="2de29-103">-Protokollversand können Sie automatisch Transaktionsprotokollsicherungen von einer *primären Datenbank* auf einer Instanz eines *primären Servers* an eine oder mehrere *sekundäre Datenbanken* auf separaten Instanzen eines *sekundären Servers* senden.</span><span class="sxs-lookup"><span data-stu-id="2de29-103">Log shipping allows you to automatically send transaction log backups from a *primary database* on a *primary server* instance to one or more *secondary databases* on separate *secondary server* instances.</span></span> <span data-ttu-id="2de29-104">Die Transaktionsprotokollsicherungen werden einzeln auf jede der sekundären Datenbanken angewendet.</span><span class="sxs-lookup"><span data-stu-id="2de29-104">The transaction log backups are applied to each of the secondary databases individually.</span></span> <span data-ttu-id="2de29-105">Eine optionale dritte Serverinstanz, die als *Überwachungsserver*bezeichnet wird, zeichnet den Verlauf und den Status von Sicherungs- und Wiederherstellungsvorgängen auf und löst optional Warnungen aus, falls diese Vorgänge nicht wie geplant ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="2de29-105">An optional third server instance, known as the *monitor server*, records the history and status of backup and restore operations and, optionally, raises alerts if these operations fail to occur as scheduled.</span></span>  
  
 <span data-ttu-id="2de29-106">**In diesem Thema:**</span><span class="sxs-lookup"><span data-stu-id="2de29-106">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="2de29-107">Vorteile</span><span class="sxs-lookup"><span data-stu-id="2de29-107">Benefits</span></span>](#Benefits)  
  
-   [<span data-ttu-id="2de29-108">Begriffe und Definitionen</span><span class="sxs-lookup"><span data-stu-id="2de29-108">Terms and Definitions</span></span>](#TermsAndDefinitions)  
  
-   [<span data-ttu-id="2de29-109">Übersicht über den Protokollversand</span><span class="sxs-lookup"><span data-stu-id="2de29-109">Log Shipping Overview</span></span>](#ComponentsAndConcepts)  
  
-   [<span data-ttu-id="2de29-110">Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="2de29-110">Interoperability</span></span>](#Interoperability)  
  
-   [<span data-ttu-id="2de29-111">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="2de29-111">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="benefits"></a><a name="Benefits"></a> <span data-ttu-id="2de29-112">Vorteile</span><span class="sxs-lookup"><span data-stu-id="2de29-112">Benefits</span></span>  
  
-   <span data-ttu-id="2de29-113">Stellt eine Lösung für die Wiederherstellung im Notfall für eine einzelne primäre Datenbank und eine oder mehrere sekundäre Datenbanken bereit, jede auf einer separaten Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2de29-113">Provides a disaster-recovery solution for a single primary database and one or more secondary databases, each on a separate instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="2de29-114">Unterstützt beschränkten schreibgeschützten Zugriff auf sekundäre Datenbanken (während des Intervalls zwischen Wiederherstellungsaufträgen).</span><span class="sxs-lookup"><span data-stu-id="2de29-114">Supports limited read-only access to secondary databases (during the interval between restore jobs).</span></span>  
  
-   <span data-ttu-id="2de29-115">Ermöglicht eine vom Benutzer angegebene Verzögerung zwischen dem Zeitpunkt, zu dem der primäre Server das Protokoll der primären Datenbank sichert, und dem Zeitpunkt, zu dem die sekundären Server die Protokollsicherung wiederherstellen (anwenden) müssen.</span><span class="sxs-lookup"><span data-stu-id="2de29-115">Allows a user-specified delay between when the primary server backs up the log of the primary database and when the secondary servers must restore (apply) the log backup.</span></span> <span data-ttu-id="2de29-116">Eine längere Verzögerung kann nützlich sein, wenn z. B. versehentlich Daten in der primären Datenbank geändert werden.</span><span class="sxs-lookup"><span data-stu-id="2de29-116">A longer delay can be useful, for example, if data is accidentally changed on the primary database.</span></span> <span data-ttu-id="2de29-117">Wenn die versehentliche Änderung schnell bemerkt wird, kann eine Verzögerung es Ihnen ermöglichen, die noch unveränderten Daten von einer sekundären Datenbank abzurufen, bevor die Änderung dort widergespiegelt wird.</span><span class="sxs-lookup"><span data-stu-id="2de29-117">If the accidental change is noticed quickly, a delay can let you retrieve still unchanged data from a secondary database before the change is reflected there.</span></span>  
  
##  <a name="terms-and-definitions"></a><a name="TermsAndDefinitions"></a> <span data-ttu-id="2de29-118">Begriffe und Definitionen</span><span class="sxs-lookup"><span data-stu-id="2de29-118">Terms and Definitions</span></span>  
 <span data-ttu-id="2de29-119">primären Servers</span><span class="sxs-lookup"><span data-stu-id="2de29-119">primary server</span></span>  
 <span data-ttu-id="2de29-120">Die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , die der Produktionsserver ist.</span><span class="sxs-lookup"><span data-stu-id="2de29-120">The instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is your production server.</span></span>  
  
 <span data-ttu-id="2de29-121">primäre Datenbank</span><span class="sxs-lookup"><span data-stu-id="2de29-121">primary database</span></span>  
 <span data-ttu-id="2de29-122">Die Datenbank auf dem primären Server, die Sie auf einem anderen Server sichern möchten.</span><span class="sxs-lookup"><span data-stu-id="2de29-122">The database on the primary server that you want to back up to another server.</span></span> <span data-ttu-id="2de29-123">Die gesamte Verwaltung der Protokollversandkonfiguration über [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] erfolgt von der primären Datenbank aus.</span><span class="sxs-lookup"><span data-stu-id="2de29-123">All administration of the log shipping configuration through [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] is performed from the primary database.</span></span>  
  
 <span data-ttu-id="2de29-124">sekundären Servers</span><span class="sxs-lookup"><span data-stu-id="2de29-124">secondary server</span></span>  
 <span data-ttu-id="2de29-125">Die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , auf der Sie eine betriebsbereite Standby-Kopie der primären Datenbank bereithalten möchten.</span><span class="sxs-lookup"><span data-stu-id="2de29-125">The instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] where you want to keep a warm standby copy of your primary database.</span></span>  
  
 <span data-ttu-id="2de29-126">Sekundäre Datenbank</span><span class="sxs-lookup"><span data-stu-id="2de29-126">secondary database</span></span>  
 <span data-ttu-id="2de29-127">Die betriebsbereite Standby-Kopie der primären Datenbank.</span><span class="sxs-lookup"><span data-stu-id="2de29-127">The warm standby copy of the primary database.</span></span> <span data-ttu-id="2de29-128">Sie sekundäre Datenbank kann sich im Status RECOVERING oder STANDBY befinden, in dem die Datenbank für den eingeschränkten schreibgeschützten Zugriff verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="2de29-128">The secondary database may be in either the RECOVERING state or the STANDBY state, which leaves the database available for limited read-only access.</span></span>  
  
 <span data-ttu-id="2de29-129">Überwachungsserver</span><span class="sxs-lookup"><span data-stu-id="2de29-129">monitor server</span></span>  
 <span data-ttu-id="2de29-130">Eine optionale Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , die alle Informationen zum Protokollversand nachverfolgt:</span><span class="sxs-lookup"><span data-stu-id="2de29-130">An optional instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that tracks all of the details of log shipping, including:</span></span>  
  
-   <span data-ttu-id="2de29-131">Wann das Transaktionsprotokoll in der primären Datenbank zuletzt gesichert wurde.</span><span class="sxs-lookup"><span data-stu-id="2de29-131">When the transaction log on the primary database was last backed up.</span></span>  
  
-   <span data-ttu-id="2de29-132">Wann die Sicherungsdateien zuletzt von den sekundären Servern kopiert und wiederhergestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="2de29-132">When the secondary servers last copied and restored the backup files.</span></span>  
  
-   <span data-ttu-id="2de29-133">Informationen zu Sicherungsfehlerwarnungen.</span><span class="sxs-lookup"><span data-stu-id="2de29-133">Information about any backup failure alerts.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2de29-134">Nach dem Konfigurieren des Überwachungsservers kann dieser nicht ohne vorhergehendes Entfernen des Protokollversands geändert werden.</span><span class="sxs-lookup"><span data-stu-id="2de29-134">Once the monitor server has been configured, it cannot be changed without removing log shipping first.</span></span>  
  
 <span data-ttu-id="2de29-135">Sicherungsauftrag</span><span class="sxs-lookup"><span data-stu-id="2de29-135">backup job</span></span>  
 <span data-ttu-id="2de29-136">Ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Auftrag, der den Sicherungsvorgang ausführt, den Verlauf auf dem lokalen Server und dem Überwachungsserver protokolliert und veraltete Sicherungsdateien und Verlaufsinformationen löscht.</span><span class="sxs-lookup"><span data-stu-id="2de29-136">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job that  performs the backup operation, logs history to the local server and the monitor server, and deletes old backup files and history information.</span></span> <span data-ttu-id="2de29-137">Wenn der Protokollversand aktiviert ist, wird die Auftragskategorie "Protokollversandsicherung" in der primären Serverinstanz erstellt.</span><span class="sxs-lookup"><span data-stu-id="2de29-137">When log shipping is enabled, the job category "Log Shipping Backup" is created on the primary server instance.</span></span>  
  
 <span data-ttu-id="2de29-138">Kopierauftrag</span><span class="sxs-lookup"><span data-stu-id="2de29-138">copy job</span></span>  
 <span data-ttu-id="2de29-139">Ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Auftrag, der die Sicherungsdateien vom primären Server in ein konfigurierbares Ziel auf dem sekundären Server kopiert und den Verlauf auf dem sekundären Server und dem Überwachungsserver protokolliert.</span><span class="sxs-lookup"><span data-stu-id="2de29-139">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job that copies the backup files from the primary server to a configurable destination on the secondary server and logs history on the secondary server and the monitor server.</span></span> <span data-ttu-id="2de29-140">Wenn der Protokollversand auf einer Datenbank aktiviert ist, wird die Auftragskategorie "Protokollversandkopie" in jeder sekundären Serverinstanz in einer Protokollversandkonfiguration erstellt.</span><span class="sxs-lookup"><span data-stu-id="2de29-140">When log shipping is enabled on a database, the job category "Log Shipping Copy" is created on each secondary server in a log shipping configuration.</span></span>  
  
 <span data-ttu-id="2de29-141">Wiederherstellungsauftrag</span><span class="sxs-lookup"><span data-stu-id="2de29-141">restore job</span></span>  
 <span data-ttu-id="2de29-142">Ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Auftrag, der die kopierten Sicherungsdateien in den sekundären Datenbanken wiederherstellt.</span><span class="sxs-lookup"><span data-stu-id="2de29-142">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job that restores the copied backup files to the secondary databases.</span></span> <span data-ttu-id="2de29-143">Er protokolliert den Verlauf auf dem lokalen Server und dem Überwachungsserver und löscht veraltete Dateien und Verlaufsinformationen.</span><span class="sxs-lookup"><span data-stu-id="2de29-143">It logs history on the local server and the monitor server, and deletes old files and old history information.</span></span> <span data-ttu-id="2de29-144">Wenn der Protokollversand in einer Datenbank aktiviert ist, wird die Auftragskategorie "Protokollversandwiederherstellung" in der sekundären Serverinstanz erstellt.</span><span class="sxs-lookup"><span data-stu-id="2de29-144">When log shipping is enabled on a database, the job category "Log Shipping Restore" is created on the secondary server instance.</span></span>  
  
 <span data-ttu-id="2de29-145">Warnungsauftrag</span><span class="sxs-lookup"><span data-stu-id="2de29-145">alert job</span></span>  
 <span data-ttu-id="2de29-146">Ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Auftrag, der Warnungen für primäre und sekundäre Datenbanken auslöst, wenn ein Sicherungs- oder ein Wiederherstellungsvorgang nicht erfolgreich innerhalb eines angegebenen Schwellenwerts abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="2de29-146">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job that raises alerts for primary and secondary databases when a backup or restore operation does not complete successfully within a specified threshold.</span></span> <span data-ttu-id="2de29-147">Wenn der Protokollversand in einer Datenbank aktiviert ist, wird die Auftragskategorie "Protokollversandwarnung"in der Überwachungsserverinstanz erstellt.</span><span class="sxs-lookup"><span data-stu-id="2de29-147">When log shipping is enabled on a database, job category "Log Shipping Alert" is created on the monitor server instance.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="2de29-148">Für jede Warnung müssen Sie eine Warnungsnummer angeben.</span><span class="sxs-lookup"><span data-stu-id="2de29-148">For each alert, you need to specify an alert number.</span></span> <span data-ttu-id="2de29-149">Stellen Sie sicher auch sicher, dass die Warnung zum Benachrichtigen eines Bedieners konfiguriert ist, wenn eine Warnung ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="2de29-149">Also, be sure to configure the alert to notify an operator when an alert is raised.</span></span>  
  
##  <a name="log-shipping-overview"></a><a name="ComponentsAndConcepts"></a> <span data-ttu-id="2de29-150">Übersicht über den Protokollversand</span><span class="sxs-lookup"><span data-stu-id="2de29-150">Log Shipping Overview</span></span>  
 <span data-ttu-id="2de29-151">Der Protokollversand besteht aus drei Vorgängen:</span><span class="sxs-lookup"><span data-stu-id="2de29-151">Log shipping consists of three operations:</span></span>  
  
1.  <span data-ttu-id="2de29-152">Sichern des Transaktionsprotokolls auf der primären Serverinstanz.</span><span class="sxs-lookup"><span data-stu-id="2de29-152">Back up the transaction log at the primary server instance.</span></span>  
  
2.  <span data-ttu-id="2de29-153">Kopieren der Transaktionsprotokolldatei auf die sekundäre Serverinstanz.</span><span class="sxs-lookup"><span data-stu-id="2de29-153">Copy the transaction log file to the secondary server instance.</span></span>  
  
3.  <span data-ttu-id="2de29-154">Wiederherstellen der Protokollsicherung auf der sekundären Serverinstanz.</span><span class="sxs-lookup"><span data-stu-id="2de29-154">Restore the log backup on the secondary server instance.</span></span>  
  
 <span data-ttu-id="2de29-155">Das Protokoll kann an mehrere sekundäre Serverinstanzen versendet werden.</span><span class="sxs-lookup"><span data-stu-id="2de29-155">The log can be shipped to multiple secondary server instances.</span></span> <span data-ttu-id="2de29-156">In diesen Fällen werden die Schritte 2 und 3 für jede sekundäre Serverinstanz dupliziert.</span><span class="sxs-lookup"><span data-stu-id="2de29-156">In such cases, operations 2 and 3 are duplicated for each secondary server instance.</span></span>  
  
 <span data-ttu-id="2de29-157">Für eine Protokollversandkonfiguration wird nicht automatisch ein Failover vom primären Server zum sekundären Server ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2de29-157">A log shipping configuration does not automatically fail over from the primary server to the secondary server.</span></span> <span data-ttu-id="2de29-158">Falls die primäre Datenbank nicht mehr verfügbar ist, kann eine der sekundären Datenbanken manuell online geschaltet werden.</span><span class="sxs-lookup"><span data-stu-id="2de29-158">If the primary database becomes unavailable, any of the secondary databases can be brought online manually.</span></span>  
  
 <span data-ttu-id="2de29-159">Sie können eine sekundäre Datenbank für Berichtszwecke verwenden.</span><span class="sxs-lookup"><span data-stu-id="2de29-159">You can use a secondary database for reporting purposes.</span></span>  
  
 <span data-ttu-id="2de29-160">Darüber hinaus können Sie Warnungen für die Protokollversandkonfiguration konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="2de29-160">In addition, you can configure alerts for your log shipping configuration.</span></span>  
  
### <a name="a-typical-log-shipping-configuration"></a><span data-ttu-id="2de29-161">A Typische Protokollversandkonfiguration</span><span class="sxs-lookup"><span data-stu-id="2de29-161">A Typical Log Shipping Configuration</span></span>  
 <span data-ttu-id="2de29-162">In der folgenden Abbildung wird eine Protokollversandkonfiguration mit der primären Serverinstanz, drei sekundären Serverinstanzen und einer Überwachungsserverinstanz dargestellt.</span><span class="sxs-lookup"><span data-stu-id="2de29-162">The following figure shows a log shipping configuration with the primary server instance, three secondary server instances, and a monitor server instance.</span></span> <span data-ttu-id="2de29-163">In der Abbildung werden die Schritte, die vom Sicherungs-, Kopier- und Wiederherstellungsauftrag ausgeführt werden, folgendermaßen veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="2de29-163">The figure illustrates the steps performed by backup, copy, and restorejobs, as follows:</span></span>  
  
1.  <span data-ttu-id="2de29-164">Die primäre Serverinstanz führt den Sicherungsauftrag aus, um das Transaktionsprotokoll in der primären Datenbank zu sichern.</span><span class="sxs-lookup"><span data-stu-id="2de29-164">The primary server instance runs the backup job to back up the transaction log on the primary database.</span></span> <span data-ttu-id="2de29-165">Diese Serverinstanz speichert die Protokollsicherung dann in einer primären Protokollsicherungsdatei, die an den Sicherungsordner gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="2de29-165">This server instance then places the log backup into a primary log-backup file, which it sends to the backup folder.</span></span>  <span data-ttu-id="2de29-166">In dieser Abbildung befindet sich der Sicherungsordner in einem freigegebenen Verzeichnis, der *Sicherungsfreigabe*.</span><span class="sxs-lookup"><span data-stu-id="2de29-166">In this figure, the backup folder is on a shared directory-the *backup share*.</span></span>  
  
2.  <span data-ttu-id="2de29-167">Jede der drei sekundären Serverinstanzen führt einen eigenen Kopierauftrag aus, um die primäre Protokollsicherungsdatei in ihren eigenen lokalen Zielordner zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="2de29-167">Each of the three secondary server instances runs its own copy job to copy the primary log-backup file to its own local destination folder.</span></span>  
  
3.  <span data-ttu-id="2de29-168">Jede sekundäre Serverinstanz führt einen eigenen Wiederherstellungsauftrag aus, um die Protokollsicherung aus dem lokalen Zielordner in der lokalen sekundären Datenbank wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="2de29-168">Each secondary server instance runs its own restore job to restore the log backup from the local destination folder onto the local secondary database.</span></span>  
  
 <span data-ttu-id="2de29-169">Die primäre Serverinstanz und die sekundäre Serverinstanz senden ihre eigenen Verlaufs- und Statusinformationen an die Überwachungsserverinstanz.</span><span class="sxs-lookup"><span data-stu-id="2de29-169">The primary and secondary server instances send their own history and status to the monitor server instance.</span></span>  
  
 <span data-ttu-id="2de29-170">![Konfiguration, die Sicherungs-, Kopier- & Wiederherstellungsaufträge anzeigt](../media/ls-typical-configuration.gif "Konfiguration, die Sicherungs-, Kopier- & Wiederherstellungsaufträge anzeigt")</span><span class="sxs-lookup"><span data-stu-id="2de29-170">![Configuration showing backup, copy, & restore jobs](../media/ls-typical-configuration.gif "Configuration showing backup, copy, & restore jobs")</span></span>  
  
##  <a name="interoperability"></a><a name="Interoperability"></a> <span data-ttu-id="2de29-171">Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="2de29-171">Interoperability</span></span>  
 <span data-ttu-id="2de29-172">Der Protokollversand kann mit den folgenden Funktionen oder Komponenten von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="2de29-172">Log shipping can be used with the following features or components of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   [<span data-ttu-id="2de29-173">Voraussetzungen für das Migrieren vom Protokoll Versand zu AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2de29-173">Prerequisites for Migrating from Log Shipping to AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](../availability-groups/windows/prereqs-migrating-log-shipping-to-always-on-availability-groups.md)  
  
-   [<span data-ttu-id="2de29-174">Datenbankspiegelung und Protokollversand &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2de29-174">Database Mirroring and Log Shipping &#40;SQL Server&#41;</span></span>](../database-mirroring/database-mirroring-and-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="2de29-175">Protokollversand und Replikation &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2de29-175">Log Shipping and Replication &#40;SQL Server&#41;</span></span>](log-shipping-and-replication-sql-server.md)  
  
> [!NOTE]  
>  [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] <span data-ttu-id="2de29-176">und Datenbankspiegelung schließen sich gegenseitig aus.</span><span class="sxs-lookup"><span data-stu-id="2de29-176">and database mirroring are mutually exclusive.</span></span> <span data-ttu-id="2de29-177">Eine Datenbank, die für eine dieser Funktionen konfiguriert ist, kann nicht für die andere konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="2de29-177">A database that is configured for one of these features cannot be configured for the other.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="2de29-178">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="2de29-178">Related Tasks</span></span>  
  
-   [<span data-ttu-id="2de29-179">Aktualisieren des Protokoll Versands auf SQL Server 2014 &#40;Transact-SQL-&#41;</span><span class="sxs-lookup"><span data-stu-id="2de29-179">Upgrade Log Shipping to SQL Server 2014 &#40;Transact-SQL&#41;</span></span>](upgrading-log-shipping-to-sql-server-2016-transact-sql.md)  
  
-   [<span data-ttu-id="2de29-180">Konfigurieren des Protokollversands &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2de29-180">Configure Log Shipping &#40;SQL Server&#41;</span></span>](configure-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="2de29-181">Hinzufügen einer sekundären Datenbank zu einer Protokollversandkonfiguration &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2de29-181">Add a Secondary Database to a Log Shipping Configuration &#40;SQL Server&#41;</span></span>](add-a-secondary-database-to-a-log-shipping-configuration-sql-server.md)  
  
-   [<span data-ttu-id="2de29-182">Entfernen einer sekundären Datenbank aus einer Protokollversandkonfiguration &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2de29-182">Remove a Secondary Database from a Log Shipping Configuration &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-a-log-shipping-configuration-sql-server.md)  
  
-   [<span data-ttu-id="2de29-183">Entfernen des Protokollversands &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2de29-183">Remove Log Shipping &#40;SQL Server&#41;</span></span>](remove-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="2de29-184">Anzeigen des Protokollversandberichts &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="2de29-184">View the Log Shipping Report &#40;SQL Server Management Studio&#41;</span></span>](view-the-log-shipping-report-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="2de29-185">Überwachen des Protokollversands &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2de29-185">Monitor Log Shipping &#40;Transact-SQL&#41;</span></span>](monitor-log-shipping-transact-sql.md)  
  
-   [<span data-ttu-id="2de29-186">Failover zu einer sekundären Datenbank für den Protokollversand &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2de29-186">Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;</span></span>](fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
-   [<span data-ttu-id="2de29-187">Failover zu einer sekundären Datenbank für den Protokollversand &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2de29-187">Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;</span></span>](fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
-   [<span data-ttu-id="2de29-188">Verwaltung von Anmeldenamen und Aufträgen nach einem Rollenwechsel &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2de29-188">Management of Logins and Jobs After Role Switching &#40;SQL Server&#41;</span></span>](../../sql-server/failover-clusters/management-of-logins-and-jobs-after-role-switching-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="2de29-189">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2de29-189">See Also</span></span>  
 [<span data-ttu-id="2de29-190">Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2de29-190">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](../availability-groups/windows/overview-of-always-on-availability-groups-sql-server.md)  
  
  
