---
title: Anzeigen von Daten Konflikten für Transaktions Veröffentlichungen (SQL Server Management Studio) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- conflict resolution [SQL Server replication], queued updating subscriptions
- queued updating subscriptions [SQL Server replication]
- viewing conflict information
ms.assetid: 9977dd75-b0de-4376-9c13-86d80567d8aa
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 228753c113bcf43ed276d989a3996e9bf23bfc16
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620810"
---
# <a name="view-data-conflicts-for-transactional-publications-sql-server-management-studio"></a><span data-ttu-id="8d2ba-102">Anzeigen von Datenkonflikten für Transaktionsveröffentlichungen (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="8d2ba-102">View Data Conflicts for Transactional Publications (SQL Server Management Studio)</span></span>
  <span data-ttu-id="8d2ba-103">Sie können Konflikte bei der Peer-zu-Peer-Transaktionsreplikation und der Transaktionsreplikation mit Abonnements mit verzögertem Update über eine Warteschlange im [!INCLUDE[msCoName](../../includes/msconame-md.md)] Replikationskonflikt-Viewer anzeigen.</span><span class="sxs-lookup"><span data-stu-id="8d2ba-103">You can view conflicts for peer-to-peer transactional replication and transactional replication with queued updating subscriptions in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Replication Conflict Viewer.</span></span> <span data-ttu-id="8d2ba-104">Informationen, wie Konflikte erkannt und behoben werden, finden Sie unter [Konflikterkennung bei der Peer-to-Peer-Replikation](transactional/peer-to-peer-conflict-detection-in-peer-to-peer-replication.md) und [Festlegen der Konfliktlösungsoptionen für verzögerte Updates über eine Warteschlange &#40;SQL Server Management Studio&#41;](publish/create-an-updatable-subscription-to-a-transactional-publication.md).</span><span class="sxs-lookup"><span data-stu-id="8d2ba-104">For information about how conflicts are detected and resolved, see [Conflict Detection in Peer-to-Peer Replication](transactional/peer-to-peer-conflict-detection-in-peer-to-peer-replication.md) and [Set Queued Updating Conflict Resolution Options &#40;SQL Server Management Studio&#41;](publish/create-an-updatable-subscription-to-a-transactional-publication.md).</span></span>  
  
 <span data-ttu-id="8d2ba-105">Die Verfügbarkeit von Konfliktdaten hängt vom Typ der Replikation und der Beibehaltungsdauer ab:</span><span class="sxs-lookup"><span data-stu-id="8d2ba-105">The availability of conflict data depends on the type of replication and the conflict retention period:</span></span>  
  
-   <span data-ttu-id="8d2ba-106">Bei der Peer-zu-Peer-Replikation schlägt der Verteilungs-Agent standardmäßig fehl, wenn er einen Konflikt erkennt.</span><span class="sxs-lookup"><span data-stu-id="8d2ba-106">For peer-to-peer replication, by default, the Distribution Agent fails when it detects a conflict.</span></span> <span data-ttu-id="8d2ba-107">Im Fehlerprotokoll wird ein Konfliktfehler protokolliert, jedoch werden in der Konflikttabelle keine Konfliktdaten erfasst; daher können sie nicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="8d2ba-107">A conflict error is logged into the error log, but no conflict data is logged into the conflict table; therefore it is not available for viewing.</span></span> <span data-ttu-id="8d2ba-108">Wenn der Verteilungs-Agent fortfahren kann, wird der Konflikt lokal auf jedem Knoten protokolliert, auf dem er erkannt wurde.</span><span class="sxs-lookup"><span data-stu-id="8d2ba-108">If the Distribution Agent is allowed to continue, a conflict is logged locally on each node where it was detected.</span></span> <span data-ttu-id="8d2ba-109">Weitere Informationen finden Sie im Abschnitt "Konfliktbehandlung" unter [Conflict Detection in Peer-to-Peer Replication](transactional/peer-to-peer-conflict-detection-in-peer-to-peer-replication.md).</span><span class="sxs-lookup"><span data-stu-id="8d2ba-109">For more information, see "Handling Conflicts" in [Conflict Detection in Peer-to-Peer Replication](transactional/peer-to-peer-conflict-detection-in-peer-to-peer-replication.md).</span></span>  
  
-   <span data-ttu-id="8d2ba-110">Bei Abonnements mit verzögertem Update über eine Warteschlange sind Daten für jeden Konflikt verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8d2ba-110">For queued updating subscriptions, data is available for every conflict.</span></span> <span data-ttu-id="8d2ba-111">Die Konfliktdaten sind im Replikationskonflikt-Viewer für den Zeitraum verfügbar, der als Beibehaltungsdauer für Konfliktdaten (bei Standardeinstellung 14 Tage) angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="8d2ba-111">Conflict data is available in the Replication Conflict Viewer for the amount of time specified for the conflict retention period, with a default of 14 days.</span></span> <span data-ttu-id="8d2ba-112">Um die Beibehaltungsdauer für Konfliktdaten festzulegen, können Sie auf zweierlei Weise vorgehen:</span><span class="sxs-lookup"><span data-stu-id="8d2ba-112">To set the conflict retention period, perform either of the following:</span></span>  
  
    -   <span data-ttu-id="8d2ba-113">Geben Sie einen Beibehaltungswert für den Parameter @conflict_retention von [sp_addpublication](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql)an.</span><span class="sxs-lookup"><span data-stu-id="8d2ba-113">Specify a retention value for the @conflict_retention parameter of [sp_addpublication](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql).</span></span>  
  
    -   <span data-ttu-id="8d2ba-114">Geben Sie den Wert `'conflict_retention'` für den @property -Parameter und einen Beibehaltungs Wert für den- @value Parameter [sp_changepublication](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql)an.</span><span class="sxs-lookup"><span data-stu-id="8d2ba-114">Specify a value of `'conflict_retention'` for the @property parameter and a retention value for the @value parameter of [sp_changepublication](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql).</span></span>  
  
### <a name="to-view-conflicts"></a><span data-ttu-id="8d2ba-115">So zeigen Sie Konflikte an</span><span class="sxs-lookup"><span data-stu-id="8d2ba-115">To view conflicts</span></span>  
  
1.  <span data-ttu-id="8d2ba-116">Stellen Sie die Verbindung zum entsprechenden Server in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]her, und erweitern Sie dann den Serverknoten:</span><span class="sxs-lookup"><span data-stu-id="8d2ba-116">Connect to the appropriate server in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node:</span></span>  
  
    -   <span data-ttu-id="8d2ba-117">Für die Peer-zu-Peer-Replikation ist dies der Knoten, bei dem der Konflikt aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="8d2ba-117">For peer-to-peer replication, this is the node at which the conflict occurred.</span></span>  
  
    -   <span data-ttu-id="8d2ba-118">Für Abonnements mit verzögertem Update über eine Warteschlange ist dies der Verleger.</span><span class="sxs-lookup"><span data-stu-id="8d2ba-118">For queued updating subscriptions, this is the Publisher.</span></span>  
  
