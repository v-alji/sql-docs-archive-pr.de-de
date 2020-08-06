---
title: Eigenschaften der Attribut Beziehung konfigurieren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- flexible relationships (Analysis Services)
- attributes [Analysis Services], relationships
- relationships [Analysis Services], attributes
- properties [Analysis Services], attribute relationships
- rigid relationships (Analysis Services)
ms.assetid: fce511af-66d7-42fc-bb3a-6c516f16b10e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 241fa2af16377fd2cacf657ec6f99c5ca4bd0c53
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608914"
---
# <a name="configure-attribute-relationship-properties"></a><span data-ttu-id="cdaf5-102">Konfigurieren von Attributbeziehungseigenschaften</span><span class="sxs-lookup"><span data-stu-id="cdaf5-102">Configure Attribute Relationship Properties</span></span>
  <span data-ttu-id="cdaf5-103">In der folgenden Tabelle sind die Eigenschaften einer Attributbeziehung aufgeführt und beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cdaf5-103">The following table lists and describes the properties of an attribute relationship.</span></span>  
  
|<span data-ttu-id="cdaf5-104">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="cdaf5-104">Property</span></span>|<span data-ttu-id="cdaf5-105">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cdaf5-105">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="cdaf5-106">attribute</span><span class="sxs-lookup"><span data-stu-id="cdaf5-106">Attribute</span></span>|<span data-ttu-id="cdaf5-107">Enthält den Namen des Attributs.</span><span class="sxs-lookup"><span data-stu-id="cdaf5-107">Contains the name of the attribute.</span></span>|  
|<span data-ttu-id="cdaf5-108">Kardinalität</span><span class="sxs-lookup"><span data-stu-id="cdaf5-108">Cardinality</span></span>|<span data-ttu-id="cdaf5-109">Zeigt die Kardinalität der Beziehung an.</span><span class="sxs-lookup"><span data-stu-id="cdaf5-109">Indicates the cardinality of the relationship.</span></span> <span data-ttu-id="cdaf5-110">Werte sind Many für eine m:1-Beziehung oder One für eine 1:1-Beziehung.</span><span class="sxs-lookup"><span data-stu-id="cdaf5-110">Values are Many, for a many to one relationship, or One, for a one to one relationship.</span></span> <span data-ttu-id="cdaf5-111">Der Standardwert lautet Many.</span><span class="sxs-lookup"><span data-stu-id="cdaf5-111">Default value is Many.</span></span> <span data-ttu-id="cdaf5-112">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] hat die Kardinalität-Eigenschaft keine Auswirkung. die Verwendung ist für eine zukünftige Implementierung reserviert.</span><span class="sxs-lookup"><span data-stu-id="cdaf5-112">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], the cardinality property has no effect - its use is reserved for a future implementation.</span></span>|  
|<span data-ttu-id="cdaf5-113">Name</span><span class="sxs-lookup"><span data-stu-id="cdaf5-113">Name</span></span>|<span data-ttu-id="cdaf5-114">Enthält den Anzeigenamen des Attributs.</span><span class="sxs-lookup"><span data-stu-id="cdaf5-114">Contains the friendly name of the attribute.</span></span>|  
|<span data-ttu-id="cdaf5-115">RelationshipType</span><span class="sxs-lookup"><span data-stu-id="cdaf5-115">RelationshipType</span></span>|<span data-ttu-id="cdaf5-116">Gibt an, ob die Elementbeziehungen im Laufe der Zeit geändert werden.</span><span class="sxs-lookup"><span data-stu-id="cdaf5-116">Indicates whether member relationships change over time.</span></span> <span data-ttu-id="cdaf5-117">Werte sind Rigid, d.h., dass die Beziehungen zwischen Elementen im Laufe der Zeit nicht geändert werden, oder Flexible, d.h., dass die Beziehungen zwischen Elementen im Laufe der Zeit geändert werden.</span><span class="sxs-lookup"><span data-stu-id="cdaf5-117">Values are Rigid, which means that relationships between members do not change over time, or Flexible, which means that relationships between members change over time.</span></span> <span data-ttu-id="cdaf5-118">Der Standardwert ist Flexible.</span><span class="sxs-lookup"><span data-stu-id="cdaf5-118">Default is Flexible.</span></span> <span data-ttu-id="cdaf5-119">Wenn Sie eine Beziehung vom Typ Flexible definieren, werden Aggregationen gelöscht und als Teil eines inkrementellen Updates neu berechnet. Sie werden nicht gelöscht, wenn nur neue Elemente hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="cdaf5-119">If you define a relationship as flexible, aggregations are dropped and recomputed as part of an incremental update (they will not be dropped if only new members are added).</span></span> <span data-ttu-id="cdaf5-120">Wenn Sie eine Beziehung vom Typ Rigid definieren, werden von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Aggregationen beim inkrementellen Aktualisieren der Dimension beibehalten.</span><span class="sxs-lookup"><span data-stu-id="cdaf5-120">If you define a relationship as rigid, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] retains aggregations when the dimension is incrementally updated.</span></span> <span data-ttu-id="cdaf5-121">Wenn eine als Beziehung vom Typ Rigid definierte Beziehung tatsächlich geändert wird, wird während der inkrementellen Verarbeitung von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ein Fehler generiert.</span><span class="sxs-lookup"><span data-stu-id="cdaf5-121">If a relationship that is defined as rigid actually changes, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] generates an error during incremental processing.</span></span> <span data-ttu-id="cdaf5-122">Durch das Angeben der entsprechenden Beziehungen und Beziehungseigenschaften wird die Abfrage- und Verarbeitungsleistung erhöht.</span><span class="sxs-lookup"><span data-stu-id="cdaf5-122">Specifying the appropriate relationships and relationship properties increases query and processing performance.</span></span>|  
|<span data-ttu-id="cdaf5-123">Sichtbar</span><span class="sxs-lookup"><span data-stu-id="cdaf5-123">Visible</span></span>|<span data-ttu-id="cdaf5-124">Bestimmt die Sichtbarkeit der Attributbeziehung.</span><span class="sxs-lookup"><span data-stu-id="cdaf5-124">Determines the visibility of the attribute relationship.</span></span> <span data-ttu-id="cdaf5-125">Die Werte sind True und False.</span><span class="sxs-lookup"><span data-stu-id="cdaf5-125">Values are True or False.</span></span> <span data-ttu-id="cdaf5-126">Der Standardwert lautet "True".</span><span class="sxs-lookup"><span data-stu-id="cdaf5-126">Default is True.</span></span>|  
  
  
