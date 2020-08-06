---
title: Verwenden von Spaltensätzen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- sparse columns, column sets
- column sets
ms.assetid: a4f9de95-dc8f-4ad8-b957-137e32bfa500
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9cb496137c3986b78a55862e434c153d354a42ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622508"
---
# <a name="use-column-sets"></a><span data-ttu-id="668c2-102">Verwenden von Spaltensätzen</span><span class="sxs-lookup"><span data-stu-id="668c2-102">Use Column Sets</span></span>
  <span data-ttu-id="668c2-103">Für Tabellen, die Sparsespalten aufweisen, können Sie einen Spaltensatz festlegen, der alle Sparsespalten in der Tabelle zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="668c2-103">Tables that use sparse columns can designate a column set to return all sparse columns in the table.</span></span> <span data-ttu-id="668c2-104">Bei einem Spaltensatz handelt es sich um eine nicht typisierte XML-Darstellung, die alle Sparsespalten einer Tabelle in einer strukturierten Ausgabe kombiniert.</span><span class="sxs-lookup"><span data-stu-id="668c2-104">A column set is an untyped XML representation that combines all the sparse columns of a table into a structured output.</span></span> <span data-ttu-id="668c2-105">Wie auch berechnete Spalten werden Spaltensätze nicht physisch in der Tabelle gespeichert.</span><span class="sxs-lookup"><span data-stu-id="668c2-105">A column set is like a calculated column in that the column set is not physically stored in the table.</span></span> <span data-ttu-id="668c2-106">Der Unterschied zwischen einem Spaltensatz und einer berechneten Spalte besteht darin, dass der Spaltensatz direkt aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="668c2-106">A column set differs from a calculated column in that the column set is directly updatable.</span></span>  
  
 <span data-ttu-id="668c2-107">Verwenden Sie Spaltensätze, wenn die Tabelle eine große Anzahl an Spalten enthält und es sehr aufwändig ist, jede Spalte einzeln zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="668c2-107">You should consider using column sets when the number of columns in a table is large, and operating on them individually is cumbersome.</span></span> <span data-ttu-id="668c2-108">Außerdem verbessert sich die Anwendungsleistung, wenn zum Auswählen und Einfügen von Daten bei Tabellen mit sehr vielen Spalten Spaltensätze verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="668c2-108">Applications might see some performance improvement when they select and insert data by using column sets on tables that have lots of columns.</span></span> <span data-ttu-id="668c2-109">Die Leistung von Spaltensätzen kann jedoch beeinträchtigt werden, wenn für die Spalten in der Tabelle sehr viele Indizes definiert werden.</span><span class="sxs-lookup"><span data-stu-id="668c2-109">However, the performance of column sets can be reduced when many indexes are defined on the columns in the table.</span></span> <span data-ttu-id="668c2-110">Das liegt daran, dass in diesem Fall für einen Ausführungsplan mehr Arbeitsspeicher erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="668c2-110">This is because the amount of memory that is required for an execution plan increases.</span></span>  
  
 <span data-ttu-id="668c2-111">Zum Definieren eines Spaltensatzes verwenden Sie die Schlüsselwörter *<Spaltensatzname>* FOR ALL_SPARSE_COLUMNS in der [CREATE TABLE](/sql/t-sql/statements/create-table-transact-sql)-Anweisung oder in der [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql)-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="668c2-111">To define a column set, use the *<column_set_name>* FOR ALL_SPARSE_COLUMNS keywords in the[CREATE TABLE](/sql/t-sql/statements/create-table-transact-sql) or [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) statements.</span></span>  
  
## <a name="guidelines-for-using-column-sets"></a><span data-ttu-id="668c2-112">Richtlinien zum Verwenden von Spaltensätzen</span><span class="sxs-lookup"><span data-stu-id="668c2-112">Guidelines for Using Column Sets</span></span>  
 <span data-ttu-id="668c2-113">Wenn Sie Spaltensätze verwenden, beachten Sie die folgenden Richtlinien:</span><span class="sxs-lookup"><span data-stu-id="668c2-113">When you use column sets, consider the following guidelines:</span></span>  
  
-   <span data-ttu-id="668c2-114">Spalten mit geringer Dichte und ein Spaltensatz können als Teil der gleichen Anweisung hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="668c2-114">Sparse columns and a column set can be added as part of the same statement.</span></span>  
  
-   <span data-ttu-id="668c2-115">Der Spaltensatz kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="668c2-115">The column set cannot be changed.</span></span> <span data-ttu-id="668c2-116">Zum Ändern eines Spaltensatzes müssen Sie diesen löschen und einen neuen Spaltensatz erstellen.</span><span class="sxs-lookup"><span data-stu-id="668c2-116">To change a column set, you must delete and re-create the column set.</span></span>  
  
-   <span data-ttu-id="668c2-117">Sie können einer Tabelle, die bereits Sparsespalten enthält, keinen Spaltensatz hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="668c2-117">A column set cannot be added to a table if that table already contains sparse columns.</span></span>  
  
-   <span data-ttu-id="668c2-118">Sie können einen Spaltensatz Tabellen hinzufügen, die keine Sparsespalten enthalten.</span><span class="sxs-lookup"><span data-stu-id="668c2-118">A column set can be added to a table that does not include any sparse columns.</span></span> <span data-ttu-id="668c2-119">Wenn Sie der Tabelle zu einem späteren Zeitpunkt Sparsespalten hinzufügen, werden diese im Spaltensatz angezeigt.</span><span class="sxs-lookup"><span data-stu-id="668c2-119">If sparse columns are later added to the table, they will appear in the column set.</span></span>  
  
-   <span data-ttu-id="668c2-120">Es ist nur ein Spaltensatz pro Tabelle zulässig.</span><span class="sxs-lookup"><span data-stu-id="668c2-120">Only one column set is allowed per table.</span></span>  
  
