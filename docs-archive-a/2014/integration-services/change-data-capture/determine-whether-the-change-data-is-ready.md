---
title: Bestimmen, ob die Änderungsdaten bereit sind | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- incremental load [Integration Services],determining readiness
ms.assetid: 04935f35-96cc-4d70-a250-0fd326f8daff
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5e672440938e366e53ba150f65d7bcd6aed8a58c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724038"
---
# <a name="determine-whether-the-change-data-is-ready"></a><span data-ttu-id="69af5-102">Bestimmen, ob die Änderungsdaten bereit sind</span><span class="sxs-lookup"><span data-stu-id="69af5-102">Determine Whether the Change Data Is Ready</span></span>
  <span data-ttu-id="69af5-103">In der Ablaufsteuerung eines [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Pakets, das ein inkrementelles Laden von Änderungsdaten ausführt, besteht der zweite Task darin, sicherzustellen, dass die Änderungsdaten für das ausgewählte Intervall bereit sind.</span><span class="sxs-lookup"><span data-stu-id="69af5-103">In the control flow of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that performs an incremental load of change data, the second task is to ensure that the change data for the selected interval is ready.</span></span> <span data-ttu-id="69af5-104">Dieser Schritt ist notwendig, da der asynchrone Aufzeichnungsprozess möglicherweise noch nicht alle Änderungen bis zum ausgewählten Endpunkt verarbeitet hat.</span><span class="sxs-lookup"><span data-stu-id="69af5-104">This step is necessary because the asynchronous capture process might not yet have processed all the changes up to the selected endpoint.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="69af5-105">Beim ersten Task für die Ablaufsteuerung müssen die Endpunkte des Änderungsintervalls berechnet werden.</span><span class="sxs-lookup"><span data-stu-id="69af5-105">The first task for the control flow is to calculate the endpoints of the change interval.</span></span> <span data-ttu-id="69af5-106">Weitere Informationen zu diesem Task finden Sie unter [Angeben eines Intervalls von Änderungsdaten](specify-an-interval-of-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="69af5-106">For more information about this task, see [Specify an Interval of Change Data](specify-an-interval-of-change-data.md).</span></span> <span data-ttu-id="69af5-107">Eine Beschreibung des Gesamtprozesses zum Entwurf der Ablaufsteuerung finden Sie unter [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="69af5-107">For a description of the overall process of designing the control flow, see [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span></span>  
  
## <a name="understanding-the-components-of-the-solution"></a><span data-ttu-id="69af5-108">Grundlegendes zu den Komponenten der Lösung</span><span class="sxs-lookup"><span data-stu-id="69af5-108">Understanding the Components of the Solution</span></span>  
 <span data-ttu-id="69af5-109">Die in diesem Thema beschriebene Lösung verwendet 4 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Komponenten:</span><span class="sxs-lookup"><span data-stu-id="69af5-109">The solution described in this topic uses 4 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] components:</span></span>  
  
-   <span data-ttu-id="69af5-110">Ein For-Schleifencontainer, der wiederholt die Ausgabe eines Tasks "SQL ausführen" auswertet.</span><span class="sxs-lookup"><span data-stu-id="69af5-110">A For Loop container that repeatedly evaluates the output of an Execute SQL Task.</span></span>  
  
-   <span data-ttu-id="69af5-111">Ein Task "SQL ausführen", der spezielle Tabellen abfragt, die der Change Data Capture-Prozess verwaltet, und dann diese Informationen verwendet, um zu bestimmen, ob Daten bereit sind.</span><span class="sxs-lookup"><span data-stu-id="69af5-111">An Execute SQL task that queries special tables that the change data capture process maintains and then uses this information to determine whether data is ready.</span></span>  
  
-   <span data-ttu-id="69af5-112">Eine Komponente, die eine Verzögerung in die Verarbeitung implementiert, wenn die Daten nicht bereit sind.</span><span class="sxs-lookup"><span data-stu-id="69af5-112">A component that implements a delay in processing when the data is not ready.</span></span> <span data-ttu-id="69af5-113">Dies kann entweder ein Skripttask oder ein Task "SQL ausführen" sein.</span><span class="sxs-lookup"><span data-stu-id="69af5-113">This can be either a Script task or an Execute SQL task.</span></span>  
  
-   <span data-ttu-id="69af5-114">Optional eine Komponente, die einen Fehler oder ein Timeout meldet, wenn der Tast "SQL ausführen" einen Wert zurückgibt, der eine Fehler- oder eine Timeoutbedingung angibt.</span><span class="sxs-lookup"><span data-stu-id="69af5-114">Optionally, a component that reports an error or a timeout when the Execute SQL task returns a value that indicates an error or a timeout condition.</span></span>  
  
 <span data-ttu-id="69af5-115">Diese Komponenten legen die Werte von mehreren Paketvariablen fest oder lesen sie, um den Ausführungsablauf innerhalb der Schleife und später im Paket zu steuern.</span><span class="sxs-lookup"><span data-stu-id="69af5-115">These components set or read the values of several package variables to control the flow of execution inside the loop and later in the package.</span></span>  
  
#### <a name="to-set-up-package-variables"></a><span data-ttu-id="69af5-116">So richten Sie Paketvariablen ein</span><span class="sxs-lookup"><span data-stu-id="69af5-116">To set up package variables</span></span>  
  
1.  <span data-ttu-id="69af5-117">Erstellen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]im Fenster **Variablen** die folgenden Variablen:</span><span class="sxs-lookup"><span data-stu-id="69af5-117">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], in the **Variables** window, create the following variables:</span></span>  
  
    1.  <span data-ttu-id="69af5-118">Erstellen Sie eine Variable mit einem integer-Datentyp, damit der Statuswert verzögert wird, der vom Task "SQL ausführen" zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="69af5-118">Create a variable with an integer data type to hold the status value returned by the Execute SQL task.</span></span>  
  
         <span data-ttu-id="69af5-119">In diesem Beispiel wird der Variablenname "DataReady" mit einem Anfangswert von 0 verwendet.</span><span class="sxs-lookup"><span data-stu-id="69af5-119">This example uses the variable name, DataReady, with an initial value of 0.</span></span>  
  
    2.  <span data-ttu-id="69af5-120">Erstellen Sie eine Variable, um den Zeitraum für die Verzögerung festzulegen, wenn Daten nicht bereit sind.</span><span class="sxs-lookup"><span data-stu-id="69af5-120">Create a variable to hold the period of time to delay when data is not ready.</span></span> <span data-ttu-id="69af5-121">Wenn Sie einen Skripttask verwenden möchten, um die Verzögerung zu implementieren, sollte die Variable einen integer-Datentyp besitzen.</span><span class="sxs-lookup"><span data-stu-id="69af5-121">If you plan to use a Script task to implement the delay, the variable should have an integer data type integer.</span></span> <span data-ttu-id="69af5-122">Wenn Sie einen Task "SQL ausführen" mit einer WAITFOR-Anweisung verwenden möchten, sollte die Variable einen Zeichenfolge-Datentyp besitzen, um Werte wie "00:00:10" zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="69af5-122">If you plan to use an Execute SQL task with a WAITFOR statement, the variable should have a string data type to accept values such as "00:00:10".</span></span>  
  
         <span data-ttu-id="69af5-123">In diesem Beispiel wird der Variablenname "DelaySeconds" mit einem Anfangswert von 10 verwendet.</span><span class="sxs-lookup"><span data-stu-id="69af5-123">This example uses the variable name, DelaySeconds, with an initial value of 10.</span></span>  
  
    3.  <span data-ttu-id="69af5-124">Erstellen Sie eine Variable mit einem integer-Datentyp, um die aktuelle Iteration der Schleife zu verzögern.</span><span class="sxs-lookup"><span data-stu-id="69af5-124">Create a variable with an integer data type to hold the current iteration of the loop.</span></span>  
  
         <span data-ttu-id="69af5-125">In diesem Beispiel wird der Variablenname "TimeoutCount" mit einem Anfangswert von 0 verwendet.</span><span class="sxs-lookup"><span data-stu-id="69af5-125">This example uses the variable name, TimeoutCount, with an initial value of 0.</span></span>  
  
    4.  <span data-ttu-id="69af5-126">Erstellen Sie eine Variable mit einem integer-Datentyp, um die Anzahl festzulegen, die die Schleife nach Daten prüfen soll, bevor ein Timeout gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="69af5-126">Create a variable with an integer data type to specify the number of times that the loop should test for data before reporting a timeout condition.</span></span>  
  
         <span data-ttu-id="69af5-127">In diesem Beispiel wird der Variablenname "TimeoutCeiling" mit einem Anfangswert von 20 verwendet.</span><span class="sxs-lookup"><span data-stu-id="69af5-127">This example uses the variable name, TimeoutCeiling, with an initial value of 20.</span></span>  
  
    5.  <span data-ttu-id="69af5-128">(Optional) Erstellen Sie eine Variable mit einem integer-Datentyp, die Sie verwenden können, um das erste Laden von Änderungsdaten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="69af5-128">(Optional) Create a variable with an integer data type that you can use to indicate the first load of change data.</span></span>  
  
         <span data-ttu-id="69af5-129">In diesem Beispiel wird der Variablenname "IntervalID" verwendet, und es wird nur auf einen Wert von 0 geprüft, um das erste Laden anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="69af5-129">This example uses the variable name, IntervalID, and checks only for a value of 0 to indicate the initial load.</span></span>  
  
## <a name="configuring-a-for-loop-container"></a><span data-ttu-id="69af5-130">Konfigurieren eines For-Schleifencontainers</span><span class="sxs-lookup"><span data-stu-id="69af5-130">Configuring a For Loop Container</span></span>  
 <span data-ttu-id="69af5-131">Mit dem Variablensatz ist der For-Schleifencontainer die erste Komponente, die hinzugefügt werden muss.</span><span class="sxs-lookup"><span data-stu-id="69af5-131">With the variables set, the For Loop container is the first component to be added.</span></span>  
  
#### <a name="to-configure-a-for-loop-container-to-wait-until-change-data-is-ready"></a><span data-ttu-id="69af5-132">So konfigurieren Sie einen For-Schleifencontainer für das Warten auf die Bereitschaft von Änderungsdaten</span><span class="sxs-lookup"><span data-stu-id="69af5-132">To configure a For Loop container to wait until change data is ready</span></span>  
  
1.  <span data-ttu-id="69af5-133">Fügen Sie auf der Registerkarte **Ablaufsteuerung** des [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designers der Ablaufsteuerung einen For-Schleifencontainer hinzu.</span><span class="sxs-lookup"><span data-stu-id="69af5-133">On the **Control Flow** tab of the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, add a For Loop container to the control flow.</span></span>  
  
2.  <span data-ttu-id="69af5-134">Verbinden Sie den Task "SQL ausführen", der die Endpunkte des Intervalls berechnet, mit dem For-Schleifencontainer.</span><span class="sxs-lookup"><span data-stu-id="69af5-134">Connect the Execute SQL Task that calculates the endpoints of the interval to the For Loop container.</span></span>  
  
3.  <span data-ttu-id="69af5-135">Aktivieren Sie im **For-Schleifen-Editor**die folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="69af5-135">In the **For Loop Editor**, select the following options:</span></span>  
  
    1.  <span data-ttu-id="69af5-136">Geben Sie für **InitExpression**`@DataReady = 0`ein.</span><span class="sxs-lookup"><span data-stu-id="69af5-136">For **InitExpression**, enter `@DataReady = 0`.</span></span>  
  
         <span data-ttu-id="69af5-137">Dieser Ausdruck legt den Anfangswert der Schleifenvariablen fest.</span><span class="sxs-lookup"><span data-stu-id="69af5-137">This expression sets the initial value of the loop variable.</span></span>  
  
    2.  <span data-ttu-id="69af5-138">Geben Sie für **EvalExpression**`@DataReady == 0`ein.</span><span class="sxs-lookup"><span data-stu-id="69af5-138">For **EvalExpression**m, enter `@DataReady == 0`.</span></span>  
  
         <span data-ttu-id="69af5-139">Wenn dieser Ausdruck **False**ergibt, wird die Ausführung aus der Schleife weitergegeben, und das inkrementelle Laden beginnt.</span><span class="sxs-lookup"><span data-stu-id="69af5-139">When this expression evaluates to **False**, execution passes out of the loop and the incremental load starts.</span></span>  
  
## <a name="configuring-the-execute-sql-task-that-queries-for-change-data"></a><span data-ttu-id="69af5-140">Konfigurieren des Tasks "SQL ausführen", der Änderungsdaten abfragt</span><span class="sxs-lookup"><span data-stu-id="69af5-140">Configuring the Execute SQL Task That Queries for Change Data</span></span>  
 <span data-ttu-id="69af5-141">Innerhalb des For-Schleifencontainers fügen Sie einen Task "SQL ausführen" hinzu.</span><span class="sxs-lookup"><span data-stu-id="69af5-141">Inside the For Loop container, you add an Execute SQL task.</span></span> <span data-ttu-id="69af5-142">Dieser Task fragt die Tabellen ab, die der Change Data Capture-Prozess in der Datenbank verwaltet.</span><span class="sxs-lookup"><span data-stu-id="69af5-142">This task queries the tables that the change data capture process maintains in the database.</span></span> <span data-ttu-id="69af5-143">Das Ergebnis dieser Abfrage ist ein Statuswert, der angibt, ob die Änderungsdaten bereit sind.</span><span class="sxs-lookup"><span data-stu-id="69af5-143">The result of this query is a status value that indicates whether the change data is ready.</span></span>  
  
 <span data-ttu-id="69af5-144">In der folgenden Tabelle zeigt die erste Spalte die Werte an, die von der Task "SQL ausführen" durch die Beispiel-Transact-SQL-Abfrage zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="69af5-144">In the following table, the first column shows the values returned from the Execute SQL task by the sample Transact-SQL query.</span></span> <span data-ttu-id="69af5-145">Die zweite Spalte zeigt an, wie die anderen Komponenten auf diese Werte reagieren.</span><span class="sxs-lookup"><span data-stu-id="69af5-145">The second column shows how the other components respond to these values.</span></span>  
  
|<span data-ttu-id="69af5-146">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="69af5-146">Return Value</span></span>|<span data-ttu-id="69af5-147">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="69af5-147">Meaning</span></span>|<span data-ttu-id="69af5-148">Antwort</span><span class="sxs-lookup"><span data-stu-id="69af5-148">Response</span></span>|  
|------------------|-------------|--------------|  
|<span data-ttu-id="69af5-149">0</span><span class="sxs-lookup"><span data-stu-id="69af5-149">0</span></span>|<span data-ttu-id="69af5-150">Gibt an, dass die Änderungsdaten nicht bereit sind.</span><span class="sxs-lookup"><span data-stu-id="69af5-150">Indicates that the change data is not ready.</span></span><br /><br /> <span data-ttu-id="69af5-151">Es gibt nach dem Endpunkt des ausgewählten Intervalls keine Change Data Capture-Datensätze.</span><span class="sxs-lookup"><span data-stu-id="69af5-151">There are no change data capture records later than the ending point of the selected interval.</span></span>|<span data-ttu-id="69af5-152">Die Ausführung setzt mit der Komponente fort, die eine Verzögerung implementiert.</span><span class="sxs-lookup"><span data-stu-id="69af5-152">Execution continues with the component that implements a delay.</span></span> <span data-ttu-id="69af5-153">Dann kehrt die Steuerung zum For-Schleifencontainer zurück, der weiterhin den Task "SQL ausführen" überprüft, solange der zurückgegebene Wert 0 ist.</span><span class="sxs-lookup"><span data-stu-id="69af5-153">Then control returns to the For Loop container, which continues to check the Execute SQL task as long as the value returned is 0.</span></span>|  
|<span data-ttu-id="69af5-154">1</span><span class="sxs-lookup"><span data-stu-id="69af5-154">1</span></span>|<span data-ttu-id="69af5-155">Könnte darauf hinweisen, dass die Änderungsdaten nicht für das vollständige Intervall erfasst wurden oder dass sie gelöscht wurden.</span><span class="sxs-lookup"><span data-stu-id="69af5-155">Might indicate that the change data has not been captured for the complete interval, or that it has been deleted.</span></span> <span data-ttu-id="69af5-156">Dies wird als Fehlerbedingung behandelt.</span><span class="sxs-lookup"><span data-stu-id="69af5-156">This is treated as an error condition.</span></span><br /><br /> <span data-ttu-id="69af5-157">Es gibt vor dem Anfangspunkt des ausgewählten Intervalls keine Change Data Capture-Datensätze.</span><span class="sxs-lookup"><span data-stu-id="69af5-157">There are no change data capture records earlier than the starting point of the selected interval</span></span>|<span data-ttu-id="69af5-158">Die Ausführung setzt mit der optionalen Komponente fort, die den Fehler protokolliert.</span><span class="sxs-lookup"><span data-stu-id="69af5-158">Execution continues with the optional component that logs the error.</span></span>|  
|<span data-ttu-id="69af5-159">2</span><span class="sxs-lookup"><span data-stu-id="69af5-159">2</span></span>|<span data-ttu-id="69af5-160">Gibt an, dass Daten bereit sind.</span><span class="sxs-lookup"><span data-stu-id="69af5-160">Indicates that data is ready.</span></span><br /><br /> <span data-ttu-id="69af5-161">Es gibt Change Data Capture-Datensätze, die vor dem Anfangspunkt und nach dem Endpunkt des ausgewählten Intervalls liegen.</span><span class="sxs-lookup"><span data-stu-id="69af5-161">There are change data capture records that are both earlier than the starting point and later than the ending point of the selected interval.</span></span>|<span data-ttu-id="69af5-162">Die Ausführung wird aus dem For-Schleifencontainer weitergegeben, und das inkrementelle Laden beginnt.</span><span class="sxs-lookup"><span data-stu-id="69af5-162">Execution passes out of the For Loop container and the incremental load starts.</span></span>|  
|<span data-ttu-id="69af5-163">3</span><span class="sxs-lookup"><span data-stu-id="69af5-163">3</span></span>|<span data-ttu-id="69af5-164">Gibt das erstmalige Laden aller verfügbaren Änderungsdaten an.</span><span class="sxs-lookup"><span data-stu-id="69af5-164">Indicates the initial load of all available change data.</span></span><br /><br /> <span data-ttu-id="69af5-165">Die Bedingungslogik erhält diesen Wert von einer speziellen Paketvariablen, die nur für diesen Zweck verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="69af5-165">The conditional logic obtains this value from a special package variable that is used only for this purpose.</span></span>|<span data-ttu-id="69af5-166">Die Ausführung wird aus dem For-Schleifencontainer weitergegeben, und das inkrementelle Laden beginnt.</span><span class="sxs-lookup"><span data-stu-id="69af5-166">Execution passes out of the For Loop container and the incremental load starts.</span></span>|  
|<span data-ttu-id="69af5-167">5</span><span class="sxs-lookup"><span data-stu-id="69af5-167">5</span></span>|<span data-ttu-id="69af5-168">Gibt an, dass der TimeoutCeiling erreicht wurde.</span><span class="sxs-lookup"><span data-stu-id="69af5-168">Indicates that the TimeoutCeiling has been reached.</span></span><br /><br /> <span data-ttu-id="69af5-169">Die Schleife hat für die festgelegte Anzahl auf Daten getestet, und Daten sind immer noch nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="69af5-169">The loop has tested for data the specified number of times, and data is still not available.</span></span> <span data-ttu-id="69af5-170">Ohne diesen Test oder einen ähnlichen Test könnte das Paket unbegrenzt ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="69af5-170">Without this test or a similar test, the package might run indefinitely.</span></span>|<span data-ttu-id="69af5-171">Die Ausführung setzt mit der optionalen Komponente fort, die den Timeout protokolliert.</span><span class="sxs-lookup"><span data-stu-id="69af5-171">Execution continues with the optional component that logs the timeout.</span></span>|  
  
#### <a name="to-configure-an-execute-sql-task-to-query-whether-change-data-is-ready"></a><span data-ttu-id="69af5-172">So konfigurieren Sie einen Task "SQL ausführen", um abzufragen, ob Änderungsdaten bereit sind</span><span class="sxs-lookup"><span data-stu-id="69af5-172">To configure an Execute SQL task to query whether change data is ready</span></span>  
  
1.  <span data-ttu-id="69af5-173">Fügen Sie innerhalb des For-Schleifencontainers einen Task "SQL ausführen" hinzu.</span><span class="sxs-lookup"><span data-stu-id="69af5-173">Inside the For Loop container, add an Execute SQL task.</span></span>  
  
2.  <span data-ttu-id="69af5-174">Aktivieren Sie im **Skripttask-Editor**auf der Seite **Skript** die folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="69af5-174">In the **Execute SQL Task Editor**, on the **General** page, select the following options:</span></span>  
  
    1.  <span data-ttu-id="69af5-175">Wählen Sie für **ResultSet**die Option **Einzelne Zeile**aus.</span><span class="sxs-lookup"><span data-stu-id="69af5-175">For **ResultSet**, select **Single row**.</span></span>  
  
    2.  <span data-ttu-id="69af5-176">Konfigurieren Sie zur Quelldatenbank eine gültige Verbindung.</span><span class="sxs-lookup"><span data-stu-id="69af5-176">Configure a valid connection to the source database.</span></span>  
  
    3.  <span data-ttu-id="69af5-177">Wählen Sie für **SQLSourceType**die Option **Direkteingabe**aus.</span><span class="sxs-lookup"><span data-stu-id="69af5-177">For **SQLSourceType**, select **Direct input**.</span></span>  
  
    4.  <span data-ttu-id="69af5-178">Geben Sie für **SQLStatement**die folgende SQL-Anweisung ein:</span><span class="sxs-lookup"><span data-stu-id="69af5-178">For **SQLStatement**, enter the following SQL statement:</span></span>  
  
        ```  
        declare @DataReady int, @TimeoutCount int  
  
        if not exists (select tran_end_time from cdc.lsn_time_mapping  
                where tran_end_time > ?  )  
            select @DataReady = 0  
        else  
            if ? = 0  
                select @DataReady = 3   
        else  
            if not exists (select tran_end_time from cdc.lsn_time_mapping  
                    where tran_end_time <= ? )  
                select @DataReady = 1   
        else  
            select @DataReady = 2  
  
        select @TimeoutCount = ?  
        if (@DataReady = 0)  
            select @TimeoutCount = @TimeoutCount + 1  
        else  
            select @TimeoutCount = 0  
  
        if (@TimeoutCount > ?)  
            select @DataReady = 5  
  
        select @DataReady as DataReady, @TimeoutCount as TimeoutCount  
  
        ```  
  
3.  <span data-ttu-id="69af5-179">Nehmen Sie auf der Seite **Parameterzuordnung** vom **Editor für den Task 'SQL ausführen'** die folgenden Zuordnungen vor:</span><span class="sxs-lookup"><span data-stu-id="69af5-179">On the **Parameter Mapping** page of the **Execute SQL Task Editor**, make the following mappings:</span></span>  
  
    1.  <span data-ttu-id="69af5-180">Ordnen Sie dem Parameter 0 die ExtractEndTime-Variable zu.</span><span class="sxs-lookup"><span data-stu-id="69af5-180">Map the ExtractEndTime variable to parameter 0.</span></span>  
  
    2.  <span data-ttu-id="69af5-181">Ordnen Sie dem Parameter 1 die IntervalID-Variable zu.</span><span class="sxs-lookup"><span data-stu-id="69af5-181">Map the IntervalID variable to parameter 1.</span></span>  
  
    3.  <span data-ttu-id="69af5-182">Ordnen Sie dem Parameter 2 die ExtractStartTime-Variable zu.</span><span class="sxs-lookup"><span data-stu-id="69af5-182">Map the ExtractStartTime variable to parameter 2.</span></span>  
  
    4.  <span data-ttu-id="69af5-183">Ordnen Sie dem Parameter 3 die TimeoutCount-Variable zu.</span><span class="sxs-lookup"><span data-stu-id="69af5-183">Map the TimeoutCount variable to parameter 3.</span></span>  
  
    5.  <span data-ttu-id="69af5-184">Ordnen Sie dem Parameter 4 die TimeoutCeiling-Variable zu.</span><span class="sxs-lookup"><span data-stu-id="69af5-184">Map the TimeoutCeiling variable to parameter 4.</span></span>  
  
4.  <span data-ttu-id="69af5-185">Ordnen Sie auf der Seite **Resultset** vom **Editor für den Task 'SQL ausführen'** das DataReady-Ergebnis der DataReady-Variablen und das TimeoutCount-Ergebnis der TimeoutCount-Variablen zu.</span><span class="sxs-lookup"><span data-stu-id="69af5-185">On the **Result Set** page of the **Execute SQL Task Editor**, map the DataReady result to the DataReady variable, and the TimeoutCount result to the TimeoutCount variable.</span></span>  
  
## <a name="waiting-until-the-change-data-is-ready"></a><span data-ttu-id="69af5-186">Warten, bis die Änderungsdaten bereit sind</span><span class="sxs-lookup"><span data-stu-id="69af5-186">Waiting Until the Change Data Is Ready</span></span>  
 <span data-ttu-id="69af5-187">Sie können unterschiedliche Methoden verwenden, um eine Verzögerung zu implementieren, wenn die Änderungsdaten nicht bereit sind.</span><span class="sxs-lookup"><span data-stu-id="69af5-187">You can use one of several methods to implement a delay when the change data is not ready.</span></span> <span data-ttu-id="69af5-188">Die folgenden zwei Prozeduren veranschaulichen, wie mit einem Skripttask oder einem Task "SQL ausführen" eine Verzögerung implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="69af5-188">The following two procedures illustrate how to use a Script task or an Execute SQL task to implement the delay.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="69af5-189">Ein vorkompiliertes Skript verursacht weniger Aufwand als ein Task "SQL ausführen".</span><span class="sxs-lookup"><span data-stu-id="69af5-189">A precompiled script incurs less overhead than an Execute SQL task.</span></span>  
  
#### <a name="to-implement-a-delay-by-using-a-script-task"></a><span data-ttu-id="69af5-190">So implementieren Sie eine Verzögerung mit einem Skripttask</span><span class="sxs-lookup"><span data-stu-id="69af5-190">To implement a delay by using a Script task</span></span>  
  
1.  <span data-ttu-id="69af5-191">Fügen Sie innerhalb des For-Schleifencontainers einen Skripttask hinzu.</span><span class="sxs-lookup"><span data-stu-id="69af5-191">Inside the For Loop container, add a Script task.</span></span>  
  
2.  <span data-ttu-id="69af5-192">Verbinden Sie den abfragenden Task "SQL ausführen", um zu bestimmen, ob die Änderungsdaten für den neuen Skripttask bereit sind.</span><span class="sxs-lookup"><span data-stu-id="69af5-192">Connect the Execute SQL task that queries to determine whether the change data is ready to the new Script task.</span></span>  
  
3.  <span data-ttu-id="69af5-193">Für die Rangfolgeneinschränkung, die den Task "SQL ausführen" mit dem Skripttask verbindet, öffnen Sie den **Rangfolgeneinschränkungs-Editor** , und wählen Sie die folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="69af5-193">For the precedence constraint that connects the Execute SQL task to the Script task, open the **Precedence Constraint Editor** and select the following options:</span></span>  
  
    1.  <span data-ttu-id="69af5-194">Wählen Sie für **Auswertungsvorgang** **Ausdruck und Einschränkung**aus.</span><span class="sxs-lookup"><span data-stu-id="69af5-194">For **Evaluation operation**, select **Expression and Constraint**.</span></span>  
  
    2.  <span data-ttu-id="69af5-195">Wählen Sie für **Wert** **Erfolg**aus.</span><span class="sxs-lookup"><span data-stu-id="69af5-195">For **Value**, select **Success**.</span></span>  
  
         <span data-ttu-id="69af5-196">Der Einschränkungswert von **Erfolg** verweist auf den Erfolg des vorherigen Tasks.</span><span class="sxs-lookup"><span data-stu-id="69af5-196">The constraint value of **Success** refers to the success of the previous task.</span></span> <span data-ttu-id="69af5-197">In diesem Fall auf den Erfolg des Tasks "SQL ausführen".</span><span class="sxs-lookup"><span data-stu-id="69af5-197">In this case, the success of the Execute SQL task.</span></span>  
  
    3.  <span data-ttu-id="69af5-198">Geben Sie für **Ausdruck**`@DataReady == 0 && @TimeoutCount <= @TimeoutCeiling`ein.</span><span class="sxs-lookup"><span data-stu-id="69af5-198">For **Expression**, enter `@DataReady == 0 && @TimeoutCount <= @TimeoutCeiling`.</span></span>  
  
    4.  <span data-ttu-id="69af5-199">Wählen Sie **Logischer AND-Operator. Alle Einschränkungen müssen zu TRUE** ausgewertet werden, sofern die Option nicht bereits ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="69af5-199">Select **Logical AND. All constraints must evaluate to True**, if not already selected.</span></span>  
  
4.  <span data-ttu-id="69af5-200">Wählen Sie im **Skripttask-Editor**auf der Seite **Skript** für **ReadOnlyVariables**die ganzzahlige Variable **User::DelaySeconds** aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="69af5-200">In the **Script Task Editor**, on the **Script** page, for **ReadOnlyVariables**, select the **User::DelaySeconds** integer variable from the list.</span></span>  
  
5.  <span data-ttu-id="69af5-201">Klicken Sie im **Skripttask-Editor**auf der Seite **Skript** auf **Skript bearbeiten** , um die Skriptentwicklungsumgebung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="69af5-201">In the **Script Task Editor**, on the **Script** page, click **Edit Script** to open the script development environment.</span></span>  
  
6.  <span data-ttu-id="69af5-202">Geben Sie in der Main-Prozedur eine der folgenden Codezeilen ein:</span><span class="sxs-lookup"><span data-stu-id="69af5-202">In the Main procedure, enter one of the following lines of code:</span></span>  
  
    -   <span data-ttu-id="69af5-203">Wenn Sie in C# programmieren, geben Sie die folgende Codezeile ein:</span><span class="sxs-lookup"><span data-stu-id="69af5-203">If you are programming in C#, enter the following line of code:</span></span>  
  
        ```  
        System.Threading.Thread.Sleep((int)Dts.Variables["DelaySeconds"].Value * 1000);  
        ```  
  
         <span data-ttu-id="69af5-204">\- oder –</span><span class="sxs-lookup"><span data-stu-id="69af5-204">\- or -</span></span>  
  
    -   <span data-ttu-id="69af5-205">Wenn Sie in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]programmieren, geben Sie die folgende Codezeile ein:</span><span class="sxs-lookup"><span data-stu-id="69af5-205">If you are programming in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)], enter the following line of code:</span></span>  
  
        ```  
        System.Threading.Thread.Sleep(Ctype(Dts.Variables("DelaySeconds").Value, Integer) * 1000)  
  
        ```  
  
        > [!NOTE]  
        >  <span data-ttu-id="69af5-206">Die `Thread.Sleep`-Methode erwartet ein Argument, das in Millisekunden angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="69af5-206">The `Thread.Sleep` method expects an argument that is specified in milliseconds.</span></span>  
  
