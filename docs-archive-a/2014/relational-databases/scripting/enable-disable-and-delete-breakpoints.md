---
title: Aktivieren, Deaktivieren und Löschen von Breakpoints
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 357b5874-273f-43a9-8e30-83872bdea5dc
author: rothja
ms.author: jroth
ms.openlocfilehash: 17e83c6488b9d9026fb78e5fb8f50e22533fa61e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622024"
---
# <a name="enable-disable-and-delete-breakpoints"></a><span data-ttu-id="aea59-102">Aktivieren, Deaktivieren und Löschen von Breakpoints</span><span class="sxs-lookup"><span data-stu-id="aea59-102">Enable, Disable, and Delete Breakpoints</span></span>
  <span data-ttu-id="aea59-103">Zum Anzeigen und Verwalten aller offenen Breakpoints können Sie das Fenster **Breakpoints** verwenden.</span><span class="sxs-lookup"><span data-stu-id="aea59-103">To view and manage all the open breakpoints, you can use the **Breakpoints** window.</span></span> <span data-ttu-id="aea59-104">Mithilfe des Fensters können Sie Informationen zu Breakpoints anzeigen und Aktionen ausführen, z. B. Löschen, Deaktivieren und Aktivieren von Breakpoints.</span><span class="sxs-lookup"><span data-stu-id="aea59-104">Use the window to view breakpoint information and to take actions such as deleting, disabling, or enabling breakpoints.</span></span>  
  
## <a name="the-breakpoints-window"></a><span data-ttu-id="aea59-105">Fenster "Breakpoints"</span><span class="sxs-lookup"><span data-stu-id="aea59-105">The Breakpoints Window</span></span>  
 <span data-ttu-id="aea59-106">Das Fenster **Breakpoints** enthält Informationen, z. B. auf welcher Codezeile sich der Breakpoint befindet.</span><span class="sxs-lookup"><span data-stu-id="aea59-106">The **Breakpoints** window lists information such as which line of code the breakpoint is located on.</span></span> <span data-ttu-id="aea59-107">Außerdem können Sie im Fenster **Breakpoints** Breakpoints löschen, deaktivieren und aktivieren.</span><span class="sxs-lookup"><span data-stu-id="aea59-107">In the **Breakpoints** window, you can also delete, disable, and enable breakpoints.</span></span> <span data-ttu-id="aea59-108">Weitere Informationen zum Fenster **Breakpoints** finden Sie unter [Breakpoints Window](transact-sql-debugger-breakpoints-window.md).</span><span class="sxs-lookup"><span data-stu-id="aea59-108">For more information about the **Breakpoints** window, see [Breakpoints Window](transact-sql-debugger-breakpoints-window.md)</span></span>  
  
 <span data-ttu-id="aea59-109">Durch das Deaktivieren von Breakpoints wird verhindert, dass der Breakpoint die Ausführung anhält, wobei die Definition jedoch beibehalten wird, falls Sie den Breakpoint später aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="aea59-109">Disabling a breakpoint prevents it from pausing execution, but leaves the definition in place in case you want to enable the breakpoint later.</span></span> <span data-ttu-id="aea59-110">Durch das Löschen von Breakpoints werden sie endgültig gelöscht.</span><span class="sxs-lookup"><span data-stu-id="aea59-110">Deleting a breakpoint removes it permanently.</span></span> <span data-ttu-id="aea59-111">Sie müssen einen neuen Breakpoint umschalten, um die Ausführung für die Anweisung anzuhalten.</span><span class="sxs-lookup"><span data-stu-id="aea59-111">You must toggle a new breakpoint to pause execution on the statement.</span></span>  
  
## <a name="to-open-the-breakpoints-window"></a><span data-ttu-id="aea59-112">So öffnen Sie das Fenster "Breakpoints"</span><span class="sxs-lookup"><span data-stu-id="aea59-112">To Open the Breakpoints Window</span></span>  
 <span data-ttu-id="aea59-113">**To open the Breakpoints window**</span><span class="sxs-lookup"><span data-stu-id="aea59-113">**To open the Breakpoints window**</span></span>  
  
 <span data-ttu-id="aea59-114">Zum Öffnen des Fensters **Breakpoints** haben Sie folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="aea59-114">You can open the **Breakpoints** window in one of the following ways:</span></span>  
  
-   <span data-ttu-id="aea59-115">Klicken Sie im Menü **Debuggen** auf **Fenster**und dann auf **Breakpoints**.</span><span class="sxs-lookup"><span data-stu-id="aea59-115">On the **Debug** menu, click **Windows**, and then click **Breakpoints**.</span></span>  
  
