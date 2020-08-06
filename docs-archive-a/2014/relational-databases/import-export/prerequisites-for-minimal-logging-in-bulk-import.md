---
title: Voraussetzungen für die minimale Protokollierung beim Massenimport | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- minimal logging [SQL Server]
- logged bulk copy [SQL Server]
- logs [SQL Server], minimal logging
- minimally logged operations [SQL Server]
- bulk importing [SQL Server], minimal logging
ms.assetid: bd1dac6b-6ef8-4735-ad4e-67bb42dc4f66
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4711e25dcfcc99e14894e47166638673c61a6831
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724725"
---
# <a name="prerequisites-for-minimal-logging-in-bulk-import"></a><span data-ttu-id="cf244-102">Voraussetzungen für die minimale Protokollierung beim Massenimport</span><span class="sxs-lookup"><span data-stu-id="cf244-102">Prerequisites for Minimal Logging in Bulk Import</span></span>
  <span data-ttu-id="cf244-103">Für eine Datenbank, bei der das vollständige Wiederherstellungsmodell verwendet wird, werden alle beim Massenimport ausgeführten Vorgänge für das Einfügen von Zeilen vollständig im Transaktionsprotokoll protokolliert.</span><span class="sxs-lookup"><span data-stu-id="cf244-103">For a database under the full recovery model, all row-insert operations that are performed by bulk import are fully logged in the transaction log.</span></span> <span data-ttu-id="cf244-104">Bei umfangreichen Datenimporten kann das Transaktionsprotokoll schnell aufgefüllt werden, wenn das vollständige Wiederherstellungsmodell verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cf244-104">Large data imports can cause the transaction log to fill rapidly if the full recovery model is used.</span></span> <span data-ttu-id="cf244-105">Im Gegensatz dazu reduziert die minimale Protokollierung von Massenimportvorgängen beim einfachen Wiederherstellungsmodell oder beim massenprotokollierten Wiederherstellungsmodell die Gefahr eines Überlaufs des Protokollspeichers durch einen Massenimportvorgang.</span><span class="sxs-lookup"><span data-stu-id="cf244-105">In contrast, under the simple recovery model or bulk-logged recovery model, minimal logging of bulk-import operations reduces the possibility that a bulk-import operation will fill the log space.</span></span> <span data-ttu-id="cf244-106">Darüber hinaus ist die minimale Protokollierung effizienter als die vollständige Protokollierung.</span><span class="sxs-lookup"><span data-stu-id="cf244-106">Minimal logging is also more efficient than full logging.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cf244-107">Das massenprotokollierte Wiederherstellungsmodell wurde entwickelt, um das vollständige Wiederherstellungsmodell während umfangreicher Massenvorgänge vorübergehend zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="cf244-107">The bulk-logged recovery model is designed to temporarily replace the full recovery model during large bulk operations.</span></span>  
  
## <a name="table-requirements-for-minimally-logging-bulk-import-operations"></a><span data-ttu-id="cf244-108">Tabellenanforderungen für die minimale Protokollierung bei Massenimportvorgängen</span><span class="sxs-lookup"><span data-stu-id="cf244-108">Table Requirements for Minimally Logging Bulk-Import Operations</span></span>  
 <span data-ttu-id="cf244-109">Für die minimale Protokollierung muss die Zieltabelle die folgenden Bedingungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="cf244-109">Minimal logging requires that the target table meets the following conditions:</span></span>  
  
-   <span data-ttu-id="cf244-110">Die Tabelle wird nicht repliziert.</span><span class="sxs-lookup"><span data-stu-id="cf244-110">The table is not being replicated.</span></span>  
  
-   <span data-ttu-id="cf244-111">Eine Tabellensperre ist angegeben (mit TABLOCK).</span><span class="sxs-lookup"><span data-stu-id="cf244-111">Table locking is specified (using TABLOCK).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cf244-112">Obwohl Dateneinfügungen bei einem minimal protokollierten Massenimportvorgang nicht im Transaktionsprotokoll protokolliert werden, protokolliert das [!INCLUDE[ssDE](../../includes/ssde-md.md)] dennoch Blockzuordnungen, wenn der Tabelle ein neuer Block zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="cf244-112">Although data insertions are not logged in the transaction log during a minimally logged bulk-import operation, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] still logs extent allocations each time a new extent is allocated to the table.</span></span>  
  
-   <span data-ttu-id="cf244-113">Die Tabelle ist keine speicheroptimierte Tabelle.</span><span class="sxs-lookup"><span data-stu-id="cf244-113">Table is not a memory-optimized table.</span></span>  
  
 <span data-ttu-id="cf244-114">Ob die minimale Protokollierung für eine Tabelle möglich ist, hängt auch davon ab, ob die Tabelle indiziert ist und, falls dies der Fall ist, ob die Tabelle leer ist:</span><span class="sxs-lookup"><span data-stu-id="cf244-114">Whether minimal logging can occur for a table also depends on whether the table is indexed and, if so, whether the table is empty:</span></span>  
  