7.  <span data-ttu-id="69af5-207">Verlassen Sie die Standardcodezeile, die `DtsExecResult.Success` aus der Ausführung des Skripts zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="69af5-207">Leave the default line of code which returns `DtsExecResult.Success` from the execution of the script.</span></span>  
  
8.  <span data-ttu-id="69af5-208">Schließen Sie die Skriptentwicklungsumgebung und den **Skripttask-Editor**.</span><span class="sxs-lookup"><span data-stu-id="69af5-208">Close the script development environment and the **Script Task Editor**.</span></span>  
  
#### <a name="to-implement-a-delay-by-using-an-execute-sql-task"></a><span data-ttu-id="69af5-209">So implementieren Sie eine Verzögerung mit einem Task "SQL ausführen"</span><span class="sxs-lookup"><span data-stu-id="69af5-209">To implement a delay by using an Execute SQL task</span></span>  
  
1.  <span data-ttu-id="69af5-210">Fügen Sie innerhalb des For-Schleifencontainers einen Task "SQL ausführen" hinzu.</span><span class="sxs-lookup"><span data-stu-id="69af5-210">Inside the For Loop container, add an Execute SQL task.</span></span>  
  
2.  <span data-ttu-id="69af5-211">Verbinden Sie den abfragenden Task "SQL ausführen", um zu bestimmen, ob die Änderungsdaten für den neuen Task "SQL ausführen" bereit sind.</span><span class="sxs-lookup"><span data-stu-id="69af5-211">Connect the Execute SQL task that queries to determine whether the change data is ready to the new Execute SQL task.</span></span>  
  
