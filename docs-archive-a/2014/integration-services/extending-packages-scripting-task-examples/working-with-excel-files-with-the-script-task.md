---
title: Arbeiten mit Excel-Dateien mit dem Skripttask | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script task [Integration Services], Excel files
- Script task [Integration Services], examples
- Excel [Integration Services]
ms.assetid: b8fa110a-2c9c-4f5a-8fe1-305555640e44
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 68a764452de548cd46e74d2a7f2f588a050a21c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618206"
---
# <a name="working-with-excel-files-with-the-script-task"></a><span data-ttu-id="54eb9-102">Arbeiten mit Excel-Dateien mit dem Skripttask</span><span class="sxs-lookup"><span data-stu-id="54eb9-102">Working with Excel Files with the Script Task</span></span>
  [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="54eb9-103">stellt den Excel-Verbindungs-Manager, die Excel-Quelle und das Excel-Ziel zum Arbeiten mit den in Kalkulationstabellen gespeicherten Daten im [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel-Dateiformat bereit.</span><span class="sxs-lookup"><span data-stu-id="54eb9-103">provides the Excel connection manager, Excel source, and Excel destination for working with data stored in spreadsheets in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel file format.</span></span> <span data-ttu-id="54eb9-104">Die in diesem Thema beschriebenen Verfahren verwenden den Skripttask zum Abrufen von Informationen über verfügbare Excel-Datenbanken (Arbeitsmappendateien) und -Tabellen (Arbeitsmappen und benannte Bereiche).</span><span class="sxs-lookup"><span data-stu-id="54eb9-104">The techniques described in this topic use the Script task to obtain information about available Excel databases (workbook files) and tables (worksheets and named ranges).</span></span> <span data-ttu-id="54eb9-105">Diese Beispiele können leicht geändert werden, um mit einer der anderen vom [!INCLUDE[msCoName](../../includes/msconame-md.md)] Jet OLE DB-Anbieter unterstützten dateibasierten Datenquellen zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="54eb9-105">These samples can easily be modified to work with any of the other file-based data sources supported by the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Jet OLE DB Provider.</span></span>  
  
 [<span data-ttu-id="54eb9-106">Konfigurieren eines Pakets zum Testen der Beispiele</span><span class="sxs-lookup"><span data-stu-id="54eb9-106">Configuring a Package to Test the Samples</span></span>](#configuring)  
  
 [<span data-ttu-id="54eb9-107">Beispiel 1: Überprüfen, ob eine Excel-Datei vorhanden ist</span><span class="sxs-lookup"><span data-stu-id="54eb9-107">Example1: Check Whether an Excel File Exists</span></span>](#example1)  
  
 [<span data-ttu-id="54eb9-108">Beispiel 2: Überprüfen, ob eine Excel-Tabelle vorhanden ist</span><span class="sxs-lookup"><span data-stu-id="54eb9-108">Example 2: Check Whether an Excel Table Exists</span></span>](#example2)  
  
 [<span data-ttu-id="54eb9-109">Beispiel 3: Abrufen einer Liste der Excel-Dateien in einem Ordner</span><span class="sxs-lookup"><span data-stu-id="54eb9-109">Example 3: Get a List of Excel Files in a Folder</span></span>](#example3)  
  
 [<span data-ttu-id="54eb9-110">Beispiel 4: Abrufen einer Liste der Tabellen in einer Excel-Datei</span><span class="sxs-lookup"><span data-stu-id="54eb9-110">Example 4: Get a List of Tables in an Excel File</span></span>](#example4)  
  
 [<span data-ttu-id="54eb9-111">Anzeigen der Ergebnisse der Beispiele</span><span class="sxs-lookup"><span data-stu-id="54eb9-111">Displaying the Results of the Samples</span></span>](#testing)  
  
> [!NOTE]  
>  <span data-ttu-id="54eb9-112">Wenn Sie einen Task erstellen möchten, den Sie einfacher in mehreren Paketen wiederverwenden können, empfiehlt es sich, den Code in diesem Skripttaskbeispiel als Ausgangspunkt für einen benutzerdefinierten Task zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="54eb9-112">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="54eb9-113">Weitere Informationen finden Sie unter [Entwickeln eines benutzerdefinierten Tasks](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="54eb9-113">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
##  <a name="configuring-a-package-to-test-the-samples"></a><a name="configuring"></a><span data-ttu-id="54eb9-114">Konfigurieren eines Pakets zum Testen der Beispiele</span><span class="sxs-lookup"><span data-stu-id="54eb9-114">Configuring a Package to Test the Samples</span></span>  
 <span data-ttu-id="54eb9-115">Sie können ein einzelnes Paket konfigurieren, um alle Beispiele in diesem Thema zu testen.</span><span class="sxs-lookup"><span data-stu-id="54eb9-115">You can configure a single package to test all the samples in this topic.</span></span> <span data-ttu-id="54eb9-116">In den Beispielen werden oft die gleichen Paketvariablen und die gleichen [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]-Klassen verwendet.</span><span class="sxs-lookup"><span data-stu-id="54eb9-116">The samples use many of the same package variables and the same [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] classes.</span></span>  
  
#### <a name="to-configure-a-package-for-use-with-the-examples-in-this-topic"></a><span data-ttu-id="54eb9-117">So konfigurieren Sie ein Paket zur Verwendung mit den in diesem Thema beschriebenen Beispielen</span><span class="sxs-lookup"><span data-stu-id="54eb9-117">To configure a package for use with the examples in this topic</span></span>  
  
1.  <span data-ttu-id="54eb9-118">Erstellen Sie in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ein neues [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]-Projekt, und öffnen Sie das Standardpaket für die Bearbeitung.</span><span class="sxs-lookup"><span data-stu-id="54eb9-118">Create a new [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] and open the default package for editing.</span></span>  
  
2.  <span data-ttu-id="54eb9-119">**Variablen:**</span><span class="sxs-lookup"><span data-stu-id="54eb9-119">**Variables**.</span></span> <span data-ttu-id="54eb9-120">Öffnen Sie das Fenster **Variablen**, und definieren Sie die folgenden Variablen:</span><span class="sxs-lookup"><span data-stu-id="54eb9-120">Open the **Variables** window and define the following variables:</span></span>  
  
    -   <span data-ttu-id="54eb9-121">`ExcelFile` vom Typ `String`.</span><span class="sxs-lookup"><span data-stu-id="54eb9-121">`ExcelFile`, of type `String`.</span></span> <span data-ttu-id="54eb9-122">Geben Sie den vollständigen Pfad zu einer vorhandenen Excel-Arbeitsmappe und den zugehörigen Dateinamen ein.</span><span class="sxs-lookup"><span data-stu-id="54eb9-122">Enter the complete path and filename to an existing Excel workbook.</span></span>  
  
    -   <span data-ttu-id="54eb9-123">`ExcelTable` vom Typ `String`.</span><span class="sxs-lookup"><span data-stu-id="54eb9-123">`ExcelTable`, of type `String`.</span></span> <span data-ttu-id="54eb9-124">Geben Sie den Namen eines vorhandenen Arbeitsblatts oder eines benannten Bereichs in der Arbeitsmappe ein, der im Wert der `ExcelFile`-Variablen genannt wird.</span><span class="sxs-lookup"><span data-stu-id="54eb9-124">Enter the name of an existing worksheet or named range in the workbook named in the value of the `ExcelFile` variable.</span></span> <span data-ttu-id="54eb9-125">Bei diesem Wert wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="54eb9-125">This value is case-sensitive.</span></span>  
  
    -   <span data-ttu-id="54eb9-126">`ExcelFileExists` vom Typ `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="54eb9-126">`ExcelFileExists`, of type `Boolean`.</span></span>  
  
    -   <span data-ttu-id="54eb9-127">`ExcelTableExists` vom Typ `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="54eb9-127">`ExcelTableExists`, of type `Boolean`.</span></span>  
  
    -   <span data-ttu-id="54eb9-128">`ExcelFolder` vom Typ `String`.</span><span class="sxs-lookup"><span data-stu-id="54eb9-128">`ExcelFolder`, of type `String`.</span></span> <span data-ttu-id="54eb9-129">Geben Sie den vollständigen Pfad eines Ordners ein, der mindestens eine Excel-Arbeitsmappe enthält.</span><span class="sxs-lookup"><span data-stu-id="54eb9-129">Enter the complete path of a folder that contains at least one Excel workbook.</span></span>  
  
    -   <span data-ttu-id="54eb9-130">`ExcelFiles` vom Typ `Object`.</span><span class="sxs-lookup"><span data-stu-id="54eb9-130">`ExcelFiles`, of type `Object`.</span></span>  
  
    -   <span data-ttu-id="54eb9-131">`ExcelTables` vom Typ `Object`.</span><span class="sxs-lookup"><span data-stu-id="54eb9-131">`ExcelTables`, of type `Object`.</span></span>  
  
3.  <span data-ttu-id="54eb9-132">**Imports-Anweisungen.**</span><span class="sxs-lookup"><span data-stu-id="54eb9-132">**Imports statements**.</span></span> <span data-ttu-id="54eb9-133">Für die meisten Codebeispiele müssen am Anfang der Skriptdatei einer oder beide der folgenden [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]-Namespaces importiert werden:</span><span class="sxs-lookup"><span data-stu-id="54eb9-133">Most of the code samples require you to import one or both of the following [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] namespaces at the top of your script file:</span></span>  
  
    -   <span data-ttu-id="54eb9-134">`System.IO` für Dateisystemvorgänge.</span><span class="sxs-lookup"><span data-stu-id="54eb9-134">`System.IO`, for file system operations.</span></span>  
  
    -   <span data-ttu-id="54eb9-135">`System.Data.OleDb` zum Öffnen von Excel-Dateien als Datenquellen.</span><span class="sxs-lookup"><span data-stu-id="54eb9-135">`System.Data.OleDb`, to open Excel files as data sources.</span></span>  
  
4.  <span data-ttu-id="54eb9-136">**Verweise**.</span><span class="sxs-lookup"><span data-stu-id="54eb9-136">**References**.</span></span> <span data-ttu-id="54eb9-137">Für die Codebeispiele, die Schemainformationen in Excel-Dateien lesen, ist ein zusätzlicher Verweis im Skriptprojekt für den `System.Xml`-Namespace erforderlich.</span><span class="sxs-lookup"><span data-stu-id="54eb9-137">The code samples that read schema information from Excel files require an additional reference in the script project to the `System.Xml` namespace.</span></span>  
  
5.  <span data-ttu-id="54eb9-138">Verwenden Sie im Dialogfeld **Optionen** auf der Seite **Allgemein** die Option **Skriptsprache**, um die Standardskriptsprache für die Skriptkomponente festzulegen.</span><span class="sxs-lookup"><span data-stu-id="54eb9-138">Set the default scripting language for the Script component by using the **Scripting language** option on the **General** page of the **Options** dialog box.</span></span> <span data-ttu-id="54eb9-139">Weitere Informationen finden Sie unter [General Page](../general-page-of-integration-services-designers-options.md).</span><span class="sxs-lookup"><span data-stu-id="54eb9-139">For more information, see [General Page](../general-page-of-integration-services-designers-options.md).</span></span>  
  
##  <a name="example-1-description-check-whether-an-excel-file-exists"></a><a name="example1"></a> <span data-ttu-id="54eb9-140">Beschreibung zu Beispiel 1: Überprüfen, ob eine Excel-Datei vorhanden ist</span><span class="sxs-lookup"><span data-stu-id="54eb9-140">Example 1 Description: Check Whether an Excel File Exists</span></span>  
 <span data-ttu-id="54eb9-141">In diesem Beispiel wird überprüft, ob die von der `ExcelFile`-Variable angegebene Excel-Arbeitsmappendatei vorhanden ist. Daraufhin wird der boolesche Wert der `ExcelFileExists`-Variable auf das Ergebnis festgelegt.</span><span class="sxs-lookup"><span data-stu-id="54eb9-141">This example determines whether the Excel workbook file specified in the `ExcelFile` variable exists, and then sets the Boolean value of the `ExcelFileExists` variable to the result.</span></span> <span data-ttu-id="54eb9-142">Sie können diesen booleschen Wert im Workflow des Pakets zur Verzweigung verwenden.</span><span class="sxs-lookup"><span data-stu-id="54eb9-142">You can use this Boolean value for branching in the workflow of the package.</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="54eb9-143">So konfigurieren Sie dieses Skripttaskbeispiel</span><span class="sxs-lookup"><span data-stu-id="54eb9-143">To configure this Script Task example</span></span>  
  
1.  <span data-ttu-id="54eb9-144">Fügen Sie dem Paket einen neuen Skript Task hinzu, und ändern Sie den Namen in `ExcelFileExists` .</span><span class="sxs-lookup"><span data-stu-id="54eb9-144">Add a new Script task to the package and change its name to `ExcelFileExists`.</span></span>  
  
2.  <span data-ttu-id="54eb9-145">Klicken Sie im **Skripttask-Editor** auf der Registerkarte **Skript** auf **ReadOnlyVariables**, und geben Sie den Eigenschaftswert mit einer der folgenden Methoden ein:</span><span class="sxs-lookup"><span data-stu-id="54eb9-145">In the **Script Task Editor**, on the **Script** tab, click **ReadOnlyVariables** and enter the property value using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="54eb9-146">Geben Sie `ExcelFile`ein.</span><span class="sxs-lookup"><span data-stu-id="54eb9-146">Type `ExcelFile`.</span></span>  
  
         <span data-ttu-id="54eb9-147">Oder</span><span class="sxs-lookup"><span data-stu-id="54eb9-147">-or-</span></span>  
  
    -   <span data-ttu-id="54eb9-148">Klicken Sie auf die Schaltfläche mit den Auslassungs Punkten (**...**) neben dem Eigenschafts Feld, und wählen Sie im Dialogfeld **Variablen auswählen** die `ExcelFile` Variable aus.</span><span class="sxs-lookup"><span data-stu-id="54eb9-148">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, select the `ExcelFile` variable.</span></span>  
  
3.  <span data-ttu-id="54eb9-149">Klicken Sie auf **ReadWriteVariables**, und geben Sie den Eigenschaftswert mit einer der folgenden Methoden ein:</span><span class="sxs-lookup"><span data-stu-id="54eb9-149">Click **ReadWriteVariables** and enter the property value using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="54eb9-150">Geben Sie `ExcelFileExists`ein.</span><span class="sxs-lookup"><span data-stu-id="54eb9-150">Type `ExcelFileExists`.</span></span>  
  
         <span data-ttu-id="54eb9-151">Oder</span><span class="sxs-lookup"><span data-stu-id="54eb9-151">-or-</span></span>  
  
    -   <span data-ttu-id="54eb9-152">Klicken Sie auf die Schaltfläche mit den Auslassungs Punkten (**...**) neben dem Eigenschafts Feld, und wählen Sie im Dialogfeld **Variablen auswählen** die `ExcelFileExists` Variable aus.</span><span class="sxs-lookup"><span data-stu-id="54eb9-152">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, select the `ExcelFileExists` variable.</span></span>  
  
4.  <span data-ttu-id="54eb9-153">Klicken Sie zum Öffnen des Skript-Editors auf **Skript bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="54eb9-153">Click **Edit Script** to open the script editor.</span></span>  
  
5.  <span data-ttu-id="54eb9-154">Fügen Sie am Anfang der Skriptdatei eine `Imports`-Anweisung für den `System.IO`-Namespace hinzu.</span><span class="sxs-lookup"><span data-stu-id="54eb9-154">Add an `Imports` statement for the `System.IO` namespace at the top of the script file.</span></span>  
  
6.  <span data-ttu-id="54eb9-155">Fügen Sie den folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="54eb9-155">Add the following code.</span></span>  
  
### <a name="example-1-code"></a><span data-ttu-id="54eb9-156">Codebeispiel 1</span><span class="sxs-lookup"><span data-stu-id="54eb9-156">Example 1 Code</span></span>  
  
```vb  
Public Class ScriptMain  
  Public Sub Main()  
    Dim fileToTest As String  
  
    fileToTest = Dts.Variables("ExcelFile").Value.ToString  
    If File.Exists(fileToTest) Then  
      Dts.Variables("ExcelFileExists").Value = True  
    Else  
      Dts.Variables("ExcelFileExists").Value = False  
    End If  
  
    Dts.TaskResult = ScriptResults.Success  
  End Sub  
End Class  
```  
  
```csharp  
public class ScriptMain  
{  
  public void Main()  
  {  
    string fileToTest;  
  
    fileToTest = Dts.Variables["ExcelFile"].Value.ToString();  
    if (File.Exists(fileToTest))  
    {  
      Dts.Variables["ExcelFileExists"].Value = true;  
    }  
    else  
    {  
      Dts.Variables["ExcelFileExists"].Value = false;  
    }  
  
    Dts.TaskResult = (int)ScriptResults.Success;  
  }  
}  
```  
  
##  <a name="example-2-description-check-whether-an-excel-table-exists"></a><a name="example2"></a> <span data-ttu-id="54eb9-157">Beschreibung zu Beispiel 2: Überprüfen, ob eine Excel-Tabelle vorhanden ist</span><span class="sxs-lookup"><span data-stu-id="54eb9-157">Example 2 Description: Check Whether an Excel Table Exists</span></span>  
 <span data-ttu-id="54eb9-158">In diesem Beispiel wird überprüft, ob das in der `ExcelTable`-Variable angegebene Excel-Arbeitsblatt bzw. der benannte Bereich in der Excel-Arbeitsmappendatei vorhanden ist, die in der `ExcelFile`-Variable angegeben wurde. Daraufhin wird der boolesche Wert der `ExcelTableExists`-Variable auf das Ergebnis festgelegt.</span><span class="sxs-lookup"><span data-stu-id="54eb9-158">This example determines whether the Excel worksheet or named range specified in the `ExcelTable` variable exists in the Excel workbook file specified in the `ExcelFile` variable, and then sets the Boolean value of the `ExcelTableExists` variable to the result.</span></span> <span data-ttu-id="54eb9-159">Sie können diesen booleschen Wert im Workflow des Pakets zur Verzweigung verwenden.</span><span class="sxs-lookup"><span data-stu-id="54eb9-159">You can use this Boolean value for branching in the workflow of the package.</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="54eb9-160">So konfigurieren Sie dieses Skripttaskbeispiel</span><span class="sxs-lookup"><span data-stu-id="54eb9-160">To configure this Script Task example</span></span>  
  
1.  <span data-ttu-id="54eb9-161">Fügen Sie dem Paket einen neuen Skript Task hinzu, und ändern Sie den Namen in `ExcelTableExists` .</span><span class="sxs-lookup"><span data-stu-id="54eb9-161">Add a new Script task to the package and change its name to `ExcelTableExists`.</span></span>  
  
2.  <span data-ttu-id="54eb9-162">Klicken Sie im **Skripttask-Editor** auf der Registerkarte **Skript** auf **ReadOnlyVariables**, und geben Sie den Eigenschaftswert mit einer der folgenden Methoden ein:</span><span class="sxs-lookup"><span data-stu-id="54eb9-162">In the **Script Task Editor**, on the **Script** tab, click **ReadOnlyVariables** and enter the property value using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="54eb9-163">Eingeben `ExcelTable` und `ExcelFile` durch Kommas getrennt`.`</span><span class="sxs-lookup"><span data-stu-id="54eb9-163">Type `ExcelTable` and `ExcelFile` separated by commas`.`</span></span>  
  
         <span data-ttu-id="54eb9-164">Oder</span><span class="sxs-lookup"><span data-stu-id="54eb9-164">-or-</span></span>  
  
    -   <span data-ttu-id="54eb9-165">Klicken Sie auf die Schaltfläche mit den Auslassungs Punkten (**...**) neben dem Eigenschafts Feld, und wählen Sie im Dialogfeld **Variablen auswählen** die `ExcelTable` Variablen und aus `ExcelFile` .</span><span class="sxs-lookup"><span data-stu-id="54eb9-165">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, select the `ExcelTable` and `ExcelFile` variables.</span></span>  
  
3.  <span data-ttu-id="54eb9-166">Klicken Sie auf **ReadWriteVariables**, und geben Sie den Eigenschaftswert mit einer der folgenden Methoden ein:</span><span class="sxs-lookup"><span data-stu-id="54eb9-166">Click **ReadWriteVariables** and enter the property value using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="54eb9-167">Geben Sie `ExcelTableExists`ein.</span><span class="sxs-lookup"><span data-stu-id="54eb9-167">Type `ExcelTableExists`.</span></span>  
  
         <span data-ttu-id="54eb9-168">Oder</span><span class="sxs-lookup"><span data-stu-id="54eb9-168">-or-</span></span>  
  
    -   <span data-ttu-id="54eb9-169">Klicken Sie auf die Schaltfläche mit den Auslassungs Punkten (**...**) neben dem Eigenschafts Feld, und wählen Sie im Dialogfeld **Variablen auswählen** die `ExcelTableExists` Variable aus.</span><span class="sxs-lookup"><span data-stu-id="54eb9-169">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, select the `ExcelTableExists` variable.</span></span>  
  
4.  <span data-ttu-id="54eb9-170">Klicken Sie zum Öffnen des Skript-Editors auf **Skript bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="54eb9-170">Click **Edit Script** to open the script editor.</span></span>  
  
5.  <span data-ttu-id="54eb9-171">Fügen Sie der Assembly `System.Xml` im Skriptprojekt einen Verweis hinzu.</span><span class="sxs-lookup"><span data-stu-id="54eb9-171">Add a reference to the `System.Xml` assembly in the script project.</span></span>  
  
6.  <span data-ttu-id="54eb9-172">Fügen Sie am Anfang der Skriptdatei `Imports`-Anweisungen für den `System.IO`-Namespace und den `System.Data.OleDb`-Namespace hinzu.</span><span class="sxs-lookup"><span data-stu-id="54eb9-172">Add `Imports` statements for the `System.IO` and `System.Data.OleDb` namespaces at the top of the script file.</span></span>  
  
7.  <span data-ttu-id="54eb9-173">Fügen Sie den folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="54eb9-173">Add the following code.</span></span>  
  
### <a name="example-2-code"></a><span data-ttu-id="54eb9-174">Codebeispiel 2</span><span class="sxs-lookup"><span data-stu-id="54eb9-174">Example 2 Code</span></span>  
  
```vb  
Public Class ScriptMain  
  Public Sub Main()  
    Dim fileToTest As String  
    Dim tableToTest As String  
    Dim connectionString As String  
    Dim excelConnection As OleDbConnection  
    Dim excelTables As DataTable  
    Dim excelTable As DataRow  
    Dim currentTable As String  
  
    fileToTest = Dts.Variables("ExcelFile").Value.ToString  
    tableToTest = Dts.Variables("ExcelTable").Value.ToString  
  
    Dts.Variables("ExcelTableExists").Value = False  
    If File.Exists(fileToTest) Then  
      connectionString = "Provider=Microsoft.Jet.OLEDB.4.0;" & _  
        "Data Source=" & fileToTest & _  
        ";Extended Properties=Excel 8.0"  
      excelConnection = New OleDbConnection(connectionString)  
      excelConnection.Open()  
      excelTables = excelConnection.GetSchema("Tables")  
      For Each excelTable In excelTables.Rows  
        currentTable = excelTable.Item("TABLE_NAME").ToString  
        If currentTable = tableToTest Then  
          Dts.Variables("ExcelTableExists").Value = True  
        End If  
      Next  
    End If  
  
    Dts.TaskResult = ScriptResults.Success  
  End Sub  
End Class  
```  
  
```csharp  
public class ScriptMain  
{  
    public void Main()  
        {  
            string fileToTest;  
            string tableToTest;  
            string connectionString;  
            OleDbConnection excelConnection;  
            DataTable excelTables;  
            string currentTable;  
  
            fileToTest = Dts.Variables["ExcelFile"].Value.ToString();  
            tableToTest = Dts.Variables["ExcelTable"].Value.ToString();  
  
            Dts.Variables["ExcelTableExists"].Value = false;  
            if (File.Exists(fileToTest))  
            {  
                connectionString = "Provider=Microsoft.Jet.OLEDB.4.0;" +  
                "Data Source=" + fileToTest + ";Extended Properties=Excel 8.0";  
                excelConnection = new OleDbConnection(connectionString);  
                excelConnection.Open();  
                excelTables = excelConnection.GetSchema("Tables");  
                foreach (DataRow excelTable in excelTables.Rows)  
                {  
                    currentTable = excelTable["TABLE_NAME"].ToString();  
                    if (currentTable == tableToTest)  
                    {  
                        Dts.Variables["ExcelTableExists"].Value = true;  
                    }  
                }  
            }  
  
            Dts.TaskResult = (int)ScriptResults.Success;  
  
        }  
}  
```  
  
##  <a name="example-3-description-get-a-list-of-excel-files-in-a-folder"></a><a name="example3"></a> <span data-ttu-id="54eb9-175">Beschreibung zu Beispiel 3: Abrufen einer Liste der Excel-Dateien in einem Ordner</span><span class="sxs-lookup"><span data-stu-id="54eb9-175">Example 3 Description: Get a List of Excel Files in a Folder</span></span>  
 <span data-ttu-id="54eb9-176">In diesem Beispiel wird ein Array mit der Liste der Excel-Dateien aus dem Ordner gefüllt, der im Wert der `ExcelFolder`-Variable angegeben wurde. Das Array wird daraufhin in die `ExcelFiles`-Variable kopiert.</span><span class="sxs-lookup"><span data-stu-id="54eb9-176">This example fills an array with the list of Excel files found in the folder specified in the value of the `ExcelFolder` variable, and then copies the array into the `ExcelFiles` variable.</span></span> <span data-ttu-id="54eb9-177">Mithilfe des Foreach-Enumerators für Daten aus Variablen können die Dateien in dem Array durchlaufen werden.</span><span class="sxs-lookup"><span data-stu-id="54eb9-177">You can use the Foreach from Variable enumerator to iterate over the files in the array.</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="54eb9-178">So konfigurieren Sie dieses Skripttaskbeispiel</span><span class="sxs-lookup"><span data-stu-id="54eb9-178">To configure this Script Task example</span></span>  
  
1.  <span data-ttu-id="54eb9-179">Fügen Sie dem Paket einen neuen Skripttask hinzu, und ändern Sie den Namen in **GetExcelFiles**.</span><span class="sxs-lookup"><span data-stu-id="54eb9-179">Add a new Script task to the package and change its name to **GetExcelFiles**.</span></span>  
  
2.  <span data-ttu-id="54eb9-180">Öffnen Sie den **Skripttask-Editor**, klicken Sie auf der Registerkarte **Skript** auf **ReadOnlyVariables**, und geben Sie den Eigenschaftswert mit einer der folgenden Methoden ein:</span><span class="sxs-lookup"><span data-stu-id="54eb9-180">Open the **Script Task Editor**, on the **Script** tab, click **ReadOnlyVariables** and enter the property value using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="54eb9-181">Geben Sie `ExcelFolder` ein.</span><span class="sxs-lookup"><span data-stu-id="54eb9-181">Type `ExcelFolder`</span></span>  
  
         <span data-ttu-id="54eb9-182">Oder</span><span class="sxs-lookup"><span data-stu-id="54eb9-182">-or-</span></span>  
  
    -   <span data-ttu-id="54eb9-183">Klicken Sie auf die Schaltfläche mit den Auslassungs Punkten (**...**) neben dem Eigenschafts Feld, und wählen Sie im Dialogfeld **Variablen auswählen** die Variable ExcelFolder aus.</span><span class="sxs-lookup"><span data-stu-id="54eb9-183">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, select the ExcelFolder variable.</span></span>  
  
3.  <span data-ttu-id="54eb9-184">Klicken Sie auf **ReadWriteVariables**, und geben Sie den Eigenschaftswert mit einer der folgenden Methoden ein:</span><span class="sxs-lookup"><span data-stu-id="54eb9-184">Click **ReadWriteVariables** and enter the property value using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="54eb9-185">Geben Sie `ExcelFiles`ein.</span><span class="sxs-lookup"><span data-stu-id="54eb9-185">Type `ExcelFiles`.</span></span>  
  
         <span data-ttu-id="54eb9-186">Oder</span><span class="sxs-lookup"><span data-stu-id="54eb9-186">-or-</span></span>  
  
    -   <span data-ttu-id="54eb9-187">Klicken Sie auf die Schaltfläche mit den Auslassungs Punkten (**...**) neben dem Eigenschafts Feld, und wählen Sie im Dialogfeld **Variablen auswählen** die Variable ExcelFiles aus.</span><span class="sxs-lookup"><span data-stu-id="54eb9-187">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, select the ExcelFiles variable.</span></span>  
  
4.  <span data-ttu-id="54eb9-188">Klicken Sie zum Öffnen des Skript-Editors auf **Skript bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="54eb9-188">Click **Edit Script** to open the script editor.</span></span>  
  
5.  <span data-ttu-id="54eb9-189">Fügen Sie am Anfang der Skriptdatei eine `Imports`-Anweisung für den `System.IO`-Namespace hinzu.</span><span class="sxs-lookup"><span data-stu-id="54eb9-189">Add an `Imports` statement for the `System.IO` namespace at the top of the script file.</span></span>  
  
6.  <span data-ttu-id="54eb9-190">Fügen Sie den folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="54eb9-190">Add the following code.</span></span>  
  
### <a name="example-3-code"></a><span data-ttu-id="54eb9-191">Codebeispiel 3</span><span class="sxs-lookup"><span data-stu-id="54eb9-191">Example 3 Code</span></span>  
  
```vb  
Public Class ScriptMain  
  Public Sub Main()  
    Const FILE_PATTERN As String = "*.xls"  
  
    Dim excelFolder As String  
    Dim excelFiles As String()  
  
    excelFolder = Dts.Variables("ExcelFolder").Value.ToString  
    excelFiles = Directory.GetFiles(excelFolder, FILE_PATTERN)  
  
    Dts.Variables("ExcelFiles").Value = excelFiles  
  
    Dts.TaskResult = ScriptResults.Success  
  End Sub  
End Class  
```  
  
```csharp  
public class ScriptMain  
{  
  public void Main()  
  {  
    const string FILE_PATTERN = "*.xls";  
  
    string excelFolder;  
    string[] excelFiles;  
  
    excelFolder = Dts.Variables["ExcelFolder"].Value.ToString();  
    excelFiles = Directory.GetFiles(excelFolder, FILE_PATTERN);  
  
    Dts.Variables["ExcelFiles"].Value = excelFiles;  
  
    Dts.TaskResult = (int)ScriptResults.Success;  
  }  
}  
```  
  
### <a name="alternate-solution"></a><span data-ttu-id="54eb9-192">Alternative Lösung</span><span class="sxs-lookup"><span data-stu-id="54eb9-192">Alternate Solution</span></span>  
 <span data-ttu-id="54eb9-193">Anstelle eines Skripttasks können Sie zum Sammeln einer Liste von Excel-Arbeitsmappen in einem Array auch den Foreach-Dateienumerator verwenden, um alle Excel-Dateien in einem Ordner zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="54eb9-193">Instead of using a Script task to gather a list of Excel files into an array, you can also use the ForEach File enumerator to iterate over all the Excel files in a folder.</span></span> <span data-ttu-id="54eb9-194">Weitere Informationen finden Sie unter [Loop through Excel Files and Tables by Using a Foreach Loop Container (Schleife durch Excel-Dateien und Tabellen mit einem Foreach-Schleifencontainer)](../control-flow/foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="54eb9-194">For more information, see [Loop through Excel Files and Tables by Using a Foreach Loop Container](../control-flow/foreach-loop-container.md).</span></span>  
  
##  <a name="example-4-description-get-a-list-of-tables-in-an-excel-file"></a><a name="example4"></a> <span data-ttu-id="54eb9-195">Beschreibung zu Beispiel 4: Abrufen einer Liste der Tabellen in einer Excel-Datei</span><span class="sxs-lookup"><span data-stu-id="54eb9-195">Example 4 Description: Get a List of Tables in an Excel File</span></span>  
 <span data-ttu-id="54eb9-196">In diesem Beispiel wird ein Array mit der Liste der Arbeitsmappen und benannten Bereiche in der Excel-Arbeitsmappendatei gefüllt, der im Wert der `ExcelFile`-Variable angegeben wurde. Das Array wird daraufhin in die `ExcelTables`-Variable kopiert.</span><span class="sxs-lookup"><span data-stu-id="54eb9-196">This example fills an array with the list of worksheets and named ranges found in the Excel workbook file specified by the value of the `ExcelFile` variable, and then copies the array into the `ExcelTables` variable.</span></span> <span data-ttu-id="54eb9-197">Mithilfe des Foreach-Enumerators für Daten aus Variablen können die Tabellen in dem Array durchlaufen werden.</span><span class="sxs-lookup"><span data-stu-id="54eb9-197">You can use the Foreach from Variable Enumerator to iterate over the tables in the array.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="54eb9-198">Die Liste der Tabellen in einer Excel-Arbeitsmappe schließt sowohl Arbeitsmappen (diese weisen das Suffix $ auf) als auch benannte Bereiche ein.</span><span class="sxs-lookup"><span data-stu-id="54eb9-198">The list of tables in an Excel workbook includes both worksheets (which have the $ suffix) and named ranges.</span></span> <span data-ttu-id="54eb9-199">Wenn Sie die Liste nach nur Arbeitsmappen oder nach nur benannten Bereichen filtern müssen, müssen Sie zu diesem Zweck möglicherweise zusätzlichen Code hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="54eb9-199">If you have to filter the list for only worksheets or only named ranges, you may have to add additional code for this purpose.</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="54eb9-200">So konfigurieren Sie dieses Skripttaskbeispiel</span><span class="sxs-lookup"><span data-stu-id="54eb9-200">To configure this Script Task example</span></span>  
  
1.  <span data-ttu-id="54eb9-201">Fügen Sie dem Paket einen neuen Skripttask hinzu, und ändern Sie den Namen in **GetExcelTables**.</span><span class="sxs-lookup"><span data-stu-id="54eb9-201">Add a new Script task to the package and change its name to **GetExcelTables**.</span></span>  
  
2.  <span data-ttu-id="54eb9-202">Öffnen Sie den **Skripttask-Editor**, klicken Sie auf der Registerkarte **Skript** auf **ReadOnlyVariables**, und geben Sie den Eigenschaftswert mit einer der folgenden Methoden ein:</span><span class="sxs-lookup"><span data-stu-id="54eb9-202">Open the **Script Task Editor**, on the **Script** tab, click **ReadOnlyVariables** and enter the property value using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="54eb9-203">Geben Sie `ExcelFile`ein.</span><span class="sxs-lookup"><span data-stu-id="54eb9-203">Type `ExcelFile`.</span></span>  
  
         <span data-ttu-id="54eb9-204">Oder</span><span class="sxs-lookup"><span data-stu-id="54eb9-204">-or-</span></span>  
  
    -   <span data-ttu-id="54eb9-205">Klicken Sie auf die Schaltfläche mit den Auslassungs Punkten (**...**) neben dem Eigenschafts Feld, und wählen Sie im Dialogfeld **Variablen auswählen** die Variable ExcelFile aus.</span><span class="sxs-lookup"><span data-stu-id="54eb9-205">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, select the ExcelFile variable.</span></span>  
  
3.  <span data-ttu-id="54eb9-206">Klicken Sie auf **ReadWriteVariables**, und geben Sie den Eigenschaftswert mit einer der folgenden Methoden ein:</span><span class="sxs-lookup"><span data-stu-id="54eb9-206">Click **ReadWriteVariables** and enter the property value using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="54eb9-207">Geben Sie `ExcelTables`ein.</span><span class="sxs-lookup"><span data-stu-id="54eb9-207">Type `ExcelTables`.</span></span>  
  
         <span data-ttu-id="54eb9-208">Oder</span><span class="sxs-lookup"><span data-stu-id="54eb9-208">-or-</span></span>  
  
    -   <span data-ttu-id="54eb9-209">Klicken Sie auf die Schaltfläche mit den Auslassungs Punkten (**...**) neben dem Eigenschafts Feld, und wählen Sie im Dialogfeld **Variablen auswählen** die Variable exceltablesvariable aus.</span><span class="sxs-lookup"><span data-stu-id="54eb9-209">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, select the ExcelTablesvariable.</span></span>  
  
4.  <span data-ttu-id="54eb9-210">Klicken Sie zum Öffnen des Skript-Editors auf **Skript bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="54eb9-210">Click **Edit Script** to open the script editor.</span></span>  
  
5.  <span data-ttu-id="54eb9-211">Fügen Sie dem `System.Xml`-Namespace einen Verweis im Skriptprojekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="54eb9-211">Add a reference to the `System.Xml` namespace in the script project.</span></span>  
  
6.  <span data-ttu-id="54eb9-212">Fügen Sie am Anfang der Skriptdatei eine `Imports`-Anweisung für den `System.Data.OleDb`-Namespace hinzu.</span><span class="sxs-lookup"><span data-stu-id="54eb9-212">Add an `Imports` statement for the `System.Data.OleDb` namespace at the top of the script file.</span></span>  
  
7.  <span data-ttu-id="54eb9-213">Fügen Sie den folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="54eb9-213">Add the following code.</span></span>  
  
### <a name="example-4-code"></a><span data-ttu-id="54eb9-214">Code zu Beispiel 4</span><span class="sxs-lookup"><span data-stu-id="54eb9-214">Example 4 Code</span></span>  
  
```vb  
Public Class ScriptMain  
  Public Sub Main()  
    Dim excelFile As String  
    Dim connectionString As String  
    Dim excelConnection As OleDbConnection  
    Dim tablesInFile As DataTable  
    Dim tableCount As Integer = 0  
    Dim tableInFile As DataRow  
    Dim currentTable As String  
    Dim tableIndex As Integer = 0  
  
    Dim excelTables As String()  
  
    excelFile = Dts.Variables("ExcelFile").Value.ToString  
    connectionString = "Provider=Microsoft.Jet.OLEDB.4.0;" & _  
        "Data Source=" & excelFile & _  
        ";Extended Properties=Excel 8.0"  
    excelConnection = New OleDbConnection(connectionString)  
    excelConnection.Open()  
    tablesInFile = excelConnection.GetSchema("Tables")  
    tableCount = tablesInFile.Rows.Count  
    ReDim excelTables(tableCount - 1)  
    For Each tableInFile In tablesInFile.Rows  
      currentTable = tableInFile.Item("TABLE_NAME").ToString  
      excelTables(tableIndex) = currentTable  
      tableIndex += 1  
    Next  
  
    Dts.Variables("ExcelTables").Value = excelTables  
  
    Dts.TaskResult = ScriptResults.Success  
  End Sub  
End Class  
```  
  
```csharp  
public class ScriptMain  
{  
  public void Main()  
        {  
            string excelFile;  
            string connectionString;  
            OleDbConnection excelConnection;  
            DataTable tablesInFile;  
            int tableCount = 0;  
            string currentTable;  
            int tableIndex = 0;  
  
            string[] excelTables = new string[5];  
  
            excelFile = Dts.Variables["ExcelFile"].Value.ToString();  
            connectionString = "Provider=Microsoft.Jet.OLEDB.4.0;" +  
                "Data Source=" + excelFile + ";Extended Properties=Excel 8.0";  
            excelConnection = new OleDbConnection(connectionString);  
            excelConnection.Open();  
            tablesInFile = excelConnection.GetSchema("Tables");  
            tableCount = tablesInFile.Rows.Count;  
  
            foreach (DataRow tableInFile in tablesInFile.Rows)  
            {  
                currentTable = tableInFile["TABLE_NAME"].ToString();  
                excelTables[tableIndex] = currentTable;  
                tableIndex += 1;  
            }  
  
            Dts.Variables["ExcelTables"].Value = excelTables;  
  
            Dts.TaskResult = (int)ScriptResults.Success;  
        }  
}  
```  
  
### <a name="alternate-solution"></a><span data-ttu-id="54eb9-215">Alternative Lösung</span><span class="sxs-lookup"><span data-stu-id="54eb9-215">Alternate Solution</span></span>  
 <span data-ttu-id="54eb9-216">Anstelle eines Skripttasks können Sie zum Sammeln einer Liste von Excel-Arbeitsmappen in einem Array auch den Enumerator für das Foreach-ADO.NET-Schemarowset verwenden, um alle Tabellen (d. h. Arbeitsmappen und benannte Bereiche) in einer Excel-Arbeitsmappendatei zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="54eb9-216">Instead of using a Script task to gather a list of Excel tables into an array, you can also use the ForEach ADO.NET Schema Rowset Enumerator to iterate over all the tables (that is, worksheets and named ranges) in an Excel workbook file.</span></span> <span data-ttu-id="54eb9-217">Weitere Informationen finden Sie unter [Loop through Excel Files and Tables by Using a Foreach Loop Container (Schleife durch Excel-Dateien und Tabellen mit einem Foreach-Schleifencontainer)](../control-flow/foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="54eb9-217">For more information, see [Loop through Excel Files and Tables by Using a Foreach Loop Container](../control-flow/foreach-loop-container.md).</span></span>  
  
##  <a name="displaying-the-results-of-the-samples"></a><a name="testing"></a> <span data-ttu-id="54eb9-218">Anzeigen der Ergebnisse dieser Beispiele</span><span class="sxs-lookup"><span data-stu-id="54eb9-218">Displaying the Results of the Samples</span></span>  
 <span data-ttu-id="54eb9-219">Wenn Sie alle Beispiele dieses Themas im selben Paket konfiguriert haben, können Sie alle Skripttasks mit einem zusätzlichen Skripttask verbinden, der die Ausgaben aller Beispiele anzeigt.</span><span class="sxs-lookup"><span data-stu-id="54eb9-219">If you have configured each of the examples in this topic in the same package, you can connect all the Script tasks to an additional Script task that displays the output of all the examples.</span></span>  
  
#### <a name="to-configure-a-script-task-to-display-the-output-of-the-examples-in-this-topic"></a><span data-ttu-id="54eb9-220">So konfigurieren Sie einen Skripttask zum Anzeigen der Ausgabe der in diesem Thema behandelten Beispiele</span><span class="sxs-lookup"><span data-stu-id="54eb9-220">To configure a Script task to display the output of the examples in this topic</span></span>  
  
1.  <span data-ttu-id="54eb9-221">Fügen Sie dem Paket einen neuen Skripttask hinzu, und ändern Sie den Namen in **DisplayResults**.</span><span class="sxs-lookup"><span data-stu-id="54eb9-221">Add a new Script task to the package and change its name to **DisplayResults**.</span></span>  
  
2.  <span data-ttu-id="54eb9-222">Verbinden Sie alle vier Beispielskripttasks miteinander, sodass nach dem erfolgreichen Abschluss des vorhergehenden Tasks der jeweils nächste Task ausgeführt wird, und verbinden Sie den vierten Beispieltask mit dem **DisplayResults**-Task.</span><span class="sxs-lookup"><span data-stu-id="54eb9-222">Connect each of the four example Script tasks to one another, so that each task runs after the preceding task completes successfully, and connect the fourth example task to the **DisplayResults** task.</span></span>  
  
3.  <span data-ttu-id="54eb9-223">Öffnen Sie den Task **DisplayResults** im **Skripttask-Editor**.</span><span class="sxs-lookup"><span data-stu-id="54eb9-223">Open the **DisplayResults** task in the **Script Task Editor**.</span></span>  
  
4.  <span data-ttu-id="54eb9-224">Klicken Sie auf der Registerkarte **Skript** auf **ReadOnlyVariables**, und fügen Sie mithilfe einer der folgenden Methoden alle sieben unter [Konfigurieren eines Pakets zum Testen der Beispiele](#configuring) aufgeführten Variablen hinzu:</span><span class="sxs-lookup"><span data-stu-id="54eb9-224">On the **Script** tab, click **ReadOnlyVariables** and use one of the following methods to add all seven variables listed in [Configuring a Package to Test the Samples](#configuring):</span></span>  
  
    -   <span data-ttu-id="54eb9-225">Geben Sie den Namen jeder Variable durch Trennzeichen getrennt ein.</span><span class="sxs-lookup"><span data-stu-id="54eb9-225">Type the name of each variable separated by commas.</span></span>  
  
         <span data-ttu-id="54eb9-226">Oder</span><span class="sxs-lookup"><span data-stu-id="54eb9-226">-or-</span></span>  
  
    -   <span data-ttu-id="54eb9-227">Klicken Sie auf die Schaltfläche mit den Auslassungs Punkten (**...**) neben dem Eigenschafts Feld, und wählen Sie im Dialogfeld **Variablen auswählen** die Variablen aus.</span><span class="sxs-lookup"><span data-stu-id="54eb9-227">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, selecting the variables.</span></span>  
  
5.  <span data-ttu-id="54eb9-228">Klicken Sie zum Öffnen des Skript-Editors auf **Skript bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="54eb9-228">Click **Edit Script** to open the script editor.</span></span>  
  
6.  <span data-ttu-id="54eb9-229">Fügen Sie am Anfang der Skriptdatei `Imports`-Anweisungen für den `Microsoft.VisualBasic`-Namespace und den `System.Windows.Forms`-Namespace hinzu.</span><span class="sxs-lookup"><span data-stu-id="54eb9-229">Add `Imports` statements for the `Microsoft.VisualBasic` and `System.Windows.Forms` namespaces at the top of the script file.</span></span>  
  
7.  <span data-ttu-id="54eb9-230">Fügen Sie den folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="54eb9-230">Add the following code.</span></span>  
  
8.  <span data-ttu-id="54eb9-231">Führen Sie das Paket aus, und überprüfen Sie die in dem Meldungsfeld angezeigten Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="54eb9-231">Run the package and examine the results displayed in a message box.</span></span>  
  
### <a name="code-to-display-the-results"></a><span data-ttu-id="54eb9-232">Code zum Anzeigen der Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="54eb9-232">Code to Display the Results</span></span>  
  
```vb  
Public Class ScriptMain  
  Public Sub Main()  
    Const EOL As String = ControlChars.CrLf  
  
    Dim results As String  
    Dim filesInFolder As String()  
    Dim fileInFolder As String  
    Dim tablesInFile As String()  
    Dim tableInFile As String  
  
    results = _  
      "Final values of variables:" & EOL & _  
      "ExcelFile: " & Dts.Variables("ExcelFile").Value.ToString & EOL & _  
      "ExcelFileExists: " & Dts.Variables("ExcelFileExists").Value.ToString & EOL & _  
      "ExcelTable: " & Dts.Variables("ExcelTable").Value.ToString & EOL & _  
      "ExcelTableExists: " & Dts.Variables("ExcelTableExists").Value.ToString & EOL & _  
      "ExcelFolder: " & Dts.Variables("ExcelFolder").Value.ToString & EOL & _  
      EOL  
  
    results &= "Excel files in folder: " & EOL  
    filesInFolder = DirectCast(Dts.Variables("ExcelFiles").Value, String())  
    For Each fileInFolder In filesInFolder  
      results &= " " & fileInFolder & EOL  
    Next  
    results &= EOL  
  
    results &= "Excel tables in file: " & EOL  
    tablesInFile = DirectCast(Dts.Variables("ExcelTables").Value, String())  
    For Each tableInFile In tablesInFile  
      results &= " " & tableInFile & EOL  
    Next  
  
    MessageBox.Show(results, "Results", MessageBoxButtons.OK, MessageBoxIcon.Information)  
  
    Dts.TaskResult = ScriptResults.Success  
  End Sub  
End Class  
```  
  
```csharp  
public class ScriptMain  
{  
  public void Main()  
        {  
            const string EOL = "\r";  
  
            string results;  
            string[] filesInFolder;  
            //string fileInFolder;  
            string[] tablesInFile;  
            //string tableInFile;  
  
            results = "Final values of variables:" + EOL + "ExcelFile: " + Dts.Variables["ExcelFile"].Value.ToString() + EOL + "ExcelFileExists: " + Dts.Variables["ExcelFileExists"].Value.ToString() + EOL + "ExcelTable: " + Dts.Variables["ExcelTable"].Value.ToString() + EOL + "ExcelTableExists: " + Dts.Variables["ExcelTableExists"].Value.ToString() + EOL + "ExcelFolder: " + Dts.Variables["ExcelFolder"].Value.ToString() + EOL + EOL;  
  
            results += "Excel files in folder: " + EOL;  
            filesInFolder = (string[])(Dts.Variables["ExcelFiles"].Value);  
            foreach (string fileInFolder in filesInFolder)  
            {  
                results += " " + fileInFolder + EOL;  
            }  
            results += EOL;  
  
            results += "Excel tables in file: " + EOL;  
            tablesInFile = (string[])(Dts.Variables["ExcelTables"].Value);  
            foreach (string tableInFile in tablesInFile)  
            {  
                results += " " + tableInFile + EOL;  
            }  
  
            MessageBox.Show(results, "Results", MessageBoxButtons.OK, MessageBoxIcon.Information);  
  
            Dts.TaskResult = (int)ScriptResults.Success;  
        }  
}  
```  
  
<span data-ttu-id="54eb9-233">![Integration Services Symbol (klein)](../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="54eb9-233">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="54eb9-234">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="54eb9-234">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="54eb9-235">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="54eb9-235">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="54eb9-236">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="54eb9-236">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54eb9-237">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="54eb9-237">See Also</span></span>  
 <span data-ttu-id="54eb9-238">[Excel-Verbindungs-Manager](../connection-manager/excel-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="54eb9-238">[Excel Connection Manager](../connection-manager/excel-connection-manager.md) </span></span>  
 [<span data-ttu-id="54eb9-239">Schleife durch Excel-Dateien und Tabellen mit einem Foreach-Schleifencontainer</span><span class="sxs-lookup"><span data-stu-id="54eb9-239">Loop through Excel Files and Tables by Using a Foreach Loop Container</span></span>](../control-flow/foreach-loop-container.md)  
  
  
