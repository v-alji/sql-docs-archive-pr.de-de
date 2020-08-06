---
title: Dateien in Verwendung überprüfen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: ccd65867-d4c0-43b2-8361-7fd41c6f79ac
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 51505b0dece146b7f6fcdf982e6f88a5715357e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617512"
---
# <a name="check-files-in-use"></a><span data-ttu-id="4afdc-102">Verwendete Dateien überprüfen</span><span class="sxs-lookup"><span data-stu-id="4afdc-102">Check Files In Use</span></span>
  <span data-ttu-id="4afdc-103">Verwenden Sie zum Vermeiden eines Neustarts von Windows nach dem Installieren von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Updates die Seite Verwendete Dateien überprüfen zum Identifizieren von Vorgängen, die vom Setupprogramm für das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Update benötigte Dateien blockieren.</span><span class="sxs-lookup"><span data-stu-id="4afdc-103">To avoid restarting Windows after you install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] updates, use the Check Files in Use page to identify processes that are locking files required by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] update Setup program.</span></span>  
  
 <span data-ttu-id="4afdc-104">Beenden Sie alle Anwendungen und Dienste, die Verbindungen mit den aktualisierten Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] herstellen.</span><span class="sxs-lookup"><span data-stu-id="4afdc-104">Stop all applications and services that make connections to the instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are being updated.</span></span> <span data-ttu-id="4afdc-105">Dies schließt das Beenden von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] und [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]ein.</span><span class="sxs-lookup"><span data-stu-id="4afdc-105">This includes stopping [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="4afdc-106">Wenn vom Setup erkannt wird, dass Dateien während der Installation blockiert sind, müssen Sie den Computer möglicherweise nach dem Fertigstellen der Installation erneut starten.</span><span class="sxs-lookup"><span data-stu-id="4afdc-106">If Setup determines that files are locked during installation, you might have to restart your computer after installation is completed.</span></span> <span data-ttu-id="4afdc-107">Gegebenenfalls werden Sie aufgefordert, den Computer neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="4afdc-107">If necessary, Setup prompts you to restart your computer.</span></span> <span data-ttu-id="4afdc-108">Wenn das Setupprogramm einen Dienst während der Installation beenden muss, wird der Dienst nach Abschluss der Installation neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="4afdc-108">If the Setup program must stop a service during installation, it will restart the service after installation is completed.</span></span>  
  
 <span data-ttu-id="4afdc-109">Damit der Computer nach der Installation nicht neu gestartet werden muss, zeigt das Setup eine Liste der Prozesse an, die Dateien sperren.</span><span class="sxs-lookup"><span data-stu-id="4afdc-109">To eliminate the requirement to restart your computer after installation, Setup displays a list of processes that are locking files.</span></span> <span data-ttu-id="4afdc-110">Beenden Sie die in der Liste aufgeführten Prozesse und Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="4afdc-110">Stop or end the processes and applications in the list.</span></span> <span data-ttu-id="4afdc-111">Klicken Sie dann auf **Überprüfung aktualisieren** , um die Überprüfung erneut auszuführen.</span><span class="sxs-lookup"><span data-stu-id="4afdc-111">Then click **Refresh check** to rerun the check.</span></span> <span data-ttu-id="4afdc-112">Klicken Sie zum Beenden einer gerade ausgeführten Überprüfung auf **Überprüfung beenden** .</span><span class="sxs-lookup"><span data-stu-id="4afdc-112">Click **Stop check** to end a check that is running.</span></span> <span data-ttu-id="4afdc-113">Wenn keine blockierten Dateien gefunden wurden, ist die Tabelle leer.</span><span class="sxs-lookup"><span data-stu-id="4afdc-113">If locked files are not found, the table is empty.</span></span> <span data-ttu-id="4afdc-114">Klicken Sie auf **Weiter** , um den Vorgang fortzusetzen, wenn alle blockierten Vorgänge beendet wurden.</span><span class="sxs-lookup"><span data-stu-id="4afdc-114">When all locked processes have been closed or stopped, click **Next** to continue.</span></span>  
  
 <span data-ttu-id="4afdc-115">Die Informationen werden vom Setup in den Protokolldateien protokolliert.</span><span class="sxs-lookup"><span data-stu-id="4afdc-115">Setup logs the information in the log files.</span></span> <span data-ttu-id="4afdc-116">Weitere Informationen zum Anzeigen der Protokolldateien finden Sie unter [Lesen und Anzeigen der Setupprotokolldateien von SQL Server](../../database-engine/install-windows/view-and-read-sql-server-setup-log-files.md) und [Vorgehensweise: Lesen einer Setupprotokolldatei von SQL Server](https://go.microsoft.com/fwlink/?LinkID=134490).</span><span class="sxs-lookup"><span data-stu-id="4afdc-116">For more information about how to view the log files, see [View and Read SQL Server Setup Log Files](../../database-engine/install-windows/view-and-read-sql-server-setup-log-files.md) and [How to: Read a SQL Server Setup Log File](https://go.microsoft.com/fwlink/?LinkID=134490).</span></span>  
  
 <span data-ttu-id="4afdc-117">Die Protokolldatei enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="4afdc-117">The following information is included in the log file:</span></span>  
  
-   <span data-ttu-id="4afdc-118">Name des Prozesses</span><span class="sxs-lookup"><span data-stu-id="4afdc-118">Name of the process</span></span>  
  
-   <span data-ttu-id="4afdc-119">Name der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Funktion</span><span class="sxs-lookup"><span data-stu-id="4afdc-119">Name of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] feature</span></span>  
  
-   <span data-ttu-id="4afdc-120">Prozesstyp</span><span class="sxs-lookup"><span data-stu-id="4afdc-120">Process type</span></span>  
  
-   <span data-ttu-id="4afdc-121">Konto, unter dem der Prozess ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="4afdc-121">Account under which the process is running</span></span>  
  
-   <span data-ttu-id="4afdc-122">Prozess-ID</span><span class="sxs-lookup"><span data-stu-id="4afdc-122">Process ID</span></span>  
  
-   <span data-ttu-id="4afdc-123">Name der gesperrten Datei</span><span class="sxs-lookup"><span data-stu-id="4afdc-123">Name of the file that is locked</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="4afdc-124">Liste der Benutzeroberflächenelemente</span><span class="sxs-lookup"><span data-stu-id="4afdc-124">UI element list</span></span>  
  
|<span data-ttu-id="4afdc-125">Name</span><span class="sxs-lookup"><span data-stu-id="4afdc-125">Name</span></span>|<span data-ttu-id="4afdc-126">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4afdc-126">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="4afdc-127">Prozess</span><span class="sxs-lookup"><span data-stu-id="4afdc-127">Process</span></span>|<span data-ttu-id="4afdc-128">Zeigt den vollständigen Namen des Prozesses an, von dem die zu aktualisierenden Dateien verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4afdc-128">Displays the full name of the process that is using the files to be updated.</span></span>|  
|<span data-ttu-id="4afdc-129">type</span><span class="sxs-lookup"><span data-stu-id="4afdc-129">Type</span></span>|<span data-ttu-id="4afdc-130">Zeigt den Typ des Prozesses an.</span><span class="sxs-lookup"><span data-stu-id="4afdc-130">Displays the type of process.</span></span>|  
|<span data-ttu-id="4afdc-131">Konto</span><span class="sxs-lookup"><span data-stu-id="4afdc-131">Account</span></span>|<span data-ttu-id="4afdc-132">Zeigt das Konto an, unter dem der Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4afdc-132">Displays the account under which the process is running.</span></span>|  
|<span data-ttu-id="4afdc-133">Prozess-ID</span><span class="sxs-lookup"><span data-stu-id="4afdc-133">Process ID</span></span>|<span data-ttu-id="4afdc-134">Zeigt die Prozess-ID an.</span><span class="sxs-lookup"><span data-stu-id="4afdc-134">Displays the process ID.</span></span>|  
  
  
