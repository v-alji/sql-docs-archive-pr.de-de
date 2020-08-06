---
title: Umbenennen einer Tabelle oder Spalte (SSAS-tabellarisch) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.renametableorcolumn.f1
ms.assetid: 88061a39-c5aa-403d-a52b-7fdb365fc235
author: minewiskan
ms.author: owend
ms.openlocfilehash: d3a2e9a9f41434e64f9ec5ea2180861b459e8f97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723121"
---
# <a name="rename-a-table-or-column-ssas-tabular"></a><span data-ttu-id="d8f33-102">Umbenennen einer Tabelle oder Spalte (SSAS – tabellarisch)</span><span class="sxs-lookup"><span data-stu-id="d8f33-102">Rename a Table or Column (SSAS Tabular)</span></span>
  <span data-ttu-id="d8f33-103">Sie können während des Importvorgangs den Namen einer Tabelle ändern, indem Sie im **Tabellenimport-Assistenten** auf der Seite **Tabellen und Sichten auswählen** einen **Anzeigenamen**eingeben.</span><span class="sxs-lookup"><span data-stu-id="d8f33-103">You can change the name of a table during the import process by typing a **Friendly Name** in the **Select Tables and Views** page of the **Table Import Wizard**.</span></span> <span data-ttu-id="d8f33-104">Sie können während des Datenimports auch Tabellen- und Spaltennamen ändern, indem Sie im **Tabellenimport-Assistenten** auf der Seite **SQL-Abfrage angeben**eine Abfrage angeben.</span><span class="sxs-lookup"><span data-stu-id="d8f33-104">You can also change table and column names if you import data by specifying a query on the **Specify a SQL Query** page of the **Table Import Wizard**.</span></span>  
  
 <span data-ttu-id="d8f33-105">Nachdem dem Modell die Daten hinzugefügt wurden, wird der Name (oder Titel) einer Tabelle auf der Tabellenregisterkarte im unteren Bereich des Modell-Designers angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d8f33-105">After you have added the data to the model, the name (or title) of a table appears on the table tab, at the bottom of the model designer.</span></span> <span data-ttu-id="d8f33-106">Sie können den Namen einer Tabelle ändern, um ihr einen geeigneteren Namen zu geben.</span><span class="sxs-lookup"><span data-stu-id="d8f33-106">You can change the name of your table to give it a more appropriate name.</span></span> <span data-ttu-id="d8f33-107">Sie können eine Spalte auch umbenennen, nachdem die Daten dem Modell hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="d8f33-107">You can also rename a column after the data has been added to the model.</span></span> <span data-ttu-id="d8f33-108">Diese Option ist insbesondere dann wichtig, wenn Sie Daten aus mehreren Quellen importiert haben und sicherstellen möchten, dass Spalten in anderen Tabellen Namen haben, die leicht zu unterscheiden sind.</span><span class="sxs-lookup"><span data-stu-id="d8f33-108">This option is especially important when you have imported data from multiple sources, and want to ensure that columns in different tables have names that are easy to distinguish.</span></span>  
  
### <a name="to-rename-a-table"></a><span data-ttu-id="d8f33-109">So benennen Sie eine Tabelle um</span><span class="sxs-lookup"><span data-stu-id="d8f33-109">To rename a table</span></span>  
  
1.  <span data-ttu-id="d8f33-110">Klicken Sie im Modell-Designer mit der rechten Maustaste auf die Registerkarte der Tabelle, die Sie umbenennen möchten, und klicken Sie auf **Umbenennen**.</span><span class="sxs-lookup"><span data-stu-id="d8f33-110">In the model designer, right-click the tab that contains the table that you want to rename, and then click **Rename**.</span></span>  
  
2.  <span data-ttu-id="d8f33-111">Geben Sie den neuen Namen ein.</span><span class="sxs-lookup"><span data-stu-id="d8f33-111">Type the new name.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d8f33-112">Sie können mit dem Dialogfeld **Tabelleneigenschaften bearbeiten** andere Eigenschaften einer Tabelle bearbeiten, einschließlich der Verbindungsinformationen und Spaltenzuordnungen.</span><span class="sxs-lookup"><span data-stu-id="d8f33-112">You can edit other properties of a table, including the connection information and column mappings, by using the **Edit Table Properties** dialog box.</span></span> <span data-ttu-id="d8f33-113">Den Namen können Sie in diesem Dialogfeld jedoch nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="d8f33-113">However, you cannot change the name in this dialog box.</span></span>  
  
### <a name="to-rename-a-column"></a><span data-ttu-id="d8f33-114">So benennen Sie eine Spalte um</span><span class="sxs-lookup"><span data-stu-id="d8f33-114">To rename a column</span></span>  
  
1.  <span data-ttu-id="d8f33-115">Doppelklicken Sie im Modell-Designer auf die Kopfzeile der Spalte, die Sie umbenennen möchten, oder klicken Sie mit der rechten Maustaste auf die Kopfzeile, und wählen Sie im Kontextmenü **Spalte umbenennen** aus.</span><span class="sxs-lookup"><span data-stu-id="d8f33-115">In the model designer, double-click the header of the column that you want to rename, or right-click the header and select **Rename Column** from the context menu.</span></span>  
  
