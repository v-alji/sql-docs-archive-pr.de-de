---
title: WMI-Verbindungs-Manager | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- connections [Integration Services], WMI
- connection managers [Integration Services], WMI
- WMI connection manager [Integration Services]
ms.assetid: fbfa4ba7-3d0d-4d6b-94ad-50741a88d03d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f15aefb0ed112f1d5b7bb05421750b6689a11339
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618862"
---
# <a name="wmi-connection-manager"></a><span data-ttu-id="2685c-102">WMI-Verbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="2685c-102">WMI Connection Manager</span></span>
  <span data-ttu-id="2685c-103">Mit einem WMI-Verbindungs-Manager kann ein Paket mithilfe der Windows-Verwaltungsinstrumentation (Windows Management Instrumentation, WMI) Informationen in einer Unternehmensumgebung verwalten.</span><span class="sxs-lookup"><span data-stu-id="2685c-103">A WMI connection manager enables a package to use Windows Management Instrumentation (WMI) to manage information in an enterprise environment.</span></span> <span data-ttu-id="2685c-104">Der Task „Webdienst“ von [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] verwendet einen WMI-Verbindungs-Manager.</span><span class="sxs-lookup"><span data-stu-id="2685c-104">The Web Service task that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes uses a WMI connection manager.</span></span>  
  
 <span data-ttu-id="2685c-105">Wenn Sie einem Paket einen WMI-Verbindungs-Manager hinzufügen, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] erstellt einen Verbindungs-Manager, der zur Laufzeit in eine WMI-Verbindung aufgelöst wird, die Eigenschaften des Verbindungs-Managers festlegt und der-Auflistung im Paket den Verbindungs-Manager hinzufügt `Connections` .</span><span class="sxs-lookup"><span data-stu-id="2685c-105">When you add a WMI connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to a WMI connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span> <span data-ttu-id="2685c-106">Die `ConnectionManagerType`-Eigenschaft des Verbindungs-Managers ist auf `WMI` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2685c-106">The `ConnectionManagerType` property of the connection manager is set to `WMI`.</span></span>  
  
## <a name="configuration-of-the-wmi-connection-manager"></a><span data-ttu-id="2685c-107">Konfiguration des WMI-Verbindungs-Managers</span><span class="sxs-lookup"><span data-stu-id="2685c-107">Configuration of the WMI Connection Manager</span></span>  
 <span data-ttu-id="2685c-108">Es gibt folgende Möglichkeiten, um einen WMI-Verbindungs-Manager zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="2685c-108">You can configure a WMI connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="2685c-109">Geben Sie den Namen eines Servers an.</span><span class="sxs-lookup"><span data-stu-id="2685c-109">Specify the name of a server.</span></span>  
  
-   <span data-ttu-id="2685c-110">Geben Sie einen Namespace auf dem Server an.</span><span class="sxs-lookup"><span data-stu-id="2685c-110">Specify a namespace on the server.</span></span>  
  
-   <span data-ttu-id="2685c-111">Wählen Sie den Authentifizierungsmodus zum Herstellen einer Verbindung mit dem Server aus.</span><span class="sxs-lookup"><span data-stu-id="2685c-111">Select the authentication mode for connecting to the server.</span></span>  
  
 <span data-ttu-id="2685c-112">Sie können Eigenschaften mit dem [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="2685c-112">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="2685c-113">Weitere Informationen zu den Eigenschaften, die Sie im [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer festlegen können, finden Sie unter [WMI-Verbindungs-Manager-Editor](../wmi-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="2685c-113">For information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [WMI Connection Manager Editor](../wmi-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="2685c-114">Weitere Informationen zum programmgesteuerten Konfigurieren eines Verbindungs-Managers finden Sie unter <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> und [Programmgesteuertes Hinzufügen von Verbindungen](../building-packages-programmatically/adding-connections-programmatically.md)festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2685c-114">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2685c-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2685c-115">See Also</span></span>  
 <span data-ttu-id="2685c-116">[Webdienst (Task)](../control-flow/web-service-task.md) </span><span class="sxs-lookup"><span data-stu-id="2685c-116">[Web Service Task](../control-flow/web-service-task.md) </span></span>  
 [<span data-ttu-id="2685c-117">Integration Services-Verbindungen &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="2685c-117">Integration Services &#40;SSIS&#41; Connections</span></span>](integration-services-ssis-connections.md)  
  
  
