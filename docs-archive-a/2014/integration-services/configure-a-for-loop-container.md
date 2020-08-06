---
title: Konfigurieren eines for-Schleifen Containers | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- containers [Integration Services], For Loop
- For Loop containers
ms.assetid: b9cd7ea7-b198-4a35-8b16-6acf09611ca5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9cb33ea5b7f3f59baad3c94f6bc845c281613ec9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609371"
---
# <a name="configure-a-for-loop-container"></a><span data-ttu-id="86f63-102">Konfigurieren eines For-Schleifencontainers</span><span class="sxs-lookup"><span data-stu-id="86f63-102">Configure a For Loop Container</span></span>
  <span data-ttu-id="86f63-103">In diesem Verfahren wird beschrieben, wie Sie einen For-Schleifencontainer mithilfe des Dialogfelds **For-Schleifen-Editor** konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="86f63-103">This procedure describes how to configure a For Loop container by using the **For Loop Editor** dialog box.</span></span>  
  
### <a name="to-configure-the-for-loop-container"></a><span data-ttu-id="86f63-104">So konfigurieren Sie den For-Schleifencontainer</span><span class="sxs-lookup"><span data-stu-id="86f63-104">To configure the For Loop container</span></span>  
  
1.  <span data-ttu-id="86f63-105">Doppelklicken Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]auf den For-Schleifencontainer, um den **For-Schleifen-Editor**zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="86f63-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], double-click the For Loop container to open the **For Loop Editor**.</span></span>  
  
2.  <span data-ttu-id="86f63-106">Ändern Sie optional den Namen und die Beschreibung des For-Schleifencontainers.</span><span class="sxs-lookup"><span data-stu-id="86f63-106">Optionally, modify the name and description of the For Loop container.</span></span>  
  
3.  <span data-ttu-id="86f63-107">Geben Sie optional einen Initialisierungsausdruck in das Textfeld **InitExpression** ein.</span><span class="sxs-lookup"><span data-stu-id="86f63-107">Optionally, type an initialization expression in the **InitExpression** text box.</span></span>  
  
4.  <span data-ttu-id="86f63-108">Geben Sie einen Auswertungsausdruck in das Textfeld **EvalExpression** ein.</span><span class="sxs-lookup"><span data-stu-id="86f63-108">Type an evaluation expression in the **EvalExpression** text box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="86f63-109">Der Ausdruck muss zu einem booleschen Wert ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="86f63-109">The expression must evaluate to a Boolean.</span></span> <span data-ttu-id="86f63-110">Wenn der Ausdruck zu `false` ausgewertet wird, wird die Ausführung der Schleife beendet.</span><span class="sxs-lookup"><span data-stu-id="86f63-110">When the expression evaluates to `false`, the loop stops running.</span></span>  
  
5.  <span data-ttu-id="86f63-111">Geben Sie optional einen Zuweisungsausdruck in das Textfeld **AssignExpression** ein.</span><span class="sxs-lookup"><span data-stu-id="86f63-111">Optionally, type an assignment expression in the **AssignExpression** text box.</span></span>  
  
6.  <span data-ttu-id="86f63-112">Klicken Sie optional auf **Ausdrücke** , und erstellen Sie auf der Seite **Ausdrücke** Eigenschaftsausdrücke für die Eigenschaften des For-Schleifencontainers.</span><span class="sxs-lookup"><span data-stu-id="86f63-112">Optionally, click **Expressions** and, on the **Expressions** page, create property expressions for the properties of the For Loop container.</span></span> <span data-ttu-id="86f63-113">Weitere Informationen finden Sie unter [Hinzufügen oder Ändern eines Eigenschaftsausdrucks](expressions/add-or-change-a-property-expression.md).</span><span class="sxs-lookup"><span data-stu-id="86f63-113">For more information, see [Add or Change a Property Expression](expressions/add-or-change-a-property-expression.md).</span></span>  
  
7.  <span data-ttu-id="86f63-114">Klicken Sie auf **OK** , um den **For-Schleifen-Editor**zu schließen.</span><span class="sxs-lookup"><span data-stu-id="86f63-114">Click **OK** to close the **For Loop Editor**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86f63-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="86f63-115">See Also</span></span>  
 <span data-ttu-id="86f63-116">[For-Schleifen Container](control-flow/for-loop-container.md) </span><span class="sxs-lookup"><span data-stu-id="86f63-116">[For Loop Container](control-flow/for-loop-container.md) </span></span>  
 <span data-ttu-id="86f63-117">[Integration Services &#40;SSIS-&#41; Ausdrücke](expressions/integration-services-ssis-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="86f63-117">[Integration Services &#40;SSIS&#41; Expressions](expressions/integration-services-ssis-expressions.md) </span></span>  
 [<span data-ttu-id="86f63-118">Verwenden von Eigenschaftsausdrücken in Paketen</span><span class="sxs-lookup"><span data-stu-id="86f63-118">Use Property Expressions in Packages</span></span>](expressions/use-property-expressions-in-packages.md)  
  
  
