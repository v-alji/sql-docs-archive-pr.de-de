---
title: Verwenden von Nachrichten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- messages [SMO]
ms.assetid: 4037a866-4826-4c1f-890c-e7e3658adf13
author: stevestein
ms.author: sstein
ms.openlocfilehash: 53b2e0fa4be2dfd53cdd8f4f0cacb7ae0bd79edb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621437"
---
# <a name="using-messages"></a><span data-ttu-id="3fc94-102">Verwenden von Meldungen</span><span class="sxs-lookup"><span data-stu-id="3fc94-102">Using Messages</span></span>
  <span data-ttu-id="3fc94-103">In SMO werden Systemmeldungen durch das <xref:Microsoft.SqlServer.Management.Smo.SystemMessageCollection>-Objekt dargestellt, das zum `Server`-Objekt gehört.</span><span class="sxs-lookup"><span data-stu-id="3fc94-103">In SMO, system messages are represented by the <xref:Microsoft.SqlServer.Management.Smo.SystemMessageCollection> object that belongs to the `Server` object.</span></span> <span data-ttu-id="3fc94-104">Da die Systemmeldungen nicht geändert werden können, sind `SystemMessage`-Objekteigenschaften schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="3fc94-104">Because the system messages cannot be modified, `SystemMessage` object properties are read-only.</span></span>  
  
 <span data-ttu-id="3fc94-105">Benutzerdefinierte Meldungen werden programmgesteuert vom <xref:Microsoft.SqlServer.Management.Smo.UserDefinedMessageCollection>-Objekt in SMO dargestellt.</span><span class="sxs-lookup"><span data-stu-id="3fc94-105">User-defined messages are represented programmatically in SMO by the <xref:Microsoft.SqlServer.Management.Smo.UserDefinedMessageCollection> object.</span></span> <span data-ttu-id="3fc94-106">Vorhandene benutzerdefinierte Meldungen können ermittelt werden, indem man die Auflistung durchläuft.</span><span class="sxs-lookup"><span data-stu-id="3fc94-106">Existing user-defined messages can be discovered by iterating through the collection.</span></span> <span data-ttu-id="3fc94-107">Neue benutzerdefinierte Meldungen können durch Instanziierung eines neuen `UserDefinedMessage`-Objekts und Festlegung der entsprechenden Eigenschaften erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="3fc94-107">New user-defined messages can be created by instantiating a new `UserDefinedMessage` object and setting the appropriate properties.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="3fc94-108">Beispiele</span><span class="sxs-lookup"><span data-stu-id="3fc94-108">Examples</span></span>  
 <span data-ttu-id="3fc94-109">Für die folgenden Codebeispiele müssen Sie die Programmierungsumgebung, die Programmiervorlage und die Programmiersprache auswählen, um Ihre Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3fc94-109">For the following code examples, you will have to select the programming environment, programming template and the programming language to create your application.</span></span> <span data-ttu-id="3fc94-110">Weitere Informationen finden Sie unter [Erstellen eines Visual Basic SMO-Projekts in Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) und [Erstellen eines Visual C&#35; SMO-Projekts in Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="3fc94-110">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) and [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="finding-a-particular-system-message-in-visual-basic"></a><span data-ttu-id="3fc94-111">Suchen einer bestimmten Systemmeldung in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3fc94-111">Finding a Particular System Message in Visual Basic</span></span>  
 <span data-ttu-id="3fc94-112">Das Codebeispiel zeigt, wie eine Systemmeldung über die ID-Nummer identifiziert und die Meldung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="3fc94-112">The code example shows how to identify a system message by ID number and display the message.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBMessages1](SMO How to#SMO_VBMessages1)]  -->  
  
## <a name="finding-a-particular-system-message-in-visual-c"></a><span data-ttu-id="3fc94-113">Suchen einer bestimmten Systemmeldung in Visual C#</span><span class="sxs-lookup"><span data-stu-id="3fc94-113">Finding a Particular System Message in Visual C#</span></span>  
 <span data-ttu-id="3fc94-114">Das Codebeispiel zeigt, wie eine Systemmeldung über die ID-Nummer identifiziert und die Meldung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="3fc94-114">The code example shows how to identify a system message by ID number and display the message.</span></span>  
  
```csharp
{  
            //Connect to the local, default instance of SQL Server.   
            Server srv = new Server();  
            //Reference an existing system message using the   
            //ItemByIdAndLanguage method.   
            SystemMessage msg = default(SystemMessage);  
            msg = srv.SystemMessages.ItemByIdAndLanguage(14126, "us_english");  
            //Display the message ID and text.   
            Console.WriteLine(msg.ID.ToString() + " " + msg.Text);  
        }  
```  
  
## <a name="finding-a-particular-system-message-in-powershell"></a><span data-ttu-id="3fc94-115">Suchen einer bestimmten Systemmeldung in PowerShell</span><span class="sxs-lookup"><span data-stu-id="3fc94-115">Finding a Particular System Message in PowerShell</span></span>  
 <span data-ttu-id="3fc94-116">Das Codebeispiel zeigt, wie eine Systemmeldung über die ID-Nummer identifiziert und die Meldung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="3fc94-116">The code example shows how to identify a system message by ID number and display the message.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server.  
CD \sql\localhost\  
$srv = Get-Item default  
  
#Get the message 14126 in US English and display it  
$msg = $srv.SystemMessages.ItemByIdAndLanguage(14126, "us_english")  
$msg.ID.ToString() + " "+ $msg.Text  
```  
  
## <a name="adding-a-new-user-defined-message-in-visual-basic"></a><span data-ttu-id="3fc94-117">Hinzufügen einer neuen benutzerdefinierten Meldung in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3fc94-117">Adding a New User-Defined Message in Visual Basic</span></span>  
 <span data-ttu-id="3fc94-118">Das Codebeispiel zeigt, wie eine benutzerdefinierte Meldung mit einer ID größer als 50.000 erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="3fc94-118">The code example demonstrates how to create a user-defined message with an ID greater than 50000.</span></span>  
  
```vb
Dim mysrv As Server  
mysrv = New Server  
Dim udm As UserDefinedMessage  
udm = New UserDefinedMessage(mysrv, 50003, "us_english", 16, "Test message")  
udm.Create()  
```  
  
## <a name="adding-a-new-user-defined-message-in-visual-c"></a><span data-ttu-id="3fc94-119">Hinzufügen einer neuen benutzerdefinierten Meldung in Visual C#</span><span class="sxs-lookup"><span data-stu-id="3fc94-119">Adding a New User-Defined Message in Visual C#</span></span>  
 <span data-ttu-id="3fc94-120">Das Codebeispiel zeigt, wie eine benutzerdefinierte Meldung mit einer ID größer als 50.000 erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="3fc94-120">The code example demonstrates how to create a user-defined message with an ID greater than 50000.</span></span>  
  
```csharp
{
            Server mysrv = new Server();  
  
            UserDefinedMessage udm = new UserDefinedMessage(mysrv, 50030, "us_english",16, "Test message");  
            udm.Create();  
             UserDefinedMessage  msg = mysrv.UserDefinedMessages.ItemByIdAndLanguage(50030, "us_english");  
            //Display the message ID and text.   
            Console.WriteLine(msg.ID.ToString() + " " + msg.Text);  
  
        }  
```  
  
## <a name="adding-a-new-user-defined-message-in-powershell"></a><span data-ttu-id="3fc94-121">Hinzufügen einer neuen benutzerdefinierten Meldung in Visual C#</span><span class="sxs-lookup"><span data-stu-id="3fc94-121">Adding a New User-Defined Message in PowerShell</span></span>
 <span data-ttu-id="3fc94-122">Das Codebeispiel zeigt, wie eine benutzerdefinierte Meldung mit einer ID größer als 50.000 erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="3fc94-122">The code example demonstrates how to create a user-defined message with an ID greater than 50000.</span></span>  
  
```powershell
#Get a server object which corresponds to the default instance  
$srv = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Server  
  
#Create a new message
$udm = New-Object -TypeName Microsoft.SqlServer.Management.SMO.UserDefinedMessage -ArgumentList `  
$srv, 50030, "us_english", 16, "Test message"  
$udm.Create()  
$msg = $srv.UserDefinedMessages.ItemByIdAndLanguage(50030, "us_english");  
$msg  
```  
