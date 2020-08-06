---
title: Erstellungs Methode auswählen (Dimensions-Assistent) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensionwizard.dimensiondefinition.f1
ms.assetid: 291b0b2d-a03a-4df6-82f7-90ad92d4d1cf
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6338a0bde7865482fb7a98d7ec36ba5a71feb806
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696213"
---
# <a name="select-creation-method-dimension-wizard"></a><span data-ttu-id="5f361-102">Erstellungsmethode auswählen (Dimensions-Assistent)</span><span class="sxs-lookup"><span data-stu-id="5f361-102">Select Creation Method (Dimension Wizard)</span></span>
  <span data-ttu-id="5f361-103">Auf der Seite **Erstellungsmethode auswählen** können Sie auswählen, wie die Dimension erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="5f361-103">Use the **Select Creation Method** page to select how to create the dimension.</span></span>  
  
 <span data-ttu-id="5f361-104">**So öffnen Sie den Dimensions-Assistenten**</span><span class="sxs-lookup"><span data-stu-id="5f361-104">**To open the Dimension Wizard**</span></span>  
  
-   <span data-ttu-id="5f361-105">Klicken Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]im **Projektmappen-Explorer**mit der rechten Maustaste auf den Ordner **Dimensionen** eines [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Projekts, und klicken Sie anschließend auf **Neue Dimension**.</span><span class="sxs-lookup"><span data-stu-id="5f361-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], in **Solution Explorer**, right-click the **Dimensions** folder for an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, and then click **New Dimension**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5f361-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="5f361-106">Options</span></span>  
 <span data-ttu-id="5f361-107">**Vorhandene Tabelle verwenden**</span><span class="sxs-lookup"><span data-stu-id="5f361-107">**Use an existing table**</span></span>  
 <span data-ttu-id="5f361-108">Erstellen Sie aus einer oder mehreren Tabellen einer Datenquelle eine Dimension.</span><span class="sxs-lookup"><span data-stu-id="5f361-108">Create a dimension from one or more tables in a data source.</span></span> <span data-ttu-id="5f361-109">Welche Attribute für die Dimension verfügbar sind, hängt von der Struktur der in der Tabelle enthaltenen Daten ab.</span><span class="sxs-lookup"><span data-stu-id="5f361-109">The attributes that are available for the dimension will depend on the structure of the data in the table.</span></span>  
  
 <span data-ttu-id="5f361-110">Weitere Informationen finden Sie unter [Erstellen einer Dimension anhand einer vorhandenen Tabelle](multidimensional-models/create-a-dimension-by-using-an-existing-table.md).</span><span class="sxs-lookup"><span data-stu-id="5f361-110">For more information, see [Create a Dimension by Using an Existing Table](multidimensional-models/create-a-dimension-by-using-an-existing-table.md).</span></span>  
  
 <span data-ttu-id="5f361-111">**Zeittabelle in der Datenquelle generieren**</span><span class="sxs-lookup"><span data-stu-id="5f361-111">**Generate a time table in the data source**</span></span>  
 <span data-ttu-id="5f361-112">Erstellen Sie eine Zeittabelle in der zugrunde liegenden Datenquelle, und verwenden Sie diese Tabelle dann zum Erstellen einer Zeitdimension.</span><span class="sxs-lookup"><span data-stu-id="5f361-112">Create a time table in the underlying data source and then use that table to create a time dimension.</span></span> <span data-ttu-id="5f361-113">Verwenden Sie diese Option, wenn keine solche Tabelle vorhanden ist und Sie sie nicht mithilfe eines Skripts erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="5f361-113">Use this option when no such table exists and you do not want to use a script to create one.</span></span> <span data-ttu-id="5f361-114">Die neue Zeittabelle enthält Daten für den Datumsbereich, die Attribute und Kalender, die Sie im Assistenten angeben.</span><span class="sxs-lookup"><span data-stu-id="5f361-114">The new time table will contain data for the date range, attributes, and calendars that you specify in the wizard.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5f361-115">Um diese Option nutzen zu können, müssen Sie über die Berechtigung zum Erstellen von Objekten in der zugrunde liegenden Datenquelle verfügen.</span><span class="sxs-lookup"><span data-stu-id="5f361-115">To use this option, you must have permission to create objects in the underlying data source.</span></span> <span data-ttu-id="5f361-116">Wenn Sie nicht zum Erstellen von Objekten in der Datenquelle berechtigt sind, verwenden Sie stattdessen die Option **Zeittabelle auf dem Server generieren** .</span><span class="sxs-lookup"><span data-stu-id="5f361-116">If you do not have permission to create objects on the data source, try to use the **Generate a time table on the server** option instead.</span></span>  
  
 <span data-ttu-id="5f361-117">Weitere Informationen finden Sie unter [Erstellen einer Zeitdimension durch Generieren einer Zeittabelle](multidimensional-models/create-a-time-dimension-by-generating-a-time-table.md).</span><span class="sxs-lookup"><span data-stu-id="5f361-117">For more information, see [Create a Time Dimension by Generating a Time Table](multidimensional-models/create-a-time-dimension-by-generating-a-time-table.md).</span></span>  
  
 <span data-ttu-id="5f361-118">**Zeittabelle auf dem Server generieren**</span><span class="sxs-lookup"><span data-stu-id="5f361-118">**Generate a time table on the server**</span></span>  
 <span data-ttu-id="5f361-119">Erstellen Sie direkt auf dem Server eine Zeittabelle, und verwenden Sie diese Tabelle dann zum Erstellen einer Zeitdimension.</span><span class="sxs-lookup"><span data-stu-id="5f361-119">Create a time table directly on the server and then use that table to create a time dimension.</span></span> <span data-ttu-id="5f361-120">Verwenden Sie diese Option, wenn Sie nicht über die Berechtigung zum Erstellen von Objekten in der zugrunde liegenden Datenquelle verfügen.</span><span class="sxs-lookup"><span data-stu-id="5f361-120">Use this option if you do not have permission to create objects in the underlying data source.</span></span> <span data-ttu-id="5f361-121">Die neue Zeitdimension enthält Daten für den Datumsbereich, die Attribute und Kalender, die Sie im Assistenten angeben.</span><span class="sxs-lookup"><span data-stu-id="5f361-121">The new time dimension will contain data for the date range, attributes, and calendars that you specify in the wizard.</span></span>  
  
 <span data-ttu-id="5f361-122">Weitere Informationen finden Sie unter [Erstellen einer Zeitdimension durch Generieren einer Zeittabelle](multidimensional-models/create-a-time-dimension-by-generating-a-time-table.md).</span><span class="sxs-lookup"><span data-stu-id="5f361-122">For more information, see [Create a Time Dimension by Generating a Time Table](multidimensional-models/create-a-time-dimension-by-generating-a-time-table.md).</span></span>  
  
 <span data-ttu-id="5f361-123">**Nichtzeittabelle in der Datenquelle generieren**</span><span class="sxs-lookup"><span data-stu-id="5f361-123">**Generate a non-time table in the data source**</span></span>  
 <span data-ttu-id="5f361-124">Entwerfen Sie die Dimension ohne die zugrunde liegende relationale Datenquelle, und generieren Sie dann das notwendige Schema für die Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="5f361-124">Design the dimension without an underlying relational data source, and then generate the necessary schema for the data source.</span></span> <span data-ttu-id="5f361-125">Dieser Ansatz wird als Top-Down-Entwurf bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="5f361-125">This approach is known as top-down modeling.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5f361-126">Um diese Option nutzen zu können, müssen Sie über die Berechtigung zum Erstellen von Objekten in der zugrunde liegenden Datenquelle verfügen.</span><span class="sxs-lookup"><span data-stu-id="5f361-126">To use this option, you must have permission to create objects in the underlying data source.</span></span>  
  
 <span data-ttu-id="5f361-127">Sie können die Dimension mit oder ohne Vorlage erstellen.</span><span class="sxs-lookup"><span data-stu-id="5f361-127">You can build the dimension with or without a template.</span></span> <span data-ttu-id="5f361-128">Um die Dimension mit einer Vorlage zu erstellen, wählen Sie die Vorlage in der Liste **Vorlage** aus.</span><span class="sxs-lookup"><span data-stu-id="5f361-128">To build the dimension with a template, select the template from the **Template** list.</span></span>  
  
 <span data-ttu-id="5f361-129">Weitere Informationen finden Sie unter [Erstellen einer Dimension durch Generieren einer Nichtzeittabelle in der Datenquelle](multidimensional-models/create-a-dimension-by-generating-a-non-time-table-in-the-data-source.md).</span><span class="sxs-lookup"><span data-stu-id="5f361-129">For more information, see [Create a Dimension by Generating a Non-Time Table in the Data Source](multidimensional-models/create-a-dimension-by-generating-a-non-time-table-in-the-data-source.md).</span></span>  
  
 <span data-ttu-id="5f361-130">**Vorlage**</span><span class="sxs-lookup"><span data-stu-id="5f361-130">**Template**</span></span>  
 <span data-ttu-id="5f361-131">Wählen Sie die Vorlage aus, die Sie zum erstellen der Dimension verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="5f361-131">Select the template that you want to use to create the dimension.</span></span> <span data-ttu-id="5f361-132">Vorlagen stellen einen vollständigen Satz von Attributen und Hierarchiedefinitionen zur Verfügung, die einem bestimmten geschäftlichen Zweck dienen.</span><span class="sxs-lookup"><span data-stu-id="5f361-132">Templates provide a complete set of attribute and hierarchy definitions oriented towards a specific business purpose.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5f361-133">Diese Option ist nur verfügbar, wenn die Option **Nichtzeittabelle in der Datenquelle generieren** ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="5f361-133">This option is only available when the **Generate a non-time table in the data source** option has been selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f361-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5f361-134">See Also</span></span>  
 <span data-ttu-id="5f361-135">[Dimensions-Assistent F1-Hilfe](dimension-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="5f361-135">[Dimension Wizard F1 Help](dimension-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="5f361-136">[Dimensionen &#40;Analysis Services Mehrdimensionale Daten&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="5f361-136">[Dimensions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="5f361-137">Dimensionen in mehrdimensionalen Modellen</span><span class="sxs-lookup"><span data-stu-id="5f361-137">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
