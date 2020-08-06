---
title: Überprüfen von Planhinweislisten nach einem Upgrade | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- plan guides [SQL Server], validating after upgrade
ms.assetid: a55ebd88-6f58-454d-b1c4-991b88add522
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 18cc0f93ddec46025f659bcb9489bfff3ca846ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701061"
---
# <a name="validate-plan-guides-after-upgrade"></a><span data-ttu-id="e9edc-102">Überprüfen von Planhinweislisten nach einem Upgrade</span><span class="sxs-lookup"><span data-stu-id="e9edc-102">Validate Plan Guides After Upgrade</span></span>
  <span data-ttu-id="e9edc-103">Es empfiehlt sich, die Definitionen der Planhinweislisten nach einem Upgrade Ihrer Anwendung auf eine neue Version von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]neu zu bewerten und zu testen.</span><span class="sxs-lookup"><span data-stu-id="e9edc-103">We recommend re-evaluating and testing plan guide definitions when you upgrade your application to a new release of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="e9edc-104">Die Anforderungen an die Leistungsoptimierung und das Abgleichverhalten der Planhinweislisten können sich ändern.</span><span class="sxs-lookup"><span data-stu-id="e9edc-104">Performance tuning requirements and plan guide matching behavior may change.</span></span> <span data-ttu-id="e9edc-105">Eine ungültige Planhinweisliste führt zwar nicht zu einem Abfragefehler, der Plan wird jedoch ohne die Planhinweisliste kompiliert und ist daher eventuell nicht die beste Wahl.</span><span class="sxs-lookup"><span data-stu-id="e9edc-105">Although an invalid plan guide will not cause a query to fail, the plan is compiled without using the plan guide and may not be the best choice.</span></span> <span data-ttu-id="e9edc-106">Nach dem Upgrade einer Datenbank auf [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]sollten Sie möglichst die folgenden Aufgaben durchführen:</span><span class="sxs-lookup"><span data-stu-id="e9edc-106">After upgrading a database to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], we recommend that you perform the following tasks:</span></span>  
  
-   <span data-ttu-id="e9edc-107">Überprüfen Sie bestehende Planhinweislisten mit der [sys.fn_validate_plan_guide](/sql/relational-databases/system-functions/sys-fn-validate-plan-guide-transact-sql) -Funktion.</span><span class="sxs-lookup"><span data-stu-id="e9edc-107">Validate existing plan guides by using the [sys.fn_validate_plan_guide](/sql/relational-databases/system-functions/sys-fn-validate-plan-guide-transact-sql) function.</span></span>  
  
-   <span data-ttu-id="e9edc-108">Suchen Sie mit erweiterten Ereignissen einige Zeit lang anhand des [Plan Guide Unsuccessful-Ereignisses](../event-classes/plan-guide-unsuccessful-event-class.md) nach Plänen ohne Planhinweisliste.</span><span class="sxs-lookup"><span data-stu-id="e9edc-108">Use extended events to monitor for misguided plans for some period of time by using the [Plan Guide Unsuccessful](../event-classes/plan-guide-unsuccessful-event-class.md) event.</span></span>  
  
  
