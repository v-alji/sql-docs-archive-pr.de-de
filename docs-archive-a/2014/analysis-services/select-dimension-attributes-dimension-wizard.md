---
title: Dimensions Attribute auswählen (Dimensions-Assistent) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensionwizard.dimensionattributes.f1
ms.assetid: f58a3e14-ab27-44d3-8c26-f5c9ee7583b0
author: minewiskan
ms.author: owend
ms.openlocfilehash: a4961092517ce1d38cfd4086ec083a939242652d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615641"
---
# <a name="select-dimension-attributes-dimension-wizard"></a><span data-ttu-id="79a9b-102">Dimensionsattribute auswählen (Dimensions-Assistent)</span><span class="sxs-lookup"><span data-stu-id="79a9b-102">Select Dimension Attributes (Dimension Wizard)</span></span>
  <span data-ttu-id="79a9b-103">Auf der Seite **Dimensionsattribute auswählen** können Sie die Attribute für die zu erstellende Dimension auswählen und ändern.</span><span class="sxs-lookup"><span data-stu-id="79a9b-103">Use the **Select Dimension Attributes** page to select and modify the attributes for the dimension to be created.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="79a9b-104">Wenn die Werte einer Spalte nicht vollständig angezeigt werden, können Sie das Assistentenfenster maximieren und die Breite jeder Spaltenüberschrift ändern, bis Sie die Werte lesen können.</span><span class="sxs-lookup"><span data-stu-id="79a9b-104">If you cannot read the values for any column, maximize the wizard window and change the width of each column heading until you can read the values.</span></span>  
  
 <span data-ttu-id="79a9b-105">**So öffnen Sie den Dimensions-Assistenten**</span><span class="sxs-lookup"><span data-stu-id="79a9b-105">**To open the Dimension Wizard**</span></span>  
  
