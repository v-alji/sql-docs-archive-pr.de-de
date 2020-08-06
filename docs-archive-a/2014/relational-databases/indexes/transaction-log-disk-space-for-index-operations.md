---
title: Transaktionsprotokollspeicherplatz für Indexvorgänge | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- index disk space [SQL Server]
- space [SQL Server], indexes
- transaction logs [SQL Server], disk space
- disk space [SQL Server], transaction logs
- space [SQL Server], transaction logs
ms.assetid: 4f8a4922-4507-4072-be67-c690528d5c3b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c34c9ff7a9494496d6c60d5920184c0ce86131d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723838"
---
# <a name="transaction-log-disk-space-for-index-operations"></a><span data-ttu-id="4f756-102">Transaktionsprotokollspeicherplatz für Indexvorgänge</span><span class="sxs-lookup"><span data-stu-id="4f756-102">Transaction Log Disk Space for Index Operations</span></span>
  <span data-ttu-id="4f756-103">Umfangreiche Indexvorgänge können riesige Datenmengen erzeugen, die zu einem schnellen Füllen des Transaktionsprotokolls führen können.</span><span class="sxs-lookup"><span data-stu-id="4f756-103">Large-scale index operations can generate large data loads that can cause the transaction log to fill quickly.</span></span> <span data-ttu-id="4f756-104">Um sicherzustellen, dass ein Rollback des Indexvorgangs möglich ist, kann das Transaktionsprotokoll nicht abgeschnitten werden, bis der Indexvorgang abgeschlossen ist. Die Sicherung des Protokolls während des Indexvorgangs ist jedoch möglich.</span><span class="sxs-lookup"><span data-stu-id="4f756-104">To make sure that the index operation can be rolled back, the transaction log cannot be truncated until the index operation has completed; however, the log can be backed up during the index operation.</span></span> <span data-ttu-id="4f756-105">Deshalb muss das Transaktionsprotokoll über ausreichend Speicherplatz verfügen, um sowohl die Transaktionen des Indexvorgangs als auch alle gleichzeitigen Benutzertransaktionen für die Dauer des Indexvorgangs aufnehmen zu können.</span><span class="sxs-lookup"><span data-stu-id="4f756-105">Therefore, the transaction log must have sufficient room to store both the index operation transactions and any concurrent user transactions for the duration of the index operation.</span></span> <span data-ttu-id="4f756-106">Das gilt sowohl für Offline- als auch für Onlineindexvorgänge.</span><span class="sxs-lookup"><span data-stu-id="4f756-106">This is true for both offline and online index operations.</span></span> <span data-ttu-id="4f756-107">Da während eines Offlineindexvorgangs der Zugriff auf die zugrunde liegenden Tabellen nicht möglich ist, treten dabei evtl. nur wenige Benutzertransaktionen auf, und das Protokoll wächst nicht so schnell an.</span><span class="sxs-lookup"><span data-stu-id="4f756-107">Because the underlying tables cannot be accessed during an offline index operation, there may be few user transactions and the log may not grow as quickly.</span></span> <span data-ttu-id="4f756-108">Bei Onlineindexvorgängen erfolgt jedoch keinerlei Einschränkung von gleichzeitigen Benutzeraktivitäten. Daher können umfangreiche Onlineindexvorgänge in Kombination mit zahlreichen gleichzeitigen Benutzertransaktionen zu einem kontinuierlichen Anwachsen des Transaktionsprotokolls führen, ohne dass es eine Möglichkeit zum Abschneiden des Protokolls gibt.</span><span class="sxs-lookup"><span data-stu-id="4f756-108">Online index operations do not prevent concurrent user activity, therefore, large-scale online index operations combined with significant concurrent user transactions can cause continuous growth of the transaction log without an option to truncate the log.</span></span>  
  
## <a name="recommendations"></a><span data-ttu-id="4f756-109">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="4f756-109">Recommendations</span></span>  
 <span data-ttu-id="4f756-110">Beim Ausführen umfangreicher Indexvorgänge sollten Sie die folgenden Empfehlungen beachten:</span><span class="sxs-lookup"><span data-stu-id="4f756-110">When you run large-scale index operations, consider the following recommendations:</span></span>  
  
