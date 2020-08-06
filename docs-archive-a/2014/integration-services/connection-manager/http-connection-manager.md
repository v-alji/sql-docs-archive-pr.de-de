---
title: HTTP-Verbindungs-Manager | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- HTTP connection manager
- Web site connections [Integration Services]
- connection managers [Integration Services], HTTP
- Web server connections [Integration Services]
- connections [Integration Services], HTTP
ms.assetid: 26b2b3e1-d02c-46ca-8d31-7aef2bbc3c53
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 10c9f0778faa25aff8db4ad54ecaa8d3ccc5b359
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724029"
---
# <a name="http-connection-manager"></a><span data-ttu-id="5e030-102">HTTP-Verbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="5e030-102">HTTP Connection Manager</span></span>
  <span data-ttu-id="5e030-103">Eine HTTP-Verbindung ermöglicht Paketen den Zugriff auf einen Webserver, indem zum Senden und Empfangen von Dateien HTTP verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5e030-103">An HTTP connection enables a package to access a Web server by using HTTP to send or receive files.</span></span> <span data-ttu-id="5e030-104">Der Task „Webdienst“ von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] verwendet diesen Verbindungs-Manager.</span><span class="sxs-lookup"><span data-stu-id="5e030-104">The Web Service task that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes uses this connection manager.</span></span>  
  
 <span data-ttu-id="5e030-105">Wenn Sie einem Paket einen HTTP-Verbindungs-Manager hinzufügen, erstellt [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] einen Verbindungs-Manager, der zur Laufzeit in eine HTTP-Verbindung aufgelöst wird, die Eigenschaften des Verbindungs-Managers festlegt und der `Connections`-Auflistung im Paket den Verbindungs-Manager hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="5e030-105">When you add an HTTP connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to an HTTP connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span>  
  
 <span data-ttu-id="5e030-106">Die `ConnectionManagerType`-Eigenschaft des Verbindungs-Managers ist festgelegt auf `HTTP.`</span><span class="sxs-lookup"><span data-stu-id="5e030-106">The `ConnectionManagerType` property of the connection manager is set to `HTTP.`</span></span>  
  
 <span data-ttu-id="5e030-107">Es gibt folgende Möglichkeiten, um den HTTP-Verbindungs-Manager zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="5e030-107">You can configure the HTTP connection manager the following ways:</span></span>  
  
-   <span data-ttu-id="5e030-108">Verwenden Sie Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="5e030-108">Use credentials.</span></span> <span data-ttu-id="5e030-109">Falls der Verbindungs-Manager Anmeldeinformationen verwendet, enthalten die Eigenschaften den Benutzernamen, ein Kennwort und eine Domäne.</span><span class="sxs-lookup"><span data-stu-id="5e030-109">If the connection manager uses credentials, its properties include the user name, password, and domain.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="5e030-110">Der HTTP-Verbindungs-Manager unterstützt nur die anonyme Authentifizierung und die Standardauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="5e030-110">The HTTP connection manager supports only anonymous authentication and basic authentication.</span></span> <span data-ttu-id="5e030-111">Er unterstützt keine Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="5e030-111">It does not support Windows Authentication.</span></span>  
  
-   <span data-ttu-id="5e030-112">Verwenden Sie ein Clientzertifikat.</span><span class="sxs-lookup"><span data-stu-id="5e030-112">Use a client certificate.</span></span> <span data-ttu-id="5e030-113">Falls der Verbindungs-Manager ein Clientzertifikat verwendet, enthalten die Eigenschaften den Zertifikatnamen.</span><span class="sxs-lookup"><span data-stu-id="5e030-113">If the connection manager uses a client certificate, its properties include the certificate name.</span></span>  
  
-   <span data-ttu-id="5e030-114">Stellen Sie ein Timeout für Verbindungen mit dem Server und eine Segmentgröße zum Schreiben von Daten bereit.</span><span class="sxs-lookup"><span data-stu-id="5e030-114">Provide a time-out for connecting to the server and a chunk size for writing data.</span></span>  
  
-   <span data-ttu-id="5e030-115">Verwenden Sie einen Proxyserver.</span><span class="sxs-lookup"><span data-stu-id="5e030-115">Use a proxy server.</span></span> <span data-ttu-id="5e030-116">Für den Proxyserver können Sie auch konfigurieren, dass Anmeldeinformationen verwendet werden und der Proxyserver umgangen wird und stattdessen lokale Adressen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5e030-116">The proxy server can also be configured to use credentials and to bypass the proxy server and use local addresses instead.</span></span>  
  
## <a name="configuration-of-the-http-connection-manager"></a><span data-ttu-id="5e030-117">Konfiguration des HTTP-Verbindungs-Managers</span><span class="sxs-lookup"><span data-stu-id="5e030-117">Configuration of the HTTP Connection Manager</span></span>  
 <span data-ttu-id="5e030-118">Sie können Eigenschaften mit dem [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="5e030-118">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="5e030-119">Klicken Sie auf eines der folgenden Themen, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer festlegen können:</span><span class="sxs-lookup"><span data-stu-id="5e030-119">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="5e030-120">HTTP-Verbindungs-Manager-Editor &#40;Seite „Server“&#41;</span><span class="sxs-lookup"><span data-stu-id="5e030-120">HTTP Connection Manager Editor &#40;Server Page&#41;</span></span>](../http-connection-manager-editor-server-page.md)  
  
-   [<span data-ttu-id="5e030-121">HTTP-Verbindungs-Manager-Editor &#40;Seite „Proxy“&#41;</span><span class="sxs-lookup"><span data-stu-id="5e030-121">HTTP Connection Manager Editor &#40;Proxy Page&#41;</span></span>](../http-connection-manager-editor-proxy-page.md)  
  
 <span data-ttu-id="5e030-122">Weitere Informationen zum programmgesteuerten Konfigurieren eines Verbindungs-Managers finden Sie unter <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>.</span><span class="sxs-lookup"><span data-stu-id="5e030-122">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e030-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5e030-123">See Also</span></span>  
 <span data-ttu-id="5e030-124">[Webdienst (Task)](../control-flow/web-service-task.md) </span><span class="sxs-lookup"><span data-stu-id="5e030-124">[Web Service Task](../control-flow/web-service-task.md) </span></span>  
 [<span data-ttu-id="5e030-125">Integration Services-Verbindungen &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="5e030-125">Integration Services &#40;SSIS&#41; Connections</span></span>](integration-services-ssis-connections.md)  
  
  