3.  <span data-ttu-id="69af5-212">Für die Rangfolgeneinschränkung, die die zwei Tasks "SQL ausführen" verbindet, öffnen Sie den **Rangfolgeneinschränkungs-Editor** , und wählen Sie die folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="69af5-212">For the precedence constraint that connects the two Execute SQL tasks, open the **Precedence Constraint Editor** and select the following options:</span></span>  
  
    1.  <span data-ttu-id="69af5-213">Wählen Sie für **Auswertungsvorgang** **Ausdruck und Einschränkung**aus.</span><span class="sxs-lookup"><span data-stu-id="69af5-213">For **Evaluation operation**, select **Expression and Constraint**.</span></span>  
  
    2.  <span data-ttu-id="69af5-214">Wählen Sie für **Wert** **Erfolg**aus.</span><span class="sxs-lookup"><span data-stu-id="69af5-214">For **Value**, select **Success**.</span></span>  
  
         <span data-ttu-id="69af5-215">Der Einschränkungswert von **Erfolg** verweist auf den Erfolg des vorherigen Tasks "SQL ausführen".</span><span class="sxs-lookup"><span data-stu-id="69af5-215">The constraint value of **Success** refers to the success of the previous Execute SQL task.</span></span>  
  
    3.  <span data-ttu-id="69af5-216">Geben Sie für **Ausdruck**`@DataReady == 0`ein.</span><span class="sxs-lookup"><span data-stu-id="69af5-216">For **Expression**, enter `@DataReady == 0`.</span></span>  
  
    4.  <span data-ttu-id="69af5-217">Wählen Sie **Logischer AND-Operator. Alle Einschränkungen müssen zu TRUE** ausgewertet werden, sofern die Option nicht bereits ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="69af5-217">Select **Logical AND. All constraints must evaluate to True**, if not already selected.</span></span>  
  
         <span data-ttu-id="69af5-218">Diese Auswahl erfordert, dass beide Bedingungen, die Einschränkung und der Ausdruck, den Wert true haben müssen.</span><span class="sxs-lookup"><span data-stu-id="69af5-218">This selection requires that both conditions, the constraint and the expression, must be true.</span></span>  
  
