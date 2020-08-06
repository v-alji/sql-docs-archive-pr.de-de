---
title: Dimensions Typen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- time dimensions [Analysis Services]
- quantitative dimensions [Analysis Services]
- BillOfMaterials dimension [Analysis Services]
- geography dimensions
- utility dimensions [Analysis Services]
- channel dimensions
- dimensions [Analysis Services], types
- products dimensions [Analysis Services]
- account dimensions [Analysis Services]
- organization dimensions
- currency dimensions [Analysis Services]
- rates dimensions
- promotion dimensions
- scenario dimensions [Analysis Services]
- customers dimensions [Analysis Services]
- Type property
ms.assetid: bd3195da-e762-4c98-b643-34c76e842343
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5e0c16a57081aa1d9ed3cc6964d1f17fa7135986
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622915"
---
# <a name="dimension-types"></a><span data-ttu-id="1d442-102">Dimensionstypen</span><span class="sxs-lookup"><span data-stu-id="1d442-102">Dimension Types</span></span>
  <span data-ttu-id="1d442-103">In der Einstellung der `Type`-Eigenschaft werden Informationen zum Inhalt einer Dimension für Server- und Clientanwendungen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="1d442-103">The `Type` property setting provides information about the contents of a dimension to server and client applications.</span></span> <span data-ttu-id="1d442-104">In einigen Fällen wird in der `Type`-Einstellung nur ein Hinweis für Clientanwendungen bereitgestellt, sie ist dann optional.</span><span class="sxs-lookup"><span data-stu-id="1d442-104">In some cases, the `Type` setting only provides guidance for client applications and is optional.</span></span> <span data-ttu-id="1d442-105">In anderen Fällen, z. B. für die `Accounts`- oder `Time`-Dimension, wird durch die Einstellungen der `Type`-Eigenschaft für die Dimension und ihre Attribute ein spezifisches serverbasiertes Verhalten festgelegt. Die Einstellungen können dann erforderlich sein, um ein bestimmtes Verhalten im Cube zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="1d442-105">In other cases, such as `Accounts` or `Time` dimensions, the `Type` property settings for the dimension and its attributes determine specific server-based behaviors and may be required to implement certain behaviors in the cube.</span></span> <span data-ttu-id="1d442-106">So kann z. B. die `Type`-Eigenschaft einer Dimension auf `Accounts` festgelegt werden, um den Clientanwendungen mitzuteilen, dass die Standarddimension Kontoattribute enthält.</span><span class="sxs-lookup"><span data-stu-id="1d442-106">For example, the `Type` property of a dimension can be set to `Accounts` to indicate to client applications that the standard dimension contains account attributes.</span></span> <span data-ttu-id="1d442-107">Weitere Informationen zu Zeit-, Konto-und Währungs Dimensionen finden Sie unter [Create a Date Type Dimension](../multidimensional-models/database-dimensions-create-a-date-type-dimension.md), [Create a Finance Account of Parent-Child Type Dimension](../multidimensional-models/database-dimensions-finance-account-of-parent-child-type.md)und [Create a Currency Type Dimension](../multidimensional-models/database-dimensions-create-a-currency-type-dimension.md).</span><span class="sxs-lookup"><span data-stu-id="1d442-107">For more information about time, account, and currency dimensions, see [Create a Date type Dimension](../multidimensional-models/database-dimensions-create-a-date-type-dimension.md), [Create a Finance Account of parent-child type Dimension](../multidimensional-models/database-dimensions-finance-account-of-parent-child-type.md), and [Create a Currency type Dimension](../multidimensional-models/database-dimensions-create-a-currency-type-dimension.md).</span></span>  
  
 <span data-ttu-id="1d442-108">Die Standardeinstellung für den Dimensionstyp ist `Regular`, sie bietet keine Informationen zum Inhalt der Dimension.</span><span class="sxs-lookup"><span data-stu-id="1d442-108">The default setting for the dimension type is `Regular`, which makes no assumptions about the contents of the dimension.</span></span> <span data-ttu-id="1d442-109">Das ist die Standardeinstellung für alle Dimensionen beim ersten Definieren einer Dimension, es sei denn, Sie haben beim Definieren der Dimension mithilfe des Dimensions-Assistenten `Time` angegeben.</span><span class="sxs-lookup"><span data-stu-id="1d442-109">This is the default setting for all dimensions when you initially define a dimension unless you specify `Time` when defining the dimension using the Dimension Wizard.</span></span> <span data-ttu-id="1d442-110">Sie sollten auch die Einstellung `Regular` für den Dimensionstyp beibehalten, wenn im Dimensions-Assistent kein geeigneter Typ aufgelistet wird.</span><span class="sxs-lookup"><span data-stu-id="1d442-110">You should also leave `Regular` as the dimension type if the Dimension Wizard does not list an appropriate type for Dimension type.</span></span>  
  
