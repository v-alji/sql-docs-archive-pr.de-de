---
title: PowerShell-Referenz (Datenbank-Engine) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 3c379a43-c497-47dd-8e7d-2b015c068bb7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 2d72f9fcedee02e475369c32a7c263578c9ff156
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618883"
---
# <a name="database-engine-powershell-reference"></a><span data-ttu-id="15c9c-102">PowerShell-Referenz (Datenbank-Engine)</span><span class="sxs-lookup"><span data-stu-id="15c9c-102">Database Engine PowerShell Reference</span></span>
  [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="15c9c-103">beinhaltet eine Reihe von Windows PowerShell 2.0-Cmdlets zur Durchführung allgemeiner Aufgaben im [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="15c9c-103">includes a set of Windows PowerShell 2.0 cmdlets for performing common actions in the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span> <span data-ttu-id="15c9c-104">Zudem können Abfrageausdrücke und Uniform Resource Names (URNs) in SQL Server PowerShell-Pfade konvertiert oder zum Angaben eines oder mehrerer Objekte im [!INCLUDE[ssDE](../includes/ssde-md.md)]verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="15c9c-104">In addition, Query Expressions and Uniform Resource Names (URN) can be converted to SQL Server PowerShell paths, or used to specify one or more objects in the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
## <a name="database-engine-cmdlets"></a><span data-ttu-id="15c9c-105">Datenbank-Engine-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="15c9c-105">Database Engine Cmdlets</span></span>  
 [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] <span data-ttu-id="15c9c-106">beinhaltet relativ wenige Cmdlets für das [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="15c9c-106">includes relatively few cmdlets for the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span> <span data-ttu-id="15c9c-107">Die meisten PowerShell-Skripts, die mit dem [!INCLUDE[ssDE](../includes/ssde-md.md)] verwendet werden, nutzen den SQL Server PowerShell-Anbieter und die Verwaltbarkeitsobjektmodelle.</span><span class="sxs-lookup"><span data-stu-id="15c9c-107">Most PowerShell scripts working with the [!INCLUDE[ssDE](../includes/ssde-md.md)] use the SQL Server PowerShell provider and the manageability object models.</span></span> <span data-ttu-id="15c9c-108">Weitere Informationen finden Sie unter [SQL Server PowerShell Provider](../powershell/sql-server-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="15c9c-108">For more information, see [SQL Server PowerShell Provider](../powershell/sql-server-powershell-provider.md).</span></span>  
  
 <span data-ttu-id="15c9c-109">Informationen zum Anfordern von Hilfe zu den SQL Server-Cmdlets in einer Windows PowerShell-Umgebung finden Sie unter [Get Help SQL Server PowerShell](../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="15c9c-109">To learn how to get help about the SQL Server cmdlets in a Windows PowerShell environment, see [Get Help SQL Server PowerShell](../powershell/sql-server-powershell.md).</span></span>  
  
### <a name="in-this-section"></a><span data-ttu-id="15c9c-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="15c9c-110">In This Section</span></span>  
 <span data-ttu-id="15c9c-111">Dieser Abschnitt enthält Informationen zu den folgenden Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="15c9c-111">This section contains information about these cmdlets.</span></span>  
  
|<span data-ttu-id="15c9c-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="15c9c-112">Description</span></span>|<span data-ttu-id="15c9c-113">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="15c9c-113">Cmdlet</span></span>|  
|-----------------|------------|  
|<span data-ttu-id="15c9c-114">Führt Transact-SQL- und XQuery-Skripte aus, z. B. Skripts, die mit dem Hilfsprogramm `sqlcmd` ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="15c9c-114">Runs Transact-SQL and XQuery scripts, such as scripts that can be run using the `sqlcmd` utility.</span></span>|[<span data-ttu-id="15c9c-115">Invoke-Sqlcmd-Cmdlet</span><span class="sxs-lookup"><span data-stu-id="15c9c-115">Invoke-Sqlcmd cmdlet</span></span>](../../2014/database-engine/invoke-sqlcmd-cmdlet.md)|  
|<span data-ttu-id="15c9c-116">Ermittelt, ob ein Datenbank-Engine-Objekt einer Richtlinie für die richtlinienbasierte Verwaltung entspricht.</span><span class="sxs-lookup"><span data-stu-id="15c9c-116">Evaluates whether a Database Engine object complies with a Policy-based Management policy.</span></span>|[<span data-ttu-id="15c9c-117">Invoke-PolicyEvaluation-Cmdlet</span><span class="sxs-lookup"><span data-stu-id="15c9c-117">Invoke-PolicyEvaluation cmdlet</span></span>](../../2014/database-engine/invoke-policyevaluation-cmdlet.md)|  
  
### <a name="information-about-other-cmdlets"></a><span data-ttu-id="15c9c-118">Informationen zu anderen Cmdlets</span><span class="sxs-lookup"><span data-stu-id="15c9c-118">Information About Other Cmdlets</span></span>  
 <span data-ttu-id="15c9c-119">Das `Encode-Sqlname`-Cmdlet und das `Decode-Sqlname`-Cmdlet helfen Ihnen, SQL Server-Bezeichner mit Zeichen anzugeben, die in PowerShell-Pfaden nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="15c9c-119">The `Encode-Sqlname` and `Decode-Sqlname` cmdlets help you specify SQL Server identifiers that contain characters not supported in PowerShell paths.</span></span> <span data-ttu-id="15c9c-120">Weitere Informationen finden Sie unter [SQL Server Identifiers in PowerShell](../powershell/sql-server-identifiers-in-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="15c9c-120">For more information, see [SQL Server Identifiers in PowerShell](../powershell/sql-server-identifiers-in-powershell.md).</span></span>  
  
 <span data-ttu-id="15c9c-121">Mit dem `Convert-UrnToPath`-Cmdlet können Sie einen eindeutigen Ressourcennamen (Unique Resource Name, URN) für ein [!INCLUDE[ssDE](../includes/ssde-md.md)]-Objekt einen Pfad für den SQL Server PowerShell-Anbieter konvertieren.</span><span class="sxs-lookup"><span data-stu-id="15c9c-121">Use the `Convert-UrnToPath` cmdlet to convert a Unique Resource Name for a [!INCLUDE[ssDE](../includes/ssde-md.md)] object to a path for the SQL Server PowerShell provider.</span></span> <span data-ttu-id="15c9c-122">Weitere Informationen finden Sie unter [Convert URNs to SQL Server Provider Paths](../../2014/database-engine/convert-urns-to-sql-server-provider-paths.md).</span><span class="sxs-lookup"><span data-stu-id="15c9c-122">For more information, see [Convert URNs to SQL Server Provider Paths](../../2014/database-engine/convert-urns-to-sql-server-provider-paths.md).</span></span>  
  
## <a name="query-expressions-and-unique-resource-names"></a><span data-ttu-id="15c9c-123">Abfrageausdrücke und eindeutige Ressourcennamen</span><span class="sxs-lookup"><span data-stu-id="15c9c-123">Query Expressions and Unique Resource Names</span></span>  
 <span data-ttu-id="15c9c-124">Bei Abfrageausdrücken handelt es sich um Zeichenfolgen, die eine ähnliche Syntax wie XPath nutzen, um eine Gruppe von Kriterien angeben, mit der ein oder mehrere Objekte in einer Objektmodellhierarchie aufgezählt werden.</span><span class="sxs-lookup"><span data-stu-id="15c9c-124">Query expressions are strings that use syntax similar to XPath to specify a set of criteria that enumerate one or more objects in an object model hierarchy.</span></span> <span data-ttu-id="15c9c-125">Ein eindeutiger Ressourcenname (Unique Resource Name, URN) ist ein spezieller Typ einer Abfrageausdrucks-Zeichenfolge, der ein einzelnes Objekt eindeutig kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="15c9c-125">A Unique Resource Name (URN) is a specific type of query expression string that uniquely identifies a single object.</span></span> <span data-ttu-id="15c9c-126">Weitere Informationen finden Sie unter [Query Expressions and Uniform Resource Names](../powershell/query-expressions-and-uniform-resource-names.md).</span><span class="sxs-lookup"><span data-stu-id="15c9c-126">For more information, see [Query Expressions and Uniform Resource Names](../powershell/query-expressions-and-uniform-resource-names.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15c9c-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="15c9c-127">See Also</span></span>  
 [<span data-ttu-id="15c9c-128">SQL Server-PowerShell</span><span class="sxs-lookup"><span data-stu-id="15c9c-128">SQL Server PowerShell</span></span>](../powershell/sql-server-powershell.md)  
  
  
