---
title: Geschachtelter after-Triggertyp, auch wenn triggerschachtelung deaktiviert ist Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- DML triggers, nested
- nested triggers option
- triggers [SQL Server], nested
ms.assetid: 94d72960-676e-40d9-81bc-08bffe778110
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: f91c04e8d69880b451c1479e2907cd1910e8f9c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726497"
---
# <a name="nested-after-trigger-fires-even-when-trigger-nesting-is-off"></a><span data-ttu-id="cfe46-102">Geschachtelter AFTER-Trigger wird sogar ausgelöst, wenn Triggerschachtelung OFF ist</span><span class="sxs-lookup"><span data-stu-id="cfe46-102">Nested AFTER trigger fires even when trigger nesting is OFF</span></span>
  <span data-ttu-id="cfe46-103">Der Upgrade Advisor hat einen AFTER-Trigger erkannt, der in einem für eine oder mehrere Tabellen definierten INSTEAD OF-Trigger geschachtelt ist.</span><span class="sxs-lookup"><span data-stu-id="cfe46-103">Upgrade Advisor detected an AFTER trigger nested inside an INSTEAD OF trigger that is defined on one or more tables.</span></span> <span data-ttu-id="cfe46-104">Geschachtelte AFTER-Trigger werden möglicherweise ausgelöst, wenn die `nested triggers`-Serverkonfigurationsoption auf 0 (null) festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="cfe46-104">Nested AFTER triggers may fire even when the `nested triggers` server configuration option is set to 0.</span></span>  
  
## <a name="component"></a><span data-ttu-id="cfe46-105">Komponente</span><span class="sxs-lookup"><span data-stu-id="cfe46-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="cfe46-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cfe46-106">Description</span></span>  
 <span data-ttu-id="cfe46-107">Der erste AFTER-Trigger, der in einem INSTEAD OF-Trigger geschachtelt ist, wird auch dann ausgelöst, wenn die `nested triggers`-Serverkonfigurationsoption auf 0 festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="cfe46-107">The first AFTER trigger nested inside an INSTEAD OF trigger fires even if the `nested triggers` server configuration option is set to 0.</span></span> <span data-ttu-id="cfe46-108">Jedoch werden bei dieser Einstellung nachfolgende AFTER-Trigger nicht ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="cfe46-108">However, under this setting, subsequent AFTER triggers do not fire.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="cfe46-109">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="cfe46-109">Corrective Action</span></span>  
 <span data-ttu-id="cfe46-110">Überprüfen Sie die Anwendungen auf geschachtelte Trigger, um zu ermitteln, ob die Anwendungen in Bezug auf dieses Verhalten bei Festlegung der `nested triggers`-Serverkonfigurationsoption auf 0 (Null) noch Ihren Geschäftsregeln entsprechen. Nehmen Sie dann geeignete Änderungen vor.</span><span class="sxs-lookup"><span data-stu-id="cfe46-110">Review your applications for nested triggers to determine whether the applications still comply with your business rules with regard to this new behavior when the `nested triggers` server configuration option is set to 0, and then make appropriate modifications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfe46-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cfe46-111">See Also</span></span>  
 <span data-ttu-id="cfe46-112">[Datenbank-Engine Upgradeprobleme](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="cfe46-112">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="cfe46-113">SQL Server 2014 Upgrade Advisor &#91;neuen&#93;</span><span class="sxs-lookup"><span data-stu-id="cfe46-113">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
