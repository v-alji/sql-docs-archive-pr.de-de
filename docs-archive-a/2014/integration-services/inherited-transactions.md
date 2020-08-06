---
title: Geerbte Transaktionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- transactions [Integration Services], inherited
- child packages
- inherited transactions [Integration Services]
ms.assetid: 90db5564-d41e-4cfe-8c9e-4e68d41eff1c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0ecb480420fe9f2492c29fad37ee3cc6e6501e3a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618192"
---
# <a name="inherited-transactions"></a><span data-ttu-id="28e97-102">Vererbte Transaktionen</span><span class="sxs-lookup"><span data-stu-id="28e97-102">Inherited Transactions</span></span>
  <span data-ttu-id="28e97-103">Ein Paket kann mithilfe des Tasks "Paket ausführen" ein anderes Paket ausführen.</span><span class="sxs-lookup"><span data-stu-id="28e97-103">A package can run another package by using the Execute Package task.</span></span> <span data-ttu-id="28e97-104">Das untergeordnete Paket, d. h. das von dem Task Paket ausführen ausgeführte Paket, kann seine eigene Pakettransaktion erstellen oder aber die Pakettransaktion des übergeordneten Pakets erben.</span><span class="sxs-lookup"><span data-stu-id="28e97-104">The child package, which is the package run by the Execute Package task, may create its own package transaction, or it may inherit the parent package transaction.</span></span>  
  
 <span data-ttu-id="28e97-105">Ein untergeordnetes Paket erbt die übergeordnete Pakettransaktion, wenn die beiden folgenden Bedingungen erfüllt sind:</span><span class="sxs-lookup"><span data-stu-id="28e97-105">A child package inherits the parent package transaction if both of the following are true:</span></span>  
  
-   <span data-ttu-id="28e97-106">Das Paket wird durch einen Task Paket ausführen aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="28e97-106">The package is invoked by an Execute Package task.</span></span>  
  
-   <span data-ttu-id="28e97-107">Der Task Paket ausführen, der das Paket aufgerufen hat, nimmt ebenfalls an der übergeordneten Pakettransaktion teil.</span><span class="sxs-lookup"><span data-stu-id="28e97-107">The Execute Package task that invoked the package also joined the parent package transaction.</span></span>  
  
 <span data-ttu-id="28e97-108">Container und Tasks des untergeordneten Pakets können nicht an der übergeordneten Pakettransaktion teilnehmen, es sei denn, das untergeordnete Paket nimmt selbst an der Transaktion teil.</span><span class="sxs-lookup"><span data-stu-id="28e97-108">Containers and tasks in the child package cannot join the parent package transaction unless the child package itself joins the transaction.</span></span>  
  
## <a name="illustration-of-package-transactions"></a><span data-ttu-id="28e97-109">Abbildung von Pakettransaktionen</span><span class="sxs-lookup"><span data-stu-id="28e97-109">Illustration of Package Transactions</span></span>  
 <span data-ttu-id="28e97-110">Im folgenden Diagramm sind drei Pakete zu sehen, die Transaktionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="28e97-110">In the following diagram, there are three packages that all use transactions.</span></span> <span data-ttu-id="28e97-111">Jedes Paket enthält zahlreiche Tasks.</span><span class="sxs-lookup"><span data-stu-id="28e97-111">Each package contains multiple tasks.</span></span> <span data-ttu-id="28e97-112">Um das Verhalten der Transaktionen zu verdeutlichen, werden nur die Tasks Paket ausführen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="28e97-112">To emphasize the behavior of the transactions, only the Execute Package tasks are shown.</span></span> <span data-ttu-id="28e97-113">Das Paket A führt die Pakete B und C aus. Das Paket B wiederum führt die Pakete D und E aus, und das Paket C führt das Paket F aus.</span><span class="sxs-lookup"><span data-stu-id="28e97-113">Package A runs packages B and C. In turn, package B runs packages D and E, and package C runs package F.</span></span>  
  
 <span data-ttu-id="28e97-114">Die Pakete und Tasks besitzen die folgenden Transaktionsattribute:</span><span class="sxs-lookup"><span data-stu-id="28e97-114">Packages and tasks have the following transaction attributes:</span></span>  
  
-   <span data-ttu-id="28e97-115">**TransactionOption** ist für die Pakete A und C auf **Required** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="28e97-115">**TransactionOption** is set to **Required** on packages A and C</span></span>  
  
-   <span data-ttu-id="28e97-116">**TransactionOption** ist für die Pakete B und D sowie für die Tasks Paket ausführen B, Paket ausführen D und Paket ausführen F auf **Supported** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="28e97-116">**TransactionOption** is set to **Supported** on packages B and D, and on the tasks Execute Package B, Execute Package D, and Execute Package F.</span></span>  
  
-   <span data-ttu-id="28e97-117">**TransactionOption** ist für das Paket E sowie für die Tasks Paket ausführen C und Paket ausführen E auf **NotSupported** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="28e97-117">**TransactionOption** is set to **NotSupported** on package E, and on the tasks Execute Package C and Execute Package E.</span></span>  
  
 <span data-ttu-id="28e97-118">![Flow von vererbten Transaktionen](media/mw-dts-executepack.gif "Flow von vererbten Transaktionen")</span><span class="sxs-lookup"><span data-stu-id="28e97-118">![Flow of inherited transactions](media/mw-dts-executepack.gif "Flow of inherited transactions")</span></span>  
  
 <span data-ttu-id="28e97-119">Nur die Pakete B, D und F können Transaktionen von ihren übergeordneten Paketen erben.</span><span class="sxs-lookup"><span data-stu-id="28e97-119">Only packages B, D, and F can inherit transactions from their parent packages.</span></span>  
  
 <span data-ttu-id="28e97-120">Die Pakete B und D erben die Transaktion, die von Paket A gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="28e97-120">Packages B and D inherit the transaction that was started by package A.</span></span>  
  
 <span data-ttu-id="28e97-121">Das Paket F erbt die Transaktion, die von Paket C gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="28e97-121">Package F inherits the transaction that was started by package C.</span></span>  
  
 <span data-ttu-id="28e97-122">Die Pakete A und C steuern ihre eigenen Transaktionen.</span><span class="sxs-lookup"><span data-stu-id="28e97-122">Packages A and C control their own transactions.</span></span>  
  
 <span data-ttu-id="28e97-123">Das Paket E verwendet keine Transaktionen.</span><span class="sxs-lookup"><span data-stu-id="28e97-123">Package E does not use transactions.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="28e97-124">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="28e97-124">Related Tasks</span></span>  
 [<span data-ttu-id="28e97-125">Konfigurieren eines Pakets für die Verwendung von Transaktionen</span><span class="sxs-lookup"><span data-stu-id="28e97-125">Configure a Package to Use Transactions</span></span>](../relational-databases/native-client-ole-db-transactions/transactions.md)  
  
  
