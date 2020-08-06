---
title: Konfigurieren eines Pakets für die Verwendung von Transaktionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- transactions [Integration Services], configuring packages to use
ms.assetid: 8bf14957-27b4-456b-81d9-e1a0e0ca94b7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f469c2439deb2d16ac9046a1628e82c34e39b31d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697081"
---
# <a name="configure-a-package-to-use-transactions"></a><span data-ttu-id="bbe6b-102">Konfigurieren eines Pakets für die Verwendung von Transaktionen</span><span class="sxs-lookup"><span data-stu-id="bbe6b-102">Configure a Package to Use Transactions</span></span>
  <span data-ttu-id="bbe6b-103">Beim Konfigurieren eines Pakets zur Verwendung von Transaktionen stehen zwei Optionen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="bbe6b-103">When you configure a package to use transactions, you have two options:</span></span>  
  
-   <span data-ttu-id="bbe6b-104">Eine einzelne Transaktion für das Paket.</span><span class="sxs-lookup"><span data-stu-id="bbe6b-104">Have a single transaction for the package.</span></span> <span data-ttu-id="bbe6b-105">In diesem Fall wird diese Transaktion durch das Paket selbst *initiiert* , während einzelne Tasks und Container des Pakets an dieser einzelnen Transaktion beteiligt sind.</span><span class="sxs-lookup"><span data-stu-id="bbe6b-105">In this case, it is the package itself that *initiates* this transaction, whereas individual tasks and containers in the package participate in this single transaction.</span></span>  
  
-   <span data-ttu-id="bbe6b-106">Mehrere Transaktionen im Paket.</span><span class="sxs-lookup"><span data-stu-id="bbe6b-106">Have multiple transactions in the package.</span></span> <span data-ttu-id="bbe6b-107">In diesem Fall unterstützt das Paket Transaktionen, die Transaktionen werden jedoch tatsächlich von einzelnen Tasks und Containern im Paket initiiert.</span><span class="sxs-lookup"><span data-stu-id="bbe6b-107">In this case, the package supports transactions, but individual tasks and containers in the package actually initiate the transactions.</span></span>  
  
 <span data-ttu-id="bbe6b-108">Im Folgenden wird beschrieben, wie beide Optionen konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="bbe6b-108">The following procedures describe how to configure both options.</span></span>  
  
## <a name="configuring-a-single-transaction"></a><span data-ttu-id="bbe6b-109">Konfigurieren einer einzelnen Transaktion</span><span class="sxs-lookup"><span data-stu-id="bbe6b-109">Configuring a Single Transaction</span></span>  
 <span data-ttu-id="bbe6b-110">Mit dieser Option initiiert das Paket selbst eine einzelne Transaktion.</span><span class="sxs-lookup"><span data-stu-id="bbe6b-110">In this option, the package itself initiates a single transaction.</span></span> <span data-ttu-id="bbe6b-111">Sie konfigurieren das Paket zum Initiieren dieser Transaktion, indem Sie die transaktionoption-Eigenschaft des Pakets auf festlegen `Required` .</span><span class="sxs-lookup"><span data-stu-id="bbe6b-111">You configure the package to initiate this transaction by setting the TransactionOption property of the package to `Required`.</span></span>  
  
 <span data-ttu-id="bbe6b-112">Danach tragen Sie bestimmte Tasks und Container in dieser einzelnen Transaktion ein.</span><span class="sxs-lookup"><span data-stu-id="bbe6b-112">Next, you enlist specific tasks and containers in this single transaction.</span></span> <span data-ttu-id="bbe6b-113">Zum Eintragen eines Tasks oder Containers in einer Transaktion legen Sie die transaktionoption-Eigenschaft dieses Tasks oder Containers auf fest `Supported` .</span><span class="sxs-lookup"><span data-stu-id="bbe6b-113">To enlist a task or container in a transaction, you set the TransactionOption property of that task or container to `Supported`.</span></span>  
  
#### <a name="to-configure-a-package-to-use-a-single-transaction"></a><span data-ttu-id="bbe6b-114">So konfigurieren Sie ein Paket zur Verwendung einer einzelnen Transaktion</span><span class="sxs-lookup"><span data-stu-id="bbe6b-114">To configure a package to use a single transaction</span></span>  
  
1.  <span data-ttu-id="bbe6b-115">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekt mit dem Paket, für das Sie die Verwendung einer Transaktion konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="bbe6b-115">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want to configure to use a transaction.</span></span>  
  
