---
title: Servereigenschaften (Seite „Prozessoren“) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.serverproperties.processor.f1
ms.assetid: cc1581a2-492b-41f0-bda5-17909b65c4f7
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c4d241f01de7ac961832e77bb09483cff275deb6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618886"
---
# <a name="server-properties-processors-page"></a><span data-ttu-id="24524-102">Servereigenschaften (Seite Prozessoren)</span><span class="sxs-lookup"><span data-stu-id="24524-102">Server Properties (Processors Page)</span></span>
  <span data-ttu-id="24524-103">Auf dieser Seite können Sie die Prozessoroptionen anzeigen und ändern.</span><span class="sxs-lookup"><span data-stu-id="24524-103">Use this page to view or modify your processor options.</span></span> <span data-ttu-id="24524-104">Prozessoraffinitätsoptionen sind nur aktiviert, wenn mehr als ein Prozessor installiert ist.</span><span class="sxs-lookup"><span data-stu-id="24524-104">Processor affinity settings are only enabled when more than one processor is installed.</span></span>  
  
## <a name="options"></a><span data-ttu-id="24524-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="24524-105">Options</span></span>  
 <span data-ttu-id="24524-106">**Prozessoraffinität**</span><span class="sxs-lookup"><span data-stu-id="24524-106">**Processor Affinity**</span></span>  
 <span data-ttu-id="24524-107">Weist Prozessoren bestimmte Threads zu, um ein Neuladen des Prozessors zu verhindern und die Threadmigration zwischen Prozessoren zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="24524-107">Assigns processors to specific threads to eliminating processor reloads and reduce thread migration across processors.</span></span> <span data-ttu-id="24524-108">Weitere Informationen finden Sie unter [Affinitätsmaske (Serverkonfigurationsoption)](affinity-mask-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="24524-108">For more information, see [affinity mask Server Configuration Option](affinity-mask-server-configuration-option.md).</span></span>  
  
 <span data-ttu-id="24524-109">**E/A-Affinität**</span><span class="sxs-lookup"><span data-stu-id="24524-109">**I/O Affinity**</span></span>  
 <span data-ttu-id="24524-110">Verbindet die Datenträger-E/A von [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mit einer angegebenen Teilmenge von CPUs.</span><span class="sxs-lookup"><span data-stu-id="24524-110">Binds [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] disk I/Os to a specified subset of CPUs.</span></span> <span data-ttu-id="24524-111">Weitere Informationen finden Sie unter [Affinity I/O Mask (Serverkonfigurationsoption)](affinity-input-output-mask-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="24524-111">For more information, see [affinity Input-Output mask Server Configuration Option](affinity-input-output-mask-server-configuration-option.md).</span></span>  
  
 <span data-ttu-id="24524-112">**Prozessor-Affinitätsmaske für alle Prozessoren automatisch festlegen**</span><span class="sxs-lookup"><span data-stu-id="24524-112">**Automatically set processor affinity mask for all processors**</span></span>  
 <span data-ttu-id="24524-113">Ermöglicht es [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , die Prozessoraffinität festzulegen.</span><span class="sxs-lookup"><span data-stu-id="24524-113">Allows [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to set the processor affinity.</span></span>  
  
 <span data-ttu-id="24524-114">**E/A-Affinitätsmaske für alle Prozessoren automatisch festlegen**</span><span class="sxs-lookup"><span data-stu-id="24524-114">**Automatically set I/O affinity mask for all processors**</span></span>  
 <span data-ttu-id="24524-115">Ermöglicht es [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , die E/A-Affinität festzulegen.</span><span class="sxs-lookup"><span data-stu-id="24524-115">Allows [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to set the I/O affinity.</span></span>  
  
 <span data-ttu-id="24524-116">**Maximale Arbeitsthreadanzahl**</span><span class="sxs-lookup"><span data-stu-id="24524-116">**Maximum worker threads**</span></span>  
 <span data-ttu-id="24524-117">0 ermöglicht es [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , die Anzahl der Arbeitsthreads dynamisch festzulegen.</span><span class="sxs-lookup"><span data-stu-id="24524-117">0 allows [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to dynamically set the number of worker threads.</span></span> <span data-ttu-id="24524-118">Diese Einstellung ist für die meisten Systeme am besten geeignet.</span><span class="sxs-lookup"><span data-stu-id="24524-118">This setting is best for most systems.</span></span> <span data-ttu-id="24524-119">In Abhängigkeit von der Systemkonfiguration kann jedoch durch Festlegen dieser Option auf einen bestimmten Wert manchmal die Leistung verbessert werden.</span><span class="sxs-lookup"><span data-stu-id="24524-119">However, depending on your system configuration, setting this option to a specific value sometimes improves performance.</span></span> <span data-ttu-id="24524-120">Weitere Informationen finden Sie unter [konfigurieren Sie die max Worker Threads Server Configuration Option](configure-the-max-worker-threads-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="24524-120">For more information, see [Configure the max worker threads Server Configuration Option](configure-the-max-worker-threads-server-configuration-option.md).</span></span>  
  
 <span data-ttu-id="24524-121">**SQL Server-Priorität höher stufen**</span><span class="sxs-lookup"><span data-stu-id="24524-121">**Boost SQL Server priority**</span></span>  
 <span data-ttu-id="24524-122">Gibt an, ob [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] unter [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows mit höherer Planungspriorität als andere Prozesse auf dem gleichen Computer ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="24524-122">Specifies whether [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should run at a higher [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows scheduling priority than other processes on the same computer.</span></span> <span data-ttu-id="24524-123">Weitere Informationen finden Sie unter [Configure the priority boost Server Configuration Option](configure-the-priority-boost-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="24524-123">For more information, see [Configure the priority boost Server Configuration Option](configure-the-priority-boost-server-configuration-option.md).</span></span>  
  
 <span data-ttu-id="24524-124">**Windows-Fibers verwenden ('Lightweightpooling')**</span><span class="sxs-lookup"><span data-stu-id="24524-124">**Use Windows fibers (lightweight pooling)**</span></span>  
 <span data-ttu-id="24524-125">Verwendet Windows-Fibers für den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Dienst statt Threads.</span><span class="sxs-lookup"><span data-stu-id="24524-125">Use Windows fibers instead of threads for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span> <span data-ttu-id="24524-126">Beachten Sie, dass diese Option nur unter Windows 2003 Server Edition verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="24524-126">Note that this is only available in Windows 2003 Server Edition.</span></span> <span data-ttu-id="24524-127">Weitere Informationen finden Sie unter [Lightweightpooling (Serverkonfigurationsoption)](lightweight-pooling-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="24524-127">For more information, see [lightweight pooling Server Configuration Option](lightweight-pooling-server-configuration-option.md).</span></span>  
  
 <span data-ttu-id="24524-128">**Konfigurierte Werte**</span><span class="sxs-lookup"><span data-stu-id="24524-128">**Configured Values**</span></span>  
 <span data-ttu-id="24524-129">Zeigt für die Optionen in diesem Bereich konfigurierte Werte an.</span><span class="sxs-lookup"><span data-stu-id="24524-129">Displays the configured values for the options on this pane.</span></span> <span data-ttu-id="24524-130">Wenn Sie diese Werte ändern, klicken Sie anschließend auf **Ausgeführte Werte** , um zu sehen, ob die Änderungen wirksam sind.</span><span class="sxs-lookup"><span data-stu-id="24524-130">If you change these values, click **Running Values** to see whether the changes have taken effect.</span></span> <span data-ttu-id="24524-131">Sind sie nicht wirksam, muss die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] zuerst neu gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="24524-131">If they have not, the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be restarted first.</span></span>  
  
 <span data-ttu-id="24524-132">**Ausgeführte Werte**</span><span class="sxs-lookup"><span data-stu-id="24524-132">**Running Values**</span></span>  
 <span data-ttu-id="24524-133">Zeigt die gegenwärtig ausgeführten Werte für die Optionen in diesem Bereich an.</span><span class="sxs-lookup"><span data-stu-id="24524-133">View the currently running values for the options on this pane.</span></span> <span data-ttu-id="24524-134">Diese Werte sind schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="24524-134">These values are read-only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24524-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="24524-135">See Also</span></span>  
 [<span data-ttu-id="24524-136">Serverkonfigurationsoptionen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="24524-136">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)  
  
  
