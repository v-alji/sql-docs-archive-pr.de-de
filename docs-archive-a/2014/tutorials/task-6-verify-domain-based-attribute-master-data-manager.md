---
title: 'Aufgabe 6: überprüfen, ob das Domänen basierte Attribut mit Master Data Manager erstellt wurde | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 6e90517a-910c-4c33-8f11-92ac3cff4fdc
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ea26202ca9e607058b1e385957be3ea3d04038b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608135"
---
# <a name="task-6-verify-that-the-domain-based-attribute-is-created-using-master-data-manager"></a><span data-ttu-id="0fb49-102">Aufgabe 6: Überprüfen, ob das domänenbasierte Attribut mithilfe von Master Data Manager erstellt wurde</span><span class="sxs-lookup"><span data-stu-id="0fb49-102">Task 6: Verify that the Domain-Based Attribute is Created using Master Data Manager</span></span>
  <span data-ttu-id="0fb49-103">In dieser Aufgabe überprüfen Sie mit **Master Data Manager**, ob die Entität **Bundesland** in **MDS** erstellt wird und ob das Attribut **Bundesland** der Entität **Lieferant** ein domänenbasiertes Attribut ist, das von der Entität **Bundesland** abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="0fb49-103">In this task, you verify that the **State** entity is created in **MDS** and the **State** attribute of the **Supplier** entity is a domain-based attribute that depends on the **State** entity by using **Master Data Manager**.</span></span>

1.  <span data-ttu-id="0fb49-104">Wechseln Sie zur **Master Data Manger**-Webanwendung.</span><span class="sxs-lookup"><span data-stu-id="0fb49-104">Switch to the **Master Data Manger** web application.</span></span>

2.  <span data-ttu-id="0fb49-105">Klicken Sie oben auf **SQL Server 2012 Master Data Services**, um zur Startseite zu gelangen.</span><span class="sxs-lookup"><span data-stu-id="0fb49-105">Click **SQL Server 2012 Master Data Services** at the top to get to the home page.</span></span>

3.  <span data-ttu-id="0fb49-106">Stellen Sie sicher, dass das Modell **Lieferanten** ausgewählt ist, und klicken Sie auf **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="0fb49-106">Ensure that **Suppliers** model is selected and click **Explorer**.</span></span> <span data-ttu-id="0fb49-107">Sie können die Seite aktualisieren, wenn **Explorer** bereits geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="0fb49-107">You could refresh the page if you already had **Explorer** open.</span></span>

4.  <span data-ttu-id="0fb49-108">Bewegen Sie die Maus über **Entitäten** in der Menüleiste. Es sind nun zwei Entitäten vorhanden: **Supplier** und **State**.</span><span class="sxs-lookup"><span data-stu-id="0fb49-108">Hover your mouse over **Entities** on the menu bar and notice that now there are two entities: **Supplier** and **State**.</span></span>

     <span data-ttu-id="0fb49-109">![Menü "Entitäten" mit Bundesland und Lieferant](../../2014/tutorials/media/et-verifythatthedbaiscreatedusingmdm-01.jpg "Menü "Entitäten" mit Bundesland und Lieferant")</span><span class="sxs-lookup"><span data-stu-id="0fb49-109">![Entities Menu with State and Supplier](../../2014/tutorials/media/et-verifythatthedbaiscreatedusingmdm-01.jpg "Entities Menu with State and Supplier")</span></span>

5.  <span data-ttu-id="0fb49-110">Klicken Sie auf **Bundesland**, wenn die Entität noch nicht geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="0fb49-110">Click **State** if the entity is not open already.</span></span>

6.  <span data-ttu-id="0fb49-111">Wählen Sie **GA** aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="0fb49-111">Select **GA** from the list.</span></span>

7.  <span data-ttu-id="0fb49-112">Ändern Sie im rechten Bereich **Details** den **Name**n im **rechten Bereich** in **Georgia**, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="0fb49-112">In the **Details** pane to the right, change the **Name** to **Georgia** in the **right pane**, and click **OK**.</span></span>