2.  <span data-ttu-id="8d2ba-119">Erweitern Sie den Ordner **Replikation** , und erweitern Sie dann den Ordner **Lokale Veröffentlichungen** .</span><span class="sxs-lookup"><span data-stu-id="8d2ba-119">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="8d2ba-120">Klicken Sie mit der rechten Maustaste auf die Veröffentlichung, für die Sie die Konflikte anzeigen möchten, und klicken Sie dann auf **Konflikte anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="8d2ba-120">Right-click the publication for which you want to view conflicts, and then click **View Conflicts**.</span></span>  
  
4.  <span data-ttu-id="8d2ba-121">Wählen Sie im Dialogfeld **Konflikttabelle auswählen** eine Datenbank, eine Veröffentlichung und eine Tabelle aus, für die Sie die Konflikte anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="8d2ba-121">In the **Select Conflict Table** dialog box, select a database, publication, and table for which to view conflicts.</span></span>  
  
5.  <span data-ttu-id="8d2ba-122">Im Replikationskonflikt-Viewer können Sie folgende Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="8d2ba-122">In the Replication Conflict Viewer, you can:</span></span>  
  
    -   <span data-ttu-id="8d2ba-123">Filtern Sie Zeilen mit den Schaltflächen rechts vom oberen Raster.</span><span class="sxs-lookup"><span data-stu-id="8d2ba-123">Filter rows with the buttons to the right of the upper grid.</span></span>  
  
    -   <span data-ttu-id="8d2ba-124">Wählen Sie eine Zeile im oberen Raster aus, um Informationen zur Zeile im unteren Raster anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8d2ba-124">Select a row in the upper grid to display information on that row in the lower grid.</span></span>  
  
    -   <span data-ttu-id="8d2ba-125">Wählen Sie eine oder mehrere Zeilen im oberen Raster aus, und klicken Sie auf **Entfernen**. Die Zeilen werden dann aus der Metatabelle für Konflikte gelöscht.</span><span class="sxs-lookup"><span data-stu-id="8d2ba-125">Select one or more rows in the upper grid, and then click **Remove**, which removes the row from the conflicts metadata table.</span></span>  
  
    -   <span data-ttu-id="8d2ba-126">Klicken Sie auf die Schaltfläche mit den Eigenschaften (**...**), um weitere Informationen zu einer in einem Konflikt beteiligten Spalte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8d2ba-126">Click the properties button (**...**) to view more information on a column involved in a conflict.</span></span>  
  
    -   <span data-ttu-id="8d2ba-127">Aktivieren Sie **Details dieses Konflikts protokollieren** , um Konfliktdaten in einer Datei zu protokollieren.</span><span class="sxs-lookup"><span data-stu-id="8d2ba-127">Select **Log the details of this conflict** to log conflict data to a file.</span></span> <span data-ttu-id="8d2ba-128">Um einen Speicherort für die Datei anzugeben, zeigen Sie auf das Menü **Ansicht** , und klicken Sie dann auf **Optionen**.</span><span class="sxs-lookup"><span data-stu-id="8d2ba-128">To specify a location for the file, point to the **View** menu, and then click **Options**.</span></span> <span data-ttu-id="8d2ba-129">Geben Sie einen Wert ein, oder klicken Sie auf die Schaltfläche mit den drei Punkten (**...**), und wechseln Sie in das entsprechende Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="8d2ba-129">Enter a value, or click the browse button (**...**), and then navigate to the appropriate file.</span></span> <span data-ttu-id="8d2ba-130">Klicken Sie auf **OK**, um das Dialogfeld **Optionen** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="8d2ba-130">Click **OK** to close the **Options** dialog box.</span></span>  
  
6.  <span data-ttu-id="8d2ba-131">Schließen Sie den Replikationskonflikt-Viewer.</span><span class="sxs-lookup"><span data-stu-id="8d2ba-131">Close the Replication Conflict Viewer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d2ba-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8d2ba-132">See Also</span></span>  
 <span data-ttu-id="8d2ba-133">[Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md) </span><span class="sxs-lookup"><span data-stu-id="8d2ba-133">[Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md) </span></span>  
 [<span data-ttu-id="8d2ba-134">Konflikterkennung und -lösung beim verzögerten Update über eine Warteschlange</span><span class="sxs-lookup"><span data-stu-id="8d2ba-134">Queued Updating Conflict Detection and Resolution</span></span>](transactional/updatable-subscriptions-queued-updating-conflict-resolution.md)  
  
  
