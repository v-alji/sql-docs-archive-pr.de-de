---
title: Verwenden von Verbindungs Servern in SMO | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- linked servers [SQL Server], SMO
ms.assetid: 0ea8837b-2596-4df1-b065-3bb717c9f22c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 58804e2be1edfa685a57f56c173c77a50e0f9126
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609066"
---
# <a name="using-linked-servers-in-smo"></a><span data-ttu-id="745e7-102">Verwenden von Verbindungsservern in SMO</span><span class="sxs-lookup"><span data-stu-id="745e7-102">Using Linked Servers in SMO</span></span>
  <span data-ttu-id="745e7-103">Ein Verbindungsserver stellt eine OLE DB-Datenquelle auf einem Remoteserver dar.</span><span class="sxs-lookup"><span data-stu-id="745e7-103">A linked server represents an OLE DB data source on a remote server.</span></span> <span data-ttu-id="745e7-104">Remote-OLE DB-Datenquellen werden mit dem <xref:Microsoft.SqlServer.Management.Smo.LinkedServer>-Objekt mithilfe der Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] verknüpft.</span><span class="sxs-lookup"><span data-stu-id="745e7-104">Remote OLE DB data sources are linked to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using the <xref:Microsoft.SqlServer.Management.Smo.LinkedServer> object.</span></span>  
  
 <span data-ttu-id="745e7-105">Remote-Datenbankserver können [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] mithilfe eines OLE DB Anbieters mit der aktuellen Instanz von verknüpft werden.</span><span class="sxs-lookup"><span data-stu-id="745e7-105">Remote database servers can be linked to the current instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using an OLE DB Provider.</span></span> <span data-ttu-id="745e7-106">In SMO werden Verbindungsserver durch das <xref:Microsoft.SqlServer.Management.Smo.LinkedServer>-Objekt dargestellt.</span><span class="sxs-lookup"><span data-stu-id="745e7-106">In SMO, linked servers are represented by the <xref:Microsoft.SqlServer.Management.Smo.LinkedServer> object.</span></span> <span data-ttu-id="745e7-107">Die <xref:Microsoft.SqlServer.Management.Smo.LinkedServer.LinkedServerLogins%2A>-Eigenschaft verweist auf eine Auflistung von <xref:Microsoft.SqlServer.Management.Smo.LinkedServerLogin>-Objekten.</span><span class="sxs-lookup"><span data-stu-id="745e7-107">The <xref:Microsoft.SqlServer.Management.Smo.LinkedServer.LinkedServerLogins%2A> property references a collection of <xref:Microsoft.SqlServer.Management.Smo.LinkedServerLogin> objects.</span></span> <span data-ttu-id="745e7-108">Diese speichern die Anmeldeinformationen, die erforderlich sind, um eine Verbindung mit dem Verbindungsserver herzustellen.</span><span class="sxs-lookup"><span data-stu-id="745e7-108">These store the logon credentials that are required to establish a connection with the linked server.</span></span>  
  
