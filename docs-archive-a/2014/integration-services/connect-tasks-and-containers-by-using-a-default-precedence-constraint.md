---
title: Verbinden von Tasks und Containern mithilfe einer Standard Rang folgen Einschränkung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- tasks [Integration Services], precedence constraints
- precedence constraints [Integration Services], connecting tasks
- default precedence constraints
- containers [Integration Services], precedence constraints
ms.assetid: 8f31f15f-98ff-4c35-b41f-8b8cfd148d75
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 00207172babdb41b1030e77e71a2c8bc3b99799d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722970"
---
# <a name="connect-tasks-and-containers-by-using-a-default-precedence-constraint"></a><span data-ttu-id="c3886-102">Verbinden von Tasks und Containern mithilfe einer Standardrangfolgeneinschränkung</span><span class="sxs-lookup"><span data-stu-id="c3886-102">Connect Tasks and Containers by Using a Default Precedence Constraint</span></span>
  <span data-ttu-id="c3886-103">Mit Rangfolgeneinschränkungen werden zwei ausführbare Dateien miteinander verbunden.</span><span class="sxs-lookup"><span data-stu-id="c3886-103">Precedence constraints connect two executables.</span></span> <span data-ttu-id="c3886-104">Bei einer ausführbaren Datei kann es sich um einen Task oder einen For-Schleifencontainer, einen Foreach-Schleifencontainer oder einen Sequenzcontainer handeln.</span><span class="sxs-lookup"><span data-stu-id="c3886-104">An executable can be any task or a For Loop, Foreach Loop, or Sequence container.</span></span> <span data-ttu-id="c3886-105">In diesem Verfahren wird beschrieben, wie Sie das Standardverhalten für Rangfolgeneinschränkungen festlegen, und wie Sie ausführbare Dateien mithilfe der Standardrangfolgeneinschränkungen verbinden.</span><span class="sxs-lookup"><span data-stu-id="c3886-105">This procedure describes how to set the default behavior for precedence constraints, and how to connect executables using the default precedence constraints.</span></span>  
  
