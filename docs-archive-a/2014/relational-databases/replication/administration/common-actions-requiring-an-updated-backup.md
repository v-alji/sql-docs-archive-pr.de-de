---
title: Häufige Aktionen, die eine aktualisierte Sicherung erfordern | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- recovery [SQL Server replication], actions requiring a backup
- restoring [SQL Server replication], actions requiring a backup
- backups [SQL Server replication], actions requiring a backup
ms.assetid: a5975bf4-183e-42e3-b7d1-ad02f89d2e1d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3eb10bdca8ee188f7b322a46665c38129d57052b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696714"
---
# <a name="common-actions-requiring-an-updated-backup"></a><span data-ttu-id="595fa-102">Häufige Aktionen, die eine aktualisierte Sicherung erfordern</span><span class="sxs-lookup"><span data-stu-id="595fa-102">Common Actions Requiring an Updated Backup</span></span>
  <span data-ttu-id="595fa-103">Wenn Sie regelmäßige Protokollsicherungen ausführen, sollten in den Protokollsicherungen auch alle replikationsrelevanten Änderungen erfasst werden.</span><span class="sxs-lookup"><span data-stu-id="595fa-103">If you perform regular log backups, any replication-related changes should be captured in the log backups.</span></span> <span data-ttu-id="595fa-104">Wenn Sie keine Protokollsicherungen ausführen, sichern Sie die Veröffentlichung, die Verteilung, das Abonnement sowie die Datenbanken **msdb**und **master** nach Änderungen am Replikationsschema oder der Topologie.</span><span class="sxs-lookup"><span data-stu-id="595fa-104">If you don't perform log backups, perform a backup of the publication, distribution, subscription, **msdb**, and **master** databases after making modifications to your replication schema or topology.</span></span>  
  
## <a name="publication-database"></a><span data-ttu-id="595fa-105">Veröffentlichungsdatenbank</span><span class="sxs-lookup"><span data-stu-id="595fa-105">Publication Database</span></span>  
 <span data-ttu-id="595fa-106">Sichern Sie die Veröffentlichungsdatenbank nach folgenden Aktionen:</span><span class="sxs-lookup"><span data-stu-id="595fa-106">Backup the publication database after:</span></span>  
  
-   <span data-ttu-id="595fa-107">Erstellen neuer Veröffentlichungen.</span><span class="sxs-lookup"><span data-stu-id="595fa-107">Creating new publications.</span></span>  
  
-   <span data-ttu-id="595fa-108">Ändern von Veröffentlichungseigenschaften, einschließlich des Filterns.</span><span class="sxs-lookup"><span data-stu-id="595fa-108">Changing any publication property, including filtering.</span></span>  
  
-   <span data-ttu-id="595fa-109">Hinzufügen von Artikeln zu einer vorhandenen Veröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="595fa-109">Adding articles to an existing publication.</span></span>  
  
-   <span data-ttu-id="595fa-110">Ausführen einer veröffentlichungsweiten erneuten Initialisierung der Abonnements.</span><span class="sxs-lookup"><span data-stu-id="595fa-110">Performing a publication-wide reinitialization of subscriptions.</span></span>  
  
-   <span data-ttu-id="595fa-111">Vornehmen einer Schemaänderung an einer veröffentlichten Tabelle.</span><span class="sxs-lookup"><span data-stu-id="595fa-111">Making a schema change on a published table.</span></span>  
  
