---
title: Eigenschaften der Cube-Hierarchie definieren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- hierarchies [Analysis Services], multilevel
- hierarchies [Analysis Services], cubes
ms.assetid: 819d0a4e-7815-4332-a605-b07ca2ade6ac
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8903a49754357aad9cf24ee63fffa45fbf120e4d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696249"
---
# <a name="define-cube-hierarchy-properties"></a><span data-ttu-id="93be4-102">Definieren von Cubehierarchieeigenschaften</span><span class="sxs-lookup"><span data-stu-id="93be4-102">Define Cube Hierarchy Properties</span></span>
  <span data-ttu-id="93be4-103">Durch Cubehierarchieeigenschaften können Sie eindeutige Einstellungen für benutzerdefinierte Hierarchien in Cubedimensionen angeben, die auf denselben Datenbankdimensionen basieren.</span><span class="sxs-lookup"><span data-stu-id="93be4-103">Cube hierarchy properties enable you to specify unique settings for user-defined hierarchies in cube dimensions based on the same database dimension.</span></span> <span data-ttu-id="93be4-104">In der folgenden Tabelle werden die Eigenschaften einer Cubehierarchie beschrieben.</span><span class="sxs-lookup"><span data-stu-id="93be4-104">The following table describes the properties of a cube hierarchy.</span></span>  
  
|<span data-ttu-id="93be4-105">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="93be4-105">Property</span></span>|<span data-ttu-id="93be4-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="93be4-106">Description</span></span>|  
|--------------|-----------------|  
|`Enabled`|<span data-ttu-id="93be4-107">Bestimmt, ob die Hierarchie für die Cubedimension aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="93be4-107">Determines whether the hierarchy is enabled for the cube dimension.</span></span>|  
|`HierarchyID`|<span data-ttu-id="93be4-108">Enthält den eindeutigen Bezeichner (ID) der Hierarchie.</span><span class="sxs-lookup"><span data-stu-id="93be4-108">Contains the unique identifier (ID) of the hierarchy.</span></span>|  
|`OptimizedState`|<span data-ttu-id="93be4-109">Bestimmt die Optimierungsebene, die auf die Hierarchie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="93be4-109">Determines the level of optimization that is applied to the hierarchy.</span></span> <span data-ttu-id="93be4-110">Diese Eigenschaft kann die folgenden Werte annehmen:</span><span class="sxs-lookup"><span data-stu-id="93be4-110">This property can have the following values:</span></span><br /><br /> <span data-ttu-id="93be4-111">`FullyOptimized`: Von der Instanz werden Indizes zum Verbessern der Abfrageleistung für die Hierarchie erstellt.</span><span class="sxs-lookup"><span data-stu-id="93be4-111">`FullyOptimized`: The instance builds indexes for the hierarchy to improve query performance.</span></span> <span data-ttu-id="93be4-112">Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="93be4-112">This is the default value.</span></span><br /><br /> <span data-ttu-id="93be4-113">`NotOptimized`: Durch die Instanz werden keine zusätzlichen Indizes erstellt.</span><span class="sxs-lookup"><span data-stu-id="93be4-113">`NotOptimized`: The instance does not build additional indexes.</span></span>|  
|`Visible`|<span data-ttu-id="93be4-114">Beschreibt die Sichtbarkeit der Cubehierarchie.</span><span class="sxs-lookup"><span data-stu-id="93be4-114">Determines the visibility of the cube hierarchy.</span></span> <span data-ttu-id="93be4-115">Standardwert: `True`.</span><span class="sxs-lookup"><span data-stu-id="93be4-115">The default value is `True`.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="93be4-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="93be4-116">See Also</span></span>  
 [<span data-ttu-id="93be4-117">Benutzerhierarchien</span><span class="sxs-lookup"><span data-stu-id="93be4-117">User Hierarchies</span></span>](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies.md)  
  
  
