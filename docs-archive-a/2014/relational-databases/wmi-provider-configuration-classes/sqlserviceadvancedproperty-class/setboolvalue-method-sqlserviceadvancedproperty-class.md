---
title: Haltepunkte festlegen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.setbreakpoints.f1
helpviewer_keywords:
- Set Breakpoints dialog box
ms.assetid: 876e61b7-875c-43f4-bbce-d7eeb90f6730
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 8115fcd845ee5ff415d13aa4fe36230234e33ca0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722638"
---
# <a name="set-breakpoints"></a><span data-ttu-id="28e96-102">Breakpoints festlegen</span><span class="sxs-lookup"><span data-stu-id="28e96-102">Set Breakpoints</span></span>
  <span data-ttu-id="28e96-103">Verwenden Sie das Dialogfeld **Breakpoints festlegen** , um die Ereignisse anzugeben, für die Breakpoints aktiviert werden sollen, sowie um das Verhalten der Breakpoints zu steuern.</span><span class="sxs-lookup"><span data-stu-id="28e96-103">Use the **Set Breakpoints** dialog box to specify the events on which to enable breakpoints and to control the behavior of the breakpoint.</span></span>  
  
## <a name="options"></a><span data-ttu-id="28e96-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="28e96-104">Options</span></span>  
 <span data-ttu-id="28e96-105">**Aktiviert**</span><span class="sxs-lookup"><span data-stu-id="28e96-105">**Enabled**</span></span>  
 <span data-ttu-id="28e96-106">Wählen Sie diese Option aus, um einen Breakpoint für ein Ergebnis zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="28e96-106">Select to enable a breakpoint on an event.</span></span>  
  
 <span data-ttu-id="28e96-107">**Break Condition**</span><span class="sxs-lookup"><span data-stu-id="28e96-107">**Break Condition**</span></span>  
 <span data-ttu-id="28e96-108">Zeigen Sie eine Liste von verfügbaren Ereignissen an, für die Breakpoints festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="28e96-108">View a list of available events on which to set breakpoints.</span></span>  
  
 <span data-ttu-id="28e96-109">**Hit Count Type**</span><span class="sxs-lookup"><span data-stu-id="28e96-109">**Hit Count Type**</span></span>  
 <span data-ttu-id="28e96-110">Geben Sie an, wann der Breakpoint wirksam werden soll.</span><span class="sxs-lookup"><span data-stu-id="28e96-110">Specify when the breakpoint takes effect.</span></span>  
  
|<span data-ttu-id="28e96-111">Wert</span><span class="sxs-lookup"><span data-stu-id="28e96-111">Value</span></span>|<span data-ttu-id="28e96-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="28e96-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="28e96-113">**Always**</span><span class="sxs-lookup"><span data-stu-id="28e96-113">**Always**</span></span>|<span data-ttu-id="28e96-114">Die Ausführung wird immer angehalten, wenn der Breakpoint erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="28e96-114">Execution is always suspended when the breakpoint is hit.</span></span>|  
|<span data-ttu-id="28e96-115">**Trefferanzahl ist gleich**</span><span class="sxs-lookup"><span data-stu-id="28e96-115">**Hit count equals**</span></span>|<span data-ttu-id="28e96-116">Die Ausführung wird angehalten, wenn die Anzahl des Auftretens des Breakpoints der Trefferanzahl entspricht.</span><span class="sxs-lookup"><span data-stu-id="28e96-116">Execution is suspended when the number of times the breakpoint has occurred is equal to the hit count.</span></span>|  
|<span data-ttu-id="28e96-117">**Trefferanzahl ist größer als oder gleich**</span><span class="sxs-lookup"><span data-stu-id="28e96-117">**Hit greater or equal**</span></span>|<span data-ttu-id="28e96-118">Die Ausführung wird angehalten, wenn die Anzahl des Auftretens des Breakpoints mindestens so groß wie die Trefferanzahl ist.</span><span class="sxs-lookup"><span data-stu-id="28e96-118">Execution is suspended when the number of times the breakpoint has occurred is equal to or greater than the hit count.</span></span>|  
|<span data-ttu-id="28e96-119">**Trefferanzahl mehrfach**</span><span class="sxs-lookup"><span data-stu-id="28e96-119">**Hit count multiple**</span></span>|<span data-ttu-id="28e96-120">Die Ausführung wird angehalten, wenn ein Mehrfaches der Trefferanzahl erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="28e96-120">Execution is suspended when a multiple of the hit count occurs.</span></span> <span data-ttu-id="28e96-121">Wenn Sie z. B. diese Option auf 5 festlegen, wird die Ausführung bei jedem fünften Mal angehalten.</span><span class="sxs-lookup"><span data-stu-id="28e96-121">For example, if you set this option to 5, execution is suspended every fifth time.</span></span>|  
  
 <span data-ttu-id="28e96-122">**Trefferanzahl**</span><span class="sxs-lookup"><span data-stu-id="28e96-122">**Hit Count**</span></span>  
 <span data-ttu-id="28e96-123">Geben Sie die Anzahl der Treffer an, nach denen ein Breakpoint ausgelöst werden soll.</span><span class="sxs-lookup"><span data-stu-id="28e96-123">Specify the number of hits at which to trigger a break.</span></span> <span data-ttu-id="28e96-124">Diese Option ist nicht verfügbar, wenn der Breakpoint immer wirksam ist.</span><span class="sxs-lookup"><span data-stu-id="28e96-124">This option is not available if the breakpoint is always in effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28e96-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="28e96-125">See Also</span></span>  
 [<span data-ttu-id="28e96-126">Debuggen der Ablaufsteuerung</span><span class="sxs-lookup"><span data-stu-id="28e96-126">Debugging Control Flow</span></span>](../../../integration-services/troubleshooting/debugging-control-flow.md)  
  
  
