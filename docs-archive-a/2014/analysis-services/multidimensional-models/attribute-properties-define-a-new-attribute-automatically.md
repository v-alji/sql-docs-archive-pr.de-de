---
title: Automatisches Definieren eines neuen Attributs | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- automatic attribute creation
- attributes [Analysis Services], creating
ms.assetid: 208a050a-5e2f-470c-b645-8d835e123db7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 40f9ae1f00dd0a6520c6d1b06111864fba02e8f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725129"
---
# <a name="define-a-new-attribute-automatically"></a><span data-ttu-id="50e7b-102">Automatisches Definieren eines neuen Attributs</span><span class="sxs-lookup"><span data-stu-id="50e7b-102">Define a New Attribute Automatically</span></span>
  <span data-ttu-id="50e7b-103">Sie können ein neues Attribut in einer Dimension erstellen, indem Sie die Drag & Drop-Bearbeitung im Dimensions-Designer verwenden.</span><span class="sxs-lookup"><span data-stu-id="50e7b-103">You can create a new attribute in a dimension by using drag-and-drop editing in the Dimension Designer.</span></span>  
  
### <a name="to-create-a-new-attribute-automatically"></a><span data-ttu-id="50e7b-104">So erstellen Sie automatisch ein neues Attribut</span><span class="sxs-lookup"><span data-stu-id="50e7b-104">To create a new attribute automatically</span></span>  
  
1.  <span data-ttu-id="50e7b-105">Öffnen Sie im Dimensions-Designer die Dimension, in der Sie das Attribut erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="50e7b-105">In Dimension Designer, open the dimension in which you want to create the attribute.</span></span>  
  
2.  <span data-ttu-id="50e7b-106">Wählen Sie auf der Registerkarte **Dimensionsstruktur** im Bereich **Datenquellensicht** die Spalte aus der Tabelle aus, an die Sie das Attribut binden möchten, und ziehen Sie dann die Spalte in den Bereich **Attribute** .</span><span class="sxs-lookup"><span data-stu-id="50e7b-106">On the **Dimension Structure** tab, in the **Data Source View** pane, in the table to which you want to bind the attribute, select the column, and then drag the column to the **Attributes** pane.</span></span>  
  
     [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="50e7b-107">erstellt das neue Attribut mit demselben Namen wie die Spalte, an die es gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="50e7b-107">creates the new attribute that has the same name as the column to which it is bound.</span></span> <span data-ttu-id="50e7b-108">Wird die Spalte von mehreren Attributen verwendet, fügt [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] eine Nummer an den Attributnamen an.</span><span class="sxs-lookup"><span data-stu-id="50e7b-108">If there are multiple attributes that use the same column, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] appends a number to the attribute name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50e7b-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="50e7b-109">See Also</span></span>  
 <span data-ttu-id="50e7b-110">[Dimensionen in mehrdimensionalen Modellen](dimensions-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="50e7b-110">[Dimensions in Multidimensional Models](dimensions-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="50e7b-111">Dimensionsattributeigenschaftenverweis</span><span class="sxs-lookup"><span data-stu-id="50e7b-111">Dimension Attribute Properties Reference</span></span>](dimension-attribute-properties-reference.md)  
  
  
