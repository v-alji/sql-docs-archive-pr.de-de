---
title: Filtern von Daten in einer Tabelle (SSAS-tabellarisch) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.customfilterdb.f1
- sql12.asvs.bidtoolset.autofiltermenu.f1
- sql12.asvs.bidtoolset.notallitemsshowing.f1
ms.assetid: 3223059d-f525-4835-bf88-ebc195d9dbdc
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3f4003457df4068713e75e6bb5c0ab78c15ac03c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696198"
---
# <a name="filter-data-in-a-table-ssas-tabular"></a><span data-ttu-id="86969-102">Filtern von Daten in einer Tabelle (SSAS – tabellarisch)</span><span class="sxs-lookup"><span data-stu-id="86969-102">Filter Data in a Table (SSAS Tabular)</span></span>
  <span data-ttu-id="86969-103">Sie können beim Importieren von Daten Filter anwenden, um zu steuern, welche Zeilen in eine Tabelle geladen werden.</span><span class="sxs-lookup"><span data-stu-id="86969-103">You can apply filters when you import data to control the rows that are loaded into a table.</span></span> <span data-ttu-id="86969-104">Nachdem Sie die Daten importiert haben, können Sie keine einzelnen Zeilen löschen.</span><span class="sxs-lookup"><span data-stu-id="86969-104">After you have imported the data, you cannot delete individual rows.</span></span> <span data-ttu-id="86969-105">Sie können jedoch benutzerdefinierte Filter anwenden, um zu steuern, wie Zeilen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="86969-105">However, you can apply custom filters to control the way that rows are displayed.</span></span> <span data-ttu-id="86969-106">Zeilen, die die Filterkriterien nicht erfüllen, werden ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="86969-106">Rows that do not meet the filtering criteria are hidden.</span></span> <span data-ttu-id="86969-107">Sie können nach einer oder mehreren Spalten filtern.</span><span class="sxs-lookup"><span data-stu-id="86969-107">You can filter by one or more columns.</span></span> <span data-ttu-id="86969-108">Filter sind additiv. Das bedeutet, dass jeder zusätzliche Filter auf dem aktuellen Filter basiert und die Teilmenge der Daten weiter reduziert.</span><span class="sxs-lookup"><span data-stu-id="86969-108">Filters are additive, which means that each additional filter is based on the current filter and further reduces the subset of data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="86969-109">Das Filtervorschaufenster schränkt die Anzahl der unterschiedlichen Werte ein, die angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="86969-109">The filter preview window limits the number of different values displayed.</span></span> <span data-ttu-id="86969-110">Wenn die Grenze überschritten wird, wird eine Meldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="86969-110">If the limit is exceeded, a message is displayed.</span></span>  
  
### <a name="to-filter-data-based-on-column-values"></a><span data-ttu-id="86969-111">So filtern Sie Daten auf Grundlage von Spaltenwerten</span><span class="sxs-lookup"><span data-stu-id="86969-111">To filter data based on column values</span></span>  
  
1.  <span data-ttu-id="86969-112">Wählen Sie im Modell-Designer eine Tabelle aus, und klicken Sie dann auf den Pfeil in der Kopfzeile der Spalte, nach der Sie filtern möchten.</span><span class="sxs-lookup"><span data-stu-id="86969-112">In the model designer, select a table, and then click the arrow in the header of the column that you want to filter by.</span></span>  
  
2.  <span data-ttu-id="86969-113">Führen Sie im Menü AutoFilter einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="86969-113">In the AutoFilter menu, do one of the following:</span></span>  
  
    -   <span data-ttu-id="86969-114">Wählen Sie in der Liste der Spaltenwerte mindestens einen Wert aus, nach dem gefiltert werden soll, bzw. heben Sie die Auswahl auf, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="86969-114">In the list of column values, select or clear one or more values to filter by, and then click **OK**.</span></span>  
  
         <span data-ttu-id="86969-115">Wenn die Anzahl der Werte sehr groß ist, kann es sein, dass einzelne Elemente nicht in der Liste angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="86969-115">If the number of values is extremely large, individual items might not be shown in the list.</span></span> <span data-ttu-id="86969-116">Stattdessen wird eine Meldung angezeigt, dass zu viele Elemente zum Anzeigen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="86969-116">Instead, you will see the message, "Too many items to show."</span></span>  
  
    -   <span data-ttu-id="86969-117">Klicken Sie je nach Typ der Spalte auf **Zahlen Filter** oder **Text Filter** , und klicken Sie dann auf die Befehle des Vergleichs Operators (z. b. ist **gleich**), oder klicken Sie auf **benutzerdefinierter Filter**.</span><span class="sxs-lookup"><span data-stu-id="86969-117">Click **Number Filters** or **Text Filters** (depending on the type of column), and then clicke of the comparison operator commands (such as **Equals**), or click **Custom Filter**.</span></span> <span data-ttu-id="86969-118">Erstellen Sie im Dialogfeld **Benutzerdefinierter Filter** den Filter, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="86969-118">In the **Custom Filter** dialog box, create the filter, and then click **OK**.</span></span>  
  
### <a name="to-clear-a-filter-for-a-column"></a><span data-ttu-id="86969-119">So löschen Sie einen Filter für eine Spalte</span><span class="sxs-lookup"><span data-stu-id="86969-119">To clear a filter for a column</span></span>  
  
1.  <span data-ttu-id="86969-120">Klicken Sie auf den Pfeil in der Kopfzeile der Spalte, für die Sie den Filter löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="86969-120">Click the arrow in the header of the column for which you want to clear a filter.</span></span>  
  
2.  <span data-ttu-id="86969-121">Klicken Sie auf \*\*Filter \<Column Name> aus löschen \*\*.</span><span class="sxs-lookup"><span data-stu-id="86969-121">Click **Clear Filter from \<Column Name>**.</span></span>  
  
### <a name="to-clear-all-filters-for-a-table"></a><span data-ttu-id="86969-122">So löschen Sie alle Filter für eine Tabelle</span><span class="sxs-lookup"><span data-stu-id="86969-122">To clear all filters for a table</span></span>  
  
1.  <span data-ttu-id="86969-123">Wählen Sie im Modell-Designer die Tabelle aus, für die Sie die Filter löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="86969-123">In the model designer, select the table for which you want to clear filters.</span></span>  
  
2.  <span data-ttu-id="86969-124">Klicken Sie auf das Menü **Spalte** und dann auf **Alle Filter löschen**.</span><span class="sxs-lookup"><span data-stu-id="86969-124">Click on the **Column** menu, and then click **Clear All Filters**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86969-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="86969-125">See Also</span></span>  
 <span data-ttu-id="86969-126">[Filtern und Sortieren von Daten &#40;tabellarischen SSAS-&#41;](../filter-and-sort-data-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="86969-126">[Filter and Sort Data &#40;SSAS Tabular&#41;](../filter-and-sort-data-ssas-tabular.md) </span></span>  
 <span data-ttu-id="86969-127">[Perspektiven &#40;tabellarischen SSAS-&#41;](perspectives-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="86969-127">[Perspectives &#40;SSAS Tabular&#41;](perspectives-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="86969-128">Rollen &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="86969-128">Roles &#40;SSAS Tabular&#41;</span></span>](roles-ssas-tabular.md)  
  
  