4.  <span data-ttu-id="69af5-219">Aktivieren Sie im **Skripttask-Editor**auf der Seite **Skript** die folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="69af5-219">In the **Execute SQL Task Editor**, on the **General** page, select the following options:</span></span>  
  
    1.  <span data-ttu-id="69af5-220">Wählen Sie für **ResultSet**die Option **Einzelne Zeile**aus.</span><span class="sxs-lookup"><span data-stu-id="69af5-220">For **ResultSet**, select **Single row**.</span></span>  
  
    2.  <span data-ttu-id="69af5-221">Konfigurieren Sie zur Quelldatenbank eine gültige Verbindung.</span><span class="sxs-lookup"><span data-stu-id="69af5-221">Configure a valid connection to the source database.</span></span>  
  
    3.  <span data-ttu-id="69af5-222">Wählen Sie für **SQLSourceType**die Option **Direkteingabe**aus.</span><span class="sxs-lookup"><span data-stu-id="69af5-222">For **SQLSourceType**, select **Direct input**.</span></span>  
  
    4.  <span data-ttu-id="69af5-223">Geben Sie für **SQLStatement**die folgende SQL-Anweisung ein:</span><span class="sxs-lookup"><span data-stu-id="69af5-223">For **SQLStatement**, enter the following SQL statement:</span></span>  
  
        ```  
        WAITFOR DELAY ?  
  
        ```  
  
