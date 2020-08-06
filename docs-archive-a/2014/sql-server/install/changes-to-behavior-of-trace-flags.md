---
title: Änderungen am Verhalten von Ablaufverfolgungsflags | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- trace flags [SQL Server], behavior changes
ms.assetid: d739df96-2659-4383-8e10-194657632526
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 11d71e8401f6b870aaeb3f64f4145b509e3a3fe0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617514"
---
# <a name="changes-to-behavior-of-trace-flags"></a><span data-ttu-id="cc77f-102">Änderungen am Verhalten von Ablaufverfolgungsflags</span><span class="sxs-lookup"><span data-stu-id="cc77f-102">Changes to behavior of trace flags</span></span>
  <span data-ttu-id="cc77f-103">Globale Ablaufverfolgungsflags, die von einer Sitzung festgelegt werden, treten in anderen Sitzungen sofort in Kraft.</span><span class="sxs-lookup"><span data-stu-id="cc77f-103">Global trace flags set by a session take effect in other sessions immediately.</span></span> <span data-ttu-id="cc77f-104">Einige Ablaufverfolgungsflags von [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] sind in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="cc77f-104">Some trace flags from [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] do not exist in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
## <a name="component"></a><span data-ttu-id="cc77f-105">Komponente</span><span class="sxs-lookup"><span data-stu-id="cc77f-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="cc77f-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cc77f-106">Description</span></span>  
 <span data-ttu-id="cc77f-107">Es empfiehlt sich, alle Ablaufverfolgungsflags zu deaktivieren, bevor Sie ein Upgrade durchführen.</span><span class="sxs-lookup"><span data-stu-id="cc77f-107">We recommend that you disable all trace flags before you upgrade.</span></span> <span data-ttu-id="cc77f-108">Ablaufverfolgungsflags, die die Daten Bank Verfügbarkeit oder Wiederherstellungsmodi ändern, können verhindern, dass [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] Ihre Instanz von erfolgreich aktualisiert [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cc77f-108">Trace flags that modify the database availability or recovery modes might prevent the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssDE](../../includes/ssde-md.md)] from successfully upgrading your instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="cc77f-109">Sie können die Ablaufverfolgungsflags aktivieren, nachdem Sie überprüft haben, ob die Ablaufverfolgungsflags erforderlich und in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] immer noch gültig sind.</span><span class="sxs-lookup"><span data-stu-id="cc77f-109">You can enable the trace flags after you verify that the trace flags are required and are still valid in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="cc77f-110">Falls Sie die Ablaufverfolgungsflags erneut aktivieren müssen, sollten Sie zusätzliche Tests für Ihre Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] durchführen.</span><span class="sxs-lookup"><span data-stu-id="cc77f-110">If you must re-enable trace flags, you should perform additional tests on your instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="cc77f-111">unterstützt globale Ablaufverfolgungsflags und Ablaufverfolgungsflags auf Sitzungsebene.</span><span class="sxs-lookup"><span data-stu-id="cc77f-111">supports global and session level trace flags.</span></span> <span data-ttu-id="cc77f-112">Ablaufverfolgungsflags können in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] als lokal oder global festgelegt werden, indem Sie ein zusätzliches Argument (-1) im DBCC TRACEON-Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="cc77f-112">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], trace flags can be specified as either local or global by using an additional argument (-1) in the DBCC TRACEON command.</span></span> <span data-ttu-id="cc77f-113">Wenn Sie dieses Argument nicht angeben, ist der Standardwert lokal.</span><span class="sxs-lookup"><span data-stu-id="cc77f-113">If this argument is not specified, the default value is local.</span></span>  
  
 <span data-ttu-id="cc77f-114">Außerdem wird [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] ein in Sitzung a fest gelegenes Ablaufverfolgungsflag in einer bereits vorhandenen Sitzung B nicht automatisch wirksam. Stattdessen tritt dieses Ablaufverfolgungsflag erst dann in Kraft, wenn in Sitzung B das erste Ablaufverfolgungsflag festgelegt ist. Dieses Verhalten ist in nicht deterministisch [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] und in und höheren Versionen deterministisch [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] , wobei globale Ablaufverfolgungsflags, die in Sitzung A festgelegt werden, sofort in anderen gleichzeitigen Sitzungen festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="cc77f-114">Also, in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], a trace flag set in session A does not automatically take effect in an already existing session B. Instead, this trace flag takes effect only after the first time any trace flag is set in session B. This behavior is nondeterministic in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] and is deterministic in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions, where global trace flags set in session A are set immediately in other concurrent sessions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc77f-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cc77f-115">See Also</span></span>  
 <span data-ttu-id="cc77f-116">[Datenbank-Engine Upgradeprobleme](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="cc77f-116">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="cc77f-117">SQL Server 2014 Upgrade Advisor &#91;neuen&#93;</span><span class="sxs-lookup"><span data-stu-id="cc77f-117">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
