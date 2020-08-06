---
title: Daten Bank Dimensions Eigenschaften | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- metadata [Analysis Services]
- dimensions [Analysis Services], characteristics
- properties [Analysis Services], dimensions
ms.assetid: 075548ef-08a3-413c-8ee0-4a074c276fcc
author: minewiskan
ms.author: owend
ms.openlocfilehash: 504e190f4c513a8c999c4d7d7ab9eaabb83298c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620030"
---
# <a name="database-dimension-properties"></a><span data-ttu-id="f87e2-102">Eigenschaften von Datenbankdimensionen</span><span class="sxs-lookup"><span data-stu-id="f87e2-102">Database Dimension Properties</span></span>
  <span data-ttu-id="f87e2-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] werden die Merkmale einer Dimension durch die Metadaten für die Dimension definiert, basierend auf den Einstellungen verschiedener Dimensions Eigenschaften und den Attributen oder Hierarchien, die in der Dimension enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="f87e2-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], the characteristics of a dimension are defined by the metadata for the dimension, based on the settings of various dimension properties, and on the attributes or hierarchies that are contained by the dimension.</span></span> <span data-ttu-id="f87e2-104">In der folgenden Tabelle werden die Dimensionseigenschaften in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f87e2-104">The following table describes the dimension properties in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