-   <span data-ttu-id="668c2-121">Spaltensätze sind optional, d. h. zur Verwendung von Sparsespalten nicht zwingend erforderlich.</span><span class="sxs-lookup"><span data-stu-id="668c2-121">A column set is optional and is not required to use sparse columns.</span></span>  
  
-   <span data-ttu-id="668c2-122">Für einen Spaltensatz können keine Einschränkungen oder Standardwerte definiert werden.</span><span class="sxs-lookup"><span data-stu-id="668c2-122">Constraints or default values cannot be defined on a column set.</span></span>  
  
-   <span data-ttu-id="668c2-123">Berechnete Spalten können keine Spaltensatz-Spalten enthalten.</span><span class="sxs-lookup"><span data-stu-id="668c2-123">Computed columns cannot contain column set columns.</span></span>  
  
-   <span data-ttu-id="668c2-124">Verteilte Abfragen werden von Tabellen mit Spaltensätzen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="668c2-124">Distributed queries are not supported on tables that contain column sets.</span></span>  
  
-   <span data-ttu-id="668c2-125">Die Replikation unterstützt Spaltensätze nicht.</span><span class="sxs-lookup"><span data-stu-id="668c2-125">Replication does not support column sets.</span></span>  
  
-   <span data-ttu-id="668c2-126">Change Data Capture unterstützt Spaltensätze nicht.</span><span class="sxs-lookup"><span data-stu-id="668c2-126">Change data capture does not support column sets.</span></span>  
  
-   <span data-ttu-id="668c2-127">Ein Spaltensatz darf nicht Teil irgendeiner Art von Index sein.</span><span class="sxs-lookup"><span data-stu-id="668c2-127">A column set cannot be part of any kind of index.</span></span> <span data-ttu-id="668c2-128">Dies gilt auch für XML-Indizes, Volltextindizes und indizierte Sichten.</span><span class="sxs-lookup"><span data-stu-id="668c2-128">This includes XML indexes, full-text indexes, and indexed views.</span></span> <span data-ttu-id="668c2-129">Ein Spaltensatz kann einem Index nicht als eingeschlossene Spalte hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="668c2-129">A column set cannot be added as an included column in any index.</span></span>  
  
-   <span data-ttu-id="668c2-130">Ein Spaltensatz darf nicht im Filterausdruck eines gefilterten Indexes oder einer gefilterten Statistik verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="668c2-130">A column set cannot be used in the filter expression of a filtered index or filtered statistics.</span></span>  
  
-   <span data-ttu-id="668c2-131">Ein in einer Sicht enthaltener Spaltensatz wird als XML-Spalte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="668c2-131">When a view includes a column set, the column set appears in the view as an XML column.</span></span>  
  
-   <span data-ttu-id="668c2-132">Ein Spaltensatz darf nicht in einer indizierten Sichtdefinition enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="668c2-132">A column set cannot be included in an indexed view definition.</span></span>  
  
-   <span data-ttu-id="668c2-133">Partitionierte Sichten, die Tabellen mit Spaltensätzen enthalten, können aktualisiert werden, wenn die Sparsespalten in der partitionierten Sicht mit Namen angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="668c2-133">Partitioned views that include tables that contain column sets are updatable when the partitioned view specifies the sparse columns by name.</span></span> <span data-ttu-id="668c2-134">Eine partitionierte Sicht kann nicht aktualisiert werden, wenn sie lediglich einen Verweis auf den Spaltensatz enthält.</span><span class="sxs-lookup"><span data-stu-id="668c2-134">A partitioned view is not updatable when it references the column set.</span></span>  
  
-   <span data-ttu-id="668c2-135">Abfragebenachrichtigungen, die auf Spaltensätze verweisen, sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="668c2-135">Query notifications that refer to column sets are not permitted.</span></span>  
  
-   <span data-ttu-id="668c2-136">Für XML-Daten gilt eine Größenbeschränkung von 2 GB.</span><span class="sxs-lookup"><span data-stu-id="668c2-136">XML data has a size limit of 2 GB.</span></span> <span data-ttu-id="668c2-137">Wenn die gesamte Datengröße aller Sparsespalten ungleich NULL in einer Zeile diesen Wert überschreitet, wird für die Abfrage bzw. den DML-Vorgang ein Fehler ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="668c2-137">If the combined data of all the nonnull sparse columns in a row exceeds this limit, the query or DML operation will produce an error.</span></span>  
  
-   <span data-ttu-id="668c2-138">Informationen zu den Daten, die von der Funktion COLUMNS_UPDATED zurückgegeben werden, finden Sie unter [Verwenden von Spalten mit geringer Dichte](use-sparse-columns.md).</span><span class="sxs-lookup"><span data-stu-id="668c2-138">For information about the data that is returned by the COLUMNS_UPDATED function, see [Use Sparse Columns](use-sparse-columns.md).</span></span>  
  
## <a name="guidelines-for-selecting-data-from-a-column-set"></a><span data-ttu-id="668c2-139">Richtlinien zum Auswählen von Daten aus einem Spaltensatz</span><span class="sxs-lookup"><span data-stu-id="668c2-139">Guidelines for Selecting Data from a Column Set</span></span>  
 <span data-ttu-id="668c2-140">Beim Auswählen von Daten aus einem Spaltensatz sind die folgenden Richtlinien zu beachten:</span><span class="sxs-lookup"><span data-stu-id="668c2-140">Consider the following guidelines for selecting data from a column set:</span></span>  
  
