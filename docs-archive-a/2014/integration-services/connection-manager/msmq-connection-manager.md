---
title: MSMQ-Verbindungs-Manager | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- connections [Integration Services], message queues
- connection managers [Integration Services], MSMQ
- MSMQ connection manager
- message queue connections [Integration Services]
ms.assetid: a86900e2-450e-479f-b207-e1b02361d395
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0c51866eeef281f6587bf281461e4faa2278308d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621137"
---
# <a name="msmq-connection-manager"></a><span data-ttu-id="1b0e7-102">MSMQ-Verbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="1b0e7-102">MSMQ Connection Manager</span></span>
  <span data-ttu-id="1b0e7-103">Mit einem MSMQ-Verbindungs-Manager kann ein Paket eine Verbindung mit einer Nachrichtenwarteschlange herstellen, die Message Queuing (MSMQ) verwendet.</span><span class="sxs-lookup"><span data-stu-id="1b0e7-103">An MSMQ connection manager enables a package to connect to a message queue that uses Message Queuing (also known as MSMQ).</span></span> <span data-ttu-id="1b0e7-104">DIe Nachrichtenwarteschlangenaufgabe, die [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] enthält, verwendet einen MSMQ-Verbindungs-Manager.</span><span class="sxs-lookup"><span data-stu-id="1b0e7-104">The Message Queue task that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes uses an MSMQ connection manager.</span></span>  
  
 <span data-ttu-id="1b0e7-105">Wenn Sie einem Paket einen MSMQ-Verbindungs-Manager hinzufügen, erstellt [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] einen Verbindungs-Manager, der zur Laufzeit in eine MSMQ-Verbindung aufgelöst wird, die Eigenschaften des Verbindungs-Managers festlegt und der `Connections`-Auflistung im Paket den Verbindungs-Manager hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="1b0e7-105">When you add an MSMQ connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to an MSMQ connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span> <span data-ttu-id="1b0e7-106">Die `ConnectionManagerType`-Eigenschaft des Verbindungs-Managers ist auf `MSMQ` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1b0e7-106">The `ConnectionManagerType` property of the connection manager is set to `MSMQ`.</span></span>  
  
 <span data-ttu-id="1b0e7-107">Es gibt folgende Möglichkeiten, um einen MSMQ-Verbindungs-Manager zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="1b0e7-107">You can configure an MSMQ connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="1b0e7-108">Geben Sie eine Verbindungszeichenfolge an.</span><span class="sxs-lookup"><span data-stu-id="1b0e7-108">Provide a connection string.</span></span>  
  
-   <span data-ttu-id="1b0e7-109">Stellen Sie den Pfad der Nachrichtenwarteschlange bereit, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="1b0e7-109">Provide the path of the message queue to connect to.</span></span>  
  
 <span data-ttu-id="1b0e7-110">Das Format des Pfads richtet sich nach dem Typ der Warteschlange, wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="1b0e7-110">The format of the path depends on the type of queue, as shown in the following table.</span></span>  
  
|<span data-ttu-id="1b0e7-111">Warteschlangentyp</span><span class="sxs-lookup"><span data-stu-id="1b0e7-111">Queue type</span></span>|<span data-ttu-id="1b0e7-112">Beispielpfad</span><span class="sxs-lookup"><span data-stu-id="1b0e7-112">Sample path</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="1b0e7-113">Öffentlich</span><span class="sxs-lookup"><span data-stu-id="1b0e7-113">Public</span></span>|<span data-ttu-id="1b0e7-114">\<computer name>\\<Warteschlangenname\></span><span class="sxs-lookup"><span data-stu-id="1b0e7-114">\<computer name>\\<queue name\></span></span>|  
|<span data-ttu-id="1b0e7-115">Privat</span><span class="sxs-lookup"><span data-stu-id="1b0e7-115">Private</span></span>|<span data-ttu-id="1b0e7-116">\<computer name>\Private$\\<Warteschlangenname\></span><span class="sxs-lookup"><span data-stu-id="1b0e7-116">\<computer name>\Private$\\<queue name\></span></span>|  
  
 <span data-ttu-id="1b0e7-117">Sie können einen Punkt (.) verwenden, um den lokalen Computer darzustellen.</span><span class="sxs-lookup"><span data-stu-id="1b0e7-117">You can use a period (.) to represent the local computer.</span></span>  
  
## <a name="configuration-of-the-msmq-connection-manager"></a><span data-ttu-id="1b0e7-118">Konfiguration des MSMQ-Verbindungs-Managers</span><span class="sxs-lookup"><span data-stu-id="1b0e7-118">Configuration of the MSMQ Connection Manager</span></span>  
 <span data-ttu-id="1b0e7-119">Sie können Eigenschaften mit dem [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="1b0e7-119">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="1b0e7-120">Weitere Informationen zu den Eigenschaften, die Sie im [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer festlegen können, finden Sie unter [MSMQ-Verbindungs-Manager-Editor](../msmq-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="1b0e7-120">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [MSMQ Connection Manager Editor](../msmq-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="1b0e7-121">Weitere Informationen zum programmgesteuerten Konfigurieren eines Verbindungs-Managers finden Sie unter <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> und [Programmgesteuertes Hinzufügen von Verbindungen](../building-packages-programmatically/adding-connections-programmatically.md)festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1b0e7-121">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b0e7-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1b0e7-122">See Also</span></span>  
 <span data-ttu-id="1b0e7-123">[Nachrichtenwarteschlange (Task)](../control-flow/message-queue-task.md) </span><span class="sxs-lookup"><span data-stu-id="1b0e7-123">[Message Queue Task](../control-flow/message-queue-task.md) </span></span>  
 [<span data-ttu-id="1b0e7-124">Integration Services-Verbindungen &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="1b0e7-124">Integration Services &#40;SSIS&#41; Connections</span></span>](integration-services-ssis-connections.md)  
  
  
