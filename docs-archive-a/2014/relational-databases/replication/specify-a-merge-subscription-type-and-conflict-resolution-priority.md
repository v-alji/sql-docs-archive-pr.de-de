---
title: Angeben eines Mergeabonnementtyps und einer Konflikt Lösungs Priorität (SQL Server Management Studio) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- merge replication conflict resolution [SQL Server replication], merge subscription resolvers
- conflict resolution [SQL Server replication], merge replication
ms.assetid: 2b828d83-2341-4924-b92a-4f81a22246c0
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a19ae6246fe59308283fbaf2f35e2c49f96b140c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726889"
---
# <a name="specify-a-merge-subscription-type-and-conflict-resolution-priority-sql-server-management-studio"></a><span data-ttu-id="b2057-102">Angeben eines Mergeabonnementtyps und einer Konfliktlösungspriorität (Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="b2057-102">Specify a Merge Subscription Type and Conflict Resolution Priority (SQL Server Management Studio)</span></span>
  <span data-ttu-id="b2057-103">Auf der Seite **Abonnementtyp** des Assistenten für neue Abonnements können Sie einen Mergeabonnementtyp und eine Konfliktlösungspriorität angeben.</span><span class="sxs-lookup"><span data-stu-id="b2057-103">Specify a merge subscription type and conflict resolution priority on the **Subscription Type** page of the New Subscription Wizard.</span></span> <span data-ttu-id="b2057-104">Weitere Informationen zum Verwenden dieses Assistenten finden Sie unter [Create a Pull Subscription](create-a-pull-subscription.md) und [Create a Push Subscription](create-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="b2057-104">For more information about using this wizard, see [Create a Pull Subscription](create-a-pull-subscription.md) and [Create a Push Subscription](create-a-push-subscription.md).</span></span>  
  
 <span data-ttu-id="b2057-105">Der Abonnementtyp kann nicht geändert werden, nachdem ein Abonnement erstellt wurde, aber die Priorität kann im Dialogfeld **Abonnementeigenschaften – \<Publisher>: \<PublicationDatabase>** für den Serverabonnementtyp geändert werden.</span><span class="sxs-lookup"><span data-stu-id="b2057-105">Subscription type cannot be modified after a subscription is created, but priority can be modified for the server subscription type in the **Subscription Properties - \<Publisher>: \<PublicationDatabase>** dialog box.</span></span> <span data-ttu-id="b2057-106">Weitere Informationen zum Zugreifen auf dieses Dialogfeld finden Sie unter [View and Modify Push Subscription Properties](view-and-modify-push-subscription-properties.md) und [View and Modify Pull Subscription Properties](view-and-modify-pull-subscription-properties.md).</span><span class="sxs-lookup"><span data-stu-id="b2057-106">For more information about accessing this dialog box, see [View and Modify Push Subscription Properties](view-and-modify-push-subscription-properties.md) and [View and Modify Pull Subscription Properties](view-and-modify-pull-subscription-properties.md).</span></span>  
  
### <a name="to-specify-a-merge-subscription-type-and-conflict-resolution-priority"></a><span data-ttu-id="b2057-107">So geben Sie einen Mergeabonnementtyp und eine Konfliktlösungspriorität an</span><span class="sxs-lookup"><span data-stu-id="b2057-107">To specify a merge subscription type and conflict resolution priority</span></span>  
  
1.  <span data-ttu-id="b2057-108">Wählen Sie auf der Seite **Abonnementtyp** des Assistenten für neue Abonnements für die Option **Abonnementtyp** entweder **Client** oder **Server** aus.</span><span class="sxs-lookup"><span data-stu-id="b2057-108">On the **Subscription Type** page of the New Subscription Wizard, select **Client** or **Server** for the **Subscription Type** option.</span></span>  
  
2.  <span data-ttu-id="b2057-109">Falls Sie den Abonnementtyp **Server**auswählen, geben Sie zudem einen Wert (0,00 bis 99,99) für die Option **Priorität für Konfliktlösung** ein.</span><span class="sxs-lookup"><span data-stu-id="b2057-109">If you select a subscription type of **Server**, also enter a value (0.00 to 99.99) for the **Priority for Conflict Resolution** option.</span></span>  
  
### <a name="to-modify-the-conflict-resolution-priority"></a><span data-ttu-id="b2057-110">So ändern Sie die Konfliktlösungspriorität</span><span class="sxs-lookup"><span data-stu-id="b2057-110">To modify the conflict resolution priority</span></span>  
  
1.  <span data-ttu-id="b2057-111">Wählen Sie unter **Abonnementeigenschaften – \<Publisher>: \<PublicationDatabase>** im Verleger einen Wert (0,00 bis 99,99) für die Option **Priorität** aus.</span><span class="sxs-lookup"><span data-stu-id="b2057-111">In the **Subscription Properties - \<Publisher>: \<PublicationDatabase>** at the Publisher, enter a value (0.00 to 99.99) for the **Priority** option.</span></span>  
  
2.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b2057-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b2057-112">See Also</span></span>  
 <span data-ttu-id="b2057-113">[Erweiterte Konflikterkennung und -lösung der Mergereplikation](merge/advanced-merge-replication-conflict-detection-and-resolution.md) </span><span class="sxs-lookup"><span data-stu-id="b2057-113">[Advanced Merge Replication Conflict Detection and Resolution](merge/advanced-merge-replication-conflict-detection-and-resolution.md) </span></span>  
 [<span data-ttu-id="b2057-114">Abonnieren von Veröffentlichungen</span><span class="sxs-lookup"><span data-stu-id="b2057-114">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
