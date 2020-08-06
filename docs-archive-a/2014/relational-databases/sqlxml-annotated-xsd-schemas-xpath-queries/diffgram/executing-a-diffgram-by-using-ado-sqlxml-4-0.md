---
title: Ausführen eines DiffGram mithilfe von ADO (SQLXML 4,0) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- providers [SQLXML], SQLOLEDB Provider
- ADO [SQLXML]
- SQLXMLOLEDB Provider, DiffGrams
- data providers [SQLXML], SQLOLEDB Provider
- DiffGrams [SQLXML], ADO
ms.assetid: 741fce82-de83-4923-86eb-30acb5b9a5e6
author: rothja
ms.author: jroth
ms.openlocfilehash: b96db25fd46b1ecbbc15c8acd912743e5560f178
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618595"
---
# <a name="executing-a-diffgram-by-using-ado-sqlxml-40"></a><span data-ttu-id="d615d-102">Ausführen eines DiffGram-Objekts mit ADO (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="d615d-102">Executing a DiffGram by Using ADO (SQLXML 4.0)</span></span>
  <span data-ttu-id="d615d-103">Diese [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic-Anwendung verwendet ADO, um eine Verbindung mit einer Instanz von Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] herzustellen, und führt dann ein DiffGram-Objekt aus.</span><span class="sxs-lookup"><span data-stu-id="d615d-103">This [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic application uses ADO to establish a connection to an instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and then executes a DiffGram.</span></span> <span data-ttu-id="d615d-104">In dieser Anwendung werden das DiffGram-Objekt und das XSD-Schema in einer Datei gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d615d-104">In this application, the DiffGram and the XSD schema are stored in a file.</span></span> <span data-ttu-id="d615d-105">Die Anwendung lädt das DiffGram-Objekt aus der angegebenen Datei.</span><span class="sxs-lookup"><span data-stu-id="d615d-105">The application loads the DiffGram from the specified file.</span></span> <span data-ttu-id="d615d-106">Sie können jedes der DiffGrams (und des zugehörigen XSD-Schemas) verwenden, das unter [DiffGram-Beispiele](diffgram-examples-sqlxml-4-0.md)beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="d615d-106">You can use any of the DiffGrams (and the associated XSD schema) described in [DiffGram Examples](diffgram-examples-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="d615d-107">Das ist der Ablauf bei der Beispielanwendung:</span><span class="sxs-lookup"><span data-stu-id="d615d-107">This is the process for the sample application:</span></span>  
  
-   <span data-ttu-id="d615d-108">Das **conn** -Objekt (**ADODB. Verbindung**) stellt eine Verbindung mit einer laufenden Instanz von SQL Server auf einem bestimmten Server her.</span><span class="sxs-lookup"><span data-stu-id="d615d-108">The **conn** object (**ADODB.Connection**) establishes a connection to a running instance of SQL Server on a specific server.</span></span>  
  
-   <span data-ttu-id="d615d-109">Das **cmd** -Objekt (**ADODB. Command**) wird auf der eingerichteten Verbindung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d615d-109">The **cmd** object (**ADODB.Command**) executes on the established connection.</span></span>  
  
-   <span data-ttu-id="d615d-110">Der Befehlsdialekt wird auf DBGUID_MSSQLXML festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d615d-110">The command dialect is set to DBGUID_MSSQLXML.</span></span>  
  
-   <span data-ttu-id="d615d-111">Das DiffGram-Objekt wird aus einer Datei in den Befehlsdaten Strom (**straumin**) kopiert.</span><span class="sxs-lookup"><span data-stu-id="d615d-111">The DiffGram is copied to the command stream (**strmIn**) from a file.</span></span>  
  
-   <span data-ttu-id="d615d-112">Der Ausgabestream des Befehls wird auf das Objekt " **straumout** " (**ADODB) festgelegt. Stream**), um alle zurückgegebenen Daten zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="d615d-112">The command's output stream is set to the **StrmOut** object (**ADODB.Stream**) to receive any returned data.</span></span>  
  
-   <span data-ttu-id="d615d-113">Wenn Sie den SQLOLEDB-Anbieter verwenden, wird die Microsoft SQLXML-Funktionalität standardmäßig von Sqlxmlx.dll bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="d615d-113">When you are using the SQLOLEDB Provider, by default you will get the Microsoft SQLXML functionality provided by Sqlxmlx.dll.</span></span> <span data-ttu-id="d615d-114">Wenn Sie Sqlxml4.dll mit dem SQLOLEDB-Anbieter verwenden möchten, muss die **SQLXML-Versions** Eigenschaft für das SQLOLEDB-Anbieter **Verbindungs** Objekt auf **SQLXML. 4.0** festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="d615d-114">To use Sqlxml4.dll with the SQLOLEDB Provider, the **SQLXML Version** property must be set to **SQLXML.4.0** on the SQLOLEDB Provider **Connection** object.</span></span>  
  
