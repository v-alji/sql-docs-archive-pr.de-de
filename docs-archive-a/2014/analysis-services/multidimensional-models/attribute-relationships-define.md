---
title: Definieren von Attribut Beziehungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- attributes [Analysis Services], relationships
- relationships [Analysis Services], attributes
ms.assetid: 9184d344-e96d-4025-ad6f-3f75129746df
author: minewiskan
ms.author: owend
ms.openlocfilehash: a694c68a55de2533c4ce7791d3be865008b6321f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608906"
---
# <a name="define-attribute-relationships"></a><span data-ttu-id="8384b-102">Definieren von Attributbeziehungen</span><span class="sxs-lookup"><span data-stu-id="8384b-102">Define Attribute Relationships</span></span>
  <span data-ttu-id="8384b-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] sind Attribute der grundlegende Baustein einer Dimension.</span><span class="sxs-lookup"><span data-stu-id="8384b-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], attributes are the fundamental building block of a dimension.</span></span> <span data-ttu-id="8384b-104">Eine Dimension enthält einen Satz von Attributen, die auf Basis von Attributbeziehungen organisiert sind.</span><span class="sxs-lookup"><span data-stu-id="8384b-104">A dimension contains a set of attributes that are organized based on attribute relationships.</span></span>  
  
 <span data-ttu-id="8384b-105">Für jede Tabelle in einer Dimension existiert eine Attributbeziehung, die das Schlüsselattribut der Tabelle mit anderen Attributen aus der Tabelle verknüpft.</span><span class="sxs-lookup"><span data-stu-id="8384b-105">For each table included in a dimension, there is an attribute relationship that relates the table's key attribute to other attributes from that table.</span></span> <span data-ttu-id="8384b-106">Diese Beziehung kommt zustande, wenn Sie die Dimension erstellen.</span><span class="sxs-lookup"><span data-stu-id="8384b-106">You create this relationship when you create the dimension.</span></span>  
  
 <span data-ttu-id="8384b-107">Eine Attributbeziehung bietet die folgenden Vorteile:</span><span class="sxs-lookup"><span data-stu-id="8384b-107">An attribute relationship provides the following advantages:</span></span>  
  
-   <span data-ttu-id="8384b-108">Sie reduziert den für die Dimensionsverarbeitung erforderlichen Speicherplatz.</span><span class="sxs-lookup"><span data-stu-id="8384b-108">Reduces the amount of memory needed for dimension processing.</span></span> <span data-ttu-id="8384b-109">Dies beschleunigt die Dimensions-, Partitions- und Abfrageverarbeitung.</span><span class="sxs-lookup"><span data-stu-id="8384b-109">This speeds up dimension, partition, and query processing.</span></span>  
  
-   <span data-ttu-id="8384b-110">Sie erhöht die Abfrageleistung, da der Speicherzugriff beschleunigt wird und Ausführungspläne besser optimiert werden können.</span><span class="sxs-lookup"><span data-stu-id="8384b-110">Increases query performance because storage access is faster and execution plans are better optimized.</span></span>  
  
-   <span data-ttu-id="8384b-111">Sie führt aufgrund der Aggregationsentwurfsalgorithmen zur Auswahl effektiverer Aggregate, sofern benutzerdefinierte Hierarchien entlang den Beziehungspfaden definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="8384b-111">Results in the selection of more effective aggregates by the aggregation design algorithms, provided that user-defined hierarchies have been defined along the relationship paths.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8384b-112">Weitere Informationen über die Bedeutung und die Auswirkungen der Definition und Konfiguration von Attribut Beziehungen finden Sie im Abschnitt "verbessern der Abfrageleistung" im [SQL Server 2005 Analysis Services Performance Guide](https://docsbay.net/Microsoft-SQL-Server-2005-Analysis-Services-Performance-Guide).</span><span class="sxs-lookup"><span data-stu-id="8384b-112">For more information about the importance and implications of defining and configuring attribute relationships, see the section, "Enhancing query performance," in the [SQL Server 2005 Analysis Services Performance Guide](https://docsbay.net/Microsoft-SQL-Server-2005-Analysis-Services-Performance-Guide).</span></span>  
  
