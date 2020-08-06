---
title: Verwenden von ADO zum Ausführen von SQLXML 4.0-Abfragen
ms.custom: ''
ms.date: 12/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- query testers [SQLXML]
- test scripts
- ADO [SQLXML]
- queries [SQLXML], ADO
- SQLXML, ADO
ms.assetid: 3d54e3bb-7c5f-427e-82f8-1403a54c4f53
author: rothja
ms.author: jroth
ms.openlocfilehash: 169d20b4192e4a5b8e7b32839f2da255fc58d89c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696706"
---
# <a name="using-ado-to-execute-sqlxml-40-queries"></a><span data-ttu-id="44911-102">Verwenden von ADO zum Ausführen von SQLXML 4.0-Abfragen</span><span class="sxs-lookup"><span data-stu-id="44911-102">Using ADO to Execute SQLXML 4.0 Queries</span></span>
  <span data-ttu-id="44911-103">In früheren Versionen von SQLXML wurde die HTTP-basierte Abfrageausführung mit virtuellen SQLXML IIS-Verzeichnissen und dem SQLXML ISAPI-Filter unterstützt.</span><span class="sxs-lookup"><span data-stu-id="44911-103">In previous versions of SQLXML, HTTP-based query execution was supported using SQLXML IIS virtual directories and the SQLXML ISAPI filter.</span></span> <span data-ttu-id="44911-104">In SQLXML 4.0 sind diese Komponenten nicht mehr verfügbar, da ähnliche und überlappende Funktionen mit systemeigenen Web-Diensten ab [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="44911-104">In SQLXML 4.0, these components have been removed as similar and overlapping functionality is provided with native XML Web services beginning in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
 <span data-ttu-id="44911-105">Als Alternative können Sie Abfragen ausführen und SQLXML 4.0 mit Ihren COM-basierten Anwendungen verwenden, indem Sie die SQLXML-Erweiterungen für ActiveX Data Objects (ADO) nutzen, die in Microsoft Data Access Components (MDAC) 2.6 eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="44911-105">As an alternative, you can execute queries and use SQLXML 4.0 with your COM-based applications, by leveraging the SQLXML extensions to ActiveX Data Objects (ADO) that were first introduced in Microsoft Data Access Components (MDAC) 2.6 and later.</span></span>  
  
 <span data-ttu-id="44911-106">Dieses Thema veranschaulicht die Verwendung von SQLXML und ADO als Bestandteile einer VBScript-Anwendung (Visual Basic Scripting Edition, ein Skript mit der Dateierweiterung VBS).</span><span class="sxs-lookup"><span data-stu-id="44911-106">This topic demonstrates using SQLXML and ADO as part of a Visual Basic Scripting Edition (VBScript) application (a script with the .vbs file extension).</span></span> <span data-ttu-id="44911-107">Es enthält erste Setupschritte, die Ihnen helfen, Abfragebeispiele in der SQLXML 4.0-Dokumentation erneut zu erstellen und zu testen.</span><span class="sxs-lookup"><span data-stu-id="44911-107">It provides initial setup procedures to help you recreate and test query samples in the SQLXML 4.0 documentation.</span></span>  
  
## <a name="creating-the-sqlxml-40-test-script"></a><span data-ttu-id="44911-108">Erstellen des SQLXML 4.0-Testskripts</span><span class="sxs-lookup"><span data-stu-id="44911-108">Creating the SQLXML 4.0 Test Script</span></span>  
 <span data-ttu-id="44911-109">In diesem Schritt erstellen Sie eine VBScript-Datei (VBS), Sqlxml4test.vbs, mit der SQLXML-Abfragen durch Nutzen der SQLXML ADO-Erweiterungen in ADO 2.6 und höher ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="44911-109">In this procedure, you create a VBScript (.vbs) file, Sqlxml4test.vbs, which can be used to execute SQLXML queries by leveraging the SQLXML ADO extensions in ADO 2.6 and later.</span></span>  
  
#### <a name="to-create-the-sqlxml-40-query-tester-using-ado-vbscript"></a><span data-ttu-id="44911-110">So erstellen Sie den SQLXML 4.0-Abfragetester mit ADO (VBScript)</span><span class="sxs-lookup"><span data-stu-id="44911-110">To create the SQLXML 4.0 query tester using ADO (VBScript).</span></span>  
  
1.  <span data-ttu-id="44911-111">Kopieren Sie den unten stehenden VBScript-Code, und fügen Sie ihn in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="44911-111">Copy the VBScript code below, and paste it into a text file.</span></span> <span data-ttu-id="44911-112">Speichern Sie die Datei unter dem Dateinamen Sqlxml4test.vbs.</span><span class="sxs-lookup"><span data-stu-id="44911-112">Save the file as Sqlxml4test.vbs.</span></span>  
  
    ```vb
    WScript.Echo "Query process may take a few seconds to complete. Please be patient."  
  
    ' Note that for SQL Server Native Client to be used as the data provider,  
    ' it needs to be installed on the client computer first. Also, SQLXML extensions   
    ' for ADO are used and available in MDAC 2.6 or later.  
  
    'Set script variables.  
    inputFile = "@@FILE_NAME@@"  
    strServer = "@@SERVER_NAME@@"  
    strDatabase = "@@DATABASE_NAME@@"  
    dbGuid = "{5d531cb2-e6ed-11d2-b252-00c04f681b71}"  
  
    ' Establish ADO connection to SQL Server and   
    ' create an instance of the ADO Command object.  
    Set conn = CreateObject("ADODB.Connection")  
    Set cmd = CreateObject("ADODB.Command")  
    conn.Open "Provider=SQLXMLOLEDB.4.0;Data Provider=SQLNCLI11;Server=" & strServer & _  
              ";Database=" & strDatabase & ";Integrated Security=SSPI"  
    Set cmd.ActiveConnection = conn  
  
    ' Create the input stream as an instance of the ADO Stream object.  
    Set inStream = CreateObject("ADODB.Stream")  
    inStream.Open  
    inStream.Charset = "utf-8"  
    inStream.LoadFromFile inputFile  
  
    ' Set ADO Command instance to use input stream.  
    Set cmd.CommandStream = inStream  
  
    ' Set the command dialect.  
    cmd.Dialect = dbGuid  
  
    ' Set a second ADO Stream instance for use as a results stream.   
    Set outStream = CreateObject("ADODB.Stream")  
    outStream.Open  
  
    ' Set dynamic properties used by the SQLXML ADO command instance.   
    cmd.Properties("XML Root").Value = "ROOT"  
    cmd.Properties("Output Encoding").Value = "UTF-8"  
  
    ' Connect the results stream to the command instance and execute the command.  
    cmd.Properties("Output Stream").Value = outStream  
    cmd.Execute , , 1024  
  
    ' Echo cropped/partial results to console.  
    WScript.Echo Left(outStream.ReadText, 1023)  
  
    inStream.Close  
    outStream.Close  
    ```  
  
2.  <span data-ttu-id="44911-113">Aktualisieren Sie die folgenden Skriptwerte für das Beispiel, das Sie testen möchten, sowie die Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="44911-113">Update the following script values for the sample you are trying to test and your test environment.</span></span>  
  
    -   <span data-ttu-id="44911-114">Suchen Sie den Namen "`@@FILE_NAME@@`", und ersetzen Sie ihn durch den Namen der Vorlagendatei.</span><span class="sxs-lookup"><span data-stu-id="44911-114">Find "`@@FILE_NAME@@`" and replace it with the name of your template file.</span></span>  
  
    -   <span data-ttu-id="44911-115">Suchen Sie den Namen "`@@SERVER_NAME@@`", und ersetzen Sie ihn durch den Namen Ihrer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Instanz (z. B. "`(local)`", wenn [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] lokal ausgeführt wird).</span><span class="sxs-lookup"><span data-stu-id="44911-115">Find "`@@SERVER_NAME@@`" and replace it with the name of your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance (for example, "`(local)`" if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running locally).</span></span>  
  
    -   <span data-ttu-id="44911-116">Suchen Sie den Namen "`@@DATABASE_NAME@@`", und ersetzen Sie ihn durch den Namen der Datenbank (z. B. entweder "`AdventureWorks2012`" oder "`tempdb`").</span><span class="sxs-lookup"><span data-stu-id="44911-116">Find "`@@DATABASE_NAME@@`" and replace it with the name of the database (for example, either "`AdventureWorks2012`" or "`tempdb`").</span></span>  
  
     <span data-ttu-id="44911-117">Aktualisieren Sie ggf. andere Werte, sofern dies in den entsprechenden Anweisungen für das Beispiel angegeben ist, das Sie lokal auf dem Computer neu erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="44911-117">Update any other values if mentioned in the specific instructions for the example you are attempting to recreate locally on your computer.</span></span>  
  
3.  <span data-ttu-id="44911-118">Speichern Sie die Datei, und schließen Sie sie.</span><span class="sxs-lookup"><span data-stu-id="44911-118">Save the file and close it.</span></span>  
  
4.  <span data-ttu-id="44911-119">Überprüfen Sie, ob Sie zusätzliche Dateien wie XML-Vorlagen oder Schemas erstellt haben, die zu dem Beispiel gehören, das Sie lokal auf dem Computer neu erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="44911-119">Verify that you have created any additional files, such as XML templates or schemas that are part of the sample you are attempting to recreate locally on your computer.</span></span> <span data-ttu-id="44911-120">Diese Dateien sollten sich in dem gleichen Verzeichnis befinden wie die Testskriptdatei (Sqlxml4test.vbs).</span><span class="sxs-lookup"><span data-stu-id="44911-120">These files should be located in the same directory where you have saved the test script file (Sqlxml4test.vbs).</span></span>  
  
5.  <span data-ttu-id="44911-121">Folgen Sie den Anweisungen im nächsten Abschnitt zur Verwendung des SQLXML 4.0-Testskripts.</span><span class="sxs-lookup"><span data-stu-id="44911-121">Follow the instructions in the next section for how to use the SQLXML 4.0 test script.</span></span>  
  
## <a name="using-the-sqlxml-40-test-script"></a><span data-ttu-id="44911-122">Verwenden des SQLXML 4.0-Testskripts</span><span class="sxs-lookup"><span data-stu-id="44911-122">Using the SQLXML 4.0 Test Script</span></span>  
 <span data-ttu-id="44911-123">Im folgenden Verfahren wird beschrieben, wie Sie die Sqlxml4test.vbs-Dateien zum Testen der in dieser Dokumentation enthaltenen Beispielabfragen verwenden.</span><span class="sxs-lookup"><span data-stu-id="44911-123">The following procedure describes how to use the Sqlxml4test.vbs files to test the example queries provided in this documentation.</span></span>  
  
#### <a name="to-use-the-sqlxml-40-query-tester"></a><span data-ttu-id="44911-124">So verwenden Sie den SQLXML 4.0-Abfragetester</span><span class="sxs-lookup"><span data-stu-id="44911-124">To use the SQLXML 4.0 query tester</span></span>  
  
1.  <span data-ttu-id="44911-125">Überprüfen Sie, ob [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client installiert ist. Gehen Sie dazu wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="44911-125">Verify that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client is installed, as follows:</span></span>  
  
    1.  <span data-ttu-id="44911-126">Zeigen Sie im **Startmenü** auf **Einstellungen**, und klicken Sie dann auf **Systemsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="44911-126">From the **Start** menu, point to **Settings**, and then click **Control Panel**.</span></span>  
  
    2.  <span data-ttu-id="44911-127">Öffnen **Sie** in der Systemsteuerung die Option Software.</span><span class="sxs-lookup"><span data-stu-id="44911-127">In Control Panel, open **Add or Remove Programs**</span></span>  
  
    3.  <span data-ttu-id="44911-128">Überprüfen Sie in der Liste der derzeit installierten Programme, ob **Microsoft SQL Server Native Client** in der Liste angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="44911-128">In the list of currently installed programs, verify that **Microsoft SQL Server Native Client** appears in the list.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="44911-129">Wenn Sie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client installieren müssen, finden Sie weitere Informationen unter [Installieren von SQL Server Native Client](../native-client/applications/installing-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="44911-129">If you need to install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, see [Installing SQL Server Native Client](../native-client/applications/installing-sql-server-native-client.md).</span></span>  
  
2.  <span data-ttu-id="44911-130">Überprüfen Sie, ob die für den Clientcomputer installierte MDAC-Version 2.6 oder höher ist.</span><span class="sxs-lookup"><span data-stu-id="44911-130">Verify that the version of MDAC installed for the client computer is 2.6 or later.</span></span> <span data-ttu-id="44911-131">Wenn Sie MDAC-Versionsinformationen überprüfen müssen, können Sie das MDAC Component Checker-Tool verwenden, das als kostenloser Download von der Microsoft-Website bereitgestellt wird [https://www.microsoft.com/](https://www.microsoft.com/) .</span><span class="sxs-lookup"><span data-stu-id="44911-131">If you need to verify MDAC version information, you can use the MDAC Component Checker tool, which is provided as free download from the Microsoft Web site [https://www.microsoft.com/](https://www.microsoft.com/).</span></span> <span data-ttu-id="44911-132">Weitere Informationen finden Sie auf der Microsoft-Website unter "MDAC Component Checker".</span><span class="sxs-lookup"><span data-stu-id="44911-132">For more information, search on "MDAC Component Checker" on the Microsoft Web site.</span></span>  
  
3.  <span data-ttu-id="44911-133">Führen Sie das Skript aus.</span><span class="sxs-lookup"><span data-stu-id="44911-133">Execute the script.</span></span>  
  
     <span data-ttu-id="44911-134">Sie können die VBScript-Datei entweder an der Befehlszeile mit Cscript.exe oder durch Doppelklicken auf die Sqlxml4test.vbs-Datei ausführen, um Windows Script Host (WScript.exe) aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="44911-134">You can execute the VBScript file either at the command line using Cscript.exe or by double-clicking Sqlxml4test.vbs file to invoke the Windows Script Host (WScript.exe).</span></span>  
  
     <span data-ttu-id="44911-135">Bei der Ausführung sollte das Skript eine Meldung mit dem Hinweis anzeigen, dass die Ausführung des Skripts eine Weile in Anspruch nehmen kann, bevor Abfrageergebnisse als Skriptausgabe zurückgegeben und angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="44911-135">When executed, the script should display a message to alert you that the script might take a few moments to execute before returning and displaying query results as script output.</span></span> <span data-ttu-id="44911-136">Wenn die Ausgabe angezeigt wird, vergleichen Sie den Inhalt mit den für das Beispiel erwarteten Ergebnissen.</span><span class="sxs-lookup"><span data-stu-id="44911-136">When the output appears, compare its contents to the expected results for the sample.</span></span>  
  
  