5.  <span data-ttu-id="69af5-224">Ordnen Sie auf der Seite **Parameterzuordnung** des Editors dem Parameter 0 die DelaySeconds-Zeichenfolgenvariable zu.</span><span class="sxs-lookup"><span data-stu-id="69af5-224">On the **Parameter Mapping** page of the editor, map the DelaySeconds string variable to parameter 0.</span></span>  
  
## <a name="handling-an-error-condition"></a><span data-ttu-id="69af5-225">Behandeln einer Fehlerbedingung</span><span class="sxs-lookup"><span data-stu-id="69af5-225">Handling an Error Condition</span></span>  
 <span data-ttu-id="69af5-226">Sie können optional eine zusätzliche Komponente innerhalb der Schleife konfigurieren, um eine Fehler- oder Timeoutbedingung zu protokollieren:</span><span class="sxs-lookup"><span data-stu-id="69af5-226">You can optionally configure an additional component inside the loop to log an error or a timeout condition:</span></span>  
  
-   <span data-ttu-id="69af5-227">Diese Komponente kann eine Fehlerbedingung protokollieren, wenn der Wert der DataReady-Variablen = 1.</span><span class="sxs-lookup"><span data-stu-id="69af5-227">This component can log an error condition when the value of the DataReady variable = 1.</span></span> <span data-ttu-id="69af5-228">Dieser Wert gibt an, dass es keine verfügbaren Änderungsdaten vor dem Start des ausgewählten Intervalls gibt.</span><span class="sxs-lookup"><span data-stu-id="69af5-228">This value indicates that there is no available change data before the start of the selected interval.</span></span>  
  