## <a name="attribute-relationship-considerations"></a><span data-ttu-id="8384b-113">Überlegungen zu Attributbeziehungen</span><span class="sxs-lookup"><span data-stu-id="8384b-113">Attribute Relationship Considerations</span></span>  
 <span data-ttu-id="8384b-114">Sofern die zugrunde liegenden Daten dies unterstützen, sollten Sie auch eindeutige Attributbeziehungen zwischen Attributen definieren.</span><span class="sxs-lookup"><span data-stu-id="8384b-114">When the underlying data supports it, you should also define unique attribute relationships between attributes.</span></span> <span data-ttu-id="8384b-115">Um eindeutige Attributbeziehungen zu definieren, verwenden Sie die Registerkarte **Attributbeziehungen** des Dimensions-Designers.</span><span class="sxs-lookup"><span data-stu-id="8384b-115">To define unique attribute relationships, use the **Attribute Relationships** tab of Dimension Designer.</span></span>  
  
 <span data-ttu-id="8384b-116">Jedes Attribut, das über eine ausgehende Beziehung verfügt, muss über einen eindeutigen Schlüssel relativ zu seinem verknüpften Attribut verfügen.</span><span class="sxs-lookup"><span data-stu-id="8384b-116">Any attribute that has an outgoing relationship must have a unique key relative to its related attribute.</span></span> <span data-ttu-id="8384b-117">Anders ausgedrückt darf ein Element in einem Quellattribut nur ein Element in einem verknüpften Attribut identifizieren.</span><span class="sxs-lookup"><span data-stu-id="8384b-117">In other words, a member in a source attribute must identify one and only one member in a related attribute.</span></span> <span data-ttu-id="8384b-118">Betrachten Sie z. B. die Beziehung "City -> State".</span><span class="sxs-lookup"><span data-stu-id="8384b-118">For example, consider the relationship, City -> State.</span></span> <span data-ttu-id="8384b-119">In dieser Beziehung ist "City" das Quellattribut und "State" das verknüpfte Attribut.</span><span class="sxs-lookup"><span data-stu-id="8384b-119">In this relationship, the source attribute is City and the related attribute is State.</span></span> <span data-ttu-id="8384b-120">Das Quell Attribut ist die "n"-Seite und die verwandte Seite ist die "One"-Seite der n:1-Beziehung.</span><span class="sxs-lookup"><span data-stu-id="8384b-120">The source attribute is the "many" side and the related side is the "one" side of the many-to-one relationship.</span></span> <span data-ttu-id="8384b-121">Der Schlüssel für das Quellattribut lautet "City + Status".</span><span class="sxs-lookup"><span data-stu-id="8384b-121">The key for the source attribute would be City + State.</span></span> <span data-ttu-id="8384b-122">Weitere Informationen finden Sie unter [Gewusst wie: Erstellen, Ändern oder Löschen einer Attributbeziehung](attribute-relationships-create-modify-or-delete-relationship.md).</span><span class="sxs-lookup"><span data-stu-id="8384b-122">For more information, see [Create, Modify, or Delete an Attribute Relationship](attribute-relationships-create-modify-or-delete-relationship.md).</span></span>  
  
 <span data-ttu-id="8384b-123">Weitere Informationen zu Eigenschaften einer Attributbeziehung finden Sie unter [Konfigurieren von Attributbeziehungseigenschaften](attribute-relationships-configure-attribute-properties.md).</span><span class="sxs-lookup"><span data-stu-id="8384b-123">For more information about properties of an attribute relationship, see [Configure Attribute Relationship Properties](attribute-relationships-configure-attribute-properties.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8384b-124">Eine falsche Definition von Attributbeziehungen kann zu ungültigen Abfrageergebnissen führen.</span><span class="sxs-lookup"><span data-stu-id="8384b-124">Defining attribute relationships incorrectly can cause invalid query results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8384b-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8384b-125">See Also</span></span>  
 [<span data-ttu-id="8384b-126">Attributbeziehungen</span><span class="sxs-lookup"><span data-stu-id="8384b-126">Attribute Relationships</span></span>](../multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md)  
  
  
