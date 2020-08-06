---
title: Abonnenten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.subscribers.f1
helpviewer_keywords:
- Subscribers [SQL Server replication]
ms.assetid: 43fb2454-c220-4d25-a826-83c332eb00d2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8c5281a53b755bc171cdf96e7856e38ee6a54a1e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615920"
---
# <a name="subscribers"></a><span data-ttu-id="9e837-102">Abonnenten</span><span class="sxs-lookup"><span data-stu-id="9e837-102">Subscribers</span></span>
  <span data-ttu-id="9e837-103">Geben [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Sie die-oder nicht-- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Abonnenten an, die ein Abonnement für die ausgewählte Veröffentlichung erhalten.</span><span class="sxs-lookup"><span data-stu-id="9e837-103">Specify the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or non-[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Subscribers that will receive a subscription to the selected publication.</span></span>  
  
## <a name="options"></a><span data-ttu-id="9e837-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="9e837-104">Options</span></span>  
 <span data-ttu-id="9e837-105">**Abonnenten**</span><span class="sxs-lookup"><span data-stu-id="9e837-105">**Subscribers**</span></span>  
 <span data-ttu-id="9e837-106">Aktivieren Sie das Kontrollkästchen im Raster, um die zugehörige [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] - oder Nicht-[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenquelle als einen Abonnenten für die auf der Seite **Veröffentlichung** ausgewählte Veröffentlichung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9e837-106">Select the check box in the grid to enable the corresponding [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or non-[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data source as a Subscriber to the publication chosen on the **Publication** page.</span></span> <span data-ttu-id="9e837-107">Wenn der Abonnent nicht aufgeführt ist, klicken Sie auf **Abonnent hinzufügen** oder **SQL Server-Abonnenten hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="9e837-107">If the Subscriber is not listed, click **Add Subscriber** or **Add SQL Server Subscriber**.</span></span>  
  
 <span data-ttu-id="9e837-108">**Abonnementdatenbank**</span><span class="sxs-lookup"><span data-stu-id="9e837-108">**Subscription database**</span></span>  
 <span data-ttu-id="9e837-109">Die in dieser Spalte angezeigten Informationen sowie die über die Spalte verfügbaren Aktionen sind vom Typ des in der **Abonnenten** -Spalte aufgeführten Abonnenten abhängig:</span><span class="sxs-lookup"><span data-stu-id="9e837-109">The information displayed in and actions available from this column depend on the type of Subscriber listed in the **Subscribers** column:</span></span>  
  
-   <span data-ttu-id="9e837-110">Wählen Sie für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Abonnenten eine Abonnementdatenbank aus der Liste **Abonnementdatenbank** aus, oder erstellen Sie eine neue Datenbank, indem Sie in derselben Liste den Befehl **Neue Datenbank** auswählen.</span><span class="sxs-lookup"><span data-stu-id="9e837-110">For [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Subscribers, select a subscription database from the **Subscription Database** list or create a new database by selecting the **New database** command from the same list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9e837-111">Wenn Sie den Verleger als einen Abonnenten aktivieren, darf die Abonnementdatenbank nicht mit der Veröffentlichungsdatenbank identisch sein.</span><span class="sxs-lookup"><span data-stu-id="9e837-111">If you are enabling the Publisher as a Subscriber, the subscription database must be different from the publication database.</span></span>  
  
-   <span data-ttu-id="9e837-112">Bei Nicht-[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Abonnenten wird die Abonnementdatenbank nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9e837-112">For non-[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Subscribers, the subscription database is not displayed.</span></span> <span data-ttu-id="9e837-113">Geben Sie im Feld **Datenquellenname** des Dialogfelds **Nicht-SQL Server-Abonnenten hinzufügen** die Datenbank und weitere Verbindungsinformationen an.</span><span class="sxs-lookup"><span data-stu-id="9e837-113">Specify the database, along with other connection information, in the **Data source name** field of the **Add Non-SQL Server** dialog box.</span></span> <span data-ttu-id="9e837-114">Sie rufen dieses Dialogfeld auf, in dem Sie zuerst auf **Abonnent hinzufügen** und anschließend auf **Nicht-SQL Server-Abonnenten hinzufügen**klicken.</span><span class="sxs-lookup"><span data-stu-id="9e837-114">This dialog box is available by clicking **Add Subscriber** and then clicking **Add Non-SQL Server Subscriber**.</span></span>  
  
 <span data-ttu-id="9e837-115">**Abonnent hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="9e837-115">**Add Subscriber**</span></span>  
 <span data-ttu-id="9e837-116">Fügen Sie einen Server zur Liste der Server hinzu, die als Abonnenten aktiviert werden können.</span><span class="sxs-lookup"><span data-stu-id="9e837-116">Add a server to the list of servers that can be enabled as Subscribers.</span></span> <span data-ttu-id="9e837-117">Diese Schaltfläche wird angezeigt, wenn alle der folgenden Bedingungen erfüllt sind:</span><span class="sxs-lookup"><span data-stu-id="9e837-117">This button is displayed when all of the following conditions are true:</span></span>  
  
-   <span data-ttu-id="9e837-118">Die von Ihnen ausgewählte Veröffentlichung ist eine Momentaufnahme- oder Transaktionsveröffentlichung, die keine Updateabonnements unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9e837-118">The publication you selected is a snapshot or transactional publication that does not support updating subscriptions.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9e837-119">Wenn die Veröffentlichung, die Sie abonnieren, über [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Abonnements verfügt und die Veröffentlichung für Nicht-[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Abonnenten noch nicht aktiviert ist, können Sie kein Nicht-[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Abonnement hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9e837-119">If the publication you are subscribing to has [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] subscriptions and the publication is not already enabled for non-[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Subscribers, you cannot add a non-[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] subscription.</span></span>  
  
-   <span data-ttu-id="9e837-120">Das Abonnement ist ein Pushabonnement.</span><span class="sxs-lookup"><span data-stu-id="9e837-120">The subscription is a push subscription.</span></span>  
  
-   <span data-ttu-id="9e837-121">Als Verleger für die ausgewählte Veröffentlichung wird [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] oder höher verwendet.</span><span class="sxs-lookup"><span data-stu-id="9e837-121">The Publisher of the selected publication is [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or later.</span></span>  
  
 <span data-ttu-id="9e837-122">Wenn Sie auf **Abonnent hinzufügen** klicken, wird ein Menü mit zwei Auswahlmöglichkeiten angezeigt: **SQL Server-Abonnenten hinzufügen** und **Nicht-SQL Server-Abonnenten hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="9e837-122">Clicking **Add Subscriber** shows a menu with two choices: **Add SQL Server Subscriber** and **Add Non-SQL Server Subscriber**.</span></span> <span data-ttu-id="9e837-123">Klicken Sie auf **Nicht-SQL Server-Abonnenten hinzufügen** , um einen Oracle- oder IBM DB2-Abonnenten hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="9e837-123">Click **Add Non-SQL Server Subscriber** to add an Oracle or IBM DB2 Subscriber.</span></span>  
  
 <span data-ttu-id="9e837-124">**SQL Server-Abonnenten hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="9e837-124">**Add SQL Server Subscriber**</span></span>  
 <span data-ttu-id="9e837-125">Fügen Sie einen Server zur Liste der Server hinzu, die als Abonnenten aktiviert werden können.</span><span class="sxs-lookup"><span data-stu-id="9e837-125">Add a server to the list of servers that can be enabled as Subscribers.</span></span> <span data-ttu-id="9e837-126">Diese Schaltfläche wird angezeigt, wenn eine oder mehrere der folgenden Bedingungen zutreffen:</span><span class="sxs-lookup"><span data-stu-id="9e837-126">This button is displayed when one or more of the following conditions is true:</span></span>  
  
-   <span data-ttu-id="9e837-127">Die von Ihnen ausgewählte Veröffentlichung ist eine Mergeveröffentlichung oder eine Momentaufnahme- oder Transaktionsveröffentlichung, die Updateabonnements unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9e837-127">The publication you selected is a merge publication, or a snapshot or transactional publication that supports updating subscriptions.</span></span>  
  
-   <span data-ttu-id="9e837-128">Das Abonnement ist ein Pullabonnement.</span><span class="sxs-lookup"><span data-stu-id="9e837-128">The subscription is a pull subscription.</span></span>  
  
-   <span data-ttu-id="9e837-129">Als Verleger für die ausgewählte Veröffentlichung wird eine Version vor [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]verwendet.</span><span class="sxs-lookup"><span data-stu-id="9e837-129">The Publisher of the selected publication is earlier than [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="9e837-130">Bei früheren Versionen wird die Schaltfläche nur angezeigt, wenn eine oder mehrere der folgenden Bedingungen zutreffen:</span><span class="sxs-lookup"><span data-stu-id="9e837-130">For earlier versions, the button is displayed only if one or more of the following conditions is true:</span></span>  
  
    -   <span data-ttu-id="9e837-131">Sie sind Mitglied der festen Serverrolle **sysadmin** auf dem Verleger.</span><span class="sxs-lookup"><span data-stu-id="9e837-131">You are a member of the **sysadmin** fixed server role at the Publisher.</span></span>  
  
    -   <span data-ttu-id="9e837-132">Der Abonnent wurde über die Seite **Abonnenten** des Dialogfelds **Verlegereigenschaften** hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="9e837-132">The Subscriber has been added on the **Subscribers** page of the **Publisher Properties** dialog box.</span></span>  
  
    -   <span data-ttu-id="9e837-133">Die Veröffentlichung lässt anonyme Abonnements zu.</span><span class="sxs-lookup"><span data-stu-id="9e837-133">The publication allows anonymous subscriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e837-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9e837-134">See Also</span></span>  
 <span data-ttu-id="9e837-135">[Create a Pull Subscription](create-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="9e837-135">[Create a Pull Subscription](create-a-pull-subscription.md) </span></span>  
 <span data-ttu-id="9e837-136">[Create a Push Subscription](create-a-push-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="9e837-136">[Create a Push Subscription](create-a-push-subscription.md) </span></span>  
 <span data-ttu-id="9e837-137">[Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md) </span><span class="sxs-lookup"><span data-stu-id="9e837-137">[Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md) </span></span>  
 [<span data-ttu-id="9e837-138">Abonnieren von Veröffentlichungen</span><span class="sxs-lookup"><span data-stu-id="9e837-138">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
