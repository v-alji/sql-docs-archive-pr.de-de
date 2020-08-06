---
title: Löschen einer Spalte (SSAS-tabellarisch) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 703db83b-e554-450e-813e-23ad08c1cdad
author: minewiskan
ms.author: owend
ms.openlocfilehash: 06af0b7fd9879661db95bb2073cced545bb4eef5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618920"
---
# <a name="delete-a-column-ssas-tabular"></a><span data-ttu-id="724bb-102">Löschen einer Spalte (SSAS – tabellarisch)</span><span class="sxs-lookup"><span data-stu-id="724bb-102">Delete a Column (SSAS Tabular)</span></span>
  <span data-ttu-id="724bb-103">In diesem Thema wird beschrieben, wie eine Spalte aus einer Tabelle eines tabellarische Modells gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="724bb-103">This topic describes how to delete a column from a tabular model table.</span></span>  
  
## <a name="delete-a-model-table-column"></a><span data-ttu-id="724bb-104">Löschen von Modelltabellenspalten</span><span class="sxs-lookup"><span data-stu-id="724bb-104">Delete a Model Table Column</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="724bb-105">Wenn Sie eine Spalte aus einer Modelltabelle löschen, wird die Spalte nicht aus einer Partitionsabfragedefinition gelöscht.</span><span class="sxs-lookup"><span data-stu-id="724bb-105">Deleting a column from a model table does not delete the column from a partition query definition.</span></span> <span data-ttu-id="724bb-106">Falls die Spalte, die Sie löschen, Teil einer Partition ist, müssen Sie die Spalte manuell aus der Partitionsabfragedefinition löschen.</span><span class="sxs-lookup"><span data-stu-id="724bb-106">If the column you are deleting is part of a partition, you must manually delete the column from the partition query definition.</span></span> <span data-ttu-id="724bb-107">Wenn Sie die Spalte nicht aus der Partitionsabfragedefinition löschen, wird die Spalte bei Verarbeitungsvorgängen abgefragt und Daten zurückgegeben, aber nicht in der Modelltabelle ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="724bb-107">Failure to delete the column from the partition query definition will cause the column to be queried and data returned, but not populated to the model table, during processing operations.</span></span> <span data-ttu-id="724bb-108">Weitere Informationen finden Sie unter [Partitionen &#40;SSAS – tabellarisch&#41;](partitions-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="724bb-108">For more information, see [Partitions &#40;SSAS Tabular&#41;](partitions-ssas-tabular.md).</span></span>  
  
#### <a name="to-delete-a-model-table-column"></a><span data-ttu-id="724bb-109">So löschen Sie eine Modelltabellenspalte</span><span class="sxs-lookup"><span data-stu-id="724bb-109">To delete a model table column</span></span>  
  
-   <span data-ttu-id="724bb-110">Klicken Sie im Modell-Designer in der Tabelle, die die Spalte enthält, mit der rechten Maustaste auf die Spalte und anschließend auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="724bb-110">In the model designer, in the table that contains the column you want to delete, right-click on the column, and then click **Delete**.</span></span>  
  
#### <a name="to-delete-a-model-table-column-by-using-the-table-properties-dialog-box"></a><span data-ttu-id="724bb-111">So löschen Sie mithilfe des Dialogfelds 'Tabelleneigenschaften' eine Modelltabellenspalte</span><span class="sxs-lookup"><span data-stu-id="724bb-111">To delete a model table column by using the Table Properties dialog box</span></span>  
  
1.  <span data-ttu-id="724bb-112">Klicken Sie im Modell-Designer auf die Tabelle, die die zu löschende Spalte enthält, klicken Sie auf das Menü **Tabelle** und dann auf  **Tabelleneigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="724bb-112">In the model designer, click on the table which contains the column you want to delete, then click the **Table** menu, and then click  **Table Properties**.</span></span>  
  
2.  <span data-ttu-id="724bb-113">Wählen Sie unter **Spaltennamen aus**die Option **Modell** aus,*um Modelltabellen-Spaltennamen zu verwenden, falls diese von der Quelle abweichen*.</span><span class="sxs-lookup"><span data-stu-id="724bb-113">In **Column names from**, select **Model** (*to use model table column names, if different from source*).</span></span>  
  
3.  <span data-ttu-id="724bb-114">Deaktivieren Sie im Dialogfeld **Tabelleneigenschaften bearbeiten** im Tabellenvorschaufenster die Spalte, die Sie löschen möchten, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="724bb-114">In the **Edit Table Properties** dialog box, in the table preview window, uncheck the column you want to delete, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="724bb-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="724bb-115">See Also</span></span>  
 <span data-ttu-id="724bb-116">[Hinzufügen von Spalten zu einer Tabelle &#40;tabellarischen SSAS-&#41;](add-columns-to-a-table-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="724bb-116">[Add Columns to a Table &#40;SSAS Tabular&#41;](add-columns-to-a-table-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="724bb-117">Partitionen &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="724bb-117">Partitions &#40;SSAS Tabular&#41;</span></span>](partitions-ssas-tabular.md)  
  
  
