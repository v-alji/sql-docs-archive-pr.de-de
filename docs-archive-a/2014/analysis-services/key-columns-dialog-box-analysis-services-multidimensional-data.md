---
title: Schlüssel Spalten (Dialog Feld) (Analysis Services-Mehrdimensionale Daten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql.asvs.dimensiondesigner.dbv.dataitemCollection.f1
helpviewer_keywords:
- DataItem Collection dialog box
ms.assetid: 585f27f2-d5eb-4516-b29a-2084010b7d51
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8a72a9e137700ddee822e68901bfde971637d07f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610156"
---
# <a name="key-columns-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="21e45-102">Dialogfeld Schlüsselspalten (Analysis Services – Mehrdimensionale Daten)</span><span class="sxs-lookup"><span data-stu-id="21e45-102">Key Columns Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="21e45-103">Verwenden Sie das Dialogfeld **Schlüsselspalten** , um die **KeyColumns** -Eigenschaft eines Attributs zu ändern.</span><span class="sxs-lookup"><span data-stu-id="21e45-103">Use the **Key Columns** dialog box to change the **KeyColumns** property of an attribute.</span></span> <span data-ttu-id="21e45-104">Weitere Informationen finden Sie unter [Ändern der KeyColumn-Eigenschaft eines Attributs](multidimensional-models/attribute-properties-modify-the-keycolumn-property.md).</span><span class="sxs-lookup"><span data-stu-id="21e45-104">For more information, see [Modify the KeyColumn Property of an Attribute](multidimensional-models/attribute-properties-modify-the-keycolumn-property.md).</span></span>  
  
 <span data-ttu-id="21e45-105">**So zeigen Sie das Dialogfeld Schlüsselspalten an**</span><span class="sxs-lookup"><span data-stu-id="21e45-105">**To display the Key Columns dialog box**</span></span>  
  
-   <span data-ttu-id="21e45-106">Wählen Sie in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]ein Attribut aus, und klicken Sie dann im Fenster **Eigenschaften** in der**KeyColumns**-Eigenschaftszelle auf die Schaltfläche mit den drei Punkten ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="21e45-106">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] or [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], select an attribute, and in the **Properties** window, click the ellipsis button (**...**) associated with the **KeyColumns** property of that attribute.</span></span>  
  
