---
title: Aktualisieren von OPENXML-XPath-Ausdrücken, um nicht unterstützte Funktionen zu entfernen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- OPENXML queries
ms.assetid: b459abaf-8787-4b65-9231-ae30e5469fd0
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 2c64408d6d705654014b6d071012001374a5f486
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617428"
---
# <a name="update-openxml-xpath-expressions-to-remove-unsupported-functions"></a><span data-ttu-id="46857-102">Aktualisieren von OPENXML-XPath-Ausdrücken, um nicht unterstützte Funktionen zu entfernen</span><span class="sxs-lookup"><span data-stu-id="46857-102">Update OPENXML XPath expressions to remove unsupported functions</span></span>
  <span data-ttu-id="46857-103">Der Upgrade Advisor hat die Verwendung der XPath-Funktionalität erkannt.</span><span class="sxs-lookup"><span data-stu-id="46857-103">Upgrade Advisor detected the use of XPath functionality.</span></span> <span data-ttu-id="46857-104">Durch das Upgrade kommt es möglicherweise zu Problemen durch die Änderungen der Xpath-Funktionalität für OPENXML-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="46857-104">You may be affected by changes in XPath functionality for OPENXML features after you upgrade.</span></span>  
  
## <a name="component"></a><span data-ttu-id="46857-105">Komponente</span><span class="sxs-lookup"><span data-stu-id="46857-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="46857-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="46857-106">Description</span></span>  
 <span data-ttu-id="46857-107">MSXML 3.0 ist jetzt die zugrunde liegende Engine, die zur Verarbeitung von XPath-Ausdrücken verwendet wird, die in OPENXML-Abfragen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="46857-107">MSXML 3.0 is now the underlying engine that is used to process XPath expressions that are used within OPENXML queries.</span></span> <span data-ttu-id="46857-108">MSXML 3.0 beinhaltet eine strengere XPath 1.0-Engine, in der die folgenden Funktionen nicht mehr unterstützt werden:</span><span class="sxs-lookup"><span data-stu-id="46857-108">MSXML 3.0 has a stricter XPath 1.0 engine in which support for the following functions has been removed:</span></span>  
  
-   <span data-ttu-id="46857-109">format-number()</span><span class="sxs-lookup"><span data-stu-id="46857-109">format-number()</span></span>  
  
-   <span data-ttu-id="46857-110">formatNumber()</span><span class="sxs-lookup"><span data-stu-id="46857-110">formatNumber()</span></span>  
  
-   <span data-ttu-id="46857-111">current()</span><span class="sxs-lookup"><span data-stu-id="46857-111">current()</span></span>  
  
-   <span data-ttu-id="46857-112">element-available()</span><span class="sxs-lookup"><span data-stu-id="46857-112">element-available()</span></span>  
  
-   <span data-ttu-id="46857-113">function-available()</span><span class="sxs-lookup"><span data-stu-id="46857-113">function-available()</span></span>  
  
-   <span data-ttu-id="46857-114">system-property()</span><span class="sxs-lookup"><span data-stu-id="46857-114">system-property()</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="46857-115">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="46857-115">Corrective Action</span></span>  
 <span data-ttu-id="46857-116">Was format-number() und formatNumber() betrifft, so können Sie [!INCLUDE[tsql](../../includes/tsql-md.md)] verwenden.</span><span class="sxs-lookup"><span data-stu-id="46857-116">In the case of format-number() and formatNumber(), you can use [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="46857-117">Für die anderen nicht unterstützten Funktionen, die weiter oben aufgeführt sind, gibt es keine direkte Problemumgehung.</span><span class="sxs-lookup"><span data-stu-id="46857-117">For the other unsupported functions listed earlier, there is no direct workaround.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46857-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="46857-118">See Also</span></span>  
 <span data-ttu-id="46857-119">[Datenbank-Engine Upgradeprobleme](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="46857-119">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="46857-120">SQL Server 2014 Upgrade Advisor &#91;neuen&#93;</span><span class="sxs-lookup"><span data-stu-id="46857-120">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
