---
title: Erstellen eines Modelladministrators (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- administrators [Master Data Services], creating
ms.assetid: dae17afc-3b39-490e-b51f-2d8da26d429e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 24efc3961e6ed5b9f41b2321dfcc4fbf16632270
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622754"
---
# <a name="create-a-model-administrator-master-data-services"></a><span data-ttu-id="bfdb3-102">Erstellen eines Modelladministrators (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="bfdb3-102">Create a Model Administrator (Master Data Services)</span></span>
  <span data-ttu-id="bfdb3-103">[!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]Erstellen Sie in einen Modell Administrator, wenn eine Gruppe oder ein Benutzer über die Berechtigung **Aktualisieren** für alle Objekte in einem oder mehreren Modellen verfügen soll.</span><span class="sxs-lookup"><span data-stu-id="bfdb3-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a model administrator when you want a group or user to have **Update** permission to all objects in one or more models.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="bfdb3-104">Um die Verwaltung zu vereinfachen, erstellen Sie eine Windows-Gruppe oder eine lokale Gruppe, und konfigurieren Sie diese als Modell Administrator.</span><span class="sxs-lookup"><span data-stu-id="bfdb3-104">To simplify administration, create a Windows or local group and configure it as a model administrator.</span></span> <span data-ttu-id="bfdb3-105">Sie können anschließend der Gruppe Benutzer hinzufügen und diese daraus entfernen, ohne auf [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="bfdb3-105">You can then add and remove users from the group without accessing [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="bfdb3-106">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="bfdb3-106">Prerequisites</span></span>  
 <span data-ttu-id="bfdb3-107">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="bfdb3-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="bfdb3-108">Sie müssen über die Berechtigung verfügen, auf den Funktionsbereich **Benutzer- und Gruppenberechtigungen** zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="bfdb3-108">You must have permission to access the **User and Group Permissions** functional area.</span></span>  
  
-   <span data-ttu-id="bfdb3-109">Sie müssen ein Modelladministrator sein.</span><span class="sxs-lookup"><span data-stu-id="bfdb3-109">You must be a model administrator.</span></span> <span data-ttu-id="bfdb3-110">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="bfdb3-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-create-a-model-administrator"></a><span data-ttu-id="bfdb3-111">So erstellen Sie einen Modelladministrator</span><span class="sxs-lookup"><span data-stu-id="bfdb3-111">To create a model administrator</span></span>  
  
1.  <span data-ttu-id="bfdb3-112">Klicken Sie in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]auf **Benutzer- und Gruppenberechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="bfdb3-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **User and Group Permissions**.</span></span>  
  
2.  <span data-ttu-id="bfdb3-113">Wählen Sie auf der Seite **Benutzer** oder **Gruppen** die Zeile für den Benutzer oder die Gruppe aus, den bzw. die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="bfdb3-113">On the **Users** or **Groups** page, select the row for the user or group that you want to edit.</span></span>  
  
3.  <span data-ttu-id="bfdb3-114">Klicken Sie auf **Ausgewähltem Benutzer bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="bfdb3-114">Click **Edit selected user**.</span></span>  
  
4.  <span data-ttu-id="bfdb3-115">Klicken Sie auf die Registerkarte **Modelle** .</span><span class="sxs-lookup"><span data-stu-id="bfdb3-115">Click the **Models** tab.</span></span>  
  
5.  <span data-ttu-id="bfdb3-116">Wählen Sie optional ein Modell aus der Liste **Modell** aus.</span><span class="sxs-lookup"><span data-stu-id="bfdb3-116">Optionally, select a model from the **Model** list.</span></span>  
  
6.  <span data-ttu-id="bfdb3-117">Klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="bfdb3-117">Click **Edit**.</span></span>  
  
7.  <span data-ttu-id="bfdb3-118">Klicken Sie auf das Modell, dem Sie die Berechtigung zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="bfdb3-118">Click the model you want to grant permission to.</span></span>  
  
8.  <span data-ttu-id="bfdb3-119">Wählen Sie im Menü die Option **Aktualisieren**aus.</span><span class="sxs-lookup"><span data-stu-id="bfdb3-119">From the menu, select **Update**.</span></span>  
  
9. <span data-ttu-id="bfdb3-120">Führen Sie die Schritte 7 und 8 für jedes Modell aus, für das Sie die Gruppe bzw. den Benutzer als Administrator definieren möchten.</span><span class="sxs-lookup"><span data-stu-id="bfdb3-120">Complete steps 7 and 8 for each model you want the group or user to be an administrator for.</span></span>  
  
10. <span data-ttu-id="bfdb3-121">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="bfdb3-121">Click **Save**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bfdb3-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="bfdb3-122">Remarks</span></span>  
 <span data-ttu-id="bfdb3-123">Weisen Sie Objekten oder Hierarchieelementen keine anderen Berechtigungen zu.</span><span class="sxs-lookup"><span data-stu-id="bfdb3-123">Do not assign any other permissions to model objects or hierarchy members.</span></span> <span data-ttu-id="bfdb3-124">Wenn Sie dies tun, ist der Benutzer kein Administrator mehr und kann das Modell nicht in einem anderen Funktionsbereich als **Explorer**anzeigen.</span><span class="sxs-lookup"><span data-stu-id="bfdb3-124">If you do, the user is no longer an administrator and cannot view the model in any functional area other than **Explorer**.</span></span>  
  
 <span data-ttu-id="bfdb3-125">Es gibt eine Ausnahme: Wenn dem **Benutzer auf der** Registerkarte **Hierarchie** Elemente eine Berechtigung **Aktualisieren** zugewiesen ist, wird der Benutzer weiterhin als Modell Administrator betrachtet.</span><span class="sxs-lookup"><span data-stu-id="bfdb3-125">There is one exception: if the user has **Update** permission assigned to a hierarchy **Root** on the **Hierarchy Members** tab, the user is still considered a model administrator.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfdb3-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bfdb3-126">See Also</span></span>  
 <span data-ttu-id="bfdb3-127">[Administratoren &#40;Master Data Services&#41;](administrators-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="bfdb3-127">[Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md) </span></span>  
 <span data-ttu-id="bfdb3-128">[Zuweisen von Berechtigungen für Modell Objekte &#40;Master Data Services&#41;](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="bfdb3-128">[Assign Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="bfdb3-129">[Hierarchie Element Berechtigungen &#40;Master Data Services zuweisen&#41;](../../2014/master-data-services/assign-hierarchy-member-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="bfdb3-129">[Assign Hierarchy Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/assign-hierarchy-member-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="bfdb3-130">[Modell Objekt Berechtigungen &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="bfdb3-130">[Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="bfdb3-131">Berechtigungen für Hierarchieelemente &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="bfdb3-131">Hierarchy Member Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/hierarchy-member-permissions-master-data-services.md)  
  
  
