---
title: Löschen von Benutzern oder Gruppen (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deleting groups [Master Data Services]
- groups [Master Data Services], deleting
- users [Master Data Services], deleting
- deleting users [Master Data Services]
ms.assetid: 0bbf9d2c-b826-48bb-8aa9-9905db6e717f
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: be302bc974994d0f4f17a8e61244065c76fa93ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621545"
---
# <a name="delete-users-or-groups-master-data-services"></a><span data-ttu-id="debbd-102">Löschen von Benutzern oder Gruppen (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="debbd-102">Delete Users or Groups (Master Data Services)</span></span>
  <span data-ttu-id="debbd-103">Löschen Sie Benutzer oder Gruppen, wenn Sie nicht mehr möchten, dass sie auf [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]zugreifen.</span><span class="sxs-lookup"><span data-stu-id="debbd-103">Delete users or groups when you no longer want them to access [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
 <span data-ttu-id="debbd-104">Beachten Sie das folgende Verhalten, wenn Sie Benutzer und Gruppen löschen:</span><span class="sxs-lookup"><span data-stu-id="debbd-104">Note the following behavior when deleting users and groups:</span></span>  
  
-   <span data-ttu-id="debbd-105">Wenn Sie einen Benutzer löschen, der Mitglied einer Gruppe ist, die Zugriff auf [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]hat, kann der Benutzer weiter auf [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] zugreifen, bis Sie den Benutzer aus Active Directory oder der lokalen Gruppe entfernen.</span><span class="sxs-lookup"><span data-stu-id="debbd-105">If you delete a user who is a member of a group that has access to [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], then the user can still access [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] until you remove the user from the Active Directory or local group.</span></span>  
  
-   <span data-ttu-id="debbd-106">Wenn Sie eine Gruppe löschen, werden alle Benutzer aus der Gruppe mit Zugriff auf [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] in der Liste **Benutzer** angezeigt, bis Sie sie löschen.</span><span class="sxs-lookup"><span data-stu-id="debbd-106">If you delete a group, all users from the group who have accessed [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] are displayed in the **Users** list until you delete them.</span></span>  
  
-   <span data-ttu-id="debbd-107">Änderungen an der Sicherheit werden 20 Minuten lang nicht an MDS [!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)] weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="debbd-107">Changes to security are not propagated to the MDS [!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)] for 20 minutes.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="debbd-108">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="debbd-108">Prerequisites</span></span>  
 <span data-ttu-id="debbd-109">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="debbd-109">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="debbd-110">Sie müssen über die Berechtigung verfügen, auf den Funktionsbereich **Benutzer- und Gruppenberechtigungen** zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="debbd-110">You must have permission to access the **Users and Group Permissions** functional area.</span></span>  
  
-   <span data-ttu-id="debbd-111">Sie müssen ein Modelladministrator sein.</span><span class="sxs-lookup"><span data-stu-id="debbd-111">You must be a model administrator.</span></span> <span data-ttu-id="debbd-112">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="debbd-112">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-delete-users-or-groups"></a><span data-ttu-id="debbd-113">So löschen Sie Benutzer oder Gruppen</span><span class="sxs-lookup"><span data-stu-id="debbd-113">To delete users or groups</span></span>  
  
1.  <span data-ttu-id="debbd-114">Klicken Sie in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]auf **Benutzer- und Gruppenberechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="debbd-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **User and Group Permissions**.</span></span>  
  
2.  <span data-ttu-id="debbd-115">Um einen Benutzer zu löschen, bleiben Sie auf der Seite **Benutzer** .</span><span class="sxs-lookup"><span data-stu-id="debbd-115">To delete a user, remain on the **Users** page.</span></span> <span data-ttu-id="debbd-116">Um eine Gruppe zu löschen, klicken Sie auf der Menüleiste auf **Gruppen verwalten**.</span><span class="sxs-lookup"><span data-stu-id="debbd-116">To delete a group, from the menu bar, click **ManageGroups.**</span></span>  
  
3.  <span data-ttu-id="debbd-117">Wählen Sie im Raster die Zeile für den Benutzer oder die Gruppe aus, die Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="debbd-117">In the grid,select the row for the user or group that you want to delete.</span></span>  
  
4.  <span data-ttu-id="debbd-118">Klicken Sie auf **Ausgewählten Benutzer löschen** oder **Ausgewählte Gruppe löschen**.</span><span class="sxs-lookup"><span data-stu-id="debbd-118">Click **Delete selected user** or **Delete selected group**.</span></span>  
  
5.  <span data-ttu-id="debbd-119">Klicken Sie im Bestätigungsdialogfeld auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="debbd-119">On the confirmation dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="debbd-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="debbd-120">See Also</span></span>  
 [<span data-ttu-id="debbd-121">Sicherheit &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="debbd-121">Security &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/security-master-data-services.md)  
  
  