-   <span data-ttu-id="668c2-141">Grundsätzlich handelt es sich bei einem Spaltensatz um eine aktualisierbare, berechnete XML-Spalte, die einen Satz zugrunde liegender relationaler Spalten in einer XML-Darstellung zusammenfasst.</span><span class="sxs-lookup"><span data-stu-id="668c2-141">Conceptually, a column set is a type of updatable, computed XML column that aggregates a set of underlying relational columns into a single XML representation.</span></span> <span data-ttu-id="668c2-142">Der Spaltensatz unterstützt nur die ALL_SPARSE_COLUMNS-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="668c2-142">The column set only supports the ALL_SPARSE_COLUMNS property.</span></span> <span data-ttu-id="668c2-143">Diese Eigenschaft dient zur Zusammenfassung aller Werte ungleich NULL in allen Sparsespalten für eine bestimmte Zeile.</span><span class="sxs-lookup"><span data-stu-id="668c2-143">This property is used to aggregate all nonnull values from all sparse columns for a particular row.</span></span>  
  
-   <span data-ttu-id="668c2-144">Im [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] -Tabellen-Editor werden Spaltensätze als bearbeitbare XML-Felder angezeigt.</span><span class="sxs-lookup"><span data-stu-id="668c2-144">In the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] table editor, column sets are displayed as an editable XML field.</span></span> <span data-ttu-id="668c2-145">Definieren Sie Spaltensätze im folgenden Format:</span><span class="sxs-lookup"><span data-stu-id="668c2-145">Define column sets in the format:</span></span>  
  
    ```  
    <column_name_1>value1</column_name_1><column_name_2>value2</column_name_2>...  
    ```  
  
     <span data-ttu-id="668c2-146">Beispiele für Spaltensatzwerte:</span><span class="sxs-lookup"><span data-stu-id="668c2-146">Examples of column set values are as follows:</span></span>  
  
    -   `<sparseProp1>10</sparseProp1><sparseProp3>20</sparseProp3>`  
  
    -   `<DocTitle>Bicycle Parts List</DocTitle><Region>West</Region>`  
  
-   <span data-ttu-id="668c2-147">Spalten mit geringer Dichte, die NULL-Werte enthalten, werden in der XML-Darstellung des Spaltensatzes nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="668c2-147">Sparse columns that contain null values are omitted from the XML representation for the column set.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="668c2-148">Durch das Hinzufügen eines Spaltensatzes ändert sich das Verhalten von SELECT \*-Abfragen.</span><span class="sxs-lookup"><span data-stu-id="668c2-148">Adding a column set changes the behavior of SELECT \* queries.</span></span> <span data-ttu-id="668c2-149">Statt der einzelnen Sparsespalten wird der Spaltensatz als XML-Spalte zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="668c2-149">The query will return the column set as an XML column and not return the individual sparse columns.</span></span> <span data-ttu-id="668c2-150">Schema-Designer und Softwareentwickler müssen darauf achten, dass der Code vorhandener Anwendungen hierdurch nicht gestört wird.</span><span class="sxs-lookup"><span data-stu-id="668c2-150">Schema designers and software developers must be careful not to break existing applications.</span></span>  
  
## <a name="inserting-or-modifying-data-in-a-column-set"></a><span data-ttu-id="668c2-151">Einfügen und Ändern von Daten in einem Spaltensatz</span><span class="sxs-lookup"><span data-stu-id="668c2-151">Inserting or Modifying Data in a Column Set</span></span>  
 <span data-ttu-id="668c2-152">Zur Änderung von Daten in einem Spaltensatz verwenden Sie die Namen der einzelnen Spalten. Sie können auch auf den Namen des Spaltensatzes verweisen und die Werte des Spaltensatzes angeben, indem Sie das XML-Format des Spaltensatzes verwenden.</span><span class="sxs-lookup"><span data-stu-id="668c2-152">Data manipulation of a sparse column can be performed by using the name of the individual columns, or by referencing the name of the column set and specifying the values of the column set by using the XML format of the column set.</span></span> <span data-ttu-id="668c2-153">Spalten mit geringer Dichte können in der XML-Spalte in beliebiger Reihenfolge angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="668c2-153">Sparse columns can appear in any order in the XML column.</span></span>  
  
 <span data-ttu-id="668c2-154">Wenn Sie die Werte von Sparsespalten mit dem XML-Spaltensatz einfügen bzw. aktualisieren, werden die Werte, die in die zugrunde liegenden Sparsespalten eingefügt werden, automatisch vom `xml`-Datentyp konvertiert.</span><span class="sxs-lookup"><span data-stu-id="668c2-154">When sparse column values are inserted or updated by using the XML column set, the values that are inserted into the underlying sparse columns are implicitly converted from the `xml` data type.</span></span> <span data-ttu-id="668c2-155">Bei numerischen Spalten werden leere Werte im XML-Format in leere Zeichenfolgen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="668c2-155">In the case of numeric columns, a blank value in the XML for the numeric column converts to an empty string.</span></span> <span data-ttu-id="668c2-156">Hierdurch wird der Wert 0 in die numerische Spalte eingefügt, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="668c2-156">This causes a zero to be inserted into the numeric column as shown in the following example.</span></span>  
  
```  
CREATE TABLE t (i int SPARSE, cs xml column_set FOR ALL_SPARSE_COLUMNS);  
GO  
INSERT t(cs) VALUES ('<i/>');  
GO  
SELECT i FROM t;  
GO  
```  
  
 <span data-ttu-id="668c2-157">In diesem Beispiel wurde kein Wert für die Spalte `i`angegeben, und der Wert `0` wurde eingefügt.</span><span class="sxs-lookup"><span data-stu-id="668c2-157">In this example, no value was specified for the column `i`, but the value `0` was inserted.</span></span>  
  
