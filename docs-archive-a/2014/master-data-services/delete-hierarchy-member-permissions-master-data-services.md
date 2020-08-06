---
title: Löschen von Hierarchieelementberechtigungen (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deleting member permissions [Master Data Services]
- members [Master Data Services], deleting permissions
- permissions [Master Data Services], deleting member permissions
ms.assetid: 7f22d5e2-70c1-422c-99c2-e995a47d812a
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 8b6e7fbfc4379733d5cb809ce4d46d2c12d05a48
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699956"
---
# <a name="delete-hierarchy-member-permissions-master-data-services"></a><span data-ttu-id="290e4-102">Löschen von Hierarchieelementberechtigungen (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="290e4-102">Delete Hierarchy Member Permissions (Master Data Services)</span></span>
  <span data-ttu-id="290e4-103">Löschen Sie in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]Modellobjektberechtigungen, um erfolgte Zuweisungen zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="290e4-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], delete model object permissions to remove any assignments that have been made.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="290e4-104">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="290e4-104">Prerequisites</span></span>  
 <span data-ttu-id="290e4-105">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="290e4-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="290e4-106">Sie müssen über die Berechtigung verfügen, auf den Funktionsbereich **Benutzer- und Gruppenberechtigungen** zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="290e4-106">You must have permission to access the **Users and Group Permissions** functional area.</span></span>  
  
-   <span data-ttu-id="290e4-107">Sie müssen ein Modelladministrator sein.</span><span class="sxs-lookup"><span data-stu-id="290e4-107">You must be a model administrator.</span></span> <span data-ttu-id="290e4-108">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="290e4-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-delete-hierarchy-member-permissions"></a><span data-ttu-id="290e4-109">So löschen Sie Hierarchieelementberechtigungen</span><span class="sxs-lookup"><span data-stu-id="290e4-109">To delete hierarchy member permissions</span></span>  
  
1.  <span data-ttu-id="290e4-110">Klicken Sie in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]auf **Benutzer- und Gruppenberechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="290e4-110">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **User and Group Permissions**.</span></span>  
  
2.  <span data-ttu-id="290e4-111">Wählen Sie auf der Seite **Benutzer** oder **Gruppen** die Zeile für den Benutzer oder die Gruppe aus, den bzw. die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="290e4-111">On the **Users** or **Groups** page, select the row for the user or group that you want to edit.</span></span>  
  
3.  <span data-ttu-id="290e4-112">Klicken Sie auf **Ausgewähltem Benutzer bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="290e4-112">Click **Edit selected user**.</span></span>  
  
4.  <span data-ttu-id="290e4-113">Klicken Sie auf die Registerkarte **Hierarchieelemente** .</span><span class="sxs-lookup"><span data-stu-id="290e4-113">Click the **Hierarchy Members** tab.</span></span>  
  
5.  <span data-ttu-id="290e4-114">Wählen Sie aus der Liste **Modell** ein Modell aus.</span><span class="sxs-lookup"><span data-stu-id="290e4-114">From the **Model** list, select a model.</span></span>  
  
6.  <span data-ttu-id="290e4-115">Wählen Sie aus der Liste **Version** eine Version aus.</span><span class="sxs-lookup"><span data-stu-id="290e4-115">From the **Version** list, select a version.</span></span>  
  
7.  <span data-ttu-id="290e4-116">Wählen Sie im Bereich **Zusammenfassung der Hierarchie Element Berechtigungen** die Zeile für die Berechtigung aus, die Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="290e4-116">In the **Hierarchy Member Permission Summary** pane, select the row for the permission that you want to delete.</span></span>  
  
8.  <span data-ttu-id="290e4-117">Klicken Sie auf **ausgewählte Berechtigung Löschen**.</span><span class="sxs-lookup"><span data-stu-id="290e4-117">Click **Delete selected permission**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="290e4-118">Sie können keine Berechtigung von einem Benutzer entfernen, wenn die Berechtigung von einer Gruppe geerbt wird.</span><span class="sxs-lookup"><span data-stu-id="290e4-118">You cannot remove a permission from a user if the permission is inherited from a group.</span></span> <span data-ttu-id="290e4-119">Sie müssen stattdessen die Berechtigung von der Gruppe entfernen.</span><span class="sxs-lookup"><span data-stu-id="290e4-119">You must remove the permission from the group instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="290e4-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="290e4-120">See Also</span></span>  
 <span data-ttu-id="290e4-121">[Hierarchie Element Berechtigungen &#40;Master Data Services&#41;](../../2014/master-data-services/hierarchy-member-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="290e4-121">[Hierarchy Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/hierarchy-member-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="290e4-122">Zuweisen von Hierarchieelementberechtigungen &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="290e4-122">Assign Hierarchy Member Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/assign-hierarchy-member-permissions-master-data-services.md)  
  
  
