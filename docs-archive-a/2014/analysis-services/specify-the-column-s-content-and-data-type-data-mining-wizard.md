---
title: Angeben der Spalten&#39;s-Inhalt und-Datentyp (Data Mining-Assistent) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.dmwizard.specifycontentdatatype.f1
ms.assetid: 7061f674-e806-46f2-8c15-e260a3c69a17
author: minewiskan
ms.author: owend
ms.openlocfilehash: 66af7280e444036468b9cc33a131993524d3586d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620544"
---
# <a name="specify-the-column39s-content-and-data-type-data-mining-wizard"></a><span data-ttu-id="a44bc-102">Angeben der Spalten&#39;s-Inhalt und-Datentyps (Data Mining-Assistent)</span><span class="sxs-lookup"><span data-stu-id="a44bc-102">Specify the Column&#39;s Content and Data Type (Data Mining Wizard)</span></span>
  <span data-ttu-id="a44bc-103">Verwenden Sie die Seite **Inhalt und Datentyp der Spalten angeben** , um den von dem Assistenten bereits festgelegten Spalten- oder Inhaltstyp zu ändern.</span><span class="sxs-lookup"><span data-stu-id="a44bc-103">Use the **Specify the Column's Content and Data Type** page to modify the column and content types that have already been set by the wizard.</span></span> <span data-ttu-id="a44bc-104">Der Assistent verwendet die Datentypen der Quellspalten sowie den ausgewählten Algorithmus, um den Standarddaten- und Inhaltstyp zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="a44bc-104">The wizard uses the data types of the source columns and the capabilities of the selected algorithm to determine the default data and content types for each column.</span></span>  
  
 <span data-ttu-id="a44bc-105">**Weitere Informationen:** [Data Mining-Assistent &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Erstellen einer relationalen Miningstruktur](data-mining/create-a-relational-mining-structure.md)</span><span class="sxs-lookup"><span data-stu-id="a44bc-105">**For More Information:** [Data Mining Wizard &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Create a Relational Mining Structure](data-mining/create-a-relational-mining-structure.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="a44bc-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="a44bc-106">Options</span></span>  
 <span data-ttu-id="a44bc-107">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="a44bc-107">**Columns**</span></span>  
 <span data-ttu-id="a44bc-108">Eine Liste der Spalten, die Sie auf der Seite **Trainingsdaten angeben** des Assistenten definiert haben.</span><span class="sxs-lookup"><span data-stu-id="a44bc-108">A list of the columns that are defined in the **Specify the Training Data** page of the wizard.</span></span>  
  
 <span data-ttu-id="a44bc-109">**Inhaltstyp**</span><span class="sxs-lookup"><span data-stu-id="a44bc-109">**Content Type**</span></span>  
 <span data-ttu-id="a44bc-110">Der Inhaltstyp, der den einzelnen Spalten zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="a44bc-110">The content type that is assigned to each column.</span></span> <span data-ttu-id="a44bc-111">Klicken Sie in eine Zelle, um den Inhaltstyp zu ändern.</span><span class="sxs-lookup"><span data-stu-id="a44bc-111">Click inside a cell to change the content type.</span></span> <span data-ttu-id="a44bc-112">Weitere Informationen zu Inhaltstypen finden Sie unter [Inhaltstypen &#40;Data Mining&#41;](data-mining/content-types-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="a44bc-112">For more information about content types, see [Content Types &#40;Data Mining&#41;](data-mining/content-types-data-mining.md).</span></span>  
  
 <span data-ttu-id="a44bc-113">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="a44bc-113">**Data Type**</span></span>  
 <span data-ttu-id="a44bc-114">Der Datentyp, der den einzelnen Spalten zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="a44bc-114">The data types that are assigned to each column.</span></span> <span data-ttu-id="a44bc-115">Klicken Sie in eine Zelle, um den Datentyp zu ändern.</span><span class="sxs-lookup"><span data-stu-id="a44bc-115">Click inside a cell to change the data type.</span></span> <span data-ttu-id="a44bc-116">Weitere Informationen zu Datentypen finden Sie unter [Datentypen &#40;Data Mining&#41;](data-mining/data-types-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="a44bc-116">For more information about data types, see [Data Types &#40;Data Mining&#41;](data-mining/data-types-data-mining.md).</span></span>  
  
 <span data-ttu-id="a44bc-117">**Detect**</span><span class="sxs-lookup"><span data-stu-id="a44bc-117">**Detect**</span></span>  
 <span data-ttu-id="a44bc-118">Klicken Sie auf diese Option, damit Inhalt vom Typ Kontinuierlich oder Diskret für numerische Spalten automatisch erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="a44bc-118">Click to automatically detect the continuous and discrete content types for numeric column.</span></span> <span data-ttu-id="a44bc-119">Dies ist für Miningstrukturen, denen OLAP-Datenquellen zugrunde liegen, nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a44bc-119">This does not apply to mining structures that are based on OLAP data sources.</span></span> <span data-ttu-id="a44bc-120">Bei OLAP-Miningstrukturen erkennt der Assistent Inhaltstypen automatisch und wählt einen Typ, der mit dem ausgewählten Algorithmus kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="a44bc-120">For OLAP mining structures, the wizard automatically detects content types and chooses a type that is compatible with the selected algorithm.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a44bc-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a44bc-121">See Also</span></span>  
 <span data-ttu-id="a44bc-122">[Der Assistent &#40;Data Mining-Assistenten wird abgeschlossen&#41;](completing-the-wizard-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="a44bc-122">[Completing the Wizard &#40;Data Mining Wizard&#41;](completing-the-wizard-data-mining-wizard.md) </span></span>  
 <span data-ttu-id="a44bc-123">[Data Mining-Assistent (F1-Hilfe &#40;Analysis Services-Data Mining-&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="a44bc-123">[Data Mining Wizard F1 Help &#40;Analysis Services - Data Mining&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="a44bc-124">Geben Sie den Data Mining-Assistenten für Trainingsdaten &#40;an&#41;</span><span class="sxs-lookup"><span data-stu-id="a44bc-124">Specify the Training Data &#40;Data Mining Wizard&#41;</span></span>](specify-the-training-data-data-mining-wizard.md)  
  
  
