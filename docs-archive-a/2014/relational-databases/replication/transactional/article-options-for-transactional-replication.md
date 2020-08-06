---
title: Article Options for Transactional Replication | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- articles [SQL Server replication], transactional replication options
- transactional replication, article options
ms.assetid: 3469b185-0ea5-4690-a71c-717230d886b6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1cc13a3d11e35ed47eac4ff401fb8b7cb607b32b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618637"
---
# <a name="article-options-for-transactional-replication"></a><span data-ttu-id="19494-102">Artikeloptionen für die Transaktionsreplikation</span><span class="sxs-lookup"><span data-stu-id="19494-102">Article Options for Transactional Replication</span></span>
  <span data-ttu-id="19494-103">Für Artikel in Transaktionsveröffentlichungen stehen eine Reihe von Optionen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="19494-103">There are a number of options for articles in transactional publications.</span></span> <span data-ttu-id="19494-104">Bei der Transaktionsreplikation haben Sie folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="19494-104">With transactional replication, you can do the following:</span></span>  
  
-   <span data-ttu-id="19494-105">Sie können angeben, wie Änderungen vom Verleger an Abonnenten weitergegeben werden.</span><span class="sxs-lookup"><span data-stu-id="19494-105">Specify how changes are propagated from the Publisher to Subscribers.</span></span> <span data-ttu-id="19494-106">Weitere Informationen finden Sie unter [Angeben der Weitergabemethode für Änderungen bei Transaktionsartikeln](transactional-articles-specify-how-changes-are-propagated.md).</span><span class="sxs-lookup"><span data-stu-id="19494-106">For more information, see [Specify How Changes Are Propagated for Transactional Articles](transactional-articles-specify-how-changes-are-propagated.md).</span></span>  
  
-   <span data-ttu-id="19494-107">Sie können angeben, dass die Ausführung einer gespeicherten Prozedur repliziert wird.</span><span class="sxs-lookup"><span data-stu-id="19494-107">Specify that the execution of a stored procedure be replicated.</span></span> <span data-ttu-id="19494-108">Dies ist bei der Replikation der Ergebnisse von wartungsorientierten gespeicherten Prozeduren hilfreich, die sich möglicherweise auf große Datenmengen auswirken.</span><span class="sxs-lookup"><span data-stu-id="19494-108">This is useful in replicating the results of maintenance-oriented stored procedures that affect large amounts of data.</span></span> <span data-ttu-id="19494-109">Weitere Informationen finden Sie unter [Publishing Stored Procedure Execution in Transactional Replication](publishing-stored-procedure-execution-in-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="19494-109">For more information, see [Publishing Stored Procedure Execution in Transactional Replication](publishing-stored-procedure-execution-in-transactional-replication.md).</span></span>  
  
-   <span data-ttu-id="19494-110">Sie können Schemaoptionen angeben, beispielsweise ob Einschränkungen und Trigger auf den Abonnenten kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="19494-110">Specify schema options, such as whether constraints and triggers are copied to the Subscriber.</span></span> <span data-ttu-id="19494-111">Weitere Informationen finden Sie unter [Angeben von Schemaoptionen](../publish/specify-schema-options.md).</span><span class="sxs-lookup"><span data-stu-id="19494-111">For more information, see [Specify Schema Options](../publish/specify-schema-options.md).</span></span>  
  
-   <span data-ttu-id="19494-112">Sie können Zeilenfilter und Spaltenfilter verwenden.</span><span class="sxs-lookup"><span data-stu-id="19494-112">Use row filters and column filters.</span></span> <span data-ttu-id="19494-113">Das Filtern von Tabellenartikeln ermöglicht es Ihnen, Datenpartitionen zu erstellen, die veröffentlicht werden können.</span><span class="sxs-lookup"><span data-stu-id="19494-113">Filtering table articles enables you to create partitions of data to be published.</span></span> <span data-ttu-id="19494-114">Weitere Informationen finden Sie unter [Filtern von veröffentlichten Daten](../publish/filter-published-data.md).</span><span class="sxs-lookup"><span data-stu-id="19494-114">For more information, see [Filter Published Data](../publish/filter-published-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19494-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="19494-115">See Also</span></span>  
 [<span data-ttu-id="19494-116">Veröffentlichen von Daten und Datenbankobjekten</span><span class="sxs-lookup"><span data-stu-id="19494-116">Publish Data and Database Objects</span></span>](../publish/publish-data-and-database-objects.md)  
  
  
