---
title: MSSQLSERVER_2519 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2519 (Database Engine error)
ms.assetid: 8dc6ad98-5db8-4c88-8dea-6d455e63b839
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c8577b07586553f4b03714cd31451ac755faf824
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608731"
---
# <a name="mssqlserver_2519"></a><span data-ttu-id="5d7a9-102">MSSQLSERVER_2519</span><span class="sxs-lookup"><span data-stu-id="5d7a9-102">MSSQLSERVER_2519</span></span>
    
## <a name="details"></a><span data-ttu-id="5d7a9-103">Details</span><span class="sxs-lookup"><span data-stu-id="5d7a9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5d7a9-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="5d7a9-104">Product Name</span></span>|<span data-ttu-id="5d7a9-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5d7a9-105">SQL Server</span></span>|  
|<span data-ttu-id="5d7a9-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="5d7a9-106">Event ID</span></span>|<span data-ttu-id="5d7a9-107">2519</span><span class="sxs-lookup"><span data-stu-id="5d7a9-107">2519</span></span>|  
|<span data-ttu-id="5d7a9-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="5d7a9-108">Event Source</span></span>|<span data-ttu-id="5d7a9-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5d7a9-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5d7a9-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="5d7a9-110">Component</span></span>|<span data-ttu-id="5d7a9-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5d7a9-111">SQLEngine</span></span>|  
|<span data-ttu-id="5d7a9-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="5d7a9-112">Symbolic Name</span></span>|<span data-ttu-id="5d7a9-113">DBCC_NO_EXPRESSION_EVALUATOR</span><span class="sxs-lookup"><span data-stu-id="5d7a9-113">DBCC_NO_EXPRESSION_EVALUATOR</span></span>|  
|<span data-ttu-id="5d7a9-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="5d7a9-114">Message Text</span></span>|<span data-ttu-id="5d7a9-115">Berechnete Spalten und benutzerdefinierte Typen können für die Objekt-ID ID O_ID ("O_NAME"-Objekt) nicht überprüft werden, weil die interne Ausdrucksauswertung nicht initialisiert werden konnte.</span><span class="sxs-lookup"><span data-stu-id="5d7a9-115">Computed columns and user-defined types cannot be checked for object ID O_ID (object "O_NAME") because the internal expression evaluator could not be initialized.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5d7a9-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="5d7a9-116">Explanation</span></span>  
 <span data-ttu-id="5d7a9-117">Die Informationsmeldung gibt an, dass DBCC vom Abfrageprozessor kein internes Objekt zur Verfügung gestellt werden konnte, um die Auswertung berechneter Spalten und benutzerdefinierter CLR-Typen (Common Language Runtime) zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="5d7a9-117">This informational message indicates that the query processor could not provide DBCC with an internal object to allow for the evaluation of computed columns and common language runtime (CLR) user-defined types.</span></span> <span data-ttu-id="5d7a9-118">Dies bedeutet, dass berechnete Spalten und benutzerdefinierte CLR-Typen nicht auf ihre Richtigkeit hin überprüft oder verwendet werden, wenn von DBCC die Konsistenz zwischen Indizes und Basistabellen überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="5d7a9-118">This means that computed columns and CLR user-defined types will not be checked for correctness or be used when DBCC checks the consistency between indexes and base tables.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5d7a9-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="5d7a9-119">User Action</span></span>  
 <span data-ttu-id="5d7a9-120">Keine</span><span class="sxs-lookup"><span data-stu-id="5d7a9-120">None</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d7a9-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5d7a9-121">See Also</span></span>  
 [<span data-ttu-id="5d7a9-122">MSSQLSERVER_2518</span><span class="sxs-lookup"><span data-stu-id="5d7a9-122">MSSQLSERVER_2518</span></span>](mssqlserver-2518-database-engine-error.md)  
  
  
