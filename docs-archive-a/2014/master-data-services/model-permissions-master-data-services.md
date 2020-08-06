---
title: Modellberechtigungen (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- models [Master Data Services], permissions
- permissions [Master Data Services], models
ms.assetid: 210f440b-2cc1-4c49-94b1-3a97e2af7bc3
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 2846918b515bba16d12d48cd7058cf25863bf569
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618078"
---
# <a name="model-permissions-master-data-services"></a><span data-ttu-id="17150-102">Modellberechtigungen (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="17150-102">Model Permissions (Master Data Services)</span></span>
  <span data-ttu-id="17150-103">Modellberechtigungen gelten für alle Entitäten, Attribute, abgeleiteten Hierarchien, expliziten Hierarchien und Auflistungen innerhalb des Modells.</span><span class="sxs-lookup"><span data-stu-id="17150-103">Model permissions apply to all entities, derived hierarchies, explicit hierarchies, and collections that exist within the model.</span></span> <span data-ttu-id="17150-104">Dem Modell zugewiesene Berechtigungen können für beliebige einzelne Objekte überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="17150-104">Permissions assigned to the model can be overridden for any individual object.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="17150-105">Wenn ein Benutzer ein Modelladministrator ist, wird das Modell in allen Funktionsbereichen der Benutzeroberfläche angezeigt.</span><span class="sxs-lookup"><span data-stu-id="17150-105">If a user is a model administrator, the model is displayed in all functional areas of the user interface.</span></span> <span data-ttu-id="17150-106">Andernfalls wird das Modell nur im Funktionsbereich **Explorer** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="17150-106">Otherwise, the model is displayed in the **Explorer** functional area only.</span></span> <span data-ttu-id="17150-107">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="17150-107">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
|<span data-ttu-id="17150-108">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="17150-108">Permission</span></span>|<span data-ttu-id="17150-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="17150-109">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="17150-110">**Schreibgeschützt**</span><span class="sxs-lookup"><span data-stu-id="17150-110">**Read-only**</span></span>|<span data-ttu-id="17150-111">Im **Explorer**wird das Modell angezeigt, aber der Benutzer kann keine Elemente hinzufügen oder entfernen, und es können keine Attributwerte, Hierarchie Mitgliedschaften oder Sammlungs Mitgliedschaften aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="17150-111">In **Explorer**, the model is displayed but the user cannot add or remove members, and cannot update attribute values, hierarchy memberships, or collection memberships.</span></span>|  
|<span data-ttu-id="17150-112">**Aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="17150-112">**Update**</span></span>|<span data-ttu-id="17150-113">Im **Explorer**wird das Modell angezeigt, und der Benutzer kann Elemente hinzufügen und entfernen, Attributwerte, Hierarchie Mitgliedschaften und Sammlungs Mitgliedschaften aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="17150-113">In **Explorer**, the model is displayed and the user can add and remove members, can update attribute values, hierarchy memberships, and collection memberships.</span></span>|  
|<span data-ttu-id="17150-114">**Deny** (Verweigern)</span><span class="sxs-lookup"><span data-stu-id="17150-114">**Deny**</span></span>|<span data-ttu-id="17150-115">Das Modell wird nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="17150-115">The model is not displayed.</span></span>|  
  
 <span data-ttu-id="17150-116">Wenn Sie einem Modell eine Berechtigung zuweisen, erhält der Benutzer Zugriff auf alle Versionen des Modells.</span><span class="sxs-lookup"><span data-stu-id="17150-116">When you assign permission to a model, the user gets access to all versions of the model.</span></span> <span data-ttu-id="17150-117">Sie können keine Berechtigung für eine einzelne Version zuweisen.</span><span class="sxs-lookup"><span data-stu-id="17150-117">You cannot assign permission to an individual version.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17150-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="17150-118">See Also</span></span>  
 <span data-ttu-id="17150-119">[Zuweisen von Berechtigungen für Modell Objekte &#40;Master Data Services&#41;](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="17150-119">[Assign Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="17150-120">[Modell Objekt Berechtigungen &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="17150-120">[Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="17150-121">[Entitäts Berechtigungen &#40;Master Data Services&#41;](../../2014/master-data-services/entity-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="17150-121">[Entity Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/entity-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="17150-122">Sammlungsberechtigungen &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="17150-122">Collection Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/collection-permissions-master-data-services.md)  
  
  
