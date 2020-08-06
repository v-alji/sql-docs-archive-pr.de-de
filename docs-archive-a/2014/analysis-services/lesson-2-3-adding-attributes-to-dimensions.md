---
title: Hinzufügen von Attributen zu Dimensionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 80551dad-97ac-40d0-90af-b810780321ce
author: minewiskan
ms.author: owend
ms.openlocfilehash: 76a04c42cc501fdca3e5ceb6481452052966796b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608030"
---
# <a name="adding-attributes-to-dimensions"></a><span data-ttu-id="e9a7e-102">Hinzufügen von Attributen zu Dimensionen</span><span class="sxs-lookup"><span data-stu-id="e9a7e-102">Adding Attributes to Dimensions</span></span>
  <span data-ttu-id="e9a7e-103">Nachdem Sie Dimensionen definiert haben, können Sie sie jetzt mit Attributen auffüllen, die die einzelnen Datenelemente in der Dimension darstellen.</span><span class="sxs-lookup"><span data-stu-id="e9a7e-103">Now that you have defined dimensions, you can populate them with attributes that represent each data element in the dimension.</span></span> <span data-ttu-id="e9a7e-104">Attribute basieren normalerweise auf Feldern einer Datenquellensicht.</span><span class="sxs-lookup"><span data-stu-id="e9a7e-104">Attributes are commonly based on fields from a data source view.</span></span> <span data-ttu-id="e9a7e-105">Wenn Sie einer Dimension Attribute hinzufügen, können Sie Felder einer beliebigen Tabelle in die Datenquellensicht einschließen.</span><span class="sxs-lookup"><span data-stu-id="e9a7e-105">When adding attributes to a dimension, you can include fields from any table in the data source view.</span></span>  
  
 <span data-ttu-id="e9a7e-106">In dieser Aufgabe verwenden Sie den Dimensions-Designer, um der Customer-Dimension und der Produkt-Dimension Attribute hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="e9a7e-106">In this task, you will use Dimension Designer to add attributes to the Customer and Product dimensions.</span></span> <span data-ttu-id="e9a7e-107">Die Customer-Dimension schließt Attribute ein, die auf Feldern sowohl aus der Customer-Tabelle als auch aus der Geography-Tabelle basieren.</span><span class="sxs-lookup"><span data-stu-id="e9a7e-107">The Customer dimension will include attributes based on fields from both the Customer and Geography tables.</span></span>  
  
## <a name="adding-attributes-to-the-customer-dimension"></a><span data-ttu-id="e9a7e-108">Hinzufügen von Attributen zur Customer-Dimension.</span><span class="sxs-lookup"><span data-stu-id="e9a7e-108">Adding Attributes to the Customer Dimension</span></span>  
  
#### <a name="to-add-attributes"></a><span data-ttu-id="e9a7e-109">So fügen Sie Attribute hinzu</span><span class="sxs-lookup"><span data-stu-id="e9a7e-109">To add attributes</span></span>  
  
1.  <span data-ttu-id="e9a7e-110">Öffnen Sie den Dimensions-Designer für die Customer-Dimension.</span><span class="sxs-lookup"><span data-stu-id="e9a7e-110">Open Dimension Designer for the Customer dimension.</span></span> <span data-ttu-id="e9a7e-111">Doppelklicken Sie dazu auf die Dimension **Customer** im Knoten **Dimensionen** des Projektmappen-Explorers.</span><span class="sxs-lookup"><span data-stu-id="e9a7e-111">To do this, double-click the **Customer** dimension in the **Dimensions** node of Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="e9a7e-112">Beachten Sie im Bereich **Attribute** die Attribute "Customer Key" und "Geography Key", die vom Cube-Assistenten erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="e9a7e-112">In the **Attributes** pane, notice the Customer Key and Geography Key attributes that were created by the Cube Wizard.</span></span>  
  
3.  <span data-ttu-id="e9a7e-113">Verwenden Sie das Symbol zum Vergrößern auf der Symbolleiste der Registerkarte **Dimensionsstruktur** , um die Tabellen im Bereich **Datenquellensicht** in einer 100-Prozent-Darstellung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e9a7e-113">On the toolbar of the **Dimension Structure** tab, make sure the Zoom icon to view the tables in the **Data Source View** pane is set at 100 percent.</span></span>  
  
