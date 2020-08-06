---
title: Transaktionen (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- transactions [Master Data Services], about transactions
- transactions [Master Data Services]
ms.assetid: 4cd2fa6f-9c76-4b7a-ae18-d4e5fd2f03f5
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c693b550e0c1adb8f5910d99c7125c85f41abb8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723966"
---
# <a name="transactions-master-data-services"></a><span data-ttu-id="b4876-102">Transaktionen (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="b4876-102">Transactions (Master Data Services)</span></span>
  <span data-ttu-id="b4876-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]werden Transaktionen jedes Mal aufgezeichnet, wenn für ein Element eine Aktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b4876-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], a transaction is recorded each time action is taken on a member.</span></span> <span data-ttu-id="b4876-104">Transaktionen können von allen Benutzern angezeigt und von Administratoren umgekehrt werden.</span><span class="sxs-lookup"><span data-stu-id="b4876-104">Transactions can be viewed by all users and reversed by administrators.</span></span> <span data-ttu-id="b4876-105">Für Transaktionen werden das Datum, die Uhrzeit, der Benutzer, der die Aktion ausgeführt hat, sowie weitere Details angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b4876-105">Transactions show the date, time, and user who took the action, along with other details.</span></span> <span data-ttu-id="b4876-106">Benutzer können einer Transaktion eine Anmerkung hinzufügen, um anzugeben, wieso die Transaktion stattgefunden hat.</span><span class="sxs-lookup"><span data-stu-id="b4876-106">Users can add an annotation to a transaction, to indicate why a transaction took place.</span></span>  
  
## <a name="when-transaction-are-recorded"></a><span data-ttu-id="b4876-107">Zeitpunkt der Transaktionsaufzeichnung</span><span class="sxs-lookup"><span data-stu-id="b4876-107">When Transaction Are Recorded</span></span>  
 <span data-ttu-id="b4876-108">Transaktionen werden aufgezeichnet, wenn Elemente:</span><span class="sxs-lookup"><span data-stu-id="b4876-108">Transactions are recorded when members:</span></span>  
  
-   <span data-ttu-id="b4876-109">Erstellt, gelöscht oder erneut aktiviert werden</span><span class="sxs-lookup"><span data-stu-id="b4876-109">Are created, deleted, or reactivated.</span></span>  
  
-   <span data-ttu-id="b4876-110">Attributwertänderungen aufweisen</span><span class="sxs-lookup"><span data-stu-id="b4876-110">Have attribute values changed.</span></span>  
  
-   <span data-ttu-id="b4876-111">In einer Hierarchie verschoben werden</span><span class="sxs-lookup"><span data-stu-id="b4876-111">Are moved in a hierarchy.</span></span>  
  
 <span data-ttu-id="b4876-112">Transaktionen werden nicht aufgezeichnet, wenn Attributwerte durch Geschäftsregeln geändert werden.</span><span class="sxs-lookup"><span data-stu-id="b4876-112">Transactions are not recorded when business rules change attribute values.</span></span>  
  
## <a name="view-and-manage-transactions"></a><span data-ttu-id="b4876-113">Anzeigen und Verwalten von Transaktionen</span><span class="sxs-lookup"><span data-stu-id="b4876-113">View and Manage Transactions</span></span>  
 <span data-ttu-id="b4876-114">Im Funktionsbereich **Explorer** können Sie von Ihnen erstellte Transaktionen anzeigen und mit Anmerkungen versehen (ihnen Kommentare hinzufügen).</span><span class="sxs-lookup"><span data-stu-id="b4876-114">In the **Explorer** functional area, you can view and annotate (add comments to) the transactions that you made yourself.</span></span>  
  
 <span data-ttu-id="b4876-115">Im Funktionsbereich **Versionsverwaltung** können Administratoren alle Transaktionen für alle Benutzer für die Modelle anzeigen, auf die sie Zugriff haben, und jede beliebige Transaktion umkehren.</span><span class="sxs-lookup"><span data-stu-id="b4876-115">In the **Version Management** functional area, administrators can view all transactions for all users for the models they have access to, and reverse any of these transactions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b4876-116">Administratoren können alle Transaktionen für alle Benutzer anzeigen, solange nicht die Berechtigungsstufe „schreibgeschützt“ im Funktionsbereich **Versionsverwaltung** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="b4876-116">Administrators can view all transactions for all users as long as they don't have the read-only permission level applied in the **Version Management** functional area .</span></span> <span data-ttu-id="b4876-117">Wenn z.B. die Berechtigung „schreibgeschützt“ und UPDATE-Berechtigungsebene für den Administrator festgelegt ist, kann dieser keine anderen Transaktionen anzeigen, da die Berechtigung „schreibgeschützt“ Vorrang vor der UPDATE-Berechtigung hat.</span><span class="sxs-lookup"><span data-stu-id="b4876-117">For example, if the read-only permission and update permission level is set for the administrator, the administrator will not be able to see other user transactions because the read-only permission will take precedence over the update permission.</span></span>

## <a name="system-settings"></a><span data-ttu-id="b4876-118">Systemeinstellungen</span><span class="sxs-lookup"><span data-stu-id="b4876-118">System Settings</span></span>  
 <span data-ttu-id="b4876-119">Im [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] ist eine Einstellung verfügbar, die beeinflusst, ob Transaktionen beim Bereitstellen von Datensätzen aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="b4876-119">There is a setting in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] that affects whether or not transactions are recorded when records are staged.</span></span> <span data-ttu-id="b4876-120">Diese Einstellung wirkt sich nur auf SQL Server 2008 R2 aus.</span><span class="sxs-lookup"><span data-stu-id="b4876-120">This setting affects SQL Server 2008 R2 only.</span></span> <span data-ttu-id="b4876-121">Sie können diese Einstellung in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] oder direkt in der Tabelle „Systemeinstellungen“ der [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] -Datenbank anpassen.</span><span class="sxs-lookup"><span data-stu-id="b4876-121">You can adjust this setting in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] or directly in the System Settings table in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="b4876-122">Weitere Informationen finden Sie unter [Systemeinstellungen &#40;Master Data Services&#41;](system-settings-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="b4876-122">For more information, see [System Settings &#40;Master Data Services&#41;](system-settings-master-data-services.md).</span></span>  
  
 <span data-ttu-id="b4876-123">Wenn Sie Daten in diese Version von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]importieren, können Sie angeben, ob Transaktionen beim Initiieren der gespeicherten Prozedur protokolliert werden.</span><span class="sxs-lookup"><span data-stu-id="b4876-123">When importing data in this version of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], you can specify whether or not to log transactions when initiating the stored procedure.</span></span> <span data-ttu-id="b4876-124">Weitere Informationen finden Sie unter [Gespeicherte Stagingprozedur &#40;Master Data Services&#41;](../../2014/master-data-services/staging-stored-procedure-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="b4876-124">For more information, see [Staging Stored Procedure &#40;Master Data Services&#41;](../../2014/master-data-services/staging-stored-procedure-master-data-services.md).</span></span>  
  
## <a name="concurrency"></a><span data-ttu-id="b4876-125">Parallelität</span><span class="sxs-lookup"><span data-stu-id="b4876-125">Concurrency</span></span>  
 <span data-ttu-id="b4876-126">Wenn ein bestimmter Entitätswert gleichzeitig in mehr als einer Explorersitzung angezeigt wird, sind gleichzeitige Bearbeitungen zum gleichen Wert möglich.</span><span class="sxs-lookup"><span data-stu-id="b4876-126">If a particular entity value is shown simultaneously in more than one Explorer session, concurrent edits to the same value are possible.</span></span> <span data-ttu-id="b4876-127">Gleichzeitige Bearbeitungen werden nicht automatisch von MDS erkannt.</span><span class="sxs-lookup"><span data-stu-id="b4876-127">Concurrent edits will not be detected automatically by MDS.</span></span> <span data-ttu-id="b4876-128">Dies kann auftreten, wenn mehrere Benutzer den MDS-Explorer im Webbrowser von mehreren Sitzungen, z. B. von mehreren Computern, mehreren Browserregisterkarten oder Fenstern oder mehreren Benutzerkonten, verwenden.</span><span class="sxs-lookup"><span data-stu-id="b4876-128">This can occur when multiple users use the MDS Explorer in the Web browser from multiple sessions, for example from multiple computers, multiple browser tabs or windows, or multiple user accounts.</span></span>  
  
 <span data-ttu-id="b4876-129">Mehr als ein Benutzer kann trotz Transaktionen, die aktiviert werden, die gleichen Entitätswerte ohne Fehler aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="b4876-129">More than one user can update the same entity values without error despite transactions being enabled.</span></span> <span data-ttu-id="b4876-130">In der Regel hat die letzte Bearbeitung zum Wert in einer Sequenz der Zeit Vorrang.</span><span class="sxs-lookup"><span data-stu-id="b4876-130">Typically the last edit to the value in a sequence of time will take precedence.</span></span> <span data-ttu-id="b4876-131">Der doppelte Bearbeitungskonflikt kann im Transaktionsverlauf manuell beachtet werden und vom Administrator manuell umgekehrt werden.</span><span class="sxs-lookup"><span data-stu-id="b4876-131">The duplicate edit conflict can be manually observed in the transaction history and can be reversed manually by the administrator.</span></span> <span data-ttu-id="b4876-132">Der Transaktionsverlauf zeigt die einzelnen Transaktionen für den **vorherigen Wert** und den **neuen Wert** für das fragliche Attribut aus jeder Sitzung an, löst aber den Konflikt nicht automatisch, wenn mehrere **neue Werte** für den gleichen alten Wert vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="b4876-132">The transaction history will show the individual transactions for the **Prior value** and **New value** for the attribute in question from each session, but will not automatically resolve the conflict when multiple **New Values** exist for the same old value.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="b4876-133">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="b4876-133">Related Tasks</span></span>  
  
|<span data-ttu-id="b4876-134">Taskbeschreibung</span><span class="sxs-lookup"><span data-stu-id="b4876-134">Task Description</span></span>|<span data-ttu-id="b4876-135">Thema</span><span class="sxs-lookup"><span data-stu-id="b4876-135">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="b4876-136">Aktion durch Umkehren einer Transaktion rückgängig machen (nur Administratoren).</span><span class="sxs-lookup"><span data-stu-id="b4876-136">Undo an action by reversing a transaction (administrators only).</span></span>|[<span data-ttu-id="b4876-137">Umkehren einer Transaktion &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="b4876-137">Reverse a Transaction &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/reverse-a-transaction-master-data-services.md)|  
  
## <a name="related-content"></a><span data-ttu-id="b4876-138">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="b4876-138">Related Content</span></span>  
  
-   [<span data-ttu-id="b4876-139">Administratoren &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="b4876-139">Administrators &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/administrators-master-data-services.md)  
  
-   [<span data-ttu-id="b4876-140">Anmerkungen &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="b4876-140">Annotations &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/annotations-master-data-services.md)  
  
  