2.  <span data-ttu-id="d8f33-116">Geben Sie den neuen Namen ein.</span><span class="sxs-lookup"><span data-stu-id="d8f33-116">Type the new name.</span></span>  
  
## <a name="naming-requirements-for-columns-and-tables"></a><span data-ttu-id="d8f33-117">Anforderungen für die Benennung von Spalten und Tabellen</span><span class="sxs-lookup"><span data-stu-id="d8f33-117">Naming Requirements for Columns and Tables</span></span>  
 <span data-ttu-id="d8f33-118">Die folgenden Wörter und Zeichen können nicht im Namen einer Tabelle oder einer Spalte verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="d8f33-118">The following words and characters cannot be used in the name of a table or column:</span></span>  
  
-   <span data-ttu-id="d8f33-119">Führende oder nachfolgende Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="d8f33-119">Leading or trailing spaces</span></span>  
  
-   <span data-ttu-id="d8f33-120">Steuerzeichen</span><span class="sxs-lookup"><span data-stu-id="d8f33-120">Control characters</span></span>  
  
-   <span data-ttu-id="d8f33-121">Die folgenden Zeichen (die in den Namen von Analysis Services-Objekten nicht gültig sind):.,; ':/ \\ \*|? &% $! + = () [] {}<></span><span class="sxs-lookup"><span data-stu-id="d8f33-121">The following characters (which are not valid in the names of Analysis Services objects): .,;':/\\*|?&%$!+=()[]{}<></span></span>  
  
-   <span data-ttu-id="d8f33-122">Von Analysis Services reservierte Schlüsselwörter, einschließlich Funktionsnamen und Operatoren von Multidimensional Expressions (MDX) und Data Mining Extensions (DMX)</span><span class="sxs-lookup"><span data-stu-id="d8f33-122">Analysis Services reserved keywords, including Multidimensional Expressions (MDX) and Data Mining Extensions (DMX) function names and operators.</span></span>  
  
## <a name="effect-of-renaming-on-existing-tables-columns-and-calculations"></a><span data-ttu-id="d8f33-123">Auswirkung des Umbenennungsvorgangs auf vorhandene Tabellen, Spalten und Berechnungen</span><span class="sxs-lookup"><span data-stu-id="d8f33-123">Effect of Renaming on Existing Tables, Columns, and Calculations</span></span>  
 <span data-ttu-id="d8f33-124">Jedes Mal, wenn Sie den Namen einer Tabelle ändern, ändern Sie den Namen des zugrunde liegenden Tabellenobjekts, der möglicherweise mehrere Spalten oder Measures enthält.</span><span class="sxs-lookup"><span data-stu-id="d8f33-124">Whenever you change the name of a table, you change the name of the underlying table object, which may contain multiple columns or measures.</span></span> <span data-ttu-id="d8f33-125">Daher müssen alle Spalten in der Tabelle und alle Beziehungen, die diese Tabelle verwenden, aktualisiert werden, um den neuen Namen in ihren Definitionen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d8f33-125">Therefore, any columns that are in the table, and any relationships that use the table, must be updated to use the new name in their definitions.</span></span> <span data-ttu-id="d8f33-126">Dieses Update wird in einigen Fällen automatisch durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="d8f33-126">This update happens automatically in some cases.</span></span> <span data-ttu-id="d8f33-127">Measures werden nicht automatisch aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="d8f33-127">Measures are not updated automatically.</span></span>  
  
 <span data-ttu-id="d8f33-128">Darüber hinaus müssen alle Berechnungen, die die umbenannte Tabelle oder Spalten in der umbenannten Tabelle verwenden, ebenfalls aktualisiert werden, und die von diesen Berechnungen abgeleiteten Daten müssen aktualisiert und neu berechnet werden.</span><span class="sxs-lookup"><span data-stu-id="d8f33-128">Moreover, any calculations that use the renamed table, or that use columns from the renamed table, must also be updated, and the data derived from those calculations must be refreshed and recalculated.</span></span> <span data-ttu-id="d8f33-129">Je nach Anzahl der betroffenen Tabellen und Berechnungen kann dies einige Zeit in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="d8f33-129">Depending on how many tables and calculations are affected, this can take some time to complete.</span></span> <span data-ttu-id="d8f33-130">Der beste Zeitpunkt zum Umbenennen von Tabellen ist daher entweder während des Importvorgangs oder bevor Sie komplexe Beziehungen und Berechnungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="d8f33-130">Therefore, the best time to rename tables is either during the import process, or before you start to build complex relationships and calculations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8f33-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d8f33-131">See Also</span></span>  
 <span data-ttu-id="d8f33-132">[Tabellen und Spalten &#40;tabellarischen SSAS-&#41;](tables-and-columns-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="d8f33-132">[Tables and Columns &#40;SSAS Tabular&#41;](tables-and-columns-ssas-tabular.md) </span></span>  
 <span data-ttu-id="d8f33-133">[Aus Power Pivot &#40;tabellarischen SSAS-&#41;importieren](import-from-power-pivot-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="d8f33-133">[Import from PowerPivot &#40;SSAS Tabular&#41;](import-from-power-pivot-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="d8f33-134">Importieren aus Analysis Services &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="d8f33-134">Import from Analysis Services &#40;SSAS Tabular&#41;</span></span>](import-from-analysis-services-ssas-tabular.md)  
  
  