2.  <span data-ttu-id="bbe6b-116">Doppelklicken Sie im Projektmappen-Explorer auf das Paket, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="bbe6b-116">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="bbe6b-117">Klicken Sie auf die Registerkarte **Ablaufsteuerung** .</span><span class="sxs-lookup"><span data-stu-id="bbe6b-117">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="bbe6b-118">Klicken Sie mit der rechten Maustaste an einer beliebigen Stelle im Hintergrund der Entwurfsoberfläche der Ablaufsteuerung, und klicken Sie anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="bbe6b-118">Right-click anywhere in the background of the control flow design surface, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="bbe6b-119">Legen Sie im Fenster **Eigenschaften** die transaktionoption-Eigenschaft auf fest `Required` .</span><span class="sxs-lookup"><span data-stu-id="bbe6b-119">In the **Properties** window, set the TransactionOption property to `Required`.</span></span>  
  
6.  <span data-ttu-id="bbe6b-120">Klicken Sie auf der Entwurfsoberfläche der Registerkarte **Ablaufsteuerung** mit der rechten Maustaste auf den Task oder den Container, für den Sie die Transaktion registrieren möchten, und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="bbe6b-120">On the design surface of the **ControlFlow** tab, right-click the task or the container that you want to enroll in the transaction, and then click **Properties**.</span></span>  
  
7.  <span data-ttu-id="bbe6b-121">Legen Sie im Fenster **Eigenschaften** die transaktionoption-Eigenschaft auf fest `Supported` .</span><span class="sxs-lookup"><span data-stu-id="bbe6b-121">In the **Properties** window, set the TransactionOption property to `Supported`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bbe6b-122">Um eine Verbindung in einer Transaktion einzutragen, registrieren Sie die Tasks, die die Verbindung verwenden, für die Transaktion.</span><span class="sxs-lookup"><span data-stu-id="bbe6b-122">To enlist a connection in a transaction, enroll the tasks that use the connection in the transaction.</span></span> <span data-ttu-id="bbe6b-123">Weitere Informationen finden Sie unter [Integration Services-Verbindungen &#40;SSIS&#41;](connection-manager/integration-services-ssis-connections.md).</span><span class="sxs-lookup"><span data-stu-id="bbe6b-123">For more information, see [Integration Services &#40;SSIS&#41; Connections](connection-manager/integration-services-ssis-connections.md).</span></span>  
  
8.  <span data-ttu-id="bbe6b-124">Wiederholen Sie die Schritte 6 und 7 für alle Tasks und Container, für die Sie die Transaktion registrieren möchten.</span><span class="sxs-lookup"><span data-stu-id="bbe6b-124">Repeat steps 6 and 7 for each task and container that you want to enroll in the transaction.</span></span>  
  
## <a name="configuring-multiple-transactions"></a><span data-ttu-id="bbe6b-125">Konfigurieren mehrerer Transaktionen</span><span class="sxs-lookup"><span data-stu-id="bbe6b-125">Configuring Multiple Transactions</span></span>  
 <span data-ttu-id="bbe6b-126">Mit dieser Option unterstützt das Paket selbst Transaktionen, startet jedoch keine Transaktion.</span><span class="sxs-lookup"><span data-stu-id="bbe6b-126">In this option, the package itself supports transactions but does not start a transaction.</span></span> <span data-ttu-id="bbe6b-127">Sie konfigurieren das Paket für die Unterstützung von Transaktionen, indem Sie die transaktionoption-Eigenschaft des Pakets auf festlegen `Supported` .</span><span class="sxs-lookup"><span data-stu-id="bbe6b-127">You configure the package to support transactions by setting the TransactionOption property of the package to `Supported`.</span></span>  
  
 <span data-ttu-id="bbe6b-128">Danach konfigurieren Sie die gewünschten Tasks und Container im Paket, um Transaktionen zu initiieren oder an Transaktionen teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="bbe6b-128">Next, you configure the desired tasks and containers inside the package to initiate or participate in transactions.</span></span> <span data-ttu-id="bbe6b-129">Zum Konfigurieren eines Tasks oder Containers zum Initiieren einer Transaktion legen Sie die transaktionoption-Eigenschaft dieses Tasks oder Containers auf fest `Required` .</span><span class="sxs-lookup"><span data-stu-id="bbe6b-129">To configure a task or container to initiate a transaction, you set the TransactionOption property of that task or container to `Required`.</span></span>  
  
