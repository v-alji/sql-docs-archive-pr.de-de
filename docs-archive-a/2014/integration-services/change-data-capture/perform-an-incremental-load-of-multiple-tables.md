---
title: Ausführen eines inkrementellen Ladens von mehreren Tabellen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- incremental load [Integration Services],multiple tables
ms.assetid: 39252dd5-09c3-46f9-a17b-15208cfd336d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e4bf81d1d529e8102271c66839440ef712219600
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610017"
---
# <a name="perform-an-incremental-load-of-multiple-tables"></a><span data-ttu-id="ac1c8-102">Ausführen eines inkrementellen Ladens von mehreren Tabellen</span><span class="sxs-lookup"><span data-stu-id="ac1c8-102">Perform an Incremental Load of Multiple Tables</span></span>
  <span data-ttu-id="ac1c8-103">Im Thema [Verbessern des inkrementellen Ladens mit Change Data Capture](change-data-capture-ssis.md)veranschaulicht das Diagramm ein einfaches Paket, das ein inkrementelles Laden in nur einer Tabelle ausführt.</span><span class="sxs-lookup"><span data-stu-id="ac1c8-103">In the topic, [Improving Incremental Loads with Change Data Capture](change-data-capture-ssis.md), the diagram illustrates a basic package that performs an incremental load on just one table.</span></span> <span data-ttu-id="ac1c8-104">Das Laden einer Tabelle ist jedoch nicht so üblich wie das Ausführen eines inkrementellen Ladens von mehreren Tabellen.</span><span class="sxs-lookup"><span data-stu-id="ac1c8-104">However, loading one table is not as common as having to perform an incremental load of multiple tables.</span></span>  
  
 <span data-ttu-id="ac1c8-105">Wenn Sie ein inkrementelles Laden von mehreren Tabellen ausführen, müssen einige Schritte einmal für alle Tabellen ausgeführt werden, und andere Schritte müssen für jede Quelltabelle wiederholt werden.</span><span class="sxs-lookup"><span data-stu-id="ac1c8-105">When you perform an incremental load of multiple tables, some steps have to be performed once for all the tables, and other steps have to be repeated for each source table.</span></span> <span data-ttu-id="ac1c8-106">Sie haben mehr als eine Option zum Implementieren dieser Schritte in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="ac1c8-106">You have more than one option for implementing these steps in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="ac1c8-107">Verwenden Sie ein übergeordnetes Paket und untergeordnete Pakete.</span><span class="sxs-lookup"><span data-stu-id="ac1c8-107">Use a parent package and child packages.</span></span>  
  
-   <span data-ttu-id="ac1c8-108">Verwenden Sie mehrere Datenflusstasks in einem einzelnen Paket.</span><span class="sxs-lookup"><span data-stu-id="ac1c8-108">Use multiple Data Flow tasks in a single package.</span></span>  
  
## <a name="loading-multiple-tables-by-using-a-parent-package-and-multiple-child-packages"></a><span data-ttu-id="ac1c8-109">Laden von mehreren Tabellen mit einem übergeordneten Paket und mehreren untergeordneten Paketen</span><span class="sxs-lookup"><span data-stu-id="ac1c8-109">Loading Multiple Tables by Using a Parent Package and Multiple Child Packages</span></span>  
 <span data-ttu-id="ac1c8-110">Sie können ein übergeordnetes Paket verwenden, um jene Schritte auszuführen, die nur einmal gemacht werden müssen.</span><span class="sxs-lookup"><span data-stu-id="ac1c8-110">You can use a parent package to perform those steps that only have to be done once.</span></span> <span data-ttu-id="ac1c8-111">Die untergeordneten Pakete führen jene Schritte aus, die für jede Quelltabelle gemacht werden müssen.</span><span class="sxs-lookup"><span data-stu-id="ac1c8-111">The child packages will perform those steps that have to be done for each source table.</span></span>  
  
#### <a name="to-create-a-parent-package-that-performs-those-steps-that-only-have-to-be-done-once"></a><span data-ttu-id="ac1c8-112">So erstellen Sie ein übergeordnetes Paket, das jene Schritte ausführt, die nur einmal gemacht werden müssen</span><span class="sxs-lookup"><span data-stu-id="ac1c8-112">To create a parent package that performs those steps that only have to be done once</span></span>  
  
1.  <span data-ttu-id="ac1c8-113">Erstellen eines übergeordneten Pakets.</span><span class="sxs-lookup"><span data-stu-id="ac1c8-113">Create a parent package.</span></span>  
  
