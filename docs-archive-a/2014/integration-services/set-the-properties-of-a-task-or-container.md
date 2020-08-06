---
title: Festlegen der Eigenschaften eines Tasks oder Containers | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- tasks [Integration Services], properties
ms.assetid: 52d47ca4-fb8c-493d-8b2b-48bb269f859b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0a4c556b94af02c2f874f2740a70b1294c35e653
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726053"
---
# <a name="set-the-properties-of-a-task-or-container"></a><span data-ttu-id="4659e-102">Festlegen der Eigenschaften eines Tasks oder Containers</span><span class="sxs-lookup"><span data-stu-id="4659e-102">Set the Properties of a Task or Container</span></span>
  <span data-ttu-id="4659e-103">Sie können die meisten Eigenschaften von Tasks und Containern im Fenster **Eigenschaften** festlegen.</span><span class="sxs-lookup"><span data-stu-id="4659e-103">You can set most properties of tasks and containers by using the **Properties** window.</span></span> <span data-ttu-id="4659e-104">Eine Ausnahme sind Eigenschaften von Taskauflistungen und Eigenschaften, die zu komplex sind, als dass sie im Fenster **Eigenschaften** festgelegt werden könnten.</span><span class="sxs-lookup"><span data-stu-id="4659e-104">The exceptions are properties of task collections and properties that are too complex to set by using the **Properties** window.</span></span> <span data-ttu-id="4659e-105">Beispielsweise können Sie nicht den Enumerator konfigurieren, der vom Foreach-Schleifencontainer im Fenster **Eigenschaften** verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4659e-105">For example, you cannot configure the enumerator that the Foreach Loop container uses in the **Properties** window.</span></span> <span data-ttu-id="4659e-106">Sie müssen einen Task- oder Container-Editor verwenden, um diese komplexen Eigenschaften festzulegen.</span><span class="sxs-lookup"><span data-stu-id="4659e-106">You must use a task or container editor to set these complex properties.</span></span> <span data-ttu-id="4659e-107">Die meisten Task- und Container-Editoren weisen mehrere Knoten auf, und jeder Knoten enthält zugehörige Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="4659e-107">Most task and container editors have multiple nodes and each node contains related properties.</span></span> <span data-ttu-id="4659e-108">Der Name des Knotens weist auf die Art der Eigenschaften hin, die der Knoten enthält.</span><span class="sxs-lookup"><span data-stu-id="4659e-108">The name of the node indicates the subject of the properties that the node contains.</span></span>  
  
 <span data-ttu-id="4659e-109">Im Folgenden wird beschrieben, wie die Eigenschaften eines Tasks oder Containers entweder mit dem Fenster **Eigenschaften** oder dem entsprechenden Task- oder Container-Editor festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="4659e-109">The following procedures describe how to set the properties of a task or container by using either the **Properties** windows, or the corresponding task or container editor.</span></span>  
  
### <a name="to-set-the-properties-of-a-task-or-container-by-using-the-properties-window"></a><span data-ttu-id="4659e-110">So legen Sie die Eigenschaften eines Tasks oder Containers mithilfe des Eigenschaftenfensters fest</span><span class="sxs-lookup"><span data-stu-id="4659e-110">To set the properties of a task or container by using the Properties window</span></span>  
  
1.  <span data-ttu-id="4659e-111">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Projekt mit dem gewünschten Paket.</span><span class="sxs-lookup"><span data-stu-id="4659e-111">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="4659e-112">Doppelklicken Sie im Projektmappen-Explorer auf das Paket, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="4659e-112">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="4659e-113">Klicken Sie auf die Registerkarte **Ablaufsteuerung** .</span><span class="sxs-lookup"><span data-stu-id="4659e-113">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="4659e-114">Klicken Sie in der Entwurfsoberfläche der Registerkarte **Ablaufsteuerung** mit der rechten Maustaste auf den Task oder Container, und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="4659e-114">On the design surface of the **Control Flow** tab, right-click the task or container, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="4659e-115">Aktualisieren Sie im Fenster **Eigenschaften** den Eigenschaftswert.</span><span class="sxs-lookup"><span data-stu-id="4659e-115">In the **Properties** window, update the property value.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4659e-116">Die meisten Eigenschaften können durch direktes Eingeben der gewünschten Werte in die jeweiligen Textfelder bzw. Auswählen der Werte aus einer Liste festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="4659e-116">Most properties can be set by typing a value directly in the text box, or by selecting a value from a list.</span></span> <span data-ttu-id="4659e-117">Einige Eigenschaften sind jedoch komplexer und verfügen über einen Editor für benutzerdefinierte Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="4659e-117">However, some properties are more complex and have a custom property editor.</span></span> <span data-ttu-id="4659e-118">Klicken Sie zum Festlegen der Eigenschaft in das Textfeld und anschließend auf die Schaltfläche zum Erstellen **(...)**. Der benutzerdefinierte Editor wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="4659e-118">To set the property, click in the text box, and then click the build **(...)** button to open the custom editor.</span></span>  
  
