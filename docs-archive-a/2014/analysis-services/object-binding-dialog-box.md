---
title: Objekt Bindung (Dialog Feld) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql.asvs.dimensiondesigner.dbv.objectbinding.f1
helpviewer_keywords:
- Object Binding dialog box
ms.assetid: 2bb5ad7c-2962-4559-8c95-cf7148bd2e72
author: minewiskan
ms.author: owend
ms.openlocfilehash: a10c91e0222b826066aeede96aa665cc22540637
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619389"
---
# <a name="object-binding-dialog-box"></a><span data-ttu-id="f60c9-102">Objektbindung (Dialogfeld)</span><span class="sxs-lookup"><span data-stu-id="f60c9-102">Object Binding Dialog Box</span></span>
  <span data-ttu-id="f60c9-103">Mithilfe des Dialogfelds **Objektbindung** in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] können Sie Bindungen zwischen der Eigenschaft eines [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Objekts und einer Tabelle oder Spalte in einer Datenquellensicht definieren.</span><span class="sxs-lookup"><span data-stu-id="f60c9-103">Use the **Object Binding** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to define bindings between the property of an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object and a table or column in a data source view.</span></span> <span data-ttu-id="f60c9-104">Sie können das Dialogfeld **Objektbindung** anzeigen, indem Sie im Fenster **Eigenschaften** von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] aus der Dropdownliste den Wert **(Neu)** für folgende Eigenschaften eines [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]-Objekts wählen:</span><span class="sxs-lookup"><span data-stu-id="f60c9-104">You can display the **Object Binding** dialog box by selecting **(new)** from the drop-down list for the value of the following properties of an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object in the **Properties** window of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]:</span></span>  
  
-   <span data-ttu-id="f60c9-105">NameColumn</span><span class="sxs-lookup"><span data-stu-id="f60c9-105">NameColumn</span></span>  
  
-   <span data-ttu-id="f60c9-106">ValueColumn</span><span class="sxs-lookup"><span data-stu-id="f60c9-106">ValueColumn</span></span>  
  
-   <span data-ttu-id="f60c9-107">CustomRollupColumn</span><span class="sxs-lookup"><span data-stu-id="f60c9-107">CustomRollupColumn</span></span>  
  
-   <span data-ttu-id="f60c9-108">CustomRollupPropertiesColumn</span><span class="sxs-lookup"><span data-stu-id="f60c9-108">CustomRollupPropertiesColumn</span></span>  
  
-   <span data-ttu-id="f60c9-109">UnaryOperatorColumn</span><span class="sxs-lookup"><span data-stu-id="f60c9-109">UnaryOperatorColumn</span></span>  
  
## <a name="options"></a><span data-ttu-id="f60c9-110">Tastatur</span><span class="sxs-lookup"><span data-stu-id="f60c9-110">Options</span></span>  
 <span data-ttu-id="f60c9-111">**Bindungstyp**</span><span class="sxs-lookup"><span data-stu-id="f60c9-111">**Binding type**</span></span>  
 <span data-ttu-id="f60c9-112">Wählen Sie die Bindung aus, die für das [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Objekt verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f60c9-112">Select the binding to use for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span> <span data-ttu-id="f60c9-113">Folgende Bindungstypen können verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="f60c9-113">The following types of binding can be used:</span></span>  
  
 <span data-ttu-id="f60c9-114">Spaltenbindung</span><span class="sxs-lookup"><span data-stu-id="f60c9-114">Column binding</span></span>  
 <span data-ttu-id="f60c9-115">Bindet das Objekt innerhalb einer Datenquellensicht an eine vorhandene Tabelle und Spalte.</span><span class="sxs-lookup"><span data-stu-id="f60c9-115">Binds the object to an existing table and column within a data source view.</span></span>  
  
 <span data-ttu-id="f60c9-116">Spalte generieren</span><span class="sxs-lookup"><span data-stu-id="f60c9-116">Generate column</span></span>  
 <span data-ttu-id="f60c9-117">Zeigt an, dass eine neue Spalte in der Datenquellensicht definiert wird, der dann eine Spaltenbindung zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="f60c9-117">Indicates that a new column is to be defined in the data source view, and a column binding is then associated with it.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f60c9-118"> Wenn diese Option ausgewählt ist, müssen Sie **Schemagenerierungs-Assistent** ausführen, bevor Sie das [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Objekt bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f60c9-118">If this option is selected, you must run the **Schema Generation Wizard** before deploying the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span>  
  
 <span data-ttu-id="f60c9-119">Zeilenbindung</span><span class="sxs-lookup"><span data-stu-id="f60c9-119">Row binding</span></span>  
 <span data-ttu-id="f60c9-120">Bindet das Objekt an eine Zeile in einer Faktentabelle und wird verwendet, um die Zählung von Measures anhand der Anzahl der in der Faktentabelle verarbeiteten Zeilen zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="f60c9-120">Binds the object to a row in a fact table and is used to facilitate count measures based on the number of rows processed in the fact table.</span></span>  
  
 <span data-ttu-id="f60c9-121">**Quell Tabelle**</span><span class="sxs-lookup"><span data-stu-id="f60c9-121">**Source table**</span></span>  
 <span data-ttu-id="f60c9-122">Zeigt eine Liste von Tabellen in der Datenquellensicht an, die dem [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Objekt zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="f60c9-122">Displays a list of tables in the data source view associated with the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span>  
  
 <span data-ttu-id="f60c9-123">**Quell Spalte**</span><span class="sxs-lookup"><span data-stu-id="f60c9-123">**Source column**</span></span>  
 <span data-ttu-id="f60c9-124">Zeigt eine Liste von Spalten in der unter **Quelltabelle**ausgewählten Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="f60c9-124">Displays a list of columns in the table selected in **Source table**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f60c9-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f60c9-125">See Also</span></span>  
 [<span data-ttu-id="f60c9-126">Analysis Services Designer und Dialog Felder &#40;Mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="f60c9-126">Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;</span></span>](analysis-services-designers-and-dialog-boxes-multidimensional-data.md)  
  
  
