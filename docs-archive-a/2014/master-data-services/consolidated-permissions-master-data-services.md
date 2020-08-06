---
title: Konsolidierte Berechtigungen (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- attributes [Master Data Services], consolidated member attribute permissions
- consolidated members [Master Data Services], attribute permissions
- permissions [Master Data Services], consolidated members
- members [Master Data Services], consolidated member permissions
ms.assetid: 084055a3-5fd3-43f3-b620-ac6afab42a3d
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c4c93e74acc84d6e742139263bedc011c4028efb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630697"
---
# <a name="consolidated-permissions-master-data-services"></a><span data-ttu-id="16fb0-102">Konsolidierte Berechtigungen (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="16fb0-102">Consolidated Permissions (Master Data Services)</span></span>
  <span data-ttu-id="16fb0-103">Konsolidierte Berechtigungen beziehen sich auf die Attributwerte für alle konsolidierten Elemente einer Entität.</span><span class="sxs-lookup"><span data-stu-id="16fb0-103">Consolidated permissions apply to the attribute values for all consolidated members of an entity.</span></span>  
  
 <span data-ttu-id="16fb0-104">Konsolidierte Berechtigungen gelten nur für Entitäten, die für explizite Hierarchien und Auflistungen aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="16fb0-104">Consolidated permissions apply only to entities that are enabled for explicit hierarchies and collections.</span></span>  
  
 <span data-ttu-id="16fb0-105">**Hinweise:**</span><span class="sxs-lookup"><span data-stu-id="16fb0-105">**Notes:**</span></span>  
  
-   <span data-ttu-id="16fb0-106">Blattberechtigungen gelten nur für den Funktionsbereich **Explorer** der Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="16fb0-106">Leaf permissions apply to the **Explorer** functional area of the user interface only.</span></span>  
  
-   <span data-ttu-id="16fb0-107">Den Attributen **Name** und **Code** zugewiesene Berechtigungen werden nicht erzwungen.</span><span class="sxs-lookup"><span data-stu-id="16fb0-107">Permissions assigned to **Name** and **Code** attributes are not enforced.</span></span>  
  
|<span data-ttu-id="16fb0-108">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="16fb0-108">Permission</span></span>|<span data-ttu-id="16fb0-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="16fb0-109">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="16fb0-110">**Schreibgeschützt**</span><span class="sxs-lookup"><span data-stu-id="16fb0-110">**Read-only**</span></span>|<span data-ttu-id="16fb0-111">Konsolidierte Elemente werden zwar angezeigt, Benutzer können jedoch keine Elemente hinzufügen, entfernen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="16fb0-111">Consolidated members are displayed but the user cannot add, remove, or change them.</span></span>|  
|<span data-ttu-id="16fb0-112">**Aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="16fb0-112">**Update**</span></span>|<span data-ttu-id="16fb0-113">Konsolidierte Elemente werden angezeigt und können vom Benutzer hinzugefügt, entfernt und geändert werden.</span><span class="sxs-lookup"><span data-stu-id="16fb0-113">Consolidated members are displayed and the user can add, remove, and change them.</span></span>|  
|<span data-ttu-id="16fb0-114">**Deny** (Verweigern)</span><span class="sxs-lookup"><span data-stu-id="16fb0-114">**Deny**</span></span>|<span data-ttu-id="16fb0-115">Konsolidierte Elemente für die Entität werden nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="16fb0-115">Consolidated members for the entity are not displayed.</span></span>|  
  
## <a name="attribute-permissions"></a><span data-ttu-id="16fb0-116">Attributberechtigungen</span><span class="sxs-lookup"><span data-stu-id="16fb0-116">Attribute Permissions</span></span>  
 <span data-ttu-id="16fb0-117">Attributberechtigungen gelten für die Attributwerte der jeweiligen Entität.</span><span class="sxs-lookup"><span data-stu-id="16fb0-117">Attribute permissions apply to the attribute's values for the specific entity.</span></span> <span data-ttu-id="16fb0-118">Benutzer, die nur über Attributberechtigungen verfügen, können keine Elemente hinzufügen oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="16fb0-118">Users with only attribute permissions cannot add or remove members.</span></span>  
  
|<span data-ttu-id="16fb0-119">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="16fb0-119">Permission</span></span>|<span data-ttu-id="16fb0-120">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="16fb0-120">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="16fb0-121">**Schreibgeschützt**</span><span class="sxs-lookup"><span data-stu-id="16fb0-121">**Read-only**</span></span>|<span data-ttu-id="16fb0-122">Das Attribut wird zwar angezeigt, aber der Benutzer kann keine Attributwerte ändern.</span><span class="sxs-lookup"><span data-stu-id="16fb0-122">The attribute is displayed but the user cannot change attribute values.</span></span>|  
|<span data-ttu-id="16fb0-123">**Aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="16fb0-123">**Update**</span></span>|<span data-ttu-id="16fb0-124">Das Attribut wird angezeigt, und der Benutzer kann Attributwerte ändern.</span><span class="sxs-lookup"><span data-stu-id="16fb0-124">The attribute is displayed and the user can change attribute values.</span></span>|  
|<span data-ttu-id="16fb0-125">**Deny** (Verweigern)</span><span class="sxs-lookup"><span data-stu-id="16fb0-125">**Deny**</span></span>|<span data-ttu-id="16fb0-126">Das Attribut wird nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="16fb0-126">The attribute is not displayed.</span></span><br /><br /> <span data-ttu-id="16fb0-127">Hinweis: Der Zugriff auf die Attribute Name und Code kann nicht explizit verweigert werden.</span><span class="sxs-lookup"><span data-stu-id="16fb0-127">Note: You cannot explicitly deny access to Name and Code attributes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="16fb0-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="16fb0-128">See Also</span></span>  
 <span data-ttu-id="16fb0-129">[Zuweisen von Berechtigungen für Modell Objekte &#40;Master Data Services&#41;](assign-model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="16fb0-129">[Assign Model Object Permissions &#40;Master Data Services&#41;](assign-model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="16fb0-130">[Blatt Berechtigungen &#40;Master Data Services&#41;](../../2014/master-data-services/leaf-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="16fb0-130">[Leaf Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/leaf-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="16fb0-131">[Modell Objekt Berechtigungen &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="16fb0-131">[Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="16fb0-132">[Mitglieder &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="16fb0-132">[Members &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md) </span></span>  
 [<span data-ttu-id="16fb0-133">Attribute &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="16fb0-133">Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/attributes-master-data-services.md)  
  
  