-   <span data-ttu-id="79a9b-106">Klicken Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]im **Projektmappen-Explorer**mit der rechten Maustaste auf den Ordner **Dimensionen** eines [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Projekts, und klicken Sie anschließend auf **Neue Dimension**.</span><span class="sxs-lookup"><span data-stu-id="79a9b-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], in **Solution Explorer**, right-click the **Dimensions** folder for an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, and then click **New Dimension**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="79a9b-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="79a9b-107">Options</span></span>  
 <span data-ttu-id="79a9b-108">(Spalte mit Kontrollkästchen)</span><span class="sxs-lookup"><span data-stu-id="79a9b-108">(Column with check boxes)</span></span>  
 <span data-ttu-id="79a9b-109">Wählen Sie diese Option aus, um ein Attribut in die Dimension einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="79a9b-109">Select to include an attribute in the dimension.</span></span>  
  
 <span data-ttu-id="79a9b-110">Wenn Sie ein spezielles Attribut einschließen möchten, aktivieren Sie das Kontrollkästchen für dieses Attribut.</span><span class="sxs-lookup"><span data-stu-id="79a9b-110">To include a specific attribute, select the check box for that attribute.</span></span>  
  
 <span data-ttu-id="79a9b-111">Wenn Sie alle Attribute einschließen möchten, aktivieren Sie das Kontrollkästchen im Spaltenheader.</span><span class="sxs-lookup"><span data-stu-id="79a9b-111">To include all attributes, select the check box in the column header.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="79a9b-112">Das Kontrollkästchen für das Schlüsselattribut kann nicht deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="79a9b-112">The check box for the key attribute cannot be cleared.</span></span>  
  
 <span data-ttu-id="79a9b-113">**Attributname**</span><span class="sxs-lookup"><span data-stu-id="79a9b-113">**Attribute Name**</span></span>  
 <span data-ttu-id="79a9b-114">Listet die verfügbaren Attribute auf.</span><span class="sxs-lookup"><span data-stu-id="79a9b-114">Lists the available attributes.</span></span>  
  
 <span data-ttu-id="79a9b-115">Wenn Sie den Namen eines Attributs ändern möchten, klicken Sie auf den Attributnamen, und geben Sie einen neuen Namen ein.</span><span class="sxs-lookup"><span data-stu-id="79a9b-115">To change the name of an attribute, click the attribute name and type a new name for the attribute.</span></span>  
  
 <span data-ttu-id="79a9b-116">**Durchsuchen aktivieren**</span><span class="sxs-lookup"><span data-stu-id="79a9b-116">**Enable Browsing**</span></span>  
 <span data-ttu-id="79a9b-117">Wählen Sie diese Option aus, damit der Endbenutzer das Attribut durchsuchen und filtern kann.</span><span class="sxs-lookup"><span data-stu-id="79a9b-117">Select to make the attribute available to the end user for browsing and filtering.</span></span> <span data-ttu-id="79a9b-118">Die Option**Durchsuchen aktivieren** muss für das Schlüsselattribut aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="79a9b-118">**Enable Browsing** must be selected for the key attribute.</span></span> <span data-ttu-id="79a9b-119">In der Standardeinstellung ist die Option **Durchsuchen aktivieren** bei Attributen, die keine Schlüsselattribut sind, nicht aktiviert, sodass diese nur als Elementeigenschaften dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="79a9b-119">For non-key attributes, the default is not to have **Enable Browsing** selected, which causes the non-key attributes to be shown only as member properties.</span></span>  
  
 <span data-ttu-id="79a9b-120">In den meisten Fällen wird das Durchsuchen eines Attributs ermöglicht oder unterbunden, indem die `AttributeHierarchyEnabled`-Eigenschaft auf `True` bzw. `False` festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="79a9b-120">In most cases, the attribute is made available or not available for browsing by setting the `AttributeHierarchyEnabled` property to `True` or `False`, respectively.</span></span> <span data-ttu-id="79a9b-121">In den folgenden drei Fällen verwendet der Assistent jedoch andere Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="79a9b-121">However, in the following three cases, the wizard uses different settings.</span></span>  
  
|<span data-ttu-id="79a9b-122">Fall</span><span class="sxs-lookup"><span data-stu-id="79a9b-122">Case</span></span>|<span data-ttu-id="79a9b-123">Einstellungen</span><span class="sxs-lookup"><span data-stu-id="79a9b-123">Settings</span></span>|  
|----------|--------------|  
|<span data-ttu-id="79a9b-124">Eine Dimension enthält eine Über-/Unterordnungshierarchie, und die Option **Durchsuchen aktivieren** ist nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="79a9b-124">A dimension contains a parent-child hierarchy and **Enable Browsing** is not selected</span></span>|<span data-ttu-id="79a9b-125">Der Assistent behält für die `AttributeHierarchyEnabled`-Eigenschaft die Einstellung `True` bei und legt das `AttributeHierarchyVisible`-Attribut für das Schlüsselattribut auf `False` fest.</span><span class="sxs-lookup"><span data-stu-id="79a9b-125">The wizard leaves the `AttributeHierarchyEnabled` property set to `True`, and sets the `AttributeHierarchyVisible` attribute to `False` for the key attribute.</span></span>|  
|<span data-ttu-id="79a9b-126">Eine Tabelle in einer Dimension enthält einen Fremdschlüssel für eine Tabelle, die nicht in der Dimension enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="79a9b-126">A table in a dimension contains a foreign key to a table that is not in the dimension</span></span>|<span data-ttu-id="79a9b-127">Der Assistent wählt den Fremdschlüssel als aufzunehmendes Attribut aus, aktiviert die Option **Durchsuchen aktivieren**aber nicht.</span><span class="sxs-lookup"><span data-stu-id="79a9b-127">The wizard selects the foreign key as an attribute to be included, but will not select **Enable Browsing**.</span></span> <span data-ttu-id="79a9b-128">Wenn Sie diese Einstellungen beibehalten, dann ist die `AttributeHiearchyEnabled`-Eigenschaft des Attributs auf `True` festgelegt, und die `AttributeHierarchyVisible`Eigenschaft ist auf `False` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="79a9b-128">If you keep these settings, the `AttributeHiearchyEnabled` property of the attribute will be set to `True`, and the `AttributeHierarchyVisible` property will be set to `False`.</span></span>|  
|<span data-ttu-id="79a9b-129">Eine Dimension enthält Schneeflockentabellen, die durch auf NULL festlegbare Fremdschlüsselspalten erreicht werden</span><span class="sxs-lookup"><span data-stu-id="79a9b-129">A dimension contains snowflake tables that are reached through nullable foreign key columns</span></span><br /><br /> <span data-ttu-id="79a9b-130">- und -</span><span class="sxs-lookup"><span data-stu-id="79a9b-130">-and-</span></span><br /><br /> <span data-ttu-id="79a9b-131">Die Option Durchsuchen aktivieren wird für das Attribut, das auf dem Schlüssel der Schneeflockentabelle basiert, nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="79a9b-131">Enable Browsing for the attribute that is based on the key of the snowflake table is not selected</span></span>|<span data-ttu-id="79a9b-132">Der Assistent erstellt das neue Attribut, dessen `AttributeHiearchyEnabled`-Eigenschaft auf `True` und dessen `AttributeHierarchyVisible`-Eigenschaft auf `False` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="79a9b-132">The wizard will create the new attribute that has the `AttributeHiearchyEnabled` property set to `True`, and the `AttributeHierarchyVisible` property set to `False`.</span></span>|  
  
 <span data-ttu-id="79a9b-133">**Attributtyp**</span><span class="sxs-lookup"><span data-stu-id="79a9b-133">**Attribute Type**</span></span>  
 <span data-ttu-id="79a9b-134">(Optional) Legen Sie den Typ des Attributs fest.</span><span class="sxs-lookup"><span data-stu-id="79a9b-134">(Optional) Set the type for the attribute.</span></span> <span data-ttu-id="79a9b-135">Der Standardwert ist **Regulär**.</span><span class="sxs-lookup"><span data-stu-id="79a9b-135">The default value is **Regular**.</span></span> <span data-ttu-id="79a9b-136">Der Attributtyp stellt Clientanwendungen Hinweise dazu bereit, welche Informationen das Attribut enthält.</span><span class="sxs-lookup"><span data-stu-id="79a9b-136">The attribute type provides guidance to client applications on what information the attribute might contain.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79a9b-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="79a9b-137">See Also</span></span>  
 <span data-ttu-id="79a9b-138">[Dimensions-Assistent F1-Hilfe](dimension-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="79a9b-138">[Dimension Wizard F1 Help](dimension-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="79a9b-139">[Dimensionen &#40;Analysis Services Mehrdimensionale Daten&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="79a9b-139">[Dimensions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="79a9b-140">Dimensionen in mehrdimensionalen Modellen</span><span class="sxs-lookup"><span data-stu-id="79a9b-140">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