## <a name="using-the-sql_variant-data-type"></a><span data-ttu-id="668c2-158">Verwenden des sql_variant-Datentyps</span><span class="sxs-lookup"><span data-stu-id="668c2-158">Using the sql_variant Data Type</span></span>  
 <span data-ttu-id="668c2-159">Der `sql_variant`-Datentyp kann mehrere unterschiedliche Datentypen speichern, z. B. `int`, `char` und `date`.</span><span class="sxs-lookup"><span data-stu-id="668c2-159">The `sql_variant` date type can store multiple different data types, such as `int`, `char`, and `date`.</span></span> <span data-ttu-id="668c2-160">Spaltensätze geben Datentypinformationen zu Dezimalstellen, Genauigkeit und Gebietsschema, die mit einem `sql_variant`-Wert verknüpft sind, in der erstellten XML-Spalte als Attribute aus.</span><span class="sxs-lookup"><span data-stu-id="668c2-160">Column sets output the data type information such as scale, precision, and locale information that is associated with a `sql_variant` value as attributes in the generated XML column.</span></span> <span data-ttu-id="668c2-161">Wenn Sie versuchen, diese Attribute in einer benutzerdefinierten XML-Anweisung als Eingabe für einen INSERT- oder UPDATE-Vorgang für einen Spaltensatz bereitzustellen, sind einige dieser Attribute obligatorisch, und anderen wird ein Standardwert zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="668c2-161">If you try to provide these attributes in a custom-generated XML statement as an input for an insert or update operation on a column set, some of these attributes are required and some of them are assigned a default value.</span></span> <span data-ttu-id="668c2-162">In der folgenden Tabelle sind die Datentypen und die Standardwerte aufgeführt, die vom Server generiert werden, wenn der Wert nicht angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="668c2-162">The following table lists the data types and the default values that the server generates when the value is not provided.</span></span>  
  
