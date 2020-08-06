---
title: MSSQLSERVER_2518 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2518 (Database Engine error)
ms.assetid: 54a13abc-4c33-43f0-b55d-e2e74a1381c8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5f5517458c1014d7830c4813b95e1120bef452e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616087"
---
# <a name="mssqlserver_2518"></a><span data-ttu-id="86ee2-102">MSSQLSERVER_2518</span><span class="sxs-lookup"><span data-stu-id="86ee2-102">MSSQLSERVER_2518</span></span>
    
## <a name="details"></a><span data-ttu-id="86ee2-103">Details</span><span class="sxs-lookup"><span data-stu-id="86ee2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="86ee2-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="86ee2-104">Product Name</span></span>|<span data-ttu-id="86ee2-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="86ee2-105">SQL Server</span></span>|  
|<span data-ttu-id="86ee2-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="86ee2-106">Event ID</span></span>|<span data-ttu-id="86ee2-107">2518</span><span class="sxs-lookup"><span data-stu-id="86ee2-107">2518</span></span>|  
|<span data-ttu-id="86ee2-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="86ee2-108">Event Source</span></span>|<span data-ttu-id="86ee2-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="86ee2-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="86ee2-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="86ee2-110">Component</span></span>|<span data-ttu-id="86ee2-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="86ee2-111">SQLEngine</span></span>|  
|<span data-ttu-id="86ee2-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="86ee2-112">Symbolic Name</span></span>|<span data-ttu-id="86ee2-113">DBCC_NO_EXPRESSION_EVAL_CLR_DISABLED</span><span class="sxs-lookup"><span data-stu-id="86ee2-113">DBCC_NO_EXPRESSION_EVAL_CLR_DISABLED</span></span>|  
|<span data-ttu-id="86ee2-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="86ee2-114">Message Text</span></span>|<span data-ttu-id="86ee2-115">Objekt-ID O_ID (Objekt "O_NAME"): Berechnete Spalten und benutzerdefinierte Typen können für dieses Objekt nicht überprüft werden, da die Common Language Runtime (CLR) deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="86ee2-115">Object ID O_ID (object "O_NAME"): Computed columns and user-defined types cannot be checked for this object because the common language runtime (CLR) is disabled.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="86ee2-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="86ee2-116">Explanation</span></span>  
 <span data-ttu-id="86ee2-117">Diese Informationsmeldung gibt an, dass der Abfrageprozessor DBCC kein internes Objekt bereitstellen konnte, um die Auswertung berechneter Spalten und CLR-benutzerdefinierter Typen (Common Language Runtime) zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="86ee2-117">This informational message indicates that the query processor could not provide DBCC with an internal object to allow for computed columns and common language runtime (CLR) user-defined types to be evaluated.</span></span> <span data-ttu-id="86ee2-118">Dieses Problem ist aufgetreten, weil eine der Spalten CLR beinhaltet, aber CLR nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="86ee2-118">This problem occurred because one of the columns involved the CLR, but the CLR is not enabled.</span></span> <span data-ttu-id="86ee2-119">Das interne Objekt deckt alle Spalten ab.</span><span class="sxs-lookup"><span data-stu-id="86ee2-119">The internal object covers all columns.</span></span> <span data-ttu-id="86ee2-120">Daher verhindert das Unvermögen, eine einzelne Spalte auszuwerten, das Erstellen des internen Objekts.</span><span class="sxs-lookup"><span data-stu-id="86ee2-120">Therefore, the inability to evaluate a single column prevents creating the internal object.</span></span> <span data-ttu-id="86ee2-121">Das bedeutet, dass berechnete Spalten nicht auf Richtigkeit überprüft werden oder verwendet werden, wenn DBCC die Konsistenz zwischen Indizes und Basistabellen überprüft.</span><span class="sxs-lookup"><span data-stu-id="86ee2-121">This means that computed columns will not be checked for correctness or be used when DBCC checks the consistency between indexes and base tables.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="86ee2-122">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="86ee2-122">User Action</span></span>  
 <span data-ttu-id="86ee2-123">Aktivieren Sie CLR, und führen Sie die DBCC-Anweisung erneut aus.</span><span class="sxs-lookup"><span data-stu-id="86ee2-123">Enable CLR and rerun the DBCC statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86ee2-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="86ee2-124">See Also</span></span>  
 [<span data-ttu-id="86ee2-125">Aktivieren der CLR-Integration</span><span class="sxs-lookup"><span data-stu-id="86ee2-125">Enabling CLR Integration</span></span>](../clr-integration/clr-integration-enabling.md)  
  
  
