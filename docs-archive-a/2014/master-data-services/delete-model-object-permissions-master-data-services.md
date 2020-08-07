---
title: Löschen von Berechtigungen für Modellobjekte (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deleting model object permissions [Master Data Services]
- permissions [Master Data Services], deleting model object permissions
- models [Master Data Services], deleting object permissions
ms.assetid: 859c5952-f600-4940-8064-1afd13f7f6dc
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 98da869476e597d76a83b0b86cc9e6e4274a25e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699951"
---
# <a name="delete-model-object-permissions-master-data-services"></a><span data-ttu-id="b25a0-102">Löschen von Berechtigungen für Modellobjekte (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="b25a0-102">Delete Model Object Permissions (Master Data Services)</span></span>
  <span data-ttu-id="b25a0-103">Löschen Sie in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]Modellobjektberechtigungen, um erfolgte Zuweisungen zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="b25a0-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], delete model object permissions to remove any assignments that have been made.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b25a0-104">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="b25a0-104">Prerequisites</span></span>  
 <span data-ttu-id="b25a0-105">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="b25a0-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="b25a0-106">Sie müssen über die Berechtigung verfügen, auf den Funktionsbereich **Benutzer- und Gruppenberechtigungen** zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="b25a0-106">You must have permission to access the **Users and Group Permissions** functional area.</span></span>  
  
-   <span data-ttu-id="b25a0-107">Sie müssen ein Modelladministrator sein.</span><span class="sxs-lookup"><span data-stu-id="b25a0-107">You must be a model administrator.</span></span> <span data-ttu-id="b25a0-108">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="b25a0-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-delete-model-object-permissions"></a><span data-ttu-id="b25a0-109">So löschen Sie Modellobjektberechtigungen</span><span class="sxs-lookup"><span data-stu-id="b25a0-109">To delete model object permissions</span></span>  
  
1.  <span data-ttu-id="b25a0-110">Klicken Sie in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]auf **Benutzer- und Gruppenberechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="b25a0-110">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **User and Group Permissions**.</span></span>  
  
2.  <span data-ttu-id="b25a0-111">Wählen Sie auf der Seite **Benutzer** oder **Gruppen** die Zeile für den Benutzer oder die Gruppe aus, den bzw. die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="b25a0-111">On the **Users** or **Groups** page, select the row for the user or group that you want to edit.</span></span>  
  
3.  <span data-ttu-id="b25a0-112">Klicken Sie auf **Ausgewähltem Benutzer bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="b25a0-112">Click **Edit selected user**.</span></span>  
  
4.  <span data-ttu-id="b25a0-113">Klicken Sie auf die Registerkarte **Modelle** .</span><span class="sxs-lookup"><span data-stu-id="b25a0-113">Click the **Models** tab.</span></span>  
  
5.  <span data-ttu-id="b25a0-114">Wählen Sie optional ein Modell aus der Liste **Modell** aus.</span><span class="sxs-lookup"><span data-stu-id="b25a0-114">Optionally, select a model from the **Model** list.</span></span>  
  
6.  <span data-ttu-id="b25a0-115">Wählen Sie im Bereich **Zusammenfassung der Modell Berechtigungen** die Zeile für die Berechtigung aus, die Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="b25a0-115">In the **Model Permission Summary** pane, select the row for the permission that you want to delete.</span></span>  
  
7.  <span data-ttu-id="b25a0-116">Klicken Sie auf **ausgewählte Berechtigung Löschen**.</span><span class="sxs-lookup"><span data-stu-id="b25a0-116">Click **Delete selected permission**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b25a0-117">Sie können keine Berechtigung von einem Benutzer entfernen, wenn die Berechtigung von einer Gruppe geerbt wird.</span><span class="sxs-lookup"><span data-stu-id="b25a0-117">You cannot remove a permission from a user if the permission is inherited from a group.</span></span> <span data-ttu-id="b25a0-118">Sie müssen stattdessen die Berechtigung von der Gruppe entfernen.</span><span class="sxs-lookup"><span data-stu-id="b25a0-118">You must remove the permission from the group instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b25a0-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b25a0-119">See Also</span></span>  
 <span data-ttu-id="b25a0-120">[Modell Objekt Berechtigungen &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="b25a0-120">[Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="b25a0-121">Zuweisen von Berechtigungen für Modellobjekte &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="b25a0-121">Assign Model Object Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md)  
  
  
