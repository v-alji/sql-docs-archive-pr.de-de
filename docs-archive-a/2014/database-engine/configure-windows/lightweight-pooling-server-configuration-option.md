---
title: Lightweightpooling (Serverkonfigurationsoption) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- default lightweight pooling
- decreasing overhead
- lightweight pooling option
- system overhead [SQL Server]
- performance [SQL Server], lightweight pooling
- context switching [SQL Server], lightweight pooling option
- excessive context switching [SQL Server]
- reducing overhead
- overhead [SQL Server]
ms.assetid: 2dc11b61-d065-4126-8e00-acf40390f9fb
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 549ff7451a31b48459b5a290b94ad406c3768a91
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618900"
---
# <a name="lightweight-pooling-server-configuration-option"></a><span data-ttu-id="1cea8-102">Lightweightpooling (Serverkonfigurationsoption)</span><span class="sxs-lookup"><span data-stu-id="1cea8-102">lightweight pooling Server Configuration Option</span></span>
  <span data-ttu-id="1cea8-103">Mit der Option **lightweight pooling** können Sie den Systemverarbeitungsaufwand im Zusammenhang mit häufigen Kontextumschaltungen senken, die teilweise in symmetrischen Multiprocessing-Umgebungen (SMP) auftreten.</span><span class="sxs-lookup"><span data-stu-id="1cea8-103">Use the **lightweight pooling** option to provide a means of reducing the system overhead associated with the excessive context switching sometimes seen in symmetric multiprocessing (SMP) environments.</span></span> <span data-ttu-id="1cea8-104">Bei häufigen Kontextumschaltungen kann die Option "Lightweightpooling" für einen besseren Durchsatz sorgen, da die Kontextumschaltungen inline ausgeführt werden, was die Anzahl der Benutzer-/Kernelringübergänge verringert.</span><span class="sxs-lookup"><span data-stu-id="1cea8-104">When excessive context switching is present, lightweight pooling can provide better throughput by performing the context switching inline, thus helping to reduce user/kernel ring transitions.</span></span>  
  
 <span data-ttu-id="1cea8-105">Der Fibermodus gilt für bestimmte Situationen, in denen der Kontextwechsel von UMS-Arbeitsthreads kritische Engpässe bei der Leistung verursacht.</span><span class="sxs-lookup"><span data-stu-id="1cea8-105">Fiber mode is intended for certain situations in which the context switching of the UMS workers are the critical bottleneck in performance.</span></span> <span data-ttu-id="1cea8-106">Da dies nur selten auftritt, verbessert der Fibermodus auch nur selten die Leistung oder die Skalierbarkeit auf einem typischen System.</span><span class="sxs-lookup"><span data-stu-id="1cea8-106">Because this is rare, fiber mode rarely enhances performance or scalability on the typical system.</span></span> <span data-ttu-id="1cea8-107">Durch den verbesserten Kontextwechsel in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] wurde auch die Notwendigkeit des Fibermodus reduziert.</span><span class="sxs-lookup"><span data-stu-id="1cea8-107">Improved context switching in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] has also reduced the need for fiber mode.</span></span> <span data-ttu-id="1cea8-108">Es wird empfohlen, die Fibermodusplanung nicht für Routinevorgänge zu verwenden,</span><span class="sxs-lookup"><span data-stu-id="1cea8-108">We do not recommend that you use fiber mode scheduling for routine operation.</span></span> <span data-ttu-id="1cea8-109">da sie die Leistung verringern kann, indem die normalen Vorteile des Kontextwechsels unterdrückt werden, und da einige Komponenten von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , die den lokalen Threadspeicher (TLS) verwenden, oder Thread-eigene Objekte, z. B. Mutexe (eine Art Win32-Kernel-Objekt), im Fibermodus nicht ordnungsgemäß arbeiten können.</span><span class="sxs-lookup"><span data-stu-id="1cea8-109">This is because it can decrease performance by inhibiting the regular benefits of context switching, and because some components of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that use Thread Local Storage (TLS) or thread-owned objects, such as mutexes (a type of Win32 kernel object), cannot function correctly in fiber mode.</span></span>  
  
 <span data-ttu-id="1cea8-110">Wenn der Wert der Option **Lightweightpooling** auf 1 festgelegt wird, wechselt [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] zur Fibermodusplanung.</span><span class="sxs-lookup"><span data-stu-id="1cea8-110">Setting **lightweight pooling** to 1 causes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to switch to fiber mode scheduling.</span></span> <span data-ttu-id="1cea8-111">Der Standardwert für diese Option ist 0.</span><span class="sxs-lookup"><span data-stu-id="1cea8-111">The default value for this option is 0.</span></span>  
  
 <span data-ttu-id="1cea8-112">Bei **Lightweightpooling** handelt es sich um eine erweiterte Option.</span><span class="sxs-lookup"><span data-stu-id="1cea8-112">The **lightweight pooling** option is an advanced option.</span></span> <span data-ttu-id="1cea8-113">Wenn Sie die Einstellung mithilfe der gespeicherten Systemprozedur **sp_configure** ändern, können Sie **Lightweightpooling** nur ändern, wenn **Erweiterte Optionen anzeigen** auf 1 festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="1cea8-113">If you are using the **sp_configure** system stored procedure to change the setting, you can change **lightweight pooling** only when **show advanced options** is set to 1.</span></span> <span data-ttu-id="1cea8-114">Diese Einstellung wird wirksam, nachdem der Server neu gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="1cea8-114">The setting takes effect after the server is restarted.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1cea8-115">Lightweightpooling wird für [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows 2000 und [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows XP nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1cea8-115">Lightweight pooling is not supported for [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows 2000 and [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows XP.</span></span> [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] <span data-ttu-id="1cea8-116">stellt eine vollständige Unterstützung für Lightweightpooling bereit.</span><span class="sxs-lookup"><span data-stu-id="1cea8-116">provides full support for lightweight pooling.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1cea8-117">CLR (Common Language Runtime) wird beim Lightweightpooling nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1cea8-117">Common language runtime (CLR) execution is not supported under lightweight pooling.</span></span> <span data-ttu-id="1cea8-118">Deaktivieren Sie eine der beiden Optionen "CLR-fähig" oder "Lightweightpooling".</span><span class="sxs-lookup"><span data-stu-id="1cea8-118">Disable one of two options: "clr enabled" or "lightweight pooling".</span></span> <span data-ttu-id="1cea8-119">Zu den Funktionen, die auf CLR basieren und nicht ordnungsgemäß im Fibermodus arbeiten, gehören der Hierarchy-Datentyp, die Replikation und die richtlinienbasierte Verwaltung.</span><span class="sxs-lookup"><span data-stu-id="1cea8-119">Features that rely upon CLR and that do not work properly in fiber mode include the hierarchy data type, replication, and Policy-Based Management.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cea8-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1cea8-120">See Also</span></span>  
 <span data-ttu-id="1cea8-121">[CLR-fähig (Serverkonfigurationsoption)](clr-enabled-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="1cea8-121">[clr enabled Server Configuration Option](clr-enabled-server-configuration-option.md) </span></span>  
 <span data-ttu-id="1cea8-122">[Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1cea8-122">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="1cea8-123">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1cea8-123">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="1cea8-124">CLR-fähig (Serverkonfigurationsoption)</span><span class="sxs-lookup"><span data-stu-id="1cea8-124">clr enabled Server Configuration Option</span></span>](clr-enabled-server-configuration-option.md)  
  
  
