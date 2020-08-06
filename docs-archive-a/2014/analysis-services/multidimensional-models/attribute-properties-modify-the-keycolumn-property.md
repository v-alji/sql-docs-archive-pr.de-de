---
title: Ändern der KeyColumn-Eigenschaft eines Attributs | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- binding attributes [Analysis Services]
- attributes [Analysis Services], binding
- key columns [Analysis Services]
ms.assetid: a2643be4-8123-4cc3-baf9-e5ec54a1669d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3367a7aec84ba59efd118a56745bb76fc5266061
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725113"
---
# <a name="modify-the-keycolumn-property-of-an-attribute"></a><span data-ttu-id="12f42-102">Ändern der KeyColumns-Eigenschaft eines Attributs</span><span class="sxs-lookup"><span data-stu-id="12f42-102">Modify the KeyColumn Property of an Attribute</span></span>
  <span data-ttu-id="12f42-103">Sie können die **KeyColumns** -Eigenschaft eines Attributs ändern.</span><span class="sxs-lookup"><span data-stu-id="12f42-103">You can modify the **KeyColumns** property of an attribute.</span></span> <span data-ttu-id="12f42-104">Nehmen wir beispielsweise an, Sie möchten einen zusammengesetzten Schlüssel statt eines einzelnen Schlüssels für das Attribut verwenden.</span><span class="sxs-lookup"><span data-stu-id="12f42-104">For example, you might want to specify a composite key instead of a single key as the key for the attribute.</span></span>  
  
### <a name="to-modify-the-keycolumns-property-of-an-attribute"></a><span data-ttu-id="12f42-105">So ändern Sie die KeyColumns-Eigenschaft eines Attributs</span><span class="sxs-lookup"><span data-stu-id="12f42-105">To modify the KeyColumns property of an attribute</span></span>  
  
1.  <span data-ttu-id="12f42-106">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]das Projekt, in dem Sie die **KeyColumns** -Eigenschaft ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="12f42-106">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project in which you want to modify the **KeyColumns** property.</span></span>  
  
2.  <span data-ttu-id="12f42-107">Öffnen Sie den Dimensions-Designer, indem Sie eine der folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="12f42-107">Open Dimension Designer by doing one of the following procedures:</span></span>  
  
    -   <span data-ttu-id="12f42-108">Klicken Sie im **Projektmappen-Explorer**im Ordner **Dimensionen** mit der rechten Maustaste auf die Dimension, und klicken Sie anschließend entweder auf **Öffnen** oder **Sicht-Designer**.</span><span class="sxs-lookup"><span data-stu-id="12f42-108">In **Solution Explorer**, right-click the dimension in the **Dimensions** folder, and then either click **Open** or **View Designer**.</span></span>  
  
         <span data-ttu-id="12f42-109">Oder</span><span class="sxs-lookup"><span data-stu-id="12f42-109">-or-</span></span>  
  
    -   <span data-ttu-id="12f42-110">Erweitern Sie im Cube-Designer auf der Registerkarte **Cubestruktur** die Cubedimension im Bereich **Dimensionen** , und klicken Sie auf \*\*Bearbeiten \<dimension> \*\*.</span><span class="sxs-lookup"><span data-stu-id="12f42-110">In Cube Designer, on the **Cube Structure** tab, expand the cube dimension in the **Dimensions** pane and click **Edit \<dimension>**.</span></span>  
  
3.  <span data-ttu-id="12f42-111">Klicken Sie im Bereich **Attribute** der Registerkarte **Dimensionsstruktur** auf das Attribut, dessen **KeyColumns** -Eigenschaft Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="12f42-111">On the **Dimension Structure** tab, in the **Attributes** pane, click the attribute whose **KeyColumns** property you want to modify.</span></span>  
  
4.  <span data-ttu-id="12f42-112">Klicken Sie im Fenster **Eigenschaften** auf den Wert für die **KeyColumns** -Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="12f42-112">In the **Properties** window, click the value for the **KeyColumns** property.</span></span>  
  
5.  <span data-ttu-id="12f42-113">Klicken Sie auf die Schaltfläche zum Durchsuchen **(...)** , die in der Wertzelle des Eigenschaftenfelds angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="12f42-113">Click the browse **(...)** button that appears in the value cell of the property box.</span></span>  
  
     <span data-ttu-id="12f42-114">Das Dialogfeld **Schlüsselspalten** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="12f42-114">The **Key Columns** dialog box opens.</span></span>  
  
6.  <span data-ttu-id="12f42-115">Um eine vorhandene Schlüsselspalte zu entfernen, wählen Sie die Spalte in der Liste **Schlüsselspalten** aus, und klicken Sie anschließend auf die Schaltfläche **\<** .</span><span class="sxs-lookup"><span data-stu-id="12f42-115">To remove an existing key column, in the **Key Columns** list, select the column, and then click the **\<** button.</span></span>  
  
7.  <span data-ttu-id="12f42-116">Um eine Schlüsselspalte hinzuzufügen, wählen Sie die Spalte in der Liste **Verfügbare Spalten** aus, und klicken Sie anschließend auf die Schaltfläche **>** .</span><span class="sxs-lookup"><span data-stu-id="12f42-116">To add a key column, in the **Available Columns** list, select the column, and then click the **>** button.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="12f42-117">Wenn Sie mehrere Schlüsselspalten definieren, bestimmt die Reihenfolge, in der diese Spalten in der Liste **Schlüsselspalten** aufgeführt sind, die Anzeigereihenfolge.</span><span class="sxs-lookup"><span data-stu-id="12f42-117">If you define multiple key columns, the order in which those columns appear in the **Key Columns** list affects the display order.</span></span> <span data-ttu-id="12f42-118">Beispielsweise verfügt ein <localizedText>Month</localizedText>-Attribut über zwei Schlüsselspalten: <localizedText>Month</localizedText> und <localizedText>Year</localizedText>.</span><span class="sxs-lookup"><span data-stu-id="12f42-118">For example, a month attribute has two key columns: month and year.</span></span> <span data-ttu-id="12f42-119">Wenn die &lt;localizedText&gt;Year&lt;/localizedText&gt;-Spalte in der Liste vor der &lt;localizedText&gt;Month&lt;/localizedText&gt;-Spalte steht, sortiert [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] zuerst nach Jahr und dann nach Monat.</span><span class="sxs-lookup"><span data-stu-id="12f42-119">If the year column appears in the list before the month column, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will sort by year and then by month.</span></span> <span data-ttu-id="12f42-120">Wenn die &lt;localizedText&gt;Month&lt;/localizedText&gt;-Spalte vor der &lt;localizedText&gt;Year&lt;/localizedText&gt;-Spalte steht, sortiert [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] zuerst nach Monat und dann nach Jahr.</span><span class="sxs-lookup"><span data-stu-id="12f42-120">If the month column appears before the year column, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will sort by month and then by year.</span></span>  
  
8.  <span data-ttu-id="12f42-121">Um die Reihenfolge von Schlüsselspalten zu ändern, wählen Sie eine Spalte aus und klicken dann auf die Schaltfläche **Nach oben** oder **Nach unten** .</span><span class="sxs-lookup"><span data-stu-id="12f42-121">To change the order of key columns, select a column, and then click the **Up** or **Down** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12f42-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="12f42-122">See Also</span></span>  
 [<span data-ttu-id="12f42-123">Dimensionsattributeigenschaftenverweis</span><span class="sxs-lookup"><span data-stu-id="12f42-123">Dimension Attribute Properties Reference</span></span>](dimension-attribute-properties-reference.md)  
  
  