8.  <span data-ttu-id="0fb49-113">Wiederholen Sie die vorherigen Schritte für andere Bundesländer.</span><span class="sxs-lookup"><span data-stu-id="0fb49-113">Repeat the previous steps for other states.</span></span>

    |<span data-ttu-id="0fb49-114">Code</span><span class="sxs-lookup"><span data-stu-id="0fb49-114">Code</span></span>|<span data-ttu-id="0fb49-115">Name</span><span class="sxs-lookup"><span data-stu-id="0fb49-115">Name</span></span>|
    |----------|----------|
    |<span data-ttu-id="0fb49-116">CA</span><span class="sxs-lookup"><span data-stu-id="0fb49-116">CA</span></span>|<span data-ttu-id="0fb49-117">Kalifornien</span><span class="sxs-lookup"><span data-stu-id="0fb49-117">California</span></span>|
    |<span data-ttu-id="0fb49-118">CO</span><span class="sxs-lookup"><span data-stu-id="0fb49-118">CO</span></span>|<span data-ttu-id="0fb49-119">Colorado</span><span class="sxs-lookup"><span data-stu-id="0fb49-119">Colorado</span></span>|
    |<span data-ttu-id="0fb49-120">BY</span><span class="sxs-lookup"><span data-stu-id="0fb49-120">IL</span></span>|<span data-ttu-id="0fb49-121">Illinois</span><span class="sxs-lookup"><span data-stu-id="0fb49-121">Illinois</span></span>|
    |<span data-ttu-id="0fb49-122">SL</span><span class="sxs-lookup"><span data-stu-id="0fb49-122">DC</span></span>|<span data-ttu-id="0fb49-123">District of Columbia</span><span class="sxs-lookup"><span data-stu-id="0fb49-123">District of Columbia</span></span>|
    |<span data-ttu-id="0fb49-124">FL</span><span class="sxs-lookup"><span data-stu-id="0fb49-124">FL</span></span>|<span data-ttu-id="0fb49-125">Florida</span><span class="sxs-lookup"><span data-stu-id="0fb49-125">Florida</span></span>|
    |<span data-ttu-id="0fb49-126">AL</span><span class="sxs-lookup"><span data-stu-id="0fb49-126">AL</span></span>|<span data-ttu-id="0fb49-127">Alabama</span><span class="sxs-lookup"><span data-stu-id="0fb49-127">Alabama</span></span>|
    |<span data-ttu-id="0fb49-128">HE</span><span class="sxs-lookup"><span data-stu-id="0fb49-128">KY</span></span>|<span data-ttu-id="0fb49-129">Kentucky</span><span class="sxs-lookup"><span data-stu-id="0fb49-129">Kentucky</span></span>|
    |<span data-ttu-id="0fb49-130">NI</span><span class="sxs-lookup"><span data-stu-id="0fb49-130">MA</span></span>|<span data-ttu-id="0fb49-131">Massachusetts</span><span class="sxs-lookup"><span data-stu-id="0fb49-131">Massachusetts</span></span>|
    |<span data-ttu-id="0fb49-132">RP</span><span class="sxs-lookup"><span data-stu-id="0fb49-132">AZ</span></span>|<span data-ttu-id="0fb49-133">Arizona</span><span class="sxs-lookup"><span data-stu-id="0fb49-133">Arizona</span></span>|
    |<span data-ttu-id="0fb49-134">MI</span><span class="sxs-lookup"><span data-stu-id="0fb49-134">MI</span></span>|<span data-ttu-id="0fb49-135">Michigan</span><span class="sxs-lookup"><span data-stu-id="0fb49-135">Michigan</span></span>|
    |<span data-ttu-id="0fb49-136">BB</span><span class="sxs-lookup"><span data-stu-id="0fb49-136">MN</span></span>|<span data-ttu-id="0fb49-137">Minnesota</span><span class="sxs-lookup"><span data-stu-id="0fb49-137">Minnesota</span></span>|
    |<span data-ttu-id="0fb49-138">NJ</span><span class="sxs-lookup"><span data-stu-id="0fb49-138">NJ</span></span>|<span data-ttu-id="0fb49-139">New Jersey</span><span class="sxs-lookup"><span data-stu-id="0fb49-139">New Jersey</span></span>|
    |<span data-ttu-id="0fb49-140">SH</span><span class="sxs-lookup"><span data-stu-id="0fb49-140">NV</span></span>|<span data-ttu-id="0fb49-141">Nevada</span><span class="sxs-lookup"><span data-stu-id="0fb49-141">Nevada</span></span>|
    |<span data-ttu-id="0fb49-142">NY</span><span class="sxs-lookup"><span data-stu-id="0fb49-142">NY</span></span>|<span data-ttu-id="0fb49-143">New York</span><span class="sxs-lookup"><span data-stu-id="0fb49-143">New York</span></span>|
    |<span data-ttu-id="0fb49-144">HH</span><span class="sxs-lookup"><span data-stu-id="0fb49-144">OH</span></span>|<span data-ttu-id="0fb49-145">Ohio</span><span class="sxs-lookup"><span data-stu-id="0fb49-145">Ohio</span></span>|
    |<span data-ttu-id="0fb49-146">OK</span><span class="sxs-lookup"><span data-stu-id="0fb49-146">OK</span></span>|<span data-ttu-id="0fb49-147">Oklahoma</span><span class="sxs-lookup"><span data-stu-id="0fb49-147">Oklahoma</span></span>|
    |<span data-ttu-id="0fb49-148">ODER</span><span class="sxs-lookup"><span data-stu-id="0fb49-148">OR</span></span>|<span data-ttu-id="0fb49-149">Oregon</span><span class="sxs-lookup"><span data-stu-id="0fb49-149">Oregon</span></span>|
    |<span data-ttu-id="0fb49-150">PA</span><span class="sxs-lookup"><span data-stu-id="0fb49-150">PA</span></span>|<span data-ttu-id="0fb49-151">Pennsylvania</span><span class="sxs-lookup"><span data-stu-id="0fb49-151">Pennsylvania</span></span>|
    |<span data-ttu-id="0fb49-152">SC</span><span class="sxs-lookup"><span data-stu-id="0fb49-152">SC</span></span>|<span data-ttu-id="0fb49-153">South Carolina</span><span class="sxs-lookup"><span data-stu-id="0fb49-153">South Carolina</span></span>|
    |<span data-ttu-id="0fb49-154">KS</span><span class="sxs-lookup"><span data-stu-id="0fb49-154">KS</span></span>|<span data-ttu-id="0fb49-155">Kansas</span><span class="sxs-lookup"><span data-stu-id="0fb49-155">Kansas</span></span>|
    |<span data-ttu-id="0fb49-156">TN</span><span class="sxs-lookup"><span data-stu-id="0fb49-156">TN</span></span>|<span data-ttu-id="0fb49-157">Tennessee</span><span class="sxs-lookup"><span data-stu-id="0fb49-157">Tennessee</span></span>|
    |<span data-ttu-id="0fb49-158">TX</span><span class="sxs-lookup"><span data-stu-id="0fb49-158">TX</span></span>|<span data-ttu-id="0fb49-159">Texas</span><span class="sxs-lookup"><span data-stu-id="0fb49-159">Texas</span></span>|
    |<span data-ttu-id="0fb49-160">UT</span><span class="sxs-lookup"><span data-stu-id="0fb49-160">UT</span></span>|<span data-ttu-id="0fb49-161">Utah</span><span class="sxs-lookup"><span data-stu-id="0fb49-161">Utah</span></span>|
    |<span data-ttu-id="0fb49-162">VA</span><span class="sxs-lookup"><span data-stu-id="0fb49-162">VA</span></span>|<span data-ttu-id="0fb49-163">Virginia</span><span class="sxs-lookup"><span data-stu-id="0fb49-163">Virginia</span></span>|
    |<span data-ttu-id="0fb49-164">WA</span><span class="sxs-lookup"><span data-stu-id="0fb49-164">WA</span></span>|<span data-ttu-id="0fb49-165">Washington</span><span class="sxs-lookup"><span data-stu-id="0fb49-165">Washington</span></span>|
    |<span data-ttu-id="0fb49-166">WI</span><span class="sxs-lookup"><span data-stu-id="0fb49-166">WI</span></span>|<span data-ttu-id="0fb49-167">Wisconsin</span><span class="sxs-lookup"><span data-stu-id="0fb49-167">Wisconsin</span></span>|
    |<span data-ttu-id="0fb49-168">HI</span><span class="sxs-lookup"><span data-stu-id="0fb49-168">HI</span></span>|<span data-ttu-id="0fb49-169">Hawaii</span><span class="sxs-lookup"><span data-stu-id="0fb49-169">Hawaii</span></span>|
    |<span data-ttu-id="0fb49-170">MD</span><span class="sxs-lookup"><span data-stu-id="0fb49-170">MD</span></span>|<span data-ttu-id="0fb49-171">Maryland</span><span class="sxs-lookup"><span data-stu-id="0fb49-171">Maryland</span></span>|
    |<span data-ttu-id="0fb49-172">CT</span><span class="sxs-lookup"><span data-stu-id="0fb49-172">CT</span></span>|<span data-ttu-id="0fb49-173">Connecticut</span><span class="sxs-lookup"><span data-stu-id="0fb49-173">Connecticut</span></span>|

