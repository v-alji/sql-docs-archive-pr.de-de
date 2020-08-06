---
title: Korrekte Überlappung der Affinitäts Maske und der Ausgabe Maske der Affinitäts Eingabe Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 1a0da6df-57ff-4f3f-aae9-2fbc4897508c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 486b4441a20db7630082344fb1f277bba053f3ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726902"
---
# <a name="correct-affinity-mask-and-affinity-input-output-mask-overlap"></a><span data-ttu-id="db8f2-102">Korrekte Überlappung der Affinitäts Maske und der Eingabe Ausgabe Maske der Affinität</span><span class="sxs-lookup"><span data-stu-id="db8f2-102">Correct Affinity Mask and Affinity Input Output Mask Overlap</span></span>
  <span data-ttu-id="db8f2-103">Diese Regel überprüft, ob die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] über einen oder mehrere Prozessoren verfügt, die sowohl für die Verwendung mit der Option Affinity Mask als auch mit der Option Affinity I/O Mask zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="db8f2-103">This rule checks whether the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has one or more processors that are assigned to be used with both the affinity mask and the affinity I/O mask options.</span></span> <span data-ttu-id="db8f2-104">Auf einem Computer, der über einen oder mehrere Prozessoren verfügt, bestimmen die Optionen Affinity Mask und Affinity I/O Mask, welche CPUs von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="db8f2-104">On a computer that has more than one processor, the affinity mask and the affinity I/O mask options are used to designate which CPUs are used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="db8f2-105">Das Aktivieren einer CPU mit den beiden Optionen Affinity Mask und Affinity I/O Mask kann die Leistung beeinträchtigen, da die Prozessoren übermäßig beansprucht werden.</span><span class="sxs-lookup"><span data-stu-id="db8f2-105">Enabling a CPU with both the affinity mask and the affinity I/O mask can slow performance by forcing the processor to be overused.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="db8f2-106">Empfehlungen zu Best Practices</span><span class="sxs-lookup"><span data-stu-id="db8f2-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="db8f2-107">Wenn Sie entweder die Option Affinity Mask oder die Option Affinity I/O Mask festlegen, sollten Sie beide Optionen festlegen, jedoch jede CPU nicht mehr als einmal aktivieren.</span><span class="sxs-lookup"><span data-stu-id="db8f2-107">When you specify either the affinity mask or the affinity I/O mask options, you should specify both, but only enable each CPU no more than once.</span></span>  
  
 <span data-ttu-id="db8f2-108">Aktivieren Sie in den Optionen Affinity Mask und Affinity I/O Mask nicht dieselbe CPU.</span><span class="sxs-lookup"><span data-stu-id="db8f2-108">Do not enable the same CPU in both the affinity mask option and the affinity I/O mask option.</span></span> <span data-ttu-id="db8f2-109">Die Bits, die den einzelnen CPUs entsprechen, sollten sich jeweils in einem der folgenden Zustände befinden:</span><span class="sxs-lookup"><span data-stu-id="db8f2-109">The bits that correspond to each CPU should be in one of the following states:</span></span>  
  
-   <span data-ttu-id="db8f2-110">0 für die Option Affinity Mask und die Option Affinity I/O Mask</span><span class="sxs-lookup"><span data-stu-id="db8f2-110">0 in both the affinity mask option and the affinity I/O mask option</span></span>  
  
-   <span data-ttu-id="db8f2-111">0 für die Option Affinity Mask und 1 für die Option Affinity I/O Mask</span><span class="sxs-lookup"><span data-stu-id="db8f2-111">0 in the affinity mask option and 1 in the affinity I/O mask option</span></span>  
  
-   <span data-ttu-id="db8f2-112">1 für die Option Affinity Mask und 0 für die Option Affinity I/O Mask</span><span class="sxs-lookup"><span data-stu-id="db8f2-112">1 in the affinity mask option and 0 in the affinity I/O mask option</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="db8f2-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="db8f2-113">For More Information</span></span>  
 [<span data-ttu-id="db8f2-114">Affinitätsmaske (Serverkonfigurationsoption)</span><span class="sxs-lookup"><span data-stu-id="db8f2-114">affinity mask Server Configuration Option</span></span>](../../database-engine/configure-windows/affinity-mask-server-configuration-option.md)  
  
 [<span data-ttu-id="db8f2-115">Affinity I/O Mask (Serverkonfigurationsoption)</span><span class="sxs-lookup"><span data-stu-id="db8f2-115">affinity Input-Output mask Server Configuration Option</span></span>](../../database-engine/configure-windows/affinity-input-output-mask-server-configuration-option.md)  
  
 [<span data-ttu-id="db8f2-116">Affinity64 Mask (Serverkonfigurationsoption)</span><span class="sxs-lookup"><span data-stu-id="db8f2-116">affinity64 mask Server Configuration Option</span></span>](../../database-engine/configure-windows/affinity64-mask-server-configuration-option.md)  
  
 [<span data-ttu-id="db8f2-117">affinity64 I/O mask (Serverkonfigurationsoption)</span><span class="sxs-lookup"><span data-stu-id="db8f2-117">affinity64 Input-Output mask Server Configuration Option</span></span>](../../database-engine/configure-windows/affinity64-input-output-mask-server-configuration-option.md)  
  
## <a name="see-also"></a><span data-ttu-id="db8f2-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="db8f2-118">See Also</span></span>  
 [<span data-ttu-id="db8f2-119">Überwachen und Erzwingen von Best Practices mit der richtlinienbasierten Verwaltung</span><span class="sxs-lookup"><span data-stu-id="db8f2-119">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
