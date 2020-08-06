---
title: Distributed Replay Anforderungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 6fffee7d-891f-4d9d-b2c3-dd19855a1c2c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 66be93534756360e722fcccaf405815e14ffa7ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617324"
---
# <a name="distributed-replay-requirements"></a><span data-ttu-id="d87cc-102">Distributed Replay Requirements</span><span class="sxs-lookup"><span data-stu-id="d87cc-102">Distributed Replay Requirements</span></span>
  <span data-ttu-id="d87cc-103">Bevor Sie die [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay-Funktion verwenden, sollten Sie die in diesem Thema beschriebenen Produktanforderungen berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="d87cc-103">Before using the [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay feature, consider the product requirements that are outlined in this topic.</span></span>  
  
## <a name="input-trace-requirements"></a><span data-ttu-id="d87cc-104">Anforderungen an die Eingabedatei für die Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="d87cc-104">Input Trace Requirements</span></span>  
 <span data-ttu-id="d87cc-105">Für die erfolgreiche Wiedergabe von Ablaufverfolgungsdaten müssen die Anforderungen an Version und Format erfüllt und die erforderlichen Ereignisse und Spalten enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="d87cc-105">To successfully replay trace data, it must meet the requirements for version and format, and contain the required events and columns.</span></span>  
  
### <a name="input-trace-versions"></a><span data-ttu-id="d87cc-106">Versionen der Eingabedatei für die Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="d87cc-106">Input Trace Versions</span></span>  
 <span data-ttu-id="d87cc-107">Distributed Replay unterstützt Eingabedaten für die Ablaufverfolgung, die in den folgenden [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Versionen erfasst wurden:</span><span class="sxs-lookup"><span data-stu-id="d87cc-107">Distributed Replay supports input trace data that is collected on the following versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]  
  
-   [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]  
  
-   [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]  
  
-   [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]  
  
-   [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]  
  
### <a name="input-trace-formats"></a><span data-ttu-id="d87cc-108">Formate für die Eingabedatei der Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="d87cc-108">Input Trace Formats</span></span>  
 <span data-ttu-id="d87cc-109">Die Eingabedaten der Ablaufverfolgung können in einen der folgenden Formate vorliegen:</span><span class="sxs-lookup"><span data-stu-id="d87cc-109">The input trace data can be in any of the following formats:</span></span>  
  
-   <span data-ttu-id="d87cc-110">Einzelne Ablaufverfolgungsdatei mit der Erweiterung `.trc` .</span><span class="sxs-lookup"><span data-stu-id="d87cc-110">A single trace file that has the `.trc` extension.</span></span>  
  
-   <span data-ttu-id="d87cc-111">Ein Satz von Rollover-Ablaufverfolgungsdateien, die der Dateirollover-Benennungskonvention folgen, z. B.: `<TraceFile>.trc`, `<TraceFile>_1.trc`, `<TraceFile>_2.trc`, `<TraceFile>_3.trc`, ... `<TraceFile>_n.trc`.</span><span class="sxs-lookup"><span data-stu-id="d87cc-111">A set of rollover trace files that follow the file rollover naming convention, for example: `<TraceFile>.trc`, `<TraceFile>_1.trc`, `<TraceFile>_2.trc`, `<TraceFile>_3.trc`, ... `<TraceFile>_n.trc`.</span></span>  
  
### <a name="input-trace-events-and-columns"></a><span data-ttu-id="d87cc-112">Ereignisse und Spalten in der Eingabedatei für die Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="d87cc-112">Input Trace Events and Columns</span></span>  
 <span data-ttu-id="d87cc-113">Die Eingabedaten der Ablaufverfolgung müssen bestimmte Ereignisse und Spalten enthalten, die von Distributed Replay wiedergegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d87cc-113">The input trace data must contain specific events and columns to be replayed by Distributed Replay.</span></span> <span data-ttu-id="d87cc-114">Die Vorlage **TSQL_Replay** in [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] enthält neben zusätzlichen Informationen alle erforderlichen Ereignisse und Spalten.</span><span class="sxs-lookup"><span data-stu-id="d87cc-114">The **TSQL_Replay** template in [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] contains all of the required events and columns, in addition to extra information.</span></span> <span data-ttu-id="d87cc-115">Weitere Informationen zu dieser Vorlage finden Sie unter [Replay Requirements](../sql-server-profiler/replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d87cc-115">For more information about that template, see [Replay Requirements](../sql-server-profiler/replay-requirements.md).</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="d87cc-116">Wenn Sie Eingabedaten der Ablaufverfolgung nicht mithilfe der Vorlage **TSQL_Replay** erfassen oder die Anforderungen an die Eingabedaten nicht erfüllt sind, können unerwartete Wiedergabeergebnisse zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d87cc-116">If you do not use the **TSQL_Replay** template to capture the input trace data, or if the input trace requirements are not satisfied, you may receive unexpected replay results.</span></span>  
  
 <span data-ttu-id="d87cc-117">Solange folgende Ereignisse enthalten sind, können Sie auch eine benutzerdefinierte Ablaufverfolgungsvorlage für die Wiedergabe von Ereignissen mit Distributed Replay verwenden:</span><span class="sxs-lookup"><span data-stu-id="d87cc-117">You can also create a custom trace template and use it to replay events with Distributed Replay, as long as it contains the following events:</span></span>  
  
-   <span data-ttu-id="d87cc-118">Audit Login</span><span class="sxs-lookup"><span data-stu-id="d87cc-118">Audit Login</span></span>  
  
-   <span data-ttu-id="d87cc-119">Audit Logout</span><span class="sxs-lookup"><span data-stu-id="d87cc-119">Audit Logout</span></span>  
  
-   <span data-ttu-id="d87cc-120">ExistingConnection</span><span class="sxs-lookup"><span data-stu-id="d87cc-120">ExistingConnection</span></span>  
  
-   <span data-ttu-id="d87cc-121">RPC Output Parameter</span><span class="sxs-lookup"><span data-stu-id="d87cc-121">RPC Output Parameter</span></span>  
  
-   <span data-ttu-id="d87cc-122">RPC:Completed</span><span class="sxs-lookup"><span data-stu-id="d87cc-122">RPC:Completed</span></span>  
  
-   <span data-ttu-id="d87cc-123">RPC:Starting</span><span class="sxs-lookup"><span data-stu-id="d87cc-123">RPC:Starting</span></span>  
  
-   <span data-ttu-id="d87cc-124">SQL:BatchCompleted</span><span class="sxs-lookup"><span data-stu-id="d87cc-124">SQL:BatchCompleted</span></span>  
  
-   <span data-ttu-id="d87cc-125">SQL:BatchStarting</span><span class="sxs-lookup"><span data-stu-id="d87cc-125">SQL:BatchStarting</span></span>  
  
 <span data-ttu-id="d87cc-126">Wenn Sie serverseitige Cursor wiedergeben, sind auch die folgenden Ereignisse erforderlich:</span><span class="sxs-lookup"><span data-stu-id="d87cc-126">If you are replaying server-side cursors, the following events are also required:</span></span>  
  
-   <span data-ttu-id="d87cc-127">CursorClose</span><span class="sxs-lookup"><span data-stu-id="d87cc-127">CursorClose</span></span>  
  
-   <span data-ttu-id="d87cc-128">CursorExecute</span><span class="sxs-lookup"><span data-stu-id="d87cc-128">CursorExecute</span></span>  
  
-   <span data-ttu-id="d87cc-129">CursorOpen</span><span class="sxs-lookup"><span data-stu-id="d87cc-129">CursorOpen</span></span>  
  
-   <span data-ttu-id="d87cc-130">CursorPrepare</span><span class="sxs-lookup"><span data-stu-id="d87cc-130">CursorPrepare</span></span>  
  
-   <span data-ttu-id="d87cc-131">CursorUnprepare</span><span class="sxs-lookup"><span data-stu-id="d87cc-131">CursorUnprepare</span></span>  
  
 <span data-ttu-id="d87cc-132">Wenn Sie serverseitige vorbereitete SQL-Anweisungen wiedergeben, sind auch die folgenden Ereignisse erforderlich:</span><span class="sxs-lookup"><span data-stu-id="d87cc-132">If you are replaying server-side prepared SQL statements, the following events are also required:</span></span>  
  
-   <span data-ttu-id="d87cc-133">Exec Prepared SQL</span><span class="sxs-lookup"><span data-stu-id="d87cc-133">Exec Prepared SQL</span></span>  
  
-   <span data-ttu-id="d87cc-134">Prepare SQL</span><span class="sxs-lookup"><span data-stu-id="d87cc-134">Prepare SQL</span></span>  
  
 <span data-ttu-id="d87cc-135">Alle Eingabedaten der Ablaufverfolgung müssen die folgenden Spalten enthalten:</span><span class="sxs-lookup"><span data-stu-id="d87cc-135">All input trace data must contain the following columns:</span></span>  
  
-   <span data-ttu-id="d87cc-136">Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="d87cc-136">Event Class</span></span>  
  
-   <span data-ttu-id="d87cc-137">EventSequence</span><span class="sxs-lookup"><span data-stu-id="d87cc-137">EventSequence</span></span>  
  
-   <span data-ttu-id="d87cc-138">TextData</span><span class="sxs-lookup"><span data-stu-id="d87cc-138">TextData</span></span>  
  
-   <span data-ttu-id="d87cc-139">Anwendungsname</span><span class="sxs-lookup"><span data-stu-id="d87cc-139">Application Name</span></span>  
  
-   <span data-ttu-id="d87cc-140">LoginName</span><span class="sxs-lookup"><span data-stu-id="d87cc-140">LoginName</span></span>  
  
-   <span data-ttu-id="d87cc-141">DatabaseName</span><span class="sxs-lookup"><span data-stu-id="d87cc-141">DatabaseName</span></span>  
  
-   <span data-ttu-id="d87cc-142">Datenbank-ID</span><span class="sxs-lookup"><span data-stu-id="d87cc-142">Database ID</span></span>  
  
-   <span data-ttu-id="d87cc-143">HostName</span><span class="sxs-lookup"><span data-stu-id="d87cc-143">HostName</span></span>  
  
-   <span data-ttu-id="d87cc-144">Binary Data</span><span class="sxs-lookup"><span data-stu-id="d87cc-144">Binary Data</span></span>  
  
-   <span data-ttu-id="d87cc-145">SPID</span><span class="sxs-lookup"><span data-stu-id="d87cc-145">SPID</span></span>  
  
-   <span data-ttu-id="d87cc-146">Startzeit</span><span class="sxs-lookup"><span data-stu-id="d87cc-146">Start Time</span></span>  
  
-   <span data-ttu-id="d87cc-147">EndTime</span><span class="sxs-lookup"><span data-stu-id="d87cc-147">EndTime</span></span>  
  
-   <span data-ttu-id="d87cc-148">IsSystem</span><span class="sxs-lookup"><span data-stu-id="d87cc-148">IsSystem</span></span>  
  
## <a name="supported-input-trace-and-target-server-combinations"></a><span data-ttu-id="d87cc-149">Unterstützte Kombinationen aus Eingabedatei der Ablaufverfolgung und Zielserver</span><span class="sxs-lookup"><span data-stu-id="d87cc-149">Supported Input Trace and Target Server Combinations</span></span>  
 <span data-ttu-id="d87cc-150">In der folgenden Tabelle finden Sie die unterstützten Versionen der Ablaufverfolgungsdaten aufgeführt, sowie jeweils die unterstützten Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , für die Daten wiedergegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="d87cc-150">The following table lists the supported versions of trace data, and for each, the supported versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that data can be replayed against.</span></span>  
  
|<span data-ttu-id="d87cc-151">Version der Eingabedaten für die Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="d87cc-151">Version of Input Trace Data</span></span>|<span data-ttu-id="d87cc-152">Unterstützte Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] für die Zielserverinstanz</span><span class="sxs-lookup"><span data-stu-id="d87cc-152">Supported Versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for the Target Server Instance</span></span>|  
|---------------------------------|------------------------------------------------------------------------------------|  
|[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]|[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]<span data-ttu-id="d87cc-153">, [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d87cc-153">, [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]|[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]<span data-ttu-id="d87cc-154">, [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d87cc-154">, [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="d87cc-155">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d87cc-155">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|[!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]|[!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]<span data-ttu-id="d87cc-156">, [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d87cc-156">, [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|[!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]|[!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]|  
  
## <a name="operating-system-requirements"></a><span data-ttu-id="d87cc-157">Betriebssystemanforderungen</span><span class="sxs-lookup"><span data-stu-id="d87cc-157">Operating System Requirements</span></span>  
 <span data-ttu-id="d87cc-158">Zum Ausführen des Verwaltungstools und der Controller- und Clientdienste werden dieselben Betriebssysteme wie für die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d87cc-158">Supported operating systems for running the administration tool and the controller and client services is the same as your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="d87cc-159">Weitere Informationen dazu, welche Betriebssysteme für Ihre-Instanz unterstützt werden [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , finden Sie unter [Hardware-und Software Anforderungen für die Installation von SQL Server 2014](../../sql-server/install/hardware-and-software-requirements-for-installing-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d87cc-159">For more information about which operating systems are supported for your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance, see [Hardware and Software Requirements for Installing SQL Server 2014](../../sql-server/install/hardware-and-software-requirements-for-installing-sql-server.md).</span></span>  
  
 <span data-ttu-id="d87cc-160">Distributed Replay-Funktionen werden unter x86-basierten und x64-basierten Betriebssystemen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d87cc-160">Distributed Replay features are supported on both x86-based and x64-based operating systems.</span></span> <span data-ttu-id="d87cc-161">Bei x64-basierten Betriebssystemen wird nur der WOW-Modus (Windows on Windows) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d87cc-161">For x64-based operating systems, only Windows on Windows (WOW) mode is supported.</span></span>  
  
## <a name="installation-limitations"></a><span data-ttu-id="d87cc-162">Installationseinschränkungen</span><span class="sxs-lookup"><span data-stu-id="d87cc-162">Installation Limitations</span></span>  
 <span data-ttu-id="d87cc-163">Jeder einzelne Computer kann nur eine einzelne Instanz jeder installierten Distributed Replay-Funktion enthalten.</span><span class="sxs-lookup"><span data-stu-id="d87cc-163">Any one computer can only have a single instance of each Distributed Replay feature installed.</span></span> <span data-ttu-id="d87cc-164">Die folgende Tabelle legt dar, wie viele Installationen der einzelnen Funktionen in einer einzelnen Distributed Replay-Umgebung zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="d87cc-164">The following table lists how many installations of each feature are allowed in a single Distributed Replay environment.</span></span>  
  
|<span data-ttu-id="d87cc-165">Distributed Replay-Funktion</span><span class="sxs-lookup"><span data-stu-id="d87cc-165">Distributed Replay Feature</span></span>|<span data-ttu-id="d87cc-166">Maximale Installationen pro Wiedergabeumgebung</span><span class="sxs-lookup"><span data-stu-id="d87cc-166">Maximum Installations Per Replay Environment</span></span>|  
|--------------------------------|--------------------------------------------------|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d87cc-167">Distributed Replay Controller-Dienst</span><span class="sxs-lookup"><span data-stu-id="d87cc-167">Distributed Replay controller service</span></span>|<span data-ttu-id="d87cc-168">1</span><span class="sxs-lookup"><span data-stu-id="d87cc-168">1</span></span>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d87cc-169">Distributed Replay Client-Dienst</span><span class="sxs-lookup"><span data-stu-id="d87cc-169">Distributed Replay client service</span></span>|<span data-ttu-id="d87cc-170">16 (physische oder virtuelle Computer)</span><span class="sxs-lookup"><span data-stu-id="d87cc-170">16 (physical or virtual computers)</span></span>|  
|<span data-ttu-id="d87cc-171">Verwaltungstool</span><span class="sxs-lookup"><span data-stu-id="d87cc-171">Administration tool</span></span>|<span data-ttu-id="d87cc-172">Unbegrenzt</span><span class="sxs-lookup"><span data-stu-id="d87cc-172">Unlimited</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="d87cc-173">Zwar kann auf einem einzelnen Computer nur eine Instanz des Verwaltungstools installiert werden, doch können Sie mehrere Instanzen des Verwaltungstools starten.</span><span class="sxs-lookup"><span data-stu-id="d87cc-173">Although only one instance of the administration tool can be installed on a single computer, you can start multiple instances of the administration tool.</span></span> <span data-ttu-id="d87cc-174">Von mehreren Verwaltungstools ausgegebene Befehle werden in der Reihenfolge aufgelöst, in der sie empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="d87cc-174">Commands issued from multiple administration tools are resolved in the order in which they are received.</span></span>  
  
## <a name="data-access-provider"></a><span data-ttu-id="d87cc-175">Datenzugriffsanbieter</span><span class="sxs-lookup"><span data-stu-id="d87cc-175">Data Access Provider</span></span>  
 <span data-ttu-id="d87cc-176">Distributed Replay unterstützt nur den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC-Datenzugriffsanbieter.</span><span class="sxs-lookup"><span data-stu-id="d87cc-176">Distributed Replay only supports the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC data access provider.</span></span>  
  
## <a name="target-server-preparation-requirements"></a><span data-ttu-id="d87cc-177">Anforderungen bei der Vorbereitung des Zielservers</span><span class="sxs-lookup"><span data-stu-id="d87cc-177">Target Server Preparation Requirements</span></span>  
 <span data-ttu-id="d87cc-178">Es wird empfohlen, den Zielserver in einer Testumgebung zu platzieren.</span><span class="sxs-lookup"><span data-stu-id="d87cc-178">We recommend that the target server be located in a test environment.</span></span> <span data-ttu-id="d87cc-179">Wenn Sie Ablaufverfolgungsdaten für eine andere Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] wiedergeben möchten als ursprünglich festgelegt, stellen Sie sicher, dass auf dem Zielserver die folgenden Aktionen ausgeführt wurden:</span><span class="sxs-lookup"><span data-stu-id="d87cc-179">To replay trace data against a different instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] than it was originally recorded, make sure that the following has been done to the target server:</span></span>  
  
-   <span data-ttu-id="d87cc-180">Alle in den Ablaufverfolgungsdaten verzeichneten Anmeldungen und Benutzer müssen auch in der gleichen Datenbank auf dem Zielserver vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="d87cc-180">All logins and users that are contained in the trace data must be present in the same database on the target server.</span></span>  
  
-   <span data-ttu-id="d87cc-181">Alle Benutzernamen und Benutzer auf dem Zielserver müssen über dieselben Berechtigungen wie auf dem ursprünglichen Server verfügen.</span><span class="sxs-lookup"><span data-stu-id="d87cc-181">All logins and users on the target server must have the same permissions they had on the original server.</span></span>  
  
-   <span data-ttu-id="d87cc-182">Die Datenbank-IDs auf dem Ziel sollten mit denen auf der Quelle übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="d87cc-182">The database IDs on the target ideally should be the same as those on the source.</span></span> <span data-ttu-id="d87cc-183">Andernfalls können Sie basierend auf **DatabaseName** einen Abgleich ausführen, sofern dieser in der Ablaufverfolgung enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="d87cc-183">However, if they are not the same, matching can be performed based on **DatabaseName** if it is present in the trace.</span></span>  
  
-   <span data-ttu-id="d87cc-184">Die Standarddatenbank für jeden in den Ablaufverfolgungsdaten enthaltenen Benutzernamen muss (auf dem Zielserver) auf die entsprechende Zieldatenbank des Benutzernamens festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="d87cc-184">The default database for each login that is contained in the trace data must be set (on the target server) to the respective target database of the login.</span></span> <span data-ttu-id="d87cc-185">Angenommen, die wiederzugebenden Ablaufverfolgungsdaten enthalten Aktivitäten für den Benutzernamen **Fred**in der Datenbank **Fred_Db** der ursprünglichen Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d87cc-185">For example, the trace data to be replayed contains activity for the login, **Fred**, in the database **Fred_Db** on the original instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d87cc-186">Dann muss auf dem Zielserver die Standarddatenbank für den Benutzernamen **Fred**auf die Datenbank festgelegt werden, die mit **Fred_Db** übereinstimmt (auch, wenn sich der Datenbankname unterscheidet).</span><span class="sxs-lookup"><span data-stu-id="d87cc-186">Therefore, on the target server, the default database for the login, **Fred**, must be set to the database that matches **Fred_Db** (even if the database name is different).</span></span> <span data-ttu-id="d87cc-187">Legen Sie mithilfe der gespeicherten Systemprozedur `sp_defaultdb` die Standarddatenbank für den Benutzernamen fest.</span><span class="sxs-lookup"><span data-stu-id="d87cc-187">To set the default database of the login, use the `sp_defaultdb` system stored procedure.</span></span>  
  
 <span data-ttu-id="d87cc-188">Beim Wiedergeben von Ereignissen, die fehlende oder fehlerhafte Benutzernamen aufweisen, können Wiedergabefehler auftreten, die Wiedergabe wird jedoch fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="d87cc-188">Replaying events associated with missing or incorrect logins results in replay errors, but the replay operation continues.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d87cc-189">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d87cc-189">See Also</span></span>  
 <span data-ttu-id="d87cc-190">[SQL Server Distributed Replay](sql-server-distributed-replay.md) </span><span class="sxs-lookup"><span data-stu-id="d87cc-190">[SQL Server Distributed Replay](sql-server-distributed-replay.md) </span></span>  
 <span data-ttu-id="d87cc-191">[Distributed Replay Sicherheit](distributed-replay-security.md) </span><span class="sxs-lookup"><span data-stu-id="d87cc-191">[Distributed Replay Security](distributed-replay-security.md) </span></span>  
 [<span data-ttu-id="d87cc-192">Installieren von Distributed Replay</span><span class="sxs-lookup"><span data-stu-id="d87cc-192">Install Distributed Replay</span></span>](install-distributed-replay-overview.md)  
  
  