4.  <span data-ttu-id="e9a7e-114">Ziehen Sie die folgenden Spalten von der **Customer** -Tabelle im Bereich **Datenquellensicht** in den Bereich **Attribute** :</span><span class="sxs-lookup"><span data-stu-id="e9a7e-114">Drag the following columns from the **Customer** table in the **Data Source View** pane to the **Attributes** pane:</span></span>  
  
    -   <span data-ttu-id="e9a7e-115">**BirthDate**</span><span class="sxs-lookup"><span data-stu-id="e9a7e-115">**BirthDate**</span></span>  
  
    -   <span data-ttu-id="e9a7e-116">**MaritalStatus**</span><span class="sxs-lookup"><span data-stu-id="e9a7e-116">**MaritalStatus**</span></span>  
  
    -   <span data-ttu-id="e9a7e-117">**Geschlecht**</span><span class="sxs-lookup"><span data-stu-id="e9a7e-117">**Gender**</span></span>  
  
    -   <span data-ttu-id="e9a7e-118">**EmailAddress**</span><span class="sxs-lookup"><span data-stu-id="e9a7e-118">**EmailAddress**</span></span>  
  
    -   <span data-ttu-id="e9a7e-119">**YearlyIncome**</span><span class="sxs-lookup"><span data-stu-id="e9a7e-119">**YearlyIncome**</span></span>  
  
    -   <span data-ttu-id="e9a7e-120">**TotalChildren**</span><span class="sxs-lookup"><span data-stu-id="e9a7e-120">**TotalChildren**</span></span>  
  
    -   <span data-ttu-id="e9a7e-121">**NumberChildrenAtHome**</span><span class="sxs-lookup"><span data-stu-id="e9a7e-121">**NumberChildrenAtHome**</span></span>  
  
    -   <span data-ttu-id="e9a7e-122">**EnglishEducation**</span><span class="sxs-lookup"><span data-stu-id="e9a7e-122">**EnglishEducation**</span></span>  
  
    -   <span data-ttu-id="e9a7e-123">**EnglishOccupation**</span><span class="sxs-lookup"><span data-stu-id="e9a7e-123">**EnglishOccupation**</span></span>  
  
    -   <span data-ttu-id="e9a7e-124">**HouseOwnerFlag**</span><span class="sxs-lookup"><span data-stu-id="e9a7e-124">**HouseOwnerFlag**</span></span>  
  
    -   <span data-ttu-id="e9a7e-125">**NumberCarsOwned**</span><span class="sxs-lookup"><span data-stu-id="e9a7e-125">**NumberCarsOwned**</span></span>  
  
    -   <span data-ttu-id="e9a7e-126">**Smartphone**</span><span class="sxs-lookup"><span data-stu-id="e9a7e-126">**Phone**</span></span>  
  
    -   <span data-ttu-id="e9a7e-127">**DateFirstPurchase**</span><span class="sxs-lookup"><span data-stu-id="e9a7e-127">**DateFirstPurchase**</span></span>  
  
    -   <span data-ttu-id="e9a7e-128">**CommuteDistance**</span><span class="sxs-lookup"><span data-stu-id="e9a7e-128">**CommuteDistance**</span></span>  
  
5.  <span data-ttu-id="e9a7e-129">Ziehen Sie die folgenden Spalten von der **Geography** -Tabelle im Bereich **Datenquellensicht** in den Bereich **Attribute** :</span><span class="sxs-lookup"><span data-stu-id="e9a7e-129">Drag the following columns from the **Geography** table in the **Data Source View** pane to the **Attributes** pane:</span></span>  
  
    -   <span data-ttu-id="e9a7e-130">**City (Ort)**</span><span class="sxs-lookup"><span data-stu-id="e9a7e-130">**City**</span></span>  
  
    -   <span data-ttu-id="e9a7e-131">**StateProvinceName**</span><span class="sxs-lookup"><span data-stu-id="e9a7e-131">**StateProvinceName**</span></span>  
  
    -   <span data-ttu-id="e9a7e-132">**EnglishCountryRegionName**</span><span class="sxs-lookup"><span data-stu-id="e9a7e-132">**EnglishCountryRegionName**</span></span>  
  
    -   <span data-ttu-id="e9a7e-133">**PostalCode**</span><span class="sxs-lookup"><span data-stu-id="e9a7e-133">**PostalCode**</span></span>  
  
6.  <span data-ttu-id="e9a7e-134">Klicken Sie im Menü File (Datei) auf **Save All** (Alles speichern).</span><span class="sxs-lookup"><span data-stu-id="e9a7e-134">On the File menu, click **Save All**.</span></span>  
  
## <a name="adding-attributes-to-the-product-dimension"></a><span data-ttu-id="e9a7e-135">Hinzufügen von Attributen zur Product-Dimension.</span><span class="sxs-lookup"><span data-stu-id="e9a7e-135">Adding Attributes to the Product Dimension</span></span>  
  
#### <a name="to-add-attributes"></a><span data-ttu-id="e9a7e-136">So fügen Sie Attribute hinzu</span><span class="sxs-lookup"><span data-stu-id="e9a7e-136">To add attributes</span></span>  
  
1.  <span data-ttu-id="e9a7e-137">Öffnen Sie den Dimensions-Designer für die Product-Dimension.</span><span class="sxs-lookup"><span data-stu-id="e9a7e-137">Open Dimension Designer for the Product dimension.</span></span> <span data-ttu-id="e9a7e-138">Doppelklicken Sie im Projektmappen-Explorer auf die Dimension **Product** .</span><span class="sxs-lookup"><span data-stu-id="e9a7e-138">Double-click the **Product** dimension in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="e9a7e-139">Beachten Sie im Bereich **Attribute** das Attribut "Product Key", das vom Cube-Assistenten erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="e9a7e-139">In the **Attributes** pane, notice the Product Key attribute that was created by the Cube Wizard.</span></span>  
  
