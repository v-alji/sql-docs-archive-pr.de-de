---
title: Hinzufügen einer Tabelle (SSAS-tabellarisch) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d713c432-db99-4983-acc1-52b0fdd58bd6
author: minewiskan
ms.author: owend
ms.openlocfilehash: a80c22c992a89ed2cb3db84809b47a7cd08cb514
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620529"
---
# <a name="add-a-table-ssas-tabular"></a><span data-ttu-id="02fcf-102">Hinzufügen einer Tabelle (SSAS – tabellarisch)</span><span class="sxs-lookup"><span data-stu-id="02fcf-102">Add a Table (SSAS Tabular)</span></span>
  <span data-ttu-id="02fcf-103">In diesem Thema wird beschrieben, wie Sie eine Tabelle aus einer Datenquelle hinzufügen, aus der Sie zuvor Daten in das Modell importiert haben.</span><span class="sxs-lookup"><span data-stu-id="02fcf-103">This topic describes how to add a table from a data source from which you have previously imported data into your model.</span></span> <span data-ttu-id="02fcf-104">Um eine Tabelle aus derselben Datenquelle hinzuzufügen, können Sie die vorhandene Datenquellenverbindung verwenden.</span><span class="sxs-lookup"><span data-stu-id="02fcf-104">To add a table from the same data source, you can use the existing data source connection.</span></span> <span data-ttu-id="02fcf-105">Es wird empfohlen, immer eine einzelne Verbindung zu verwenden, wenn Sie eine beliebige Anzahl von Tabellen aus einer einzelnen Datenquelle importieren.</span><span class="sxs-lookup"><span data-stu-id="02fcf-105">It is recommended you always use a single connection when importing any number of tables from a single data source.</span></span>  
  
### <a name="to-add-a-table-from-an-existing-data-source"></a><span data-ttu-id="02fcf-106">So fügen Sie eine Tabelle aus einer vorhandenen Datenquelle hinzu</span><span class="sxs-lookup"><span data-stu-id="02fcf-106">To add a table from an existing data source</span></span>  
  
1.  <span data-ttu-id="02fcf-107">Klicken Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]im Menü **Modell** auf **Vorhandene Verbindungen**.</span><span class="sxs-lookup"><span data-stu-id="02fcf-107">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click the **Model** menu, and then click **Existing Connections**.</span></span>  
  
2.  <span data-ttu-id="02fcf-108">Wählen Sie auf der Seite **Vorhandene Verbindungen** die Verbindung mit der Datenquelle aus, die über die hinzuzufügende Tabelle verfügt, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="02fcf-108">On the **Existing Connections** page, select the connection to the data source that has the table you want to add, and then click **Open**.</span></span>  
  
3.  <span data-ttu-id="02fcf-109">Wählen Sie auf der Seite **Tabellen und Sichten auswählen** die Tabelle aus der Datenquelle aus, die Sie dem Modell hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="02fcf-109">On the **Select Tables and Views** page, select the table from the data source you want to add to your model.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="02fcf-110">Die Seite **Tabellen und Sichten auswählen** enthält keine Tabellen, die zuvor als überprüft importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="02fcf-110">The **Select Tables and Views** page will not show tables that were previously imported as checked.</span></span>  <span data-ttu-id="02fcf-111">Wenn Sie eine Tabelle auswählen, die zuvor mithilfe dieser Verbindung importiert wurde, und Sie der Tabelle keinen anderen Anzeigenamen gegeben haben, wird eine 1 an den Anzeigenamen angefügt.</span><span class="sxs-lookup"><span data-stu-id="02fcf-111">If you select a table that was previously imported using this connection, and you did not give the table a different friendly name, a 1 will be appended to the friendly name.</span></span> <span data-ttu-id="02fcf-112">Tabellen, die zuvor mithilfe dieser Verbindung importiert wurden, müssen nicht erneut ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="02fcf-112">You do not need to re-select any tables that were previously imported by using this connection.</span></span>  
  
4.  <span data-ttu-id="02fcf-113">Verwenden Sie ggf. **Vorschau und Filter**, um nur bestimmte Spalten auszuwählen bzw. Filter auf die zu importierenden Daten anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="02fcf-113">If necessary, use **Preview & Filter** to select only certain columns or apply filters to the data to be imported.</span></span>  
  
5.  <span data-ttu-id="02fcf-114">Klicken Sie auf **Fertig stellen** , um die neue Tabelle zu importieren.</span><span class="sxs-lookup"><span data-stu-id="02fcf-114">Click **Finish** to import the new table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="02fcf-115">Wenn Sie mehrere Tabellen gleichzeitig aus einer einzelnen Datenquelle importieren, werden im Modell automatisch die Tabellenbeziehungen erstellt, die in der Datenquelle vorhanden waren.</span><span class="sxs-lookup"><span data-stu-id="02fcf-115">When importing multiple tables at the same time from a single data source, any relationships between those tables at the source will automatically be created in the model.</span></span> <span data-ttu-id="02fcf-116">Wenn Sie später eine Tabelle hinzufügen, kann es jedoch erforderlich sein, manuell Beziehungen zwischen den neu hinzugefügten und den zuvor importierten Tabellen im Modell zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="02fcf-116">When adding a table later; however, you may need to manually create relationships in the model between newly added tables and the tables that were previously imported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02fcf-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="02fcf-117">See Also</span></span>  
 <span data-ttu-id="02fcf-118">[Importieren von Daten &#40;tabellarischen SSAS-&#41;](../import-data-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="02fcf-118">[Import Data &#40;SSAS Tabular&#41;](../import-data-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="02fcf-119">Löschen einer Tabelle &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="02fcf-119">Delete a Table &#40;SSAS Tabular&#41;</span></span>](delete-a-table-ssas-tabular.md)  
  
  
