---
title: Mehrere Transaktionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- transactions [Integration Services], multiple
- multiple transactions
ms.assetid: c3664a94-be89-40c0-a3a0-84b74a7fedbe
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5ff909c92a23c965047edc0fcf278e17e4c76d94
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618097"
---
# <a name="multiple-transactions"></a><span data-ttu-id="7e98b-102">Mehrere Transaktionen</span><span class="sxs-lookup"><span data-stu-id="7e98b-102">Multiple Transactions</span></span>
  <span data-ttu-id="7e98b-103">Es ist möglich, dass ein Paket nicht miteinander verbundene Transaktionen in einem [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Paket enthält.</span><span class="sxs-lookup"><span data-stu-id="7e98b-103">It is possible for a package to include unrelated transactions in an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package.</span></span> <span data-ttu-id="7e98b-104">Immer wenn ein Container in der Mitte einer geschachtelten Hierarchie von Containern keine Transaktionen unterstützt, starten die Container, die sich in der Hierarchie oberhalb oder unterhalb des Containers befinden, separate Transaktionen, wenn sie für die Unterstützung von Transaktionen konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="7e98b-104">Any time a container in the middle of a nested container hierarchy does not support transactions, the containers above or below it in the hierarchy start separate transactions if they are configured to support transactions.</span></span> <span data-ttu-id="7e98b-105">Die Transaktionen führen einen Commit oder Rollback aus, und zwar nacheinander und beginnend beim innersten Task innerhalb der geschachtelten Containerhierarchie bis zum Paket.</span><span class="sxs-lookup"><span data-stu-id="7e98b-105">The transactions commit or roll back in order from the innermost task in the nested container hierarchy to the package.</span></span> <span data-ttu-id="7e98b-106">Nachdem die innere Transaktion einen Commit ausgeführt hat, erfolgt jedoch kein Rollback, wenn eine äußere Transaktion abgebrochen wird.</span><span class="sxs-lookup"><span data-stu-id="7e98b-106">However, after the inner transaction commits, it does not roll back if an outer transaction is aborted.</span></span>

## <a name="illustration-of-multiple-transactions"></a><span data-ttu-id="7e98b-107">Veranschaulichung mehrerer Transaktionen</span><span class="sxs-lookup"><span data-stu-id="7e98b-107">Illustration of Multiple Transactions</span></span>
 <span data-ttu-id="7e98b-108">Ein Paket enthält z. B. einen Sequenzcontainer, der zwei Foreach-Schleifencontainer enthält, und jeder Container enthält zwei SQL Ausführen-Tasks.</span><span class="sxs-lookup"><span data-stu-id="7e98b-108">For example, a package has a Sequence container that holds two Foreach Loop containers, and each container include two Execute SQL tasks.</span></span> <span data-ttu-id="7e98b-109">Der Sequenzcontainer und die Execute SQL-Tasks unterstützen Transaktionen, die Foreach-Schleifencontainer hingegen nicht.</span><span class="sxs-lookup"><span data-stu-id="7e98b-109">The Sequence container supports transactions, the Foreach Loop containers do not, and the Execute SQL tasks do.</span></span> <span data-ttu-id="7e98b-110">In diesem Beispiel startet jeder Execute SQL-Task seine eigene Transaktion und führt keinen Rollback aus, wenn die Transaktion auf dem Sequenztask abgebrochen wurde.</span><span class="sxs-lookup"><span data-stu-id="7e98b-110">In this example, each Execute SQL task would start its own transaction and would not roll back if the transaction on the Sequence task was aborted.</span></span>

 <span data-ttu-id="7e98b-111">Die TransactionOption-Eigenschaften des Sequenzcontainers, der Foreach-Schleifencontainer und die Tasks „SQL ausführen“ sind folgendermaßen festgelegt:</span><span class="sxs-lookup"><span data-stu-id="7e98b-111">The TransactionOption properties of the Sequence container, Foreach Loop container and the Execute SQL tasks are set as follows:</span></span>

-   <span data-ttu-id="7e98b-112">Die TransactionOption-Eigenschaft des Sequenzcontainers ist auf **Required**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="7e98b-112">The TransactionOption property of the Sequence container is set to **Required**.</span></span>

-   <span data-ttu-id="7e98b-113">Die TransactionOption-Eigenschaften der Foreach-Schleifencontainer sind auf **NotSupported**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="7e98b-113">The TransactionOption properties of the Foreach Loop containers are set to **NotSupported**.</span></span>

-   <span data-ttu-id="7e98b-114">Die TransactionOption-Eigenschaften der Tasks „SQL ausführen“ sind auf **Required**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="7e98b-114">The TransactionOption properties of the Execute SQL tasks are set to **Required**.</span></span>

 <span data-ttu-id="7e98b-115">Das folgende Diagramm zeigt die fünf nicht miteinander verbundenen Transaktionen im Paket.</span><span class="sxs-lookup"><span data-stu-id="7e98b-115">The following diagram shows the five unrelated transactions in the package.</span></span> <span data-ttu-id="7e98b-116">Eine Transaktion wird durch den Sequenzcontainer gestartet, und vier Transaktionen werden durch die SQL Ausführen-Tasks gestartet.</span><span class="sxs-lookup"><span data-stu-id="7e98b-116">One transaction is started by the Sequence container and four transactions are started by the Execute SQL tasks.</span></span>

 <span data-ttu-id="7e98b-117">![Implementierung von mehreren Transaktionen](media/mw-dts-trans2.gif "Implementierung von mehreren Transaktionen")</span><span class="sxs-lookup"><span data-stu-id="7e98b-117">![Implementation of multiple transactions](media/mw-dts-trans2.gif "Implementation of multiple transactions")</span></span>

## <a name="related-tasks"></a><span data-ttu-id="7e98b-118">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="7e98b-118">Related Tasks</span></span>
 [<span data-ttu-id="7e98b-119">Konfigurieren eines Pakets für die Verwendung von Transaktionen</span><span class="sxs-lookup"><span data-stu-id="7e98b-119">Configure a Package to Use Transactions</span></span>](../relational-databases/native-client-ole-db-transactions/transactions.md)


