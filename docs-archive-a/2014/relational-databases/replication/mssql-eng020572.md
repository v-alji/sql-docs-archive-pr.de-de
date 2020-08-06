---
title: MSSQL_ENG020572 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG020572 error
ms.assetid: 636566db-ffcf-4109-8c11-15b8c7cb9cd9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5762f160e119012f4fdc0ca1a205ba0ecf690378
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622586"
---
# <a name="mssql_eng020572"></a><span data-ttu-id="ddf06-102">MSSQL_ENG020572</span><span class="sxs-lookup"><span data-stu-id="ddf06-102">MSSQL_ENG020572</span></span>
    
## <a name="message-details"></a><span data-ttu-id="ddf06-103">Meldungsdetails</span><span class="sxs-lookup"><span data-stu-id="ddf06-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ddf06-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="ddf06-104">Product Name</span></span>|<span data-ttu-id="ddf06-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ddf06-105">SQL Server</span></span>|  
|<span data-ttu-id="ddf06-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="ddf06-106">Event ID</span></span>|<span data-ttu-id="ddf06-107">20572</span><span class="sxs-lookup"><span data-stu-id="ddf06-107">20572</span></span>|  
|<span data-ttu-id="ddf06-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="ddf06-108">Event Source</span></span>|<span data-ttu-id="ddf06-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ddf06-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ddf06-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="ddf06-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="ddf06-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="ddf06-111">Symbolic Name</span></span>||  
|<span data-ttu-id="ddf06-112">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="ddf06-112">Message Text</span></span>|<span data-ttu-id="ddf06-113">Das Abonnement des Abonnenten '%s' für den '%s'-Artikel in der '%s'-Veröffentlichung wurde nach einem Datenüberprüfungsfehler neu initialisiert.</span><span class="sxs-lookup"><span data-stu-id="ddf06-113">Subscriber '%s' subscription to article '%s' in publication '%s' has been reinitialized after a validation failure.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ddf06-114">Erklärung</span><span class="sxs-lookup"><span data-stu-id="ddf06-114">Explanation</span></span>  
 <span data-ttu-id="ddf06-115">Die Daten des Abonnenten wurden gegen die Daten des Verlegers abgeglichen, und es wurde keine Übereinstimmung der Daten festgestellt. Daher konnte die Überprüfung nicht erfolgreich abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="ddf06-115">The data at the Subscriber was validated against the data at the Publisher, and the data did not match; therefore validation failed.</span></span> <span data-ttu-id="ddf06-116">Bei der Angabe zur Ausführung einer Überprüfung haben Sie die Option aktiviert, dass im Falle eines Fehlers bei der Überprüfung eine erneute Initialisierung des Abonnements erfolgen soll.</span><span class="sxs-lookup"><span data-stu-id="ddf06-116">When you specified that validation should be performed, you selected the option that a subscription should be reinitialized if validation failed.</span></span> <span data-ttu-id="ddf06-117">Für eine erneute Initialisierung des Abonnements muss eine neue Momentaufnahme auf dem Abonnenten angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="ddf06-117">Reinitializing a subscription involves applying a new snapshot at the Subscriber.</span></span> <span data-ttu-id="ddf06-118">Weitere Informationen zur Überprüfung finden Sie unter [Validate Replicated Data](validate-data-at-the-subscriber.md).</span><span class="sxs-lookup"><span data-stu-id="ddf06-118">For more information about validation, see [Validate Replicated Data](validate-data-at-the-subscriber.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ddf06-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="ddf06-119">User Action</span></span>  
 <span data-ttu-id="ddf06-120">Die Daten auf dem Verleger und auf dem Abonnenten stimmen überein, nachdem die neue Momentaufnahme auf dem Abonnenten angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="ddf06-120">Data at the Publisher and Subscriber will match after the new snapshot is applied at the Subscriber.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddf06-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ddf06-121">See Also</span></span>  
 [<span data-ttu-id="ddf06-122">Fehler- und Ereignisreferenz &#40;Replikation&#41;</span><span class="sxs-lookup"><span data-stu-id="ddf06-122">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