## <a name="options"></a><span data-ttu-id="21e45-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="21e45-107">Options</span></span>  
 <span data-ttu-id="21e45-108">**Quell Tabelle**</span><span class="sxs-lookup"><span data-stu-id="21e45-108">**Source table**</span></span>  
 <span data-ttu-id="21e45-109">Wählen Sie die Quelltabelle aus, für die Sie die Schlüsselspalten auswählen möchten.</span><span class="sxs-lookup"><span data-stu-id="21e45-109">Select the source table for which you want to select its key columns.</span></span> <span data-ttu-id="21e45-110">Sie können die Quelltabelle in der Datenquellensicht in einer Liste aller Tabellen auswählen.</span><span class="sxs-lookup"><span data-stu-id="21e45-110">You can select the source table from a list of all tables in the Data Source View.</span></span>  
  
 <span data-ttu-id="21e45-111">**Verfügbare Spalten**</span><span class="sxs-lookup"><span data-stu-id="21e45-111">**Available Columns**</span></span>  
 <span data-ttu-id="21e45-112">Wählen Sie die Spalten aus, die Sie als Schlüsselspalten verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="21e45-112">Select the columns that you want to use as key columns.</span></span> <span data-ttu-id="21e45-113">Sie können die Spalten in einer Liste auswählen, die alle Spalten der angegebenen **Quelltabelle** enthält, die noch nicht als Schlüsselspalten ausgewählt wurden.</span><span class="sxs-lookup"><span data-stu-id="21e45-113">You can select the columns from a list of columns in the specified **Source table** that have not yet been selected as key columns.</span></span>  
  
 <span data-ttu-id="21e45-114">Sie fügen die ausgewählten Spalten der Liste **Schlüsselspalten** hinzu, indem Sie auf die Schaltfläche **>** klicken.</span><span class="sxs-lookup"><span data-stu-id="21e45-114">To add the selected columns to the **Key Columns** list, click the **>** button.</span></span>  
  
 <span data-ttu-id="21e45-115">**Schlüsselspalten**</span><span class="sxs-lookup"><span data-stu-id="21e45-115">**Key Columns**</span></span>  
 <span data-ttu-id="21e45-116">Definieren Sie die Reihenfolge der ausgewählten Schlüsselspalten.</span><span class="sxs-lookup"><span data-stu-id="21e45-116">Define the order of the selected key columns.</span></span> <span data-ttu-id="21e45-117">Die Reihenfolge der Schlüsselspalten ist wichtig für die Definition des richtigen zusammengesetzten Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="21e45-117">The order of the key columns is important in defining the correct composite key.</span></span> <span data-ttu-id="21e45-118">Um die Reihenfolge von Schlüsselspalten zu ändern, wählen Sie eine Spalte aus und klicken dann auf die Schaltfläche **Nach oben** oder **Nach unten** .</span><span class="sxs-lookup"><span data-stu-id="21e45-118">To order or reorder the list of key columns, select a column, and then click the **Up** or **Down** buttons.</span></span>  
  
 <span data-ttu-id="21e45-119">Um eine Spalte aus der Liste **Schlüsselspalten** zu entfernen, wählen Sie die Spalte aus, und klicken Sie anschließend auf die Schaltfläche **\<** klicken.</span><span class="sxs-lookup"><span data-stu-id="21e45-119">To remove a column from the **Key Columns** list, select the column and click the **\<** button.</span></span>  
  
 <span data-ttu-id="21e45-120">**Nach oben**</span><span class="sxs-lookup"><span data-stu-id="21e45-120">**Up**</span></span>  
 <span data-ttu-id="21e45-121">Klicken Sie auf diese Schaltfläche, um die in der Liste **Schlüsselspalten** ausgewählte Spalte um eine Position nach oben zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="21e45-121">Click to move the column selected in **Key Columns** up one position.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="21e45-122">Diese Option ist nur dann aktiviert, wenn die Liste mehrere Spalten umfasst und eine Spalte ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="21e45-122">This option is enabled only if the list contains more than one column and a column is selected.</span></span>  
  
 <span data-ttu-id="21e45-123">**Nach unten**</span><span class="sxs-lookup"><span data-stu-id="21e45-123">**Down**</span></span>  
 <span data-ttu-id="21e45-124">Klicken Sie auf diese Schaltfläche, um die in der Liste **Schlüsselspalten** ausgewählte Spalte um eine Position nach unten zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="21e45-124">Click to move the column selected in **Key Columns** down one position.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="21e45-125">Diese Option ist nur dann aktiviert, wenn die Liste mehrere Spalten umfasst und eine Spalte ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="21e45-125">This option is enabled only if the list contains more than one column and a column is selected.</span></span>  
  
 **>**  
 <span data-ttu-id="21e45-126">Klicken Sie auf diese Option, um am Ende der Liste **Schlüsselspalten**eine neue Spalte hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="21e45-126">Click to add a new column to the end of the columns listed in **Key Columns**.</span></span>  
  
 **<**  
 <span data-ttu-id="21e45-127">Klicken Sie auf diese Schaltfläche, um die ausgewählte Spalte aus den in der Liste **Schlüsselspalten**aufgeführten Spalten zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="21e45-127">Click to remove the selected column from the columns listed in **Key Columns**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21e45-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="21e45-128">See Also</span></span>  
 [<span data-ttu-id="21e45-129">Analysis Services Designer und Dialog Felder &#40;Mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="21e45-129">Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;</span></span>](analysis-services-designers-and-dialog-boxes-multidimensional-data.md)  
  
  
