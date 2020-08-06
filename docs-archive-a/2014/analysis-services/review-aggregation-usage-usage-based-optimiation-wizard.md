---
title: Aggregations Verwendung überprüfen (Assistent für Verwendungs basierte Optimierung) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.storagedesignwizard.reviewaggregationusage.f1
ms.assetid: 49ce2094-c4dc-4e46-8cef-c17c5db084ca
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5ef9f900e64858515db226d1f9b864874a4ba827
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610131"
---
# <a name="review-aggregation-usage-usage-based-optimiation-wizard"></a><span data-ttu-id="c77a3-102">Aggregationsverwendung überprüfen (Assistent für verwendungsbasierte Optimierung)</span><span class="sxs-lookup"><span data-stu-id="c77a3-102">Review Aggregation Usage (Usage-Based Optimiation Wizard)</span></span>
  <span data-ttu-id="c77a3-103">Mithilfe der Seite **Aggregationsverwendung überprüfen** können Sie die Einstellungen für die Aggregationsverwendung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c77a3-103">Use the **Review Aggregation Usage** page to configure aggregation usage settings.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c77a3-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="c77a3-104">Options</span></span>  
 <span data-ttu-id="c77a3-105">**Standard**</span><span class="sxs-lookup"><span data-stu-id="c77a3-105">**Default**</span></span>  
 <span data-ttu-id="c77a3-106">Wählen Sie diese Option aus, um die Einstellung der Aggregationsverwendung für das Attribut auf den Standard festzulegen.</span><span class="sxs-lookup"><span data-stu-id="c77a3-106">Select to set the aggregation usage setting for the attribute to Default.</span></span> <span data-ttu-id="c77a3-107">Bei dieser Einstellung wendet der Designer eine Standardregel basierend auf dem Typ des Attributs und der Dimension an.</span><span class="sxs-lookup"><span data-stu-id="c77a3-107">By using this setting, the designer applies a default rule based on the type of attribute and dimension.</span></span>  
  
 <span data-ttu-id="c77a3-108">**Vollständig**</span><span class="sxs-lookup"><span data-stu-id="c77a3-108">**Full**</span></span>  
 <span data-ttu-id="c77a3-109">Wählen Sie diese Option aus, um die vollständige Aggregationsverwendung für das Attribut festzulegen.</span><span class="sxs-lookup"><span data-stu-id="c77a3-109">Select to set the aggregation usage setting for the attribute to Full.</span></span> <span data-ttu-id="c77a3-110">Bei Verwendung dieser Einstellung muss jede Aggregation für den Cube dieses Attribut oder ein verknüpftes Attribut enthalten, das sich weiter unten in der Attributkette befindet.</span><span class="sxs-lookup"><span data-stu-id="c77a3-110">By using this setting, every aggregation for the cube must include this attribute or a related attribute that is lower in the attribute chain.</span></span> <span data-ttu-id="c77a3-111">Die Einstellung für die vollständige Aggregationsverwendung sollte vermieden werden, wenn ein Attribut viele Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="c77a3-111">The Full aggregation usage setting should be avoided when an attribute contains many members.</span></span> <span data-ttu-id="c77a3-112">Falls diese Einstellung für mehrere Attribute oder für Attribute definiert ist, die über viele Elemente verfügen, kann hierdurch aufgrund einer Größenüberschreitung der Entwurf von Aggregationen verhindert werden.</span><span class="sxs-lookup"><span data-stu-id="c77a3-112">If specified for multiple attributes or attributes that have many members, this setting might prevent aggregations from being designed because of excessive size.</span></span>  
  
 <span data-ttu-id="c77a3-113">**None**</span><span class="sxs-lookup"><span data-stu-id="c77a3-113">**None**</span></span>  
 <span data-ttu-id="c77a3-114">Wählen Sie diese Option aus, um keine Aggregationsverwendung für das Attribut festzulegen.</span><span class="sxs-lookup"><span data-stu-id="c77a3-114">Select to set the aggregation usage setting for the attribute to None.</span></span> <span data-ttu-id="c77a3-115">Wird diese Einstellung verwendet, kann keine Aggregation für den Cube dieses Attribut enthalten.</span><span class="sxs-lookup"><span data-stu-id="c77a3-115">By using this setting, no aggregation for the cube can include this attribute.</span></span>  
  
 <span data-ttu-id="c77a3-116">**Unbegrenzt**</span><span class="sxs-lookup"><span data-stu-id="c77a3-116">**Unrestricted**</span></span>  
 <span data-ttu-id="c77a3-117">Wählen Sie diese Option aus, um eine uneingeschränkte Aggregationsverwendung für das Attribut festzulegen.</span><span class="sxs-lookup"><span data-stu-id="c77a3-117">Select to set the aggregation usage setting for the attribute to Unrestricted.</span></span> <span data-ttu-id="c77a3-118">Wird diese Einstellung verwendet, werden keine Einschränkungen auf den Aggregations-Designer angwendet.</span><span class="sxs-lookup"><span data-stu-id="c77a3-118">By using this setting, no restrictions are put on the aggregation designer.</span></span> <span data-ttu-id="c77a3-119">Das Attribut muss aber dennoch ausgewertet werden, um festzustellen, ob es sich um einen wertvollen Aggregationskandidaten handelt.</span><span class="sxs-lookup"><span data-stu-id="c77a3-119">However, the attribute must still be evaluated to determine whether it is a valuable aggregation candidate.</span></span>  
  
 <span data-ttu-id="c77a3-120">**Alle als Standard festlegen**</span><span class="sxs-lookup"><span data-stu-id="c77a3-120">**Set All to Default**</span></span>  
 <span data-ttu-id="c77a3-121">Wählen Sie diese Option aus, um die Einstellungen der Aggregationsverwendung für alle Attribute auf den Standard festzulegen.</span><span class="sxs-lookup"><span data-stu-id="c77a3-121">Select to set the aggregation usage settings for all attributes to Default.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c77a3-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c77a3-122">See Also</span></span>  
 <span data-ttu-id="c77a3-123">[Aggregations Entwurfs-Assistent F1-Hilfe](aggregation-design-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="c77a3-123">[Aggregation Design Wizard F1 Help](aggregation-design-wizard-f1-help.md) </span></span>  
 [<span data-ttu-id="c77a3-124">Analysis Services Assistenten &#40;Mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="c77a3-124">Analysis Services Wizards &#40;Multidimensional Data&#41;</span></span>](analysis-services-wizards-multidimensional-data.md)  
  
  