## <a name="available-dimension-types"></a><span data-ttu-id="1d442-111">Verfügbare Dimensionstypen</span><span class="sxs-lookup"><span data-stu-id="1d442-111">Available Dimension Types</span></span>  
 <span data-ttu-id="1d442-112">In der folgenden Tabelle werden die in verfügbaren Dimensions Typen beschrieben [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1d442-112">The following table describes the dimension types available in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
|<span data-ttu-id="1d442-113">Dimensionstyp</span><span class="sxs-lookup"><span data-stu-id="1d442-113">Dimension type</span></span>|<span data-ttu-id="1d442-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1d442-114">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="1d442-115">Regulär</span><span class="sxs-lookup"><span data-stu-id="1d442-115">Regular</span></span>|<span data-ttu-id="1d442-116">Eine Dimension, für die kein spezieller Dimensionstyp festgelegt wurde</span><span class="sxs-lookup"><span data-stu-id="1d442-116">A dimension whose type has not been set to a special dimension type.</span></span>|  
|<span data-ttu-id="1d442-117">Time</span><span class="sxs-lookup"><span data-stu-id="1d442-117">Time</span></span>|<span data-ttu-id="1d442-118">Eine Dimension, deren Attribute Zeiträume darstellen, z. B. Jahre, Semester, Quartale, Monate und Tage</span><span class="sxs-lookup"><span data-stu-id="1d442-118">A dimension whose attributes represent time periods, such as years, semesters, quarters, months, and days.</span></span>|  
|<span data-ttu-id="1d442-119">Organization</span><span class="sxs-lookup"><span data-stu-id="1d442-119">Organization</span></span>|<span data-ttu-id="1d442-120">Eine Dimension, deren Attribute organisatorische Informationen darstellen, z. B. Angestellte oder Tochterunternehmen</span><span class="sxs-lookup"><span data-stu-id="1d442-120">A dimension whose attributes represent organizational information, such as employees or subsidiaries.</span></span>|  
|<span data-ttu-id="1d442-121">Geografie</span><span class="sxs-lookup"><span data-stu-id="1d442-121">Geography</span></span>|<span data-ttu-id="1d442-122">Eine Dimension, deren Attribute geografische Informationen darstellen, z. B. Städte oder Postleitzahlen</span><span class="sxs-lookup"><span data-stu-id="1d442-122">A dimension whose attributes represent geographic information, such as cities or postal codes.</span></span>|  
|<span data-ttu-id="1d442-123">BillOfMaterials</span><span class="sxs-lookup"><span data-stu-id="1d442-123">BillOfMaterials</span></span>|<span data-ttu-id="1d442-124">Eine Dimension, deren Attribute Informationen zu Inventar oder Produktion darstellen, z. B. Stücklisten für Produkte</span><span class="sxs-lookup"><span data-stu-id="1d442-124">A dimension whose attributes represent inventory or manufacturing information, such as parts lists for products.</span></span>|  
|<span data-ttu-id="1d442-125">Konten</span><span class="sxs-lookup"><span data-stu-id="1d442-125">Accounts</span></span>|<span data-ttu-id="1d442-126">Eine Dimension, deren Attribute ein Kontodiagramm für Finanzberichte darstellen</span><span class="sxs-lookup"><span data-stu-id="1d442-126">A dimension whose attributes represent a chart of accounts for financial reporting purposes.</span></span>|  
|<span data-ttu-id="1d442-127">Kunden</span><span class="sxs-lookup"><span data-stu-id="1d442-127">Customers</span></span>|<span data-ttu-id="1d442-128">Eine Dimension, deren Attribute Kunden- oder Kontaktinformationen darstellen</span><span class="sxs-lookup"><span data-stu-id="1d442-128">A dimension whose attributes represent customer or contact information.</span></span>|  
|<span data-ttu-id="1d442-129">Produkte</span><span class="sxs-lookup"><span data-stu-id="1d442-129">Products</span></span>|<span data-ttu-id="1d442-130">Eine Dimension, deren Attribute Produktinformationen darstellen</span><span class="sxs-lookup"><span data-stu-id="1d442-130">A dimension whose attributes represent product information.</span></span>|  
|<span data-ttu-id="1d442-131">Szenario</span><span class="sxs-lookup"><span data-stu-id="1d442-131">Scenario</span></span>|<span data-ttu-id="1d442-132">Eine Dimension, deren Attribute Informationen für Planung oder strategische Analyse darstellen</span><span class="sxs-lookup"><span data-stu-id="1d442-132">A dimension whose attributes represent planning or strategic analysis information.</span></span>|  
|<span data-ttu-id="1d442-133">Quantitative</span><span class="sxs-lookup"><span data-stu-id="1d442-133">Quantitative</span></span>|<span data-ttu-id="1d442-134">Eine Dimension, deren Attribute quantitative Informationen darstellen</span><span class="sxs-lookup"><span data-stu-id="1d442-134">A dimension whose attributes represent quantitative information.</span></span>|  
|<span data-ttu-id="1d442-135">Hilfsprogramm</span><span class="sxs-lookup"><span data-stu-id="1d442-135">Utility</span></span>|<span data-ttu-id="1d442-136">Eine Dimension, deren Attribute verschiedene Informationen darstellen</span><span class="sxs-lookup"><span data-stu-id="1d442-136">A dimension whose attributes represent miscellaneous information.</span></span>|  
|<span data-ttu-id="1d442-137">Währung</span><span class="sxs-lookup"><span data-stu-id="1d442-137">Currency</span></span>|<span data-ttu-id="1d442-138">Dieser Dimensionstyp enthält Währungsdaten und Metadaten</span><span class="sxs-lookup"><span data-stu-id="1d442-138">This type of dimension contains currency data and metadata.</span></span>|  
|<span data-ttu-id="1d442-139">Rates</span><span class="sxs-lookup"><span data-stu-id="1d442-139">Rates</span></span>|<span data-ttu-id="1d442-140">Eine Dimension, deren Attribute Währungskursinformationen darstellen</span><span class="sxs-lookup"><span data-stu-id="1d442-140">A dimension whose attributes represent currency rate information.</span></span>|  
|<span data-ttu-id="1d442-141">Channel</span><span class="sxs-lookup"><span data-stu-id="1d442-141">Channel</span></span>|<span data-ttu-id="1d442-142">Eine Dimension, deren Attribute verschiedene Kanalinformationen darstellen</span><span class="sxs-lookup"><span data-stu-id="1d442-142">A dimension whose attributes represent channel information.</span></span>|  
|<span data-ttu-id="1d442-143">Promotion</span><span class="sxs-lookup"><span data-stu-id="1d442-143">Promotion</span></span>|<span data-ttu-id="1d442-144">Eine Dimension, deren Attribute verschiedene Marketinghöherstufungsinformationen darstellen</span><span class="sxs-lookup"><span data-stu-id="1d442-144">A dimension whose attributes represent marketing promotion information.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1d442-145">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1d442-145">See Also</span></span>  
 <span data-ttu-id="1d442-146">[Erstellen einer Dimension mithilfe einer vorhandenen Tabelle](../multidimensional-models/create-a-dimension-by-using-an-existing-table.md) </span><span class="sxs-lookup"><span data-stu-id="1d442-146">[Create a Dimension by Using an Existing Table](../multidimensional-models/create-a-dimension-by-using-an-existing-table.md) </span></span>  
 [<span data-ttu-id="1d442-147">Dimensionen &#40;Analysis Services – mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="1d442-147">Dimensions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimensions-analysis-services-multidimensional-data.md)  
  
  