-   <span data-ttu-id="69af5-229">Diese Komponente kann auch eine Timeoutbedingung protokollieren, wenn der Wert der TimeoutCeiling-Variablen erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="69af5-229">This component can also log a timeout condition when the value of the TimeoutCeiling variable is reached.</span></span> <span data-ttu-id="69af5-230">Dieser Wert gibt an, dass die Schleife für die festgelegte Anzahl auf Daten getestet hat und Daten immer noch nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="69af5-230">This value indicates the loop has tested for data the specified number of times, and data is still not available.</span></span> <span data-ttu-id="69af5-231">Ohne diesen Test oder einen ähnlichen Test könnte das Paket unbegrenzt ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="69af5-231">Without this test or a similar test, the package might run indefinitely.</span></span>  
  
#### <a name="to-configure-an-optional-script-task-to-log-an-error-condition"></a><span data-ttu-id="69af5-232">So konfigurieren Sie einen optionalen Skripttask zur Protokollierung einer Fehlerbedingung</span><span class="sxs-lookup"><span data-stu-id="69af5-232">To configure an optional Script task to log an error condition</span></span>  
  
1.  <span data-ttu-id="69af5-233">Wenn Sie den Fehler oder das Timeout berichten möchten, indem Sie eine Meldung ins Protokoll schreiben, konfigurieren Sie die Protokollierung für das Paket.</span><span class="sxs-lookup"><span data-stu-id="69af5-233">If you want to report the error or timeout by writing a message to the log, configure logging for the package.</span></span> <span data-ttu-id="69af5-234">Weitere Informationen finden Sie unter [Aktivieren der Paketprotokollierung in SQL Server Data Tools](../enable-package-logging-in-sql-server-data-tools.md).</span><span class="sxs-lookup"><span data-stu-id="69af5-234">For more information, see [Enable Package Logging in SQL Server Data Tools](../enable-package-logging-in-sql-server-data-tools.md).</span></span>  
  