-   <span data-ttu-id="595fa-112">Ausführen einer bedarfsgesteuerten Skriptausführung mit [sp_addscriptexec &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addscriptexec-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="595fa-112">Performing on-demand script execution with [sp_addscriptexec &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addscriptexec-transact-sql).</span></span>  
  
-   <span data-ttu-id="595fa-113">Ändern von Artikeleigenschaften.</span><span class="sxs-lookup"><span data-stu-id="595fa-113">Changing any article property.</span></span>  
  
-   <span data-ttu-id="595fa-114">Löschen von Veröffentlichungen.</span><span class="sxs-lookup"><span data-stu-id="595fa-114">Dropping any publications.</span></span>  
  
-   <span data-ttu-id="595fa-115">Löschen von Artikeln.</span><span class="sxs-lookup"><span data-stu-id="595fa-115">Dropping any articles.</span></span>  
  
-   <span data-ttu-id="595fa-116">Deaktivieren der Replikation.</span><span class="sxs-lookup"><span data-stu-id="595fa-116">Disabling replication.</span></span>  
  
## <a name="distribution-database"></a><span data-ttu-id="595fa-117">Verteilungsdatenbank</span><span class="sxs-lookup"><span data-stu-id="595fa-117">Distribution Database</span></span>  
 <span data-ttu-id="595fa-118">Sichern Sie die Verteilungsdatenbank nach folgenden Aktionen:</span><span class="sxs-lookup"><span data-stu-id="595fa-118">Backup the distribution database after:</span></span>  
  
-   <span data-ttu-id="595fa-119">Erstellen oder Ändern von Replikations-Agentprofilen.</span><span class="sxs-lookup"><span data-stu-id="595fa-119">Creating or modifying replication agent profiles.</span></span>  
  
-   <span data-ttu-id="595fa-120">Ändern von Parametern für die Replikations-Agentprofile.</span><span class="sxs-lookup"><span data-stu-id="595fa-120">Modifying replication agent profile parameters.</span></span>  
  
-   <span data-ttu-id="595fa-121">Ändern der Eigenschaften von Replikations-Agents (einschließlich der Zeitpläne) für Pushabonnements.</span><span class="sxs-lookup"><span data-stu-id="595fa-121">Changing the replication agent properties (including schedules) for any push subscriptions.</span></span>  
  
-   <span data-ttu-id="595fa-122">Ein neuer Identitätsbereich wird von der Funktion der automatischen Identitätsbereichsverwaltung zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="595fa-122">A new range of identities is assigned by the automatic identity range management feature.</span></span>  
  
## <a name="subscription-database"></a><span data-ttu-id="595fa-123">Abonnementdatenbank</span><span class="sxs-lookup"><span data-stu-id="595fa-123">Subscription Database</span></span>  
 <span data-ttu-id="595fa-124">Sichern Sie die Abonnementdatenbank nach folgenden Aktionen:</span><span class="sxs-lookup"><span data-stu-id="595fa-124">Backup the subscription database after:</span></span>  
  
-   <span data-ttu-id="595fa-125">Ändern von Abonnementeigenschaften.</span><span class="sxs-lookup"><span data-stu-id="595fa-125">Changing any subscription property.</span></span>  
  
-   <span data-ttu-id="595fa-126">Ändern der Priorität eines Mergeabonnements auf dem Verleger.</span><span class="sxs-lookup"><span data-stu-id="595fa-126">Changing the priority for a merge subscription at the Publisher.</span></span>  
  
-   <span data-ttu-id="595fa-127">Löschen von Abonnements.</span><span class="sxs-lookup"><span data-stu-id="595fa-127">Dropping any subscriptions.</span></span>  
  
-   <span data-ttu-id="595fa-128">Deaktivieren der Replikation.</span><span class="sxs-lookup"><span data-stu-id="595fa-128">Disabling replication.</span></span>  
  
## <a name="msdb-database"></a><span data-ttu-id="595fa-129">msdb-Datenbank</span><span class="sxs-lookup"><span data-stu-id="595fa-129">msdb Database</span></span>  
 <span data-ttu-id="595fa-130">Sichern Sie die **msdb** -Systemdatenbank auf dem entsprechenden Knoten nach den folgenden Aktionen:</span><span class="sxs-lookup"><span data-stu-id="595fa-130">Backup the **msdb** system database at the appropriate node after:</span></span>  
  
-   <span data-ttu-id="595fa-131">Aktivieren oder Deaktivieren der Replikation.</span><span class="sxs-lookup"><span data-stu-id="595fa-131">Enabling or disabling replication.</span></span>  
  
-   <span data-ttu-id="595fa-132">Hinzufügen oder Löschen einer Verteilungsdatenbank (auf dem Verteiler).</span><span class="sxs-lookup"><span data-stu-id="595fa-132">Adding or dropping a distribution database (at the Distributor).</span></span>  
  
-   <span data-ttu-id="595fa-133">Aktivieren oder Deaktivieren einer Datenbank für das Veröffentlichen (auf dem Verleger).</span><span class="sxs-lookup"><span data-stu-id="595fa-133">Enabling or disabling a database for publishing (at the Publisher).</span></span>  
  
-   <span data-ttu-id="595fa-134">Erstellen oder Ändern von Replikations-Agentprofilen (auf dem Verteiler).</span><span class="sxs-lookup"><span data-stu-id="595fa-134">Creating or modifying replication agent profiles (at the Distributor).</span></span>  
  
-   <span data-ttu-id="595fa-135">Ändern von Parametern für Replikations-Agentprofile (auf dem Verteiler).</span><span class="sxs-lookup"><span data-stu-id="595fa-135">Modifying any replication agent profile parameters (at the Distributor).</span></span>  
  
-   <span data-ttu-id="595fa-136">Ändern der Eigenschaften von Replikations-Agents (einschließlich der Zeitpläne) für Pushabonnements (auf dem Verteiler).</span><span class="sxs-lookup"><span data-stu-id="595fa-136">Changing the replication agent properties (including schedules) for any push subscriptions (at the Distributor).</span></span>  
  
-   <span data-ttu-id="595fa-137">Ändern der Eigenschaften von Replikations-Agents (einschließlich der Zeitpläne) für Pullabonnements (auf dem Abonnenten).</span><span class="sxs-lookup"><span data-stu-id="595fa-137">Changing the replication agent properties (including schedules) for any pull subscriptions (at the Subscriber).</span></span>  
  
-   <span data-ttu-id="595fa-138">Erstellen eines DTS-Pakets, das einer Transaktionsveröffentlichung zugewiesen ist, die transformierbare Abonnements verwendet (auf dem Verteiler und Abonnenten).</span><span class="sxs-lookup"><span data-stu-id="595fa-138">Creating a DTS package associated with a transactional publication that uses transformable subscriptions (at the Distributor and Subscriber).</span></span>  
  
-   <span data-ttu-id="595fa-139">Hinzufügen oder Löschen eines transformierbaren Abonnements (auf dem Verteiler und Abonnementen).</span><span class="sxs-lookup"><span data-stu-id="595fa-139">Adding or dropping a transformable subscription (at the Distributor and Subscriber).</span></span>  
  
## <a name="master-database"></a><span data-ttu-id="595fa-140">master-Datenbank</span><span class="sxs-lookup"><span data-stu-id="595fa-140">master Database</span></span>  
 <span data-ttu-id="595fa-141">Sichern Sie die **master** -Systemdatenbank auf dem entsprechenden Knoten nach den folgenden Aktionen:</span><span class="sxs-lookup"><span data-stu-id="595fa-141">Backup the **master** system database at the appropriate node after:</span></span>  
  
-   <span data-ttu-id="595fa-142">Aktivieren oder Deaktivieren der Replikation.</span><span class="sxs-lookup"><span data-stu-id="595fa-142">Enabling or disabling replication.</span></span>  
  
-   <span data-ttu-id="595fa-143">Hinzufügen oder Löschen einer Verteilungsdatenbank (auf dem Verteiler).</span><span class="sxs-lookup"><span data-stu-id="595fa-143">Adding or dropping a distribution database (at the Distributor).</span></span>  
  
-   <span data-ttu-id="595fa-144">Aktivieren oder Deaktivieren einer Datenbank für das Veröffentlichen (auf dem Verleger).</span><span class="sxs-lookup"><span data-stu-id="595fa-144">Enabling or disabling a database for publishing (at the Publisher).</span></span>  
  
-   <span data-ttu-id="595fa-145">Hinzufügen der ersten Veröffentlichung oder Löschen der letzten Veröffentlichung in einer Datenbank (auf dem Verleger).</span><span class="sxs-lookup"><span data-stu-id="595fa-145">Adding the first or dropping the last publication in any database (at the Publisher).</span></span>  
  
-   <span data-ttu-id="595fa-146">Hinzufügen des ersten Abonnements oder Löschen des letzten Abonnements in einer Datenbank (auf dem Abonnenten).</span><span class="sxs-lookup"><span data-stu-id="595fa-146">Adding the first or dropping the last subscription in any database (at the Subscriber).</span></span>  
  
-   <span data-ttu-id="595fa-147">Aktivieren oder Deaktivieren eines Verlegers auf einem Verteilungsverleger (auf dem Verleger und dem Verteiler).</span><span class="sxs-lookup"><span data-stu-id="595fa-147">Enabling or disabling a Publisher at a Distribution Publisher (at the Publisher and Distributor).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="595fa-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="595fa-148">See Also</span></span>  
 <span data-ttu-id="595fa-149">[Sichern und Wiederherstellen von SQL Server-Datenbanken](../../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="595fa-149">[Back Up and Restore of SQL Server Databases](../../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span></span>  
 [<span data-ttu-id="595fa-150">Sichern und Wiederherstellen von replizierten Datenbanken</span><span class="sxs-lookup"><span data-stu-id="595fa-150">Back Up and Restore Replicated Databases</span></span>](back-up-and-restore-replicated-databases.md)  
  
  
