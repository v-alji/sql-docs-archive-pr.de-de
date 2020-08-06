---
title: Quellcubedimension auswählen (Data Mining-Assistent) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.dmwizard.selectsourcecube.f1
ms.assetid: 556e216b-5e21-4160-967d-4c57591fbab4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6295a5312b4501236e0ce8f5776fc43c0d014581
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610089"
---
# <a name="select-the-source-cube-dimension-data-mining-wizard"></a><span data-ttu-id="ab97d-102">Quellcubedimension auswählen (Data Mining-Assistent)</span><span class="sxs-lookup"><span data-stu-id="ab97d-102">Select the Source Cube Dimension (Data Mining Wizard)</span></span>
  <span data-ttu-id="ab97d-103">Mithilfe der Seite **Quellcubedimension auswählen** wählen Sie die Dimension des Cubes aus, die die zu analysierenden Fälle enthält.</span><span class="sxs-lookup"><span data-stu-id="ab97d-103">Use the **Select the Source Cube Dimension** page to select the dimension from the cube that contains the cases you want to analyze.</span></span> <span data-ttu-id="ab97d-104">Wenn Sie beispielsweise ein Modell zur Analyse des Kaufverhaltens von Kunden auf der Grundlage von demografischen Daten erstellen, wählen Sie die Customer-Dimension aus, die in der Regel einen eindeutigen Datensatz für jeden Kunden und verschiedene Attribute mit demografischen Daten enthält, wie z. B. Geschlecht, Wohnsitz oder Einkommen.</span><span class="sxs-lookup"><span data-stu-id="ab97d-104">For example, if you are building a model that analyzes the purchasing behavior of customers based on demographics, you would select the Customer dimension, which typically contains a unique record for each customer and various attributes that represent demographics, such as gender, location, or income.</span></span> <span data-ttu-id="ab97d-105">Zu einem späteren Zeitpunkt können Sie im Assistenten eine Tabelle hinzuzufügen, die sich auf diese Falltabelle bezieht. Sie können beispielsweise eine geschachtelte Tabelle hinzufügen, die anzeigt, welche Produkte der Kunde gekauft hat.</span><span class="sxs-lookup"><span data-stu-id="ab97d-105">Later in the wizard you will have the opportunity to add a table that is related to this case table: for example, you might add a nested table that shows which products the customer has purchased.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ab97d-106">Diese Seite wird nur dann angezeigt, wenn Sie auf der Seite **Definitionsmethode auswählen** des Assistenten **Aus vorhandenem Cube ausgewähl**t haben.</span><span class="sxs-lookup"><span data-stu-id="ab97d-106">This page will appear only if you have selected **From existing cube** on the **Select the Definition Method** page of the wizard.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ab97d-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="ab97d-107">Options</span></span>  
 <span data-ttu-id="ab97d-108">**Quellcubedimension auswählen**</span><span class="sxs-lookup"><span data-stu-id="ab97d-108">**Select a Source Cube Dimension**</span></span>  
 <span data-ttu-id="ab97d-109">Wählen Sie die Dimension des Cubes aus, der die Quelldaten für Ihre Miningstruktur bereitstellen wird.</span><span class="sxs-lookup"><span data-stu-id="ab97d-109">Select the dimension of the cube that will provide the source data for your mining structure.</span></span>  
  
## <a name="choosing-a-dimension"></a><span data-ttu-id="ab97d-110">Auswählen einer Dimension</span><span class="sxs-lookup"><span data-stu-id="ab97d-110">Choosing a Dimension</span></span>  
 <span data-ttu-id="ab97d-111">Da Sie nur eine Dimension zur Verwendung in Ihrem Modell auswählen können, ist es wichtig, dass Sie die Struktur des Cubes verstehen und die Dimension auswählen, die die besten Informationen für Ihr Modell bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="ab97d-111">Because you can select only one dimension for use in your model, it is important that you understand the cube structure and select the dimension that provides the best information for your model.</span></span> <span data-ttu-id="ab97d-112">Wenn Sie nicht sicher sind, welche Dimension Sie verwenden sollen, könnte es hilfreich sein, den Cube zu durchsuchen und die Felder und Daten darin mit dem Dimensions-Designer zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="ab97d-112">If you are not sure which dimension to use, it might be helpful to browse the cube and review the fields and the data in them by using Dimension Designer.</span></span> <span data-ttu-id="ab97d-113">Weitere Informationen finden Sie unter [Durchsuchen von Dimensionsdaten im Dimensions-Designer](multidimensional-models/database-dimensions-browse-dimension-data-in-dimension-designer.md).</span><span class="sxs-lookup"><span data-stu-id="ab97d-113">For more information, see [Browse Dimension Data in Dimension Designer](multidimensional-models/database-dimensions-browse-dimension-data-in-dimension-designer.md).</span></span>  
  
 <span data-ttu-id="ab97d-114">Wenn Sie nicht mit Dimensionen vertraut sind, lesen Sie unter [Einführung in Dimensionen &#40;Analysis Services – mehrdimensionale Daten&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) nach.</span><span class="sxs-lookup"><span data-stu-id="ab97d-114">If you are unfamiliar with dimensions in general, see [Introduction to Dimensions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="ab97d-115">Weitere Informationen über den Informationstyp, der in der Regel in einer einzelnen Dimension enthalten ist, einschließlich Attributen und Measures, die möglicherweise für das Data Mining nützlich sind, finden Sie unter [Dimension Relationships](multidimensional-models-olap-logical-cube-objects/dimension-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="ab97d-115">For more information about the type of information that is typically contained in a single dimension, including attributes and measures that might be useful for data mining, see [Dimension Relationships](multidimensional-models-olap-logical-cube-objects/dimension-relationships.md).</span></span>  
  
 <span data-ttu-id="ab97d-116">Wenn die Dimension, die Sie auswählen, nicht alle verknüpften Attribute enthält, die Sie benötigen, um das Data Mining-Modell zu erstellen, müssen Sie möglicherweise die Dimension ändern.</span><span class="sxs-lookup"><span data-stu-id="ab97d-116">If the dimension that you choose does not contain all of the related attributes that you need to build the data mining model, you might need to modify the dimension.</span></span> <span data-ttu-id="ab97d-117">Weitere Informationen finden Sie unter [Definieren von Datenbankdimensionen](multidimensional-models/define-database-dimensions.md).</span><span class="sxs-lookup"><span data-stu-id="ab97d-117">For more information, see [Define Database Dimensions](multidimensional-models/define-database-dimensions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab97d-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ab97d-118">See Also</span></span>  
 <span data-ttu-id="ab97d-119">[Data Mining-Assistent (F1-Hilfe &#40;Analysis Services-Data Mining-&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="ab97d-119">[Data Mining Wizard F1 Help &#40;Analysis Services - Data Mining&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="ab97d-120">[Erstellen Sie die Data Mining-Struktur &#40;Data Mining-Assistenten&#41;](create-the-data-mining-structure-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="ab97d-120">[Create the Data Mining Structure &#40;Data Mining Wizard&#41;](create-the-data-mining-structure-data-mining-wizard.md) </span></span>  
 [<span data-ttu-id="ab97d-121">Wählen Sie den Fall Schlüssel &#40;Data Mining-Assistenten aus&#41;</span><span class="sxs-lookup"><span data-stu-id="ab97d-121">Select the Case Key &#40;Data Mining Wizard&#41;</span></span>](select-the-case-key-data-mining-wizard.md)  
  
  