6.  <span data-ttu-id="4659e-119">Erstellen Sie optional Eigenschaftsausdrücke, um die Eigenschaften des Tasks oder Containers dynamisch zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="4659e-119">Optionally, create property expressions to dynamically update the properties of the task or container.</span></span> <span data-ttu-id="4659e-120">Weitere Informationen finden Sie unter [Hinzufügen oder Ändern eines Eigenschaftsausdrucks](expressions/add-or-change-a-property-expression.md).</span><span class="sxs-lookup"><span data-stu-id="4659e-120">For more information, see [Add or Change a Property Expression](expressions/add-or-change-a-property-expression.md).</span></span>  
  
7.  <span data-ttu-id="4659e-121">Klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern** , um das aktualisierte Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="4659e-121">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-set-the-properties-of-a-task-or-container-by-using-a-task-or-container-editor"></a><span data-ttu-id="4659e-122">So legen Sie die Eigenschaften eines Tasks oder Containers mithilfe eines Task- oder Container-Editors fest</span><span class="sxs-lookup"><span data-stu-id="4659e-122">To set the properties of a task or container by using a task or container editor</span></span>  
  
1.  <span data-ttu-id="4659e-123">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Projekt mit dem gewünschten Paket.</span><span class="sxs-lookup"><span data-stu-id="4659e-123">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="4659e-124">Doppelklicken Sie im Projektmappen-Explorer auf das Paket, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="4659e-124">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="4659e-125">Klicken Sie auf die Registerkarte **Ablaufsteuerung** .</span><span class="sxs-lookup"><span data-stu-id="4659e-125">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="4659e-126">Klicken Sie auf der Entwurfsoberfläche der Registerkarte **Ablaufsteuerung** mit der rechten Maustaste auf den Task oder Container, und klicken Sie auf **Bearbeiten** , um den entsprechenden Task- bzw. Container-Editor zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="4659e-126">On the design surface of the **Control Flow** tab, right-click the task or container, and then click **Edit** to open the corresponding task or container editor.</span></span>  
  
     <span data-ttu-id="4659e-127">Informationen zum Konfigurieren eines For-Schleifencontainers finden Sie unter [Konfigurieren eines For-Schleifencontainers](control-flow/for-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="4659e-127">For information about how to configure the For Loop container, see [Configure a For Loop Container](control-flow/for-loop-container.md).</span></span>  
  
     <span data-ttu-id="4659e-128">Weitere Informationen zum Konfigurieren des Foreach-Schleifen Containers finden Sie unter [Konfigurieren eines Foreach-Schleifen Containers](control-flow/foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="4659e-128">For information about how to configure the Foreach Loop container, see [Configure a Foreach Loop Container](control-flow/foreach-loop-container.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4659e-129">Der Sequenzcontainer weist keinen benutzerdefinierten Editor auf.</span><span class="sxs-lookup"><span data-stu-id="4659e-129">The Sequence container has no custom editor.</span></span>  
  
5.  <span data-ttu-id="4659e-130">Falls der Task- oder Container-Editor mehrere Knoten aufweist, klicken Sie auf den Knoten mit der Eigenschaft, die Sie festlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="4659e-130">If the task or container editor has multiple nodes, click the node that contains the property that you want to set.</span></span>  
  
6.  <span data-ttu-id="4659e-131">Klicken Sie optional auf **Ausdrücke** , und erstellen Sie auf der Seite **Ausdrücke** Eigenschaftsausdrücke, um die Eigenschaften des Tasks oder Containers dynamisch zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="4659e-131">Optionally, click **Expressions** and, on the **Expressions** page, create property expressions to dynamically update the properties of the task or container.</span></span> <span data-ttu-id="4659e-132">Weitere Informationen finden Sie unter [Hinzufügen oder Ändern eines Eigenschaftsausdrucks](expressions/add-or-change-a-property-expression.md).</span><span class="sxs-lookup"><span data-stu-id="4659e-132">For more information, see [Add or Change a Property Expression](expressions/add-or-change-a-property-expression.md).</span></span>  
  
7.  <span data-ttu-id="4659e-133">Aktualisieren Sie den Eigenschaftswert.</span><span class="sxs-lookup"><span data-stu-id="4659e-133">Update the property value.</span></span>  
  
8.  <span data-ttu-id="4659e-134">Klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern** , um das aktualisierte Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="4659e-134">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4659e-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4659e-135">See Also</span></span>  
 <span data-ttu-id="4659e-136">[Integration Services-Tasks](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="4659e-136">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="4659e-137">SQL Server Integration Services-Container</span><span class="sxs-lookup"><span data-stu-id="4659e-137">Integration Services Containers</span></span>](control-flow/integration-services-containers.md)  
  
  