2.  <span data-ttu-id="ac1c8-114">Verwenden Sie in der Ablaufsteuerung einen Task "SQL ausführen" oder [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Ausdrücke, um die Endpunkte zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="ac1c8-114">In the control flow, use an Execute SQL task or [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expressions to calculate the endpoints.</span></span>  
  
     <span data-ttu-id="ac1c8-115">Ein Beispiel zur Berechnung von Endpunkten finden Sie unter [Angeben eines Intervalls von Änderungsdaten](specify-an-interval-of-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="ac1c8-115">For an example of how to calculate endpoints, see [Specify an Interval of Change Data](specify-an-interval-of-change-data.md).</span></span>  
  
3.  <span data-ttu-id="ac1c8-116">Verwenden Sie bei Bedarf einen For-Schleifencontainer, um die Ausführung so lange zu verzögern, bis die Änderungsdaten für den ausgewählten Zeitraum bereit sind.</span><span class="sxs-lookup"><span data-stu-id="ac1c8-116">If needed, use a For Loop container to delay execution until change data for the selected period is ready.</span></span>  
  
     <span data-ttu-id="ac1c8-117">Ein Beispiel eines solchen For-Schleifencontainers finden Sie unter [Bestimmen, ob die Änderungsdaten bereit sind](determine-whether-the-change-data-is-ready.md).</span><span class="sxs-lookup"><span data-stu-id="ac1c8-117">For an example of such a For Loop container, see [Determine Whether the Change Data Is Ready](determine-whether-the-change-data-is-ready.md).</span></span>  
  
4.  <span data-ttu-id="ac1c8-118">Verwenden Sie mehrere Tasks "Paket ausführen", um untergeordnete Pakete für jede zu ladende Tabelle auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ac1c8-118">Use multiple Execute Package tasks to execute child packages for each table to be loaded.</span></span> <span data-ttu-id="ac1c8-119">Übergeben Sie die im übergeordneten Paket berechneten Endpunkte an jedes untergeordnete Paket, indem Sie die Variablenkonfiguration für übergeordnete Pakete verwenden.</span><span class="sxs-lookup"><span data-stu-id="ac1c8-119">Pass the endpoints calculated in the parent package to each child package by using Parent Package Variable configurations.</span></span>  
  
     <span data-ttu-id="ac1c8-120">Weitere Informationen finden Sie unter [Paket ausführen (Task)](../control-flow/execute-package-task.md) und [Verwenden der Werte von Variablen und Parametern in einem untergeordneten Paket](../use-the-values-of-variables-and-parameters-in-a-child-package.md).</span><span class="sxs-lookup"><span data-stu-id="ac1c8-120">For more information, see [Execute Package Task](../control-flow/execute-package-task.md) and [Use the Values of Variables and Parameters in a Child Package](../use-the-values-of-variables-and-parameters-in-a-child-package.md).</span></span>  
  
#### <a name="to-create-child-packages-to-perform-those-steps-that-have-to-be-done-for-each-source-table"></a><span data-ttu-id="ac1c8-121">So erstellen Sie untergeordnete Pakete, um jene Schritte auszuführen, die für jede Quelltabelle gemacht werden müssen</span><span class="sxs-lookup"><span data-stu-id="ac1c8-121">To create child packages to perform those steps that have to be done for each source table</span></span>  
  
1.  <span data-ttu-id="ac1c8-122">Erstellen Sie für jede Quelltabelle ein untergeordnetes Paket.</span><span class="sxs-lookup"><span data-stu-id="ac1c8-122">For each source table, create a child package.</span></span>  
  
2.  <span data-ttu-id="ac1c8-123">Verwenden Sie in der Ablaufsteuerung einen Skripttask oder einen Task "SQL ausführen", um die SQL-Anweisung zusammenzustellen, mit der Änderungen abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="ac1c8-123">In the control flow, use a Script task or an Execute SQL task to assemble the SQL statement that will be used to query for changes.</span></span>  
  
     <span data-ttu-id="ac1c8-124">Ein Beispiel zum Zusammenstellen der Abfrage finden Sie unter [Vorbereiten zur Abfrage der Änderungsdaten](prepare-to-query-for-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="ac1c8-124">For an example of how to assemble the query, see [Prepare to Query for the Change Data](prepare-to-query-for-the-change-data.md).</span></span>  
  
3.  <span data-ttu-id="ac1c8-125">Verwenden Sie in jedem untergeordneten Paket einen einzelnen Datenflusstask, um die Änderungsdaten zu laden und diese auf das Ziel anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="ac1c8-125">Use a single Data Flow task in each child package to load the change data and apply it to the destination.</span></span> <span data-ttu-id="ac1c8-126">Konfigurieren Sie den Datenfluss, wie in den folgenden Stufen beschrieben:</span><span class="sxs-lookup"><span data-stu-id="ac1c8-126">Configure the Data Flow as described in the following steps:</span></span>  
  
    1.  <span data-ttu-id="ac1c8-127">Verwenden Sie im Datenfluss eine Quellkomponente, um die Änderungstabellen nach den Änderungen abzufragen, die innerhalb der ausgewählten Endpunkte liegen.</span><span class="sxs-lookup"><span data-stu-id="ac1c8-127">In the data flow, use a source component to query the change tables for the changes that fall within the selected endpoints.</span></span>  
  
         <span data-ttu-id="ac1c8-128">Ein Beispiel zur Abfrage der Änderungstabellen finden Sie unter [Abrufen und Verstehen der Änderungsdaten](retrieve-and-understand-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="ac1c8-128">For an example of how to query the change tables, see [Retrieve and Understand the Change Data](retrieve-and-understand-the-change-data.md).</span></span>  
  
    2.  <span data-ttu-id="ac1c8-129">Verwenden Sie eine Transformation für bedingtes Teilen, um Einfügungen, Updates und Löschungen an andere Ausgaben zur entsprechenden Verarbeitung weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="ac1c8-129">Use a Conditional Split transformation to direct inserts, updates, and deletes to different outputs for appropriate processing.</span></span>  
  
         <span data-ttu-id="ac1c8-130">Ein Beispiel für die Konfiguration dieser Transformation zur Weiterleitung einer Ausgabe finden Sie unter [Verarbeiten von Einfügungen, Updates und Löschungen](process-inserts-updates-and-deletes.md).</span><span class="sxs-lookup"><span data-stu-id="ac1c8-130">For an example of how to configure this transformation to direct output, see [Process Inserts, Updates, and Deletes](process-inserts-updates-and-deletes.md).</span></span>  
  
    3.  <span data-ttu-id="ac1c8-131">Verwenden Sie eine Zielkomponente, um die Einfügungen auf das Ziel anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="ac1c8-131">Use a destination component to apply the inserts to the destination.</span></span> <span data-ttu-id="ac1c8-132">Verwenden Sie Transformationen für OLE DB-Befehl mit parametrisierten UPDATE- und DELETE-Anweisungen, um Updates und Löschungen auf das Ziel anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="ac1c8-132">Use OLE DB Command transformations with parameterized UPDATE and DELETE statements to apply updates and deletes to the destination.</span></span>  
  
         <span data-ttu-id="ac1c8-133">Ein Beispiel für die Verwendung dieser Transformation zur Anwendung von Updates und Löschungen finden Sie unter [Anwenden der Änderungen auf das Ziel](apply-the-changes-to-the-destination.md).</span><span class="sxs-lookup"><span data-stu-id="ac1c8-133">For an example of how to use this transformation to apply updates and deletes, see [Apply the Changes to the Destination](apply-the-changes-to-the-destination.md).</span></span>  
  
## <a name="loading-multiple-tables-by-using-multiple-data-flow-tasks-in-a-single-package"></a><span data-ttu-id="ac1c8-134">Laden von mehreren Tabellen mit mehreren Datenflusstasks in einem einzelnen Paket</span><span class="sxs-lookup"><span data-stu-id="ac1c8-134">Loading Multiple Tables by Using Multiple Data Flow Tasks in a Single Package</span></span>  
 <span data-ttu-id="ac1c8-135">Alternativ können Sie ein einzelnes Paket verwenden, das für jede zu ladende Quelltabelle einen separaten Datenflusstask enthält.</span><span class="sxs-lookup"><span data-stu-id="ac1c8-135">Alternatively, you can use a single package that contains a separate Data Flow task for each source table to be loaded.</span></span>  
  
#### <a name="to-load-multiple-tables-by-using-multiple-data-flow-tasks-in-a-single-package"></a><span data-ttu-id="ac1c8-136">So laden Sie mehrere Tabellen mit mehreren Datenflusstasks in einem einzelnen Paket</span><span class="sxs-lookup"><span data-stu-id="ac1c8-136">To load multiple tables by using multiple Data Flow tasks in a single package</span></span>  
  
1.  <span data-ttu-id="ac1c8-137">Erstellen eines einzelnen Pakets.</span><span class="sxs-lookup"><span data-stu-id="ac1c8-137">Create a single package.</span></span>  
  
2.  <span data-ttu-id="ac1c8-138">Verwenden Sie in der Ablaufsteuerung einen Task "SQL ausführen" oder [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Ausdrücke, um die Endpunkte zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="ac1c8-138">In the control flow, use an Execute SQL Task or [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expressions to calculate the endpoints.</span></span>  
  
     <span data-ttu-id="ac1c8-139">Ein Beispiel zur Berechnung von Endpunkten finden Sie unter [Angeben eines Intervalls von Änderungsdaten](specify-an-interval-of-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="ac1c8-139">For an example of how to calculate endpoints, see [Specify an Interval of Change Data](specify-an-interval-of-change-data.md).</span></span>  
  
3.  <span data-ttu-id="ac1c8-140">Verwenden Sie bei Bedarf einen For-Schleifencontainer, um die Ausführung so lange zu verzögern, bis die Änderungsdaten für das ausgewählte Intervall bereit sind.</span><span class="sxs-lookup"><span data-stu-id="ac1c8-140">If needed, use a For Loop container to delay execution until the change data for the selected interval is ready.</span></span>  
  
     <span data-ttu-id="ac1c8-141">Ein Beispiel eines solchen For-Schleifencontainers finden Sie unter [Bestimmen, ob die Änderungsdaten bereit sind](determine-whether-the-change-data-is-ready.md).</span><span class="sxs-lookup"><span data-stu-id="ac1c8-141">For an example of such a For Loop container, see [Determine Whether the Change Data Is Ready](determine-whether-the-change-data-is-ready.md).</span></span>  
  
4.  <span data-ttu-id="ac1c8-142">Verwenden Sie einen Skripttask oder einen Task "SQL ausführen", um die SQL-Anweisung zusammenzustellen, mit der Änderungen abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="ac1c8-142">Use a Script task or an Execute SQL task to assemble the SQL statement that will be used to query for changes.</span></span>  
  
     <span data-ttu-id="ac1c8-143">Ein Beispiel zum Zusammenstellen der Abfrage finden Sie unter [Vorbereiten zur Abfrage der Änderungsdaten](prepare-to-query-for-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="ac1c8-143">For an example of how to assemble the query, see [Prepare to Query for the Change Data](prepare-to-query-for-the-change-data.md).</span></span>  
  
5.  <span data-ttu-id="ac1c8-144">Verwenden Sie mehrere Datenflusstasks, um die Änderungsdaten von jeder Quelltabelle zu laden und diese auf das Ziel anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="ac1c8-144">Use multiple Data Flow tasks to load the change data from each source table and apply it to the destination.</span></span> <span data-ttu-id="ac1c8-145">Konfigurieren Sie jeden Datenflusstask, wie in den folgenden Schritten beschrieben:</span><span class="sxs-lookup"><span data-stu-id="ac1c8-145">Configure each Data Flow task as described in the following steps.</span></span>  
  
    1.  <span data-ttu-id="ac1c8-146">Verwenden Sie in jedem Datenfluss eine Quellkomponente, um die Änderungstabellen nach den Änderungen abzufragen, die innerhalb der ausgewählten Endpunkte liegen.</span><span class="sxs-lookup"><span data-stu-id="ac1c8-146">In each data flow, use a source component to query the change tables for the changes that fall within the selected endpoints.</span></span>  
  
         <span data-ttu-id="ac1c8-147">Ein Beispiel zur Abfrage der Änderungstabellen finden Sie unter [Abrufen und Verstehen der Änderungsdaten](retrieve-and-understand-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="ac1c8-147">For an example of how to query the change tables, see [Retrieve and Understand the Change Data](retrieve-and-understand-the-change-data.md).</span></span>  
  
    2.  <span data-ttu-id="ac1c8-148">Verwenden Sie eine Transformation für bedingtes Teilen, um Einfügungen, Updates und Löschungen an andere Ausgaben zur entsprechenden Verarbeitung weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="ac1c8-148">Use a Conditional Split transformation to direct inserts, updates, and deletes to different outputs for appropriate processing.</span></span>  
  
         <span data-ttu-id="ac1c8-149">Ein Beispiel für die Konfiguration dieser Transformation zur Weiterleitung einer Ausgabe finden Sie unter [Verarbeiten von Einfügungen, Updates und Löschungen](process-inserts-updates-and-deletes.md).</span><span class="sxs-lookup"><span data-stu-id="ac1c8-149">For an example of how to configure this transformation to direct output, see [Process Inserts, Updates, and Deletes](process-inserts-updates-and-deletes.md).</span></span>  
  
    3.  <span data-ttu-id="ac1c8-150">Verwenden Sie eine Zielkomponente, um die Einfügungen auf das Ziel anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="ac1c8-150">Use a destination component to apply the inserts to the destination.</span></span> <span data-ttu-id="ac1c8-151">Verwenden Sie Transformationen für OLE DB-Befehl mit parametrisierten UPDATE- und DELETE-Anweisungen, um Updates und Löschungen auf das Ziel anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="ac1c8-151">Use OLE DB Command transformations with parameterized UPDATE and DELETE statements to apply updates and deletes to the destination.</span></span>  
  
         <span data-ttu-id="ac1c8-152">Ein Beispiel für die Verwendung dieser Transformation zur Anwendung von Updates und Löschungen finden Sie unter [Anwenden der Änderungen auf das Ziel](apply-the-changes-to-the-destination.md).</span><span class="sxs-lookup"><span data-stu-id="ac1c8-152">For an example of how to use this transformation to apply updates and deletes, see [Apply the Changes to the Destination](apply-the-changes-to-the-destination.md).</span></span>  
  
  
