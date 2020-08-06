---
title: Rang folgen Einschränkungs-Editor | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.precedenceconstraint.f1
helpviewer_keywords:
- Precedence Constraint Editor dialog box
ms.assetid: b10d4330-6e35-4037-b309-ef56efcd60c5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b6853d1974f4276361d60e1d73b34c72a366a7f4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615425"
---
# <a name="precedence-constraint-editor"></a><span data-ttu-id="0895b-102">Rangfolgeneinschränkungs-Editor</span><span class="sxs-lookup"><span data-stu-id="0895b-102">Precedence Constraint Editor</span></span>
  <span data-ttu-id="0895b-103">Verwenden Sie das Dialogfeld **Rangfolgeneinschränkungs-Editor** , um Rangfolgeneinschränkungen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="0895b-103">Use the **Precedence Constraint Editor** dialog box to configure precedence constraints.</span></span>  
  
## <a name="options"></a><span data-ttu-id="0895b-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="0895b-104">Options</span></span>  
 <span data-ttu-id="0895b-105">**Auswertungsvorgang**</span><span class="sxs-lookup"><span data-stu-id="0895b-105">**Evaluation operation**</span></span>  
 <span data-ttu-id="0895b-106">Geben Sie den Auswertungsvorgang an, den die Rangfolgeneinschränkung verwendet.</span><span class="sxs-lookup"><span data-stu-id="0895b-106">Specify the evaluation operation that the precedence constraint uses.</span></span> <span data-ttu-id="0895b-107">Folgende Vorgänge sind möglich: **Einschränkung**, **Ausdruck**, **Ausdruck und Einschränkung**und **Ausdruck oder Einschränkung**.</span><span class="sxs-lookup"><span data-stu-id="0895b-107">The operations are: **Constraint**, **Expression**, **Expression and Constraint**, and **Expression or Constraint**.</span></span>  
  
 <span data-ttu-id="0895b-108">**Wert**</span><span class="sxs-lookup"><span data-stu-id="0895b-108">**Value**</span></span>  
 <span data-ttu-id="0895b-109">Geben Sie den Einschränkungswert an: **Erfolg**, **Fehler**oder **Beendigung**.</span><span class="sxs-lookup"><span data-stu-id="0895b-109">Specify the constraint value: **Success**, **Failure**, or **Completion**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0895b-110"> Die Rangfolgeneinschränkungslinie wird für **Erfolg**grün, für **Fehler**hervorgehoben und für **Beendigung**blau dargestellt.</span><span class="sxs-lookup"><span data-stu-id="0895b-110">The precedence constraint line is green for **Success**, highlighted for **Failure**, and blue for **Completion**.</span></span>  
  
 <span data-ttu-id="0895b-111">**Ausdruck**</span><span class="sxs-lookup"><span data-stu-id="0895b-111">**Expression**</span></span>  
 <span data-ttu-id="0895b-112">Wenn Sie den Vorgang **Ausdruck**, **Ausdruck und Einschränkung**oder **Ausdruck oder Einschränkung**verwenden, geben Sie einen Ausdruck ein, oder starten Sie den Ausdrucks-Generator, um einen Ausdruck zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0895b-112">If using the operations **Expression**, **Expression and Constraint**, or **Expression or Constraint**, type an expression or launch the Expression Builder to create the expression.</span></span> <span data-ttu-id="0895b-113">Der Ausdruck muss zu einem booleschen Wert ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="0895b-113">The expression must evaluate to a Boolean.</span></span>  
  
 <span data-ttu-id="0895b-114">**Test**</span><span class="sxs-lookup"><span data-stu-id="0895b-114">**Test**</span></span>  
 <span data-ttu-id="0895b-115">Überprüfen Sie den Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="0895b-115">Validate the expression.</span></span>  
  
 <span data-ttu-id="0895b-116">**Logisches AND**</span><span class="sxs-lookup"><span data-stu-id="0895b-116">**Logical AND**</span></span>  
 <span data-ttu-id="0895b-117">Damit geben Sie an, dass für die ausführbare Datei mehrere Rangfolgeneinschränkungen gemeinsam überprüft werden müssen.</span><span class="sxs-lookup"><span data-stu-id="0895b-117">Select to specify that multiple precedence constraints on the same executable must be evaluated together.</span></span> <span data-ttu-id="0895b-118">Sämtliche Einschränkungen müssen mit `True` ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="0895b-118">All constraints must evaluate to `True`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0895b-119">Dieser Typ der Rangfolgeneinschränkung wird als durchgehende grüne, hervorgehobene oder blaue Linie dargestellt.</span><span class="sxs-lookup"><span data-stu-id="0895b-119">This type of precedence constraint appears as a solid green, highlighted or blue line.</span></span>  
  
 <span data-ttu-id="0895b-120">**Logisches OR**</span><span class="sxs-lookup"><span data-stu-id="0895b-120">**Logical OR**</span></span>  
 <span data-ttu-id="0895b-121">Damit geben Sie an, dass für die ausführbare Datei mehrere Rangfolgeneinschränkungen gemeinsam überprüft werden müssen.</span><span class="sxs-lookup"><span data-stu-id="0895b-121">Select to specify that multiple precedence constraints on the same executable must be evaluated together.</span></span> <span data-ttu-id="0895b-122">Mindestens eine Einschränkung muss mit `True` ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="0895b-122">At least one constraint must evaluate to `True`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0895b-123">Dieser Typ der Rangfolgeneinschränkung wird als gepunktete grüne, hervorgehobene oder blaue Linie dargestellt.</span><span class="sxs-lookup"><span data-stu-id="0895b-123">This type of precedence constraint appears as a dotted green, highlighted, or blue line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0895b-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0895b-124">See Also</span></span>  
 <span data-ttu-id="0895b-125">[Rang folgen Einschränkungen](control-flow/precedence-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="0895b-125">[Precedence Constraints](control-flow/precedence-constraints.md) </span></span>  
 <span data-ttu-id="0895b-126">[Integration Services-Tasks](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="0895b-126">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="0895b-127">[Integration Services Container](control-flow/integration-services-containers.md) </span><span class="sxs-lookup"><span data-stu-id="0895b-127">[Integration Services Containers](control-flow/integration-services-containers.md) </span></span>  
 [<span data-ttu-id="0895b-128">Integration Services-Ausdrücke &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="0895b-128">Integration Services &#40;SSIS&#41; Expressions</span></span>](expressions/integration-services-ssis-expressions.md)  
  
  
