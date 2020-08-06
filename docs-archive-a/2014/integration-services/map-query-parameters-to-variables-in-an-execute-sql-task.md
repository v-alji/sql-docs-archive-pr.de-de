---
title: Zuordnen von Abfrage Parametern zu Variablen in einem Task "SQL ausführen" | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- queries [Integration Services], parameter mapping
- parameterized SQL commands [Integration Services]
- parameters [Integration Services]
- mapping query parameters to variables [Integration Services]
- Execute SQL task [Integration Services]
- variables [Integration Services], mapping parameters to
ms.assetid: 6a164349-dfcf-4995-80bc-d4e7aee52a83
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8511d70b40f2934680e1cb790763045c04e8204a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617164"
---
# <a name="map-query-parameters-to-variables-in-an-execute-sql-task"></a><span data-ttu-id="e394d-102">Zuordnen von Abfrageparametern zu Variablen in einem Task SQL ausführen</span><span class="sxs-lookup"><span data-stu-id="e394d-102">Map Query Parameters to Variables in an Execute SQL Task</span></span>

  <span data-ttu-id="e394d-103">In diesem Thema wird beschrieben, wie Sie eine parametrisierte SQL-Anweisung im Task 'SQL ausführen' verwenden und wie Sie Zuordnungen zwischen Variablen und den Parametern der SQL-Anweisung erstellen.</span><span class="sxs-lookup"><span data-stu-id="e394d-103">This topic describes how to use a parameterized SQL statement in the Execute SQL task and create mappings between variables and the parameters in the SQL statement.</span></span>  
  
 <span data-ttu-id="e394d-104">Weitere Informationen zum Task SQL ausführen, zu den Parametermarkierungen und den Parameternamen, die Sie mit verschiedenen Verbindungstypen verwenden, finden Sie unter [SQL ausführen (Task)](control-flow/execute-sql-task.md) und [Parameter und Rückgabecodes im Task „SQL ausführen“](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md).</span><span class="sxs-lookup"><span data-stu-id="e394d-104">To learn more about the Execute SQL task, the parameter markers, and parameter names you use with different connection types, see [Execute SQL Task](control-flow/execute-sql-task.md) and [Parameters and Return Codes in the Execute SQL Task](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md).</span></span>  
  
### <a name="to-map-a-query-parameter-to-a-variable"></a><span data-ttu-id="e394d-105">So ordnen Sie einer Variablen einen Abfrageparameter zu</span><span class="sxs-lookup"><span data-stu-id="e394d-105">To map a query parameter to a variable</span></span>  
  