## <a name="ole-db-providers"></a><span data-ttu-id="745e7-109">OLE DB-Anbieter</span><span class="sxs-lookup"><span data-stu-id="745e7-109">OLE-DB Providers</span></span>  
 <span data-ttu-id="745e7-110">In SMO werden installierte OLE-DB-Anbieter durch eine Auflistung von <xref:Microsoft.SqlServer.Management.Smo.OleDbProviderSettings>-Objekten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="745e7-110">In SMO, installed OLE-DB providers are represented by a collection of <xref:Microsoft.SqlServer.Management.Smo.OleDbProviderSettings> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="745e7-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="745e7-111">Example</span></span>  
 <span data-ttu-id="745e7-112">Für das folgende Codebeispiel müssen Sie die Programmierungsumgebung, die Programmiervorlage und die Programmiersprache auswählen, um Ihre Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="745e7-112">For the following code example, you will have to select the programming environment, programming template and the programming language to create your application.</span></span> <span data-ttu-id="745e7-113">Weitere Informationen finden Sie unter [Erstellen eines Visual Basic SMO-Projekts in Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) und [Erstellen eines Visual C&#35; SMO-Projekts in Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="745e7-113">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) and [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-a-link-to-an-ole-db-provider-server-in-visual-basic"></a><span data-ttu-id="745e7-114">Erstellen eines Links zu einem OLE DB-Anbieterserver in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="745e7-114">Creating a link to an OLE-DB Provider Server in Visual Basic</span></span>  
 <span data-ttu-id="745e7-115">Im folgenden Codebeispiel wird veranschaulicht, wie ein Link zu einer heterogenen [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] OLE DB-Datenquelle mithilfe des <xref:Microsoft.SqlServer.Management.Smo.LinkedServer>-Objekts erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="745e7-115">The code example shows how to create a link to a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] OLE DB, heterogeneous data source by using the <xref:Microsoft.SqlServer.Management.Smo.LinkedServer> object.</span></span> <span data-ttu-id="745e7-116">Durch die Angabe von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] als Produktname wird über den [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Client OLE DB-Anbieter auf die Daten auf einem Verbindungsserver zugegriffen. Dies ist der offizielle OLE DB-Anbieter für [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="745e7-116">By specifying [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] as the product name, data is accessed on the linked server by using the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Client OLE DB Provider, which is the official OLE DB provider for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBLinkedServers1](SMO How to#SMO_VBLinkedServers1)]  -->  
  
## <a name="creating-a-link-to-an-ole-db-provider-server-in-visual-c"></a><span data-ttu-id="745e7-117">Erstellen eines Links zu einem OLE DB-Anbieterserver in Visual C#</span><span class="sxs-lookup"><span data-stu-id="745e7-117">Creating a link to an OLE-DB Provider Server in Visual C#</span></span>  
 <span data-ttu-id="745e7-118">Im folgenden Codebeispiel wird veranschaulicht, wie ein Link zu einer heterogenen [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] OLE DB-Datenquelle mithilfe des <xref:Microsoft.SqlServer.Management.Smo.LinkedServer>-Objekts erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="745e7-118">The code example shows how to create a link to a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] OLE DB, heterogeneous data source by using the <xref:Microsoft.SqlServer.Management.Smo.LinkedServer> object.</span></span> <span data-ttu-id="745e7-119">Durch die Angabe von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] als Produktname wird über den [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Client OLE DB-Anbieter auf die Daten auf einem Verbindungsserver zugegriffen. Dies ist der offizielle OLE DB-Anbieter für [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="745e7-119">By specifying [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] as the product name, data is accessed on the linked server by using the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Client OLE DB Provider, which is the official OLE DB provider for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
```csharp
//Connect to the local, default instance of SQL Server.   
{   
   Server srv = new Server();   
   //Create a linked server.   
   LinkedServer lsrv = default(LinkedServer);   
   lsrv = new LinkedServer(srv, "OLEDBSRV");   
   //When the product name is SQL Server the remaining properties are   
   //not required to be set.   
   lsrv.ProductName = "SQL Server";   
   lsrv.Create();   
}   
```  
  
## <a name="creating-a-link-to-an-ole-db-provider-server-in-powershell"></a><span data-ttu-id="745e7-120">Erstellen eines Links zu einem OLE DB-Anbieterserver in PowerShell</span><span class="sxs-lookup"><span data-stu-id="745e7-120">Creating a link to an OLE-DB Provider Server in PowerShell</span></span>  
 <span data-ttu-id="745e7-121">Im folgenden Codebeispiel wird veranschaulicht, wie ein Link zu einer heterogenen [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] OLE DB-Datenquelle mithilfe des <xref:Microsoft.SqlServer.Management.Smo.LinkedServer>-Objekts erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="745e7-121">The code example shows how to create a link to a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] OLE DB, heterogeneous data source by using the <xref:Microsoft.SqlServer.Management.Smo.LinkedServer> object.</span></span> <span data-ttu-id="745e7-122">Durch die Angabe von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] als Produktname wird über den [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Client OLE DB-Anbieter auf die Daten auf einem Verbindungsserver zugegriffen. Dies ist der offizielle OLE DB-Anbieter für [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="745e7-122">By specifying [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] as the product name, data is accessed on the linked server by using the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Client OLE DB Provider, which is the official OLE DB provider for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
```powershell
#Get a server object which corresponds to the default instance  
$svr = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Server  
  
#Create a linked server object which corresponds to an OLEDB type of SQL server product  
$lsvr = New-Object -TypeName Microsoft.SqlServer.Management.SMO.LinkedServer -ArgumentList $svr,"OLEDBSRV"  
  
#When the product name is SQL Server the remaining properties are not required to be set.
$lsvr.ProductName = "SQL Server"
  
#Create the Database Object  
$lsvr.Create()
```  
