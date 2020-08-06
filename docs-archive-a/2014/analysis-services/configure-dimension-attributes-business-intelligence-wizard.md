---
title: Dimensions Attribute konfigurieren (Business Intelligence-Assistent) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.biwizard.acctintelligence.selectattributes.f1
ms.assetid: 3d046e63-bcb1-4ab1-9c37-652463fa68c3
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1d2e9bc83b7a6d83b6d2808b472d67169266ff07
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610246"
---
# <a name="configure-dimension-attributes-business-intelligence-wizard"></a><span data-ttu-id="765d7-102">Dimensionsattribute konfigurieren (Business Intelligence-Assistent)</span><span class="sxs-lookup"><span data-stu-id="765d7-102">Configure Dimension Attributes (Business Intelligence Wizard)</span></span>
  <span data-ttu-id="765d7-103">Mithilfe der Seite **Dimensionsattribute konfigurieren** können Sie die Dimensionsattribute den Typen von Attributen zuordnen, die von [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] verwendet werden, um Attribute für Kontodimensionen zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="765d7-103">Use the **Configure Dimension Attributes** page to map the dimension attributes to the attribute types that [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] uses to identify attributes for account dimensions.</span></span>  
  
## <a name="options"></a><span data-ttu-id="765d7-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="765d7-104">Options</span></span>  
 <span data-ttu-id="765d7-105">**Dimensionstyp**</span><span class="sxs-lookup"><span data-stu-id="765d7-105">**Dimension type**</span></span>  
 <span data-ttu-id="765d7-106">Zeigt den ausgewählten Dimensionstyp an.</span><span class="sxs-lookup"><span data-stu-id="765d7-106">Displays the selected dimension type.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="765d7-107">Diese Option ist nicht verfügbar, da die- `Type` Eigenschaft der Dimension für Konto Dimensionen nicht in einen anderen Wert als *Account* geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="765d7-107">This option is not available because the `Type` property of the dimension cannot be changed to a value other than *Account* for account dimensions.</span></span>  
  
 <span data-ttu-id="765d7-108">**Dimensionsattribute**</span><span class="sxs-lookup"><span data-stu-id="765d7-108">**Dimension attributes**</span></span>  
 <span data-ttu-id="765d7-109">Zeigt die gültigen Typen von Attributen an, die vorhandenen Dimensionsattributen in der Dimension zugeordnet werden können.</span><span class="sxs-lookup"><span data-stu-id="765d7-109">Displays the valid attribute types that can be mapped to existing dimension attributes in the dimension.</span></span>  
  
 <span data-ttu-id="765d7-110">**Darunter**</span><span class="sxs-lookup"><span data-stu-id="765d7-110">**Include**</span></span>  
 <span data-ttu-id="765d7-111">Aktivieren Sie ein Kontrollkästchen, um den entsprechenden Attributtyp in der Dimension einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="765d7-111">Select a check box to include the corresponding attribute type in the dimension.</span></span>  
  
 <span data-ttu-id="765d7-112">**Attributtyp**</span><span class="sxs-lookup"><span data-stu-id="765d7-112">**Attribute Type**</span></span>  
 <span data-ttu-id="765d7-113">Führt die Attributtypen auf, die vorhandenen Dimensionsattributen in der Dimension zugeordnet werden können.</span><span class="sxs-lookup"><span data-stu-id="765d7-113">Lists the attribute types that can be mapped to existing dimension attributes in the dimension.</span></span>  
  
 <span data-ttu-id="765d7-114">**Dimensionsattribut**</span><span class="sxs-lookup"><span data-stu-id="765d7-114">**Dimension Attribute**</span></span>  
 <span data-ttu-id="765d7-115">Wählen Sie das Dimensionsattribut aus, das dem entsprechenden Attributtyp zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="765d7-115">Select the dimension attribute that should be mapped to the corresponding attribute type.</span></span>  
  
 <span data-ttu-id="765d7-116">**Measures anhand des Kontotyps als semiadditiv festlegen**</span><span class="sxs-lookup"><span data-stu-id="765d7-116">**Set measures to be semiadditive based on account type**</span></span>  
 <span data-ttu-id="765d7-117">Wählen Sie diese Option, um alle dieser Dimension zugeordneten Measures zu ändern, die nach Kontotyp aggregiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="765d7-117">Select to change every measure associated with this dimension to be aggregated by account type.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="765d7-118">Diese Option wird nicht angezeigt, wenn der Business Intelligence-Assistent vom Dimensions-Designer aus oder durch Klicken mit der rechten Maustaste auf eine Dimension im Projektmappen-Explorer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="765d7-118">This option does not appear if the Business Intelligence Wizard was started from Dimension Designer or by right-clicking a dimension in Solution Explorer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="765d7-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="765d7-119">See Also</span></span>  
 <span data-ttu-id="765d7-120">[Business Intelligence Wizard (F1-Hilfe)](business-intelligence-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="765d7-120">[Business Intelligence Wizard F1 Help](business-intelligence-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="765d7-121">[Cube-Designer &#40;Analysis Services Mehrdimensionale Daten&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="765d7-121">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="765d7-122">Der Dimensions-Designer &#40;Analysis Services Mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="765d7-122">Dimension Designer &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimension-designer-analysis-services-multidimensional-data.md)  
  
  