2.  <span data-ttu-id="69af5-235">Fügen Sie innerhalb des For-Schleifencontainers einen Skripttask hinzu.</span><span class="sxs-lookup"><span data-stu-id="69af5-235">Inside the For Loop container, add a Script task.</span></span>  
  
3.  <span data-ttu-id="69af5-236">Verbinden Sie den abfragenden Task "SQL ausführen", um zu bestimmen, ob die Änderungsdaten für den neuen Skripttask bereit sind.</span><span class="sxs-lookup"><span data-stu-id="69af5-236">Connect the Execute SQL task that queries to determine whether the change data is ready to the new Script task.</span></span>  
  
4.  <span data-ttu-id="69af5-237">Für die Rangfolgeneinschränkung, die den Task "SQL ausführen" mit dem Skripttask verbindet, öffnen Sie den **Rangfolgeneinschränkungs-Editor** , und wählen Sie die folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="69af5-237">For the precedence constraint that connects the Execute SQL task to the Script task, open the **Precedence Constraint Editor** and select the following options:</span></span>  
  
    1.  <span data-ttu-id="69af5-238">Wählen Sie für **Auswertungsvorgang** **Ausdruck und Einschränkung**aus.</span><span class="sxs-lookup"><span data-stu-id="69af5-238">For **Evaluation operation**, select **Expression and Constraint**.</span></span>  
  
    2.  <span data-ttu-id="69af5-239">Wählen Sie für **Wert** **Erfolg**aus.</span><span class="sxs-lookup"><span data-stu-id="69af5-239">For **Value**, select **Success**.</span></span>  
  
         <span data-ttu-id="69af5-240">Der Einschränkungswert von **Erfolg** verweist auf den Erfolg des vorherigen Tasks.</span><span class="sxs-lookup"><span data-stu-id="69af5-240">The constraint value of **Success** refers to the success of the previous task.</span></span> <span data-ttu-id="69af5-241">In diesem Fall auf den Erfolg des Tasks "SQL ausführen".</span><span class="sxs-lookup"><span data-stu-id="69af5-241">In this case, the success of the Execute SQL task.</span></span>  
  
    3.  <span data-ttu-id="69af5-242">Geben Sie für **Ausdruck**`@DataReady == 1 || @DataReady == 5`ein.</span><span class="sxs-lookup"><span data-stu-id="69af5-242">For **Expression**, enter `@DataReady == 1 || @DataReady == 5`.</span></span>  
  
    4.  <span data-ttu-id="69af5-243">Wählen Sie **Logischer AND-Operator. Alle Einschränkungen müssen zu TRUE** ausgewertet werden, sofern die Option nicht bereits ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="69af5-243">Select **Logical AND. All constraints must evaluate to True**, if not already selected.</span></span>  
  
         <span data-ttu-id="69af5-244">Diese Auswahl erfordert, dass beide Bedingungen, die Einschränkung und der Ausdruck, den Wert true haben müssen.</span><span class="sxs-lookup"><span data-stu-id="69af5-244">This selection requires that both conditions, the constraint and the expression, must be true.</span></span>  
  
