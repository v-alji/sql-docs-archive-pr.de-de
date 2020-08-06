---
title: Benutzer und Gruppen (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- users [Master Data Services]
- groups [Master Data Services]
- users [Master Data Services], about users
- groups [Master Data Services], about groups
ms.assetid: ed08dd2d-248e-4b68-91d4-e9961cb50eed
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: efad65bf273d58b4f60b98d050a8b99705cb00ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727005"
---
# <a name="users-and-groups-master-data-services"></a><span data-ttu-id="ec804-102">Benutzer und Gruppen (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="ec804-102">Users and Groups (Master Data Services)</span></span>
  <span data-ttu-id="ec804-103">Um auf die [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] -Webanwendung zuzugreifen, muss der Benutzer über ein Windows-Domänenkonto oder ein Konto auf dem Servercomputer verfügen, auf dem [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] installiert ist.</span><span class="sxs-lookup"><span data-stu-id="ec804-103">To access the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application a user must have a Windows domain account or an account on the server computer where [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] is installed.</span></span> <span data-ttu-id="ec804-104">Sie können wie folgt Zugriff auf [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] gewähren:</span><span class="sxs-lookup"><span data-stu-id="ec804-104">To grant access to [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] you can either:</span></span>  
  
-   <span data-ttu-id="ec804-105">Fügen Sie das Benutzerkonto einer Domänengruppe oder lokalen Gruppe hinzu und fügen Sie die Gruppe dann zur Liste der Gruppen in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]hinzu.</span><span class="sxs-lookup"><span data-stu-id="ec804-105">Add the user account to a domain or local group and then add the group to the list of groups in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
-   <span data-ttu-id="ec804-106">Fügen Sie das Benutzerkonto zur Liste der Benutzer in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]hinzu.</span><span class="sxs-lookup"><span data-stu-id="ec804-106">Add the user account to the list of users in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ec804-107">Wenn ein Benutzer zu einer Gruppe gehört, die Zugriff auf [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]hat, wird der Name des Benutzers beim ersten Zugriff auf [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] oder MDS [!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)]automatisch zur Liste der Benutzer hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ec804-107">When a user belongs to a group that has access to [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], the user's name is automatically added to the list of users the first time the user accesses [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] or the MDS [!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)].</span></span>  
  
 <span data-ttu-id="ec804-108">Um innerhalb des Funktionsbereichs **Explorer** der Benutzeroberfläche Aktionen ausführen zu können, müssen der Gruppe bzw. dem Benutzer Zugriff auf den Funktionsbereich **Explorer** gewährt und Berechtigungen für Modellobjekte zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="ec804-108">To take action within the **Explorer** functional area of the UI, the group or user must be assigned access to the **Explorer** functional area and assigned permission to model objects.</span></span>  
  
 <span data-ttu-id="ec804-109">Wenn ein Benutzer oder eine Gruppe Zugriff auf andere Funktionsbereiche benötigt, muss der Benutzer bzw. die Gruppe als Administrator definiert werden.</span><span class="sxs-lookup"><span data-stu-id="ec804-109">If a user or group needs access to other functional areas, the user or group must be an administrator.</span></span> <span data-ttu-id="ec804-110">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ec804-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
## <a name="best-practice"></a><span data-ttu-id="ec804-111">Bewährte Methode</span><span class="sxs-lookup"><span data-stu-id="ec804-111">Best Practice</span></span>  
 <span data-ttu-id="ec804-112">Um die Verwaltung zu vereinfachen, erstellen Sie Gruppen und weisen den Funktionsbereichen und Modellobjekten die einzelnen Gruppenberechtigungen zu.</span><span class="sxs-lookup"><span data-stu-id="ec804-112">To simplify administration, create groups and assign each group permission to functional areas and model objects.</span></span> <span data-ttu-id="ec804-113">Sie können anschließend der Gruppe Benutzer hinzufügen und diese daraus entfernen, ohne auf die [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] -Benutzeroberfläche zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="ec804-113">You can then add and remove users from the groups without accessing the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] UI.</span></span>  
  
 <span data-ttu-id="ec804-114">Weisen Sie einem einzelnen Benutzer keine zusätzlichen Berechtigungen zu und nehmen Sie einen Benutzer nicht in mehrere Gruppen auf, die Zugriff auf [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]haben.</span><span class="sxs-lookup"><span data-stu-id="ec804-114">Do not assign additional permissions to an individual user, and do not include a user in multiple groups that have access to [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span> <span data-ttu-id="ec804-115">Verwenden Sie außerdem keine Hierarchieelementberechtigungen, es sei denn, eine Gruppe soll beschränkten Zugriff auf bestimmte Elemente haben.</span><span class="sxs-lookup"><span data-stu-id="ec804-115">In addition, do not use hierarchy member permissions unless you want a group to have limited access to specific members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec804-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ec804-116">See Also</span></span>  
 <span data-ttu-id="ec804-117">[Benutzer &#40;Master Data Services hinzufügen&#41;](../../2014/master-data-services/add-a-user-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="ec804-117">[Add a User &#40;Master Data Services&#41;](../../2014/master-data-services/add-a-user-master-data-services.md) </span></span>  
 <span data-ttu-id="ec804-118">[Gruppe &#40;Master Data Services hinzufügen&#41;](../../2014/master-data-services/add-a-group-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="ec804-118">[Add a Group &#40;Master Data Services&#41;](../../2014/master-data-services/add-a-group-master-data-services.md) </span></span>  
 <span data-ttu-id="ec804-119">[Löschen von Benutzern oder Gruppen &#40;Master Data Services&#41;](../../2014/master-data-services/delete-users-or-groups-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="ec804-119">[Delete Users or Groups &#40;Master Data Services&#41;](../../2014/master-data-services/delete-users-or-groups-master-data-services.md) </span></span>  
 [<span data-ttu-id="ec804-120">Testen der Berechtigungen eines Benutzers &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="ec804-120">Test a User's Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/test-a-user-s-permissions-master-data-services.md)  
  
  
