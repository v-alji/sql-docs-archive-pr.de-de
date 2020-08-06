---
title: FTP-Verbindungs-Manager | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- FTP connection manager
- connections [Integration Services], FTP
- connection managers [Integration Services], FTP
ms.assetid: c4f43455-29ca-44ba-ac7f-ea729b1daf93
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a402f399ba4b7e69fc1d3cbca9dd64b32217ced1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697078"
---
# <a name="ftp-connection-manager"></a><span data-ttu-id="9269e-102">FTP-Verbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="9269e-102">FTP Connection Manager</span></span>
  <span data-ttu-id="9269e-103">Mit einem FTP-Verbindungs-Manager kann ein Paket eine Verbindung mit einem FTP-Server (File Transfer Protocol) herstellen.</span><span class="sxs-lookup"><span data-stu-id="9269e-103">An FTP connection manager enables a package to connect to a File Transfer Protocol (FTP) server.</span></span> <span data-ttu-id="9269e-104">Der FTP-Task von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] verwendet diesen Verbindungs-Manager.</span><span class="sxs-lookup"><span data-stu-id="9269e-104">The FTP task that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes uses this connection manager.</span></span>  
  
 <span data-ttu-id="9269e-105">Wenn Sie einem Paket einen FTP-Verbindungs-Manager hinzufügen, erstellt [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] einen Verbindungs-Manager, der zur Laufzeit als FTP-Verbindung aufgelöst werden kann, die Eigenschaften des Verbindungs-Managers festlegt und der `Connections`-Auflistung im Paket den Verbindungs-Manager hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="9269e-105">When you add an FTP connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that can be resolved as an FTP connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span>  
  
 <span data-ttu-id="9269e-106">Die `ConnectionManagerType`-Eigenschaft des Verbindungs-Managers ist auf `FTP` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9269e-106">The `ConnectionManagerType` property of the connection manager is set to `FTP`.</span></span>  
  
 <span data-ttu-id="9269e-107">Es gibt folgende Möglichkeiten, um den FTP-Verbindungs-Manager zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="9269e-107">You can configure the FTP connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="9269e-108">Geben Sie einen Servernamen und einen Serverport an.</span><span class="sxs-lookup"><span data-stu-id="9269e-108">Specify a server name and server port.</span></span>  
  
-   <span data-ttu-id="9269e-109">Geben Sie den anonymen Zugriff an, oder stellen Sie einen Benutzernamen und ein Kennwort für die Standardauthentifizierung bereit.</span><span class="sxs-lookup"><span data-stu-id="9269e-109">Specify anonymous access, or provide a user name and a password for basic authentication.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="9269e-110">Der FTP-Verbindungs-Manager unterstützt nur die anonyme Authentifizierung und die Standardauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="9269e-110">The FTP connection manager supports only anonymous authentication and basic authentication.</span></span> <span data-ttu-id="9269e-111">Er unterstützt keine Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="9269e-111">It does not support Windows Authentication.</span></span>  
  
-   <span data-ttu-id="9269e-112">Legen Sie das Timeout, die Wiederholungsversuche und die jeweils zu kopierende Datenmenge fest.</span><span class="sxs-lookup"><span data-stu-id="9269e-112">Set the time-out, number of retries, and the amount of data to copy at a time.</span></span>  
  
-   <span data-ttu-id="9269e-113">Geben Sie an, ob der FTP-Verbindungs-Manager den passiven oder aktiven Modus verwendet.</span><span class="sxs-lookup"><span data-stu-id="9269e-113">Indicate whether the FTP connection manager uses passive or active mode.</span></span>  
  
 <span data-ttu-id="9269e-114">Sie müssen u. U. die folgenden Standardwerte des Verbindungs-Managers ändern, je nach Konfiguration der FTP-Site, zu der der FTP-Verbindungs-Manager eine Verbindung herstellt:</span><span class="sxs-lookup"><span data-stu-id="9269e-114">Depending on the configuration of the FTP site to which the FTP connection manager connects, you may need to change the following default values of the connection manager:</span></span>  
  
-   <span data-ttu-id="9269e-115">Der Serverport wird auf 21 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9269e-115">The server port is set to 21.</span></span> <span data-ttu-id="9269e-116">Sie sollten den Port angeben, an dem von der FTP-Site gelauscht wird.</span><span class="sxs-lookup"><span data-stu-id="9269e-116">You should specify the port that the FTP site listens to.</span></span>  
  
-   <span data-ttu-id="9269e-117">Der Benutzername ist auf "anonym" festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9269e-117">The user name is set to "anonymous".</span></span> <span data-ttu-id="9269e-118">Sie sollten die für die FTP-Site erforderlichen Anmeldeinformationen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="9269e-118">You should provide the credentials that the FTP site requires.</span></span>  
  
## <a name="activepassive-modes"></a><span data-ttu-id="9269e-119">Aktiver/passiver Modus</span><span class="sxs-lookup"><span data-stu-id="9269e-119">Active/Passive Modes</span></span>  
 <span data-ttu-id="9269e-120">Ein FTP-Verbindungs-Manager kann Dateien mithilfe des aktiven oder passiven Modus senden und empfangen.</span><span class="sxs-lookup"><span data-stu-id="9269e-120">An FTP connection manager can send and receive files using either active mode or passive mode.</span></span> <span data-ttu-id="9269e-121">Im aktiven Modus wird die Datenverbindung vom Server initiiert, im passiven Modus wird sie vom Client initiiert.</span><span class="sxs-lookup"><span data-stu-id="9269e-121">In active mode, the server initiates the data connection, and in passive mode, the client initiates the data connection.</span></span>  
  
## <a name="configuration-of-the-ftp-connection-manager"></a><span data-ttu-id="9269e-122">Konfiguration des FTP-Verbindungs-Managers</span><span class="sxs-lookup"><span data-stu-id="9269e-122">Configuration of the FTP Connection Manager</span></span>  
 <span data-ttu-id="9269e-123">Sie können Eigenschaften mit dem [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="9269e-123">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="9269e-124">Weitere Informationen zu den Eigenschaften, die Sie im [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer festlegen können, finden Sie unter [FTP-Verbindungs-Manager-Editor](../ftp-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="9269e-124">For information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [FTP Connection Manager Editor](../ftp-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="9269e-125">Weitere Informationen zum programmgesteuerten Konfigurieren eines Verbindungs-Managers finden Sie unter <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> und [Programmgesteuertes Hinzufügen von Verbindungen](../building-packages-programmatically/adding-connections-programmatically.md)festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9269e-125">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9269e-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9269e-126">See Also</span></span>  
 <span data-ttu-id="9269e-127">[FTP-Task](../control-flow/ftp-task.md) </span><span class="sxs-lookup"><span data-stu-id="9269e-127">[FTP Task](../control-flow/ftp-task.md) </span></span>  
 [<span data-ttu-id="9269e-128">Integration Services-Verbindungen &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="9269e-128">Integration Services &#40;SSIS&#41; Connections</span></span>](integration-services-ssis-connections.md)  
  
  