-   <span data-ttu-id="aea59-116">Klicken Sie auf der Symbolleiste **Debuggen** auf die Schaltfläche **Breakpoints** .</span><span class="sxs-lookup"><span data-stu-id="aea59-116">On the **Debug** toolbar, click the **Breakpoints** button.</span></span>  
  
-   <span data-ttu-id="aea59-117">Drücken Sie STRG+ALT+B.</span><span class="sxs-lookup"><span data-stu-id="aea59-117">Press CTRL+ALT+B.</span></span>  
  
## <a name="to-disable-a-single-breakpoint"></a><span data-ttu-id="aea59-118">So deaktivieren Sie einen einzelnen Breakpoint</span><span class="sxs-lookup"><span data-stu-id="aea59-118">To Disable a Single Breakpoint</span></span>  
 <span data-ttu-id="aea59-119">**To disable a single breakpoint**</span><span class="sxs-lookup"><span data-stu-id="aea59-119">**To disable a single breakpoint**</span></span>  
  
 <span data-ttu-id="aea59-120">Sie können einen einzelnen Breakpoint folgendermaßen deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="aea59-120">You can disable a single breakpoint in one of the following ways:</span></span>  
  
-   <span data-ttu-id="aea59-121">Klicken Sie im Fenster „Abfrage-Editor“ mit der rechten Maustaste auf den Breakpoint, und klicken Sie anschließend auf **Breakpoint deaktivieren**.</span><span class="sxs-lookup"><span data-stu-id="aea59-121">In the Query Editor window, right-click the breakpoint, and then click **Disable Breakpoint**.</span></span>  
  
-   <span data-ttu-id="aea59-122">Deaktivieren Sie im Fenster "Breakpoints" das Kontrollkästchen links neben dem Breakpoint.</span><span class="sxs-lookup"><span data-stu-id="aea59-122">In the Breakpoints window, clear the check box to the left of the breakpoint.</span></span>  
  
## <a name="to-disable-all-breakpoints"></a><span data-ttu-id="aea59-123">So deaktivieren Sie alle Breakpoints</span><span class="sxs-lookup"><span data-stu-id="aea59-123">To Disable All Breakpoints</span></span>  
 <span data-ttu-id="aea59-124">**To disable all breakpoints**</span><span class="sxs-lookup"><span data-stu-id="aea59-124">**To disable all breakpoints**</span></span>  
  
 <span data-ttu-id="aea59-125">Sie können alle Breakpoints folgendermaßen deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="aea59-125">You can disable all breakpoints in one of the following ways:</span></span>  
  
-   <span data-ttu-id="aea59-126">Klicken Sie im Menü **Debuggen** auf **Alle Breakpoints deaktivieren**.</span><span class="sxs-lookup"><span data-stu-id="aea59-126">On the **Debug** menu, click **Disable All Breakpoints**.</span></span>  
  
-   <span data-ttu-id="aea59-127">Klicken Sie auf der Symbolleiste des Fensters **Breakpoints** auf die Schaltfläche **Alle Breakpoints deaktivieren** .</span><span class="sxs-lookup"><span data-stu-id="aea59-127">On the toolbar of the **Breakpoints** window, click the **Disable All Breakpoints** button.</span></span>  
  
## <a name="to-enable-a-single-breakpoint"></a><span data-ttu-id="aea59-128">So aktivieren Sie einen einzelnen Breakpoint</span><span class="sxs-lookup"><span data-stu-id="aea59-128">To Enable a Single Breakpoint</span></span>  
 <span data-ttu-id="aea59-129">**To enable a single breakpoint**</span><span class="sxs-lookup"><span data-stu-id="aea59-129">**To enable a single breakpoint**</span></span>  
  
 <span data-ttu-id="aea59-130">Sie können einen einzelnen Breakpoint folgendermaßen aktivieren:</span><span class="sxs-lookup"><span data-stu-id="aea59-130">You can enable a single breakpoint in one of the following ways:</span></span>  
  
-   <span data-ttu-id="aea59-131">Klicken Sie im Fenster „Abfrage-Editor“ mit der rechten Maustaste auf den Breakpoint, und klicken Sie anschließend auf **Breakpoint aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="aea59-131">In the Query Editor window, right-click the breakpoint, and then click **Enable Breakpoint**.</span></span>  
  
-   <span data-ttu-id="aea59-132">Aktivieren Sie im Fenster "Breakpoints" das Kontrollkästchen links neben dem Breakpoint.</span><span class="sxs-lookup"><span data-stu-id="aea59-132">In the Breakpoints window, click the box to the left of the breakpoint.</span></span>  
  