|<span data-ttu-id="668c2-163">Datentyp</span><span class="sxs-lookup"><span data-stu-id="668c2-163">Data type</span></span>|<span data-ttu-id="668c2-164">localeID\*</span><span class="sxs-lookup"><span data-stu-id="668c2-164">localeID\*</span></span>|<span data-ttu-id="668c2-165">sqlCompareOptions</span><span class="sxs-lookup"><span data-stu-id="668c2-165">sqlCompareOptions</span></span>|<span data-ttu-id="668c2-166">sqlCollationVersion</span><span class="sxs-lookup"><span data-stu-id="668c2-166">sqlCollationVersion</span></span>|<span data-ttu-id="668c2-167">SqlSortId</span><span class="sxs-lookup"><span data-stu-id="668c2-167">SqlSortId</span></span>|<span data-ttu-id="668c2-168">Maximale Länge</span><span class="sxs-lookup"><span data-stu-id="668c2-168">Maximum length</span></span>|<span data-ttu-id="668c2-169">Precision</span><span class="sxs-lookup"><span data-stu-id="668c2-169">Precision</span></span>|<span data-ttu-id="668c2-170">Skalieren</span><span class="sxs-lookup"><span data-stu-id="668c2-170">Scale</span></span>|  
|---------------|----------------|-----------------------|-------------------------|---------------|--------------------|---------------|-----------|  
|<span data-ttu-id="668c2-171">`char`, `varchar`, `binary`</span><span class="sxs-lookup"><span data-stu-id="668c2-171">`char`, `varchar`, `binary`</span></span>|<span data-ttu-id="668c2-172">-1</span><span class="sxs-lookup"><span data-stu-id="668c2-172">-1</span></span>|<span data-ttu-id="668c2-173">'Standardwert'</span><span class="sxs-lookup"><span data-stu-id="668c2-173">'Default'</span></span>|<span data-ttu-id="668c2-174">0</span><span class="sxs-lookup"><span data-stu-id="668c2-174">0</span></span>|<span data-ttu-id="668c2-175">0</span><span class="sxs-lookup"><span data-stu-id="668c2-175">0</span></span>|<span data-ttu-id="668c2-176">8\.000</span><span class="sxs-lookup"><span data-stu-id="668c2-176">8000</span></span>|<span data-ttu-id="668c2-177">Nicht zutreffend\*\*</span><span class="sxs-lookup"><span data-stu-id="668c2-177">Not applicable\*\*</span></span>|<span data-ttu-id="668c2-178">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="668c2-178">Not applicable</span></span>|  
|`nvarchar`|<span data-ttu-id="668c2-179">-1</span><span class="sxs-lookup"><span data-stu-id="668c2-179">-1</span></span>|<span data-ttu-id="668c2-180">'Standardwert'</span><span class="sxs-lookup"><span data-stu-id="668c2-180">'Default'</span></span>|<span data-ttu-id="668c2-181">0</span><span class="sxs-lookup"><span data-stu-id="668c2-181">0</span></span>|<span data-ttu-id="668c2-182">0</span><span class="sxs-lookup"><span data-stu-id="668c2-182">0</span></span>|<span data-ttu-id="668c2-183">4000</span><span class="sxs-lookup"><span data-stu-id="668c2-183">4000</span></span>|<span data-ttu-id="668c2-184">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="668c2-184">Not applicable</span></span>|<span data-ttu-id="668c2-185">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="668c2-185">Not applicable</span></span>|  
|<span data-ttu-id="668c2-186">`decimal`, `float`, `real`</span><span class="sxs-lookup"><span data-stu-id="668c2-186">`decimal`, `float`, `real`</span></span>|<span data-ttu-id="668c2-187">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="668c2-187">Not applicable</span></span>|<span data-ttu-id="668c2-188">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="668c2-188">Not applicable</span></span>|<span data-ttu-id="668c2-189">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="668c2-189">Not applicable</span></span>|<span data-ttu-id="668c2-190">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="668c2-190">Not applicable</span></span>|<span data-ttu-id="668c2-191">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="668c2-191">Not applicable</span></span>|<span data-ttu-id="668c2-192">18</span><span class="sxs-lookup"><span data-stu-id="668c2-192">18</span></span>|<span data-ttu-id="668c2-193">0</span><span class="sxs-lookup"><span data-stu-id="668c2-193">0</span></span>|  
|<span data-ttu-id="668c2-194">`integer`, `bigint`, `tinyint`, `smallint`</span><span class="sxs-lookup"><span data-stu-id="668c2-194">`integer`, `bigint`, `tinyint`, `smallint`</span></span>|<span data-ttu-id="668c2-195">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="668c2-195">Not applicable</span></span>|<span data-ttu-id="668c2-196">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="668c2-196">Not applicable</span></span>|<span data-ttu-id="668c2-197">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="668c2-197">Not applicable</span></span>|<span data-ttu-id="668c2-198">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="668c2-198">Not applicable</span></span>|<span data-ttu-id="668c2-199">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="668c2-199">Not applicable</span></span>|<span data-ttu-id="668c2-200">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="668c2-200">Not applicable</span></span>|<span data-ttu-id="668c2-201">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="668c2-201">Not applicable</span></span>|  
|`datetime2`|<span data-ttu-id="668c2-202">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="668c2-202">Not applicable</span></span>|<span data-ttu-id="668c2-203">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="668c2-203">Not applicable</span></span>|<span data-ttu-id="668c2-204">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="668c2-204">Not applicable</span></span>|<span data-ttu-id="668c2-205">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="668c2-205">Not applicable</span></span>|<span data-ttu-id="668c2-206">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="668c2-206">Not applicable</span></span>|<span data-ttu-id="668c2-207">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="668c2-207">Not applicable</span></span>|<span data-ttu-id="668c2-208">7</span><span class="sxs-lookup"><span data-stu-id="668c2-208">7</span></span>|  
|`datetime offset`|<span data-ttu-id="668c2-209">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="668c2-209">Not applicable</span></span>|<span data-ttu-id="668c2-210">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="668c2-210">Not applicable</span></span>|<span data-ttu-id="668c2-211">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="668c2-211">Not applicable</span></span>|<span data-ttu-id="668c2-212">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="668c2-212">Not applicable</span></span>|<span data-ttu-id="668c2-213">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="668c2-213">Not applicable</span></span>|<span data-ttu-id="668c2-214">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="668c2-214">Not applicable</span></span>|<span data-ttu-id="668c2-215">7</span><span class="sxs-lookup"><span data-stu-id="668c2-215">7</span></span>|  
|<span data-ttu-id="668c2-216">`datetime`, `date`, `smalldatetime`</span><span class="sxs-lookup"><span data-stu-id="668c2-216">`datetime`, `date`, `smalldatetime`</span></span>|<span data-ttu-id="668c2-217">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="668c2-217">Not applicable</span></span>|<span data-ttu-id="668c2-218">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="668c2-218">Not applicable</span></span>|<span data-ttu-id="668c2-219">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="668c2-219">Not applicable</span></span>|<span data-ttu-id="668c2-220">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="668c2-220">Not applicable</span></span>|<span data-ttu-id="668c2-221">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="668c2-221">Not applicable</span></span>|<span data-ttu-id="668c2-222">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="668c2-222">Not applicable</span></span>|<span data-ttu-id="668c2-223">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="668c2-223">Not applicable</span></span>|  
|<span data-ttu-id="668c2-224">`money`, `smallmoney`</span><span class="sxs-lookup"><span data-stu-id="668c2-224">`money`, `smallmoney`</span></span>|<span data-ttu-id="668c2-225">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="668c2-225">Not applicable</span></span>|<span data-ttu-id="668c2-226">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="668c2-226">Not applicable</span></span>|<span data-ttu-id="668c2-227">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="668c2-227">Not applicable</span></span>|<span data-ttu-id="668c2-228">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="668c2-228">Not applicable</span></span>|<span data-ttu-id="668c2-229">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="668c2-229">Not applicable</span></span>|<span data-ttu-id="668c2-230">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="668c2-230">Not applicable</span></span>|<span data-ttu-id="668c2-231">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="668c2-231">Not applicable</span></span>|  
|`time`|<span data-ttu-id="668c2-232">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="668c2-232">Not applicable</span></span>|<span data-ttu-id="668c2-233">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="668c2-233">Not applicable</span></span>|<span data-ttu-id="668c2-234">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="668c2-234">Not applicable</span></span>|<span data-ttu-id="668c2-235">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="668c2-235">Not applicable</span></span>|<span data-ttu-id="668c2-236">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="668c2-236">Not applicable</span></span>|<span data-ttu-id="668c2-237">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="668c2-237">Not applicable</span></span>|<span data-ttu-id="668c2-238">7</span><span class="sxs-lookup"><span data-stu-id="668c2-238">7</span></span>|  
  
 <span data-ttu-id="668c2-239">\*  „localeID -1“ ist das Standardgebietsschema.</span><span class="sxs-lookup"><span data-stu-id="668c2-239">\*  localeID -1 means the default locale.</span></span> <span data-ttu-id="668c2-240">Das englischsprachige Gebietsschema ist 1033.</span><span class="sxs-lookup"><span data-stu-id="668c2-240">The English locale is 1033.</span></span>  
  
 <span data-ttu-id="668c2-241">\*\*  Nicht zutreffend = Bei einem SELECT-Vorgang für den Spaltensatz werden für diese Attribute keine Werte ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="668c2-241">\*\*  Not applicable = No values are output for these attributes during a select operation on the column set.</span></span> <span data-ttu-id="668c2-242">Gibt eine Fehlermeldung zurück, wenn für dieses Attribut von dem Aufrufer in der für einen Spaltensatz in einem INSERT- oder UPDATE-Vorgang bereitgestellten XML-Darstellung ein Wert angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="668c2-242">Generates an error when a value is specified for this attribute by the caller in the XML representation provided for a column set in an insert or update operation.</span></span>  
  