-   <span data-ttu-id="cf244-115">Wenn die Tabelle keine Indizes besitzt, werden die Datenseiten minimal protokolliert.</span><span class="sxs-lookup"><span data-stu-id="cf244-115">If the table has no indexes, data pages are minimally logged.</span></span>  
  
-   <span data-ttu-id="cf244-116">Falls die Tabelle keinen gruppierten Index, aber mindestens einen nicht gruppierten Index aufweist, werden die Datenseiten immer minimal protokolliert.</span><span class="sxs-lookup"><span data-stu-id="cf244-116">If the table has no clustered index but has one or more nonclustered indexes, data pages are always minimally logged.</span></span> <span data-ttu-id="cf244-117">Wie Indexseiten protokolliert werden, hängt jedoch davon ab, ob die Tabelle leer ist:</span><span class="sxs-lookup"><span data-stu-id="cf244-117">How index pages are logged, however, depends on whether the table is empty:</span></span>  
  
    -   <span data-ttu-id="cf244-118">Falls die Tabelle leer ist, werden Indexseiten minimal protokolliert.</span><span class="sxs-lookup"><span data-stu-id="cf244-118">If the table is empty, index pages are minimally logged.</span></span>  
  
    -   <span data-ttu-id="cf244-119">Falls die Tabelle nicht leer ist, werden Indexseiten vollständig protokolliert.</span><span class="sxs-lookup"><span data-stu-id="cf244-119">If table is non-empty, index pages are fully logged.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="cf244-120">Wenn Sie mit einer leeren Tabelle beginnen und die Daten in mehreren Batches massenimportieren, werden für den ersten Batch sowohl Index- als auch Datenseiten minimal protokolliert. Ab dem zweiten Batch jedoch werden nur Datenseiten minimal protokolliert.</span><span class="sxs-lookup"><span data-stu-id="cf244-120">If you start with an empty table and bulk import the data in multiple batches, both index and data pages are minimally logged for the first batch, but beginning with the second batch, only data pages are minimally logged.</span></span>  
  
-   <span data-ttu-id="cf244-121">Falls die Tabelle einen gruppierten Index aufweist und leer ist, werden Daten- und Indexseiten minimal protokolliert.</span><span class="sxs-lookup"><span data-stu-id="cf244-121">If the table has a clustered index and is empty, both data and index pages are minimally logged.</span></span> <span data-ttu-id="cf244-122">Wenn dagegen eine Tabelle einen gruppierten Index aufweist und nicht leer ist, werden Daten- und Indexseiten unabhängig vom Wiederherstellungsmodell vollständig protokolliert.</span><span class="sxs-lookup"><span data-stu-id="cf244-122">In contrast, if a table has a clustered index and is non-empty, data pages and index pages are both fully logged regardless of the recovery model.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cf244-123">Wenn Sie mit einer leeren Tabelle beginnen und die Daten in Batches massenimportieren, werden für den ersten Batch sowohl Index- als auch Datenseiten minimal protokolliert. Ab dem zweiten Batch jedoch werden nur Datenseiten massenprotokolliert.</span><span class="sxs-lookup"><span data-stu-id="cf244-123">If you start with an empty table and bulk import the data in batches, both index and data pages are minimally logged for the first batch, but from the second batch onwards, only data pages are bulk logged.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cf244-124">Wenn die Transaktionsreplikation aktiviert ist, werden BULK INSERT-Vorgänge auch unter dem massenprotokollierten Wiederherstellungsmodell vollständig protokolliert.</span><span class="sxs-lookup"><span data-stu-id="cf244-124">When transactional replication is enabled, BULK INSERT operations are fully logged even under the Bulk Logged recovery model.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="cf244-125">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="cf244-125">Related Tasks</span></span>  
  
-   [<span data-ttu-id="cf244-126">Anzeigen oder Ändern des Wiederherstellungsmodells einer Datenbank &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cf244-126">View or Change the Recovery Model of a Database &#40;SQL Server&#41;</span></span>](../backup-restore/view-or-change-the-recovery-model-of-a-database-sql-server.md)  
  

  
## <a name="see-also"></a><span data-ttu-id="cf244-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cf244-127">See Also</span></span>  
 <span data-ttu-id="cf244-128">[Wiederherstellungsmodelle &#40;SQL Server&#41;](../backup-restore/recovery-models-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="cf244-128">[Recovery Models &#40;SQL Server&#41;](../backup-restore/recovery-models-sql-server.md) </span></span>  
 <span data-ttu-id="cf244-129">[bcp (Hilfsprogramm)](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="cf244-129">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="cf244-130">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cf244-130">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="cf244-131">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cf244-131">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="cf244-132">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cf244-132">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="cf244-133">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cf244-133">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="cf244-134">[Tabellenhinweise &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-table) </span><span class="sxs-lookup"><span data-stu-id="cf244-134">[Table Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-table) </span></span>  
 [<span data-ttu-id="cf244-135">INSERT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cf244-135">INSERT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/insert-transact-sql)  
  
  