#### <a name="to-configure-a-package-to-use-multiple-transactions"></a><span data-ttu-id="bbe6b-130">So konfigurieren Sie die Verwendung mehrerer Transaktionen für ein Paket</span><span class="sxs-lookup"><span data-stu-id="bbe6b-130">To configure a package to use multiple transactions</span></span>  
  
1.  <span data-ttu-id="bbe6b-131">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekt mit dem Paket, das Sie für die Verwendung von Transaktionen konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="bbe6b-131">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want to configure to use transaction.s</span></span>  
  
2.  <span data-ttu-id="bbe6b-132">Doppelklicken Sie im Projektmappen-Explorer auf das Paket, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="bbe6b-132">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="bbe6b-133">Klicken Sie auf die Registerkarte **Ablaufsteuerung** .</span><span class="sxs-lookup"><span data-stu-id="bbe6b-133">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="bbe6b-134">Klicken Sie mit der rechten Maustaste an einer beliebigen Stelle im Hintergrund der Entwurfsoberfläche der Ablaufsteuerung, und klicken Sie anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="bbe6b-134">Right-click anywhere in the background of the control flow design surface, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="bbe6b-135">Legen Sie im Fenster **Eigenschaften** die transaktionoption-Eigenschaft auf fest `Supported` .</span><span class="sxs-lookup"><span data-stu-id="bbe6b-135">In the **Properties** window, set the TransactionOption property to `Supported`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bbe6b-136">Das Paket unterstützt Transaktionen, aber die Transaktionen werden von Tasks oder Containern im Paket gestartet.</span><span class="sxs-lookup"><span data-stu-id="bbe6b-136">The package supports transactions, but the transactions are started by task or containers in the package.</span></span>  
  
6.  <span data-ttu-id="bbe6b-137">Klicken Sie auf der Entwurfsoberfläche der Registerkarte **Ablaufsteuerung** mit der rechten Maustaste auf den Task oder den Container im Paket, für den Sie eine Transaktion starten möchten, und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="bbe6b-137">On the design surface of the **ControlFlow** tab, right-click the task or the container in the package for which you want to start a transaction, and then click **Properties**.</span></span>  
  
7.  <span data-ttu-id="bbe6b-138">Legen Sie im Fenster **Eigenschaften** die transaktionoption-Eigenschaft auf fest `Required` .</span><span class="sxs-lookup"><span data-stu-id="bbe6b-138">In the **Properties** window, set the TransactionOption property to `Required`.</span></span>  
  
8.  <span data-ttu-id="bbe6b-139">Wenn eine Transaktion von einem Container gestartet wird, klicken Sie mit der rechten Maustaste auf den Task oder den Container, für den Sie die Transaktion registrieren möchten, und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="bbe6b-139">If a transaction is started by a container, right-click the task or the container that you want to enroll in the transaction, and then click **Properties**.</span></span>  
  
9. <span data-ttu-id="bbe6b-140">Legen Sie im Fenster **Eigenschaften** die transaktionoption-Eigenschaft auf fest `Supported` .</span><span class="sxs-lookup"><span data-stu-id="bbe6b-140">In the **Properties** window, set the TransactionOption property to `Supported`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bbe6b-141">Um eine Verbindung in einer Transaktion einzutragen, registrieren Sie die Tasks, die die Verbindung verwenden, für die Transaktion.</span><span class="sxs-lookup"><span data-stu-id="bbe6b-141">To enlist a connection in a transaction, enroll the tasks that use the connection in the transaction.</span></span> <span data-ttu-id="bbe6b-142">Weitere Informationen finden Sie unter [Integration Services-Verbindungen &#40;SSIS&#41;](connection-manager/integration-services-ssis-connections.md).</span><span class="sxs-lookup"><span data-stu-id="bbe6b-142">For more information, see [Integration Services &#40;SSIS&#41; Connections](connection-manager/integration-services-ssis-connections.md).</span></span>  
  
10. <span data-ttu-id="bbe6b-143">Wiederholen Sie die Schritte 6 bis 9 für alle Tasks und Container, die eine Transaktion initiieren.</span><span class="sxs-lookup"><span data-stu-id="bbe6b-143">Repeat steps 6 through 9 for each task and container that starts a transaction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbe6b-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bbe6b-144">See Also</span></span>  
 [<span data-ttu-id="bbe6b-145">Integration Services-Transaktionen</span><span class="sxs-lookup"><span data-stu-id="bbe6b-145">Integration Services Transactions</span></span>](integration-services-transactions.md)  
  
  
