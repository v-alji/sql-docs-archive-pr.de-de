---
title: Anzeigen der Statistikeigenschaften | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
f1_keywords:
- sql12.swb.statistics.details.f1
helpviewer_keywords:
- viewing statistics properties
- statistics [SQL Server], viewing properties
ms.assetid: 0eaa2101-006e-4015-9979-3468b50e0aaa
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 63cabc5d8844982604993acac6a791317ee36925
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621404"
---
# <a name="view-statistics-properties"></a><span data-ttu-id="5e02c-102">Anzeigen von Statistikeigenschaften</span><span class="sxs-lookup"><span data-stu-id="5e02c-102">View Statistics Properties</span></span>
  <span data-ttu-id="5e02c-103">Sie können die aktuelle Abfrageoptimierungsstatistik für eine Tabelle oder eine indizierte Sicht in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]anzeigen.</span><span class="sxs-lookup"><span data-stu-id="5e02c-103">You can display current query optimization statistics for a table or indexed view in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="5e02c-104">Statistikobjekte enthalten einen Header mit Metadaten über die Statistik, ein Histogramm mit der Verteilung der Werte in der ersten Schlüsselspalte des Statistikobjekts sowie einen Dichtevektor zum Messen der Korrelation zwischen Spalten.</span><span class="sxs-lookup"><span data-stu-id="5e02c-104">Statistics objects include a header with metadata about the statistics, a histogram with the distribution of values in the first key column of the statistics object, and a density vector to measure cross-column correlation.</span></span> <span data-ttu-id="5e02c-105">Weitere Informationen zu Histogrammen und Dichtevektoren finden Sie unter [DBCC SHOW_STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-show-statistics-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5e02c-105">For more information about histograms and density vectors, see [DBCC SHOW_STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-show-statistics-transact-sql)</span></span>  
  
 <span data-ttu-id="5e02c-106">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="5e02c-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5e02c-107">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="5e02c-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5e02c-108">Security</span><span class="sxs-lookup"><span data-stu-id="5e02c-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5e02c-109">**So zeigen Sie Statistikeigenschaften an mit:**</span><span class="sxs-lookup"><span data-stu-id="5e02c-109">**To view statistics properties, using:**</span></span>  
  
     [<span data-ttu-id="5e02c-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5e02c-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5e02c-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5e02c-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5e02c-112">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="5e02c-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5e02c-113">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="5e02c-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5e02c-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="5e02c-114">Permissions</span></span>  
 <span data-ttu-id="5e02c-115">Zum Anzeigen des Statistikobjekts muss der Benutzer Besitzer der Tabelle oder Mitglied der festen Serverrolle `sysadmin` bzw. der festen Datenbankrollen `db_owner` oder `db_ddladmin` sein.</span><span class="sxs-lookup"><span data-stu-id="5e02c-115">In order to view the statistics object, the user must own the table or the user must be a member of the `sysadmin` fixed server role, the `db_owner` fixed database role, or the `db_ddladmin` fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5e02c-116">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5e02c-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-statistics-properties"></a><span data-ttu-id="5e02c-117">So zeigen Sie Statistikeigenschaften an</span><span class="sxs-lookup"><span data-stu-id="5e02c-117">To view statistics properties</span></span>  
  
1.  <span data-ttu-id="5e02c-118">Klicken Sie im **Objekt-Explorer**auf das Pluszeichen, um die Datenbank zu erweitern, in der Sie eine neue Statistik erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="5e02c-118">In **Object Explorer**, click the plus sign to expand the database in which you want to create a new statistic.</span></span>  
  
2.  <span data-ttu-id="5e02c-119">Klicken Sie auf das Pluszeichen, um den Ordner **Tabellen** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="5e02c-119">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="5e02c-120">Klicken Sie auf das Pluszeichen, um die Tabelle zu erweitern, in der Sie die Eigenschaften der Statistik anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="5e02c-120">Click the plus sign to expand the table in which you want to view the statistic's properties.</span></span>  
  
4.  <span data-ttu-id="5e02c-121">Klicken Sie auf das Pluszeichen, um den Ordner **Statistik** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="5e02c-121">Click the plus sign to expand the **Statistics** folder.</span></span>  
  
5.  <span data-ttu-id="5e02c-122">Klicken Sie mit der rechten Maustaste auf das Statistikobjekt, dessen Eigenschaften Sie anzeigen möchten, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="5e02c-122">Right-click the Statistics object of which you want to view the properties and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="5e02c-123">Klicken Sie im Dialogfeld **Statistikeigenschaften -** _statistics_name_ im Bereich **Seite auswählen** auf die Option **Details**.</span><span class="sxs-lookup"><span data-stu-id="5e02c-123">In the **Statistics Properties -** _statistics_name_ dialog box, in the **Select a page** pane, select **Details**.</span></span>  
  
     <span data-ttu-id="5e02c-124">Die folgenden Eigenschaften werden auf der Seite **Details** im Dialogfeld **Statistikeigenschaften -** _statistics_name_ angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5e02c-124">The following properties show on the **Details** page in the **Statistics Properties -** _statistics_name_ dialog box.</span></span>  
  
     <span data-ttu-id="5e02c-125">**Tabellenname**</span><span class="sxs-lookup"><span data-stu-id="5e02c-125">**Table Name**</span></span>  
     <span data-ttu-id="5e02c-126">Zeigt den Namen der Tabelle an, die von den Statistiken beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="5e02c-126">Displays the name of the table described by the statistics.</span></span>  
  
     <span data-ttu-id="5e02c-127">**Statistikname**</span><span class="sxs-lookup"><span data-stu-id="5e02c-127">**Statistics Name**</span></span>  
     <span data-ttu-id="5e02c-128">Zeigt den Namen des Datenbankobjekts an, in dem die Statistiken gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="5e02c-128">Displays the name of the database object where the statistics are stored.</span></span>  
  
     <span data-ttu-id="5e02c-129">**Statistik für INDEXstatistics_name**</span><span class="sxs-lookup"><span data-stu-id="5e02c-129">**Statistics for INDEXstatistics_name**</span></span>  
     <span data-ttu-id="5e02c-130">Dieses Textfeld zeigt die Eigenschaften an, die vom Statistikobjekt zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="5e02c-130">This text box shows the properties returned from the statistics object.</span></span> <span data-ttu-id="5e02c-131">Diese Eigenschaften gehören zu drei unterschiedlichen Bereichen: STAT_HEADER. DENSITY_VECTOR und HISTOGRAM.</span><span class="sxs-lookup"><span data-stu-id="5e02c-131">This properties are divided into three sections: Stats Header, Density Vector, and Histogram.</span></span>  
  
     <span data-ttu-id="5e02c-132">Die folgenden Informationen beschreiben die Spalten, die im Resultset für STAT_HEADER zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="5e02c-132">The following information describes the columns returned in the result set for the Stats Header.</span></span>  
  
     <span data-ttu-id="5e02c-133">**Name**</span><span class="sxs-lookup"><span data-stu-id="5e02c-133">**Name**</span></span>  
     <span data-ttu-id="5e02c-134">Name des Statistikobjekts.</span><span class="sxs-lookup"><span data-stu-id="5e02c-134">Name of the statistics object.</span></span>  
  
     <span data-ttu-id="5e02c-135">**Aktualisiert**</span><span class="sxs-lookup"><span data-stu-id="5e02c-135">**Updated**</span></span>  
     <span data-ttu-id="5e02c-136">Datum und Uhrzeit des letzten Updates der Statistik.</span><span class="sxs-lookup"><span data-stu-id="5e02c-136">Date and time the statistics were last updated.</span></span>  
  
     <span data-ttu-id="5e02c-137">**Zeilen**</span><span class="sxs-lookup"><span data-stu-id="5e02c-137">**Rows**</span></span>  
     <span data-ttu-id="5e02c-138">Gesamtanzahl der Zeilen in der Tabelle oder indizierten Sicht zum Zeitpunkt des letzten Updates der Statistik.</span><span class="sxs-lookup"><span data-stu-id="5e02c-138">Total number of rows in the table or indexed view when the statistics were last updated.</span></span> <span data-ttu-id="5e02c-139">Wenn die Statistik gefiltert wird oder einem gefilterten Index entspricht, kann die Anzahl der Zeilen geringer als die Anzahl der Zeilen in der Tabelle sein.</span><span class="sxs-lookup"><span data-stu-id="5e02c-139">If the statistics are filtered or correspond to a filtered index, the number of rows might be less than the number of rows in the table.</span></span>  
  
     <span data-ttu-id="5e02c-140">**Rows Sampled**</span><span class="sxs-lookup"><span data-stu-id="5e02c-140">**Rows Sampled**</span></span>  
     <span data-ttu-id="5e02c-141">Gesamtzahl der Zeilen, die für die statistischen Berechnungen in die Stichprobe aufgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="5e02c-141">Total number of rows sampled for statistics calculations.</span></span> <span data-ttu-id="5e02c-142">Wenn Rows Sampled < Rows, sind das angezeigte Histogramm und die Dichteergebnisse Schätzungen auf Grundlage der als Stichprobe entnommenen Zeilen.</span><span class="sxs-lookup"><span data-stu-id="5e02c-142">If Rows Sampled < Rows, the displayed histogram and density results are estimates based on the sampled rows.</span></span>  
  
     <span data-ttu-id="5e02c-143">**Schritte**</span><span class="sxs-lookup"><span data-stu-id="5e02c-143">**Steps**</span></span>  
     <span data-ttu-id="5e02c-144">Anzahl der Schritte im Histogramm.</span><span class="sxs-lookup"><span data-stu-id="5e02c-144">Number of steps in the histogram.</span></span> <span data-ttu-id="5e02c-145">Jeder Schritt umfasst einen Bereich von Spaltenwerten gefolgt von einem oberen Spaltengrenzwert.</span><span class="sxs-lookup"><span data-stu-id="5e02c-145">Each step spans a range of column values followed by an upper bound column value.</span></span> <span data-ttu-id="5e02c-146">Die Histogrammschritte werden in der Statistik in der ersten Schlüsselspalte definiert.</span><span class="sxs-lookup"><span data-stu-id="5e02c-146">The histogram steps are defined on the first key column in the statistics.</span></span> <span data-ttu-id="5e02c-147">Die maximale Anzahl von Schritten ist 200.</span><span class="sxs-lookup"><span data-stu-id="5e02c-147">The maximum number of steps is 200.</span></span>  
  
     <span data-ttu-id="5e02c-148">**Density**</span><span class="sxs-lookup"><span data-stu-id="5e02c-148">**Density**</span></span>  
     <span data-ttu-id="5e02c-149">Berechnet als 1 / *verschiedene Werte* für alle Werte in der ersten Schlüsselspalte des Statistikobjekts mit Ausnahme der Begrenzungswerte des Histogramms.</span><span class="sxs-lookup"><span data-stu-id="5e02c-149">Calculated as 1 / *distinct values* for all values in the first key column of the statistics object, excluding the histogram boundary values.</span></span> <span data-ttu-id="5e02c-150">Dieser Dichtewert wird vom Abfrageoptimierer nicht verwendet und für die Abwärtskompatibilität mit Versionen vor SQL Server 2008 angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5e02c-150">This Density value is not used by the query optimizer and is displayed for backward compatibility with versions before SQL Server 2008.</span></span>  
  
     <span data-ttu-id="5e02c-151">**Average Key Length**</span><span class="sxs-lookup"><span data-stu-id="5e02c-151">**Average Key Length**</span></span>  
     <span data-ttu-id="5e02c-152">Durchschnittliche Anzahl von Bytes pro Wert für alle Schlüsselspalten im Statistikobjekt.</span><span class="sxs-lookup"><span data-stu-id="5e02c-152">Average number of bytes per value for all of the key columns in the statistics object.</span></span>  
  
     <span data-ttu-id="5e02c-153">**String Index**</span><span class="sxs-lookup"><span data-stu-id="5e02c-153">**String Index**</span></span>  
     <span data-ttu-id="5e02c-154">"Ja" gibt an, dass das Statistikobjekt Statistiken über Zusammenfassungen von Zeichenfolgen enthält, um die Kardinalitätsschätzungen für Abfrageprädikate, die den LIKE-Operator verwenden, zu verbessern, z. B. `WHERE ProductName LIKE '%Bike'`.</span><span class="sxs-lookup"><span data-stu-id="5e02c-154">Yes indicates the statistics object contains string summary statistics to improve the cardinality estimates for query predicates that use the LIKE operator; for example, `WHERE ProductName LIKE '%Bike'`.</span></span> <span data-ttu-id="5e02c-155">Zusammenfassungen von Zeichenfolgen werden getrennt vom Histogramm gespeichert und in der ersten Schlüsselspalte des Statistikobjekts erstellt, wenn es vom Typ **char**, **varchar**, **nchar**, **nvarchar**, **varchar(max)** , **nvarchar(max)** , **text**, or **ntext**ist.</span><span class="sxs-lookup"><span data-stu-id="5e02c-155">String summary statistics are stored separately from the histogram and are created on the first key column of the statistics object when it is of type **char**, **varchar**, **nchar**, **nvarchar**, **varchar(max)**, **nvarchar(max)**, **text**, or **ntext**.</span></span>  
  
     <span data-ttu-id="5e02c-156">**Filterausdruck**</span><span class="sxs-lookup"><span data-stu-id="5e02c-156">**Filter Expression**</span></span>  
     <span data-ttu-id="5e02c-157">Prädikat für die Teilmenge von Tabellenzeilen, die im Statistikobjekt enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="5e02c-157">Predicate for the subset of table rows included in the statistics object.</span></span> <span data-ttu-id="5e02c-158">NULL = Nicht gefilterte Statistik.</span><span class="sxs-lookup"><span data-stu-id="5e02c-158">NULL = non-filtered statistics.</span></span>  
  
     <span data-ttu-id="5e02c-159">**Unfiltered Rows**</span><span class="sxs-lookup"><span data-stu-id="5e02c-159">**Unfiltered Rows**</span></span>  
     <span data-ttu-id="5e02c-160">Gesamtzahl von Zeilen in der Tabelle vor dem Anwenden des Filterausdrucks.</span><span class="sxs-lookup"><span data-stu-id="5e02c-160">Total number of rows in the table before applying the filter expression.</span></span> <span data-ttu-id="5e02c-161">Wenn Filter Expression NULL ist, ist Unfiltered Rows gleich Rows.</span><span class="sxs-lookup"><span data-stu-id="5e02c-161">If Filter Expression is NULL, Unfiltered Rows is equal to Rows.</span></span>  
  
     <span data-ttu-id="5e02c-162">Die folgenden Informationen beschreiben die Spalten, die im Resultset für DENSITY_VECTOR zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="5e02c-162">The following information describes the columns returned in the result set for the Density Vector.</span></span>  
  
     <span data-ttu-id="5e02c-163">**All Density**</span><span class="sxs-lookup"><span data-stu-id="5e02c-163">**All Density**</span></span>  
     <span data-ttu-id="5e02c-164">Die Dichte ist 1 / *verschiedene Werte*.</span><span class="sxs-lookup"><span data-stu-id="5e02c-164">Density is 1 / *distinct values*.</span></span> <span data-ttu-id="5e02c-165">Die Ergebnisse zeigen die Dichte für jedes Präfix von Spalten im Statistikobjekt mit einer Zeile pro Dichte an.</span><span class="sxs-lookup"><span data-stu-id="5e02c-165">Results display density for each prefix of columns in the statistics object, one row per density.</span></span> <span data-ttu-id="5e02c-166">Bei einem unterschiedlichen Wert handelt es sich um eine unterschiedliche Liste der Spaltenwerte pro Zeile und pro Spaltenpräfix.</span><span class="sxs-lookup"><span data-stu-id="5e02c-166">A distinct value is a distinct list of the column values per row and per columns prefix.</span></span> <span data-ttu-id="5e02c-167">Wenn das Statistikobjekt beispielsweise Schlüsselspalten (A, B, C) enthält, geben die Ergebnisse die Dichte der unterschiedlichen Wertelisten jedes dieser Spaltenpräfixe an: (A), (A,B) und (A, B, C).</span><span class="sxs-lookup"><span data-stu-id="5e02c-167">For example, if the statistics object contains key columns (A, B, C), the results report the density of the distinct lists of values in each of these column prefixes: (A), (A,B), and (A, B, C).</span></span> <span data-ttu-id="5e02c-168">Mit dem Präfix (A, B, C) ist jede dieser Listen eine Liste unterschiedlicher Werte: (3, 5, 6), (4, 4, 6), (4, 5, 6), (4, 5, 7).</span><span class="sxs-lookup"><span data-stu-id="5e02c-168">Using the prefix (A, B, C), each of these lists is a distinct value list: (3, 5, 6), (4, 4, 6), (4, 5, 6), (4, 5, 7).</span></span> <span data-ttu-id="5e02c-169">Mit dem Präfix (A, B) weisen dieselben Spaltenwerte diese unterschiedlichen Wertelisten auf: (3, 5), (4, 4) und (4, 5).</span><span class="sxs-lookup"><span data-stu-id="5e02c-169">Using the prefix (A, B) the same column values have these distinct value lists: (3, 5), (4, 4), and (4, 5).</span></span>  
  
     <span data-ttu-id="5e02c-170">**Average Length**</span><span class="sxs-lookup"><span data-stu-id="5e02c-170">**Average Length**</span></span>  
     <span data-ttu-id="5e02c-171">Durchschnittliche Länge in Bytes zum Speichern einer Liste der Spaltenwerte für das Spaltenpräfix.</span><span class="sxs-lookup"><span data-stu-id="5e02c-171">Average length, in bytes, to store a list of the column values for the column prefix.</span></span> <span data-ttu-id="5e02c-172">Wenn die Werte in der Liste (3, 5, 6) beispielsweise jeweils 4 Bytes erfordern, beträgt die Länge 12 Bytes.</span><span class="sxs-lookup"><span data-stu-id="5e02c-172">For example, if the values in the list (3, 5, 6) each require 4 bytes the length is 12 bytes.</span></span>  
  
     <span data-ttu-id="5e02c-173">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="5e02c-173">**Columns**</span></span>  
     <span data-ttu-id="5e02c-174">Namen der Spalten im Präfix, für die All Density und Average Length angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="5e02c-174">Names of columns in the prefix for which All density and Average length are displayed.</span></span>  
  
     <span data-ttu-id="5e02c-175">Die folgenden Informationen beschreiben die Spalten, die im Resultset für HISTOGRAM zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="5e02c-175">The following information describes the columns returned in the result set for the Histogram.</span></span>  
  
     <span data-ttu-id="5e02c-176">**RANGE_HI_KEY**</span><span class="sxs-lookup"><span data-stu-id="5e02c-176">**RANGE_HI_KEY**</span></span>  
     <span data-ttu-id="5e02c-177">Oberer Spaltengrenzwert für einen Histogrammschritt.</span><span class="sxs-lookup"><span data-stu-id="5e02c-177">Upper bound column value for a histogram step.</span></span> <span data-ttu-id="5e02c-178">Der Spaltenwert wird auch als Schlüsselwert bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="5e02c-178">The column value is also called a key value.</span></span>  
  
     <span data-ttu-id="5e02c-179">**RANGE_ROWS**</span><span class="sxs-lookup"><span data-stu-id="5e02c-179">**RANGE_ROWS**</span></span>  
     <span data-ttu-id="5e02c-180">Geschätzte Anzahl von Zeilen, deren Spaltenwerte innerhalb eines Histogrammschritts liegen, ohne den oberen Grenzwert.</span><span class="sxs-lookup"><span data-stu-id="5e02c-180">Estimated number of rows whose column value falls within a histogram step, excluding the upper bound.</span></span>  
  
     <span data-ttu-id="5e02c-181">**EQ_ROWS**</span><span class="sxs-lookup"><span data-stu-id="5e02c-181">**EQ_ROWS**</span></span>  
     <span data-ttu-id="5e02c-182">Geschätzte Anzahl von Zeilen, deren Spaltenwerte der Obergrenze des Histogrammschritts entsprechen.</span><span class="sxs-lookup"><span data-stu-id="5e02c-182">Estimated number of rows whose column value equals the upper bound of the histogram step.</span></span>  
  
     <span data-ttu-id="5e02c-183">**DISTINCT_RANGE_ROWS**</span><span class="sxs-lookup"><span data-stu-id="5e02c-183">**DISTINCT_RANGE_ROWS**</span></span>  
     <span data-ttu-id="5e02c-184">Geschätzte Anzahl von Zeilen mit einem unterschiedlichen Spaltenwert innerhalb eines Histogrammschritts ohne den oberen Grenzwert.</span><span class="sxs-lookup"><span data-stu-id="5e02c-184">Estimated number of rows with a distinct column value within a histogram step, excluding the upper bound.</span></span>  
  
     <span data-ttu-id="5e02c-185">**AVG_RANGE_ROWS**</span><span class="sxs-lookup"><span data-stu-id="5e02c-185">**AVG_RANGE_ROWS**</span></span>  
     <span data-ttu-id="5e02c-186">Durchschnittliche Anzahl von Zeilen mit doppelten Spaltenwerten in einem Histogrammschritt ohne den oberen Grenzwert (RANGE_ROWS / DISTINCT_RANGE_ROWS für DISTINCT_RANGE_ROWS > 0).</span><span class="sxs-lookup"><span data-stu-id="5e02c-186">Average number of rows with duplicate column values within a histogram step, excluding the upper bound (RANGE_ROWS / DISTINCT_RANGE_ROWS for DISTINCT_RANGE_ROWS > 0).</span></span>  
  
7.  <span data-ttu-id="5e02c-187">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e02c-187">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5e02c-188">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5e02c-188">Using Transact-SQL</span></span>  
  
#### <a name="to-view-statistics-properties"></a><span data-ttu-id="5e02c-189">So zeigen Sie Statistikeigenschaften an</span><span class="sxs-lookup"><span data-stu-id="5e02c-189">To view statistics properties</span></span>  
  
1.  <span data-ttu-id="5e02c-190">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="5e02c-190">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5e02c-191">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="5e02c-191">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5e02c-192">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="5e02c-192">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- The following example displays all statistics information for the AK_Address_rowguid index of the Person.Address table.   
    DBCC SHOW_STATISTICS ("Person.Address", AK_Address_rowguid);   
    GO  
    ```  
  
 <span data-ttu-id="5e02c-193">Weitere Informationen finden Sie unter [DBCC SHOW_STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-show-statistics-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5e02c-193">For more information, see [DBCC SHOW_STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-show-statistics-transact-sql).</span></span>  
  
#### <a name="to-find-all-of-the-statistics-on-a-table-or-view"></a><span data-ttu-id="5e02c-194">So suchen Sie nach allen Statistiken einer Tabelle oder Sicht</span><span class="sxs-lookup"><span data-stu-id="5e02c-194">To find all of the statistics on a table or view</span></span>  
  
1.  <span data-ttu-id="5e02c-195">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="5e02c-195">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5e02c-196">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="5e02c-196">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5e02c-197">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="5e02c-197">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    /*Gets the following information: name and ID of the statistics, whether the statistics were created automatically or by the user, whether the statistics were created with the NORECOMPUTE option, and whether the statistics have a filter and, if so, what that filter is.  
    */  
    SELECT name AS statistics_name  
        ,stats_id  
        ,auto_created  
        ,user_created  
        ,no_recompute  
        ,has_filter  
        ,filter_definition  
    -- using the sys.stats catalog view  
    FROM sys.stats  
    -- for the Sales.SpecialOffer table  
    WHERE object_id = OBJECT_ID('Sales.SpecialOffer');  
    GO  
    ```  
  
 <span data-ttu-id="5e02c-198">Weitere Informationen finden Sie unter [sys.stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-stats-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5e02c-198">For more information, see [sys.stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-stats-transact-sql).</span></span>  
  
  
