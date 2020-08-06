---
title: Verwenden eines Recordsetziels | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Recordset destination
ms.assetid: a7b143dc-8008-404f-83b0-b45ffbca6029
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 34d1d5a7aa76876a9d8718b691b1d24a8835e2e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621074"
---
# <a name="use-a-recordset-destination"></a><span data-ttu-id="1b438-102">Verwenden eines Recordsetziels</span><span class="sxs-lookup"><span data-stu-id="1b438-102">Use a Recordset Destination</span></span>
  <span data-ttu-id="1b438-103">Das Recordsetziel speichert keine Daten in einer externen Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="1b438-103">The Recordset destination does not save data to an external data source.</span></span> <span data-ttu-id="1b438-104">Stattdessen speichert das Recordsetziel Daten im Speicher eines Recordsets, das in einer [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Paketvariablen des Datentyps `Object` gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="1b438-104">Instead, the Recordset destination saves data in memory in a recordset that is stored in an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package variable of the `Object` data type.</span></span> <span data-ttu-id="1b438-105">Nachdem die Daten vom Recordsetziel gespeichert wurden, verwenden Sie typischerweise einen Foreach-Schleifencontainer mit dem Foreach-ADO-Enumerator zum Verarbeiten jeweils einer Zeile des Recordsets.</span><span class="sxs-lookup"><span data-stu-id="1b438-105">After the Recordset destination saves the data, you typically use a Foreach Loop container with the Foreach ADO enumerator to process one row of the recordset at a time.</span></span> <span data-ttu-id="1b438-106">Der Foreach-ADO-Enumerator speichert den Wert jeder einzelnen Spalte für die aktuelle Zeile in einer separaten Paketvariablen.</span><span class="sxs-lookup"><span data-stu-id="1b438-106">The Foreach ADO enumerator saves the value from each column of the current row into a separate package variable.</span></span> <span data-ttu-id="1b438-107">Anschließend lesen die im Foreach-Schleifencontainer konfigurierten Tasks diese Werte in den Variablen und führen für diese Aktionen aus.</span><span class="sxs-lookup"><span data-stu-id="1b438-107">Then, the tasks that you configure inside the Foreach Loop container read those values from the variables and perform some action with them.</span></span>  
  
 <span data-ttu-id="1b438-108">Sie können das Recordsetziel in vielen verschiedenen Szenarios verwenden.</span><span class="sxs-lookup"><span data-stu-id="1b438-108">You can use the Recordset destination in many different scenarios.</span></span> <span data-ttu-id="1b438-109">Im Folgenden finden Sie einige Beispiele:</span><span class="sxs-lookup"><span data-stu-id="1b438-109">Here are some examples:</span></span>  
  
-   <span data-ttu-id="1b438-110">Mit einem Task „Mail senden“ und der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Ausdruckssprache können Sie für jede Zeile im Recordset eine benutzerdefinierte E-Mail-Nachricht senden.</span><span class="sxs-lookup"><span data-stu-id="1b438-110">You can use a Send Mail task and the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expression language to send a customized e-mail message for each row in the recordset.</span></span>  
  
-   <span data-ttu-id="1b438-111">Mit einer in einem Datenflusstask als Quelle konfigurierten Skriptkomponente können Sie die Spaltenwerte in die Spalten des Datenflusses einlesen.</span><span class="sxs-lookup"><span data-stu-id="1b438-111">You can use a Script component configured as a source, inside a Data Flow task, to read the column values into the columns of the data flow.</span></span> <span data-ttu-id="1b438-112">Dann können Sie Transformationen und Ziele verwenden, um die Zeile zu transformieren und zu speichern.</span><span class="sxs-lookup"><span data-stu-id="1b438-112">Then, you can use transformations and destinations to transform and save the row.</span></span> <span data-ttu-id="1b438-113">In diesem Beispiel wird der Datenflusstask für jede Zeile einmal ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1b438-113">In this example, the Data Flow task runs once for each row.</span></span>  
  
 <span data-ttu-id="1b438-114">In den folgenden Abschnitten wird zuerst der allgemeine Vorgang bei der Verwendung des Recordsetziels beschrieben, anschließend wird ein spezielles Beispiel für die Verwendung des Ziels gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1b438-114">The following sections first describe the general process of using the Recordset destination and then show a specific example of how to use the destination.</span></span>  
  
## <a name="general-steps-to-using-a-recordset-destination"></a><span data-ttu-id="1b438-115">Allgemeine Schritte bei der Verwendung eines Recordsetziels</span><span class="sxs-lookup"><span data-stu-id="1b438-115">General Steps to Using a Recordset Destination</span></span>  
 <span data-ttu-id="1b438-116">Im folgenden Verfahren sind die zum Speichern von Daten in einem Recordsetziel und anschließenden Verarbeiten der einzelnen Zeilen mit dem Foreach-Schleifencontainer erforderlichen Schritte zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="1b438-116">The following procedure summarizes the steps that are required to save data to a Recordset destination, and then use the Foreach Loop container to process each row.</span></span>  
  
#### <a name="to-save-data-to-a-recordset-destination-and-process-each-row-by-using-the-foreach-loop-container"></a><span data-ttu-id="1b438-117">So speichern Sie Daten in einem Recordsetziel und verarbeiten jede einzelne Zeile mit dem Foreach-Schleifencontainer</span><span class="sxs-lookup"><span data-stu-id="1b438-117">To save data to a Recordset destination and process each row by using the Foreach Loop container</span></span>  
  
1.  <span data-ttu-id="1b438-118">Erstellen oder öffnen Sie ein [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]-Paket in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1b438-118">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], create or open an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package.</span></span>  
  
2.  <span data-ttu-id="1b438-119">Erstellen Sie eine Variable für das vom Recordsetziel im Speicher gespeicherte Recordset, und legen Sie den Variablentyp auf `Object` fest.</span><span class="sxs-lookup"><span data-stu-id="1b438-119">Create a variable that will contain the recordset saved into memory by the Recordset destination, and set the variable's type to `Object`.</span></span>  
  
3.  <span data-ttu-id="1b438-120">Erstellen Sie zusätzliche Variablen der entsprechenden Typen für die Werte der einzelnen Spalten im zu verwendenden Recordset.</span><span class="sxs-lookup"><span data-stu-id="1b438-120">Create additional variables of the appropriate types to contain the values of each column in the recordset that you want to use.</span></span>  
  
4.  <span data-ttu-id="1b438-121">Fügen Sie den Verbindungs-Manager hinzu, der für die Datenquelle für den Datenfluss erforderlich ist, und konfigurieren Sie diesen.</span><span class="sxs-lookup"><span data-stu-id="1b438-121">Add and configure the connection manager required by the data source that you plan to use in your data flow.</span></span>  
  
5.  <span data-ttu-id="1b438-122">Fügen Sie dem Paket einen Datenflusstask hinzu, und konfigurieren Sie auf der Registerkarte Datenfluss des [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designers Quellen und Transformationen zum Laden und Transformieren der Daten.</span><span class="sxs-lookup"><span data-stu-id="1b438-122">Add a Data Flow task to the package, and on the Data Flow tab of [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, configure sources and transformations to load and transform the data.</span></span>  
  
6.  <span data-ttu-id="1b438-123">Fügen Sie dem Datenfluss ein Recordsetziel hinzu, und stellen Sie eine Verbindung mit den Transformationen her.</span><span class="sxs-lookup"><span data-stu-id="1b438-123">Add a Recordset destination to the data flow and connect it to the transformations.</span></span> <span data-ttu-id="1b438-124">Geben Sie für die `VariableName`-Eigenschaft des Recordsetziels den Namen der Variablen ein, die das Recordset aufnehmen soll.</span><span class="sxs-lookup"><span data-stu-id="1b438-124">For the `VariableName` property of the Recordset destination, enter the name of the variable that you created to hold the recordset.</span></span>  
  
7.  <span data-ttu-id="1b438-125">Fügen Sie auf der Registerkarte „Ablaufsteuerung“ des [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designers einen Foreach-Schleifencontainer hinzu, und verbinden Sie diesen Container nach dem Datenflusstask.</span><span class="sxs-lookup"><span data-stu-id="1b438-125">On the Control Flow tab of [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, add a Foreach Loop container and connect this container after the Data Flow task.</span></span> <span data-ttu-id="1b438-126">Öffnen Sie dann den **Foreach-Schleifen-Editor** , um den Container mit den folgenden Einstellungen zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="1b438-126">Then, open the **Foreach Loop Editor** to configure the container with the following settings:</span></span>  
  
    1.  <span data-ttu-id="1b438-127">Wählen Sie auf der Seite **Sammlung** den Foreach-ADO-Enumerator aus.</span><span class="sxs-lookup"><span data-stu-id="1b438-127">On the **Collection** page, select the Foreach ADO Enumerator.</span></span> <span data-ttu-id="1b438-128">Wählen Sie dann unter **ADO-Objektquellvariable**die Variable aus, die das Recordset enthält.</span><span class="sxs-lookup"><span data-stu-id="1b438-128">Then, for **ADO object source variable**, select the variable that contains the recordset.</span></span>  
  
    2.  <span data-ttu-id="1b438-129">Ordnen Sie auf der Seite **Variablenzuordnungen** den nullbasierten Index der einzelnen zu verwendenden Spalten der entsprechenden Variablen zu.</span><span class="sxs-lookup"><span data-stu-id="1b438-129">On the **Variable Mappings** page, map the zero-based index of each column that you want to use to the appropriate variable.</span></span>  
  
         <span data-ttu-id="1b438-130">Bei jeder Iteration der Schleife füllt der Enumerator diese Variablen mit den Spaltenwerten aus der aktuellen Zeile auf.</span><span class="sxs-lookup"><span data-stu-id="1b438-130">On each iteration of the loop, the enumerator populates these variables with the column values from the current row.</span></span>  
  
8.  <span data-ttu-id="1b438-131">Fügen Sie im Foreach-Schleifencontainer Tasks zum Verarbeiten jeweils einer Zeile des Recordsets durch Lesen der Variablenwerte hinzu, und konfigurieren Sie diese.</span><span class="sxs-lookup"><span data-stu-id="1b438-131">Inside the Foreach Loop container, add and configure tasks to process one row of the recordset at a time by reading the values from the variables.</span></span>  
  
## <a name="example-of-using-the-recordset-destination"></a><span data-ttu-id="1b438-132">Beispiel für die Verwendung des Recordsetziels</span><span class="sxs-lookup"><span data-stu-id="1b438-132">Example of Using the Recordset Destination</span></span>  
 <span data-ttu-id="1b438-133">Im folgenden Beispiel lädt der Datenflusstask Informationen zu [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] -Mitarbeitern aus der Sales.SalesPerson-Tabelle in ein Recordsetziel.</span><span class="sxs-lookup"><span data-stu-id="1b438-133">In the following example, the Data Flow task loads information about [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] employees from the Sales.SalesPerson table into a Recordset destination.</span></span> <span data-ttu-id="1b438-134">Anschließend liest ein Foreach-Schleifencontainer jeweils eine Datenzeile und ruft einen Task "Mail senden" auf.</span><span class="sxs-lookup"><span data-stu-id="1b438-134">Then, a Foreach Loop container reads one row of data at a time, and calls a Send Mail task.</span></span> <span data-ttu-id="1b438-135">Der Task "Mail senden" verwendet Ausdrücke zum Senden benutzerdefinierter E-Mail-Nachrichten an die einzelnen Vertriebsmitarbeiter, in der deren Bonussummen angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="1b438-135">The Send Mail task uses expressions to send a customized e-mail message to each salesperson about the amount of his or her bonus.</span></span>  
  
#### <a name="to-create-the-project-and-configure-the-variables"></a><span data-ttu-id="1b438-136">So erstellen Sie das Projekt und konfigurieren die Variablen</span><span class="sxs-lookup"><span data-stu-id="1b438-136">To create the project and configure the variables</span></span>  
  
1.  <span data-ttu-id="1b438-137">Erstellen Sie in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]ein neues [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Projekt.</span><span class="sxs-lookup"><span data-stu-id="1b438-137">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], create a new [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="1b438-138">Wählen Sie im Menü **SSIS** den Befehl **Variablen**aus.</span><span class="sxs-lookup"><span data-stu-id="1b438-138">On the **SSIS** menu, select **Variables**.</span></span>  
  
3.  <span data-ttu-id="1b438-139">Erstellen Sie im Fenster **Variablen** die Variablen für das Recordset sowie die Spaltenwerte in der aktuellen Zeile:</span><span class="sxs-lookup"><span data-stu-id="1b438-139">In the **Variables** window, create the variables that will hold the recordset and the column values from the current row:</span></span>  
  
    1.  <span data-ttu-id="1b438-140">Erstellen Sie die Variable `BonusRecordset`, und legen Sie deren Typ auf `Object` fest.</span><span class="sxs-lookup"><span data-stu-id="1b438-140">Create a variable named, `BonusRecordset`, and set its type to `Object`.</span></span>  
  
         <span data-ttu-id="1b438-141">Die Variable `BonusRecordset` enthält das Recordset.</span><span class="sxs-lookup"><span data-stu-id="1b438-141">The `BonusRecordset` variable holds the recordset.</span></span>  
  
    2.  <span data-ttu-id="1b438-142">Erstellen Sie die Variable `EmailAddress`, und legen Sie deren Typ auf `String` fest.</span><span class="sxs-lookup"><span data-stu-id="1b438-142">Create a variable named, `EmailAddress`, and set its type to `String`.</span></span>  
  
         <span data-ttu-id="1b438-143">Die Variable `EmailAddress` enthält die E-Mail-Adresse der Vertriebsperson.</span><span class="sxs-lookup"><span data-stu-id="1b438-143">The `EmailAddress` variable holds the salesperson's e-mail address.</span></span>  
  
    3.  <span data-ttu-id="1b438-144">Erstellen Sie die Variable `FirstName`, und legen Sie deren Typ auf `String` fest.</span><span class="sxs-lookup"><span data-stu-id="1b438-144">Create a variable named, `FirstName`, and set its type to `String`.</span></span>  
  
         <span data-ttu-id="1b438-145">Die Variable `FirstName` enthält den Vornamen der Vertriebsperson.</span><span class="sxs-lookup"><span data-stu-id="1b438-145">The `FirstName` variable holds the salesperson's first name.</span></span>  
  
    4.  <span data-ttu-id="1b438-146">Erstellen Sie die Variable `Bonus`, und legen Sie deren Typ auf `Double` fest.</span><span class="sxs-lookup"><span data-stu-id="1b438-146">Create a variable named, `Bonus`, and set its type to `Double`.</span></span>  
  
         <span data-ttu-id="1b438-147">Die Variable `Bonus` enthält den Betrag für den Bonus der Vertriebsperson.</span><span class="sxs-lookup"><span data-stu-id="1b438-147">The `Bonus` variable holds the amount of the salesperson's bonus.</span></span>  
  
#### <a name="to-configure-the-connection-managers"></a><span data-ttu-id="1b438-148">So konfigurieren Sie die Verbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="1b438-148">To configure the connection managers</span></span>  
  
1.  <span data-ttu-id="1b438-149">Fügen Sie im Bereich Verbindungs-Manager des [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designers einen neuen OLE DB-Verbindungs-Manager hinzu, mit dem eine Verbindung mit der [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] -Beispieldatenbank hergestellt wird, und konfigurieren Sie diesen.</span><span class="sxs-lookup"><span data-stu-id="1b438-149">In the Connection Managers area of the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, add and configure a new OLE DB connection manager that connects to the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] sample database.</span></span>  
  
     <span data-ttu-id="1b438-150">Die OLE DB-Quelle im Datenflusstask verwendet diesen Verbindungs-Manager zum Abrufen von Daten.</span><span class="sxs-lookup"><span data-stu-id="1b438-150">The OLE DB source in the Data Flow task will use this connection manager to retrieve data.</span></span>  
  
2.  <span data-ttu-id="1b438-151">Fügen Sie im Bereich Verbindungs-Manager einen neuen SMTP-Verbindungs-Manager hinzu, mit dem eine Verbindung mit einem verfügbaren SMTP-Server hergestellt wird, und konfigurieren Sie diesen.</span><span class="sxs-lookup"><span data-stu-id="1b438-151">In the Connection Managers area, add and configure a new SMTP connection manager that connects to an available SMTP server.</span></span>  
  
     <span data-ttu-id="1b438-152">Der Task "Mail senden" im Foreach-Schleifencontainer verwendet diesen Verbindungs-Manager zum Senden von E-Mail-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="1b438-152">The Send Mail task inside the Foreach Loop container will use this connection manager to send emails.</span></span>  
  
#### <a name="to-configure-the-data-flow-and-the-recordset-destination"></a><span data-ttu-id="1b438-153">So konfigurieren Sie den Datenfluss und das Recordsetziel</span><span class="sxs-lookup"><span data-stu-id="1b438-153">To configure the data flow and the Recordset Destination</span></span>  
  
1.  <span data-ttu-id="1b438-154">Fügen Sie auf der Registerkarte **Ablaufsteuerung** des [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designers der Entwurfsoberfläche einen Datenflusstask hinzu.</span><span class="sxs-lookup"><span data-stu-id="1b438-154">On the **Control Flow** tab of [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, add a Data Flow task to the design surface.</span></span>  
  
2.  <span data-ttu-id="1b438-155">Fügen Sie dem Datenflusstask auf der Registerkarte **Datenfluss** eine OLE DB-Datenquelle hinzu, und öffnen Sie dann den **Quellen-Editor für OLE DB.**</span><span class="sxs-lookup"><span data-stu-id="1b438-155">On the **Data Flow** tab, add an OLE DB source to the Data Flow task, and then open the **OLE DB Source Editor.**</span></span>  
  
3.  <span data-ttu-id="1b438-156">Konfigurieren Sie auf der Seite **Verbindungs-Manager** des Editors die Quelle mit den folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="1b438-156">On the **Connection Manager** page of the editor, configure the source with the following settings:</span></span>  
  
    1.  <span data-ttu-id="1b438-157">Wählen Sie unter **OLE DB-Verbindungs-Manager**den zuvor erstellten OLE DB-Verbindungs-Manager aus.</span><span class="sxs-lookup"><span data-stu-id="1b438-157">For **OLE DB connection manager**, select the OLE DB connection manager that you previously created.</span></span>  
  
    2.  <span data-ttu-id="1b438-158">Wählen Sie unter **Datenzugriffsmodus**die Option **SQL-Befehl**aus.</span><span class="sxs-lookup"><span data-stu-id="1b438-158">For **Data access mode**, select **SQL command**.</span></span>  
  
    3.  <span data-ttu-id="1b438-159">Geben Sie unter **SQL-Befehlstext**die folgende Abfrage ein:</span><span class="sxs-lookup"><span data-stu-id="1b438-159">For **SQL command text**, enter the following query:</span></span>  
  
        ```  
        SELECT     Person.Contact.EmailAddress, Person.Contact.FirstName, CONVERT(float, Sales.SalesPerson.Bonus) AS Bonus  
        FROM         Sales.SalesPerson INNER JOIN  
                              Person.Contact ON Sales.SalesPerson.SalesPersonID = Person.Contact.ContactID  
        ```  
  
        > [!NOTE]  
        >  <span data-ttu-id="1b438-160">Sie müssen den `currency`-Wert in der Bonus-Spalte in den Datentyp `float` konvertieren, bevor Sie diesen in eine Paketvariable vom Typ `Double` laden können.</span><span class="sxs-lookup"><span data-stu-id="1b438-160">You have to convert the `currency` value in the Bonus column to a `float` before you can load that value into a package variable whose type is `Double`.</span></span>  
  
4.  <span data-ttu-id="1b438-161">Fügen Sie auf der Registerkarte **Datenfluss** ein Recordsetziel hinzu, und stellen Sie eine Verbindung mit dem Ziel nach der der OLE DB-Quelle her.</span><span class="sxs-lookup"><span data-stu-id="1b438-161">On the **Data Flow** tab, add a Recordset destination, and connect the destination after the OLE DB source.</span></span>  
  
5.  <span data-ttu-id="1b438-162">Öffnen Sie den **Recordsetziel-Editor**, und konfigurieren Sie das Ziel mit den folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="1b438-162">Open the **Recordset Destination Editor**, and configure the destination with the following settings:</span></span>  
  
    1.  <span data-ttu-id="1b438-163">Wählen Sie auf der Registerkarte **Komponenteneigenschaften** für Eigenschaft die Option aus `VariableName` `User::BonusRecordset` .</span><span class="sxs-lookup"><span data-stu-id="1b438-163">On the **Component Properties** tab, for `VariableName` property, select `User::BonusRecordset`.</span></span>  
  
    2.  <span data-ttu-id="1b438-164">Wählen Sie auf der Registerkarte **Eingabespalten** alle drei verfügbaren Spalten aus.</span><span class="sxs-lookup"><span data-stu-id="1b438-164">On the **Input Columns** tab, select all three of the available columns.</span></span>  
  
#### <a name="to-configure-the-foreach-loop-container-and-run-the-package"></a><span data-ttu-id="1b438-165">So konfigurieren Sie den Foreach-Schleifencontainer und führen das Paket aus</span><span class="sxs-lookup"><span data-stu-id="1b438-165">To configure the Foreach Loop container and run the package</span></span>  
  
1.  <span data-ttu-id="1b438-166">Fügen Sie auf der Registerkarte **Ablaufsteuerung** des [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designers einen Foreach-Schleifencontainer hinzu, und verbinden Sie den Container nach dem Datenflusstask.</span><span class="sxs-lookup"><span data-stu-id="1b438-166">On the **Control Flow** tab of [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, add a Foreach Loop container, and connect the container after the Data Flow task.</span></span>  
  
2.  <span data-ttu-id="1b438-167">Öffnen Sie den **Foreach-Schleifen-Editor**, und konfigurieren Sie den Container mit den folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="1b438-167">Open the **Foreach Loop Editor**, and configure the container with the following settings:</span></span>  
  
    1.  <span data-ttu-id="1b438-168">Wählen Sie **auf der Seite** **Auflistung für Enumerator**die Option **Foreach-ADO-Enumerator**und unter **ADO-Objekt Quellvariable**die Option aus `User::BonusRecordset` .</span><span class="sxs-lookup"><span data-stu-id="1b438-168">On the **Collection** page, for **Enumerator**, select **Foreach ADO Enumerator**, and for **ADO object source variable**, select `User::BonusRecordset`.</span></span>  
  
    2.  <span data-ttu-id="1b438-169">Ordnen Sie auf der Seite **Variablen** Zuordnungen dem Index `User::EmailAddress` 0, `User::FirstName` dem Index 1 und dem `User::Bonus` Index 2 zu.</span><span class="sxs-lookup"><span data-stu-id="1b438-169">On the **Variable Mappings** page, map `User::EmailAddress` to index 0, `User::FirstName` to index 1, and `User::Bonus` to index 2.</span></span>  
  
3.  <span data-ttu-id="1b438-170">Fügen Sie auf der Registerkarte **Ablaufsteuerung** im Foreach-Schleifencontainer einen Task „Mail senden“ hinzu.</span><span class="sxs-lookup"><span data-stu-id="1b438-170">On the **Control Flow** tab, inside the Foreach Loop container, add a Send Mail task.</span></span>  
  
4.  <span data-ttu-id="1b438-171">Öffnen Sie den **Editor für den Task „Mail senden“** , und konfigurieren Sie auf der Seite **E-Mail** den Task mit den folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="1b438-171">Open the **Send Mail Task Editor**, and then on the **Mail** page, configure the task with the following settings:</span></span>  
  
    1.  <span data-ttu-id="1b438-172">Wählen Sie für **SmtpConnection**den SMTP-Verbindungs-Manager aus, der zuvor konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="1b438-172">For **SmtpConnection**, select the SMTP connection manager that was configured previously.</span></span>  
  
    2.  <span data-ttu-id="1b438-173">Geben Sie unter **From**eine geeignete E-Mail-Adresse ein.</span><span class="sxs-lookup"><span data-stu-id="1b438-173">For **From**, enter an appropriate e-mail address.</span></span>  
  
         <span data-ttu-id="1b438-174">Wenn Sie Ihre eigene E-Mail-Adresse verwenden, können Sie überprüfen, ob das Paket erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1b438-174">If you use your own e-mail address, you will be able to confirm that the package runs successfully.</span></span> <span data-ttu-id="1b438-175">Für Nachrichten, die vom Task „Mail senden“ an die fiktiven Vertriebspersonen von [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)]gesendet wurden, erhalten Sie Unzustellbarkeitsmeldungen.</span><span class="sxs-lookup"><span data-stu-id="1b438-175">You will receive undeliverable receipts for the messages sent by the Send Mail task to the fictitious salespersons of [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)].</span></span>  
  
    3.  <span data-ttu-id="1b438-176">Geben Sie unter **To**eine Standard-E-Mail-Adresse ein.</span><span class="sxs-lookup"><span data-stu-id="1b438-176">For **To**, enter a default e-mail address.</span></span>  
  
         <span data-ttu-id="1b438-177">Dieser Wert wird nicht verwendet, sondern zur Laufzeit durch die E-Mail-Adresse der betreffenden Vertriebsperson ersetzt.</span><span class="sxs-lookup"><span data-stu-id="1b438-177">This value will not be used, but will be replaced at run time by the e-mail address of each salesperson.</span></span>  
  
    4.  <span data-ttu-id="1b438-178">Geben Sie unter **Subject**„Ihr Jahresbonus“ ein.</span><span class="sxs-lookup"><span data-stu-id="1b438-178">For **Subject**, enter "Your annual bonus".</span></span>  
  
    5.  <span data-ttu-id="1b438-179">Wählen Sie für **MessageSourceType**die Option **Direkteingabe**aus.</span><span class="sxs-lookup"><span data-stu-id="1b438-179">For **MessageSourceType**, select **Direct Input**.</span></span>  
  
5.  <span data-ttu-id="1b438-180">Klicken Sie auf der Seite **Ausdrücke** des **Editors für den Task „Mail senden“** auf die Schaltfläche mit den drei Punkten ( **...** ), um den **Eigenschaftsausdrucks-Editor**zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="1b438-180">On the **Expressions** page of the **Send Mail Task Editor**, click the ellipsis button (**...**) to open the **Property Expressions Editor**.</span></span>  
  
6.  <span data-ttu-id="1b438-181">Geben Sie im **Eigenschaftsausdrucks-Editor**die folgenden Informationen ein:</span><span class="sxs-lookup"><span data-stu-id="1b438-181">In the **Property Expressions Editor**, enter the following information:</span></span>  
  
    1.  <span data-ttu-id="1b438-182">Fügen Sie unter **ToLine**den folgenden Ausdruck hinzu:</span><span class="sxs-lookup"><span data-stu-id="1b438-182">For **ToLine**, add the following expression:</span></span>  
  
        ```  
        @[User::EmailAddress]  
        ```  
  
    2.  <span data-ttu-id="1b438-183">Fügen Sie für die **MessageSource** -Eigenschaft den folgenden Ausdruck hinzu:</span><span class="sxs-lookup"><span data-stu-id="1b438-183">For the **MessageSource** property, add the following expression:</span></span>  
  
        ```  
        "Dear " +  @[User::FirstName] + ": The amount of your bonus for this year is $" +  (DT_WSTR, 12) @[User::Bonus] + ". Thank you!"  
        ```  
  
7.  <span data-ttu-id="1b438-184">Führen Sie das Paket aus.</span><span class="sxs-lookup"><span data-stu-id="1b438-184">Run the package.</span></span>  
  
     <span data-ttu-id="1b438-185">Wenn Sie einen gültigen SMTP-Server und Ihre eigene E-Mail-Adresse angegeben haben, erhalten Sie für die Nachrichten, die vom Task "Mail senden" an die fiktiven Vertriebspersonen von [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)]gesendet wurden, Unzustellbarkeitsmeldungen.</span><span class="sxs-lookup"><span data-stu-id="1b438-185">If you have specified a valid SMTP server and provided your own e-mail address, you will receive undeliverable receipts for the messages that the Send Mail task sends to the fictitious salespersons of [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)].</span></span>  
  
  
