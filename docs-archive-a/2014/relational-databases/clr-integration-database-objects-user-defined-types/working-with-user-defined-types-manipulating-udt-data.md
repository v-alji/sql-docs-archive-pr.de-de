---
title: Bearbeiten von UDT-Daten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- TSQL
helpviewer_keywords:
- CAST function
- data deletions [CLR integration]
- data insertions [CLR integration]
- CONVERT function
- data updates [CLR integration]
- comparing data
- updating data [CLR integration]
- removing data
- IsByteOrdered property
- variables [CLR integration]
- data manipulation [CLR integration]
- user-defined types [CLR integration], data manipulation
- deleting data
- UDTs [CLR integration], data manipulation
- invoking UDT methods
- inserting data
ms.assetid: 51b1a5f2-7591-4e11-bfe2-d88e0836403f
author: rothja
ms.author: jroth
ms.openlocfilehash: 75810a2ffd92130e45025f742d43ba7917d73992
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698307"
---
# <a name="manipulating-udt-data"></a><span data-ttu-id="41dc9-102">Bearbeiten von UDT-Daten</span><span class="sxs-lookup"><span data-stu-id="41dc9-102">Manipulating UDT Data</span></span>
  [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="41dc9-103">stellt keine spezialisierte Syntax für INSERT-, UPDATE- oder DELETE-Anweisungen zum Ändern von Daten in Spalten vom benutzerdefinierten Typ (User-defined Type, UDT) bereit.</span><span class="sxs-lookup"><span data-stu-id="41dc9-103">provides no specialized syntax for INSERT, UPDATE, or DELETE statements when modifying data in user-defined type (UDT) columns.</span></span> <span data-ttu-id="41dc9-104">Die [!INCLUDE[tsql](../../includes/tsql-md.md)]-Funktionen CAST oder CONVERT werden verwendet, um systemeigene Datentypen in den benutzerdefinierten Typ (UDT) umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="41dc9-104">The [!INCLUDE[tsql](../../includes/tsql-md.md)] CAST or CONVERT functions are used to cast native data types to the UDT type.</span></span>  
  
## <a name="inserting-data-in-a-udt-column"></a><span data-ttu-id="41dc9-105">Einfügen von Daten in eine UDT-Spalte</span><span class="sxs-lookup"><span data-stu-id="41dc9-105">Inserting Data in a UDT Column</span></span>  
 <span data-ttu-id="41dc9-106">Die folgenden [!INCLUDE[tsql](../../includes/tsql-md.md)] Anweisungen fügen drei Zeilen mit Beispiel Daten in die **Points** -Tabelle ein.</span><span class="sxs-lookup"><span data-stu-id="41dc9-106">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements insert three rows of sample data into the **Points** table.</span></span> <span data-ttu-id="41dc9-107">Der **Point** -Datentyp besteht aus X-und Y-ganzzahligen Werten, die als Eigenschaften des UDT verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="41dc9-107">The **Point** data type consists of X and Y integer values that are exposed as properties of the UDT.</span></span> <span data-ttu-id="41dc9-108">Sie müssen entweder die CAST-oder die Convert-Funktion verwenden, um die durch Kommas getrennten X-und Y-Werte in den **Punkttyp** umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="41dc9-108">You must use either the CAST or CONVERT function to cast the comma-delimited X and Y values to the **Point** type.</span></span> <span data-ttu-id="41dc9-109">Die ersten beiden Anweisungen verwenden die Convert-Funktion, um einen Zeichen folgen Wert in den **Punkttyp** zu konvertieren, und die dritte Anweisung verwendet die CAST-Funktion:</span><span class="sxs-lookup"><span data-stu-id="41dc9-109">The first two statements use the CONVERT function to convert a string value to the **Point** type, and the third statement uses the CAST function:</span></span>  
  
```  
INSERT INTO dbo.Points (PointValue) VALUES (CONVERT(Point, '3,4'));  
INSERT INTO dbo.Points (PointValue) VALUES (CONVERT(Point, '1,5'));  
INSERT INTO dbo.Points (PointValue) VALUES (CAST ('1,99' AS Point));  
```  
  
## <a name="selecting-data"></a><span data-ttu-id="41dc9-110">Auswählen von Daten</span><span class="sxs-lookup"><span data-stu-id="41dc9-110">Selecting Data</span></span>  
 <span data-ttu-id="41dc9-111">Die folgende SELECT-Anweisung wählt den Binärwert des UDTs aus.</span><span class="sxs-lookup"><span data-stu-id="41dc9-111">The following SELECT statement selects the binary value of the UDT.</span></span>  
  
```  
SELECT ID, PointValue FROM dbo.Points  
```  
  
 <span data-ttu-id="41dc9-112">Um die Ausgabe in einem lesbaren Format anzuzeigen, müssen Sie die- `ToString` Methode des **Point** -UDT aufzurufen, die den Wert in seine Zeichen folgen Darstellung konvertiert.</span><span class="sxs-lookup"><span data-stu-id="41dc9-112">To see the output displayed in a readable format, call the `ToString` method of the **Point** UDT, which converts the value to its string representation.</span></span>  
  
```  
SELECT ID, PointValue.ToString() AS PointValue   
FROM dbo.Points;  
```  
  
 <span data-ttu-id="41dc9-113">Hierdurch werden folgende Ergebnisse erzielt.</span><span class="sxs-lookup"><span data-stu-id="41dc9-113">This produces the following results.</span></span>  
  
```  
IDPointValue  
----------  
13,4  
21,5  
31,99  
```  
  
 <span data-ttu-id="41dc9-114">Sie können auch die [!INCLUDE[tsql](../../includes/tsql-md.md)]-Funktionen CAST und CONVERT verwenden, um dieselben Ergebnisse zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="41dc9-114">You can also use the [!INCLUDE[tsql](../../includes/tsql-md.md)] CAST and CONVERT functions to achieve the same results.</span></span>  
  
```  
SELECT ID, CAST(PointValue AS varchar)   
FROM dbo.Points;  
  
SELECT ID, CONVERT(varchar, PointValue)   
FROM dbo.Points;  
```  
  
 <span data-ttu-id="41dc9-115">Der **Point** -UDT macht seine X-und Y-Koordinaten als Eigenschaften verfügbar, die Sie dann einzeln auswählen können.</span><span class="sxs-lookup"><span data-stu-id="41dc9-115">The **Point** UDT exposes its X and Y coordinates as properties, which you can then select individually.</span></span> <span data-ttu-id="41dc9-116">Die folgende [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisung wählt die X- und die Y-Koordinate getrennt aus:</span><span class="sxs-lookup"><span data-stu-id="41dc9-116">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement selects the X and Y coordinates separately:</span></span>  
  
```  
SELECT ID, PointValue.X AS xVal, PointValue.Y AS yVal   
FROM dbo.Points;  
```  
  
 <span data-ttu-id="41dc9-117">Die X-Eigenschaft und die Y-Eigenschaft geben einen ganzzahligen Wert zurück, der im Resultset angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="41dc9-117">The X and Y properties return an integer value, which is displayed in the result set.</span></span>  
  
```  
IDxValyVal  
----------  
134  
215  
3199  
```  
  
## <a name="working-with-variables"></a><span data-ttu-id="41dc9-118">Arbeiten mit Variablen</span><span class="sxs-lookup"><span data-stu-id="41dc9-118">Working with Variables</span></span>  
 <span data-ttu-id="41dc9-119">Sie können mit Variablen arbeiten, indem Sie die DECLARE-Anweisung verwenden, um einem UDT eine Variable zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="41dc9-119">You can work with variables using the DECLARE statement to assign a variable to a UDT type.</span></span> <span data-ttu-id="41dc9-120">In den folgenden Anweisungen werden mithilfe der [!INCLUDE[tsql](../../includes/tsql-md.md)]-SET-Anweisung einem UDT ein Wert zugewiesen und durch den Aufruf der `ToString`-Methode des UDTs für die Variable die Ergebnisse angezeigt:</span><span class="sxs-lookup"><span data-stu-id="41dc9-120">The following statements assign a value using the [!INCLUDE[tsql](../../includes/tsql-md.md)] SET statement and display the results by calling the UDT's `ToString` method on the variable:</span></span>  
  
```  
DECLARE @PointValue Point;  
SET @PointValue = (SELECT PointValue FROM dbo.Points  
    WHERE ID = 2);  
SELECT @PointValue.ToString() AS PointValue;  
```  
  
 <span data-ttu-id="41dc9-121">Das Resultset zeigt den Wert der Variablen an:</span><span class="sxs-lookup"><span data-stu-id="41dc9-121">The result set displays the variable value:</span></span>  
  
```  
PointValue  
----------  
-1,5  
```  
  
 <span data-ttu-id="41dc9-122">Mit den folgenden [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisungen wird dasselbe Ergebnis erzielt. Dabei wird für die Variablenzuweisung SELECT statt SET verwendet:</span><span class="sxs-lookup"><span data-stu-id="41dc9-122">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements achieve the same result using SELECT rather than SET for the variable assignment:</span></span>  
  
```  
DECLARE @PointValue Point;  
SELECT @PointValue = PointValue FROM dbo.Points  
    WHERE ID = 2;  
SELECT @PointValue.ToString() AS PointValue;  
```  
  
 <span data-ttu-id="41dc9-123">Der Unterschied zwischen der Verwendung von SELECT statt SET für die Variablenzuweisung besteht darin, dass SELECT ermöglicht, mehrere Variable in einer SELECT-Anweisung zuzuweisen, während die SET-Syntax erfordert, dass jede Variable durch eine eigene SET-Anweisung zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="41dc9-123">The difference between using SELECT and SET for variable assignment is that SELECT allows you to assign multiple variables in one SELECT statement, whereas the SET syntax requires each variable assignment to have its own SET statement.</span></span>  
  
## <a name="comparing-data"></a><span data-ttu-id="41dc9-124">Vergleichen von Daten</span><span class="sxs-lookup"><span data-stu-id="41dc9-124">Comparing Data</span></span>  
 <span data-ttu-id="41dc9-125">Mithilfe von Vergleichoperatoren können Sie Werte in Ihrem UDT vergleichen, wenn Sie beim Definieren der Klasse für die `IsByteOrdered`-Eigenschaft `true` festlegen.</span><span class="sxs-lookup"><span data-stu-id="41dc9-125">You can use comparison operators to compare values in your UDT if you have set the `IsByteOrdered` property to `true` when defining the class.</span></span> <span data-ttu-id="41dc9-126">Weitere Informationen finden Sie unter [Erstellen eines benutzerdefinierten Typs](creating-user-defined-types.md).</span><span class="sxs-lookup"><span data-stu-id="41dc9-126">For more information, see [Creating a User-Defined Type](creating-user-defined-types.md).</span></span>  
  
```  
SELECT ID, PointValue.ToString() AS Points   
FROM dbo.Points  
WHERE PointValue > CONVERT(Point, '2,2');  
```  
  
 <span data-ttu-id="41dc9-127">Unabhängig von der `IsByteOrdered`-Einstellung können Sie interne Werte des UDTs vergleichen, wenn die Werte selbst vergleichbar sind.</span><span class="sxs-lookup"><span data-stu-id="41dc9-127">You can compare internal values of the UDT regardless of the `IsByteOrdered` setting if the values themselves are comparable.</span></span> <span data-ttu-id="41dc9-128">Die folgende [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisung wählt die Zeilen aus, in denen X größer ist als Y:</span><span class="sxs-lookup"><span data-stu-id="41dc9-128">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement selects rows where X is greater than Y:</span></span>  
  
```  
SELECT ID, PointValue.ToString() AS PointValue   
FROM dbo.Points  
WHERE PointValue.X < PointValue.Y;  
```  
  
 <span data-ttu-id="41dc9-129">Vergleichsoperatoren können auch mit Variablen verwendet werden, wie in dieser Abfrage gezeigt, in der nach einem übereinstimmenden PointValue gesucht wird.</span><span class="sxs-lookup"><span data-stu-id="41dc9-129">You can also use comparison operators with variables, as shown in this query that searches for a matching PointValue.</span></span>  
  
```  
DECLARE @ComparePoint Point;  
SET @ComparePoint = CONVERT(Point, '3,4');  
SELECT ID, PointValue.ToString() AS MatchingPoint   
FROM dbo.Points  
WHERE PointValue = @ComparePoint;  
```  
  
## <a name="invoking-udt-methods"></a><span data-ttu-id="41dc9-130">Aufrufen von UDT-Methoden</span><span class="sxs-lookup"><span data-stu-id="41dc9-130">Invoking UDT Methods</span></span>  
 <span data-ttu-id="41dc9-131">Sie können auch Methoden aufrufen, die im UDT in [!INCLUDE[tsql](../../includes/tsql-md.md)] definiert sind.</span><span class="sxs-lookup"><span data-stu-id="41dc9-131">You can also invoke methods that are defined in your UDT in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="41dc9-132">Die **Point** -Klasse enthält drei Methoden: `Distance` , `DistanceFrom` und `DistanceFromXY` .</span><span class="sxs-lookup"><span data-stu-id="41dc9-132">The **Point** class contains three methods, `Distance`, `DistanceFrom`, and `DistanceFromXY`.</span></span> <span data-ttu-id="41dc9-133">Die Code Auflistungen, die diese drei Methoden definieren, finden Sie unter [Programmieren benutzerdefinierter Typen](creating-user-defined-types-coding.md).</span><span class="sxs-lookup"><span data-stu-id="41dc9-133">For the code listings defining these three methods, see [Coding User-Defined Types](creating-user-defined-types-coding.md).</span></span>  
  
 <span data-ttu-id="41dc9-134">Die folgende [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisung ruft die `PointValue.Distance`-Methode auf:</span><span class="sxs-lookup"><span data-stu-id="41dc9-134">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement calls the `PointValue.Distance` method:</span></span>  
  
```  
SELECT ID, PointValue.X AS [Point.X],   
    PointValue.Y AS [Point.Y],  
    PointValue.Distance() AS DistanceFromZero   
FROM dbo.Points;  
```  
  
 <span data-ttu-id="41dc9-135">Die Ergebnisse werden in der `Distance` Spalte angezeigt:</span><span class="sxs-lookup"><span data-stu-id="41dc9-135">The results are displayed in the `Distance` column:</span></span>  
  
```  
IDXYDistance  
------------------------  
1345  
2155.09901951359278  
319999.0050503762308  
```  
  
 <span data-ttu-id="41dc9-136">Die `DistanceFrom` -Methode nimmt ein Argument des **Point** -Datentyps an und zeigt den Abstand zwischen dem angegebenen Punkt und dem PointValue-Wert an:</span><span class="sxs-lookup"><span data-stu-id="41dc9-136">The `DistanceFrom` method takes an argument of **Point** data type, and displays the distance from the specified point to the PointValue:</span></span>  
  
```  
SELECT ID, PointValue.ToString() AS Pnt,  
   PointValue.DistanceFrom(CONVERT(Point, '1,99')) AS DistanceFromPoint  
FROM dbo.Points;  
```  
  
 <span data-ttu-id="41dc9-137">Es werden die Ergebnisse der `DistanceFrom`-Methode für jede Zeile in der Tabelle angezeigt:</span><span class="sxs-lookup"><span data-stu-id="41dc9-137">The results display the results of the `DistanceFrom` method for each row in the table:</span></span>  
  
```  
ID PntDistanceFromPoint  
---------------------  
13,495.0210502993942  
21,594  
31,990  
```  
  
 <span data-ttu-id="41dc9-138">Die `DistanceFromXY`-Methode übernimmt die Punkte einzeln als Argumente:</span><span class="sxs-lookup"><span data-stu-id="41dc9-138">The `DistanceFromXY` method takes the points individually as arguments:</span></span>  
  
```  
SELECT ID, PointValue.X as X, PointValue.Y as Y,   
PointValue.DistanceFromXY(1, 99) AS DistanceFromXY   
FROM dbo.Points  
```  
  
 <span data-ttu-id="41dc9-139">Das Resultset ist mit dem der `DistanceFrom`-Methode identisch.</span><span class="sxs-lookup"><span data-stu-id="41dc9-139">The result set is the same as the `DistanceFrom` method.</span></span>  
  
## <a name="updating-data-in-a-udt-column"></a><span data-ttu-id="41dc9-140">Aktualisieren von Daten in einer UDT-Spalte</span><span class="sxs-lookup"><span data-stu-id="41dc9-140">Updating Data in a UDT Column</span></span>  
 <span data-ttu-id="41dc9-141">Verwenden Sie die [!INCLUDE[tsql](../../includes/tsql-md.md)]-UPDATE-Anweisung, um Daten in einer UDT-Spalte zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="41dc9-141">To update data in a UDT column, use the [!INCLUDE[tsql](../../includes/tsql-md.md)] UPDATE statement.</span></span> <span data-ttu-id="41dc9-142">Sie können auch eine Methode des UDTs verwenden, um den Status des Objekts zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="41dc9-142">You can also use a method of the UDT to update the state of the object.</span></span> <span data-ttu-id="41dc9-143">Die folgende [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisung aktualisiert eine einzelne Zeile in der Tabelle:</span><span class="sxs-lookup"><span data-stu-id="41dc9-143">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement updates a single row in the table:</span></span>  
  
```  
UPDATE dbo.Points  
SET PointValue = CAST('1,88' AS Point)  
WHERE ID = 3  
```  
  
 <span data-ttu-id="41dc9-144">Sie können auch UDT-Elemente getrennt aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="41dc9-144">You can also update UDT elements separately.</span></span> <span data-ttu-id="41dc9-145">Die folgende [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisung aktualisiert nur die Y-Koordinate:</span><span class="sxs-lookup"><span data-stu-id="41dc9-145">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement updates only the Y coordinate:</span></span>  
  
```  
UPDATE dbo.Points  
SET PointValue.Y = 99  
WHERE ID = 3  
```  
  
 <span data-ttu-id="41dc9-146">Wenn der UDT so definiert wurde, dass für die Bytesortierung `true` festgelegt wurde, kann [!INCLUDE[tsql](../../includes/tsql-md.md)] die UDT-Spalte in einer WHERE-Klausel auswerten.</span><span class="sxs-lookup"><span data-stu-id="41dc9-146">If the UDT has been defined with byte ordering set to `true`, [!INCLUDE[tsql](../../includes/tsql-md.md)] can evaluate the UDT column in a WHERE clause.</span></span>  
  
```  
UPDATE dbo.Points  
SET PointValue = '4,5'  
WHERE PointValue = '3,4';  
```  
  
### <a name="updating-limitations"></a><span data-ttu-id="41dc9-147">Einschränkungen für Updates</span><span class="sxs-lookup"><span data-stu-id="41dc9-147">Updating Limitations</span></span>  
 <span data-ttu-id="41dc9-148">Mehrere Eigenschaften können mit [!INCLUDE[tsql](../../includes/tsql-md.md)] nicht gleichzeitig aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="41dc9-148">You cannot update multiple properties at once using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="41dc9-149">Beispielsweise schlägt die folgende UPDATE-Anweisung fehl, und es wird ein Fehler ausgegeben, da Sie denselben Spaltennamen nicht zwei Mal in derselben UPDATE-Anweisung verwenden können.</span><span class="sxs-lookup"><span data-stu-id="41dc9-149">For example, the following UPDATE statement fails with an error because you cannot use the same column name twice in one UDATE statement.</span></span>  
  
```  
UPDATE dbo.Points  
SET PointValue.X = 5, PointValue.Y = 99  
WHERE ID = 3  
```  
  
 <span data-ttu-id="41dc9-150">Um jeden Punkt einzeln zu aktualisieren, müssen Sie in der Point-UDT-Assembly eine Mutatormethode erstellen.</span><span class="sxs-lookup"><span data-stu-id="41dc9-150">To update each point individually, you would need to create a mutator method in the Point UDT assembly.</span></span> <span data-ttu-id="41dc9-151">Anschließend können Sie die Mutatormethode aufrufen, um das Objekt in einer [!INCLUDE[tsql](../../includes/tsql-md.md)]-UPDATE-Anweisung zu aktualisieren, wie im Folgenden dargestellt:</span><span class="sxs-lookup"><span data-stu-id="41dc9-151">You can then invoke the mutator method to update the object in a [!INCLUDE[tsql](../../includes/tsql-md.md)] UPDATE statement, as in the following:</span></span>  
  
```  
UPDATE dbo.Points  
SET PointValue.SetXY(5, 99)  
WHERE ID = 3  
```  
  
## <a name="deleting-data-in-a-udt-column"></a><span data-ttu-id="41dc9-152">Löschen von Daten in einer UDT-Spalte</span><span class="sxs-lookup"><span data-stu-id="41dc9-152">Deleting Data in a UDT Column</span></span>  
 <span data-ttu-id="41dc9-153">Um Daten in einem UDT zu löschen, verwenden Sie die [!INCLUDE[tsql](../../includes/tsql-md.md)]-DELETE-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="41dc9-153">To delete data in a UDT, use the [!INCLUDE[tsql](../../includes/tsql-md.md)] DELETE statement.</span></span> <span data-ttu-id="41dc9-154">Die folgende Anweisung löscht alle Zeilen in der Tabelle, die den in der WHERE-Klausel angegebenen Kriterien entsprechen.</span><span class="sxs-lookup"><span data-stu-id="41dc9-154">The following statement deletes all rows in the table that match the criteria specified in the WHERE clause.</span></span> <span data-ttu-id="41dc9-155">Wenn Sie die WHERE-Klausel einer DELETE-Anweisung weglassen, werden alle Zeilen in der Tabelle gelöscht.</span><span class="sxs-lookup"><span data-stu-id="41dc9-155">If you omit the WHERE clause in a DELETE statement, all rows in the table will be deleted.</span></span>  
  
```  
DELETE FROM dbo.Points  
WHERE PointValue = CAST('1,99' AS Point)  
```  
  
 <span data-ttu-id="41dc9-156">Sollen die Werte aus einer UDT-Spalte gelöscht werden, andere Zeilenwerte jedoch intakt bleiben, verwenden Sie die UPDATE-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="41dc9-156">Use the UPDATE statement if you want to remove the values in a UDT column while leaving other row values intact.</span></span> <span data-ttu-id="41dc9-157">In diesem Beispiel wird für PointValue NULL festgelegt.</span><span class="sxs-lookup"><span data-stu-id="41dc9-157">This example sets the PointValue to null.</span></span>  
  
```  
UPDATE dbo.Points  
SET PointValue = null  
WHERE ID = 2  
```  
  
## <a name="see-also"></a><span data-ttu-id="41dc9-158">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="41dc9-158">See Also</span></span>  
 [<span data-ttu-id="41dc9-159">Arbeiten mit benutzerdefinierten Typen in SQL Server</span><span class="sxs-lookup"><span data-stu-id="41dc9-159">Working with User-Defined Types in SQL Server</span></span>](working-with-user-defined-types-in-sql-server.md)  
  
  
