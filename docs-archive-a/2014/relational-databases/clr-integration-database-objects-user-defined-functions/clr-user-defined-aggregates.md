---
title: Benutzerdefinierte CLR-Aggregate | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- aggregate functions [CLR integration]
- custom aggregates [CLR integration]
- calculations [CLR integration]
- user-defined functions [CLR integration]
ms.assetid: bad9b7e8-5967-4afa-8dc8-6d840faf9372
author: rothja
ms.author: jroth
ms.openlocfilehash: d1ef5d07fe082d0eeb2c3484d6e99572d8fc80e5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618732"
---
# <a name="clr-user-defined-aggregates"></a><span data-ttu-id="6f92b-102">Benutzerdefinierte CLR-Aggregate</span><span class="sxs-lookup"><span data-stu-id="6f92b-102">CLR User-Defined Aggregates</span></span>
  <span data-ttu-id="6f92b-103">Aggregatfunktionen führen eine Berechnung für eine Gruppe von Werten durch und geben einen einzelnen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="6f92b-103">Aggregate functions perform a calculation on a set of values and return a single value.</span></span> <span data-ttu-id="6f92b-104">Hat traditionell [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nur integrierte Aggregatfunktionen unterstützt, wie z. b. `SUM` oder `MAX` , die für einen Satz von skalaren Eingabe Werten verwendet werden und einen einzelnen Aggregatwert aus diesem Satz generieren.</span><span class="sxs-lookup"><span data-stu-id="6f92b-104">Traditionally, [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has supported only built-in aggregate functions, such as `SUM` or `MAX`, that operate on a set of input scalar values and generate a single aggregate value from that set.</span></span> <span data-ttu-id="6f92b-105">Die Integration von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in die [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework-CLR (Common Language Runtime) ermöglicht Entwicklern jetzt, benutzerdefinierte Aggregatfunktionen in verwaltetem Code zu erstellen und diese Funktionen für [!INCLUDE[tsql](../../includes/tsql-md.md)] und anderen verwalteten Code zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="6f92b-105">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] integration with the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework common language runtime (CLR) now allows developers to create custom aggregate functions in managed code, and to make these functions accessible to [!INCLUDE[tsql](../../includes/tsql-md.md)] or other managed code.</span></span>  
  
 <span data-ttu-id="6f92b-106">In der folgenden Tabelle sind die Themen dieses Abschnitts aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="6f92b-106">The following table lists the topics in this section.</span></span>  
  
 [<span data-ttu-id="6f92b-107">Anforderungen für benutzerdefinierte CLR-Aggregate</span><span class="sxs-lookup"><span data-stu-id="6f92b-107">Requirements for CLR User-Defined Aggregates</span></span>](clr-user-defined-aggregates-requirements.md)  
 <span data-ttu-id="6f92b-108">Stellt eine Übersicht über die Anforderungen zum Implementieren von benutzerdefinierten CLR-Aggregatfunktionen bereit.</span><span class="sxs-lookup"><span data-stu-id="6f92b-108">Provides an overview of the requirements for implementing CLR user-defined aggregate functions.</span></span>  
  
 [<span data-ttu-id="6f92b-109">Aufrufen von CLR-benutzerdefinierten Aggregatfunktionen</span><span class="sxs-lookup"><span data-stu-id="6f92b-109">Invoking CLR User-Defined Aggregate Functions</span></span>](clr-user-defined-aggregate-invoking-functions.md)  
 <span data-ttu-id="6f92b-110">Erläutert, wie benutzerdefinierte Aggregate aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="6f92b-110">Explains how to invoke user-defined aggregates.</span></span>  
  
  
