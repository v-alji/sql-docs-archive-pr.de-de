---
title: Attribut Beziehungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- member properties [Analysis Services], attribute relationships
- security [Analysis Services], properties
- PROPERTIES keyword
- storage [Analysis Services], attribute relationships
- natural hierarchies [Analysis Services]
- dimensions [Analysis Services], member properties
- queries [MDX], attribute relationships
- user-defined hierarchies [Analysis Services]
- attributes [Analysis Services], relationships
- member properties [Analysis Services]
- members [Analysis Services], attribute relationships
- storing data [Analysis Services], attribute relationships
- relationships [Analysis Services], attributes
ms.assetid: 2491422a-4cf5-4b23-b6ab-289222b22ce8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 122638a2728a8a85ee58661196797383da20eef8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702027"
---
# <a name="attribute-relationships"></a><span data-ttu-id="54081-102">Attributbeziehungen</span><span class="sxs-lookup"><span data-stu-id="54081-102">Attribute Relationships</span></span>
  <span data-ttu-id="54081-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] sind Attribute innerhalb einer Dimension immer entweder direkt oder indirekt mit dem Schlüssel Attribut verknüpft.</span><span class="sxs-lookup"><span data-stu-id="54081-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], attributes within a dimension are always related either directly or indirectly to the key attribute.</span></span> <span data-ttu-id="54081-104">Wenn Sie eine Dimension auf Basis eines Sternschemas definieren, in dem sämtliche Dimensionsattribute aus derselben relationalen Tabelle abgeleitet werden, wird automatisch eine Attributbeziehung zwischen dem Schlüsselattribut und den einzelnen Nichtschlüsselattributen definiert.</span><span class="sxs-lookup"><span data-stu-id="54081-104">When you define a dimension based on a star schema, which is where all dimension attributes are derived from the same relational table, an attribute relationship is automatically defined between the key attribute and each non-key attribute of the dimension.</span></span> <span data-ttu-id="54081-105">Wenn Sie eine Dimension auf Basis eines Schneeflockenschemas definieren, in dem Dimensionsattribute aus mehreren verknüpften Tabellen abgeleitet werden, wird eine Attributbeziehung automatisch wie folgt definiert:</span><span class="sxs-lookup"><span data-stu-id="54081-105">When you define a dimension based on a snowflake schema, which is where dimension attributes are derived from multiple related tables, an attribute relationship is automatically defined as follows:</span></span>  
  
-   <span data-ttu-id="54081-106">Zwischen dem Schlüsselattribut und den einzelnen Nichtschlüsselattributen, die an die Spalten in der Dimensionshaupttabelle gebunden sind</span><span class="sxs-lookup"><span data-stu-id="54081-106">Between the key attribute and each non-key attribute bound to columns in the main dimension table.</span></span>  
  
-   <span data-ttu-id="54081-107">Zwischen dem Schlüsselattribut und dem Attribut, das an den Fremdschlüssel in der sekundären Tabelle gebunden ist, die die zugrunde liegenden Dimensionstabellen verknüpft</span><span class="sxs-lookup"><span data-stu-id="54081-107">Between the key attribute and the attribute bound to the foreign key in the secondary table that links the underlying dimension tables.</span></span>  
  
