---
title: Zuweisen von Berechtigungen für Modellobjekte (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- models [Master Data Services], assigning object permissions
- permissions [Master Data Services], assigning model object permissions
ms.assetid: 4b80148d-2318-415c-9479-28c240e48bcd
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 92ac8ef3ac63b7128c4cbb7e9305ee6bd56ca010
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618763"
---
# <a name="assign-model-object-permissions-master-data-services"></a><span data-ttu-id="bf7b3-102">Zuweisen von Berechtigungen für Modellobjekte (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="bf7b3-102">Assign Model Object Permissions (Master Data Services)</span></span>
  <span data-ttu-id="bf7b3-103">Weisen Sie in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]Berechtigungen zu Modellobjekten hinzu, wenn Sie einem Benutzer oder einer Gruppe Zugriff auf Daten im Funktionsbereich **Explorer** von [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]gewähren oder einen Benutzer oder eine Gruppe als Administrator festlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="bf7b3-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], assign permissions to model objects when you need to give a user or group access to data in the **Explorer** functional area of [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], or when you need to make a user or group an administrator.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bf7b3-104">Wenn Sie einem Modell eine Berechtigung zuweisen, wird allen anderen Modellen die Berechtigung implizit verweigert.</span><span class="sxs-lookup"><span data-stu-id="bf7b3-104">When you assign permission to a model, permission to all other models is implicitly denied.</span></span> <span data-ttu-id="bf7b3-105">Wenn Sie keine Modellobjektberechtigungen zuweisen, kann der Benutzer oder die Gruppe auf keine Daten in **Explorer**zugreifen.</span><span class="sxs-lookup"><span data-stu-id="bf7b3-105">If you do not assign model object permissions, the user or group cannot access any data in **Explorer**.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="bf7b3-106">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="bf7b3-106">Prerequisites</span></span>  
 <span data-ttu-id="bf7b3-107">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="bf7b3-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="bf7b3-108">Sie müssen über die Berechtigung verfügen, auf den Funktionsbereich **Benutzer- und Gruppenberechtigungen** zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="bf7b3-108">You must have permission to access the **Users and Group Permissions** functional area.</span></span>  
  
-   <span data-ttu-id="bf7b3-109">Sie müssen ein Modelladministrator sein.</span><span class="sxs-lookup"><span data-stu-id="bf7b3-109">You must be a model administrator.</span></span> <span data-ttu-id="bf7b3-110">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="bf7b3-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-assign-model-object-permissions"></a><span data-ttu-id="bf7b3-111">So weisen Sie Modellobjektberechtigungen zu</span><span class="sxs-lookup"><span data-stu-id="bf7b3-111">To assign model object permissions</span></span>  
  
1.  <span data-ttu-id="bf7b3-112">Klicken Sie in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]auf **Benutzer- und Gruppenberechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="bf7b3-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **User and Group Permissions**.</span></span>  
  
2.  <span data-ttu-id="bf7b3-113">Wählen Sie auf der Seite **Benutzer** oder **Gruppen** die Zeile für den Benutzer oder die Gruppe aus, den bzw. die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="bf7b3-113">On the **Users** or **Groups** page, select the row for the user or group that you want to edit.</span></span>  
  
3.  <span data-ttu-id="bf7b3-114">Klicken Sie auf **Ausgewähltem Benutzer bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="bf7b3-114">Click **Edit selected user**.</span></span>  
  
4.  <span data-ttu-id="bf7b3-115">Klicken Sie auf die Registerkarte **Modelle** .</span><span class="sxs-lookup"><span data-stu-id="bf7b3-115">Click the **Models** tab.</span></span>  
  
5.  <span data-ttu-id="bf7b3-116">Wählen Sie optional ein Modell aus der Liste **Modell** aus.</span><span class="sxs-lookup"><span data-stu-id="bf7b3-116">Optionally, select a model from the **Model** list.</span></span>  
  
6.  <span data-ttu-id="bf7b3-117">Klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="bf7b3-117">Click **Edit**.</span></span>  
  
7.  <span data-ttu-id="bf7b3-118">Erweitern Sie die Struktur, und klicken Sie auf das Modellobjekt, dem Sie Berechtigungen zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="bf7b3-118">Expand the tree, and click the model object you want to assign permissions to.</span></span>  
  
8.  <span data-ttu-id="bf7b3-119">**Wählen Sie**im Menü die Option schreibgeschützt, **Aktualisieren**oder **verweigern**aus.</span><span class="sxs-lookup"><span data-stu-id="bf7b3-119">From the menu, select **Read-only**, **Update**, or **Deny**.</span></span>  
  
9. <span data-ttu-id="bf7b3-120">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="bf7b3-120">Click **Save**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="bf7b3-121">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="bf7b3-121">Next Steps</span></span>  
  
-   <span data-ttu-id="bf7b3-122">(Optional) [Zuweisen von Hierarchieelementberechtigungen &#40;Master Data Services&#41;](../../2014/master-data-services/assign-hierarchy-member-permissions-master-data-services.md)</span><span class="sxs-lookup"><span data-stu-id="bf7b3-122">(Optional) [Assign Hierarchy Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/assign-hierarchy-member-permissions-master-data-services.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf7b3-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bf7b3-123">See Also</span></span>  
 <span data-ttu-id="bf7b3-124">[Löschen von Berechtigungen für Modell Objekte &#40;Master Data Services&#41;](../../2014/master-data-services/delete-model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="bf7b3-124">[Delete Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/delete-model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="bf7b3-125">[Modell Objekt Berechtigungen &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="bf7b3-125">[Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="bf7b3-126">Erstellen eines Modelladministrators &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="bf7b3-126">Create a Model Administrator &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-model-administrator-master-data-services.md)  
  
  
