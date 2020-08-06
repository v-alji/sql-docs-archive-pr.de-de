---
title: Cube-Eigenschaften | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- Collation property
- ID property
- ErrorConfiguration property
- cubes [Analysis Services], properties
- Description property
- DefaultMeasure property
- ProcessingMode property
- AggregationPrefix property
- EstimatedRows property
- Visible property
- StorageLocation property
- StorageMode property
- ScriptErrorHandlingMode property
- Source property
- ScriptCacheProcessingMode property
- Language property
- Name property
- properties [Analysis Services], cubes
- ProcessingPriority property
- ProactiveCaching property
ms.assetid: 72ca3387-620d-4473-8e23-7fe1f2b3d5bf
author: minewiskan
ms.author: owend
ms.openlocfilehash: 27d4202774107795eaddf76c27e21010d534d977
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609512"
---
# <a name="cube-properties"></a><span data-ttu-id="ad8af-102">Cubeeigenschaften</span><span class="sxs-lookup"><span data-stu-id="ad8af-102">Cube Properties</span></span>
  <span data-ttu-id="ad8af-103">Cubes verfügen über eine Reihe von Eigenschaften, die Sie festlegen können und die sich auf das cubeweite Verhalten auswirken.</span><span class="sxs-lookup"><span data-stu-id="ad8af-103">Cubes have a number of properties that you can set to affect cube-wide behavior.</span></span> <span data-ttu-id="ad8af-104">Diese Eigenschaften sind in der folgenden Tabelle zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="ad8af-104">These properties are summarized in the following table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ad8af-105">Manche Eigenschaften werden beim Erstellen des Cubes automatisch festgelegt und können nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="ad8af-105">Some properties are set automatically when the cube is created and cannot be changed.</span></span>  
  
 <span data-ttu-id="ad8af-106">Weitere Informationen zum Festlegen von Cube-Eigenschaften finden Sie unter [Cube Designer &#40;Analysis Services-Multidimensional Data&#41;](../cube-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="ad8af-106">For more information about how to set cube properties, see [Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](../cube-designer-analysis-services-multidimensional-data.md).</span></span>  
  
|<span data-ttu-id="ad8af-107">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="ad8af-107">Property</span></span>|<span data-ttu-id="ad8af-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ad8af-108">Description</span></span>|  
|--------------|-----------------|  
|`AggregationPrefix`|<span data-ttu-id="ad8af-109">Gibt das für Aggregationsnamen verwendete gemeinsame Präfix an.</span><span class="sxs-lookup"><span data-stu-id="ad8af-109">Specifies the common prefix that is used for aggregation names.</span></span>|  
|`Collation`|<span data-ttu-id="ad8af-110">Gibt den Gebietsschemabezeichner (LCID) und das Vergleichsflag, durch einen Unterstrich voneinander getrennt, an, wie z. B. Latin1_General_C1_AS.</span><span class="sxs-lookup"><span data-stu-id="ad8af-110">Specifies the locale identifier (LCID) and the comparison flag, separated by an underscore: for example, Latin1_General_C1_AS.</span></span>|  
|`DefaultMeasure`|<span data-ttu-id="ad8af-111">Enthält einen mehrdimensionalen Ausdruck (Multidimensional Expression, MDX), der das Standardmeasure für den Cube definiert.</span><span class="sxs-lookup"><span data-stu-id="ad8af-111">Contains a Multidimensional Expressions (MDX) expression that defines the default measure for the cube.</span></span>|  
|`Description`|<span data-ttu-id="ad8af-112">Stellt eine Beschreibung des Cubes bereit, die in Clientanwendungen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="ad8af-112">Provides a description of the cube, which may be exposed in client applications.</span></span>|  
|`ErrorConfiguration`|<span data-ttu-id="ad8af-113">Enthält konfigurierbare Fehlerbehandlungseinstellungen für die Bearbeitung doppelter Schlüssel, unbekannter Schlüssel, für Fehlergrenzen, Aktionen bei Erkennung von Fehlern, Fehlerprotokolldateien und die Bearbeitung von NULL-Schlüsseln.</span><span class="sxs-lookup"><span data-stu-id="ad8af-113">Contains configurable error handling settings for handling of duplicate keys, unknown keys, error limits, action upon error detection, error log file, and null key handling.</span></span>|  
|`EstimatedRows`|<span data-ttu-id="ad8af-114">Gibt die Anzahl der geschätzten Zeilen im Cube an.</span><span class="sxs-lookup"><span data-stu-id="ad8af-114">Specifies the number of estimated rows in the cube.</span></span>|  
|`ID`|<span data-ttu-id="ad8af-115">Enthält den eindeutigen Bezeichner (ID) des Cubes.</span><span class="sxs-lookup"><span data-stu-id="ad8af-115">Contains the unique identifier (ID) of the cube.</span></span>|  
|`Language`|<span data-ttu-id="ad8af-116">Gibt den Standardsprachbezeichner für den Cube an.</span><span class="sxs-lookup"><span data-stu-id="ad8af-116">Specifies the default language identifier of the cube.</span></span>|  
|`Name`|<span data-ttu-id="ad8af-117">Gibt den benutzerfreundlichen Namen des Attributs an.</span><span class="sxs-lookup"><span data-stu-id="ad8af-117">Specifies the user-friendly name of the cube.</span></span>|  
|`ProactiveCaching`|<span data-ttu-id="ad8af-118">Definiert die Einstellungen für den Cube für die proaktive Zwischenspeicherung.</span><span class="sxs-lookup"><span data-stu-id="ad8af-118">Defines proactive cache settings for the cube.</span></span>|  
|`ProcessingMode`|<span data-ttu-id="ad8af-119">Gibt an, ob während oder nach der Verarbeitung indiziert und aggregiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="ad8af-119">Indicates whether indexing and aggregating should occur during or after processing.</span></span> <span data-ttu-id="ad8af-120">Optionen sind **reguläre** oder `lazy` .</span><span class="sxs-lookup"><span data-stu-id="ad8af-120">Options are **regular** or `lazy`.</span></span>|  
|`ProcessingPriority`|<span data-ttu-id="ad8af-121">Legt die Verarbeitungspriorität des Cubes bei Hintergrundvorgängen wie z. B. verzögerte Aggregationen und Indizierungen fest.</span><span class="sxs-lookup"><span data-stu-id="ad8af-121">Determines the processing priority of the cube during background operations, such as lazy aggregations and indexing.</span></span> <span data-ttu-id="ad8af-122">Der Standardwert ist **0**.</span><span class="sxs-lookup"><span data-stu-id="ad8af-122">The default value is **0**.</span></span>|  
|`ScriptCacheProcessingMode`|<span data-ttu-id="ad8af-123">Gibt an, ob der Skriptcache während oder nach der Verarbeitung erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ad8af-123">Indicates whether the script cache should be built during or after processing.</span></span> <span data-ttu-id="ad8af-124">Optionen sind **reguläre** und `lazy` .</span><span class="sxs-lookup"><span data-stu-id="ad8af-124">Options are **regular** and `lazy`.</span></span>|  
|`ScriptErrorHandlingMode`|<span data-ttu-id="ad8af-125">Bestimmt die Fehlerbehandlung.</span><span class="sxs-lookup"><span data-stu-id="ad8af-125">Determines error handling.</span></span> <span data-ttu-id="ad8af-126">Optionen sind `IgnoreNone` oder.`IgnoreAll`</span><span class="sxs-lookup"><span data-stu-id="ad8af-126">Options are `IgnoreNone` or `IgnoreAll`</span></span>|  
|`Source`|<span data-ttu-id="ad8af-127">Zeigt die für den Cube verwendete Datenquellensicht.</span><span class="sxs-lookup"><span data-stu-id="ad8af-127">Displays the data source view used for the cube.</span></span>|  
|`StorageLocation`|<span data-ttu-id="ad8af-128">Gibt den Speicherort des Dateisystems für den Cube an.</span><span class="sxs-lookup"><span data-stu-id="ad8af-128">Specifies the file system storage location for the cube.</span></span> <span data-ttu-id="ad8af-129">Wenn kein Speicherort angegeben ist, wird er von der Datenbank geerbt, die das Cubeobjekt enthält.</span><span class="sxs-lookup"><span data-stu-id="ad8af-129">If none is specified, the location is inherited from the database that contains the cube object.</span></span>|  
|`StorageMode`|<span data-ttu-id="ad8af-130">Gibt den Speichermodus für den Cube an.</span><span class="sxs-lookup"><span data-stu-id="ad8af-130">Specifies the storage mode for the cube.</span></span> <span data-ttu-id="ad8af-131">Werte sind `MOLAP` , `ROLAP` oder.`HOLAP``.`</span><span class="sxs-lookup"><span data-stu-id="ad8af-131">Values are `MOLAP`, `ROLAP`, or `HOLAP``.`</span></span>|  
|`Visible`|<span data-ttu-id="ad8af-132">Bestimmt die Sichtbarkeit des Cubes.</span><span class="sxs-lookup"><span data-stu-id="ad8af-132">Determines the visibility of the cube.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="ad8af-133">Weitere Informationen zum Festlegen von Werten für die ErrorConfiguration-Eigenschaft beim Arbeiten mit NULL-Werten und anderen Problemen mit der Datenintegrität finden Sie unter [Handling Data Integrity Issues in Analysis Services 2005](https://go.microsoft.com/fwlink/?LinkId=81891).</span><span class="sxs-lookup"><span data-stu-id="ad8af-133">For more information about setting values for the ErrorConfiguration property when working with null values and other data integrity issues, see [Handling Data Integrity Issues in Analysis Services 2005](https://go.microsoft.com/fwlink/?LinkId=81891).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad8af-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ad8af-134">See Also</span></span>  
 [<span data-ttu-id="ad8af-135">Proaktives Zwischenspeichern &#40;Partitionen&#41;</span><span class="sxs-lookup"><span data-stu-id="ad8af-135">Proactive Caching &#40;Partitions&#41;</span></span>](partitions-proactive-caching.md)  
  
  