9. <span data-ttu-id="0fb49-174">Wählen Sie ein beliebiges Bundesland aus, und klicken Sie auf **Transaktionen anzeigen** in der Symbolleiste.</span><span class="sxs-lookup"><span data-stu-id="0fb49-174">Select any of the state entries and click **View Transactions** from the Toolbar.</span></span> <span data-ttu-id="0fb49-175">Es sollte die Transaktion für das gerade vorgenommene Update in der Liste der Transaktionen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="0fb49-175">You should see the transaction for the update you just made is in the list of transactions.</span></span>

10. <span data-ttu-id="0fb49-176">Bewegen Sie die Maus über das Menü **Entitäten**, und klicken Sie auf **Lieferant**.</span><span class="sxs-lookup"><span data-stu-id="0fb49-176">Hover the mouse over **Entities** menu and click **Supplier**.</span></span>

11. <span data-ttu-id="0fb49-177">Der Wert für das Feld **Bundesland** kann im Bereich **Details** über die Dropdownliste geändert werden.</span><span class="sxs-lookup"><span data-stu-id="0fb49-177">Now, notice that a value for the **State** field can be changed in the **Details** pane by using the drop-down list.</span></span> <span data-ttu-id="0fb49-178">Sie können auch sehen, dass in der Liste links und in der Dropdownliste im Bereich **Details** zuerst Code und dann der Name in geschweiften Klammern angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="0fb49-178">You can also see that, in the list to the left and in the drop-down list in the **Details** pane, code is displayed first and then the name in curly braces.</span></span> <span data-ttu-id="0fb49-179">Sie können auch jeden beliebigen anderen Wert im Bereich **Details** ändern.</span><span class="sxs-lookup"><span data-stu-id="0fb49-179">You can also change any other value in the **Details** pane.</span></span>

     <span data-ttu-id="0fb49-180">![Attribut mit aktualisiertem Code und Namen von Bundesstaaten](../../2014/tutorials/media/et-verifythatthedbaiscreatedusingmdm-02.jpg "Attribut mit aktualisiertem Code und Namen von Bundesstaaten")</span><span class="sxs-lookup"><span data-stu-id="0fb49-180">![State Attribute with Updated Code and Names](../../2014/tutorials/media/et-verifythatthedbaiscreatedusingmdm-02.jpg "State Attribute with Updated Code and Names")</span></span>

## <a name="next-step"></a><span data-ttu-id="0fb49-181">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="0fb49-181">Next Step</span></span>
 [<span data-ttu-id="0fb49-182">Aufgabe 7: Anzeigen von Updates, die mit Master Data Manager in Excel durchgeführt wurden</span><span class="sxs-lookup"><span data-stu-id="0fb49-182">Task 7: Viewing Updates Made using Master Data Manager in Excel</span></span>](../../2014/tutorials/task-7-viewing-updates-made-using-master-data-manager-in-excel.md)


