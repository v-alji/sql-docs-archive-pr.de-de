---
title: Datenquellen von vorhandenen Objekten (Datenquellen-Assistent) (Analysis Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.datasourcewizard.specifyobject.f1
ms.assetid: e6ef6dea-9db8-45c4-8959-f9febd7caf7b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 621c938f4902c95dee1e2fcccb0f292597a565f1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702111"
---
# <a name="data-sources-from-existing-objects-data-source-wizard-analysis-services"></a><span data-ttu-id="89a92-102">Datenquellen von vorhandenen Objekten (Datenquellen-Assistent) (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="89a92-102">Data sources from existing objects (Data Source Wizard) (Analysis Services)</span></span>
  <span data-ttu-id="89a92-103">Auf der Seite **Datenquellen von vorhandenen Objekten** können Sie eine vorhandene Datenquelle oder ein Projekt angeben, die/das als Grundlage der neuen Datenquelle verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="89a92-103">Use the **Data sources from existing objects** page to specify an existing data source or project on which to base the new data source.</span></span>  
  
## <a name="options"></a><span data-ttu-id="89a92-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="89a92-104">Options</span></span>  
 <span data-ttu-id="89a92-105">**Eine Datenquelle basierend auf einer in der Lösung vorhandenen Datenquelle erstellen**</span><span class="sxs-lookup"><span data-stu-id="89a92-105">**Create a data source based on an existing data source in your solution**</span></span>  
 <span data-ttu-id="89a92-106">Wählen Sie diese Option aus, um die neue Datenquelle auf der Grundlage einer in der Lösung vorhandenen Datenquelle zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="89a92-106">Select to base the new data source on an existing data source in the solution.</span></span> <span data-ttu-id="89a92-107">Wenn ein Projekt, das die neue Datenquelle verwendet, erstellt, aktualisiert oder bereitgestellt wird, werden von der neuen Datenquelle die Einstellungen aus der Datenbank übernommen, die bei Auswahl dieser Option angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="89a92-107">When a project that uses the new data source is built, refreshed, or deployed, the new data source acquires the settings from the data source you specify when you select this option.</span></span>  
  
 <span data-ttu-id="89a92-108">**Datenquelle**</span><span class="sxs-lookup"><span data-stu-id="89a92-108">**Data source**</span></span>  
 <span data-ttu-id="89a92-109">Wählen Sie in der Liste der Datenquellen, die nach Projekten gruppiert ist, eine Datenquelle aus, auf der die neue Datenquelle basieren soll.</span><span class="sxs-lookup"><span data-stu-id="89a92-109">Select a data source on which you want to base the new data source from the list of data sources, which is grouped by project.</span></span>  
  
 <span data-ttu-id="89a92-110">**Eine Datenquelle basierend auf einem Analysis Services-Projekt erstellen**</span><span class="sxs-lookup"><span data-stu-id="89a92-110">**Create a data source based on an Analysis Services project**</span></span>  
 <span data-ttu-id="89a92-111">Wählen Sie diese Option aus, um eine neue Datenquelle zu erstellen, die auf ein anderes [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Projekt in der aktuellen Lösung</span><span class="sxs-lookup"><span data-stu-id="89a92-111">Select to create a new data source that references another [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project in the current solution.</span></span> <span data-ttu-id="89a92-112">Die neue Datenquelle übernimmt die Einstellungen aus den `TargetServer`- und den `TargetDatabase`-Eigenschaften des ausgewählten Projekts.</span><span class="sxs-lookup"><span data-stu-id="89a92-112">The new data source acquires settings from the `TargetServer` and `TargetDatabase` properties of the selected project.</span></span> <span data-ttu-id="89a92-113">Wenn ein Projekt, das die neue Datenquelle verwendet, erstellt, aktualisiert oder bereitgestellt wird, werden von der neuen Datenquelle die Einstellungen aus der Datenbank übernommen, die bei Auswahl dieser Option angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="89a92-113">When a project that uses the new data source is built, refreshed, or deployed, the new data source acquires settings from the data source you specify when you select this option.</span></span>  
  
 <span data-ttu-id="89a92-114">**Projekt**</span><span class="sxs-lookup"><span data-stu-id="89a92-114">**Project**</span></span>  
 <span data-ttu-id="89a92-115">Wählen Sie das Projekt aus, auf das in der neuen Datenquelle verwiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="89a92-115">Select the project that you want to reference in the new data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89a92-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="89a92-116">See Also</span></span>  
 <span data-ttu-id="89a92-117">[Datenquellen-Assistent (F1-Hilfe &#40;Analysis Services&#41;](data-source-wizard-f1-help-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="89a92-117">[Data Source Wizard F1 Help &#40;Analysis Services&#41;](data-source-wizard-f1-help-analysis-services.md) </span></span>  
 <span data-ttu-id="89a92-118">[Datenquellen in mehrdimensionalen Modellen](multidimensional-models/data-sources-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="89a92-118">[Data Sources in Multidimensional Models](multidimensional-models/data-sources-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="89a92-119">Unterstützte Datenquellen &#40;mehrdimensionalen SSAS-&#41;</span><span class="sxs-lookup"><span data-stu-id="89a92-119">Data Sources Supported &#40;SSAS Multidimensional&#41;</span></span>](multidimensional-models/supported-data-sources-ssas-multidimensional.md)  
  
  
