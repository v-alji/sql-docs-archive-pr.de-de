---
title: Erstellungs Methode auswählen (Cube-Assistent) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubewizard.cubedefinition.f1
ms.assetid: 985d3b5b-7891-465b-862d-f7e75431b342
author: minewiskan
ms.author: owend
ms.openlocfilehash: c8c4d611e00a2b3f5d115ea5749b1e494a44bf57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621192"
---
# <a name="select-creation-method-cube-wizard"></a><span data-ttu-id="45dd4-102">Erstellungsmethode auswählen (Cube-Assistent)</span><span class="sxs-lookup"><span data-stu-id="45dd4-102">Select Creation Method (Cube Wizard)</span></span>
  <span data-ttu-id="45dd4-103">Auf der Seite **Erstellungsmethode auswählen** können Sie angeben, wie der Cube erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="45dd4-103">Use the **Select Creation Method** page to specify how to create the cube.</span></span>  
  
## <a name="options"></a><span data-ttu-id="45dd4-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="45dd4-104">Options</span></span>  
 <span data-ttu-id="45dd4-105">**Vorhandene Tabellen verwenden**</span><span class="sxs-lookup"><span data-stu-id="45dd4-105">**Use existing tables**</span></span>  
 <span data-ttu-id="45dd4-106">Wählen Sie diese Option aus, um einen Cube mithilfe vorhandener Tabellen in einer Datenquelle zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="45dd4-106">Select to create a cube by using existing tables in a data source.</span></span> <span data-ttu-id="45dd4-107">Der Assistent führt Sie durch den Vorgang der Auswahl und Definition von Measuregruppen und Dimensionen anhand vorhandener Tabellen zur Erstellung des neuen Cubes.</span><span class="sxs-lookup"><span data-stu-id="45dd4-107">The wizard will guide you through the process of selecting and defining measure groups and dimensions based on existing tables to build your new cube.</span></span>  
  
 <span data-ttu-id="45dd4-108">**Leeren Cube erstellen**</span><span class="sxs-lookup"><span data-stu-id="45dd4-108">**Create an empty cube**</span></span>  
 <span data-ttu-id="45dd4-109">Wählen Sie diese Option aus, um einen leeren Cube zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="45dd4-109">Select to create an empty cube.</span></span> <span data-ttu-id="45dd4-110">Diese Option ist dann hilfreich, wenn Sie alles manuell erstellen möchten, oder wenn es sich bei allen Measuregruppen im Cube um verknüpfte Measuregruppen handelt.</span><span class="sxs-lookup"><span data-stu-id="45dd4-110">This option is useful when you want to create everything manually, or when all measure groups in the cube are linked measure groups.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="45dd4-111">Diese Option ist nur dann verfügbar, wenn Sie mit einem [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Projekt arbeiten, aber nicht dann, wenn Sie direkt mit einer [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Datenbank verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="45dd4-111">This option is only available when you are working with an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project and not when you are connected directly to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="45dd4-112">**Tabellen in der Datenquelle generieren**</span><span class="sxs-lookup"><span data-stu-id="45dd4-112">**Generate tables in the data source**</span></span>  
 <span data-ttu-id="45dd4-113">Wählen Sie diese Option aus, um zuerst einen Cube zu erstellen und anschließend anhand der Cubedefinition neue Tabellen in der Datenquelle zu generieren.</span><span class="sxs-lookup"><span data-stu-id="45dd4-113">Select to create a cube first and then generate new tables in the data source based on the cube definition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="45dd4-114">Um diese Option nutzen zu können, müssen Sie über die Berechtigung zum Erstellen von Objekten in der zugrunde liegenden Datenquelle verfügen.</span><span class="sxs-lookup"><span data-stu-id="45dd4-114">To use this option, you must have permission to create objects in the underlying data source.</span></span>  
  
 <span data-ttu-id="45dd4-115">Bei Auswahl dieser Option ist auch die Option **Vorlage** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="45dd4-115">Selecting this option will make the **Template** option available.</span></span>  
  
 <span data-ttu-id="45dd4-116">**Vorlage**</span><span class="sxs-lookup"><span data-stu-id="45dd4-116">**Template**</span></span>  
 <span data-ttu-id="45dd4-117">Wählen Sie die Vorlage aus, die Sie zum Erstellen des Cubes verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="45dd4-117">Select the template that you want to use to create the cube.</span></span> <span data-ttu-id="45dd4-118">Vorlagen enthalten einen Satz von Definitionen, die auf einen bestimmten geschäftlichen Zweck ausgerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="45dd4-118">Templates provide a set of definitions oriented towards a specific business purpose.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="45dd4-119">Diese Option ist nur verfügbar, wenn die Option **Tabelle in der Datenquelle generieren** ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="45dd4-119">This option is only available when the **Generate tables in the data source** option has been selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45dd4-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="45dd4-120">See Also</span></span>  
 <span data-ttu-id="45dd4-121">[Cubeobjekte &#40;Analysis Services Mehrdimensionale Daten&#41;](multidimensional-models-olap-logical-cube-objects/cube-objects-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="45dd4-121">[Cube Objects &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-cube-objects/cube-objects-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="45dd4-122">[Cubes in mehrdimensionalen Modellen](multidimensional-models/cubes-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="45dd4-122">[Cubes in Multidimensional Models](multidimensional-models/cubes-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="45dd4-123">Dimensionen in mehrdimensionalen Modellen</span><span class="sxs-lookup"><span data-stu-id="45dd4-123">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
