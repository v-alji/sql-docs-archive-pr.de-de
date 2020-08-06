---
title: Hinzufügen einer Gruppe (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- groups [Master Data Services], adding
- adding groups [Master Data Services]
ms.assetid: c7a88381-3b2c-4af7-9cf7-3a930c1abdee
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 8f9da1d558ccb648af8fbc0dd3b802751bd5ae44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721553"
---
# <a name="add-a-group-master-data-services"></a><span data-ttu-id="61216-102">Hinzufügen einer Gruppe (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="61216-102">Add a Group (Master Data Services)</span></span>
  <span data-ttu-id="61216-103">Fügen Sie der Liste **Gruppen** in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] eine Gruppe hinzu, um damit zu beginnen, Berechtigungen für die Webanwendung zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="61216-103">Add a group to the **Groups** list in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] to begin the process of assigning permission to the Web application.</span></span> <span data-ttu-id="61216-104">Bevor ein Benutzer in der Gruppe auf [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]zugreifen kann, müssen Sie einem oder mehr Funktionsbereichen und Modellobjekten die Gruppenberechtigung geben.</span><span class="sxs-lookup"><span data-stu-id="61216-104">Before a user in the group can access [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], you must give the group permission to one or more functional areas and model objects.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="61216-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="61216-105">Prerequisites</span></span>  
 <span data-ttu-id="61216-106">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="61216-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="61216-107">Sie müssen über die Berechtigung verfügen, auf den Funktionsbereich **Benutzer- und Gruppenberechtigungen** zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="61216-107">You must have permission to access the **Users and Group Permissions** functional area.</span></span>  
  
### <a name="to-add-a-group"></a><span data-ttu-id="61216-108">So fügen Sie eine Gruppe hinzu</span><span class="sxs-lookup"><span data-stu-id="61216-108">To add a group</span></span>  
  
1.  <span data-ttu-id="61216-109">Klicken Sie in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]auf **Benutzer- und Gruppenberechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="61216-109">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **User and Group Permissions**.</span></span>  
  
2.  <span data-ttu-id="61216-110">Klicken Sie auf der Seite **Benutzer** auf der Menüleiste auf **Gruppen verwalten**.</span><span class="sxs-lookup"><span data-stu-id="61216-110">On the **Users** page, from the menu bar, click **Manage Groups**.</span></span>  
  
3.  <span data-ttu-id="61216-111">Klicken Sie auf **Gruppen hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="61216-111">Click **Add groups**.</span></span>  
  
4.  <span data-ttu-id="61216-112">Geben Sie den Namen der Gruppe ein, und stellen Sie diesem den Active Directory-Domänennamen oder den Namen des Servercomputers voran, z.B. *Domäne\Gruppenname* oder *Computer\Gruppenname*.</span><span class="sxs-lookup"><span data-stu-id="61216-112">Type the group's name preceded by the Active Directory domain name or by the server computer's name, as in *domain\group_name* or *computer\group_name*.</span></span>  
  
5.  <span data-ttu-id="61216-113">Klicken Sie optional auf **Namen überprüfen**.</span><span class="sxs-lookup"><span data-stu-id="61216-113">Optionally, click **Check names**.</span></span>  
  
6.  <span data-ttu-id="61216-114">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="61216-114">Click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="61216-115">Wenn der Benutzer zum ersten Mal auf den [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]zugreift, wird der Name des Benutzers zur Benutzerliste des [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="61216-115">When the user first accesses [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], the user's name is added to the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] list of users.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="61216-116">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="61216-116">Next Steps</span></span>  
  
-   [<span data-ttu-id="61216-117">Zuweisen von Berechtigungen für Funktionsbereiche &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="61216-117">Assign Functional Area Permissions &#40;Master Data Services&#41;</span></span>](assign-functional-area-permissions-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="61216-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="61216-118">See Also</span></span>  
 [<span data-ttu-id="61216-119">Sicherheit &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="61216-119">Security &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/security-master-data-services.md)  
  
  