## <a name="creating-default-precedence-constraints"></a><span data-ttu-id="c3886-106">Erstellen von Standardrangfolgeneinschränkungen</span><span class="sxs-lookup"><span data-stu-id="c3886-106">Creating Default Precedence Constraints</span></span>  
 <span data-ttu-id="c3886-107">Wenn Sie den [!INCLUDE[ssIS](../includes/ssis-md.md)]-Designer zum ersten Mal verwenden, lautet der Standardwert einer Rangfolgeneinschränkung `Success`.</span><span class="sxs-lookup"><span data-stu-id="c3886-107">When you first use [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, the default value of a precedence constraint is `Success`.</span></span> <span data-ttu-id="c3886-108">Führen Sie die folgenden Schritte aus, um für den [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designer einen anderen Standardwert für Rangfolgeneinschränkungen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c3886-108">Follow these steps to configure [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer to use a different default value for precedence constraints.</span></span>  
  
#### <a name="to-set-the-default-value-for-precedence-constraints"></a><span data-ttu-id="c3886-109">So legen Sie den Standardwert für Rangfolgeneinschränkungen fest</span><span class="sxs-lookup"><span data-stu-id="c3886-109">To set the default value for precedence constraints</span></span>  
  
1.  <span data-ttu-id="c3886-110">Öffnen Sie [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c3886-110">Open [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="c3886-111">Klicken Sie im Menü **Extras** auf **Optionen**.</span><span class="sxs-lookup"><span data-stu-id="c3886-111">On the **Tools** menu, click **Options**.</span></span>  
  
3.  <span data-ttu-id="c3886-112">Erweitern Sie im Dialogfeld **Optionen** den Ordner **Business Intelligence-Designer** , und erweitern Sie dann **Integration Services-Designer**.</span><span class="sxs-lookup"><span data-stu-id="c3886-112">In the **Options** dialog box, expand **Business Intelligence Designers,** and then expand **Integration Services Designers**.</span></span>  
  
4.  <span data-ttu-id="c3886-113">Klicken Sie auf **Automatische Ablaufsteuerungsverbindung** , und aktivieren Sie das Kontrollkästchen **Neue Form standardmäßig mit der ausgewählten Form verbinden**.</span><span class="sxs-lookup"><span data-stu-id="c3886-113">Click **Control Flow Auto Connect** and select **Connect a new shape to the selected shape by default**.</span></span>  
  
5.  <span data-ttu-id="c3886-114">Wählen Sie in der Dropdownliste **Failure-Einschränkung für die neue Form verwenden** oder **Completion-Einschränkung für die neue Form verwenden**aus.</span><span class="sxs-lookup"><span data-stu-id="c3886-114">In the drop-down list, choose either **Use a Failure constraint for the new shape** or **Use a Completion constraint for the new shape**.</span></span>  
  
6.  <span data-ttu-id="c3886-115">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c3886-115">Click **OK**.</span></span>  
  
#### <a name="to-create-a-default-precedence-constraint"></a><span data-ttu-id="c3886-116">So erstellen Sie eine Standardrangfolgeneinschränkung</span><span class="sxs-lookup"><span data-stu-id="c3886-116">To create a default precedence constraint</span></span>  
  
1.  <span data-ttu-id="c3886-117">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Projekt mit dem gewünschten Paket.</span><span class="sxs-lookup"><span data-stu-id="c3886-117">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="c3886-118">Doppelklicken Sie im Projektmappen-Explorer auf das Paket, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="c3886-118">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="c3886-119">Klicken Sie auf die Registerkarte **Ablaufsteuerung** .</span><span class="sxs-lookup"><span data-stu-id="c3886-119">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="c3886-120">Klicken Sie in der Entwurfsoberfläche der Registerkarte **Ablaufsteuerung** auf den Task oder Container, und ziehen Sie dessen Konnektor auf die ausführbare Datei, auf die Sie die Rangfolgeneinschränkung anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="c3886-120">On the design surface of the **Control Flow** tab, click the task or container and drag its connector to the executable to which you want the precedence constraint to apply.</span></span>  
  
5.  <span data-ttu-id="c3886-121">Klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern** , um das aktualisierte Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="c3886-121">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3886-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c3886-122">See Also</span></span>  
 <span data-ttu-id="c3886-123">[Rang folgen Einschränkungen](control-flow/precedence-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="c3886-123">[Precedence Constraints](control-flow/precedence-constraints.md) </span></span>  
 <span data-ttu-id="c3886-124">[Festlegen des Werts einer Rang folgen Einschränkung mithilfe des Kontextmenüs](../../2014/integration-services/set-the-value-of-a-precedence-constraint-by-using-the-shortcut-menu.md) </span><span class="sxs-lookup"><span data-stu-id="c3886-124">[Set the Value of a Precedence Constraint by Using the Shortcut Menu](../../2014/integration-services/set-the-value-of-a-precedence-constraint-by-using-the-shortcut-menu.md) </span></span>  
 <span data-ttu-id="c3886-125">[Festlegen der Eigenschaften einer Rang folgen Einschränkung](../../2014/integration-services/set-the-properties-of-a-precedence-constraint.md) </span><span class="sxs-lookup"><span data-stu-id="c3886-125">[Set the Properties of a Precedence Constraint](../../2014/integration-services/set-the-properties-of-a-precedence-constraint.md) </span></span>  
 [<span data-ttu-id="c3886-126">Verwenden eines Ausdrucks in einer Rangfolgeneinschränkung</span><span class="sxs-lookup"><span data-stu-id="c3886-126">Use an Expression in a Precedence Constraint</span></span>](../../2014/integration-services/use-an-expression-in-a-precedence-constraint.md)  
  
  
