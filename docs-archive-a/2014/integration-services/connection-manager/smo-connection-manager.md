---
title: SMO-Verbindungs-Manager | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- connections [Integration Services], SMO
- SMO connection manager
- connection managers [Integration Services], SMO
ms.assetid: d273f1fb-a6a8-4f2f-a5ff-55c2e3de4723
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 988eef214608399bc3ec483d9976c2f5d52acb2a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724870"
---
# <a name="smo-connection-manager"></a><span data-ttu-id="2fb41-102">SMO-Verbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="2fb41-102">SMO Connection Manager</span></span>
  <span data-ttu-id="2fb41-103">Mit einem SMO-Verbindungs-Manager kann ein Paket eine Verbindung mit einem SMO-Server (SQL Management Object) herstellen.</span><span class="sxs-lookup"><span data-stu-id="2fb41-103">An SMO connection manager enables a package to connect to a SQL Management Object (SMO) server.</span></span> <span data-ttu-id="2fb41-104">Die Übertragungstasks von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] verwenden einen SMO-Verbindungs-Manager.</span><span class="sxs-lookup"><span data-stu-id="2fb41-104">The transfer tasks that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes use an SMO connection manager.</span></span> <span data-ttu-id="2fb41-105">Beispielsweise verwendet der Task Anmeldungen übertragen, der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldungen überträgt, einen SMO-Verbindungs-Manager.</span><span class="sxs-lookup"><span data-stu-id="2fb41-105">For example, the Transfer Logins task that transfers [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logins uses an SMO connection manager.</span></span>  
  
 <span data-ttu-id="2fb41-106">Wenn Sie einem Paket einen SMO-Verbindungs-Manager hinzufügen, erstellt [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] einen Verbindungs-Manager, der zur Laufzeit in eine SMO-Verbindung aufgelöst wird, die Eigenschaften des Verbindungs-Managers festlegt und der `Connections`-Auflistung im Paket den Verbindungs-Manager hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="2fb41-106">When you add an SMO connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to an SMO connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span> <span data-ttu-id="2fb41-107">Die `ConnectionManagerType`-Eigenschaft des Verbindungs-Managers ist auf `SMOServer` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2fb41-107">The `ConnectionManagerType` property of the connection manager is set to `SMOServer`.</span></span>  
  
 <span data-ttu-id="2fb41-108">Es gibt folgende Möglichkeiten, um einen SMO-Verbindungs-Manager zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="2fb41-108">You can configure an SMO connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="2fb41-109">Geben Sie den Namen eines Servers an, auf dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installiert ist.</span><span class="sxs-lookup"><span data-stu-id="2fb41-109">Specify the name of a server on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed.</span></span>  
  
-   <span data-ttu-id="2fb41-110">Wählen Sie den Authentifizierungsmodus zum Herstellen einer Verbindung mit dem Server aus.</span><span class="sxs-lookup"><span data-stu-id="2fb41-110">Select the authentication mode for connecting to the server.</span></span>  
  
## <a name="configuration-of-the-smo-connection-manager"></a><span data-ttu-id="2fb41-111">Konfiguration des SMO-Verbindungs-Managers</span><span class="sxs-lookup"><span data-stu-id="2fb41-111">Configuration of the SMO Connection Manager</span></span>  
 <span data-ttu-id="2fb41-112">Sie können Eigenschaften mit dem [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="2fb41-112">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="2fb41-113">Weitere Informationen zu den Eigenschaften, die Sie im [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer festlegen können, finden Sie unter [SMO-Verbindungs-Manager-Editor](../smo-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="2fb41-113">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [SMO Connection Manager Editor](../smo-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="2fb41-114">Weitere Informationen zum programmgesteuerten Konfigurieren eines Verbindungs-Managers finden Sie unter <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> und [Programmgesteuertes Hinzufügen von Verbindungen](../building-packages-programmatically/adding-connections-programmatically.md)festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2fb41-114">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fb41-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2fb41-115">See Also</span></span>  
 [<span data-ttu-id="2fb41-116">Integration Services-Verbindungen &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="2fb41-116">Integration Services &#40;SSIS&#41; Connections</span></span>](integration-services-ssis-connections.md)  
  
  
