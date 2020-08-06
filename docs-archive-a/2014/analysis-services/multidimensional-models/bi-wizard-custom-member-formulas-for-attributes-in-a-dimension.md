---
title: Festlegen benutzerdefinierter Element Formeln für Attribute in einer Dimension | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Business Intelligence enhancements [Analysis Services], custom member formulas
- member formulas [Analysis Services]
- dimensions [Analysis Services], Business Intelligence enhancements
- custom member formulas [Analysis Services]
- CustomRollupColumn property
ms.assetid: c4467b08-ce59-4de7-a2d9-c22e246bdd52
author: minewiskan
ms.author: owend
ms.openlocfilehash: 112f8944bd20b2b6a464b0d84fb8ac1a0e89d976
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615661"
---
# <a name="set-custom-member-formulas-for-attributes-in-a-dimension"></a><span data-ttu-id="e139c-102">Festlegen benutzerdefinierter Elementformeln für Attribute in einer Dimension</span><span class="sxs-lookup"><span data-stu-id="e139c-102">Set Custom Member Formulas for Attributes in a Dimension</span></span>
  <span data-ttu-id="e139c-103">Fügen Sie einem Cube oder einer Dimension eine Erweiterung für benutzerdefinierte Elementformeln hinzu, um die Standardaggregation, die einem Dimensionselement zugeordnet ist, durch die Ergebnisse eines MDX-Ausdrucks (Multidimensional Expressions) zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="e139c-103">Add a custom member formula enhancement to a cube or dimension to replace the default aggregation that is associated with a dimension member with the results of a Multidimensional Expressions (MDX) expression.</span></span> <span data-ttu-id="e139c-104">(Durch diese Erweiterung wird die `CustomRollupColumn`-Eigenschaft für ein angegebenes Attribut in einer Dimension festgelegt.)</span><span class="sxs-lookup"><span data-stu-id="e139c-104">(This enhancement sets the `CustomRollupColumn` property on a specified attribute in a dimension.)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e139c-105">Benutzerdefinierte Formeln stehen nur für Dimensionen zur Verfügung, die auf bestehenden Datenquellen basieren.</span><span class="sxs-lookup"><span data-stu-id="e139c-105">A custom member formula is available only for dimensions that are based on existing data sources.</span></span> <span data-ttu-id="e139c-106">Bei Dimensionen, die ohne Datenquelle erstellt wurden, müssen Sie den Schemagenerierungs-Assistenten ausführen, um eine Datenquellensicht vor dem Hinzufügen einer benutzerdefinierten Elementformel zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e139c-106">For dimensions that were created without using a data source, you must run the Schema Generation Wizard to create a data source view before adding a custom member formula.</span></span>  
  
 <span data-ttu-id="e139c-107">Verwenden Sie zum Hinzufügen einer benutzerdefinierten Elementformel den Business Intelligence-Assistenten, und wählen Sie auf der Seite **Erweiterung auswählen** die Option **Benutzerdefinierte Elementformel erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="e139c-107">To add a custom member formula, you use the Business Intelligence Wizard, and select the **Create a custom member formula** option on the **Choose Enhancement** page.</span></span> <span data-ttu-id="e139c-108">Der Assistent führt Sie durch die Schritte zum Auswählen einer Dimension, auf die eine benutzerdefinierte Elementformel angewendet werden soll, sowie zum Aktivieren der Formel.</span><span class="sxs-lookup"><span data-stu-id="e139c-108">This wizard then guides you through the steps of selecting a dimension to which you want to apply a custom member formula and enabling the custom member formula.</span></span>  
  
## <a name="selecting-a-dimension"></a><span data-ttu-id="e139c-109">Auswählen einer Dimension</span><span class="sxs-lookup"><span data-stu-id="e139c-109">Selecting a Dimension</span></span>  
 <span data-ttu-id="e139c-110">Auf der ersten Seite des Assistenten unter **Benutzerdefinierte Elementformel erstellen** geben Sie die Dimension an, auf die eine benutzerdefinierte Elementformel angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e139c-110">On the first **Create a Custom Member Formula** page of the wizard, you specify the dimension to which you want to apply a custom member formula.</span></span> <span data-ttu-id="e139c-111">Durch Anwenden der benutzerdefinierten Elementformel auf die ausgewählte Dimension werden Änderungen an der Dimension vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="e139c-111">The custom member formula enhancement added to this selected dimension will result in changes to the dimension.</span></span> <span data-ttu-id="e139c-112">Diese Änderungen werden an alle Cubes vererbt, die die ausgewählte Dimension enthalten.</span><span class="sxs-lookup"><span data-stu-id="e139c-112">These changes will be inherited by all cubes that include the selected dimension.</span></span>  
  
## <a name="enabling-a-custom-member-formula"></a><span data-ttu-id="e139c-113">Aktivieren einer benutzerdefinierten Elementformel</span><span class="sxs-lookup"><span data-stu-id="e139c-113">Enabling a Custom Member Formula</span></span>  
 <span data-ttu-id="e139c-114">Auf der zweiten Seite unter **Benutzerdefinierte Elementformel erstellen** ordnen Sie die Quellspalte, die die benutzerdefinierte Elementformel enthält, einem oder mehreren Attributen in der Dimension zu.</span><span class="sxs-lookup"><span data-stu-id="e139c-114">On the second **Create a Custom Member Formula** page, you associate the source column that contains the custom member formula with one or more attributes in the dimension.</span></span> <span data-ttu-id="e139c-115">Aktivieren Sie in der **Attribut** -Spalte das Kontrollkästchen neben dem Attribut, das der Spalte mit der benutzerdefinierten Elementformel zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e139c-115">In the **Attribute** column, select the check box next to the attribute that you want to associate with the custom member formula column.</span></span> <span data-ttu-id="e139c-116">Nach dem Auswählen der einzelnen Attribute zeigt der Assistent das Dialogfeld **Spalte auswählen** an.</span><span class="sxs-lookup"><span data-stu-id="e139c-116">After you select each attribute, the wizard displays the **Select a Column** dialog box.</span></span> <span data-ttu-id="e139c-117">Klicken Sie in diesem Dialogfeld auf die Spalte in der Dimensionstabelle, die die Formel enthält.</span><span class="sxs-lookup"><span data-stu-id="e139c-117">In this dialog box, click the column in the dimension table that contains the formula.</span></span> <span data-ttu-id="e139c-118">Wenn Sie eine Auswahl nach dem Schließen des Dialogfelds **Spalte auswählen** ändern möchten, klicken Sie auf die zu ändernde **Quellspaltenzelle** , und klicken Sie dann auf die Auslassungspunkte (**...**), um das Dialogfeld **Spalte auswählen** erneut zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="e139c-118">If you want to change a selection after you close the **Select a Column** dialog box, click the **Source Column** cell that you want to change, and then click the ellipsis (**...**) to open the **Select a Column** dialog box again.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e139c-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e139c-119">See Also</span></span>  
 [<span data-ttu-id="e139c-120">Verwenden des Business Intelligence-Assistenten zum Erweitern von Dimensionen</span><span class="sxs-lookup"><span data-stu-id="e139c-120">Use the Business Intelligence Wizard to Enhance Dimensions</span></span>](../use-the-business-intelligence-wizard-to-enhance-dimensions.md)  
  
  
