---
title: Löschen einer Tabelle (SSAS-tabellarisch) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: be4ed45f-fde3-466c-9869-49bd3ddb505e
author: minewiskan
ms.author: owend
ms.openlocfilehash: c72fa90426440c1be84318a15cf0d761ef16aca8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620516"
---
# <a name="delete-a-table-ssas-tabular"></a><span data-ttu-id="26d1b-102">Löschen einer Tabelle (SSAS – tabellarisch)</span><span class="sxs-lookup"><span data-stu-id="26d1b-102">Delete a Table (SSAS Tabular)</span></span>
  <span data-ttu-id="26d1b-103">Im Modell-Designer können Sie Tabellen in der Arbeitsbereichsdatenbank des Modells löschen, die Sie nicht mehr benötigen.</span><span class="sxs-lookup"><span data-stu-id="26d1b-103">In the model designer, you can delete tables in your model workspace database that you no longer need.</span></span> <span data-ttu-id="26d1b-104">Das Löschen einer Tabelle wirkt sich nicht auf die ursprünglichen Quelldaten aus, sondern nur auf die importierten Daten, mit denen Sie gearbeitet haben.</span><span class="sxs-lookup"><span data-stu-id="26d1b-104">Deleting a table does not affect the original source data, only the data that you imported and were working with.</span></span> <span data-ttu-id="26d1b-105">Das Löschen einer Tabelle kann nicht rückgängig gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="26d1b-105">You cannot undo the deletion of a table.</span></span>  
  
### <a name="to-delete-a-table"></a><span data-ttu-id="26d1b-106">So löschen Sie eine Tabelle</span><span class="sxs-lookup"><span data-stu-id="26d1b-106">To delete a table</span></span>  
  
-   <span data-ttu-id="26d1b-107">Klicken Sie unten im Modell-Designer mit der rechten Maustaste auf die Registerkarte der Tabelle, die gelöscht werden soll, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="26d1b-107">Right-click the tab at the bottom of the model designer for the table that you want to delete, and then click **Delete**.</span></span>  
  
## <a name="considerations-when-deleting-tables"></a><span data-ttu-id="26d1b-108">Überlegungen beim Löschen von Tabellen</span><span class="sxs-lookup"><span data-stu-id="26d1b-108">Considerations when Deleting Tables</span></span>  
  
-   <span data-ttu-id="26d1b-109">Wenn Sie eine Tabelle löschen, wird die gesamte Registerkarte gelöscht, auf der sich die Tabelle befand.</span><span class="sxs-lookup"><span data-stu-id="26d1b-109">When you delete a table, the entire tab that the table was on is deleted.</span></span>  
  
-   <span data-ttu-id="26d1b-110">Wenn dieser Tabelle Measures zugeordnet waren, wird die Definition des Measures ebenfalls gelöscht.</span><span class="sxs-lookup"><span data-stu-id="26d1b-110">If any measures were associated with that table, the definition of the measure will also be deleted.</span></span>  
  
-   <span data-ttu-id="26d1b-111">Wenn Sie mithilfe dieser Tabelle berechnete Spalten erstellt haben, werden auch die Spalten in dieser Tabelle gelöscht. Berechnete Spalten in anderen Tabellen, die Spalten aus der gelöschten Tabelle verwenden, verursachen einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="26d1b-111">If you created any calculated columns using that table, columns in that table are also deleted; any calculated columns in other tables that use columns from the deleted table will display an error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26d1b-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="26d1b-112">See Also</span></span>  
 [<span data-ttu-id="26d1b-113">Tabellen und Spalten &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="26d1b-113">Tables and Columns &#40;SSAS Tabular&#41;</span></span>](tables-and-columns-ssas-tabular.md)  
  
  
