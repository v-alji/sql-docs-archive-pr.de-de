---
title: Navigationszugriff (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- navigational access [Master Data Services]
- security [Master Data Services], navigational access
ms.assetid: 3403b7b0-44e2-48c3-a1b7-9c4612b874b8
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 7af3c16d98320b6fea3d4611e9e4c6d37c6015bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607859"
---
# <a name="navigational-access-master-data-services"></a><span data-ttu-id="84c27-102">Navigationszugriff (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="84c27-102">Navigational Access (Master Data Services)</span></span>
  <span data-ttu-id="84c27-103">Der Navigationszugriff gilt für die Modellobjektsicherheit, die auf der Registerkarte **Modelle** zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="84c27-103">Navigational access applies to model object security, which is assigned on the **Models** tab.</span></span>  
  
 <span data-ttu-id="84c27-104">Navigationszugriff ist der Zugriff auf höhere Ebenen als die Ebene, für die Sie Sicherheit zugewiesen haben.</span><span class="sxs-lookup"><span data-stu-id="84c27-104">Navigational access is the access you get to levels higher than where you've assigned security.</span></span>  
  
 <span data-ttu-id="84c27-105">In diesem Beispiel werden einer Entität Berechtigungen zugewiesen, der Navigationszugriff wird daher auf der Modellebene gewährt.</span><span class="sxs-lookup"><span data-stu-id="84c27-105">In this example, permissions are assigned to an entity, and so navigational access is granted at the model level.</span></span>  
  
 <span data-ttu-id="84c27-106">![mds_conc_inheritance_model](../../2014/master-data-services/media/mds-conc-inheritance-model.gif "mds_conc_inheritance_model")</span><span class="sxs-lookup"><span data-stu-id="84c27-106">![mds_conc_inheritance_model](../../2014/master-data-services/media/mds-conc-inheritance-model.gif "mds_conc_inheritance_model")</span></span>  
  
 <span data-ttu-id="84c27-107">**Entitäten**</span><span class="sxs-lookup"><span data-stu-id="84c27-107">**Entities**</span></span>  
  
 <span data-ttu-id="84c27-108">Wenn Sie einer Entität, den Blattelementen oder konsolidierten Elementen Berechtigungen zuweisen, bedeutet Navigationszugriff, dass Sie den Namen und den Code für alle Elemente lesen oder aktualisieren können.</span><span class="sxs-lookup"><span data-stu-id="84c27-108">When you assign permission to an entity, its leaf members, or its consolidated members, navigational access means you can read or update the name and code for all members.</span></span> <span data-ttu-id="84c27-109">Sie können auch den Modellnamen lesen.</span><span class="sxs-lookup"><span data-stu-id="84c27-109">You can also read the model name.</span></span>  
  
 <span data-ttu-id="84c27-110">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="84c27-110">**Attributes**</span></span>  
  
 <span data-ttu-id="84c27-111">Wenn Sie einem Attribut Berechtigungen zuweisen, bedeutet Navigationszugriff, dass Sie den Namen und den Code für alle Elemente in der Entität lesen oder aktualisieren können.</span><span class="sxs-lookup"><span data-stu-id="84c27-111">When you assign permission to an attribute, navigational access means you can read or update the name and code for all members in the entity.</span></span> <span data-ttu-id="84c27-112">Sie können auch den Modellnamen lesen.</span><span class="sxs-lookup"><span data-stu-id="84c27-112">You can also read the model name.</span></span>  
  
 <span data-ttu-id="84c27-113">**Sammlungen**</span><span class="sxs-lookup"><span data-stu-id="84c27-113">**Collections**</span></span>  
  
 <span data-ttu-id="84c27-114">Wenn Sie Auflistungen Berechtigungen zuweisen, können Sie den Namen, Code, die Beschreibung und Besitzer-ID lesen oder aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="84c27-114">When you assign permissions to collections, you can read or update the name, code, description and owner ID.</span></span> <span data-ttu-id="84c27-115">Sie können auch den Modellnamen lesen.</span><span class="sxs-lookup"><span data-stu-id="84c27-115">You can also read the model name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84c27-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="84c27-116">See Also</span></span>  
 [<span data-ttu-id="84c27-117">Vorgehensweise: Festlegen von Berechtigungen &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="84c27-117">How Permissions Are Determined &#40;Master Data Services&#41;</span></span>](how-permissions-are-determined-master-data-services.md)  
  
  
