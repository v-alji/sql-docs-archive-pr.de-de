---
title: Angeben eines Intervalls von Änderungsdaten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- incremental load [Integration Services],specifying interval
ms.assetid: 17899078-8ba3-4f40-8769-e9837dc3ec60
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 70b9c14d609f2db69ee5751eca18acb5262a07a1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616126"
---
# <a name="specify-an-interval-of-change-data"></a><span data-ttu-id="02437-102">Angeben eines Intervalls von Änderungsdaten</span><span class="sxs-lookup"><span data-stu-id="02437-102">Specify an Interval of Change Data</span></span>
  <span data-ttu-id="02437-103">In der Ablaufsteuerung eines [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Pakets, das ein inkrementelles Laden von Änderungsdaten ausführt, ist der erste Task die Berechnung der Endpunkte des Änderungsintervalls.</span><span class="sxs-lookup"><span data-stu-id="02437-103">In the control flow of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that performs an incremental load of change data, the first task is to calculate the endpoints of the change interval.</span></span> <span data-ttu-id="02437-104">Diese Endpunkte sind `datetime`-Werte und werden in Paketvariablen für die spätere Verwendung im Paket gespeichert.</span><span class="sxs-lookup"><span data-stu-id="02437-104">These endpoints are `datetime` values and will be stored in package variables for use later in the package.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="02437-105">Eine Beschreibung des Gesamtprozesses zum Entwurf der Ablaufsteuerung finden Sie unter [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="02437-105">For a description of the overall process of designing the control flow, see [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span></span>  
  
## <a name="set-up-package-variables-for-the-endpoints"></a><span data-ttu-id="02437-106">Einrichten von Paketvariablen für die Endpunkte</span><span class="sxs-lookup"><span data-stu-id="02437-106">Set Up Package Variables for the Endpoints</span></span>  
 <span data-ttu-id="02437-107">Vor dem Konfigurieren des Tasks "SQL ausführen" zur Berechnung der Endpunkte müssen die Paketvariablen definiert werden, die die Endpunkte speichern.</span><span class="sxs-lookup"><span data-stu-id="02437-107">Before configuring the Execute SQL task to calculate the endpoints, the package variables that will store the endpoints have to be defined.</span></span>  
  
#### <a name="to-set-up-package-variables"></a><span data-ttu-id="02437-108">So richten Sie Paketvariablen ein</span><span class="sxs-lookup"><span data-stu-id="02437-108">To set up package variables</span></span>  
  
1.  <span data-ttu-id="02437-109">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]ein neues [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Projekt.</span><span class="sxs-lookup"><span data-stu-id="02437-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open a new [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="02437-110">Erstellen Sie im Fenster **Variablen** die folgenden Variablen:</span><span class="sxs-lookup"><span data-stu-id="02437-110">In the **Variables** window, create the following variables:</span></span>  
  
    1.  <span data-ttu-id="02437-111">Erstellen Sie eine Variable mit dem `datetime`-Datentyp, um den Anfangspunkt für das Intervall zu speichern.</span><span class="sxs-lookup"><span data-stu-id="02437-111">Create a variable with the `datetime` data type to hold the starting point for the interval.</span></span>  
  
         <span data-ttu-id="02437-112">In diesem Beispiel wird der Variablenname "ExtractStartTime" verwendet.</span><span class="sxs-lookup"><span data-stu-id="02437-112">This example uses the variable name, ExtractStartTime.</span></span>  
  
    2.  <span data-ttu-id="02437-113">Erstellen Sie eine weitere Variable mit dem `datetime`-Datentyp, um den Endpunkt für das Intervall zu speichern.</span><span class="sxs-lookup"><span data-stu-id="02437-113">Create another variable with the `datetime` data type to hold the ending point for the interval.</span></span>  
  
         <span data-ttu-id="02437-114">In diesem Beispiel wird der Variablenname "ExtractEndTime" verwendet.</span><span class="sxs-lookup"><span data-stu-id="02437-114">This example uses the variable name, ExtractEndTime.</span></span>  
  
 <span data-ttu-id="02437-115">Wenn Sie die Endpunkte in einem Masterpaket berechnen, das mehrere untergeordnete Pakete ausführt, können Sie die Variablenkonfiguration für übergeordnete Pakete verwenden, um die Werte dieser Variablen an jedes untergeordnete Paket weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="02437-115">If you calculate the endpoints in a master package that executes multiple child packages, you can use Parent Package Variable configurations to pass the values of these variables to each child package.</span></span> <span data-ttu-id="02437-116">Weitere Informationen finden Sie unter [Paket ausführen (Task)](../control-flow/execute-package-task.md) und [Verwenden der Werte von Variablen und Parametern in einem untergeordneten Paket](../use-the-values-of-variables-and-parameters-in-a-child-package.md).</span><span class="sxs-lookup"><span data-stu-id="02437-116">For more information, see [Execute Package Task](../control-flow/execute-package-task.md) and [Use the Values of Variables and Parameters in a Child Package](../use-the-values-of-variables-and-parameters-in-a-child-package.md).</span></span>  
  
## <a name="calculate-a-starting-point-and-an-ending-point-for-change-data"></a><span data-ttu-id="02437-117">Berechnen eines Anfangspunkts und eines Endpunkts für Änderungsdaten</span><span class="sxs-lookup"><span data-stu-id="02437-117">Calculate a Starting Point and an Ending Point for Change Data</span></span>  
 <span data-ttu-id="02437-118">Nachdem Sie die Paketvariablen für die Intervallendpunkte eingerichtet haben, können Sie die Ist-Werte für diese Endpunkte berechnen und diese Werte den entsprechenden Paketvariablen zuordnen.</span><span class="sxs-lookup"><span data-stu-id="02437-118">After you set up the package variables for the interval endpoints, you can calculate the actual values for those endpoints and map those values to the corresponding package variables.</span></span> <span data-ttu-id="02437-119">Da diese Endpunkte `datetime`-Werte sind, müssen Sie Funktionen verwenden, die `datetime`-Werte berechnen oder mit diesen funktionieren können.</span><span class="sxs-lookup"><span data-stu-id="02437-119">Because those endpoints are `datetime` values, you will have to use functions that can calculate or work with `datetime` values.</span></span> <span data-ttu-id="02437-120">Die [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Ausdruckssprache und Transact-SQL verfügen über Funktionen, die mit `datetime`-Werten funktionieren:</span><span class="sxs-lookup"><span data-stu-id="02437-120">Both the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expression language and Transact-SQL have functions that work with `datetime` values:</span></span>  
  
 <span data-ttu-id="02437-121">Funktionen in der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Ausdruckssprache, die mit `datetime`-Werten funktionieren</span><span class="sxs-lookup"><span data-stu-id="02437-121">Functions in the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expression language that work with `datetime` values</span></span>  
 -   [<span data-ttu-id="02437-122">DATEADD &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="02437-122">DATEADD &#40;SSIS Expression&#41;</span></span>](../expressions/dateadd-ssis-expression.md)  
  
-   [<span data-ttu-id="02437-123">DATEDIFF &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="02437-123">DATEDIFF &#40;SSIS Expression&#41;</span></span>](../expressions/datediff-ssis-expression.md)  
  
-   [<span data-ttu-id="02437-124">DATEPART &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="02437-124">DATEPART &#40;SSIS Expression&#41;</span></span>](../expressions/datepart-ssis-expression.md)  
  
-   [<span data-ttu-id="02437-125">DAY &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="02437-125">DAY &#40;SSIS Expression&#41;</span></span>](../expressions/day-ssis-expression.md)  
  
-   [<span data-ttu-id="02437-126">GETDATE &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="02437-126">GETDATE &#40;SSIS Expression&#41;</span></span>](../expressions/getdate-ssis-expression.md)  
  
-   [<span data-ttu-id="02437-127">GETUTCDATE &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="02437-127">GETUTCDATE &#40;SSIS Expression&#41;</span></span>](../expressions/getutcdate-ssis-expression.md)  
  
-   [<span data-ttu-id="02437-128">MONTH &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="02437-128">MONTH &#40;SSIS Expression&#41;</span></span>](../expressions/month-ssis-expression.md)  
  
-   [<span data-ttu-id="02437-129">YEAR &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="02437-129">YEAR &#40;SSIS Expression&#41;</span></span>](../expressions/year-ssis-expression.md)  
  
 <span data-ttu-id="02437-130">Funktionen in Transact-SQL, die mit `datetime`-Werten funktionieren</span><span class="sxs-lookup"><span data-stu-id="02437-130">Functions in Transact-SQL that work with `datetime` values</span></span>  
 <span data-ttu-id="02437-131">[Datums- und Uhrzeitdatentypen und zugehörige Funktionen &#40;Transact-SQL&#41;](/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="02437-131">[Date and Time Data Types and Functions &#40;Transact-SQL&#41;](/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql).</span></span>  
  
 <span data-ttu-id="02437-132">Bevor Sie eine dieser `datetime`-Funktionen verwenden, um Endpunkte zu berechnen, müssen Sie bestimmen, ob das Intervall unveränderlich ist und regelmäßig auftritt.</span><span class="sxs-lookup"><span data-stu-id="02437-132">Before you use any one of these `datetime` functions to calculate the endpoints, you have to determine whether the interval is fixed and occurs on a regular schedule.</span></span> <span data-ttu-id="02437-133">In der Regel möchten Sie regelmäßig in Quelltabellen aufgetretene Änderungen in Zieltabellen übernehmen.</span><span class="sxs-lookup"><span data-stu-id="02437-133">Typically, you want to apply changes that have occurred in source tables to destination tables on a regular schedule.</span></span> <span data-ttu-id="02437-134">Beispielsweise möchten Sie diese Änderungen auf einer stündlichen, täglichen oder wöchentlichen Basis übernehmen.</span><span class="sxs-lookup"><span data-stu-id="02437-134">For example, you might want to apply those changes on an hourly, daily, or weekly basis.</span></span>  
  
 <span data-ttu-id="02437-135">Nachdem Sie sich darüber im Klaren sind, ob Ihr Änderungsintervall unveränderlich oder eher zufällig ist, können Sie die Endpunkte berechnen.</span><span class="sxs-lookup"><span data-stu-id="02437-135">After you understand whether your change interval is fixed or is more random, you can calculate the endpoints:</span></span>  
  
-   <span data-ttu-id="02437-136">**Berechnen des Startdatums und der Startzeit**.</span><span class="sxs-lookup"><span data-stu-id="02437-136">**Calculating the starting date and time**.</span></span> <span data-ttu-id="02437-137">Sie verwenden das Enddatum und die Endzeit des vorherigen Ladens als aktuelles Startdatum und aktuelle Startzeit.</span><span class="sxs-lookup"><span data-stu-id="02437-137">You use the ending date and time from the previous load as the current starting date and time.</span></span> <span data-ttu-id="02437-138">Wenn Sie ein unveränderliches Intervall für das inkrementelle Laden verwenden, können Sie diesen Wert mit den `datetime`-Funktionen von Transact-SQL oder der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Ausdruckssprache berechnen.</span><span class="sxs-lookup"><span data-stu-id="02437-138">If you use a fixed interval for incremental loads, you can calculate this value by using the `datetime` functions of Transact-SQL or of the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expression language.</span></span> <span data-ttu-id="02437-139">Andernfalls müssen Sie möglicherweise die Endpunkte zwischen den Ausführungen persistent speichern und einen Task "SQL ausführen" oder einen Skripttask verwenden, um den vorherigen Endpunkt zu laden.</span><span class="sxs-lookup"><span data-stu-id="02437-139">Otherwise, you might have to persist the endpoints between executions, and use an Execute SQL task or a Script task to load the previous endpoint.</span></span>  
  
-   <span data-ttu-id="02437-140">**Berechnen des Enddatums und der Endzeit**.</span><span class="sxs-lookup"><span data-stu-id="02437-140">**Calculating the ending date and time**.</span></span> <span data-ttu-id="02437-141">Wenn Sie ein unveränderliches Intervall für das inkrementelle Laden verwenden, berechnen Sie das aktuelle Enddatum und die aktuelle Endzeit als Offset des Startdatums und der Startzeit.</span><span class="sxs-lookup"><span data-stu-id="02437-141">If you use a fixed interval for incremental loads, calculate the current ending date and time as an offset from the starting date and time.</span></span> <span data-ttu-id="02437-142">Sie können diesen Wert auch mit den `datetime` Funktionen von Transact-SQL oder der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] Ausdruckssprache berechnen.</span><span class="sxs-lookup"><span data-stu-id="02437-142">Again, you can calculate this value by using the `datetime` functions of Transact-SQL or of the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expression language.</span></span>  
  
 <span data-ttu-id="02437-143">In der folgenden Prozedur verwendet das Änderungsintervall ein unveränderliches Intervall und setzt voraus, dass das Paket für inkrementelles Laden ohne Ausnahme täglich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="02437-143">In the following procedure, the change interval uses a fixed interval and assumes that the incremental load package is run daily without exception.</span></span> <span data-ttu-id="02437-144">Andernfalls würden Änderungsdaten für verpasste Intervalle verloren gehen.</span><span class="sxs-lookup"><span data-stu-id="02437-144">Otherwise, change data for missed intervals would be lost.</span></span> <span data-ttu-id="02437-145">Der Startpunkt für das Intervall ist vorgestern Mitternacht, d. h. vor 24 bis 48 Stunden.</span><span class="sxs-lookup"><span data-stu-id="02437-145">The starting point for the interval is midnight the day before yesterday, that is, between 24 and 48 hours ago.</span></span> <span data-ttu-id="02437-146">Der Endpunkt für das Intervall ist gestern Mitternacht, d. h. in der vorherigen Nacht vor 0 bis 24 Stunden.</span><span class="sxs-lookup"><span data-stu-id="02437-146">The ending point for the interval is midnight yesterday, that is, the previous night, between 0 and 24 hours ago.</span></span>  
  
#### <a name="to-calculate-the-starting-point-and-ending-point-for-the-capture-interval"></a><span data-ttu-id="02437-147">So berechnen Sie den Startpunkt und den Endpunkt für das Aufzeichnungsintervall</span><span class="sxs-lookup"><span data-stu-id="02437-147">To calculate the starting point and ending point for the capture interval</span></span>  
  
1.  <span data-ttu-id="02437-148">Fügen Sie auf der Registerkarte **Ablaufsteuerung** des [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designers dem Paket einen Task "SQL ausführen" hinzu.</span><span class="sxs-lookup"><span data-stu-id="02437-148">On the **Control Flow** tab of [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, add an Execute SQL Task to the package.</span></span>  
  
2.  <span data-ttu-id="02437-149">Öffnen Sie den **Editor für den Task 'SQL ausführen'** , und aktivieren Sie auf der Seite **Allgemein** des Editors die folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="02437-149">Open the **Execute SQL Task Editor**, and on the **General** page of the editor, select the following options:</span></span>  
  
    1.  <span data-ttu-id="02437-150">Wählen Sie für **ResultSet**die Option **Einzelne Zeile**aus.</span><span class="sxs-lookup"><span data-stu-id="02437-150">For **ResultSet**, select **Single row**.</span></span>  
  
    2.  <span data-ttu-id="02437-151">Konfigurieren Sie zur Quelldatenbank eine gültige Verbindung.</span><span class="sxs-lookup"><span data-stu-id="02437-151">Configure a valid connection to the source database.</span></span>  
  
    3.  <span data-ttu-id="02437-152">Wählen Sie für **SQLSourceType**die Option **Direkteingabe**aus.</span><span class="sxs-lookup"><span data-stu-id="02437-152">For **SQLSourceType**, select **Direct input**.</span></span>  
  
    4.  <span data-ttu-id="02437-153">Geben Sie für **SQLStatement**die folgende SQL-Anweisung ein:</span><span class="sxs-lookup"><span data-stu-id="02437-153">For **SQLStatement**, enter the following SQL statement:</span></span>  
  
        ```  
        SELECT DATEADD(dd,0, DATEDIFF(dd,0,GETDATE()-1)) AS ExtractStartTime,  
          DATEADD(dd,0, DATEDIFF(dd,0,GETDATE())) AS ExtractEndTime  
  
        ```  
  
3.  <span data-ttu-id="02437-154">Ordnen Sie auf der Seite **Resultset** vom **Editor für den Task 'SQL ausführen'** der ExtractStartTime-Paketvariablen das ExtractStartTime-Ergebnis und der ExtractEndTime-Paketvariablen das ExtractEndTime-Ergebnis zu.</span><span class="sxs-lookup"><span data-stu-id="02437-154">On the **Result Set** page of the **Execute SQL Task Editor**, map the ExtractStartTime result to the ExtractStartTime package variable, and map the ExtractEndTime result to the ExtractEndTime package variable.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="02437-155">Wenn Sie einen Ausdruck verwenden, um den Wert einer [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Variablen festzulegen, wird der Ausdruck jedes Mal ausgewertet, wenn auf den Wert der Variablen zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="02437-155">When you use an expression to set the value of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] variable, the expression is evaluated every time that the value of the variable is accessed.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="02437-156">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="02437-156">Next Step</span></span>  
 <span data-ttu-id="02437-157">Nachdem Sie den Startpunkt und den Endpunkt für eine Reihe von Änderungen berechnet haben, müssen Sie im nächsten Schritt bestimmen, ob die Änderungsdaten bereit sind.</span><span class="sxs-lookup"><span data-stu-id="02437-157">After you calculate the starting point and ending point for a range of changes, the next step is to determine whether the change data is ready.</span></span>  
  
 <span data-ttu-id="02437-158">**Nächstes Thema:** [Bestimmen, ob die Änderungsdaten bereit sind](determine-whether-the-change-data-is-ready.md)</span><span class="sxs-lookup"><span data-stu-id="02437-158">**Next topic:** [Determine Whether the Change Data Is Ready](determine-whether-the-change-data-is-ready.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02437-159">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="02437-159">See Also</span></span>  
 <span data-ttu-id="02437-160">[Verwenden von Variablen in Paketen](../use-variables-in-packages.md) </span><span class="sxs-lookup"><span data-stu-id="02437-160">[Use Variables in Packages](../use-variables-in-packages.md) </span></span>  
 <span data-ttu-id="02437-161">[Integration Services-Ausdrücke &#40;SSIS&#41;](../expressions/integration-services-ssis-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="02437-161">[Integration Services &#40;SSIS&#41; Expressions](../expressions/integration-services-ssis-expressions.md) </span></span>  
 <span data-ttu-id="02437-162">[SQL ausführen (Task)](../control-flow/execute-sql-task.md) </span><span class="sxs-lookup"><span data-stu-id="02437-162">[Execute SQL Task](../control-flow/execute-sql-task.md) </span></span>  
 [<span data-ttu-id="02437-163">Skripttask</span><span class="sxs-lookup"><span data-stu-id="02437-163">Script Task</span></span>](../control-flow/script-task.md)  
  
  
