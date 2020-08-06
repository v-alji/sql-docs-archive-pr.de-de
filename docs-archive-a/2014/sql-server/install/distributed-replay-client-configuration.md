---
title: Distributed Replay Client Konfiguration | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: ccf03e32-6bd9-43c0-b9b6-9fe0d9163339
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 53124029483c25ed7894b279283e1de02c647350
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622405"
---
# <a name="distributed-replay-client-configuration"></a><span data-ttu-id="d6506-102">Distributed Replay Client-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="d6506-102">Distributed Replay Client Configuration</span></span>
  <span data-ttu-id="d6506-103">Verwenden Sie die Seite für die **Distributed Replay Client-Konfiguration** des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Installations-Assistenten, um die Benutzer anzugeben, denen Sie Administratorberechtigungen für den Distributed Replay Client-Dienst gewähren möchten.</span><span class="sxs-lookup"><span data-stu-id="d6506-103">Use the **Distributed Replay Client Configuration** page of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard to specify the users you want to grant administrative permissions to for the Distributed Replay client service.</span></span>  
  
 <span data-ttu-id="d6506-104">Benutzer, die über Administratorberechtigungen verfügen, besitzen unbeschränkten Zugriff auf den Distributed Replay Client-Dienst.</span><span class="sxs-lookup"><span data-stu-id="d6506-104">Users that have administrative permissions will have unlimited access to the Distributed Replay client service.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d6506-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="d6506-105">Options</span></span>  
 <span data-ttu-id="d6506-106">**Controllername**</span><span class="sxs-lookup"><span data-stu-id="d6506-106">**Controller Name**</span></span>  
 <span data-ttu-id="d6506-107">Dies ist ein optionaler Parameter, und der Standardwert ist \<*blank*> .</span><span class="sxs-lookup"><span data-stu-id="d6506-107">This is an optional parameter, and the default value is \<*blank*>.</span></span>  
  
 <span data-ttu-id="d6506-108">Geben Sie den Namen des Controllers ein, mit dem der Clientcomputer für den Distributed Replay Client-Dienst kommuniziert.</span><span class="sxs-lookup"><span data-stu-id="d6506-108">Enter the name of the controller that the client computer will communicate with for the Distributed Replay client service.</span></span> <span data-ttu-id="d6506-109">Beachten Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="d6506-109">Note the following:</span></span>  
  
-   <span data-ttu-id="d6506-110">Der Name muss ein vollqualifizierter Domänenname sein.</span><span class="sxs-lookup"><span data-stu-id="d6506-110">The name must be a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="d6506-111">Ein Host mit dem Namen "server1" kann in der Produkthierarchie von Microsoft z. B. den vollqualifizierten Domänennamen "server1.products.microsoft.com" haben.</span><span class="sxs-lookup"><span data-stu-id="d6506-111">For example, a host called server1 in the products hierarchy at Microsoft may have an FQDN of server1.products.microsoft.com.</span></span>  
  
-   <span data-ttu-id="d6506-112">Wenn Sie bereits einen Controller eingerichtet haben, geben Sie den Namen des Controllers beim Konfigurieren jedes Clients ein.</span><span class="sxs-lookup"><span data-stu-id="d6506-112">If you have already set up a controller, enter the name of the controller while configuring each client.</span></span>  
  
-   <span data-ttu-id="d6506-113">Wenn Sie noch keinen Controller eingerichtet haben, können Sie das Feld für den Controllernamen leer lassen.</span><span class="sxs-lookup"><span data-stu-id="d6506-113">If you have net yet set up a controller, you can leave the controller name blank.</span></span> <span data-ttu-id="d6506-114">Sie müssen den Controllernamen jedoch in der **Clientkonfigurationsdatei** manuell eingeben.</span><span class="sxs-lookup"><span data-stu-id="d6506-114">However, you must manually enter the controller name in the **client configuration** file.</span></span>  
  
 <span data-ttu-id="d6506-115">**Arbeitsverzeichnis**</span><span class="sxs-lookup"><span data-stu-id="d6506-115">**Working Directory**</span></span>  
 <span data-ttu-id="d6506-116">Geben Sie das Arbeitsverzeichnis für den Distributed Replay Client-Dienst an.</span><span class="sxs-lookup"><span data-stu-id="d6506-116">Specify the working directory for the Distributed Replay client service.</span></span>  
  
 <span data-ttu-id="d6506-117">Das Standardarbeitsverzeichnis lautet \<*drive letter*>:\Programme\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\DReplayClient\WorkingDir\\.</span><span class="sxs-lookup"><span data-stu-id="d6506-117">The default working directory is \<*drive letter*>:\Program Files\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\DReplayClient\WorkingDir\\.</span></span>  
  
 <span data-ttu-id="d6506-118">**Ergebnisverzeichnis**</span><span class="sxs-lookup"><span data-stu-id="d6506-118">**Result Directory**</span></span>  
 <span data-ttu-id="d6506-119">Geben Sie das Ergebnisverzeichnis für den Distributed Replay Client-Dienst an.</span><span class="sxs-lookup"><span data-stu-id="d6506-119">Specify the result directory for the Distributed Replay client service.</span></span>  
  
 <span data-ttu-id="d6506-120">Das Standardergebnisverzeichnis lautet \<*drive letter*>:\Programme\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\DReplayClient\ResultDir\\.</span><span class="sxs-lookup"><span data-stu-id="d6506-120">The default result directory is \<*drive letter*>:\Program Files\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\DReplayClient\ResultDir\\.</span></span>  
  
  