3.  <span data-ttu-id="e9a7e-140">Verwenden Sie das Symbol zum Vergrößern auf der Symbolleiste der Registerkarte **Dimensionsstruktur** , um die Tabellen im Bereich **Datenquellensicht** in einer 100-Prozent-Darstellung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e9a7e-140">On the toolbar of the **Dimension Structure** tab, make sure the Zoom icon to view the tables in the **Data Source View** pane is set at 100 percent.</span></span>  
  
4.  <span data-ttu-id="e9a7e-141">Ziehen Sie die folgenden Spalten von der **Product** -Tabelle im Bereich **Datenquellensicht** in den Bereich **Attribute** :</span><span class="sxs-lookup"><span data-stu-id="e9a7e-141">Drag the following columns from the **Product** table in the **Data Source View** pane to the **Attributes** pane:</span></span>  
  
    -   <span data-ttu-id="e9a7e-142">**StandardCost**</span><span class="sxs-lookup"><span data-stu-id="e9a7e-142">**StandardCost**</span></span>  
  
    -   <span data-ttu-id="e9a7e-143">**Farbe**</span><span class="sxs-lookup"><span data-stu-id="e9a7e-143">**Color**</span></span>  
  
    -   <span data-ttu-id="e9a7e-144">**SafetyStockLevel**</span><span class="sxs-lookup"><span data-stu-id="e9a7e-144">**SafetyStockLevel**</span></span>  
  
    -   <span data-ttu-id="e9a7e-145">**ReorderPoint**</span><span class="sxs-lookup"><span data-stu-id="e9a7e-145">**ReorderPoint**</span></span>  
  
    -   <span data-ttu-id="e9a7e-146">**ListPrice**</span><span class="sxs-lookup"><span data-stu-id="e9a7e-146">**ListPrice**</span></span>  
  
    -   <span data-ttu-id="e9a7e-147">**Größe**</span><span class="sxs-lookup"><span data-stu-id="e9a7e-147">**Size**</span></span>  
  
    -   <span data-ttu-id="e9a7e-148">**SizeRange**</span><span class="sxs-lookup"><span data-stu-id="e9a7e-148">**SizeRange**</span></span>  
  
    -   <span data-ttu-id="e9a7e-149">**Weight**</span><span class="sxs-lookup"><span data-stu-id="e9a7e-149">**Weight**</span></span>  
  
    -   <span data-ttu-id="e9a7e-150">**DaysToManufacture**</span><span class="sxs-lookup"><span data-stu-id="e9a7e-150">**DaysToManufacture**</span></span>  
  
    -   <span data-ttu-id="e9a7e-151">**ProductLine**</span><span class="sxs-lookup"><span data-stu-id="e9a7e-151">**ProductLine**</span></span>  
  
    -   <span data-ttu-id="e9a7e-152">**DealerPrice**</span><span class="sxs-lookup"><span data-stu-id="e9a7e-152">**DealerPrice**</span></span>  
  
    -   <span data-ttu-id="e9a7e-153">**Klasse**</span><span class="sxs-lookup"><span data-stu-id="e9a7e-153">**Class**</span></span>  
  
    -   <span data-ttu-id="e9a7e-154">**style**</span><span class="sxs-lookup"><span data-stu-id="e9a7e-154">**Style**</span></span>  
  
    -   <span data-ttu-id="e9a7e-155">**ModelName**</span><span class="sxs-lookup"><span data-stu-id="e9a7e-155">**ModelName**</span></span>  
  
    -   <span data-ttu-id="e9a7e-156">**StartDate**</span><span class="sxs-lookup"><span data-stu-id="e9a7e-156">**StartDate**</span></span>  
  
    -   <span data-ttu-id="e9a7e-157">**EndDate**</span><span class="sxs-lookup"><span data-stu-id="e9a7e-157">**EndDate**</span></span>  
  
    -   <span data-ttu-id="e9a7e-158">**Status**</span><span class="sxs-lookup"><span data-stu-id="e9a7e-158">**Status**</span></span>  
  
5.  <span data-ttu-id="e9a7e-159">Klicken Sie im Menü File (Datei) auf **Save All** (Alles speichern).</span><span class="sxs-lookup"><span data-stu-id="e9a7e-159">On the File menu, click **Save All**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="e9a7e-160">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="e9a7e-160">Next Task in Lesson</span></span>  
 [<span data-ttu-id="e9a7e-161">Überprüfen von Cube- und Dimensionseigenschaften</span><span class="sxs-lookup"><span data-stu-id="e9a7e-161">Reviewing Cube and Dimension Properties</span></span>](lesson-2-4-reviewing-cube-and-dimension-properties.md)  
  
## <a name="see-also"></a><span data-ttu-id="e9a7e-162">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e9a7e-162">See Also</span></span>  
 [<span data-ttu-id="e9a7e-163">Dimensionsattributeigenschaftenverweis</span><span class="sxs-lookup"><span data-stu-id="e9a7e-163">Dimension Attribute Properties Reference</span></span>](multidimensional-models/dimension-attribute-properties-reference.md)  
  
  
