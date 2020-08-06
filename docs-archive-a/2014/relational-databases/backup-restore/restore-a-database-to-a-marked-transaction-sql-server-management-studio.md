---
title: Wiederherstellen einer Datenbank bis zu einer markierten Transaktion (SQL Server Management Studio) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.restoretlog.markedtransaction.f1
helpviewer_keywords:
- database restores [SQL Server], marked transactions
- restoring databases [SQL Server], marked transactions
- marked transactions [SQL Server], restoring
ms.assetid: 8f0ea144-1819-4832-905f-e5d0f49b066b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8de9ef5bed389f020f14e60ccd99f39698e7110f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620467"
---
# <a name="restore-a-database-to-a-marked-transaction-sql-server-management-studio"></a><span data-ttu-id="806ff-102">Wiederherstellen einer Datenbank bis zu einer markierten Transaktion (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="806ff-102">Restore a Database to a Marked Transaction (SQL Server Management Studio)</span></span>
  <span data-ttu-id="806ff-103">Wenn sich eine Datenbank im Wiederherstellungsstatus befindet, können Sie das Dialogfeld **Transaktionsprotokoll wiederherstellen** verwenden, um die Datenbank bis zu einer markierten Transaktion in den verfügbaren Protokollsicherungen wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="806ff-103">When a database is in the restoring state, you can use the **Restore Transaction Log** dialog box to restore the database to a marked transaction in the available log backups.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="806ff-104">Weitere Informationen finden Sie unter [Wiederherstellen von verwandten Datenbanken mithilfe von markierten Transaktionen &#40;vollständiges Wiederherstellungsmodell&#41;](use-marked-transactions-to-recover-related-databases-consistently.md) und [Wiederherstellen verwandter Datenbanken mit einer markierten Transaktion](recovery-of-related-databases-that-contain-marked-transaction.md).</span><span class="sxs-lookup"><span data-stu-id="806ff-104">For more information, see [Use Marked Transactions to Recover Related Databases Consistently &#40;Full Recovery Model&#41;](use-marked-transactions-to-recover-related-databases-consistently.md) and [Recovery of Related  Databases That Contain Marked Transaction](recovery-of-related-databases-that-contain-marked-transaction.md).</span></span>  
  
### <a name="to-restore-a-marked-transaction"></a><span data-ttu-id="806ff-105">So stellen Sie eine markierte Transaktion wieder her</span><span class="sxs-lookup"><span data-stu-id="806ff-105">To restore a marked transaction</span></span>  
  
1.  <span data-ttu-id="806ff-106">Klicken Sie nach dem Herstellen einer Verbindung mit der entsprechenden Instanz von [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] im Objekt-Explorer auf den Servernamen, um die Serverstruktur zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="806ff-106">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="806ff-107">Erweitern Sie **Datenbanken**, und wählen Sie je nach Datenbank eine Benutzerdatenbank aus, oder erweitern Sie **Systemdatenbanken** , und wählen Sie eine Systemdatenbank aus.</span><span class="sxs-lookup"><span data-stu-id="806ff-107">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="806ff-108">Klicken Sie mit der rechten Maustaste auf die Datenbank, zeigen Sie auf **Tasks**, und klicken Sie dann auf **Wiederherstellen**.</span><span class="sxs-lookup"><span data-stu-id="806ff-108">Right-click the database, point to **Tasks**, and then click **Restore**.</span></span>  
  
4.  <span data-ttu-id="806ff-109">Klicken Sie auf **Transaktionsprotokoll**, um das Dialogfeld **Transaktionsprotokoll wiederherstellen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="806ff-109">Click **Transaction Log**, which opens the **Restore Transaction Log** dialog box.</span></span>  
  
5.  <span data-ttu-id="806ff-110">Wählen Sie **Markierte Transaktion** im Abschnitt **Wiederherstellen in** auf der Seite **Allgemein**aus, um das Dialogfeld **Markierte Transaktion auswählen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="806ff-110">On the **General** page, in the **Restore To** section, select **Marked transaction**, which opens the **Select Marked Transaction** dialog box.</span></span> <span data-ttu-id="806ff-111">Dieses Dialogfeld zeigt ein Raster an, in dem die markierten Transaktionen aufgelistet sind, die in den ausgewählten Transaktionsprotokollsicherungen zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="806ff-111">This dialog box displays a grid listing the marked transactions available in the selected transaction log backups.</span></span>  
  
     <span data-ttu-id="806ff-112">Standardmäßig erfolgt die Wiederherstellung bis zur markierten Transaktion (die jedoch nicht eingeschlossen wird).</span><span class="sxs-lookup"><span data-stu-id="806ff-112">By default, the restore is up to, but excluding, the marked transaction.</span></span> <span data-ttu-id="806ff-113">Um die markierte Transaktion ebenfalls wiederherzustellen, wählen Sie **Markierte Transaktion einschließen**aus.</span><span class="sxs-lookup"><span data-stu-id="806ff-113">To restore the marked transaction also, select **Include marked transaction**.</span></span>  
  
     <span data-ttu-id="806ff-114">In der folgenden Tabelle werden die Spaltenheader des Rasters aufgelistet und deren Werte beschrieben.</span><span class="sxs-lookup"><span data-stu-id="806ff-114">The following table lists the column headers of the grid and describes their values.</span></span>  
  
    |<span data-ttu-id="806ff-115">Header</span><span class="sxs-lookup"><span data-stu-id="806ff-115">Header</span></span>|<span data-ttu-id="806ff-116">Wert</span><span class="sxs-lookup"><span data-stu-id="806ff-116">Value</span></span>|  
    |------------|-----------|  
    |\<blank>|<span data-ttu-id="806ff-117">Zeigt ein Kontrollkästchen zur Auswahl der Markierung an.</span><span class="sxs-lookup"><span data-stu-id="806ff-117">Displays a checkbox for selecting the mark.</span></span>|  
    |<span data-ttu-id="806ff-118">**Transaktionsmarkierung**</span><span class="sxs-lookup"><span data-stu-id="806ff-118">**Transaction Mark**</span></span>|<span data-ttu-id="806ff-119">Name der markierten Transaktion, der vom Benutzer zugewiesen wurde, als für die Transaktion der Commit ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="806ff-119">Name of the marked transaction specified by the user when the transaction was committed.</span></span>|  
    |<span data-ttu-id="806ff-120">**Date**</span><span class="sxs-lookup"><span data-stu-id="806ff-120">**Date**</span></span>|<span data-ttu-id="806ff-121">Datum und Uhrzeit, zu der für die Transaktion der Commit ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="806ff-121">Date and time of the transaction when it was committed.</span></span> <span data-ttu-id="806ff-122">Als Transaktionsdatum und -uhrzeit werden das Datum und die Uhrzeit angezeigt, die in der **msdbgmarkhistory** -Tabelle aufgezeichnet wurden, nicht das Datum und die Uhrzeit des Clientcomputers.</span><span class="sxs-lookup"><span data-stu-id="806ff-122">Transaction date and time are displayed as recorded in the **msdbgmarkhistory** table, not in the client computer's date and time.</span></span>|  
    |<span data-ttu-id="806ff-123">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="806ff-123">**Description**</span></span>|<span data-ttu-id="806ff-124">Die Beschreibung der markierten Transaktion, die der Benutzer angegeben hat, als für die Transaktion ein Commit ausgeführt wurde (sofern zutreffend).</span><span class="sxs-lookup"><span data-stu-id="806ff-124">Description of marked transaction specified by the user when the transaction was committed (if any).</span></span>|  
    |<span data-ttu-id="806ff-125">**LSN**</span><span class="sxs-lookup"><span data-stu-id="806ff-125">**LSN**</span></span>|<span data-ttu-id="806ff-126">Die Protokollfolgenummer (LSN, Log Sequence Number) der markierten Transaktion.</span><span class="sxs-lookup"><span data-stu-id="806ff-126">Log sequence number of the marked transaction.</span></span>|  
    |<span data-ttu-id="806ff-127">**Datenbank**</span><span class="sxs-lookup"><span data-stu-id="806ff-127">**Database**</span></span>|<span data-ttu-id="806ff-128">Der Name der Datenbank, in der für die markierte Transaktion ein Commit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="806ff-128">Name of the database where the marked transaction was committed.</span></span>|  
    |<span data-ttu-id="806ff-129">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="806ff-129">**User Name**</span></span>|<span data-ttu-id="806ff-130">Der Name des Datenbankbenutzers, der für die markierte Transaktion ein Commit ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="806ff-130">Name of the database user who committed the marked transaction.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="806ff-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="806ff-131">See Also</span></span>  
 <span data-ttu-id="806ff-132">[Wiederherstellen einer Datenbanksicherung &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="806ff-132">[Restore a Database Backup &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span></span>  
 [<span data-ttu-id="806ff-133">Wiederherstellen einer Transaktionsprotokollsicherung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="806ff-133">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](restore-a-transaction-log-backup-sql-server.md)  
  
  