-   <span data-ttu-id="54081-108">Zwischen dem Attribut, das an den Fremdschlüssel in der sekundären Tabelle gebunden ist, und den einzelnen Nichtschlüsselattributen, die an Spalten aus der sekundären Tabelle gebunden sind</span><span class="sxs-lookup"><span data-stu-id="54081-108">Between the attribute bound to foreign key in the secondary table and each non-key attribute bound to columns from the secondary table.</span></span>  
  
 <span data-ttu-id="54081-109">Es kann jedoch Gründe dafür geben, die Standardattributbeziehungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="54081-109">However, there are a number of reasons why you might want to change these default attribute relationships.</span></span> <span data-ttu-id="54081-110">Ein möglicher Grund wäre, dass Sie eine natürliche Hierarchie, eine benutzerdefinierte Sortierreihenfolge oder Dimensionsgranularität auf Basis eines Nichtschlüsselattributs definieren möchten.</span><span class="sxs-lookup"><span data-stu-id="54081-110">For example, you might want to define a natural hierarchy, a custom sort order, or dimension granularity based on a non-key attribute.</span></span> <span data-ttu-id="54081-111">Weitere Informationen finden Sie unter [Dimensions Attribut Eigenschaften Reference](../multidimensional-models/dimension-attribute-properties-reference.md).</span><span class="sxs-lookup"><span data-stu-id="54081-111">For more information, see [Dimension Attribute Properties Reference](../multidimensional-models/dimension-attribute-properties-reference.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="54081-112">Attributbeziehungen sind in MDX (Multidimensional Expressions) als Elementeigenschaften bekannt.</span><span class="sxs-lookup"><span data-stu-id="54081-112">Attribute relationships are known in Multidimensional Expressions (MDX) as member properties.</span></span>  
  
## <a name="natural-hierarchy-relationships"></a><span data-ttu-id="54081-113">Beziehungen mit natürlicher Hierarchie</span><span class="sxs-lookup"><span data-stu-id="54081-113">Natural Hierarchy Relationships</span></span>  
 <span data-ttu-id="54081-114">Eine Hierarchie wird als natürlich bezeichnet, wenn die in der benutzerdefinierten Hierarchie enthaltenen Attribute 1:n-Beziehungen mit dem jeweils direkt darunter liegenden Attribut haben.</span><span class="sxs-lookup"><span data-stu-id="54081-114">A hierarchy is a natural hierarchy when each attribute included in the user-defined hierarchy has a one to many relationship with the attribute immediately below it.</span></span> <span data-ttu-id="54081-115">Ein Beispiel ist eine Customer-Dimension, die auf einer relationalen Quelltabelle mit acht Spalten basiert:</span><span class="sxs-lookup"><span data-stu-id="54081-115">For example, consider a Customer dimension based on a relational source table with eight columns:</span></span>  
  
-   <span data-ttu-id="54081-116">CustomerKey</span><span class="sxs-lookup"><span data-stu-id="54081-116">CustomerKey</span></span>  
  
-   <span data-ttu-id="54081-117">CustomerName</span><span class="sxs-lookup"><span data-stu-id="54081-117">CustomerName</span></span>  
  
-   <span data-ttu-id="54081-118">Age</span><span class="sxs-lookup"><span data-stu-id="54081-118">Age</span></span>  
  
-   <span data-ttu-id="54081-119">Geschlecht</span><span class="sxs-lookup"><span data-stu-id="54081-119">Gender</span></span>  
  
-   <span data-ttu-id="54081-120">Email</span><span class="sxs-lookup"><span data-stu-id="54081-120">Email</span></span>  
  
-   <span data-ttu-id="54081-121">City</span><span class="sxs-lookup"><span data-stu-id="54081-121">City</span></span>  
  
-   <span data-ttu-id="54081-122">Country</span><span class="sxs-lookup"><span data-stu-id="54081-122">Country</span></span>  
  
-   <span data-ttu-id="54081-123">Region</span><span class="sxs-lookup"><span data-stu-id="54081-123">Region</span></span>  
  
 <span data-ttu-id="54081-124">Die entsprechende Analysis Services-Dimension verfügt über sieben Attribute:</span><span class="sxs-lookup"><span data-stu-id="54081-124">The corresponding Analysis Services dimension has seven attributes:</span></span>  
  
-   <span data-ttu-id="54081-125">Customer (basierend auf CustomerKey, wobei CustomerName Elementnamen angibt)</span><span class="sxs-lookup"><span data-stu-id="54081-125">Customer (based on CustomerKey, with CustomerName supplying member names)</span></span>  
  
-   <span data-ttu-id="54081-126">Age, Gender, Email, City, Region, Country</span><span class="sxs-lookup"><span data-stu-id="54081-126">Age, Gender, Email, City, Region, Country</span></span>  
  
 <span data-ttu-id="54081-127">Beziehungen, die natürliche Hierarchien darstellen, werden dadurch erzwungen, dass eine Attributbeziehung zwischen dem Attribut einer Ebene und dem Attribut der darunter liegenden Ebene erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="54081-127">Relationships representing natural hierarchies are enforced by creating an attribute relationship between the attribute for a level and the attribute for the level below it.</span></span> <span data-ttu-id="54081-128">Für [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] gibt dies eine natürliche Beziehung und potenzielle Aggregation an.</span><span class="sxs-lookup"><span data-stu-id="54081-128">For [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], this specifies a natural relationship and potential aggregation.</span></span> <span data-ttu-id="54081-129">In der Customer-Dimension besteht für die Attribute Country, Region, City und Customer eine natürliche Hierarchie.</span><span class="sxs-lookup"><span data-stu-id="54081-129">In the Customer dimension, a natural hierarchy exists for the Country, Region, City, and Customer attributes.</span></span> <span data-ttu-id="54081-130">Die natürliche Hierarchie für `{Country, Region, City, Customer}` wird durch Hinzufügen der folgenden Attributbeziehungen beschrieben:</span><span class="sxs-lookup"><span data-stu-id="54081-130">The natural hierarchy for `{Country, Region, City, Customer}` is described by adding the following attribute relationships:</span></span>  
  
-   <span data-ttu-id="54081-131">Das Country-Attribut als Attributbeziehung zum Region-Attribut.</span><span class="sxs-lookup"><span data-stu-id="54081-131">The Country attribute as an attribute relationship to the Region attribute.</span></span>  
  
-   <span data-ttu-id="54081-132">Das Region-Attribut als Attributbeziehung zum City-Attribut.</span><span class="sxs-lookup"><span data-stu-id="54081-132">The Region attribute as an attribute relationship to the City attribute.</span></span>  
  
-   <span data-ttu-id="54081-133">Das City-Attribut als Attributbeziehung zum Customer-Attribut.</span><span class="sxs-lookup"><span data-stu-id="54081-133">The City attribute as an attribute relationship to the Customer attribute.</span></span>  
  
 <span data-ttu-id="54081-134">Zum Navigieren von Daten im Cube können Sie auch eine benutzerdefinierte Hierarchie erstellen, die keine natürliche Hierarchie in den Daten darstellt (Dies wird als *Ad-hoc-* oder *Berichterstattungs* Hierarchie bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="54081-134">For navigating data in the cube, you can also create a user-defined hierarchy that does not represent a natural hierarchy in the data (which is called an *ad hoc* or *reporting* hierarchy).</span></span> <span data-ttu-id="54081-135">Sie könnten z. B. eine benutzerdefinierte Hierarchie auf der Basis von `{Age, Gender}` erstellen.</span><span class="sxs-lookup"><span data-stu-id="54081-135">For example, you could create a user-defined hierarchy based on `{Age, Gender}`.</span></span> <span data-ttu-id="54081-136">Benutzer sehen keinen Unterschied in der Art und Weise, wie sich die beiden Hierarchien Verhalten. die natürliche Hierarchie profitiert von Aggregations-und Indizierungs Strukturen, die für die natürlichen Beziehungen in den Quelldaten ausgeblendet sind.</span><span class="sxs-lookup"><span data-stu-id="54081-136">Users do not see any difference in how the two hierarchies behave, although the natural hierarchy benefits from aggregating and indexing structures - hidden from the user - that account for the natural relationships in the source data.</span></span>  
  
 <span data-ttu-id="54081-137">Durch die `SourceAttribute`-Eigenschaft einer Ebene ist festgelegt, mit welchem Attribut die Ebene beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="54081-137">The `SourceAttribute` property of a level determines which attribute is used to describe the level.</span></span> <span data-ttu-id="54081-138">Die `KeyColumns`-Eigenschaft des Attributs gibt an, welche Spalte in der Datenquellensicht die Elemente bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="54081-138">The `KeyColumns` property on the attribute specifies the column in the data source view that supplies the members.</span></span> <span data-ttu-id="54081-139">Mit der `NameColumn`-Eigenschaft des Attributs kann eine andere Namensspalte für die Elemente festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="54081-139">The `NameColumn` property on the attribute can specify a different name column for the members.</span></span>  
  
 <span data-ttu-id="54081-140">Zum Definieren einer Ebene in einer benutzerdefinierten Hierarchie mithilfe von [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] können Sie mit dem **Dimensions-Designer** ein Dimensions Attribut, eine Spalte in einer Dimensions Tabelle oder eine Spalte aus einer verknüpften Tabelle auswählen, die in der Datenquellen Sicht für den Cube enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="54081-140">To define a level in a user-defined hierarchy using [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], the **Dimension Designer** allows you to select a dimension attribute, a column in a dimension table, or a column from a related table included in the data source view for the cube.</span></span> <span data-ttu-id="54081-141">Weitere Informationen zum Erstellen von benutzerdefinierten Hierarchien finden Sie unter [Erstellen von benutzerdefinierten Hierarchien](../multidimensional-models/user-defined-hierarchies-create.md).</span><span class="sxs-lookup"><span data-stu-id="54081-141">For more information about creating user-defined hierarchies, see [Create User-Defined Hierarchies](../multidimensional-models/user-defined-hierarchies-create.md).</span></span>  
  
 <span data-ttu-id="54081-142">In Analysis Services erfolgt in der Regel eine Annahme zum Inhalt von Elementen.</span><span class="sxs-lookup"><span data-stu-id="54081-142">In Analysis Services, an assumption is usually made about the content of members.</span></span> <span data-ttu-id="54081-143">Blattelemente haben keine nachfolgenden Werte und enthalten von zugrunde liegenden Datenquellen abgeleitete Daten.</span><span class="sxs-lookup"><span data-stu-id="54081-143">Leaf members have no descendents and contain data derived from underlying data sources.</span></span> <span data-ttu-id="54081-144">Nicht-Blattelemente haben nachfolgende Werte und enthalten von Aggregationen abgeleitete Daten, die für untergeordnete Elemente ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="54081-144">Nonleaf members have descendents and contain data derived from aggregations performed on child members.</span></span> <span data-ttu-id="54081-145">Auf aggregierten Ebenen basieren Elemente auf Aggregationen der untergeordneten Ebenen.</span><span class="sxs-lookup"><span data-stu-id="54081-145">In aggregated levels, members are based on aggregations of subordinate levels.</span></span> <span data-ttu-id="54081-146">Wenn also die `IsAggregatable`-Eigenschaft für das Quellattribut einer Ebene auf `False` festgelegt ist, sollten keine aggregierbaren Attribute als nächst höhere Ebenen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="54081-146">Therefore, when the `IsAggregatable` property is set to `False` on a source attribute for a level, no aggregatable attributes should be added as levels above it.</span></span>  
  
## <a name="defining-an-attribute-relationship"></a><span data-ttu-id="54081-147">Definieren einer Attributbeziehung</span><span class="sxs-lookup"><span data-stu-id="54081-147">Defining an Attribute Relationship</span></span>  
 <span data-ttu-id="54081-148">Die wesentliche Einschränkung beim Erstellen einer Attributbeziehung liegt darin, sicherzustellen, dass das Attribut, auf das durch die Attributbeziehung verwiesen wird, maximal einen Wert für jeweils ein Element in dem Attribut aufweist, zu dem die Attributbeziehung gehört.</span><span class="sxs-lookup"><span data-stu-id="54081-148">The main constraint when you create an attribute relationship is to make sure that the attribute referred to by the attribute relationship has no more than one value for any member in the attribute to which the attribute relationship belongs.</span></span> <span data-ttu-id="54081-149">Wenn Sie beispielsweise eine Beziehung zwischen einem City-Attribut und einem State-Attribut definieren, kann sich jede Stadt nur auf ein Bundesland beziehen.</span><span class="sxs-lookup"><span data-stu-id="54081-149">For example, if you define a relationship between a City attribute and a State attribute, each city can only relate to a single state.</span></span>  
  
## <a name="attribute-relationship-queries"></a><span data-ttu-id="54081-150">Abfragen von Attributbeziehungen</span><span class="sxs-lookup"><span data-stu-id="54081-150">Attribute Relationship Queries</span></span>  
 <span data-ttu-id="54081-151">Sie können MDX-Abfragen verwenden, um Daten aus Attributbeziehungen abzurufen, und zwar in Form von Elementeigenschaften, mit dem `PROPERTIES`-Schlüsselwort der `SELECT`-MDX-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="54081-151">You can use MDX queries to retrieve data from attribute relationships, in the form of member properties, with the `PROPERTIES` keyword of the MDX `SELECT` statement.</span></span> <span data-ttu-id="54081-152">Weitere Informationen zum Verwenden von MDX zum Abrufen von Element Eigenschaften finden Sie unter [using Member Properties &#40;MDX&#41;](../multidimensional-models/mdx/mdx-member-properties.md).</span><span class="sxs-lookup"><span data-stu-id="54081-152">For more information about how to use MDX to retrieve member properties, see [Using Member Properties &#40;MDX&#41;](../multidimensional-models/mdx/mdx-member-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54081-153">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="54081-153">See Also</span></span>  
 <span data-ttu-id="54081-154">[Attribute und Attribut Hierarchien](attributes-and-attribute-hierarchies.md) </span><span class="sxs-lookup"><span data-stu-id="54081-154">[Attributes and Attribute Hierarchies](attributes-and-attribute-hierarchies.md) </span></span>  
 <span data-ttu-id="54081-155">[Dimensions Attribut-Eigenschaften Referenz](../multidimensional-models/dimension-attribute-properties-reference.md) </span><span class="sxs-lookup"><span data-stu-id="54081-155">[Dimension Attribute Properties Reference](../multidimensional-models/dimension-attribute-properties-reference.md) </span></span>  
 <span data-ttu-id="54081-156">[Benutzer Hierarchien](user-hierarchies.md) </span><span class="sxs-lookup"><span data-stu-id="54081-156">[User Hierarchies](user-hierarchies.md) </span></span>  
 [<span data-ttu-id="54081-157">Eigenschaften der Benutzerhierarchie</span><span class="sxs-lookup"><span data-stu-id="54081-157">User Hierarchy Properties</span></span>](user-hierarchies-properties.md)  
  
  