1.  <span data-ttu-id="4f756-111">Stellen Sie sicher, dass das Transaktionsprotokoll gesichert und abgeschnitten wurde, bevor Sie umfangreiche Onlineindexvorgänge ausführen. Außerdem muss das Protokoll über ausreichend Speicherplatz verfügen können, um den vorgesehenen Index und die Benutzertransaktionen speichern zu können.</span><span class="sxs-lookup"><span data-stu-id="4f756-111">Make sure the transaction log has been backed up and truncated before running large-scale index operations online, and that the log has sufficient space to store the projected index and user transactions.</span></span>  
  
2.  <span data-ttu-id="4f756-112">Setzen Sie die Option SORT_IN_TEMPDB für den Indexvorgang eventuell auf ON.</span><span class="sxs-lookup"><span data-stu-id="4f756-112">Consider setting the SORT_IN_TEMPDB option to ON for the index operation.</span></span> <span data-ttu-id="4f756-113">Damit werden die Indextransaktionen von den gleichzeitigen Benutzertransaktionen getrennt.</span><span class="sxs-lookup"><span data-stu-id="4f756-113">This separates the index transactions from the concurrent user transactions.</span></span> <span data-ttu-id="4f756-114">Die Indextransaktionen werden dann im Transaktionsprotokoll **tempdb** gespeichert, während die gleichzeitigen Benutzertransaktionen im Protokoll der Benutzerdatenbank gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="4f756-114">The index transactions will be stored in the **tempdb** transaction log, and the concurrent user transactions will be stored in the transaction log of the user database.</span></span> <span data-ttu-id="4f756-115">Damit kann das Transaktionsprotokoll der Benutzerdatenbank bei Bedarf während des Indexvorgangs abgeschnitten werden.</span><span class="sxs-lookup"><span data-stu-id="4f756-115">This allows for the transaction log of the user database to be truncated during the index operation if it is required.</span></span> <span data-ttu-id="4f756-116">Wenn Sich das Protokoll **tempdb** außerdem auf einem anderen Datenträger als das Datenbankprotokoll befindet, konkurrieren die beiden Protokolle nicht um Speicherplatz auf demselben Datenträger.</span><span class="sxs-lookup"><span data-stu-id="4f756-116">Additionally, if the **tempdb** log is not on the same disk as the user database log, the two logs are not competing for the same disk space.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4f756-117">Überprüfen Sie, dass die Datenbank **tempdb** und das Transaktionsprotokoll über ausreichend Speicherplatz zur Durchführung des Indexvorgangs verfügen.</span><span class="sxs-lookup"><span data-stu-id="4f756-117">Verify that the **tempdb** database and transaction log have sufficient disk space to handle the index operation.</span></span> <span data-ttu-id="4f756-118">Das **tempdb** -Transaktionsprotokoll kann nicht abgeschnitten werden, so lange der Indexvorgang noch nicht abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="4f756-118">The **tempdb** transaction log cannot be truncated until the index operation is completed.</span></span>  
  
3.  <span data-ttu-id="4f756-119">Verwenden Sie ein Datenbankwiederherstellungsmodell, das eine minimale Protokollierung des Indexvorgangs zulässt.</span><span class="sxs-lookup"><span data-stu-id="4f756-119">Use a database recovery model that allows for minimal logging of the index operation.</span></span> <span data-ttu-id="4f756-120">Damit kann die Größe des Protokolls verringert und das vollständige Füllen des Speicherplatzes durch das Protokoll verhindert werden.</span><span class="sxs-lookup"><span data-stu-id="4f756-120">This may reduce the size of the log and prevent the log from filling the log space.</span></span>  
  
4.  <span data-ttu-id="4f756-121">Führen Sie den Onlineindexvorgang nicht in einer expliziten Transaktion aus.</span><span class="sxs-lookup"><span data-stu-id="4f756-121">Do not run the online index operation in an explicit transaction.</span></span> <span data-ttu-id="4f756-122">Das Protokoll wird nicht abgeschnitten, bis die explizite Transaktion abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="4f756-122">The log will not be truncated until the explicit transaction ends.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="4f756-123">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="4f756-123">Related Content</span></span>  
 [<span data-ttu-id="4f756-124">Speicherplatzanforderungen für Index-DDL-Vorgänge</span><span class="sxs-lookup"><span data-stu-id="4f756-124">Disk Space Requirements for Index DDL Operations</span></span>](disk-space-requirements-for-index-ddl-operations.md)  
  
 [<span data-ttu-id="4f756-125">Beispiel für den zum Speichern eines Indexes belegten Speicherplatz</span><span class="sxs-lookup"><span data-stu-id="4f756-125">Index Disk Space Example</span></span>](index-disk-space-example.md)  
  
  