## <a name="to-enable-all-breakpoints"></a><span data-ttu-id="aea59-133">So aktivieren Sie alle Breakpoints</span><span class="sxs-lookup"><span data-stu-id="aea59-133">To Enable All Breakpoints</span></span>  
 <span data-ttu-id="aea59-134">**To enable all breakpoints**</span><span class="sxs-lookup"><span data-stu-id="aea59-134">**To enable all breakpoints**</span></span>  
  
 <span data-ttu-id="aea59-135">Sie können alle Breakpoints folgendermaßen aktivieren:</span><span class="sxs-lookup"><span data-stu-id="aea59-135">You can enable all breakpoints in one of the following ways:</span></span>  
  
-   <span data-ttu-id="aea59-136">Klicken Sie im Menü **Debuggen** auf **Alle Breakpoints aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="aea59-136">On the **Debug** menu, click **Enable All Breakpoints**.</span></span>  
  
-   <span data-ttu-id="aea59-137">Klicken Sie auf der Symbolleiste des Fensters **Breakpoints** auf die Schaltfläche **Alle Breakpoints aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="aea59-137">On the toolbar of the **Breakpoints** window, click the **Enable All Breakpoints** button.</span></span>  
  
## <a name="to-delete-a-single-breakpoint"></a><span data-ttu-id="aea59-138">So löschen Sie einen einzelnen Breakpoint</span><span class="sxs-lookup"><span data-stu-id="aea59-138">To Delete a Single Breakpoint</span></span>  
 <span data-ttu-id="aea59-139">**To delete a single breakpoint**</span><span class="sxs-lookup"><span data-stu-id="aea59-139">**To delete a single breakpoint**</span></span>  
  
 <span data-ttu-id="aea59-140">Sie können einen einzelnen Breakpoint folgendermaßen löschen:</span><span class="sxs-lookup"><span data-stu-id="aea59-140">You can delete a single breakpoint in one of the following ways:</span></span>  
  
-   <span data-ttu-id="aea59-141">Klicken Sie im Fenster „Abfrage-Editor“ mit der rechten Maustaste auf den Breakpoint, und klicken Sie anschließend auf **Breakpoint löschen**.</span><span class="sxs-lookup"><span data-stu-id="aea59-141">In the Query Editor window, right-click the breakpoint, and then click **Delete Breakpoint**.</span></span>  
  
-   <span data-ttu-id="aea59-142">Klicken Sie im Fenster „Breakpoints“ mit der rechten Maustaste auf den Breakpoint, und klicken Sie anschließend im Kontextmenü auf **Löschen** .</span><span class="sxs-lookup"><span data-stu-id="aea59-142">In the Breakpoints window, right-click the breakpoint, and then click **Delete** on the shortcut menu.</span></span>  
  
-   <span data-ttu-id="aea59-143">Wählen Sie im Fenster "Breakpoints" den Breakpoint aus, und drücken Sie dann ENTF.</span><span class="sxs-lookup"><span data-stu-id="aea59-143">In the Breakpoints window, select the breakpoint, and then press DELETE.</span></span>  
  
## <a name="to-delete-all-breakpoints"></a><span data-ttu-id="aea59-144">So löschen Sie alle Breakpoints</span><span class="sxs-lookup"><span data-stu-id="aea59-144">To Delete All Breakpoints</span></span>  
 <span data-ttu-id="aea59-145">**To delete all breakpoints**</span><span class="sxs-lookup"><span data-stu-id="aea59-145">**To delete all breakpoints**</span></span>  
  
 <span data-ttu-id="aea59-146">Sie können alle Breakpoints folgendermaßen löschen:</span><span class="sxs-lookup"><span data-stu-id="aea59-146">You can delete all breakpoints in one of the following ways:</span></span>  
  
-   <span data-ttu-id="aea59-147">Klicken Sie im Menü **Debuggen** auf **Alle Breakpoints löschen**.</span><span class="sxs-lookup"><span data-stu-id="aea59-147">On the **Debug** menu, cllick **Delete All Breakpoints**.</span></span>  
  
-   <span data-ttu-id="aea59-148">Klicken Sie auf der Symbolleiste des Fensters **Breakpoints** auf die Schaltfläche **Alle Breakpoints löschen** .</span><span class="sxs-lookup"><span data-stu-id="aea59-148">On the toolbar of the **Breakpoints** window, click the **Delete All Breakpoints** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aea59-149">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="aea59-149">See Also</span></span>  
 [<span data-ttu-id="aea59-150">Ein- und Ausschalten eines Breakpoints</span><span class="sxs-lookup"><span data-stu-id="aea59-150">Toggle a Breakpoint</span></span>](../spatial/point.md)  
  
  