5.  <span data-ttu-id="69af5-245">Wählen Sie im **Skripttask-Editor**auf der Seite **Skript** des Editors für **ReadOnlyVariables** **User::DataReady** und **User::ExtractStartTime** aus der Liste aus, um deren Werte für das Skript verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="69af5-245">In the **Script Task Editor**, on the **Script** page of the editor, for **ReadOnlyVariables**, select **User::DataReady** and **User::ExtractStartTime** from the list to make their values available to the script.</span></span>  
  
     <span data-ttu-id="69af5-246">Wenn Sie Informationen von bestimmten Systemvariablen (z. B. System::PackageName) in die Informationen, die in das Protokoll geschrieben werden, einschließen möchten, wählen Sie auch diese Variablen aus.</span><span class="sxs-lookup"><span data-stu-id="69af5-246">If you want to include information from certain system variables (for example, System::PackageName) in the information that you write to the log, select those variables also.</span></span>  
  
6.  <span data-ttu-id="69af5-247">Klicken Sie im **Skripttask-Editor**auf der Seite **Skript** auf **Skript bearbeiten** , um die Skriptentwicklungsumgebung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="69af5-247">In the **Script Task Editor**, on the **Script** page, click **Edit Script** to open the script development environment.</span></span>  
  
7.  <span data-ttu-id="69af5-248">Geben Sie in der Main-Prozedur Code ein, um einen Fehler zu protokollieren, indem Sie die `Dts.Log`-Methode aufrufen, oder um ein Ereignis auszulösen, indem Sie eine der Methoden der `Dts.Events`-Schnittstelle aufrufen.</span><span class="sxs-lookup"><span data-stu-id="69af5-248">In the Main procedure, enter code to log an error by calling the `Dts.Log` method, or to raise an event by calling one of the methods of the `Dts.Events` interface.</span></span> <span data-ttu-id="69af5-249">Informieren Sie das Paket über den Fehler, indem Sie `Dts.TaskResult = Dts.Results.Failure`zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="69af5-249">Inform the package of the error by returning `Dts.TaskResult = Dts.Results.Failure`.</span></span>  
  
     <span data-ttu-id="69af5-250">Im folgenden Beispiel wird gezeigt, wie eine Meldung ins Protokoll geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="69af5-250">The following sample shows how to write a message to the log.</span></span> <span data-ttu-id="69af5-251">Weitere Informationen finden Sie unter [Logging in the Script Task](../extending-packages-scripting/task/logging-in-the-script-task.md), [Raising Events in the Script Task](../extending-packages-scripting/task/raising-events-in-the-script-task.md)und [Returning Results from the Script Task](../extending-packages-scripting/task/returning-results-from-the-script-task.md).</span><span class="sxs-lookup"><span data-stu-id="69af5-251">For more information, see [Logging in the Script Task](../extending-packages-scripting/task/logging-in-the-script-task.md), [Raising Events in the Script Task](../extending-packages-scripting/task/raising-events-in-the-script-task.md), and [Returning Results from the Script Task](../extending-packages-scripting/task/returning-results-from-the-script-task.md).</span></span>  
  
    ```  
    ' User variables.  
    Dim dataReady As Integer = _  
      CType(Dts.Variables("DataReady").Value, Integer)  
    Dim extractStartTime As Date = _  
      CType(Dts.Variables("ExtractStartTime").Value, DateTime)  
  
    ' System variables.  
    Dim packageName As String = _  
      Dts.Variables("PackageName").Value.ToString()  
    Dim executionStartTime As Date = _  
      CType(Dts.Variables("StartTime").Value, DateTime)  
  
    Dim eventMessage As New System.Text.StringBuilder()  
  
    If dataReady = 1 OrElse dataReady = 5 Then  
  
      If dataReady = 1 Then  
        eventMessage.AppendLine("Start Time Error")  
      Else  
        eventMessage.AppendLine("Timeout Error")  
      End If  
  
      With eventMessage  
        .Append("The package ")  
        .Append(packageName)  
        .Append(" started at ")  
        .Append(executionStartTime.ToString())  
        .Append(" and ended at ")  
        .AppendLine(DateTime.Now().ToString())  
        If dataReady = 1 Then  
          .Append("The specified ExtractStartTime was ")  
          .AppendLine(extractStartTime.ToString())  
        End If  
      End With  
  
      System.Windows.Forms.MessageBox.Show(eventMessage.ToString())  
  
      Dts.Log(eventMessage.ToString(), 0, Nothing)  
  
      Dts.TaskResult = Dts.Results.Failure  
  
    Else  
  
      Dts.TaskResult = Dts.Results.Success  
  
    End If  
  
    ```  
  
8.  <span data-ttu-id="69af5-252">Schließen Sie die Skriptentwicklungsumgebung und den **Skripttask-Editor**.</span><span class="sxs-lookup"><span data-stu-id="69af5-252">Close the script development environment and the **Script Task Editor**.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="69af5-253">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="69af5-253">Next Step</span></span>  
 <span data-ttu-id="69af5-254">Nachdem Sie ermittelt haben, dass die Änderungsdaten bereit sind, müssen Sie im nächsten Schritt die Abfrage der Änderungsdaten vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="69af5-254">After you determine that change data is ready, the next step is to prepare to query for the change data.</span></span>  
  
 <span data-ttu-id="69af5-255">**Nächstes Thema:** [Vorbereiten zur Abfrage der Änderungsdaten](prepare-to-query-for-the-change-data.md)</span><span class="sxs-lookup"><span data-stu-id="69af5-255">**Next topic:** [Prepare to Query for the Change Data](prepare-to-query-for-the-change-data.md)</span></span>  
  
  