## <a name="security"></a><span data-ttu-id="668c2-243">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="668c2-243">Security</span></span>  
 <span data-ttu-id="668c2-244">Das Sicherheitsmodell für Spaltensätze funktioniert ähnlich wie das Sicherheitsmodell zwischen Tabellen und Spalten.</span><span class="sxs-lookup"><span data-stu-id="668c2-244">The security model for a column set works similar to the security model that exists between table and columns.</span></span> <span data-ttu-id="668c2-245">Spaltensätze können als Minitabellen visualisiert werden, und die SELECT-Vorgänge entsprechen den SELECT \*-Vorgängen für diese Minitabellen.</span><span class="sxs-lookup"><span data-stu-id="668c2-245">Column sets can be visualized as a minitable and a select operation is like a SELECT \* operation on this minitable.</span></span> <span data-ttu-id="668c2-246">Bei der Beziehung zwischen Spaltensatz und Sparsespalten handelt es sich jedoch nicht um einen Container, sondern um eine Gruppenbeziehung.</span><span class="sxs-lookup"><span data-stu-id="668c2-246">But, the relationship between column set to sparse columns is a grouping relationship instead of strictly a container.</span></span> <span data-ttu-id="668c2-247">Das Sicherheitsmodell prüft die Sicherheit der Spaltensatz-Spalte, wobei die DENY-Vorgänge für die zugrunde liegenden Sparsespalten berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="668c2-247">The security model checks the security on the column set column, and honors the DENY operations on the underlying sparse columns.</span></span> <span data-ttu-id="668c2-248">Für das Sicherheitsmodell gelten die folgenden zusätzlichen Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="668c2-248">Additional characteristics of the security model are as follows:</span></span>  
  
-   <span data-ttu-id="668c2-249">Wie bei anderen Spalten in der Tabelle können Sicherheitsberechtigungen für den Spaltensatz erteilt und aufgehoben werden.</span><span class="sxs-lookup"><span data-stu-id="668c2-249">Security permissions can be granted and revoked from the column set column, similar to any other column in the table.</span></span>  
  
-   <span data-ttu-id="668c2-250">Der GRANT- bzw. REVOKE-Vorgang für SELECT-, INSERT-, UPDATE-, DELETE- und REFERENCES-Berechtigungen für einen Spaltensatz wirkt sich nicht auf die zugrunde liegenden Spalten aus.</span><span class="sxs-lookup"><span data-stu-id="668c2-250">A GRANT or REVOKE of SELECT, INSERT, UPDATE, DELETE, and REFERENCES permission on a column set column does not propagate to the underlying member columns of that set.</span></span> <span data-ttu-id="668c2-251">Dieser Vorgang gilt nur für die Verwendung der Spaltensatz-Spalte.</span><span class="sxs-lookup"><span data-stu-id="668c2-251">It applies only to the usage of the column set column.</span></span> <span data-ttu-id="668c2-252">Die DENY-Berechtigung für einen Spaltensatz gilt jedoch auch für die zugrunde liegenden Sparsespalten.</span><span class="sxs-lookup"><span data-stu-id="668c2-252">DENY permission on a column set does propagate to the underlying sparse columns of the table.</span></span>  
  
-   <span data-ttu-id="668c2-253">Zur Ausführung von SELECT-, INSERT-, UPDATE- und DELETE-Anweisungen für den Spaltensatz muss der Benutzer über die entsprechenden Berechtigungen für den Spaltensatz und über die entsprechenden Berechtigungen für alle Sparsespalten in der Tabelle verfügen.</span><span class="sxs-lookup"><span data-stu-id="668c2-253">Executing SELECT, INSERT, UPDATE, and DELETE statements on the column set column require that the user has corresponding permissions on the column set column, and also the corresponding permission on all the sparse columns in the table.</span></span> <span data-ttu-id="668c2-254">Da der Spaltensatz alle Sparsespalten in der Tabelle darstellt, müssen Sie über Berechtigungen für alle diese Spalten verfügen, einschließlich Spalten, die Sie nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="668c2-254">Because the column set represents all the sparse columns in the table, you must have permission on all the sparse columns, and this includes sparse columns that you might not be changing.</span></span>  
  
-   <span data-ttu-id="668c2-255">Durch die Ausführung einer REVOKE-Anweisung für eine Sparsespalte bzw. einen Spaltensatz wird die Sicherheitseinstellung auf die Einstellung des übergeordneten Objekts zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="668c2-255">Executing a REVOKE statement on a sparse column or column set defaults the security to their parent object.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="668c2-256">Beispiele</span><span class="sxs-lookup"><span data-stu-id="668c2-256">Examples</span></span>  
 <span data-ttu-id="668c2-257">In den folgenden Beispielen enthält eine Dokumenttabelle die gemeinsamen Spalten `DocID` und `Title`.</span><span class="sxs-lookup"><span data-stu-id="668c2-257">In the following examples, a document table contains the common set of columns `DocID` and `Title`.</span></span> <span data-ttu-id="668c2-258">Die Produktionsgruppe möchte eine `ProductionSpecification` -Spalte und eine `ProductionLocation` -Spalte für alle Produktionsdokumente.</span><span class="sxs-lookup"><span data-stu-id="668c2-258">The Production group wants a `ProductionSpecification` and `ProductionLocation` column for all production documents.</span></span> <span data-ttu-id="668c2-259">Die Marketinggruppe möchte eine `MarketingSurveyGroup` -Spalte für Marketingdokumente.</span><span class="sxs-lookup"><span data-stu-id="668c2-259">The Marketing group wants a `MarketingSurveyGroup` column for marketing documents.</span></span>  
  
