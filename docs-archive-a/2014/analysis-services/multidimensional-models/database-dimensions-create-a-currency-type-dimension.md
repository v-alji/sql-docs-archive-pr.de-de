---
title: Erstellen einer Currency Type-Dimension | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- dimensions [Analysis Services], currency
- currency [Analysis Services]
- converting currency
- currency dimensions [Analysis Services]
ms.assetid: b1f037d1-ce47-4e47-a1c2-5ec9e781cff6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 91123fb5fda898e90056057114295335fbd1d32c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698684"
---
# <a name="create-a-currency-type-dimension"></a><span data-ttu-id="0b440-102">Erstellen einer Währungstypdimension</span><span class="sxs-lookup"><span data-stu-id="0b440-102">Create a Currency type Dimension</span></span>
  <span data-ttu-id="0b440-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ist eine Dimension vom Typ Currency eine Dimension, deren Attribute eine Liste von Währungen für Finanzberichte darstellen.</span><span class="sxs-lookup"><span data-stu-id="0b440-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], a currency type dimension is a dimension whose attributes represent a list of currencies for financial reporting purposes.</span></span>  
  
 <span data-ttu-id="0b440-104">Mit einer Währungsdimension können Sie einem Cube in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]Funktionen für die Währungsumrechnung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0b440-104">A currency dimension lets you add currency conversion capabilities to a cube in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="0b440-105">Wenn Sie einem Cube die Währungsumrechnung hinzufügen möchten, verwenden Sie den Business Intelligence-Assistenten zum Definieren eines Multidimensional Expressions-(MDX-)Skriptbefehls, der Währungsmeasures in Werte konvertiert, die für das Gebietsschema der Clientanwendung geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="0b440-105">To add currency conversion to a cube, you use the Business Intelligence Wizard define a Multidimensional Expressions (MDX) script command that converts currency measures to values that are appropriate for the locale of the client application.</span></span> <span data-ttu-id="0b440-106">Um dieses MDX-Skript erstellen zu können, benötigt der Business Intelligence-Assistent folgende Informationen:</span><span class="sxs-lookup"><span data-stu-id="0b440-106">To create this MDX script, the Business Intelligence Wizard needs the following information:</span></span>  
  
-   <span data-ttu-id="0b440-107">Eine Währungsdimension, die Quellwährungen darstellt.</span><span class="sxs-lookup"><span data-stu-id="0b440-107">A currency dimension that represents source currencies.</span></span> <span data-ttu-id="0b440-108">(Bei dieser Dimension handelt es sich um die Quellwährungsdimension.)</span><span class="sxs-lookup"><span data-stu-id="0b440-108">(This dimension is the source currency dimension.)</span></span>  
  
