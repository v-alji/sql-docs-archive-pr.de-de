---
title: Überlappende Benutzer- und Gruppenberechtigungen (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- users [Master Data Services], resolving permissions
- permissions [Master Data Services], user and group overlaps
- groups [Master Data Services], resolving permissions
ms.assetid: 31c3cf7d-17d4-4474-b6a7-ffcb9fc45b37
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 7044bf6260170cbc598719ec204ddb6f861f6301
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698360"
---
# <a name="overlapping-user-and-group-permissions-master-data-services"></a><span data-ttu-id="b38d8-102">Überlappende Benutzer- und Gruppenberechtigungen (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="b38d8-102">Overlapping User and Group Permissions (Master Data Services)</span></span>
  <span data-ttu-id="b38d8-103">Benutzerberechtigungen basieren auf:</span><span class="sxs-lookup"><span data-stu-id="b38d8-103">A user's permissions are based on:</span></span>  
  
-   <span data-ttu-id="b38d8-104">Berechtigungen aus Gruppenmitgliedschaften</span><span class="sxs-lookup"><span data-stu-id="b38d8-104">Permissions from group memberships.</span></span>  
  
-   <span data-ttu-id="b38d8-105">Dem Benutzer explizit zugewiesenen Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="b38d8-105">Permissions assigned explicitly to the user.</span></span>  
  
 <span data-ttu-id="b38d8-106">Wenn ein Benutzer mehreren Gruppen angehört und diese Gruppen Zugriff auf Master Data Manager haben, gelten die folgenden Regeln:</span><span class="sxs-lookup"><span data-stu-id="b38d8-106">If a user is a member of multiple groups, and those groups have access to Master Data Manager, the following rules apply:</span></span>  
  
-   <span data-ttu-id="b38d8-107">Mit**Verweigern** werden alle anderen Berechtigungen überschrieben.</span><span class="sxs-lookup"><span data-stu-id="b38d8-107">**Deny** overrides all other permissions.</span></span>  
  
-   <span data-ttu-id="b38d8-108">Das **Update** über **schreibt schreibgeschützt.**</span><span class="sxs-lookup"><span data-stu-id="b38d8-108">**Update** overrides **Read-only**.</span></span>  
  
 <span data-ttu-id="b38d8-109">Diese Regeln gelten sowohl für die Registerkarte **Modelle** als auch für die Registerkarte **Hierarchieelemente** .</span><span class="sxs-lookup"><span data-stu-id="b38d8-109">These rules apply to both the **Models** and **Hierarchy Members** tabs.</span></span> <span data-ttu-id="b38d8-110">Berechtigungen werden für jede Registerkarte aufgelöst und dann kombiniert.</span><span class="sxs-lookup"><span data-stu-id="b38d8-110">Permissions are resolved for each tab and then combined.</span></span> <span data-ttu-id="b38d8-111">Weitere Informationen finden Sie unter [Vorgehensweise: Festlegen von Berechtigungen &#40;Master Data Services&#41;](how-permissions-are-determined-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="b38d8-111">For more information, see [How Permissions Are Determined &#40;Master Data Services&#41;](how-permissions-are-determined-master-data-services.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b38d8-112">Sie können die Auflösung überlappender Benutzer- und Gruppenberechtigungen in der Benutzeroberfläche anzeigen.</span><span class="sxs-lookup"><span data-stu-id="b38d8-112">You can view the resolution of user and group overlapping permissions in the user interface.</span></span> <span data-ttu-id="b38d8-113">Sowohl die Registerkarte **Modelle** als auch die Registerkarte **Hierarchieelemente** verfügt über eine Dropdownliste, aus der Sie **Effektiv** auswählen können, um effektive Berechtigungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b38d8-113">Both the **Models** and **Hierarchy Members** tab have a drop-down list from which you can choose **Effective** to view effective permissions.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="b38d8-114">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="b38d8-114">Example 1</span></span>  
 <span data-ttu-id="b38d8-115">![mds_conc_user_group_ex_1](../../2014/master-data-services/media/mds-conc-user-group-ex-1.gif "mds_conc_user_group_ex_1")</span><span class="sxs-lookup"><span data-stu-id="b38d8-115">![mds_conc_user_group_ex_1](../../2014/master-data-services/media/mds-conc-user-group-ex-1.gif "mds_conc_user_group_ex_1")</span></span>  
  
 <span data-ttu-id="b38d8-116">Der Benutzer gehört der Gruppe 1 und der Gruppe 2 an.</span><span class="sxs-lookup"><span data-stu-id="b38d8-116">The user belongs to Group 1 and Group 2.</span></span>  
  
 <span data-ttu-id="b38d8-117">Der **Benutzer verfügt für** die Product-Entität über die Berechtigung schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="b38d8-117">The user has **Read-only** permission to the Product entity.</span></span>  
  
 <span data-ttu-id="b38d8-118">Gruppe 1 verfügt für die Entität „Product“ über die Berechtigung **Aktualisieren** .</span><span class="sxs-lookup"><span data-stu-id="b38d8-118">Group 1 has **Update** permission to the Product entity.</span></span>  
  
 <span data-ttu-id="b38d8-119">Gruppe **2 verfügt für** die Product-Entität über die Berechtigung schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="b38d8-119">Group 2 has **Read-only** permission to the Product entity.</span></span>  
  
 <span data-ttu-id="b38d8-120">Ergebnis: Die effektive Berechtigung des Benutzers für die Entität „Product“ lautet **Aktualisieren** .</span><span class="sxs-lookup"><span data-stu-id="b38d8-120">Result: The user's effective permission is **Update** to the Product entity.</span></span>  
  
## <a name="example-2"></a><span data-ttu-id="b38d8-121">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="b38d8-121">Example 2</span></span>  
 <span data-ttu-id="b38d8-122">![mds_conc_user_group_ex_2](../../2014/master-data-services/media/mds-conc-user-group-ex-2.gif "mds_conc_user_group_ex_2")</span><span class="sxs-lookup"><span data-stu-id="b38d8-122">![mds_conc_user_group_ex_2](../../2014/master-data-services/media/mds-conc-user-group-ex-2.gif "mds_conc_user_group_ex_2")</span></span>  
  
 <span data-ttu-id="b38d8-123">Der Benutzer gehört der Gruppe 1 und der Gruppe 2 an.</span><span class="sxs-lookup"><span data-stu-id="b38d8-123">The user belongs to Group 1 and Group 2.</span></span>  
  
 <span data-ttu-id="b38d8-124">Der **Benutzer verfügt für** die Product-Entität über die Berechtigung schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="b38d8-124">The user has **Read-only** permission to the Product entity.</span></span>  
  
 <span data-ttu-id="b38d8-125">Gruppe 1 verfügt für die Entität „Product“ über die Berechtigung **Aktualisieren** .</span><span class="sxs-lookup"><span data-stu-id="b38d8-125">Group 1 has **Update** permission to Product entity.</span></span>  
  
 <span data-ttu-id="b38d8-126">Gruppe 2 verfügt für die Entität „Product“ über die Berechtigung **Verweigern** .</span><span class="sxs-lookup"><span data-stu-id="b38d8-126">Group 2 has **Deny** permission to the Product entity.</span></span>  
  
 <span data-ttu-id="b38d8-127">Ergebnis: Die effektive Berechtigung des Benutzers für die Entität „Product“ lautet **Verweigern** .</span><span class="sxs-lookup"><span data-stu-id="b38d8-127">Result: The user's effective permission is **Deny** to the Product entity.</span></span>  
  
## <a name="example-3"></a><span data-ttu-id="b38d8-128">Beispiel 3</span><span class="sxs-lookup"><span data-stu-id="b38d8-128">Example 3</span></span>  
 <span data-ttu-id="b38d8-129">![mds_conc_user_group_ex_3](../../2014/master-data-services/media/mds-conc-user-group-ex-3.gif "mds_conc_user_group_ex_3")</span><span class="sxs-lookup"><span data-stu-id="b38d8-129">![mds_conc_user_group_ex_3](../../2014/master-data-services/media/mds-conc-user-group-ex-3.gif "mds_conc_user_group_ex_3")</span></span>  
  
 <span data-ttu-id="b38d8-130">Der Benutzer gehört der Gruppe 1 und der Gruppe 2 an.</span><span class="sxs-lookup"><span data-stu-id="b38d8-130">The user belongs to Group 1 and Group 2.</span></span>  
  
 <span data-ttu-id="b38d8-131">Der Benutzer verfügt für eine Gruppe von Elementen unter einem Hierarchieknoten über die Berechtigung **Aktualisieren** .</span><span class="sxs-lookup"><span data-stu-id="b38d8-131">The user has **Update** permission to a group of members in a hierarchy node.</span></span>  
  
 <span data-ttu-id="b38d8-132">Gruppe **1 verfügt für** eine Gruppe von Elementen in einem Hierarchie Knoten über die Berechtigung schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="b38d8-132">Group 1 has **Read-only** permission to a group of members in a hierarchy node.</span></span>  
  
 <span data-ttu-id="b38d8-133">Gruppe **2 verfügt für** eine Gruppe von Elementen in einem Hierarchie Knoten über die Berechtigung schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="b38d8-133">Group 2 has **Read-only** permission to a group of members in a hierarchy node.</span></span>  
  
 <span data-ttu-id="b38d8-134">Ergebnis: Die effektive Berechtigung des Benutzers für die Elemente lautet **Aktualisieren** .</span><span class="sxs-lookup"><span data-stu-id="b38d8-134">Result: The user's effective permission is **Update** to the members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b38d8-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b38d8-135">See Also</span></span>  
 <span data-ttu-id="b38d8-136">[Wie Berechtigungen &#40;Master Data Services bestimmt werden&#41;](how-permissions-are-determined-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="b38d8-136">[How Permissions Are Determined &#40;Master Data Services&#41;](how-permissions-are-determined-master-data-services.md) </span></span>  
 [<span data-ttu-id="b38d8-137">Überlappende Modell- und Elementberechtigungen &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="b38d8-137">Overlapping Model and Member Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/overlapping-model-and-member-permissions-master-data-services.md)  
  
  
