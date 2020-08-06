---
title: 'Lektion 3: Ändern von Measures, Attributen und Hierarchien | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 17d243cb-9bfb-43d7-8e6f-4d601fd62150
author: minewiskan
ms.author: owend
ms.openlocfilehash: c410136540a0ba85d50fbabc8b2d3c52be1823f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619427"
---
# <a name="lesson-3-modifying-measures-attributes-and-hierarchies"></a><span data-ttu-id="86bc3-102">Lektion 3: Ändern von Measures, Attributen und Hierarchien</span><span class="sxs-lookup"><span data-stu-id="86bc3-102">Lesson 3: Modifying Measures, Attributes and Hierarchies</span></span>
  <span data-ttu-id="86bc3-103">Nach dem Definieren des Anfangscubes können Sie den Cube nun besser verwendbar und benutzerfreundlicher machen.</span><span class="sxs-lookup"><span data-stu-id="86bc3-103">After defining your initial cube, you are ready to improve the usefulness and friendliness of the cube.</span></span> <span data-ttu-id="86bc3-104">Fügen Sie zu diesem Zweck Hierarchien hinzu, die die Navigation und Aggregation auf verschiedenen Ebenen unterstützen, wenden Sie Formate auf bestimmte Measures an und definieren Sie Berechnungen und Beziehungen.</span><span class="sxs-lookup"><span data-stu-id="86bc3-104">You can do this by adding hierarchies that support navigation and aggregation at various levels, by applying formats to specific measure, and by defining calculations and relationships.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="86bc3-105">Für alle Lektionen in diesem Lernprogramm sind abgeschlossene Projekte online verfügbar.</span><span class="sxs-lookup"><span data-stu-id="86bc3-105">Completed projects for all of the lessons in this tutorial are available online.</span></span> <span data-ttu-id="86bc3-106">Sie können jede Lektion aufrufen, indem Sie ein abgeschlossenes Projekt aus der vorherigen Lektion als Ausgangspunkt verwenden.</span><span class="sxs-lookup"><span data-stu-id="86bc3-106">You can jump ahead to any lesson by using the completed project from the previous lesson as a starting point.</span></span> <span data-ttu-id="86bc3-107">[Klicken Sie hier](https://go.microsoft.com/fwlink/?LinkID=221866) , um die Beispielprojekte für dieses Lernprogramm herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="86bc3-107">[Click here](https://go.microsoft.com/fwlink/?LinkID=221866) to download the sample projects that go with this tutorial.</span></span>  
  
 <span data-ttu-id="86bc3-108">Diese Lektion enthält die folgenden Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="86bc3-108">This lesson contains the following tasks:</span></span>  
  
 [<span data-ttu-id="86bc3-109">Ändern von Measures</span><span class="sxs-lookup"><span data-stu-id="86bc3-109">Modifying Measures</span></span>](lesson-3-1-modifying-measures.md)  
 <span data-ttu-id="86bc3-110">In dieser Aufgabe geben Sie Formatierungseigenschaften für die Währungs- und Prozentsatzmeasures im [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial-Cube an.</span><span class="sxs-lookup"><span data-stu-id="86bc3-110">In this task, you specify formatting properties for the currency and percentage measures in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube.</span></span>  
  
 [<span data-ttu-id="86bc3-111">Ändern der Customer-Dimension</span><span class="sxs-lookup"><span data-stu-id="86bc3-111">Modifying the Customer Dimension</span></span>](lesson-3-2-modifying-the-customer-dimension.md)  
 <span data-ttu-id="86bc3-112">In dieser Aufgabe definieren Sie eine Benutzerhierarchie, erstellen benannte Berechnungen, ändern Attribute, von denen benannte Berechnungen verwendet werden sollen, und gruppieren Attribute und Benutzerhierarchien in Anzeigeordner.</span><span class="sxs-lookup"><span data-stu-id="86bc3-112">In this task, you define a user hierarchy, create named calculations, modify attributes to use named calculations, and group attributes and user hierarchies into display folders.</span></span>  
  
 [<span data-ttu-id="86bc3-113">Ändern der Product-Dimension</span><span class="sxs-lookup"><span data-stu-id="86bc3-113">Modifying the Product Dimension</span></span>](lesson-3-3-modifying-the-product-dimension.md)  
 <span data-ttu-id="86bc3-114">In dieser Aufgabe definieren Sie eine Benutzerhierarchie, erstellen benannte Berechnungen, definieren den Elementnamen Alle und definieren Anzeigeordner.</span><span class="sxs-lookup"><span data-stu-id="86bc3-114">In this task, you define a user hierarchy, create named calculations, define the All member name, and define display folders.</span></span>  
  
 [<span data-ttu-id="86bc3-115">Ändern der Date-Dimension</span><span class="sxs-lookup"><span data-stu-id="86bc3-115">Modifying the Date Dimension</span></span>](lesson-3-4-modifying-the-date-dimension.md)  
 <span data-ttu-id="86bc3-116">In dieser Aufgabe definieren Sie eine Benutzerhierarchie, ändern Attributelementnamen und verwenden zusammengesetzte Schlüssel, um eindeutige Attributelemente anzugeben.</span><span class="sxs-lookup"><span data-stu-id="86bc3-116">In this task, you define a user hierarchy, modify attribute member names, and use composite keys to specify unique attribute members.</span></span>  
  
 [<span data-ttu-id="86bc3-117">Durchsuchen des bereitgestellten Cubes</span><span class="sxs-lookup"><span data-stu-id="86bc3-117">Browsing the Deployed Cube</span></span>](lesson-3-5-browsing-the-deployed-cube.md)  
 <span data-ttu-id="86bc3-118">In dieser Aufgabe durchsuchen Sie Cube- und Dimensionsdaten mithilfe des Browsers im Cube-Designer.</span><span class="sxs-lookup"><span data-stu-id="86bc3-118">In this task, you browse cube data by using the browser in Cube Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86bc3-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="86bc3-119">See Also</span></span>  
 <span data-ttu-id="86bc3-120">[Analysis Services Tutorial-Szenario](analysis-services-tutorial-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="86bc3-120">[Analysis Services Tutorial Scenario](analysis-services-tutorial-scenario.md) </span></span>  
 [<span data-ttu-id="86bc3-121">Mehrdimensionale Modellierung &#40;Adventure Works-Tutorial&#41;</span><span class="sxs-lookup"><span data-stu-id="86bc3-121">Multidimensional Modeling &#40;Adventure Works Tutorial&#41;</span></span>](multidimensional-modeling-adventure-works-tutorial.md)  
  
  
