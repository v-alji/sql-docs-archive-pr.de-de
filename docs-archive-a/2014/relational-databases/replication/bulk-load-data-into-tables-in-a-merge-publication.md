---
title: Massen Laden von Daten in Tabellen in einer Mergeveröffentlichung (Replikations Programmierung mit Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- bulk load [SQL Server replication]
- merge replication bulk loading [SQL Server replication]
- sp_addtabletocontents
ms.assetid: 16e6498a-b449-4051-aec4-ea814a2ad993
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f669a1f7132aa0f588fd89fb9747a7dc9017fcf1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725537"
---
# <a name="bulk-load-data-into-tables-in-a-merge-publication-replication-transact-sql-programming"></a><span data-ttu-id="33a00-102">Massenladen von Daten in Tabellen in einer Mergeveröffentlichung (Replikationsprogrammierung mit Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="33a00-102">Bulk-Load Data into Tables in a Merge Publication (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="33a00-103">Beim Laden von Daten in Tabellen unter Berücksichtigung der Informationen in [bcp Utility](../../tools/bcp-utility.md) oder mithilfe des [BULK INSERT](/sql/t-sql/statements/bulk-insert-transact-sql) -Befehls werden die Mergereplikationstrigger, die die internen Überwachungsdaten in der [MSmerge_contents](/sql/relational-databases/system-tables/msmerge-contents-transact-sql) -Systemtabelle verwalten, standardmäßig nicht ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="33a00-103">When data is loaded into tables using the [bcp Utility](../../tools/bcp-utility.md) or the [BULK INSERT](/sql/t-sql/statements/bulk-insert-transact-sql) command, by default, the merge replication triggers that maintain tracking data in the [MSmerge_contents](/sql/relational-databases/system-tables/msmerge-contents-transact-sql) system table are not fired.</span></span> <span data-ttu-id="33a00-104">Sie haben die Möglichkeit, das Auslösen der Mergereplikationstrigger beim Laden der Daten zu erzwingen, oder Sie können die generierten Replikationsmetadaten programmgesteuert nach dem Massenkopiervorgang mithilfe gespeicherter Replikationsprozeduren einfügen.</span><span class="sxs-lookup"><span data-stu-id="33a00-104">You can either force the merge replication triggers to fire as the data is loaded, or you can insert the generated replication metadata programmatically after the bulk copy operation using replication stored procedures.</span></span>  
  
### <a name="to-bulk-load-data-into-tables-published-by-merge-replication-using-the-bcp-utility"></a><span data-ttu-id="33a00-105">So können Sie mit dem Hilfsprogramm "bcp" Daten per Massenladevorgang in mithilfe der Mergereplikation veröffentlichte Tabellen laden</span><span class="sxs-lookup"><span data-stu-id="33a00-105">To bulk-load data into tables published by merge replication using the bcp utility</span></span>  
  
1.  <span data-ttu-id="33a00-106">Führen Sie auf dem Verleger oder dem Abonnenten das Hilfsprogramm [bcp Utility](../../tools/bcp-utility.md) oder [BULK INSERT](/sql/t-sql/statements/bulk-insert-transact-sql) aus, um Daten in eine mithilfe der Mergereplikation veröffentlichte Tabelle einzufügen.</span><span class="sxs-lookup"><span data-stu-id="33a00-106">At either the Publisher or Subscriber, execute the [bcp Utility](../../tools/bcp-utility.md) or [BULK INSERT](/sql/t-sql/statements/bulk-insert-transact-sql) to insert data into a table published using merge replication.</span></span>  
  
2.  <span data-ttu-id="33a00-107">Verwenden Sie eine der folgenden Methoden, um sicherzustellen, dass die Replikationsmetadaten für die eingefügten Daten generiert werden.</span><span class="sxs-lookup"><span data-stu-id="33a00-107">Use one of the following methods to ensure that replication metadata is generated for the inserted data.</span></span>  
  
    -   <span data-ttu-id="33a00-108">Führen Sie den Massenkopiervorgang mithilfe der FIRE_TRIGGERS-Option aus.</span><span class="sxs-lookup"><span data-stu-id="33a00-108">Execute the bulk copy using the FIRE_TRIGGERS option.</span></span>  
  
    -   <span data-ttu-id="33a00-109">Führen Sie in der Datenbank, in die Daten eingefügt wurden, [sp_addtabletocontents (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-addtabletocontents-transact-sql) aus.</span><span class="sxs-lookup"><span data-stu-id="33a00-109">On the database into which data was inserted, execute [sp_addtabletocontents &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addtabletocontents-transact-sql).</span></span> <span data-ttu-id="33a00-110">Geben Sie den Namen der Tabelle an, in die die Daten eingefügt wurden **@table_name** .</span><span class="sxs-lookup"><span data-stu-id="33a00-110">Specify the table name into which the data was inserted for **@table_name**.</span></span>  
  
  
