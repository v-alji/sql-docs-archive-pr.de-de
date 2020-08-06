---
title: Verwenden eines Ausdrucks in einer Rang folgen Einschränkung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- precedence constraints [Integration Services], adding expressions
- expressions [Integration Services], adding
ms.assetid: 601038bb-3b17-42ac-b09d-5b3a82fb6564
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a997efa448a8381cc8251cd4cbf69dc59f8968e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701288"
---
# <a name="use-an-expression-in-a-precedence-constraint"></a><span data-ttu-id="943ac-102">Verwenden eines Ausdrucks in einer Rangfolgeneinschränkung</span><span class="sxs-lookup"><span data-stu-id="943ac-102">Use an Expression in a Precedence Constraint</span></span>
  <span data-ttu-id="943ac-103">In diesem Verfahren wird beschrieben, wie Sie einer Rangfolgeneinschränkung mithilfe des Dialogfelds **Rangfolgeneinschränkungs-Editor** einen Ausdruck hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="943ac-103">This procedure describes how to add an expression to a precedence constraint by using the **Precedence Constraint Editor** dialog box.</span></span> <span data-ttu-id="943ac-104">Wenn Sie einer Rangfolgeneinschränkung einen Ausdruck hinzufügen möchten, muss das Paket mindestens zwei ausführbare Dateien einschließen (Tasks oder Container), die mit einer Rangfolgeneinschränkung verbunden sein müssen.</span><span class="sxs-lookup"><span data-stu-id="943ac-104">Before you can add an expression to a precedence constraint, the package must include at least two executables, either tasks or containers, and they must be connected by a precedence constraint.</span></span>  
  
### <a name="to-add-an-expression-to-a-precedence-constraint"></a><span data-ttu-id="943ac-105">So fügen Sie einer Rangfolgeneinschränkung einen Ausdruck hinzu</span><span class="sxs-lookup"><span data-stu-id="943ac-105">To add an expression to a precedence constraint</span></span>  
  
1.  <span data-ttu-id="943ac-106">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Projekt mit dem gewünschten Paket.</span><span class="sxs-lookup"><span data-stu-id="943ac-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="943ac-107">Doppelklicken Sie im Projektmappen-Explorer auf das Paket, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="943ac-107">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="943ac-108">Klicken Sie auf die Registerkarte **Ablaufsteuerung** .</span><span class="sxs-lookup"><span data-stu-id="943ac-108">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="943ac-109">Doppelklicken Sie auf der Entwurfsoberfläche der Registerkarte **Ablaufsteuerung** auf die Rangfolgeneinschränkung.</span><span class="sxs-lookup"><span data-stu-id="943ac-109">On the design surface of the **Control Flow** tab, double-click the precedence constraint.</span></span> <span data-ttu-id="943ac-110">Das Dialogfeld **Rangfolgeneinschränkungs-Editor** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="943ac-110">The **Precedence Constraint Editor** opens.</span></span>  
  
5.  <span data-ttu-id="943ac-111">Wählen Sie **Ausdruck**, **Ausdruck und Einschränkung**oder **Ausdruck oder Einschränkung** in der Liste **Auswertungsvorgang** aus.</span><span class="sxs-lookup"><span data-stu-id="943ac-111">Select **Expression**, **Expression and Constraint**, or **Expression or Constraint** in the **Evaluation operation** list.</span></span>  
  
6.  <span data-ttu-id="943ac-112">Geben Sie in das Textfeld **Ausdruck** einen Ausdruck ein, oder starten Sie den Ausdrucks-Generator, um einen Ausdruck zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="943ac-112">Type an expression in the **Expression** text box or launch the Expression Builder to create an expression.</span></span>  
  
7.  <span data-ttu-id="943ac-113">Klicken Sie auf **Testen**, um die Ausdruckssyntax zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="943ac-113">To validate the expression syntax, click **Test**.</span></span>  
  
8.  <span data-ttu-id="943ac-114">Klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern** , um das aktualisierte Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="943ac-114">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="943ac-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="943ac-115">See Also</span></span>  
 <span data-ttu-id="943ac-116">[Rang folgen Einschränkungen](control-flow/precedence-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="943ac-116">[Precedence Constraints](control-flow/precedence-constraints.md) </span></span>  
 <span data-ttu-id="943ac-117">[Verbinden von Tasks und Containern mithilfe einer Standard Rang folgen Einschränkung](../../2014/integration-services/connect-tasks-and-containers-by-using-a-default-precedence-constraint.md) </span><span class="sxs-lookup"><span data-stu-id="943ac-117">[Connect Tasks and Containers by Using a Default Precedence Constraint](../../2014/integration-services/connect-tasks-and-containers-by-using-a-default-precedence-constraint.md) </span></span>  
 <span data-ttu-id="943ac-118">[Festlegen des Werts einer Rang folgen Einschränkung mithilfe des Kontextmenüs](../../2014/integration-services/set-the-value-of-a-precedence-constraint-by-using-the-shortcut-menu.md) </span><span class="sxs-lookup"><span data-stu-id="943ac-118">[Set the Value of a Precedence Constraint by Using the Shortcut Menu](../../2014/integration-services/set-the-value-of-a-precedence-constraint-by-using-the-shortcut-menu.md) </span></span>  
 <span data-ttu-id="943ac-119">[Festlegen der Eigenschaften einer Rang folgen Einschränkung](../../2014/integration-services/set-the-properties-of-a-precedence-constraint.md) </span><span class="sxs-lookup"><span data-stu-id="943ac-119">[Set the Properties of a Precedence Constraint](../../2014/integration-services/set-the-properties-of-a-precedence-constraint.md) </span></span>  
 [<span data-ttu-id="943ac-120">Integration Services-Ausdrücke &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="943ac-120">Integration Services &#40;SSIS&#41; Expressions</span></span>](expressions/integration-services-ssis-expressions.md)  
  
  
