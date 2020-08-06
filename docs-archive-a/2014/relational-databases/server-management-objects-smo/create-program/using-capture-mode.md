---
title: Verwenden des Aufzeichnungsmodus | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- SQL Server Management Objects, capture mode
- capture mode [SMO]
- SMO [SQL Server], capture mode
ms.assetid: ace29bf0-705a-434f-82e4-db99d01c5008
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4ac69b9403329846b38c7ff61c645eb9879b6225
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719795"
---
# <a name="using-capture-mode"></a><span data-ttu-id="79634-102">Verwenden des Aufzeichnungsmodus</span><span class="sxs-lookup"><span data-stu-id="79634-102">Using Capture Mode</span></span>
  <span data-ttu-id="79634-103">SMO-Programme können die entsprechenden [!INCLUDE[tsql](../../../includes/tsql-md.md)]-Anweisungen, die vom Programm anstelle der ausgeführten Anweisungen (oder zusätzlich zu diesen) ausgegeben werden, aufzeichnen.</span><span class="sxs-lookup"><span data-stu-id="79634-103">SMO programs can capture and record the equivalent [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements issued by the program in place of, or in addition to, the statements that are executed by the program.</span></span> <span data-ttu-id="79634-104">Sie können den Aufzeichnungsmodus mithilfe des <xref:Microsoft.SqlServer.Management.Common.ServerConnection>-Objekts oder mithilfe der <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A>-Eigenschaft des <xref:Microsoft.SqlServer.Management.Smo.Server>-Objekts aktivieren.</span><span class="sxs-lookup"><span data-stu-id="79634-104">You enable capture mode by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object, or by using the <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Server> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79634-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="79634-105">Example</span></span>  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="enabling-capture-mode-in-visual-basic"></a><span data-ttu-id="79634-106">Aktivieren des Aufzeichnungsmodus in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="79634-106">Enabling Capture Mode in Visual Basic</span></span>  
 <span data-ttu-id="79634-107">In diesem Codebeispiel wird zunächst der Aufzeichnungsmodus aktiviert, anschließend werden die im Aufzeichnungspuffer enthaltenen [!INCLUDE[tsql](../../../includes/tsql-md.md)]-Befehle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="79634-107">This code example enables capture mode, and then displays the [!INCLUDE[tsql](../../../includes/tsql-md.md)] commands held in the capture buffer.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBCapture1](SMO How to#SMO_VBCapture1)]  -->  
  
## <a name="enabling-capture-mode-in-visual-c"></a><span data-ttu-id="79634-108">Aktivieren des Aufzeichnungsmodus in Visual C#</span><span class="sxs-lookup"><span data-stu-id="79634-108">Enabling Capture Mode in Visual C#</span></span>  
 <span data-ttu-id="79634-109">In diesem Codebeispiel wird zunächst der Aufzeichnungsmodus aktiviert, anschließend werden die im Aufzeichnungspuffer enthaltenen [!INCLUDE[tsql](../../../includes/tsql-md.md)]-Befehle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="79634-109">This code example enables capture mode, and then displays the [!INCLUDE[tsql](../../../includes/tsql-md.md)] commands held in the capture buffer.</span></span>  
  
```  
{   
// Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
// Set the execution mode to CaptureSql for the connection.   
srv.ConnectionContext.SqlExecutionModes = SqlExecutionModes.CaptureSql;   
// Make a modification to the server that is to be captured.   
srv.UserOptions.AnsiNulls = true;   
srv.Alter();   
// Iterate through the strings in the capture buffer and display the captured statements.   
string s;   
foreach ( String p_s in srv.ConnectionContext.CapturedSql.Text ) {   
   Console.WriteLine(p_s);   
}   
// Execute the captured statements.   
srv.ConnectionContext.ExecuteNonQuery(srv.ConnectionContext.CapturedSql.Text);   
// Revert to immediate execution mode.   
srv.ConnectionContext.SqlExecutionModes = SqlExecutionModes.ExecuteSql;   
}  
```  
  
  