|<span data-ttu-id="f87e2-105">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="f87e2-105">Property</span></span>|<span data-ttu-id="f87e2-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f87e2-106">Description</span></span>|  
|--------------|-----------------|  
|`AttributeAllMemberName`|<span data-ttu-id="f87e2-107">Gibt den Namen des Alle-Elements für Attribute in einer Dimension an.</span><span class="sxs-lookup"><span data-stu-id="f87e2-107">Specifies the name of the All member for attributes in a dimension.</span></span>|  
|`Collation`|<span data-ttu-id="f87e2-108">Bestimmt die von der Dimension verwendete Sortierung.</span><span class="sxs-lookup"><span data-stu-id="f87e2-108">Determines the collation used by the dimension.</span></span>|  
|`CurrentStorageMode`|<span data-ttu-id="f87e2-109">Enthält den aktuellen Speichermodus für die Dimension.</span><span class="sxs-lookup"><span data-stu-id="f87e2-109">Contains the current storage mode for the dimension.</span></span>|  
|`DependsOnDimension`|<span data-ttu-id="f87e2-110">Enthält die ID einer anderen Dimension, von der die Dimension abhängt, falls vorhanden.</span><span class="sxs-lookup"><span data-stu-id="f87e2-110">Contains the ID of another dimension on which the dimension depends, if any.</span></span>|  
|`Description`|<span data-ttu-id="f87e2-111">Enthält die Beschreibung einer Dimension.</span><span class="sxs-lookup"><span data-stu-id="f87e2-111">Contains the description of the dimension.</span></span>|  
|`ErrorConfiguration`|<span data-ttu-id="f87e2-112">Konfigurierbare Fehlerbehandlungseinstellungen für die Bearbeitung doppelter Schlüssel, unbekannter Schlüssel, für Fehlergrenzen, Aktionen bei Erkennung von Fehlern, Fehlerprotokolldateien und die Bearbeitung von NULL-Schlüsseln.</span><span class="sxs-lookup"><span data-stu-id="f87e2-112">Configurable error handling settings for handling of duplicate keys, unknown keys, error limits, action upon error detection, error log file, and null key handling.</span></span>|  
|`ID`|<span data-ttu-id="f87e2-113">Enthält den eindeutigen Bezeichner (ID) der Dimension.</span><span class="sxs-lookup"><span data-stu-id="f87e2-113">Contains the unique identifier (ID) of the dimension.</span></span>|  
|`Language`|<span data-ttu-id="f87e2-114">Gibt die Standardsprache für die Dimension an.</span><span class="sxs-lookup"><span data-stu-id="f87e2-114">Specifies the default language for the dimension.</span></span>|  
|`MdxMissingMemberMode`|<span data-ttu-id="f87e2-115">Legt die Verarbeitung fehlender Elemente in MDX-Anweisungen (Multidimensional Expressions) fest.</span><span class="sxs-lookup"><span data-stu-id="f87e2-115">Determines how missing members are handled for Multidimensional Expressions (MDX) statements.</span></span>|  
|`MiningModelID`|<span data-ttu-id="f87e2-116">Enthält die ID des Miningmodells, der die Data Mining-Dimension zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="f87e2-116">Contains the ID of the mining model with which the data mining dimension is associated.</span></span> <span data-ttu-id="f87e2-117">Diese Eigenschaft kann nur angewendet werden, wenn die Dimension eine Miningmodelldimension ist.</span><span class="sxs-lookup"><span data-stu-id="f87e2-117">This property is applicable only if the dimension is a mining model dimension.</span></span>|  
|`Name`|<span data-ttu-id="f87e2-118">Gibt den Namen der Dimension an.</span><span class="sxs-lookup"><span data-stu-id="f87e2-118">Specifies the name of the dimension.</span></span>|  
|`ProactiveCaching`|<span data-ttu-id="f87e2-119">Definiert die Einstellungen für die Dimension für die proaktive Zwischenspeicherung.</span><span class="sxs-lookup"><span data-stu-id="f87e2-119">Defines the proactive cache settings for the dimension.</span></span>|  
|`ProcessingGroup`|<span data-ttu-id="f87e2-120">Gibt die Verarbeitungsgruppe an.</span><span class="sxs-lookup"><span data-stu-id="f87e2-120">Specifies the processing group.</span></span> <span data-ttu-id="f87e2-121">Die Werte sind ByAttribute oder ByTable.</span><span class="sxs-lookup"><span data-stu-id="f87e2-121">Values are ByAttribute or ByTable.</span></span> <span data-ttu-id="f87e2-122">Der Standardwert ist `ByAttribute`.</span><span class="sxs-lookup"><span data-stu-id="f87e2-122">Default is `ByAttribute`.</span></span>|  
|`ProcessingMode`|<span data-ttu-id="f87e2-123">Gibt an, ob [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] während oder nach der Verarbeitung indizieren und aggregieren soll.</span><span class="sxs-lookup"><span data-stu-id="f87e2-123">Indicates whether [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] should index and aggregate during or after processing.</span></span>|  
|`ProcessingPriority`|<span data-ttu-id="f87e2-124">Bestimmt die Verarbeitungspriorität der Dimension während Hintergrundvorgängen wie verzögerte Aggregation, Indizierung oder Clustererstellung.</span><span class="sxs-lookup"><span data-stu-id="f87e2-124">Determines the processing priority of the dimension during background operations such as lazy aggregation, indexing, or clustering.</span></span>|  
|`Source`|<span data-ttu-id="f87e2-125">Identifiziert die Datenquellensicht, an die die Dimension gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="f87e2-125">Identifies the data source view to which the dimension is bound.</span></span>|  
|`StorageMode`|<span data-ttu-id="f87e2-126">Bestimmt den Speichermodus für die Dimension.</span><span class="sxs-lookup"><span data-stu-id="f87e2-126">Determines the storage mode for the dimension.</span></span>|  
|`Type`|<span data-ttu-id="f87e2-127">Gibt den Typ der Dimension an.</span><span class="sxs-lookup"><span data-stu-id="f87e2-127">Specifies the type of the dimension.</span></span>|  
|`UnknownMember`|<span data-ttu-id="f87e2-128">Gibt an, ob das unbekannte Element sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="f87e2-128">Indicates whether the unknown member is visible.</span></span>|  
|`UnknownMemberName`|<span data-ttu-id="f87e2-129">Gibt die Beschriftung in der standardmäßigen Sprache der Dimension für das unbekannte Element der Dimension an.</span><span class="sxs-lookup"><span data-stu-id="f87e2-129">Specifies the caption, in the default language of the dimension, for the unknown member of the dimension.</span></span>|  
|`WriteEnabled`|<span data-ttu-id="f87e2-130">Gibt an, ob das Rückschreiben von Dimensionen unterstützt wird (unterliegt den Sicherheitsberechtigungen).</span><span class="sxs-lookup"><span data-stu-id="f87e2-130">Indicates whether dimension writebacks are available (subject to security permissions).</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="f87e2-131">Weitere Informationen zum Festlegen von Werten für die Eigenschaften ErrorConfiguration und UnknownMember beim Arbeiten mit NULL-Werten und anderen Problemen mit der Datenintegrität finden Sie unter [Handling Data Integrity Issues in Analysis Services 2005](https://go.microsoft.com/fwlink/?LinkId=81891).</span><span class="sxs-lookup"><span data-stu-id="f87e2-131">For more information about setting values for the ErrorConfiguration and UnknownMember properties when working with null values and other data integrity issues, see [Handling Data Integrity Issues in Analysis Services 2005](https://go.microsoft.com/fwlink/?LinkId=81891).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f87e2-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f87e2-132">See Also</span></span>  
 <span data-ttu-id="f87e2-133">[Attribute und Attribut Hierarchien](attributes-and-attribute-hierarchies.md) </span><span class="sxs-lookup"><span data-stu-id="f87e2-133">[Attributes and Attribute Hierarchies](attributes-and-attribute-hierarchies.md) </span></span>  
 <span data-ttu-id="f87e2-134">[Benutzer Hierarchien](user-hierarchies.md) </span><span class="sxs-lookup"><span data-stu-id="f87e2-134">[User Hierarchies](user-hierarchies.md) </span></span>  
 <span data-ttu-id="f87e2-135">[Dimensions Beziehungen](../multidimensional-models-olap-logical-cube-objects/dimension-relationships.md) </span><span class="sxs-lookup"><span data-stu-id="f87e2-135">[Dimension Relationships](../multidimensional-models-olap-logical-cube-objects/dimension-relationships.md) </span></span>  
 [<span data-ttu-id="f87e2-136">Dimensionen &#40;Analysis Services – mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="f87e2-136">Dimensions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimensions-analysis-services-multidimensional-data.md)  
  
  
