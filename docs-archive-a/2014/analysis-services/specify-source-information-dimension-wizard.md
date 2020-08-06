---
title: Quell Informationen angeben (Dimensions-Assistent) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensionwizard.dimensionmaintable.f1
ms.assetid: 0538b490-5185-49e1-a783-4ce3539a0de5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 99bbaac0bdf24a18dcde455e779f056b98106dc4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620548"
---
# <a name="specify-source-information-dimension-wizard"></a><span data-ttu-id="4abad-102">Quellinformationen angeben (Dimensions-Assistent)</span><span class="sxs-lookup"><span data-stu-id="4abad-102">Specify Source Information (Dimension Wizard)</span></span>
  <span data-ttu-id="4abad-103">Mithilfe der Seite **Hauptdimensionstabelle auswählen** können Sie die Datenquellensicht, die Hauptdimensionstabelle, die Schlüsselspalten und die Elementnamenspalte für die zu erstellende Dimension auswählen.</span><span class="sxs-lookup"><span data-stu-id="4abad-103">Use the **Select the Main Dimension Table** page to select the data source view, main dimension table, key columns, and member name column for the dimension to be created.</span></span>  
  
 <span data-ttu-id="4abad-104">**So öffnen Sie den Dimensions-Assistenten**</span><span class="sxs-lookup"><span data-stu-id="4abad-104">**To open the Dimension Wizard**</span></span>  
  
-   <span data-ttu-id="4abad-105">Klicken Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]im **Projektmappen-Explorer**mit der rechten Maustaste auf den Ordner **Dimensionen** eines [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Projekts, und klicken Sie anschließend auf **Neue Dimension**.</span><span class="sxs-lookup"><span data-stu-id="4abad-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], in **Solution Explorer**, right-click the **Dimensions** folder for an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, and then click **New Dimension**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="4abad-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="4abad-106">Options</span></span>  
 <span data-ttu-id="4abad-107">**Datenquellen Sicht**</span><span class="sxs-lookup"><span data-stu-id="4abad-107">**Data source view**</span></span>  
 <span data-ttu-id="4abad-108">Wählen Sie eine Datenquellensicht aus.</span><span class="sxs-lookup"><span data-stu-id="4abad-108">Select a data source view.</span></span>  
  
 <span data-ttu-id="4abad-109">**Haupttabelle**</span><span class="sxs-lookup"><span data-stu-id="4abad-109">**Main table**</span></span>  
 <span data-ttu-id="4abad-110">Wählen Sie eine Tabelle aus der ausgewählten Datenquellensicht aus, die als Haupttabelle für die Dimension verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4abad-110">Select a table from the selected data source view to use as the main table for the dimension.</span></span>  
  
 <span data-ttu-id="4abad-111">**Schlüssel Spalten**</span><span class="sxs-lookup"><span data-stu-id="4abad-111">**Key columns**</span></span>  
 <span data-ttu-id="4abad-112">Wählen Sie die Schlüsselspalten aus der in **Haupttabelle** angegebenen Tabelle für das Schlüsselattribut der Dimension aus.</span><span class="sxs-lookup"><span data-stu-id="4abad-112">Select the key columns from the table specified in **Main table** for the key attribute of the dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4abad-113">Es können mehrere Spalten ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="4abad-113">More than one column can be selected.</span></span> <span data-ttu-id="4abad-114">Wenn eine Tabelle einen zusammengesetzten Primärschlüssel enthält, wählen Sie alle im zusammengesetzten Primärschlüssel enthaltenen Spalten aus.</span><span class="sxs-lookup"><span data-stu-id="4abad-114">If the table contains a composite primary key, select all the columns included in the composite primary key.</span></span> <span data-ttu-id="4abad-115">Wichtig ist die Reihenfolge der Schlüsselspalten.</span><span class="sxs-lookup"><span data-stu-id="4abad-115">The order of the key columns is important.</span></span>  
  
 <span data-ttu-id="4abad-116">**Namensspalte**</span><span class="sxs-lookup"><span data-stu-id="4abad-116">**Name column**</span></span>  
 <span data-ttu-id="4abad-117">Wählen Sie die Spalte aus der in **Haupttabelle** angegebenen Tabelle aus, die die Elementnamen für die Dimension enthält.</span><span class="sxs-lookup"><span data-stu-id="4abad-117">Select the column from the table specified in **Main table** that provides the member names for the dimension.</span></span> <span data-ttu-id="4abad-118">Es muss eine Namensspalte angegeben werden, wenn ein zusammengesetzter Schlüssel verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4abad-118">A name column must be specified when a composite key is used.</span></span> <span data-ttu-id="4abad-119">Sie erstellen die Namensspalte für einen zusammengesetzten Schlüssel, indem Sie eine benannte Berechnung in der Datenquellensicht definieren, mit der die angegebenen Schlüsselspalten verkettet werden.</span><span class="sxs-lookup"><span data-stu-id="4abad-119">To create a name column for a composite key, we recommend that you create a named calculation in the data source view that concatenates the specified key columns.</span></span> <span data-ttu-id="4abad-120">Wenn ein einzelner Schlüssel verwendet wird, ist die Namensspalte optional.</span><span class="sxs-lookup"><span data-stu-id="4abad-120">When a single key is used, the name column is optional.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4abad-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4abad-121">See Also</span></span>  
 <span data-ttu-id="4abad-122">[Dimensions-Assistent F1-Hilfe](dimension-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="4abad-122">[Dimension Wizard F1 Help](dimension-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="4abad-123">[Dimensionen &#40;Analysis Services Mehrdimensionale Daten&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="4abad-123">[Dimensions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="4abad-124">Dimensionen in mehrdimensionalen Modellen</span><span class="sxs-lookup"><span data-stu-id="4abad-124">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
