---
title: Behandeln von SMO-Ausnahmen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- SMO [SQL Server], exceptions
- exceptions [SMO]
- SQL Server Management Objects, exceptions
- inner exceptions [SMO]
ms.assetid: 4c725ff2-6588-44ca-b86a-87979e164153
author: stevestein
ms.author: sstein
ms.openlocfilehash: f4ae9e475a019c9bf874ee3f8365f3f3ac8e19d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621983"
---
# <a name="handling-smo-exceptions"></a><span data-ttu-id="28772-102">Behandeln von SMO-Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="28772-102">Handling SMO Exceptions</span></span>
  <span data-ttu-id="28772-103">In verwaltetem Code werden Ausnahmen ausgelöst, wenn ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="28772-103">In managed code, exceptions are thrown when an error occurs.</span></span> <span data-ttu-id="28772-104">SMO-Methoden und -Eigenschaften melden keinen Erfolg oder Fehler mit dem Rückgabewert.</span><span class="sxs-lookup"><span data-stu-id="28772-104">SMO methods and properties do not report success or failure in the return value.</span></span> <span data-ttu-id="28772-105">Stattdessen können Ausnahmen von einem Ausnahmehandler abgefangen und behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="28772-105">Instead, exceptions can be caught and handled by an exception handler.</span></span>  
  
 <span data-ttu-id="28772-106">In SMO sind verschiedene Ausnahmeklassen vorhanden.</span><span class="sxs-lookup"><span data-stu-id="28772-106">Different exception classes exist in the SMO.</span></span> <span data-ttu-id="28772-107">Informationen über die Ausnahme können aus den Ausnahmeeigenschaften wie der `Message`-Eigenschaft, die eine Textmeldung über die Ausnahme angibt, extrahiert werden.</span><span class="sxs-lookup"><span data-stu-id="28772-107">Information about the exception can be extracted from the exception properties such as the `Message` property that gives a text message about the exception.</span></span>  
  
 <span data-ttu-id="28772-108">Die Ausnahmebehandlungsanweisungen sind für die Programmiersprache spezifisch.</span><span class="sxs-lookup"><span data-stu-id="28772-108">The exception handling statements are specific to the programming language.</span></span> <span data-ttu-id="28772-109">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic gibt es hierfür beispielsweise die `Catch`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="28772-109">For example, in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic it is the `Catch` statement.</span></span>  
  
