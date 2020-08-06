---
title: SMTP-Verbindungs-Manager | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- connections [Integration Services], SMTP
- SMTP connection manager [Integration Services]
- connection managers [Integration Services], SMTP
ms.assetid: 3795d442-714b-4bbb-9acd-75bf277a468a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f3c090ab672790901baae01ae86f8d22e008b4ac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724869"
---
# <a name="smtp-connection-manager"></a><span data-ttu-id="2a38f-102">SMTP-Verbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="2a38f-102">SMTP Connection Manager</span></span>
  <span data-ttu-id="2a38f-103">Mit einem SMTP-Verbindungs-Manager kann ein Paket eine Verbindung mit einem SMTP-Server (Simple Mail Transfer Protocol) herstellen.</span><span class="sxs-lookup"><span data-stu-id="2a38f-103">An SMTP connection manager enables a package to connect to a Simple Mail Transfer Protocol (SMTP) server.</span></span> <span data-ttu-id="2a38f-104">Der Task „Mail senden“ von [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] verwendet einen SMTP-Verbindungs-Manager.</span><span class="sxs-lookup"><span data-stu-id="2a38f-104">The Send Mail task that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes uses an SMTP connection manager.</span></span>  
  
 <span data-ttu-id="2a38f-105">Wenn Sie Microsoft Exchange als SMTP-Server verwenden, müssen Sie den SMTP-Verbindungs-Manager u. U. für die Verwendung der Windows-Authentifizierung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="2a38f-105">When using Microsoft Exchange as the SMTP server, you may need to configure the SMTP connection manager to use Windows Authentication.</span></span> <span data-ttu-id="2a38f-106">Exchange-Server können so konfiguriert werden, dass keine nicht authentifizierten SMTP-Verbindungen zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="2a38f-106">Exchange servers may be configured to not allow unauthenticated SMTP connections.</span></span>  
  
## <a name="configuration-the-smtp-connection-manager"></a><span data-ttu-id="2a38f-107">Konfiguration des SMTP-Verbindungs-Managers</span><span class="sxs-lookup"><span data-stu-id="2a38f-107">Configuration the SMTP Connection Manager</span></span>  
 <span data-ttu-id="2a38f-108">Wenn Sie einem Paket einen SMTP-Verbindungs-Manager hinzufügen, erstellt [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] einen Verbindungs-Manager, der zur Laufzeit in eine SMTP-Verbindung aufgelöst wird, die Eigenschaften des Verbindungs-Managers festlegt und der `Connections`-Auflistung im Paket den Verbindungs-Manager hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="2a38f-108">When you add an SMTP connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to an SMTP connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span> <span data-ttu-id="2a38f-109">Die `ConnectionManagerType`-Eigenschaft des Verbindungs-Managers ist auf `SMTP` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2a38f-109">The `ConnectionManagerType` property of the connection manager is set to `SMTP`.</span></span>  
  
 <span data-ttu-id="2a38f-110">Es gibt folgende Möglichkeiten, um einen SMTP-Verbindungs-Manager zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="2a38f-110">You can configure an SMTP connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="2a38f-111">Geben Sie eine Verbindungszeichenfolge an.</span><span class="sxs-lookup"><span data-stu-id="2a38f-111">Provide a connection string.</span></span>  
  
-   <span data-ttu-id="2a38f-112">Geben Sie den Namen eines SMTP-Servers an.</span><span class="sxs-lookup"><span data-stu-id="2a38f-112">Specify the name of an SMTP server.</span></span>  
  
-   <span data-ttu-id="2a38f-113">Geben Sie die zu verwendende Authentifizierungsmethode an.</span><span class="sxs-lookup"><span data-stu-id="2a38f-113">Specify the authentication method to use.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="2a38f-114">Der SMTP-Verbindungs-Manager unterstützt nur die anonyme Authentifizierung und die Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="2a38f-114">The SMTP connection manager supports only anonymous authentication and Windows Authentication.</span></span> <span data-ttu-id="2a38f-115">Er unterstützt keine Standardauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="2a38f-115">It does not support basic authentication.</span></span>  
  
-   <span data-ttu-id="2a38f-116">Geben Sie an, ob beim Senden von E-Mail-Nachrichten SSL (Secure Sockets Layer) zur Verschlüsselung der Kommunikation verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="2a38f-116">Specify whether to encrypt communication using Secure Sockets Layer (SSL) when sending e-mail messages.</span></span>  
  
 <span data-ttu-id="2a38f-117">Sie können Eigenschaften mit dem [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="2a38f-117">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="2a38f-118">Weitere Informationen zu den Eigenschaften, die Sie im [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer festlegen können, finden Sie unter [SMTP-Verbindungs-Manager-Editor](../smtp-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="2a38f-118">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [SMTP Connection Manager Editor](../smtp-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="2a38f-119">Weitere Informationen zum programmgesteuerten Konfigurieren eines Verbindungs-Managers finden Sie unter <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> und [Programmgesteuertes Hinzufügen von Verbindungen](../building-packages-programmatically/adding-connections-programmatically.md)festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2a38f-119">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
  