-   <span data-ttu-id="0b440-109">Eine Measuregruppe, die die zu verwendenden Wechselkurse darstellt.</span><span class="sxs-lookup"><span data-stu-id="0b440-109">A measure group that represents the exchange rates that will be used.</span></span>  
  
 <span data-ttu-id="0b440-110">Anhand dieser Informationen entwirft der Business Intelligence-Assistent einen Währungsumrechnungsprozess, der die entsprechende Zielwährungsdimension (die Währungsdimension, die Zielwährungen darstellt) identifiziert.</span><span class="sxs-lookup"><span data-stu-id="0b440-110">From this information, the Business Intelligence Wizard will design a currency conversion process that identifies the appropriate destination currency dimension (the currency dimension that represents destination currencies).</span></span> <span data-ttu-id="0b440-111">Abhängig von der Anzahl der Währungsumrechnungen, die für Ihre Business Intelligence-Lösung erforderlich sind, kann der Business Intelligence-Assistent mehrere Zielwährungsdimensionen definieren.</span><span class="sxs-lookup"><span data-stu-id="0b440-111">Depending on the number of currency conversions that your business intelligence solution requires, the Business Intelligence Wizard can define multiple destination currency dimensions.</span></span> <span data-ttu-id="0b440-112">Weitere Informationen zum Definieren von Währungsumrechnungen finden Sie unter [Währungsumrechnungen &#40;Analysis Services&#41;](../currency-conversions-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="0b440-112">For more information about defining currency conversions, see [Currency Conversions &#40;Analysis Services&#41;](../currency-conversions-analysis-services.md).</span></span>  
  
 <span data-ttu-id="0b440-113">Wenn Sie eine Dimension als Währungsdimension identifizieren möchten, legen Sie die `Type`-Eigenschaft der Dimension auf `Currency` fest.</span><span class="sxs-lookup"><span data-stu-id="0b440-113">To identify a dimension as a currency dimension, set the `Type` property of the dimension to `Currency`.</span></span>  
  
## <a name="dimension-structure"></a><span data-ttu-id="0b440-114">Dimensionsstruktur</span><span class="sxs-lookup"><span data-stu-id="0b440-114">Dimension Structure</span></span>  
 <span data-ttu-id="0b440-115">Eine Währungsdimension enthält zumindest ein Schlüsselattribut, das die einzelnen Währungen in der Dimensionstabelle für die Währungsdimension identifiziert.</span><span class="sxs-lookup"><span data-stu-id="0b440-115">A currency dimension contains, at least, a key attribute identifying individual currencies in the dimension table for the currency dimension.</span></span> <span data-ttu-id="0b440-116">Der Wert des Schlüsselattributs ist in Quell- und Zielwährungsdimensionen unterschiedlich.</span><span class="sxs-lookup"><span data-stu-id="0b440-116">The value of the key attribute is different in both source and destination currency dimensions:</span></span>  
  
-   <span data-ttu-id="0b440-117">Wenn Sie ein Attribut als Schlüsselattribut einer Quellwährungsdimension identifizieren möchten, legen Sie die `Type`-Eigenschaft des Attributs auf `CurrencySource` fest.</span><span class="sxs-lookup"><span data-stu-id="0b440-117">To identify an attribute as the key attribute of a source currency dimension, set the `Type` property of the attribute to `CurrencySource`.</span></span>  
  
-   <span data-ttu-id="0b440-118">Wenn Sie ein Attribut als Zielwährungsdimension identifizieren möchten, legen Sie die `Type`-Eigenschaft des Attributs auf `CurrencyDestination` fest.</span><span class="sxs-lookup"><span data-stu-id="0b440-118">To identify an attribute as the destination currency dimension, set the `Type` property of the attribute to `CurrencyDestination`.</span></span>  
  
 <span data-ttu-id="0b440-119">Für Berichtszwecke enthalten sowohl Quell- als auch Zielwährungsdimensionen optional folgende Attribute:</span><span class="sxs-lookup"><span data-stu-id="0b440-119">For reporting purposes, both source and destination currency dimensions can optionally contain the following attributes:</span></span>  
  
-   <span data-ttu-id="0b440-120">Ein Attribut für den Namen der Währung.</span><span class="sxs-lookup"><span data-stu-id="0b440-120">A currency name attribute.</span></span>  
  
     <span data-ttu-id="0b440-121">Wenn Sie ein Attribut als Attribut für den Namen der Währung identifizieren möchten, legen Sie die `Type`-Eigenschaft des Attributs auf `CurrencyName` fest.</span><span class="sxs-lookup"><span data-stu-id="0b440-121">To identify an attribute as a currency name attribute, set the `Type` property of the attribute to `CurrencyName`.</span></span>  
  
-   <span data-ttu-id="0b440-122">Ein Attribut für die Quelle der Währung.</span><span class="sxs-lookup"><span data-stu-id="0b440-122">A currency source attribute.</span></span>  
  
     <span data-ttu-id="0b440-123">Wenn Sie ein Attribut als Attribut für die Quelle der Währung identifizieren möchten, legen Sie die `Type`-Eigenschaft des Attributs auf `CurrencySource` fest.</span><span class="sxs-lookup"><span data-stu-id="0b440-123">To identify an attribute as a currency source attribute, set the `Type` property of the attribute to `CurrencySource`.</span></span>  
  
-   <span data-ttu-id="0b440-124">Einen Währungscode gemäß der International Standards Organization (ISO).</span><span class="sxs-lookup"><span data-stu-id="0b440-124">A currency International Standards Organization (ISO) code.</span></span>  
  
     <span data-ttu-id="0b440-125">Wenn Sie ein Attribut als Attribut für den ISO-Währungscode identifizieren möchten, legen Sie die `Type`-Eigenschaft des Attributs auf `CurrencyIsoCode` fest.</span><span class="sxs-lookup"><span data-stu-id="0b440-125">To identify an attribute as a currency ISO code attribute, set the `Type` property of the attribute to `CurrencyIsoCode`.</span></span>  
  
 <span data-ttu-id="0b440-126">Weitere Informationen zu Attributtypen finden Sie unter [Konfigurieren von Attributtypen](attribute-properties-configure-attribute-types.md).</span><span class="sxs-lookup"><span data-stu-id="0b440-126">For more information about attribute types, see [Configure Attribute Types](attribute-properties-configure-attribute-types.md).</span></span>  
  
## <a name="defining-account-intelligence-with-the-business-intelligence-wizard"></a><span data-ttu-id="0b440-127">Definieren von Kontointelligenz mit dem Business Intelligence-Assistenten</span><span class="sxs-lookup"><span data-stu-id="0b440-127">Defining Account Intelligence with the Business Intelligence Wizard</span></span>  
 <span data-ttu-id="0b440-128">Nachdem Sie eine Kontodimension definiert und diese Dimension einem Cube hinzugefügt haben, können Sie den Business Intelligence-Assistenten verwenden, um der Dimension die Kontointelligenzfunktionalität hinzuzufügen, beispielsweise das Identifizieren und Zuordnen von Kontotypen.</span><span class="sxs-lookup"><span data-stu-id="0b440-128">After you have defined an account dimension and added that dimension to a cube, you can use the Business Intelligence Wizard to add account intelligence functionality, such as identifying and mapping account types, to the dimension.</span></span> <span data-ttu-id="0b440-129">Weitere Informationen finden Sie unter [Hinzufügen von Kontointelligenz zu einer Dimension](bi-wizard-add-account-intelligence-to-a-dimension.md).</span><span class="sxs-lookup"><span data-stu-id="0b440-129">For more information, see [Add Account Intelligence to a Dimension](bi-wizard-add-account-intelligence-to-a-dimension.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b440-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0b440-130">See Also</span></span>  
 <span data-ttu-id="0b440-131">[Attribute und Attribut Hierarchien](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md) </span><span class="sxs-lookup"><span data-stu-id="0b440-131">[Attributes and Attribute Hierarchies](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md) </span></span>  
 <span data-ttu-id="0b440-132">[Business Intelligence Wizard (F1-Hilfe)](../business-intelligence-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="0b440-132">[Business Intelligence Wizard F1 Help](../business-intelligence-wizard-f1-help.md) </span></span>  
 [<span data-ttu-id="0b440-133">Dimensionstypen</span><span class="sxs-lookup"><span data-stu-id="0b440-133">Dimension Types</span></span>](../multidimensional-models-olap-logical-dimension-objects/database-dimension-properties-types.md)  
  
  