## <a name="inner-exceptions"></a><span data-ttu-id="28772-110">Interne Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="28772-110">Inner Exceptions</span></span>  
 <span data-ttu-id="28772-111">Ausnahmen können entweder allgemein oder spezifisch sein.</span><span class="sxs-lookup"><span data-stu-id="28772-111">Exceptions can either be general or specific.</span></span> <span data-ttu-id="28772-112">Allgemeine Ausnahmen enthalten einen Satz spezifischer Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="28772-112">General exceptions contain a set of specific exceptions.</span></span> <span data-ttu-id="28772-113">Einige `Catch`-Anweisungen können dazu verwendet werden, erwartete Fehler zu behandeln und die übrigen Fehler an den allgemeinen Ausnahmebehandlungscode weiterzugeben.</span><span class="sxs-lookup"><span data-stu-id="28772-113">Several `Catch` statements can be used to handle anticipated errors and let remaining errors fall through to general exception handling code.</span></span> <span data-ttu-id="28772-114">Ausnahmen treten oft in einer überlappenden Sequenz auf.</span><span class="sxs-lookup"><span data-stu-id="28772-114">Exceptions often occur in a cascading sequence.</span></span> <span data-ttu-id="28772-115">Häufig wird eine SMO-Ausnahme von einer SQL-Ausnahme verursacht.</span><span class="sxs-lookup"><span data-stu-id="28772-115">Frequently, an SMO exception might have been caused by an SQL exception.</span></span> <span data-ttu-id="28772-116">Um dies zu ermitteln, wird die `InnerException`-Eigenschaft nacheinander verwendet. So wird die ursprüngliche Ausnahme bestimmt, die die letzte Ausnahme auf oberster Ebene ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="28772-116">The way to detect this is to use the `InnerException` property successively to determine the original exception that caused the final, top-level exception.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="28772-117">Die `SQLException` Ausnahme wird im Namespace " **System. Data. SqlClient** " deklariert.</span><span class="sxs-lookup"><span data-stu-id="28772-117">The `SQLException` exception is declared in the **System.Data.SqlClient** namespace.</span></span>  
  
 <span data-ttu-id="28772-118">![Diagramm mit Ausnahmeflussebenen](../../../database-engine/dev-guide/media/exception-flow.gif "Diagramm mit Ausnahmeflussebenen")</span><span class="sxs-lookup"><span data-stu-id="28772-118">![A diagram that shows the levels from which an excp](../../../database-engine/dev-guide/media/exception-flow.gif "A diagram that shows the levels from which an excp")</span></span>  
  
 <span data-ttu-id="28772-119">Die Abbildung zeigt den Verlauf der Ausnahmen durch die Anwendungsebenen.</span><span class="sxs-lookup"><span data-stu-id="28772-119">The diagram shows the flow of exceptions through the layers of the application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="28772-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="28772-120">Example</span></span>  
 <span data-ttu-id="28772-121">Zum Verwenden eines angegebenen Codebeispiels müssen Sie die Programmierumgebung, Programmiervorlage und die zu verwendende Programmiersprache auswählen, um Ihre Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="28772-121">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="28772-122">Weitere Informationen finden Sie unter [Erstellen eines Visual C-&#35; SMO-Projekts in Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md) oder [Erstellen eines Visual Basic SMO-Projekts in Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="28772-122">For more information, see [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md) or [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="catching-an-exception-in-visual-basic"></a><span data-ttu-id="28772-123">Abfangen einer Ausnahme in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="28772-123">Catching an Exception in Visual Basic</span></span>  
 <span data-ttu-id="28772-124">In diesem Codebeispiel wird gezeigt, wie die [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]-Anweisung `Try...Catch...Finally`verwendet wird, um eine SMO-Ausnahme abzufangen.</span><span class="sxs-lookup"><span data-stu-id="28772-124">This code example shows how to use the `Try...Catch...Finally`[!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] statement to catch a SMO exception.</span></span> <span data-ttu-id="28772-125">Alle SMO-Ausnahmen haben den Typ SmoException und werden im SMO-Verweis aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="28772-125">All SMO exceptions have the type SmoException, and are listed in the SMO reference.</span></span> <span data-ttu-id="28772-126">Die Sequenz von internen Ausnahmen wird angezeigt, um den Ursprung des Fehlers anzugeben.</span><span class="sxs-lookup"><span data-stu-id="28772-126">The sequence of inner exceptions is displayed to show the root of the error.</span></span> <span data-ttu-id="28772-127">Weitere Informationen finden Sie in der Dokumentation zu [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] .NET.</span><span class="sxs-lookup"><span data-stu-id="28772-127">For more information, see the [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] .NET documentation.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBExceptions1](SMO How to#SMO_VBExceptions1)]  -->  
  
## <a name="catching-an-exception-in-visual-c"></a><span data-ttu-id="28772-128">Abfangen einer Ausnahme in Visual C#</span><span class="sxs-lookup"><span data-stu-id="28772-128">Catching an Exception in Visual C#</span></span>  
 <span data-ttu-id="28772-129">In diesem Codebeispiel wird gezeigt, wie die Visual C#-Anweisung `Try...Catch...Finally` verwendet wird, um eine SMO-Ausnahme abzufangen.</span><span class="sxs-lookup"><span data-stu-id="28772-129">This code example shows how to use the `Try...Catch...Finally` Visual C# statement to catch a SMO exception.</span></span> <span data-ttu-id="28772-130">Alle SMO-Ausnahmen haben den Typ SmoException und werden im SMO-Verweis aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="28772-130">All SMO exceptions have the type SmoException, and are listed in the SMO reference.</span></span> <span data-ttu-id="28772-131">Die Sequenz von internen Ausnahmen wird angezeigt, um den Ursprung des Fehlers anzugeben.</span><span class="sxs-lookup"><span data-stu-id="28772-131">The sequence of inner exceptions is displayed to show the root of the error.</span></span> <span data-ttu-id="28772-132">Weitere Informationen finden Sie in der Dokumentation zu Visual C#.</span><span class="sxs-lookup"><span data-stu-id="28772-132">For more information, see the Visual C# documentation.</span></span>  
  
```  
{   
//This sample requires the Microsoft.SqlServer.Management.Smo.Agent namespace to be included.   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Define an Operator object variable by supplying the parent SQL Agent and the name arguments in the constructor.   
//Note that the Operator type requires [] parenthesis to differentiate it from a Visual Basic key word.   
op = new Operator(srv.JobServer, "Test_Operator");   
op.Create();   
//Start exception handling.   
try {   
    //Create the operator again to cause an SMO exception.   
    OperatorCategory opx;   
    opx = new OperatorCategory(srv.JobServer, "Test_Operator");   
    opx.Create();   
}   
//Catch the SMO exception   
catch (SmoException smoex) {   
    Console.WriteLine("This is an SMO Exception");   
   //Display the SMO exception message.   
   Console.WriteLine(smoex.Message);   
   //Display the sequence of non-SMO exceptions that caused the SMO exception.   
   Exception ex;   
   ex = smoex.InnerException;   
   while (!object.ReferenceEquals(ex.InnerException, (null))) {   
      Console.WriteLine(ex.InnerException.Message);   
      ex = ex.InnerException;   
    }   
    }   
   //Catch other non-SMO exceptions.   
   catch (Exception ex) {   
      Console.WriteLine("This is not an SMO exception.");   
}   
}  
```  
  
  