### <a name="a-creating-a-table-that-has-a-column-set"></a><span data-ttu-id="668c2-260">A.</span><span class="sxs-lookup"><span data-stu-id="668c2-260">A.</span></span> <span data-ttu-id="668c2-261">Erstellen einer Tabelle mit einem Spaltensatz</span><span class="sxs-lookup"><span data-stu-id="668c2-261">Creating a table that has a column set</span></span>  
 <span data-ttu-id="668c2-262">Im folgenden Beispiel wird eine Tabelle erstellt, die Sparsespalten und den Spaltensatz `SpecialPurposeColumns` enthält.</span><span class="sxs-lookup"><span data-stu-id="668c2-262">The following example creates the table that uses sparse columns and includes the column set `SpecialPurposeColumns`.</span></span> <span data-ttu-id="668c2-263">Im Beispiel werden zwei Zeilen in die Tabelle eingefügt, und anschließend werden Daten aus der Tabelle ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="668c2-263">The example inserts two rows into the table, and then selects data from the table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="668c2-264">Diese Tabelle hat nur fünf Spalten, um die Anzeige und das Lesen zu erleichtern.</span><span class="sxs-lookup"><span data-stu-id="668c2-264">This table has only five columns to make it easier to display and read.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
  
CREATE TABLE DocumentStoreWithColumnSet  
    (DocID int PRIMARY KEY,  
     Title varchar(200) NOT NULL,  
     ProductionSpecification varchar(20) SPARSE NULL,  
     ProductionLocation smallint SPARSE NULL,  
     MarketingSurveyGroup varchar(20) SPARSE NULL,  
     MarketingProgramID int SPARSE NULL,  
     SpecialPurposeColumns XML COLUMN_SET FOR ALL_SPARSE_COLUMNS);  
GO  
```  
  
### <a name="b-inserting-data-to-a-table-by-using-the-names-of-the-sparse-columns"></a><span data-ttu-id="668c2-265">B.</span><span class="sxs-lookup"><span data-stu-id="668c2-265">B.</span></span> <span data-ttu-id="668c2-266">Einfügen von Daten in eine Tabelle anhand der Namen der Sparsespalten</span><span class="sxs-lookup"><span data-stu-id="668c2-266">Inserting data to a table by using the names of the sparse columns</span></span>  
 <span data-ttu-id="668c2-267">In den folgenden Beispielen werden zwei Zeilen in die in Beispiel A erstellte Tabelle eingefügt. Hierzu werden die Namen der Sparsespalten verwendet, und auf den Spaltensatz wird nicht verwiesen.</span><span class="sxs-lookup"><span data-stu-id="668c2-267">The following examples insert two rows into the table that is created in example A. The examples use the names of the sparse columns and do not reference the column set.</span></span>  
  
```  
INSERT DocumentStoreWithColumnSet (DocID, Title, ProductionSpecification, ProductionLocation)  
VALUES (1, 'Tire Spec 1', 'AXZZ217', 27);  
GO  
  
INSERT DocumentStoreWithColumnSet (DocID, Title, MarketingSurveyGroup)  
VALUES (2, 'Survey 2142', 'Men 25 - 35');  
GO  
```  
  
### <a name="c-inserting-data-to-a-table-by-using-the-name-of-the-column-set"></a><span data-ttu-id="668c2-268">C.</span><span class="sxs-lookup"><span data-stu-id="668c2-268">C.</span></span> <span data-ttu-id="668c2-269">Einfügen von Daten in eine Tabelle anhand des Spaltensatznamens</span><span class="sxs-lookup"><span data-stu-id="668c2-269">Inserting data to a table by using the name of the column set</span></span>  
 <span data-ttu-id="668c2-270">Im folgenden Beispiel wird eine dritte Zeile in die in Beispiel A erstellte Tabelle eingefügt. Diesmal werden die Namen der Sparsespalten nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="668c2-270">The following example inserts a third row into the table that is created in example A. This time the names of the sparse columns are not used.</span></span> <span data-ttu-id="668c2-271">Stattdessen wird der Name des Spaltensatzes verwendet, und der INSERT-Vorgang gibt die Werte für zwei der vier Sparsespalten im XML-Format zurück.</span><span class="sxs-lookup"><span data-stu-id="668c2-271">Instead, the name of the column set is used, and the insert provides the values for two of the four sparse columns in XML format.</span></span>  
  
```  
INSERT DocumentStoreWithColumnSet (DocID, Title, SpecialPurposeColumns)  
VALUES (3, 'Tire Spec 2', '<ProductionSpecification>AXW9R411</ProductionSpecification><ProductionLocation>38</ProductionLocation>');  
GO  
```  
  
### <a name="d-observing-the-results-of-a-column-set-when-select--is-used"></a><span data-ttu-id="668c2-272">D:</span><span class="sxs-lookup"><span data-stu-id="668c2-272">D.</span></span> <span data-ttu-id="668c2-273">Prüfen der Ergebnisse eines Spaltensatzes bei Verwendung von SELECT \*</span><span class="sxs-lookup"><span data-stu-id="668c2-273">Observing the results of a column set when SELECT \* is used</span></span>  
 <span data-ttu-id="668c2-274">Im folgenden Beispiel werden alle Spalten der Tabelle ausgewählt, die einen Spaltensatz enthält.</span><span class="sxs-lookup"><span data-stu-id="668c2-274">The following example selects all the columns from the table that contains a column set.</span></span> <span data-ttu-id="668c2-275">Es wird eine XML-Spalte mit den kombinierten Werten der Sparsespalten zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="668c2-275">It returns an XML column with the combined values of the sparse columns.</span></span> <span data-ttu-id="668c2-276">Die Sparsespalten werden nicht einzeln zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="668c2-276">It does not return the sparse columns individually.</span></span>  
  
```  
SELECT DocID, Title, SpecialPurposeColumns FROM DocumentStoreWithColumnSet ;  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `DocID Title        SpecialPurposeColumns`  
  
 `1      Tire Spec 1  <ProductionSpecification>AXZZ217</ProductionSpecification><ProductionLocation>27</ProductionLocation>`  
  
 `2      Survey 2142  <MarketingSurveyGroup>Men 25 - 35</MarketingSurveyGroup>`  
  
 `3      Tire Spec 2  <ProductionSpecification>AXW9R411</ProductionSpecification><ProductionLocation>38</ProductionLocation>`  
  
