---
title: MSSQL_ENG014157 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014157 error
ms.assetid: 1a0890cf-d977-43e0-a2ba-9c5ff1a8f856
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0682d740d82c995d64427f56aabce24b8a48ca65
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616496"
---
# <a name="mssql_eng014157"></a><span data-ttu-id="52212-102">MSSQL_ENG014157</span><span class="sxs-lookup"><span data-stu-id="52212-102">MSSQL_ENG014157</span></span>
    
## <a name="message-details"></a><span data-ttu-id="52212-103">Meldungsdetails</span><span class="sxs-lookup"><span data-stu-id="52212-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="52212-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="52212-104">Product Name</span></span>|<span data-ttu-id="52212-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="52212-105">SQL Server</span></span>|  
|<span data-ttu-id="52212-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="52212-106">Event ID</span></span>|<span data-ttu-id="52212-107">14157</span><span class="sxs-lookup"><span data-stu-id="52212-107">14157</span></span>|  
|<span data-ttu-id="52212-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="52212-108">Event Source</span></span>|<span data-ttu-id="52212-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="52212-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="52212-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="52212-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="52212-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="52212-111">Symbolic Name</span></span>||  
|<span data-ttu-id="52212-112">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="52212-112">Message Text</span></span>|<span data-ttu-id="52212-113">Das Abonnement des Abonnenten '%1!s!' für die %2!s!-Veröffentlichung ist abgelaufen und wurde gelöscht.</span><span class="sxs-lookup"><span data-stu-id="52212-113">The subscription created by Subscriber '%s' to publication '%s' has expired and has been dropped.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="52212-114">Erklärung</span><span class="sxs-lookup"><span data-stu-id="52212-114">Explanation</span></span>  
 <span data-ttu-id="52212-115">Ein Abonnent muss innerhalb der angegebenen Beibehaltungsdauer für die Veröffentlichung mit dem Verleger synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="52212-115">A Subscriber must synchronize with the Publisher within the time specified in the publication retention period.</span></span> <span data-ttu-id="52212-116">Falls ein Abonnent nicht innerhalb dieses Zeitraums synchronisiert wird, läuft das Abonnement ab.</span><span class="sxs-lookup"><span data-stu-id="52212-116">If a Subscriber does not synchronize within this period, the subscription expires.</span></span> <span data-ttu-id="52212-117">Weitere Informationen finden Sie unter [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span><span class="sxs-lookup"><span data-stu-id="52212-117">For more information, see [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="52212-118">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="52212-118">User Action</span></span>  
 <span data-ttu-id="52212-119">Das Abonnement muss neu erstellt und initialisiert werden, damit der Abonnent wieder Datenänderungen empfangen kann:</span><span class="sxs-lookup"><span data-stu-id="52212-119">The subscription must be re-created and initialized before the Subscriber can begin receiving data changes again:</span></span>  
  
-   <span data-ttu-id="52212-120">Weitere Informationen zum Erstellen von Abonnements finden Sie unter [Abonnieren von Veröffentlichungen](subscribe-to-publications.md).</span><span class="sxs-lookup"><span data-stu-id="52212-120">For information about creating subscriptions, see [Subscribe to Publications](subscribe-to-publications.md).</span></span>  
  
-   <span data-ttu-id="52212-121">Informationen zum Initialisieren von Abonnements finden Sie unter [Initialisieren eines Abonnements](initialize-a-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="52212-121">For information about initializing subscriptions, see [Initialize a Subscription](initialize-a-subscription.md).</span></span>  
  
 <span data-ttu-id="52212-122">Wenn die Abonnementdatenbank Änderungen enthält, die noch nicht mit dem Verleger synchronisiert wurden, können Sie mit [tablediff Utility](../../tools/tablediff-utility.md) (Hilfsprogramm) ermitteln, welche Zeilen in der Veröffentlichungs- bzw. Abonnementdatenbanken unterschiedlich sind.</span><span class="sxs-lookup"><span data-stu-id="52212-122">If the subscription database contains changes that have not been synchronized with the Publisher, you can use the [tablediff Utility](../../tools/tablediff-utility.md) to determine which rows are different in the publication and subscription databases.</span></span>  
  
 <span data-ttu-id="52212-123">Sie können die Beibehaltungsdauer für die Veröffentlichung erhöhen, um zu vermeiden, dass Abonnements ablaufen.</span><span class="sxs-lookup"><span data-stu-id="52212-123">You can increase the publication retention period to avoid having subscriptions expire.</span></span> <span data-ttu-id="52212-124">Geben Sie keinen zu hohen Wert ein, da dies zur Speicherung von mehr Daten und Metadaten und damit einer Beeinträchtigung der Leistung führen kann.</span><span class="sxs-lookup"><span data-stu-id="52212-124">Use caution in setting a high value, because this can result in more data and metadata being stored, which affects performance.</span></span> <span data-ttu-id="52212-125">Weitere Informationen finden Sie unter [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span><span class="sxs-lookup"><span data-stu-id="52212-125">For more information, see [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52212-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="52212-126">See Also</span></span>  
 [<span data-ttu-id="52212-127">Fehler- und Ereignisreferenz &#40;Replikation&#41;</span><span class="sxs-lookup"><span data-stu-id="52212-127">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
