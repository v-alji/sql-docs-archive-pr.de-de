---
title: Vorlage zur Ebenenbenennung (Dialog Feld) (Analysis Services Mehrdimensionale Daten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.levelnamingtemplatedialog.f1
helpviewer_keywords:
- Level Naming Template dialog box
ms.assetid: 96cad715-213e-4eac-9003-130a2f5fc985
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4dd704e619e49f0dd1adb8fed8f1e743b61309af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727254"
---
# <a name="level-naming-template-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="29f34-102">Dialogfeld 'Vorlage zur Ebenenbenennung' (Analysis Services – Mehrdimensionale Daten)</span><span class="sxs-lookup"><span data-stu-id="29f34-102">Level Naming Template Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="29f34-103">Mithilfe des Dialogfelds **Vorlage zur Ebenenbenennung** in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] können Sie eine Vorlage zur Ebenenbenennung für ein übergeordnetes Attribut in einer Dimension erstellen.</span><span class="sxs-lookup"><span data-stu-id="29f34-103">Use the **Level Naming Template** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to construct the level naming template for a parent attribute in a dimension.</span></span> <span data-ttu-id="29f34-104">Weitere Informationen über Vorlagen zur Ebenenbenennung finden Sie unter [NamingTemplate Element &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/properties/namingtemplate-element-assl).</span><span class="sxs-lookup"><span data-stu-id="29f34-104">For more information about level naming templates, see [NamingTemplate Element &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/properties/namingtemplate-element-assl).</span></span> <span data-ttu-id="29f34-105">Sie können das Dialogfeld **Vorlage zur Ebenenbenennung** anzeigen, indem Sie im Dimensions-Designer auf der Registerkarte Übersetzungen im Bereich Übersetzungs Details auf die Schaltfläche mit den Auslassungs Punkten (**...**) klicken. `NamingTemplate` **Translation Details** **Translations** **Dimension Designer**</span><span class="sxs-lookup"><span data-stu-id="29f34-105">You can display the **Level Naming Template** dialog box by clicking the ellipsis button (**...**) on the `NamingTemplate` value of a translation for an attribute in the **Translation Details** pane on the **Translations** tab of **Dimension Designer**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="29f34-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="29f34-106">Options</span></span>  
  
|<span data-ttu-id="29f34-107">Begriff</span><span class="sxs-lookup"><span data-stu-id="29f34-107">Term</span></span>|<span data-ttu-id="29f34-108">Definition</span><span class="sxs-lookup"><span data-stu-id="29f34-108">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="29f34-109">**Ebenenvorlage definieren**</span><span class="sxs-lookup"><span data-stu-id="29f34-109">**Define the level template**</span></span>|<span data-ttu-id="29f34-110">Zeigt ein Raster an, in dem Sie die Hierarchie der Ebenen in dem übergeordneten Attribut gestalten können.</span><span class="sxs-lookup"><span data-stu-id="29f34-110">Displays a grid in which you can design the hierarchy of levels in the parent attribute.</span></span> <span data-ttu-id="29f34-111">Das Raster enthält die folgenden Spalten:</span><span class="sxs-lookup"><span data-stu-id="29f34-111">The grid contains the following columns:</span></span><br /><br /> <span data-ttu-id="29f34-112">**Level**: zeigt die Ordnungsposition der Ebene an, für die der in **Name** angegebene Name verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="29f34-112">**Level**: Displays the ordinal position of the level for which the name specified in **Name** is used.</span></span> <span data-ttu-id="29f34-113">Wählen Sie die Option **Name** in der Zeile aus, die ein Sternchen (\*) unter **Ebene**enthält, um eine neue Vorlage für die Benennung einer Ebene hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="29f34-113">To add a new naming template for a level, select **Name** on the row that contains an asterisk (\*) in **Level**.</span></span><br /><br /> <span data-ttu-id="29f34-114">**Name**: enthält die Benennungs Vorlage für die Ebene, die unter **Ebene**angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="29f34-114">**Name**: Contains the naming template used for the level indicated in **Level**.</span></span> <span data-ttu-id="29f34-115">Als Platzhalter für die Ordnungsposition der Ebene in der Vorlage zur Benennung fügen Sie ein einzelnes Sternchen (\*) hinzu.</span><span class="sxs-lookup"><span data-stu-id="29f34-115">To add a placeholder for the level ordinal position in the naming template, add a single asterisk (\*).</span></span> <span data-ttu-id="29f34-116">Wenn Sie ein Sternchen als Teil des Namens hinzufügen möchten, der von der Benennungs Vorlage erstellt wurde, fügen Sie zwei Sternchen ( \* \* ) hinzu.</span><span class="sxs-lookup"><span data-stu-id="29f34-116">To add an asterisk as part of the name created by the naming template, add two asterisks (\*\*).</span></span>|  
|<span data-ttu-id="29f34-117">**Alle löschen**</span><span class="sxs-lookup"><span data-stu-id="29f34-117">**Clear All**</span></span>|<span data-ttu-id="29f34-118">Entfernt alle Zeilen unter **Ebenenvorlage definieren**.</span><span class="sxs-lookup"><span data-stu-id="29f34-118">Select to remove all rows in **Define the level template**.</span></span>|  
|<span data-ttu-id="29f34-119">**Ergebnis**</span><span class="sxs-lookup"><span data-stu-id="29f34-119">**Result**</span></span>|<span data-ttu-id="29f34-120">Zeigt die im Dialogfeld erstellte Vorlage zur Ebenenbenennung an.</span><span class="sxs-lookup"><span data-stu-id="29f34-120">Displays the level naming template constructed by the dialog box.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="29f34-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="29f34-121">See Also</span></span>  
 <span data-ttu-id="29f34-122">[Analysis Services Designer und Dialog Felder &#40;Mehrdimensionale Daten&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="29f34-122">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="29f34-123">Übersetzungen &#40;Dimensions-Designer&#41; &#40;Analysis Services Mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="29f34-123">Translations &#40;Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](translations-dimension-designer-analysis-services-multidimensional-data.md)  
  
  