-   <span data-ttu-id="d615d-115">Der Befehl (DiffGram) wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d615d-115">The command (DiffGram) is executed.</span></span>  
  
 <span data-ttu-id="d615d-116">Der folgende Code stellt die Beispielanwendung dar.</span><span class="sxs-lookup"><span data-stu-id="d615d-116">The following code is the sample application.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d615d-117">Im Code müssen Sie den Namen der Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in der Verbindungszeichenfolge bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="d615d-117">In the code, you must provide the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span>  
  
```  
Private Sub Command1_Click()  
  Dim cmd As New ADODB.Command  
  Dim conn As New ADODB.Connection  
  Dim strmOut As New ADODB.Stream  
  Dim strmIn As New ADODB.Stream  
  
  'Open a connection to SQL Server.  
  conn.Provider = "SQLOLEDB"  
  conn.Open "server=SqlServerName; database=tempdb; Integrated Security=SSPI; "  
  conn.Properties("SQLXML Version") = "SQLXML.4.0"  
  Set cmd.ActiveConnection = conn  
  strmIn.Open  
  strmIn.Charset = "UTF-8"  
  strmIn.LoadFromFile "C:\SomeFilePath\SampleDiffGram.xml"  
  strmIn.Position = 0  
  Set cmd.CommandStream = strmIn  
  
  strmOut.Open  
  cmd.Properties("Output Stream").Value = strmOut  
  cmd.Properties("Output Encoding").Value = "UTF-8"  
  
  cmd.Dialect = "{5d531cb2-e6ed-11d2-b252-00c04f681b71}"  
  cmd.Properties("Mapping Schema") = "C:\SomeFilePath\SampleDiffGram.xml"  
  cmd.Execute , , adExecuteStream  
  strmOut.Position = 0  
  Set cmd = Nothing  
  strmOut.Charset = "UTF-8"  
  strmOut.SaveToFile "C:\DropIt.txt", adSaveCreateOverWrite  
  strmOut.Close  
  Set strmOut = Nothing  
  
End Sub  
```  
  
### <a name="to-test-the-diffgram"></a><span data-ttu-id="d615d-118">So testen Sie das DiffGram-Objekt</span><span class="sxs-lookup"><span data-stu-id="d615d-118">To test the DiffGram</span></span>  
  
1.  <span data-ttu-id="d615d-119">Kopieren Sie in einen Ordner auf Ihrem Computer eines der Diffgrams und das entsprechende XSD-Schema aus einem der Beispiele in [DiffGram-Beispielen](diffgram-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="d615d-119">To a folder on your computer, copy any one of the DiffGrams and the corresponding XSD schema from one of the examples in [DiffGram Examples](diffgram-examples-sqlxml-4-0.md).</span></span>  
  
2.  <span data-ttu-id="d615d-120">Öffnen Sie Visual Basic, und erstellen Sie ein Standard-EXE-Projekt.</span><span class="sxs-lookup"><span data-stu-id="d615d-120">Open Visual Basic and create a Standard EXE project.</span></span>  
  
3.  <span data-ttu-id="d615d-121">Fügen Sie dem Projekt die folgenden Verweise hinzu:</span><span class="sxs-lookup"><span data-stu-id="d615d-121">Add these references to the project:</span></span>  
  
    ```  
    Microsoft ActiveX Data Objects 2.8 Library  
    ```  
  
4.  <span data-ttu-id="d615d-122">Klicken Sie in der Toolbox auf **CommandButton**, und zeichnen Sie dann eine Schaltfläche im Formular.</span><span class="sxs-lookup"><span data-stu-id="d615d-122">In the Toolbox, click **CommandButton**, and then draw a button on the form.</span></span>  
  
5.  <span data-ttu-id="d615d-123">Doppelklicken Sie auf die Schaltfläche, um den Code zu bearbeiten, und fügen Sie den Anwendungscode aus dem Dokument hinzu.</span><span class="sxs-lookup"><span data-stu-id="d615d-123">Double-click the button to edit the code, and add the application code that is provided in the topic.</span></span>  
  
6.  <span data-ttu-id="d615d-124">Bearbeiten Sie den Code, um das DiffGram-Objekt und die XSD-Dateinamen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="d615d-124">Edit the code to specify the DiffGram and XSD file names.</span></span> <span data-ttu-id="d615d-125">Bearbeiten Sie außerdem die Verbindungszeichenfolge nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="d615d-125">Also edit the connection string as appropriate.</span></span>  
  
7.  <span data-ttu-id="d615d-126">Führen Sie die Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="d615d-126">Execute the application.</span></span> <span data-ttu-id="d615d-127">Das Ergebnis der Ausführung hängt davon ab, was für ein DiffGram-Objekt Sie ausführen.</span><span class="sxs-lookup"><span data-stu-id="d615d-127">The result of the execution depends on what DiffGram you are executing.</span></span>  
  
  
