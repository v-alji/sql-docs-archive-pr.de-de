---
title: MSMQ-Verbindungs-Manager-Editor | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.msmqconnectionmanager.f1
helpviewer_keywords:
- MSMQ Connection Manager Editor
ms.assetid: ef842cb4-82da-4550-85fe-9bedbc1e77c7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 41d4231ce121d596c8d818485eccf5ddf6127470
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609310"
---
# <a name="msmq-connection-manager-editor"></a><span data-ttu-id="babcf-102">MSMQ-Verbindungs-Manager-Editor</span><span class="sxs-lookup"><span data-stu-id="babcf-102">MSMQ Connection Manager Editor</span></span>
  <span data-ttu-id="babcf-103">Mithilfe des Dialogfelds **MSMQ-Verbindungs-Manager** geben Sie den Pfad zu einer Message Queuing-Meldungswarteschlange (auch bekannt als MSMQ) an.</span><span class="sxs-lookup"><span data-stu-id="babcf-103">Use the **MSMQ Connection Manager** dialog box to specify the path to a Message Queuing (also known as MSMQ) message queue.</span></span>  
  
 <span data-ttu-id="babcf-104">Weitere Informationen zum MSMQ-Verbindungs-Manager finden Sie unter [MSMQ Connection Manager](connection-manager/msmq-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="babcf-104">To learn more about the MSMQ connection manager, see [MSMQ Connection Manager](connection-manager/msmq-connection-manager.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="babcf-105">Der MSMQ-Verbindungs-Manager unterstützt lokale öffentliche und private Warteschlangen sowie öffentliche Remotewarteschlangen.</span><span class="sxs-lookup"><span data-stu-id="babcf-105">The MSMQ connection manager supports local public and private queues and remote public queues.</span></span> <span data-ttu-id="babcf-106">Er unterstützt keine privaten Remotewarteschlangen.</span><span class="sxs-lookup"><span data-stu-id="babcf-106">It does not support remote private queues.</span></span> <span data-ttu-id="babcf-107">Eine Problemumgehung mithilfe des Skripttasks finden Sie unter [Senden mit dem Skripttask an eine private Remotemeldungswarteschlange](control-flow/script-task.md).</span><span class="sxs-lookup"><span data-stu-id="babcf-107">For a workaround that uses the Script Task, see [Sending to a Remote Private Message Queue with the Script Task](control-flow/script-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="babcf-108">Tastatur</span><span class="sxs-lookup"><span data-stu-id="babcf-108">Options</span></span>  
 <span data-ttu-id="babcf-109">**Name**</span><span class="sxs-lookup"><span data-stu-id="babcf-109">**Name**</span></span>  
 <span data-ttu-id="babcf-110">Geben Sie einen eindeutigen Namen für den Verbindungs-Manager im Workflow an.</span><span class="sxs-lookup"><span data-stu-id="babcf-110">Provide a unique name for the MSMQ connection manager in the workflow.</span></span> <span data-ttu-id="babcf-111">Der angegebene Name wird im [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="babcf-111">The name provided will be displayed within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="babcf-112">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="babcf-112">**Description**</span></span>  
 <span data-ttu-id="babcf-113">Beschreiben Sie den Verbindungs-Manager.</span><span class="sxs-lookup"><span data-stu-id="babcf-113">Describe the connection manager.</span></span> <span data-ttu-id="babcf-114">Die bewährte Methode ist hierbei, den Verbindungs-Manager zweckbezogen zu beschreiben, sodass Pakete selbsterklärend und leichter zu verwalten sind.</span><span class="sxs-lookup"><span data-stu-id="babcf-114">As a best practice, describe the connection manager in terms of its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
 <span data-ttu-id="babcf-115">**Path**</span><span class="sxs-lookup"><span data-stu-id="babcf-115">**Path**</span></span>  
 <span data-ttu-id="babcf-116">Geben Sie den vollständigen Pfad der Meldungswarteschlange ein.</span><span class="sxs-lookup"><span data-stu-id="babcf-116">Type the complete path of the message queue.</span></span> <span data-ttu-id="babcf-117">Das Format des Pfades ist vom Typ der Warteschlange abhängig.</span><span class="sxs-lookup"><span data-stu-id="babcf-117">The format of the path depends on the type of queue.</span></span>  
  
|<span data-ttu-id="babcf-118">Warteschlangentyp</span><span class="sxs-lookup"><span data-stu-id="babcf-118">Queue type</span></span>|<span data-ttu-id="babcf-119">Beispielpfad</span><span class="sxs-lookup"><span data-stu-id="babcf-119">Sample path</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="babcf-120">Öffentlich</span><span class="sxs-lookup"><span data-stu-id="babcf-120">Public</span></span>|<span data-ttu-id="babcf-121">\<computer name>\\<Warteschlangenname\></span><span class="sxs-lookup"><span data-stu-id="babcf-121">\<computer name>\\<queue name\></span></span>|  
|<span data-ttu-id="babcf-122">Privat</span><span class="sxs-lookup"><span data-stu-id="babcf-122">Private</span></span>|<span data-ttu-id="babcf-123">\<computer name>\Private$\\<Warteschlangenname\></span><span class="sxs-lookup"><span data-stu-id="babcf-123">\<computer name>\Private$\\<queue name\></span></span>|  
  
 <span data-ttu-id="babcf-124">Sie können "." verwenden, um den lokalen Computer darzustellen.</span><span class="sxs-lookup"><span data-stu-id="babcf-124">You can use "." to represent the local computer.</span></span>  
  
 <span data-ttu-id="babcf-125">**Test**</span><span class="sxs-lookup"><span data-stu-id="babcf-125">**Test**</span></span>  
 <span data-ttu-id="babcf-126">Nachdem die Konfiguration des MSMQ-Verbindungs-Managers abgeschlossen ist, überprüfen Sie die Gültigkeit der Verbindung, indem Sie auf **Testen**klicken.</span><span class="sxs-lookup"><span data-stu-id="babcf-126">After configuring the MSMQ connection manager, confirm that the connection is viable by clicking **Test**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="babcf-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="babcf-127">See Also</span></span>  
 [<span data-ttu-id="babcf-128">Fehler- und Meldungsreferenz von Integration Services</span><span class="sxs-lookup"><span data-stu-id="babcf-128">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
