---
title: Deaktivieren des Lightweightpoolings | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 481bb43d-6fe5-497c-9096-971fb6bf733b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 13b9ccba0a3a5805dab2eec1d04cc161e6dbd6ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725590"
---
# <a name="disable-lightweight-pooling"></a><span data-ttu-id="c529a-102">Deaktivieren des Lightweightpoolings</span><span class="sxs-lookup"><span data-stu-id="c529a-102">Disable Lightweight Pooling</span></span>
  <span data-ttu-id="c529a-103">Diese Regel überprüft, ob Lightweightpooling auf dem Server deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="c529a-103">This rule checks that lightweight pooling is disabled on the server.</span></span> <span data-ttu-id="c529a-104">Wenn Lightweightpooling auf 1 festgelegt wird, wechselt [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] zur Fibermodusplanung.</span><span class="sxs-lookup"><span data-stu-id="c529a-104">Setting lightweightpooling to 1 causes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to switch to fiber mode scheduling.</span></span> <span data-ttu-id="c529a-105">Der Fibermodus ist für bestimmte Situationen vorgesehen, in denen der Kontextwechsel der UMS-Arbeitsthreads kritische Engpässe bei der Leistung verursacht.</span><span class="sxs-lookup"><span data-stu-id="c529a-105">Fiber mode is intended for certain situations in which the context switching of the UMS workers is the important bottleneck in performance.</span></span> <span data-ttu-id="c529a-106">Da dies nur selten auftritt, verbessert der Fibermodus auch nur selten die Leistung oder die Skalierbarkeit auf einem typischen System.</span><span class="sxs-lookup"><span data-stu-id="c529a-106">Because this is rare, fiber mode seldom improves performance or scalability on the typical system.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="c529a-107">Empfehlungen zu Best Practices</span><span class="sxs-lookup"><span data-stu-id="c529a-107">Best Practices Recommendations</span></span>  
 <span data-ttu-id="c529a-108">Die Lightweightpooling-Option darf nur nach gründlichen Tests aktiviert werden, nachdem alle anderen Möglichkeiten zur Leistungsoptimierung ausgewertet wurden und der Kontextwechsel ein bekanntes Problem in Ihrer Umgebung darstellt.</span><span class="sxs-lookup"><span data-stu-id="c529a-108">The lightweightpooling option should only be enabled after thorough testing, after all other performance tuning opportunities are evaluated, and when context switching is a known issue in your environment.</span></span>  
  
 <span data-ttu-id="c529a-109">Es wird empfohlen, die Fibermodusplanung nicht für Routinevorgänge zu verwenden, da sie die Leistung verringern kann, indem die normalen Vorteile des Kontextwechsels unterdrückt werden, und da einige Komponenten von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , die den lokalen Threadspeicher (TLS) verwenden, oder Thread-eigene Objekte, z. B. Mutexe (eine Art Win32-Kernel-Objekt), im Fibermodus nicht ordnungsgemäß arbeiten können.</span><span class="sxs-lookup"><span data-stu-id="c529a-109">We recommend that you do not use fiber mode scheduling for routine operation because it can decrease performance by preventing the regular benefits of context switching, and because some components of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that use Thread Local Storage (TLS) or thread-owned objects, such as mutexes (a kind of Win32 kernel object), cannot function correctly in fiber mode</span></span>  
  
 <span data-ttu-id="c529a-110">Um Lightweightpooling zu entfernen, führen Sie die folgende Anweisung aus, und starten Sie dann [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]neu.</span><span class="sxs-lookup"><span data-stu-id="c529a-110">To remove lightweight pooling, execute the following statement, and then restart the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
```  
sp_configure 'show advanced options', 1;  
GO  
sp_configure 'lightweightpooling', 0;  
GO  
RECONFIGURE;  
GO  
```  
  
## <a name="for-more-information"></a><span data-ttu-id="c529a-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c529a-111">For More Information</span></span>  
 [<span data-ttu-id="c529a-112">Lightweightpooling (Serverkonfigurationsoption)</span><span class="sxs-lookup"><span data-stu-id="c529a-112">lightweight pooling Server Configuration Option</span></span>](../../database-engine/configure-windows/lightweight-pooling-server-configuration-option.md)  
  
## <a name="see-also"></a><span data-ttu-id="c529a-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c529a-113">See Also</span></span>  
 [<span data-ttu-id="c529a-114">Überwachen und Erzwingen von Best Practices mit der richtlinienbasierten Verwaltung</span><span class="sxs-lookup"><span data-stu-id="c529a-114">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