### <a name="e-observing-the-results-of-selecting-the-column-set-by-name"></a><span data-ttu-id="668c2-277">E.</span><span class="sxs-lookup"><span data-stu-id="668c2-277">E.</span></span> <span data-ttu-id="668c2-278">Prüfen der Ergebnisse der Auswahl des Spaltensatzes nach Name</span><span class="sxs-lookup"><span data-stu-id="668c2-278">Observing the results of selecting the column set by name</span></span>  
 <span data-ttu-id="668c2-279">Da die Produktionsabteilung nicht an den Marketingdaten interessiert ist, wird in diesem Beispiel eine `WHERE` -Klausel zur Einschränkung der Ausgabe hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="668c2-279">Because the Production department is not interested in the marketing data, this example adds a `WHERE` clause to restrict the output.</span></span> <span data-ttu-id="668c2-280">In diesem Beispiel wird der Name des Spaltensatzes verwendet.</span><span class="sxs-lookup"><span data-stu-id="668c2-280">The example uses the name of the column set.</span></span>  
  
```  
SELECT DocID, Title, SpecialPurposeColumns  
FROM DocumentStoreWithColumnSet  
WHERE ProductionSpecification IS NOT NULL ;  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `DocID Title        SpecialPurposeColumns`  
  
 `1     Tire Spec 1  <ProductionSpecification>AXZZ217</ProductionSpecification><ProductionLocation>27</ProductionLocation>`  
  
 `3     Tire Spec 2  <ProductionSpecification>AXW9R411</ProductionSpecification><ProductionLocation>38</ProductionLocation>`  
  
### <a name="f-observing-the-results-of-selecting-sparse-columns-by-name"></a><span data-ttu-id="668c2-281">F.</span><span class="sxs-lookup"><span data-stu-id="668c2-281">F.</span></span> <span data-ttu-id="668c2-282">Prüfen der Ergebnisse der Auswahl von Sparsespalten nach Name</span><span class="sxs-lookup"><span data-stu-id="668c2-282">Observing the results of selecting sparse columns by name</span></span>  
 <span data-ttu-id="668c2-283">Auch wenn eine Tabelle einen Spaltensatz enthält, können Sie eine Abfrage anhand der einzelnen Spaltennamen durchführen, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="668c2-283">When a table contains a column set, you can still query the table by using the individual column names as shown in the following example.</span></span>  
  
```  
SELECT DocID, Title, ProductionSpecification, ProductionLocation   
FROM DocumentStoreWithColumnSet  
WHERE ProductionSpecification IS NOT NULL ;  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `DocID Title        ProductionSpecification ProductionLocation`  
  
 `1     Tire Spec 1  AXZZ217                 27`  
  
 `3     Tire Spec 2  AXW9R411                38`  
  
### <a name="g-updating-a-table-by-using-a-column-set"></a><span data-ttu-id="668c2-284">G.</span><span class="sxs-lookup"><span data-stu-id="668c2-284">G.</span></span> <span data-ttu-id="668c2-285">Aktualisieren einer Tabelle mithilfe eines Spaltensatzes</span><span class="sxs-lookup"><span data-stu-id="668c2-285">Updating a table by using a column set</span></span>  
 <span data-ttu-id="668c2-286">Im folgenden Beispiel wird der dritte Datensatz mit neuen Werten für beide Sparsespalten aktualisiert, die von der Zeile verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="668c2-286">The following example updates the third record with new values for both sparse columns that are used by that row.</span></span>  
  
```  
UPDATE DocumentStoreWithColumnSet  
SET SpecialPurposeColumns = '<ProductionSpecification>ZZ285W</ProductionSpecification><ProductionLocation>38</ProductionLocation>'  
WHERE DocID = 3 ;  
GO  
```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="668c2-287">Mit einer UPDATE-Anweisung, die einen Spaltensatz verwendet, werden alle Sparsespalten in der Tabelle aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="668c2-287">An UPDATE statement that uses a column set updates all the sparse columns in the table.</span></span> <span data-ttu-id="668c2-288">Spalten mit geringer Dichte, auf die nicht verwiesen wird, werden auf NULL festgelegt.</span><span class="sxs-lookup"><span data-stu-id="668c2-288">Sparse columns that are not referenced are updated to NULL.</span></span>  
  
 <span data-ttu-id="668c2-289">Im folgenden Beispiel wird der dritte Datensatz aktualisiert, es wird jedoch nur der Wert für eine der beiden Spalten mit Werten angegeben.</span><span class="sxs-lookup"><span data-stu-id="668c2-289">The following example updates the third record, but only specifies the value of one of the two populated columns.</span></span> <span data-ttu-id="668c2-290">Die zweite Spalte `ProductionLocation` ist nicht in der `UPDATE` -Anweisung enthalten und wird auf NULL aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="668c2-290">The second column `ProductionLocation` is not included in the `UPDATE` statement and is updated to NULL.</span></span>  
  
```  
UPDATE DocumentStoreWithColumnSet  
SET SpecialPurposeColumns = '<ProductionSpecification>ZZ285W</ProductionSpecification>'  
WHERE DocID = 3 ;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="668c2-291">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="668c2-291">See Also</span></span>  
 [<span data-ttu-id="668c2-292">Verwenden von Spalten mit geringer Dichte</span><span class="sxs-lookup"><span data-stu-id="668c2-292">Use Sparse Columns</span></span>](use-sparse-columns.md)  
  
  
