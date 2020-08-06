---
title: Trennen der Verbindung zu einer Instanz von SQL Server | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- SQL Server Management Objects, disconnecting
- SMO [SQL Server], disconnecting
- instances of SQL Server, disconnecting
- disconnecting [SMO]
ms.assetid: 4ca7f7eb-6b3f-4c73-ac63-88afa8570b61
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3514fce8fb8f1ccc8bd1b54acfa27825eaebbd34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621995"
---
# <a name="disconnecting-from-an-instance-of-sql-server"></a><span data-ttu-id="0fdb3-102">Trennen der Verbindung zu einer Instanz von SQL Server</span><span class="sxs-lookup"><span data-stu-id="0fdb3-102">Disconnecting from an Instance of SQL Server</span></span>
  <span data-ttu-id="0fdb3-103">Das manuelle Schließen und Trennen der Verbindung von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects (SMO) ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0fdb3-103">Manually closing and disconnecting [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects (SMO) objects is not required.</span></span> <span data-ttu-id="0fdb3-104">Verbindungen werden bei Bedarf hergestellt und geschlossen.</span><span class="sxs-lookup"><span data-stu-id="0fdb3-104">Connections are opened and closed as required.</span></span>  
  
## <a name="connection-pooling"></a><span data-ttu-id="0fdb3-105">Verbindungspooling</span><span class="sxs-lookup"><span data-stu-id="0fdb3-105">Connection Pooling</span></span>  
 <span data-ttu-id="0fdb3-106">Wenn die <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Connect%2A>-Methode aufgerufen wird, wird die Verbindung nicht automatisch freigegeben.</span><span class="sxs-lookup"><span data-stu-id="0fdb3-106">When the <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Connect%2A> method is called, the connection is not automatically released.</span></span> <span data-ttu-id="0fdb3-107">Die <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Disconnect%2A>-Methode muss explizit aufgerufen werden, um die Verbindung zum Verbindungspool freizugeben.</span><span class="sxs-lookup"><span data-stu-id="0fdb3-107">The <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Disconnect%2A> method must be called explicitly to release the connection to the connection pool.</span></span> <span data-ttu-id="0fdb3-108">Sie können auch eine nicht in einem Pool enthaltene Verbindung anfordern.</span><span class="sxs-lookup"><span data-stu-id="0fdb3-108">Also, you can request a non-pooled connection.</span></span> <span data-ttu-id="0fdb3-109">Hierfür wird die <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.NonPooledConnection%2A>-Eigenschaft der <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A>-Eigenschaft, die auf das <xref:Microsoft.SqlServer.Management.Common.ServerConnection>-Objekt verweist, festgelegt.</span><span class="sxs-lookup"><span data-stu-id="0fdb3-109">You do this by setting the <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.NonPooledConnection%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A> property that references the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object.</span></span>  
  
## <a name="disconnecting-from-an-instance-of-sql-server-for-rmo"></a><span data-ttu-id="0fdb3-110">Trennen der Verbindung zu einer Instanz von SQL&#160;Server für RMO</span><span class="sxs-lookup"><span data-stu-id="0fdb3-110">Disconnecting from an Instance of SQL Server for RMO</span></span>  
 <span data-ttu-id="0fdb3-111">Das Schließen von Serververbindungen beim Programmieren mit RMO funktioniert etwas anders als mit SMO.</span><span class="sxs-lookup"><span data-stu-id="0fdb3-111">Closing server connections when you are programming with RMO works slightly different from SMO.</span></span>  
  
 <span data-ttu-id="0fdb3-112">Da die Server Verbindung für ein RMO-Objekt durch das-Objekt aufrechterhalten wird <xref:Microsoft.SqlServer.Management.Common.ServerConnection> , wird dieses Objekt auch verwendet, wenn eine Verbindung mit einer Instanz von getrennt wird, [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Wenn Sie mithilfe von RMO programmieren.</span><span class="sxs-lookup"><span data-stu-id="0fdb3-112">Because the server connection for an RMO object is maintained by the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object, this object is also used when disconnecting from an instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] when you program by using RMO.</span></span> <span data-ttu-id="0fdb3-113">Um mit dem <xref:Microsoft.SqlServer.Management.Common.ServerConnection>-Objekt eine Verbindung zu schließen, rufen Sie die <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Disconnect%2A>-Methode des RMO-Objekts auf.</span><span class="sxs-lookup"><span data-stu-id="0fdb3-113">To close a connection by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object, call the <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Disconnect%2A> method of the RMO object.</span></span> <span data-ttu-id="0fdb3-114">Nachdem die Verbindung geschlossen wurde, können keine RMO-Objekte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0fdb3-114">After the connection has been closed, RMO objects cannot be used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0fdb3-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0fdb3-115">Example</span></span>  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="closing-and-disconnecting-an-smo-object-in-visual-basic"></a><span data-ttu-id="0fdb3-116">Schließen und Trennen der Verbindung eines SMO-Objekts in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0fdb3-116">Closing and Disconnecting an SMO Object in Visual Basic</span></span>  
 <span data-ttu-id="0fdb3-117">Dieses Codebeispiel zeigt, wie Sie eine nicht in einem Pool enthaltene Verbindung anfordern, indem Sie die <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.NonPooledConnection%2A>-Eigenschaft der <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A>-Objekteigenschaft festlegen.</span><span class="sxs-lookup"><span data-stu-id="0fdb3-117">This code example shows how to request a non-pooled connection by setting the <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.NonPooledConnection%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A> object property.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VB4](SMO How to#SMO_VB4)]  -->  
  
## <a name="closing-and-disconnecting-an-smo-object-in-visual-c"></a><span data-ttu-id="0fdb3-118">Schließen und Trennen der Verbindung eines SMO-Objekts in Visual C#</span><span class="sxs-lookup"><span data-stu-id="0fdb3-118">Closing and Disconnecting an SMO Object in Visual C#</span></span>  
 <span data-ttu-id="0fdb3-119">Dieses Codebeispiel zeigt, wie Sie eine nicht in einem Pool enthaltene Verbindung anfordern, indem Sie die <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.NonPooledConnection%2A>-Eigenschaft der <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A>-Objekteigenschaft festlegen.</span><span class="sxs-lookup"><span data-stu-id="0fdb3-119">This code example shows how to request a non-pooled connection by setting the <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.NonPooledConnection%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A> object property.</span></span>  
  
```  
{   
Server srv;   
srv = new Server();   
//Disable automatic disconnection.   
srv.ConnectionContext.AutoDisconnectMode = AutoDisconnectMode.NoAutoDisconnect;   
//Connect to the local, default instance of SQL Server.   
srv.ConnectionContext.Connect();   
//The actual connection is made when a property is retrieved.   
Console.WriteLine(srv.Information.Version);   
//Disconnect explicitly.   
srv.ConnectionContext.Disconnect();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="0fdb3-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0fdb3-120">See Also</span></span>  
 <xref:Microsoft.SqlServer.Management.Smo.Server>   
 <xref:Microsoft.SqlServer.Management.Common.ServerConnection>  
  
  
