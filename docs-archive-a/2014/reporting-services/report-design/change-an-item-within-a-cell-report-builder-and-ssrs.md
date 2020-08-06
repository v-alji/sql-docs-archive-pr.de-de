---
title: Ändern eines Elements in einer Zelle (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 91a54778-8929-41f9-bb4c-826cec636be4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 80ef171713e6505867e00e343ce17b70cab9045a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726517"
---
# <a name="change-an-item-within-a-cell-report-builder-and-ssrs"></a><span data-ttu-id="1f25d-102">Ändern eines Elements in einer Zelle (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="1f25d-102">Change an Item Within a Cell (Report Builder and SSRS)</span></span>
  <span data-ttu-id="1f25d-103">Nur ein Nichtcontainerelement, z. B. ein Textfeld, eine Zeile oder ein Bild, kann durch ein neues Berichtselement ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="1f25d-103">Only a non-container item, such as a text box, line, or image, can be replaced by a new report item.</span></span> <span data-ttu-id="1f25d-104">Sie können beispielsweise eine Tabelle in ein Textfeld ziehen, um das Textfeld durch eine Tabelle zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="1f25d-104">For example, you can drag a table into a text box to replace the text box with a table.</span></span>  
  
 <span data-ttu-id="1f25d-105">Enthält die Zelle ein Containerelement, wie z. B. ein Rechteck, eine Liste, eine Tabelle oder eine Matrix, wird das neue Element zum enthaltenen Element hinzugefügt, anstatt es zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="1f25d-105">If the cell contains a container item such as a rectangle, list, table, or matrix, the new item is added to the containing item instead of replacing it.</span></span> <span data-ttu-id="1f25d-106">Um ein Containerelement durch ein neues Element zu ersetzen, löschen Sie den Container.</span><span class="sxs-lookup"><span data-stu-id="1f25d-106">To replace a container item with a new item, delete the container.</span></span> <span data-ttu-id="1f25d-107">Beim Löschen des Containerelements wird dafür ein Textfeld eingefügt, das Sie durch ein anderes Element ersetzen können.</span><span class="sxs-lookup"><span data-stu-id="1f25d-107">Deleting the container item replaces it with a text box, which you can then replace with another item.</span></span>  
  
 <span data-ttu-id="1f25d-108">Standardmäßig enthalten alle Zellen in einem Tabellen-, Matrix- oder Listendatenbereich ein Textfeld.</span><span class="sxs-lookup"><span data-stu-id="1f25d-108">By default, all cells in a table, matrix, or list data region contain a text box.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-an-item-within-a-cell"></a><span data-ttu-id="1f25d-109">So ändern Sie ein Element in einer Zelle</span><span class="sxs-lookup"><span data-stu-id="1f25d-109">To change an item within a cell</span></span>  
  
-   <span data-ttu-id="1f25d-110">Klicken Sie auf der Registerkarte **Einfügen** in der Gruppe **Datenbereiche** oder **Berichtselemente** auf das Element, das Sie dem Bericht hinzufügen möchten, und klicken Sie dann auf den Bericht.</span><span class="sxs-lookup"><span data-stu-id="1f25d-110">On the **Insert** tab, in the **Data Regions** or **Report Items** group, click the item that you want to add to the report, and then click the report.</span></span> <span data-ttu-id="1f25d-111">Das Element wird dem Bericht hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1f25d-111">The item is added to the report.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1f25d-112">Das Dialogfeld **Bildeigenschaften** wird geöffnet, wenn Sie ein Bildberichtselement in eine Zelle ziehen, in der Sie Eigenschaften wie die Quelle des Bilds festlegen können, bevor das Bild der Zelle hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="1f25d-112">The **Image Properties** dialog box opens when you drag an image report item to a cell, where you can set properties such as the source of the image before the image is added to the cell.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f25d-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1f25d-113">See Also</span></span>  
 <span data-ttu-id="1f25d-114">[Bilder, Textfelder, Rechtecke und Linien &#40;Berichts-Generator und SSRS&#41;](rectangles-and-lines-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1f25d-114">[Images, Text Boxes, Rectangles, and Lines &#40;Report Builder and SSRS&#41;](rectangles-and-lines-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="1f25d-115">Listen (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="1f25d-115">Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
