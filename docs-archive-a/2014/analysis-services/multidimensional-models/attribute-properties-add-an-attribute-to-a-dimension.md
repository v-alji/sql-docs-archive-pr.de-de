---
title: Hinzufügen eines Attributs zu einer Dimension | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- adding attributes
- automatic attribute creation
- attributes [Analysis Services], creating
- attributes [Analysis Services], adding
- manual attribute creation [Analysis Services]
ms.assetid: 25826ba1-2b38-4b34-bd3a-7eba116093ae
author: minewiskan
ms.author: owend
ms.openlocfilehash: 776591e94deedc679592cfe36d53fb1fea4093d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622255"
---
# <a name="add-an--attribute-to-a-dimension"></a><span data-ttu-id="cff07-102">Hinzufügen eines Attributs zu einer Dimension</span><span class="sxs-lookup"><span data-stu-id="cff07-102">Add an  Attribute to a Dimension</span></span>
  <span data-ttu-id="cff07-103">Sie können ein Attribut entweder automatisch oder manuell in einer Dimension hinzufügen [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cff07-103">You can add an attribute to a dimension either automatically or manually in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="cff07-104">Um ein Attribut automatisch zu erstellen, wählen Sie in **auf der Registerkarte** Dimensionsstruktur [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]des Dimensions-Designers die Spalte aus, die Sie einem Attribut zuordnen möchten, und ziehen Sie diese Spalte dann aus dem Bereich **Datenquellensicht** in den Bereich **Attribute** .</span><span class="sxs-lookup"><span data-stu-id="cff07-104">To create an attribute automatically, on the **Dimension Structure** tab of Dimension Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], select the column that you want to map to an attribute, and then drag that column from the **Data Source View** pane to the **Attributes** pane.</span></span> <span data-ttu-id="cff07-105">Dadurch wird ein Attribut erstellt, das der Spalte zugeordnet ist. Dem Attribut wird derselbe Name zugeordnet wie der Name der Spalte.</span><span class="sxs-lookup"><span data-stu-id="cff07-105">This creates an attribute that is mapped to the column, and assigns the same name to the attribute as the name of the column.</span></span> <span data-ttu-id="cff07-106">Ist bereits ein Attribut mit diesem Namen vorhanden, fügt [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] eine Ordinalzahl als Suffix hinzu, beginnend mit "1" für den ersten doppelten Namen.</span><span class="sxs-lookup"><span data-stu-id="cff07-106">If an attribute that uses that name already exists, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] adds an ordinal number suffix, starting with "1" for the first duplicate name.</span></span>  
  
 <span data-ttu-id="cff07-107">Um ein Attribut manuell zu erstellen, legen Sie für den Bereich **Attribute** die Rasteransicht fest.</span><span class="sxs-lookup"><span data-stu-id="cff07-107">To create an attribute manually, set the **Attributes** pane to grid view.</span></span> <span data-ttu-id="cff07-108">Klicken Sie in der Spalte Name der letzten Zeile im Raster auf das **\<new attribute>** Element.</span><span class="sxs-lookup"><span data-stu-id="cff07-108">In the name column of the last row in the grid, click the **\<new attribute>** item.</span></span> <span data-ttu-id="cff07-109">Geben Sie einen Namen für das neue Attribut ein.</span><span class="sxs-lookup"><span data-stu-id="cff07-109">Type a name for the new attribute.</span></span> <span data-ttu-id="cff07-110">Dadurch wird ein Attribut erstellt, das keiner Spalte zugeordnet ist und für alle Eigenschaften Standardeinstellungen besitzt.</span><span class="sxs-lookup"><span data-stu-id="cff07-110">This creates an attribute that is not mapped to a column and that has default settings for all its properties.</span></span> <span data-ttu-id="cff07-111">Sie können die Zuordnung im Fenster **Eigenschaften** von [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] festlegen, indem Sie die **KeyColumns** -Eigenschaft für das neue Attribut konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="cff07-111">You can set the mapping in the **Properties** window of [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] by configuring the **KeyColumns** property for the new attribute.</span></span>  
  
 <span data-ttu-id="cff07-112">Weitere Informationen finden Sie unter [Automatisches Definieren eines neuen Attributs](attribute-properties-define-a-new-attribute-automatically.md), [Manuelles Definieren eines neuen Attributs](../define-a-new-attribute-manually.md), [Binden eines Attributs an eine Namensspalte](attribute-properties-bind-an-attribute-to-a-name-column.md), und [Ändern der KeyColumns-Eigenschaft eines Attributs](attribute-properties-modify-the-keycolumn-property.md).</span><span class="sxs-lookup"><span data-stu-id="cff07-112">For more information, see [Define a New Attribute Automatically](attribute-properties-define-a-new-attribute-automatically.md), [Define a New Attribute Manually](../define-a-new-attribute-manually.md), [Bind an Attribute to a Name Column](attribute-properties-bind-an-attribute-to-a-name-column.md), and [Modify the KeyColumn Property of an Attribute](attribute-properties-modify-the-keycolumn-property.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cff07-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cff07-113">See Also</span></span>  
 [<span data-ttu-id="cff07-114">Dimensionsattributeigenschaftenverweis</span><span class="sxs-lookup"><span data-stu-id="cff07-114">Dimension Attribute Properties Reference</span></span>](dimension-attribute-properties-reference.md)  
  
  
