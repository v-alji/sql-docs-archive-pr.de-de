---
title: Aggregations Verwendung überprüfen (Aggregations Entwurfs-Assistent) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.aggregationdesignwizard.reviewusage.f1
ms.assetid: 107ee872-3df2-4931-b56c-af11e38f6745
author: minewiskan
ms.author: owend
ms.openlocfilehash: afbb02dae64f3f7ebd57065c3ff8a7d1e202dcf2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610132"
---
# <a name="review-aggregation-usage-aggregation-design-wizard"></a><span data-ttu-id="61af9-102">Aggregationsverwendung überprüfen (Aggregationsentwurfs-Assistent)</span><span class="sxs-lookup"><span data-stu-id="61af9-102">Review Aggregation Usage (Aggregation Design Wizard)</span></span>
  <span data-ttu-id="61af9-103">Mithilfe der Seite **Aggregationsverwendung überprüfen** können Sie die Einstellungen für die Aggregationsverwendung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="61af9-103">Use the **Review Aggregation Usage** page to configure aggregation usage settings.</span></span>  
  
## <a name="options"></a><span data-ttu-id="61af9-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="61af9-104">Options</span></span>  
 <span data-ttu-id="61af9-105">**Standard**</span><span class="sxs-lookup"><span data-stu-id="61af9-105">**Default**</span></span>  
 <span data-ttu-id="61af9-106">Wählen Sie diese Option aus, um die Einstellung der Aggregationsverwendung für das Attribut auf den Standard festzulegen.</span><span class="sxs-lookup"><span data-stu-id="61af9-106">Select to set the aggregation usage setting for the attribute to Default.</span></span> <span data-ttu-id="61af9-107">Bei dieser Einstellung wendet der Designer eine Standardregel basierend auf dem Typ des Attributs und der Dimension an.</span><span class="sxs-lookup"><span data-stu-id="61af9-107">By using this setting, the designer applies a default rule based on the type of attribute and dimension.</span></span>  
  
 `Full`  
 <span data-ttu-id="61af9-108">Wählen Sie diese Option aus, um die Aggregationsverwendung für das Attribut auf `Full` festzulegen.</span><span class="sxs-lookup"><span data-stu-id="61af9-108">Select to set the aggregation usage setting for the attribute to `Full`.</span></span> <span data-ttu-id="61af9-109">Bei Verwendung dieser Einstellung muss jede Aggregation für den Cube dieses Attribut oder ein verknüpftes Attribut enthalten, das sich weiter unten in der Attributkette befindet.</span><span class="sxs-lookup"><span data-stu-id="61af9-109">By using this setting, every aggregation for the cube must include this attribute or a related attribute that is lower in the attribute chain.</span></span> <span data-ttu-id="61af9-110">Die Einstellung `Full` für die Aggregationsverwendung sollte vermieden werden, wenn ein Attribut viele Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="61af9-110">The `Full` aggregation usage setting should be avoided when an attribute contains many members.</span></span> <span data-ttu-id="61af9-111">Falls diese Einstellung für mehrere Attribute oder für Attribute definiert ist, die über viele Elemente verfügen, kann hierdurch aufgrund einer Größenüberschreitung der Entwurf von Aggregationen verhindert werden.</span><span class="sxs-lookup"><span data-stu-id="61af9-111">If specified for multiple attributes or attributes that have many members, this setting might prevent aggregations from being designed because of excessive size.</span></span>  
  
 <span data-ttu-id="61af9-112">**None**</span><span class="sxs-lookup"><span data-stu-id="61af9-112">**None**</span></span>  
 <span data-ttu-id="61af9-113">Wählen Sie diese Option aus, um keine Aggregationsverwendung für das Attribut festzulegen.</span><span class="sxs-lookup"><span data-stu-id="61af9-113">Select to set the aggregation usage setting for the attribute to None.</span></span> <span data-ttu-id="61af9-114">Wird diese Einstellung verwendet, kann keine Aggregation für den Cube dieses Attribut enthalten.</span><span class="sxs-lookup"><span data-stu-id="61af9-114">By using this setting, no aggregation for the cube can include this attribute.</span></span>  
  
 `Unrestricted`  
 <span data-ttu-id="61af9-115">Wählen Sie diese Option aus, um die Aggregationsverwendung für das Attribut auf `Unrestricted` festzulegen.</span><span class="sxs-lookup"><span data-stu-id="61af9-115">Select to set the aggregation usage setting for the attribute to `Unrestricted`.</span></span> <span data-ttu-id="61af9-116">Bei Verwendung dieser Einstellung werden keine Einschränkungen auf den Aggregations-Designer angewendet, das Attribut muss aber dennoch ausgewertet werden, um festzustellen, ob es sich um einen wertvollen Aggregationskandidaten handelt.</span><span class="sxs-lookup"><span data-stu-id="61af9-116">By using this setting, no restrictions are put on the aggregation designer; however, the attribute must still be evaluated to determine whether it is a valuable aggregation candidate.</span></span>  
  
 <span data-ttu-id="61af9-117">**Alle als Standard festlegen**</span><span class="sxs-lookup"><span data-stu-id="61af9-117">**Set All to Default**</span></span>  
 <span data-ttu-id="61af9-118">Wählen Sie diese Option aus, um die Einstellungen der Aggregationsverwendung für alle Attribute auf den Standard festzulegen.</span><span class="sxs-lookup"><span data-stu-id="61af9-118">Select to set the aggregation usage settings for all attributes to Default.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61af9-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="61af9-119">See Also</span></span>  
 <span data-ttu-id="61af9-120">[Aggregations Entwurfs-Assistent F1-Hilfe](aggregation-design-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="61af9-120">[Aggregation Design Wizard F1 Help](aggregation-design-wizard-f1-help.md) </span></span>  
 [<span data-ttu-id="61af9-121">Analysis Services Assistenten &#40;Mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="61af9-121">Analysis Services Wizards &#40;Multidimensional Data&#41;</span></span>](analysis-services-wizards-multidimensional-data.md)  
  
  
