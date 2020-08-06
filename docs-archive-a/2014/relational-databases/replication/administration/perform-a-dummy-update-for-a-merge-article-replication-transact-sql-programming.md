---
title: Ausführen eines Pseudo Updates für einen Mergeartikel (Replikations Programmierung mit Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- sp_mergedummyupdate
- dummy updates [SQL Server replication]
ms.assetid: 2f339210-4d85-4843-bd94-e86f7100d3ef
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 07fa0f868b2c3f98496046b138424d7d3a2fa2fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721410"
---
# <a name="perform-a-dummy-update-for-a-merge-article-replication-transact-sql-programming"></a><span data-ttu-id="5a04c-102">Ausführen eines Pseudoupdates für einen Mergeartikel (Replikationsprogrammierung mit Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="5a04c-102">Perform a Dummy Update for a Merge Article (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="5a04c-103">Bei der Mergereplikation kommen im Rahmen des Replikationsvorgangs Trigger zum Einsatz: Beim Aktualisieren einer veröffentlichten Tabelle wird ein Update-Trigger ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="5a04c-103">Merge replication uses triggers as part of the replication process; when an update is made to published table, an update trigger fires.</span></span> <span data-ttu-id="5a04c-104">In manchen Fällen können Daten aktualisiert werden, ohne dass der Trigger ausgelöst wird, z. B. bei WRITETEXT- und UPDATETEXT-Vorgängen.</span><span class="sxs-lookup"><span data-stu-id="5a04c-104">In some cases, data can be updated without the trigger firing, such as during the WRITETEXT and UPDATETEXT operations.</span></span> <span data-ttu-id="5a04c-105">In diesen Fällen müssen Sie explizit eine UPDATE-Pseudoanweisung hinzufügen, um die Änderung zu replizieren.</span><span class="sxs-lookup"><span data-stu-id="5a04c-105">In these cases, you need to add a dummy UPDATE statement explicitly to replicate the change.</span></span> <span data-ttu-id="5a04c-106">Sie können eine UPDATE-Pseudoanweisung mithilfe gespeicherter Replikationsprozeduren hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="5a04c-106">You can add a dummy UPDATE statement using replication stored procedures.</span></span>  
  
### <a name="to-add-a-dummy-update-statement"></a><span data-ttu-id="5a04c-107">So fügen Sie eine UPDATE-Pseudoanweisung hinzu</span><span class="sxs-lookup"><span data-stu-id="5a04c-107">To add a dummy UPDATE statement</span></span>  
  
1.  <span data-ttu-id="5a04c-108">Führen Sie den Vorgang (z. B. UPDATETEXT) für eine Zeile in einer veröffentlichten Tabelle für einen Mergevorgang aus, für die ein Pseudoupdate erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="5a04c-108">Execute the operation (for example, UPDATETEXT) on a row in a merge published table  that requires a dummy update.</span></span>  
  
2.  <span data-ttu-id="5a04c-109">Führen Sie auf dem Server (Verleger oder Abonnent) auf der Datenbank, auf dem die Änderung vorgenommen wurde, [sp_mergedummyupdate &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-mergedummyupdate-transact-sql) aus.</span><span class="sxs-lookup"><span data-stu-id="5a04c-109">At the server (Publisher or Subscriber) on the database where the change was made, execute [sp_mergedummyupdate &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-mergedummyupdate-transact-sql).</span></span> <span data-ttu-id="5a04c-110">Geben Sie die Tabelle, für die die Änderung vorgenommen wurde **@source_object** , und den eindeutigen Bezeichner der geänderten Zeile für an **@rowguid** .</span><span class="sxs-lookup"><span data-stu-id="5a04c-110">Specify the table on which the change was made for **@source_object**, and the unique identifier of the changed row for **@rowguid**.</span></span>  
  
3.  <span data-ttu-id="5a04c-111">Synchronisieren Sie das Abonnement, um die geänderte Zeile zu replizieren.</span><span class="sxs-lookup"><span data-stu-id="5a04c-111">Synchronize the subscription to replicate the changed row.</span></span>  
  
  