1.  <span data-ttu-id="e394d-106">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]das gewünschte [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Paket.</span><span class="sxs-lookup"><span data-stu-id="e394d-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package you want to work with.</span></span>  
  
2.  <span data-ttu-id="e394d-107">Doppelklicken Sie im Projektmappen-Explorer auf das Paket, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="e394d-107">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="e394d-108">Klicken Sie auf die Registerkarte **Ablaufsteuerung** .</span><span class="sxs-lookup"><span data-stu-id="e394d-108">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="e394d-109">Wenn das Paket noch keinen Task SQL ausführen enthält, fügen Sie der Ablaufsteuerung des Pakets einen solchen Task hinzu.</span><span class="sxs-lookup"><span data-stu-id="e394d-109">If the package does not already include an Execute SQL task, add one to the control flow of the package.</span></span> <span data-ttu-id="e394d-110">Weitere Informationen finden Sie unter [Hinzufügen oder Löschen eines Tasks oder Containers in einer Ablauf Steuerung](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md) .</span><span class="sxs-lookup"><span data-stu-id="e394d-110">For more information, see [Add or Delete a Task or a Container in a Control Flow](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md)</span></span>  
  <span data-ttu-id="e394d-111">.</span><span class="sxs-lookup"><span data-stu-id="e394d-111">.</span></span>  
  
5.  <span data-ttu-id="e394d-112">Doppelklicken Sie auf den Task SQL ausführen.</span><span class="sxs-lookup"><span data-stu-id="e394d-112">Double-click the Execute SQL task.</span></span>  
  
6.  <span data-ttu-id="e394d-113">Stellen Sie auf eine der folgenden Arten einen parametrisierten SQL-Befehl bereit:</span><span class="sxs-lookup"><span data-stu-id="e394d-113">Provide a parameterized SQL command in one of the following ways:</span></span>  
  
    -   <span data-ttu-id="e394d-114">Verwenden Sie die direkte Eingabe, und geben Sie den SQL-Befehl für die SQLStatement-Eigenschaft ein.</span><span class="sxs-lookup"><span data-stu-id="e394d-114">Use direct input and type the SQL command in the SQLStatement property.</span></span>  
  
    -   <span data-ttu-id="e394d-115">Verwenden Sie die direkte Eingabe, klicken Sie auf **Abfrage erstellen**, und erstellen Sie einen SQL-Befehl mithilfe der grafischen Tools des Abfrage-Generators.</span><span class="sxs-lookup"><span data-stu-id="e394d-115">Use direct input, click **Build Query**, and then create an SQL command using the graphical tools that the Query Builder provides.</span></span>  
  
    -   <span data-ttu-id="e394d-116">Verwenden Sie eine Dateiverbindung, und verweisen Sie auf die Datei, die den SQL-Befehl enthält.</span><span class="sxs-lookup"><span data-stu-id="e394d-116">Use a file connection and then reference the file that contains the SQL command.</span></span>  
  
    -   <span data-ttu-id="e394d-117">Verwenden Sie eine Variable, und verweisen Sie auf die Variable, die den SQL-Befehl enthält.</span><span class="sxs-lookup"><span data-stu-id="e394d-117">Use a variable and then reference the variable that contains the SQL command.</span></span>  
  
     <span data-ttu-id="e394d-118">Die in parametrisierten SQL-Anweisungen verwendeten Parametermarkierungen hängen vom Verbindungstyp ab, den der Task SQL ausführen verwendet.</span><span class="sxs-lookup"><span data-stu-id="e394d-118">The parameter markers that you use in parameterized SQL statements depend on the connection type that the Execute SQL task uses.</span></span>  
  
    |<span data-ttu-id="e394d-119">Verbindungstyp</span><span class="sxs-lookup"><span data-stu-id="e394d-119">Connection type</span></span>|<span data-ttu-id="e394d-120">Parametermarkierung</span><span class="sxs-lookup"><span data-stu-id="e394d-120">Parameter marker</span></span>|  
    |---------------------|----------------------|  
    |<span data-ttu-id="e394d-121">ADO</span><span class="sxs-lookup"><span data-stu-id="e394d-121">ADO</span></span>|<span data-ttu-id="e394d-122">?</span><span class="sxs-lookup"><span data-stu-id="e394d-122">?</span></span>|  
    |<span data-ttu-id="e394d-123">ADO.NET und SQLMOBILE</span><span class="sxs-lookup"><span data-stu-id="e394d-123">ADO.NET and SQLMOBILE</span></span>|@\<parameter name>|  
    |<span data-ttu-id="e394d-124">ODBC</span><span class="sxs-lookup"><span data-stu-id="e394d-124">ODBC</span></span>|<span data-ttu-id="e394d-125">?</span><span class="sxs-lookup"><span data-stu-id="e394d-125">?</span></span>|  
    |<span data-ttu-id="e394d-126">EXCEL und OLE DB</span><span class="sxs-lookup"><span data-stu-id="e394d-126">EXCEL and OLE DB</span></span>|<span data-ttu-id="e394d-127">?</span><span class="sxs-lookup"><span data-stu-id="e394d-127">?</span></span>|  
  
     <span data-ttu-id="e394d-128">In der folgenden Tabelle finden Sie eine Auflistung von Beispielen des SELECT-Befehls nach verschiedenen Verbindungs-Managertypen.</span><span class="sxs-lookup"><span data-stu-id="e394d-128">The following table lists examples of the SELECT command by connection manager type.</span></span> <span data-ttu-id="e394d-129">Parameter stellen die Filterwerte in den WHERE-Klauseln bereit.</span><span class="sxs-lookup"><span data-stu-id="e394d-129">Parameters provide the filter values in the WHERE clauses.</span></span> <span data-ttu-id="e394d-130">In den Beispielen wird die SELECT-Anweisung verwendet, um Produkte aus der **Product** -Tabelle in [!INCLUDE[ssSampleDBUserInputNonLocal](../includes/sssampledbuserinputnonlocal-md.md)] zurückzugeben, die eine **ProductID** aufweisen, die größer oder kleiner als die angegebenen Werte von zwei Parametern ist.</span><span class="sxs-lookup"><span data-stu-id="e394d-130">The examples use SELECT to return products from the **Product** table in [!INCLUDE[ssSampleDBUserInputNonLocal](../includes/sssampledbuserinputnonlocal-md.md)] that have a **ProductID** greater than and less than the values specified by two parameters.</span></span>  
  
    |<span data-ttu-id="e394d-131">Verbindungstyp</span><span class="sxs-lookup"><span data-stu-id="e394d-131">Connection type</span></span>|<span data-ttu-id="e394d-132">SELECT-Syntax</span><span class="sxs-lookup"><span data-stu-id="e394d-132">SELECT syntax</span></span>|  
    |---------------------|-------------------|  
    |<span data-ttu-id="e394d-133">EXCEL, ODBC und OLEDB</span><span class="sxs-lookup"><span data-stu-id="e394d-133">EXCEL, ODBC, and OLEDB</span></span>|`SELECT* FROM Production.Product WHERE ProductId > ? AND ProductID < ?`|  
    |<span data-ttu-id="e394d-134">ADO</span><span class="sxs-lookup"><span data-stu-id="e394d-134">ADO</span></span>|`SELECT* FROM Production.Product WHERE ProductId > ? AND ProductID < ?`|  
    |[!INCLUDE[vstecado](../includes/vstecado-md.md)]|`SELECT* FROM Production.Product WHERE ProductId > @parmMinProductID AND ProductID < @parmMaxProductID`|  
  
     <span data-ttu-id="e394d-135">Beispiele zum Verwenden von Parametern mit gespeicherten Prozeduren finden Sie unter [Parameters and Return Codes in the Execute SQL Task](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md).</span><span class="sxs-lookup"><span data-stu-id="e394d-135">For examples of using parameters with stored procedures, see [Parameters and Return Codes in the Execute SQL Task](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md).</span></span>  
  
7.  <span data-ttu-id="e394d-136">Klicken Sie auf **Parameterzuordnung**.</span><span class="sxs-lookup"><span data-stu-id="e394d-136">Click **Parameter Mapping**.</span></span>  
  
8.  <span data-ttu-id="e394d-137">Klicken Sie auf **Hinzufügen**, um eine Parameterzuordnung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="e394d-137">To add a parameter mapping, click **Add**.</span></span>  
  
9. <span data-ttu-id="e394d-138">Stellen Sie im Feld **Parametername** einen Namen bereit.</span><span class="sxs-lookup"><span data-stu-id="e394d-138">Provide a name in the **Parameter Name** box.</span></span>  
  
     <span data-ttu-id="e394d-139">Die verwendeten Parameternamen hängen vom Verbindungstyp ab, den der Task 'SQL ausführen' verwendet.</span><span class="sxs-lookup"><span data-stu-id="e394d-139">The parameter names that you use depend on the connection type that the Execute SQL task uses.</span></span>  
  
    |<span data-ttu-id="e394d-140">Verbindungstyp</span><span class="sxs-lookup"><span data-stu-id="e394d-140">Connection type</span></span>|<span data-ttu-id="e394d-141">Parametername</span><span class="sxs-lookup"><span data-stu-id="e394d-141">Parameter name</span></span>|  
    |---------------------|--------------------|  
    |<span data-ttu-id="e394d-142">ADO</span><span class="sxs-lookup"><span data-stu-id="e394d-142">ADO</span></span>|<span data-ttu-id="e394d-143">Param1, Param2, …</span><span class="sxs-lookup"><span data-stu-id="e394d-143">Param1, Param2, ...</span></span>|  
    |<span data-ttu-id="e394d-144">ADO.NET und SQLMOBILE</span><span class="sxs-lookup"><span data-stu-id="e394d-144">ADO.NET and SQLMOBILE</span></span>|@\<parameter name>|  
    |<span data-ttu-id="e394d-145">ODBC</span><span class="sxs-lookup"><span data-stu-id="e394d-145">ODBC</span></span>|<span data-ttu-id="e394d-146">1, 2, 3, ...</span><span class="sxs-lookup"><span data-stu-id="e394d-146">1, 2, 3, ...</span></span>|  
    |<span data-ttu-id="e394d-147">EXCEL und OLE DB</span><span class="sxs-lookup"><span data-stu-id="e394d-147">EXCEL and OLE DB</span></span>|<span data-ttu-id="e394d-148">0, 1, 2, 3, ...</span><span class="sxs-lookup"><span data-stu-id="e394d-148">0, 1, 2, 3, ...</span></span>|  
  
10. <span data-ttu-id="e394d-149">Wählen Sie in der Liste **Variablenname** eine Variable aus.</span><span class="sxs-lookup"><span data-stu-id="e394d-149">From the **Variable Name** list, select a variable.</span></span> <span data-ttu-id="e394d-150">Weitere Informationen finden Sie unter [Hinzufügen, Löschen, Ändern des Bereichs von benutzerdefinierten Variablen in einem Paket](../../2014/integration-services/add-delete-change-scope-of-user-defined-variable-in-a-package.md).</span><span class="sxs-lookup"><span data-stu-id="e394d-150">For more information, see [Add, Delete, Change Scope of User-Defined Variable in a Package](../../2014/integration-services/add-delete-change-scope-of-user-defined-variable-in-a-package.md).</span></span>  
  
11. <span data-ttu-id="e394d-151">Geben Sie in der Liste **Richtung** an, ob der Parameter eine Eingabe, eine Ausgabe oder ein Rückgabewert ist.</span><span class="sxs-lookup"><span data-stu-id="e394d-151">In the **Direction** list, specify if the parameter is an input, an output, or a return value.</span></span>  
  
12. <span data-ttu-id="e394d-152">Legen Sie in der Liste **Datentyp** den Datentyp des Parameters fest.</span><span class="sxs-lookup"><span data-stu-id="e394d-152">In the **Data Type** list, set the data type of the parameter.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="e394d-153">Der Datentyp des Parameters muss mit dem Datentyp der Variablen kompatibel sein.</span><span class="sxs-lookup"><span data-stu-id="e394d-153">The data type of the parameter must be compatible with the data type of the variable.</span></span>  
  
13. <span data-ttu-id="e394d-154">Wiederholen Sie die Schritte 8 bis 11 für jeden Parameter in der SQL-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="e394d-154">Repeat steps 8 through 11 for each parameter in the SQL statement.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="e394d-155">Die Reihenfolge von Parameterzuordnungen muss mit der Reihenfolge identisch sein, in der Parameter in der SQL-Anweisung aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="e394d-155">The order of parameter mappings must be the same as the order in which the parameters appear in the SQL statement.</span></span>  
  
14. <span data-ttu-id="e394d-156">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e394d-156">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e394d-157">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e394d-157">See Also</span></span>  
 <span data-ttu-id="e394d-158">[SQL ausführen (Task)](control-flow/execute-sql-task.md) </span><span class="sxs-lookup"><span data-stu-id="e394d-158">[Execute SQL Task](control-flow/execute-sql-task.md) </span></span>  
 <span data-ttu-id="e394d-159">[Parameter und Rückgabe Codes im Task "SQL ausführen"](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md) </span><span class="sxs-lookup"><span data-stu-id="e394d-159">[Parameters and Return Codes in the Execute SQL Task](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md) </span></span>  
 [<span data-ttu-id="e394d-160">Integration Services-Variablen &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="e394d-160">Integration Services &#40;SSIS&#41; Variables</span></span>](integration-services-ssis-variables.md)  
  
  
