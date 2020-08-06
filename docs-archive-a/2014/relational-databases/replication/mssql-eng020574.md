---
title: MSSQL_ENG020574 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG02574 error
ms.assetid: 4e98f8de-287c-4090-81ee-dc8f80dfa6a1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8e224e9a87d40fa826a05c669216649c45185037
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622585"
---
# <a name="mssql_eng020574"></a><span data-ttu-id="a7bc9-102">MSSQL_ENG020574</span><span class="sxs-lookup"><span data-stu-id="a7bc9-102">MSSQL_ENG020574</span></span>
    
## <a name="message-details"></a><span data-ttu-id="a7bc9-103">Meldungsdetails</span><span class="sxs-lookup"><span data-stu-id="a7bc9-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a7bc9-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="a7bc9-104">Product Name</span></span>|<span data-ttu-id="a7bc9-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a7bc9-105">SQL Server</span></span>|  
|<span data-ttu-id="a7bc9-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="a7bc9-106">Event ID</span></span>|<span data-ttu-id="a7bc9-107">20574</span><span class="sxs-lookup"><span data-stu-id="a7bc9-107">20574</span></span>|  
|<span data-ttu-id="a7bc9-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="a7bc9-108">Event Source</span></span>|<span data-ttu-id="a7bc9-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a7bc9-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a7bc9-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="a7bc9-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="a7bc9-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="a7bc9-111">Symbolic Name</span></span>||  
|<span data-ttu-id="a7bc9-112">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="a7bc9-112">Message Text</span></span>|<span data-ttu-id="a7bc9-113">Fehler bei der Datenüberprüfung für das Abonnement des Abonnenten '%s' für den '%s'-Artikel in der '%s'-Veröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="a7bc9-113">Subscriber '%s' subscription to article '%s' in publication '%s' failed data validation.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a7bc9-114">Erklärung</span><span class="sxs-lookup"><span data-stu-id="a7bc9-114">Explanation</span></span>  
 <span data-ttu-id="a7bc9-115">Die Daten des Abonnenten wurden gegen die Daten des Verlegers abgeglichen, und es wurde keine Übereinstimmung der Daten festgestellt. Daher konnte die Überprüfung nicht erfolgreich abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="a7bc9-115">The data at the Subscriber was validated against the data at the Publisher, and the data did not match; therefore validation failed.</span></span> <span data-ttu-id="a7bc9-116">Weitere Informationen zur Überprüfung finden Sie unter [Validate Replicated Data](validate-data-at-the-subscriber.md).</span><span class="sxs-lookup"><span data-stu-id="a7bc9-116">For more information about validation, see [Validate Replicated Data](validate-data-at-the-subscriber.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a7bc9-117">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="a7bc9-117">User Action</span></span>  
 <span data-ttu-id="a7bc9-118">Folgendes Vorgehen wird empfohlen:</span><span class="sxs-lookup"><span data-stu-id="a7bc9-118">We recommend that you do the following:</span></span>  
  
-   <span data-ttu-id="a7bc9-119">Ermitteln Sie den Grund für den Fehler bei der Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="a7bc9-119">Determine why validation failed.</span></span>  
  
-   <span data-ttu-id="a7bc9-120">Beheben Sie das zugrunde liegende Problem, das zu dem Fehler geführt hat.</span><span class="sxs-lookup"><span data-stu-id="a7bc9-120">Correct the underlying issue that caused the failure.</span></span>  
  
-   <span data-ttu-id="a7bc9-121">Stellen Sie die Konvergenz der Daten her, indem Sie das Abonnement erneut initialisieren oder eine andere geeignete Methode verwenden.</span><span class="sxs-lookup"><span data-stu-id="a7bc9-121">Bring the data into convergence by reinitializing the subscription or through another method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7bc9-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a7bc9-122">See Also</span></span>  
 [<span data-ttu-id="a7bc9-123">Fehler- und Ereignisreferenz &#40;Replikation&#41;</span><span class="sxs-lookup"><span data-stu-id="a7bc9-123">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
