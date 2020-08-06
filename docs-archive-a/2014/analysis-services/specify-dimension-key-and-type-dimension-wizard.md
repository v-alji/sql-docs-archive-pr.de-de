---
title: Dimensions Schlüssel und-Typ angeben (Dimensions-Assistent) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensionwizard.dimensionkeyandtype.f1
ms.assetid: d7d5db55-36c3-45f6-ade3-29aa516589c1
author: minewiskan
ms.author: owend
ms.openlocfilehash: cc08584ed12de8597b8289fd223cc47945d7d087
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620563"
---
# <a name="specify-dimension-key-and-type-dimension-wizard"></a><span data-ttu-id="04807-102">Dimensionsschlüssel und -typ angeben (Dimensions-Assistent)</span><span class="sxs-lookup"><span data-stu-id="04807-102">Specify Dimension Key and Type (Dimension Wizard)</span></span>
  <span data-ttu-id="04807-103">Auf der Seite **Dimensionsschlüssel und -typ angeben** können Sie das Schlüsselattribut der Dimension definieren und kennzeichnen, ob es sich um eine langsam veränderliche Dimension (Slowly Changing Dimension, SCD) handelt.</span><span class="sxs-lookup"><span data-stu-id="04807-103">Use the **Specify Dimension Key and Type** page to define the key attribute of the dimension and to indicate whether the dimension is a slowly changing dimension (SCD).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="04807-104"> Diese Seite wird nur angezeigt, wenn Sie auf der Seite **Erstellungsmethode auswählen** die Option **Dimension ohne eine Datenquelle erstellen** und auf der Seite **Dimensionstyp auswählen** die Option **Standarddimension** ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="04807-104">This page is displayed only if you selected **Build the dimension without using a data source** on the **Select Build Method** page and if you selected **Standard dimension** on the **Select the Dimension Type** page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="04807-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="04807-105">Options</span></span>  
 <span data-ttu-id="04807-106">**Schlüsselattribut**</span><span class="sxs-lookup"><span data-stu-id="04807-106">**Key attribute**</span></span>  
 <span data-ttu-id="04807-107">Wählen Sie das Attribut aus, das als Schlüsselattribut der Dimension dienen soll.</span><span class="sxs-lookup"><span data-stu-id="04807-107">Select the attribute that will be the key attribute for the dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="04807-108">Wenn für die Dimension keine Attribute definiert wurden, ist für diese Option lediglich der Wert **Erstellen Sie das Schlüsselattribut automatisch**</span><span class="sxs-lookup"><span data-stu-id="04807-108">If no attributes have been defined for the dimension, the only value available for this option is **Create key attribute automatically.**</span></span> <span data-ttu-id="04807-109">verfügbar. Sobald für die Dimension Attribute definiert sind, ist dieser Wert nicht mehr verfügbar.</span><span class="sxs-lookup"><span data-stu-id="04807-109">This value is not available if any attributes are defined for the dimension.</span></span>  
  
 <span data-ttu-id="04807-110">**Dies ist eine veränderliche Dimension**</span><span class="sxs-lookup"><span data-stu-id="04807-110">**This is a changing dimension**</span></span>  
 <span data-ttu-id="04807-111">Wählen Sie diese Option aus, um zu kennzeichnen, dass es sich bei der Dimension um eine langsam veränderliche Dimension handelt.</span><span class="sxs-lookup"><span data-stu-id="04807-111">Select to indicate that the dimension is a slowly changing dimension.</span></span> <span data-ttu-id="04807-112">Wenn Sie diese Option auswählen, werden zusätzliche Spalten und Attribute erstellt, die verwendet werden können, um die Bewegungen der Elemente in den Hierarchien der Dimension im Verlauf der Zeit nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="04807-112">Selecting this option will create additional columns and attributes that can be used to track the movement of members within the hierarchies of the dimension over time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04807-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="04807-113">See Also</span></span>  
 <span data-ttu-id="04807-114">[Dimensions-Assistent F1-Hilfe](dimension-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="04807-114">[Dimension Wizard F1 Help](dimension-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="04807-115">[Dimensionen &#40;Analysis Services Mehrdimensionale Daten&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="04807-115">[Dimensions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="04807-116">Dimensionen in mehrdimensionalen Modellen</span><span class="sxs-lookup"><span data-stu-id="04807-116">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
