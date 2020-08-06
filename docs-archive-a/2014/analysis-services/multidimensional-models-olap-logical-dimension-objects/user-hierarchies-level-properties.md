---
title: Leveleigenschaften | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- user hierarchies [Analysis Services]
- hierarchies [Analysis Services], user
ms.assetid: dabb7335-887b-442a-b67c-4901ba1242b7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 553503b9d35142bcc998b4ec12ad2e29d4c66318
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609507"
---
# <a name="level-properties"></a><span data-ttu-id="364fd-102">Ebeneneigenschaften</span><span class="sxs-lookup"><span data-stu-id="364fd-102">Level Properties</span></span> 
  <span data-ttu-id="364fd-103">In der folgenden Tabelle sind die Eigenschaften einer Ebene in einer benutzerdefinierten Hierarchie aufgelistet und beschrieben.</span><span class="sxs-lookup"><span data-stu-id="364fd-103">The following table lists and describes the properties of a level in a user-defined hierarchy.</span></span>  
  
|<span data-ttu-id="364fd-104">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="364fd-104">Property</span></span>|<span data-ttu-id="364fd-105">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="364fd-105">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="364fd-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="364fd-106">Description</span></span>|<span data-ttu-id="364fd-107">Enthält die Beschreibung der Ebene.</span><span class="sxs-lookup"><span data-stu-id="364fd-107">Contains the description of the level.</span></span>|  
|<span data-ttu-id="364fd-108">HideMemberIf</span><span class="sxs-lookup"><span data-stu-id="364fd-108">HideMemberIf</span></span>|<span data-ttu-id="364fd-109">Gibt an, ob und wann ein Element auf einer Ebene aus Clientanwendungen ausgeblendet werden sollte.</span><span class="sxs-lookup"><span data-stu-id="364fd-109">Indicates whether and when a member in a level should be hidden from client applications.</span></span> <span data-ttu-id="364fd-110">Diese Eigenschaft kann die folgenden Werte annehmen:</span><span class="sxs-lookup"><span data-stu-id="364fd-110">This property can have the following values:</span></span><br /><br /> <span data-ttu-id="364fd-111">Nie</span><span class="sxs-lookup"><span data-stu-id="364fd-111">Never</span></span><br /> <span data-ttu-id="364fd-112">Elemente werden nie ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="364fd-112">Members are never hidden.</span></span> <span data-ttu-id="364fd-113">Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="364fd-113">This is the default value.</span></span><br /><br /> <span data-ttu-id="364fd-114">OnlyChildWithNoName</span><span class="sxs-lookup"><span data-stu-id="364fd-114">OnlyChildWithNoName</span></span><br /> <span data-ttu-id="364fd-115">Ein Element wird ausgeblendet, wenn das Element das einzige untergeordnete Element eines übergeordneten Elements ist und der Name des Elements leer ist.</span><span class="sxs-lookup"><span data-stu-id="364fd-115">A member is hidden when the member is the only child of its parent and the member's name is empty.</span></span><br /><br /> <span data-ttu-id="364fd-116">OnlyChildWithParentName</span><span class="sxs-lookup"><span data-stu-id="364fd-116">OnlyChildWithParentName</span></span><br /> <span data-ttu-id="364fd-117">Ein Element wird ausgeblendet, wenn das Element das einzige untergeordnete Element eines übergeordneten Elements ist und der Name des Elements identisch mit dem des übergeordneten Elements ist.</span><span class="sxs-lookup"><span data-stu-id="364fd-117">A member is hidden when the member is the only child of its parent and the member's name is identical to that of its parent.</span></span><br /><br /> <span data-ttu-id="364fd-118">NoName</span><span class="sxs-lookup"><span data-stu-id="364fd-118">NoName</span></span><br /> <span data-ttu-id="364fd-119">Ein Element wird ausgeblendet, wenn der Name des Elements leer ist.</span><span class="sxs-lookup"><span data-stu-id="364fd-119">A member is hidden when the member's name is empty.</span></span><br /><br /> <span data-ttu-id="364fd-120">ParentName</span><span class="sxs-lookup"><span data-stu-id="364fd-120">ParentName</span></span><br /> <span data-ttu-id="364fd-121">Ein Element wird ausgeblendet, wenn der Name des Elements identisch mit dem Namen des übergeordneten Elements ist.</span><span class="sxs-lookup"><span data-stu-id="364fd-121">A member is hidden when the member's name is identical to that of its parent.</span></span>|  
|<span data-ttu-id="364fd-122">id</span><span class="sxs-lookup"><span data-stu-id="364fd-122">ID</span></span>|<span data-ttu-id="364fd-123">Enthält den eindeutigen Bezeichner (ID) der Ebene.</span><span class="sxs-lookup"><span data-stu-id="364fd-123">Contains the unique identifier (ID) of the level.</span></span>|  
|<span data-ttu-id="364fd-124">Name</span><span class="sxs-lookup"><span data-stu-id="364fd-124">Name</span></span>|<span data-ttu-id="364fd-125">Enthält den Anzeigenamen der Ebene.</span><span class="sxs-lookup"><span data-stu-id="364fd-125">Contains the friendly name of the level.</span></span> <span data-ttu-id="364fd-126">Standardmäßig stimmt der Name einer Ebene mit dem Namen des Quellattributs überein.</span><span class="sxs-lookup"><span data-stu-id="364fd-126">By default, the name of a level is the same as the name of the source attribute.</span></span>|  
|<span data-ttu-id="364fd-127">SourceAttribute</span><span class="sxs-lookup"><span data-stu-id="364fd-127">SourceAttribute</span></span>|<span data-ttu-id="364fd-128">Enthält den Namen des Quellattributs, auf dem die Ebene basiert.</span><span class="sxs-lookup"><span data-stu-id="364fd-128">Contains the name of the source attribute on which the level is based.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="364fd-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="364fd-129">See Also</span></span>  
 [<span data-ttu-id="364fd-130">Eigenschaften der Benutzerhierarchie</span><span class="sxs-lookup"><span data-stu-id="364fd-130">User Hierarchy Properties</span></span>](user-hierarchies-properties.md)  
  
  
