---
title: Installieren von Reporting Services und Internetinformationsdienste nebeneinander (einheitlicher SSRS-Modus) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- deploying [Reporting Services], IIS
ms.assetid: 9b651fa5-f582-4f18-a77d-0dde95d9d211
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c16bb8e5cd8fd040e0048c17183d69bae68268ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695433"
---
# <a name="install-reporting-services-and-internet-information-services-side-by-side-ssrs-native-mode"></a><span data-ttu-id="5a25b-102">Gleichzeitiges Installieren von Reporting Services und Internetinformationsdiensten (einheitlicher SSRS-Modus)</span><span class="sxs-lookup"><span data-stu-id="5a25b-102">Install Reporting Services and Internet Information Services Side-by-Side (SSRS Native Mode)</span></span>
  <span data-ttu-id="5a25b-103">Sie können [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] (SSRS) und Internetinformationsdienste (IIS) auf dem gleichen Computer installieren und ausführen.</span><span class="sxs-lookup"><span data-stu-id="5a25b-103">You can install and run [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] (SSRS) and Internet Information Services (IIS) on the same computer.</span></span> <span data-ttu-id="5a25b-104">Je nach IIS-Version treten bestimmte Interoperabilitätsprobleme auf.</span><span class="sxs-lookup"><span data-stu-id="5a25b-104">The version of IIS that you are using determines the interoperability issues you must address.</span></span>  
  
||  
|-|  
|[!INCLUDE[applies](../../includes/applies-md.md)]<span data-ttu-id="5a25b-105">Einheitlicher [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Modus</span><span class="sxs-lookup"><span data-stu-id="5a25b-105">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode</span></span>|  
  
|<span data-ttu-id="5a25b-106">IIS-Version</span><span class="sxs-lookup"><span data-stu-id="5a25b-106">IIS version</span></span>|<span data-ttu-id="5a25b-107">Probleme</span><span class="sxs-lookup"><span data-stu-id="5a25b-107">Issues</span></span>|<span data-ttu-id="5a25b-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5a25b-108">Description</span></span>|  
|-----------------|------------|-----------------|  
|<span data-ttu-id="5a25b-109">IIS 6.0, 7.0, 8.0, 8.5</span><span class="sxs-lookup"><span data-stu-id="5a25b-109">IIS 6.0, 7.0, 8.0, 8.5</span></span>|<span data-ttu-id="5a25b-110">Für eine bestimmte Anwendung vorgesehene Anforderungen werden von einer anderen Anwendung angenommen.</span><span class="sxs-lookup"><span data-stu-id="5a25b-110">Requests intended for one application are accepted by a different application.</span></span><br /><br /> <span data-ttu-id="5a25b-111">HTTP.SYS erzwingt Rangfolgeregeln für URL-Reservierungen.</span><span class="sxs-lookup"><span data-stu-id="5a25b-111">HTTP.SYS enforces precedence rules for URL reservations.</span></span> <span data-ttu-id="5a25b-112">Anforderungen, die an Anwendungen gesendet werden, die den gleichen virtuellen Verzeichnisnamen aufweisen und gemeinsam Port 80 überwachen, erreichen möglicherweise nicht das vorgesehene Ziel, wenn die URL-Reservierung im Vergleich zur URL-Reservierung einer anderen Anwendung schwach ist.</span><span class="sxs-lookup"><span data-stu-id="5a25b-112">Requests that are sent to applications that have the same virtual directory name and that jointly monitor port 80 might not reach the intended target if the URL reservation is weak relative to the URL reservation of another application.</span></span>|<span data-ttu-id="5a25b-113">Unter bestimmten Bedingungen empfängt ein registrierter Endpunkt, der einen anderen URL-Endpunkt im URL-Reservierungsschema außer Kraft setzt, HTTP-Anforderungen für die andere Anwendung.</span><span class="sxs-lookup"><span data-stu-id="5a25b-113">Under certain conditions, a registered endpoint that supersedes another URL endpoint in the URL reservation scheme might receive HTTP requests intended for the other application.</span></span><br /><br /> <span data-ttu-id="5a25b-114">Durch die Verwendung eindeutiger Namen für die virtuellen Verzeichnisse des Report Server-Webdiensts und des Berichts-Managers kann dieser Konflikt vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="5a25b-114">Using unique virtual directory names for the Report Server Web service and Report Manager helps you avoid this conflict.</span></span><br /><br /> <span data-ttu-id="5a25b-115">Detaillierte Informationen über dieses Szenario sind in diesem Thema enthalten.</span><span class="sxs-lookup"><span data-stu-id="5a25b-115">Detailed information about this scenario is provided in this topic.</span></span>|  
  
## <a name="precedence-rules-for-url-reservations"></a><span data-ttu-id="5a25b-116">Rangfolgeregeln für URL-Reservierungen</span><span class="sxs-lookup"><span data-stu-id="5a25b-116">Precedence Rules for URL Reservations</span></span>  
 <span data-ttu-id="5a25b-117">Um die Interoperabilitätsprobleme zwischen IIS und [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]lösen zu können, müssen Sie zunächst die URL-Reservierungsrangfolgeregeln verstehen.</span><span class="sxs-lookup"><span data-stu-id="5a25b-117">Before you can address interoperability issues between IIS and [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you must understand URL reservation precedence rules.</span></span> <span data-ttu-id="5a25b-118">Rangfolgeregeln können folgendermaßen beschrieben werden: Je expliziter eine URL-Reservierung definiert ist, umso eher erhält sie die Anforderungen für diese URL.</span><span class="sxs-lookup"><span data-stu-id="5a25b-118">Precedence rules can be generalized into the following statement: a URL reservation that has more explicitly defined values is first in line to receive requests that match the URL.</span></span>  
  
-   <span data-ttu-id="5a25b-119">Eine URL-Reservierung, die ein virtuelles Verzeichnis angibt, ist expliziter als eine URL-Reservierung ohne virtuelles Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="5a25b-119">A URL reservation that specifies a virtual directory is more explicit than one that omits a virtual directory.</span></span>  
  
-   <span data-ttu-id="5a25b-120">Eine URL-Reservierung, die eine einzige Adresse angibt (mittels einer IP-Adresse, eines vollqualifizierten Domänennamens, eines Computernamens im Netzwerk oder eines Hostnamens) ist expliziter als ein Platzhalter.</span><span class="sxs-lookup"><span data-stu-id="5a25b-120">A URL reservation that specifies a single address (by way of an IP address, a fully qualified domain name, a network computer name, or a host name) is more explicit than a wildcard.</span></span>  
  
-   <span data-ttu-id="5a25b-121">Eine URL-Reservierung, die einen starken Platzhalter angibt, ist expliziter als eine URL-Reservierung mit einem schwachen Platzhalter.</span><span class="sxs-lookup"><span data-stu-id="5a25b-121">A URL reservation that specifies a strong wildcard is more explicit than a weak wildcard.</span></span>  
  
 <span data-ttu-id="5a25b-122">In den folgenden Beispielen werden verschiedene URL-Reservierungen gezeigt. Als Erste steht die URL-Reservierung mit der höchsten Explizität, als Letzte die mit der geringsten Explizität:</span><span class="sxs-lookup"><span data-stu-id="5a25b-122">The following examples show a range of URL reservations, ordered from most explicit to least explicit:</span></span>  
  
|<span data-ttu-id="5a25b-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5a25b-123">Example</span></span>|<span data-ttu-id="5a25b-124">Anforderung</span><span class="sxs-lookup"><span data-stu-id="5a25b-124">Request</span></span>|  
|-------------|-------------|  
|<span data-ttu-id="5a25b-125">http: \/ /123.234.345.456:80/Berichte</span><span class="sxs-lookup"><span data-stu-id="5a25b-125">http:\//123.234.345.456:80/reports</span></span>|<span data-ttu-id="5a25b-126">Empfängt alle Anforderungen, die an http: \/ /123.234.345.456/Reports oder http:///Reports gesendet werden, \<computername> Wenn ein Domain Name Service die IP-Adresse in diesen Hostnamen auflösen kann.</span><span class="sxs-lookup"><span data-stu-id="5a25b-126">Receives all requests that are sent to http:\//123.234.345.456/reports or http://\<computername>/reports if a domain name service can resolve the IP address to that host name.</span></span>|  
|http://+:80/reports|<span data-ttu-id="5a25b-127">Empfängt alle Anforderungen, die an eine IP-Adresse oder einen Hostnamen gesendet werden, die bzw. der gültig für diesen Computer ist, sofern die URL den Namen des virtuellen Verzeichnisses "reports" enthält.</span><span class="sxs-lookup"><span data-stu-id="5a25b-127">Receives any requests that are sent to any IP address or host name that is valid for that computer as long as the URL contains the "reports" virtual directory name.</span></span>|  
|<span data-ttu-id="5a25b-128">http: \/ /123.234.345.456:80</span><span class="sxs-lookup"><span data-stu-id="5a25b-128">http:\//123.234.345.456:80</span></span>|<span data-ttu-id="5a25b-129">Empfängt jede Anforderung, die http: \/ /123.234.345.456 oder http://angibt, \<computername> Wenn ein Domain Name Service die IP-Adresse in diesen Hostnamen auflösen kann.</span><span class="sxs-lookup"><span data-stu-id="5a25b-129">Receives any request that specifies http:\//123.234.345.456 or http://\<computername> if a domain name service can resolve the IP address to that host name.</span></span>|  
|http://+:80|<span data-ttu-id="5a25b-130">Empfängt für alle Anwendungsendpunkte, die **Alle zugewiesenen**zugeordnet sind, Anforderungen, die nicht bereits von anderen Anwendungen empfangen wurden.</span><span class="sxs-lookup"><span data-stu-id="5a25b-130">Receives requests that are not already received by other applications, for any application endpoints that are mapped to **All Assigned**.</span></span>|  
|<span data-ttu-id="5a25b-131">http://\*:80</span><span class="sxs-lookup"><span data-stu-id="5a25b-131">http://\*:80</span></span>|<span data-ttu-id="5a25b-132">Empfängt für Anwendungsendpunkte, die **Alle nicht zugewiesenen**zugeordnet sind, Anforderungen, die nicht bereits von anderen Anwendungen empfangen wurden.</span><span class="sxs-lookup"><span data-stu-id="5a25b-132">Receives requests that are not already received by other applications, for application endpoints that are mapped to **All Unassigned**.</span></span>|  
  
 <span data-ttu-id="5a25b-133">Ein Zeichen für einen Portkonflikt ist die folgende Fehlermeldung: 'System.IO.FileLoadException: Der Prozess kann nicht auf die Datei zugreifen, da sie von einem anderen Prozess verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5a25b-133">One indication of a port conflict is that you will see the following error message: 'System.IO.FileLoadException: The process cannot access the file because it is being used by another process.</span></span> <span data-ttu-id="5a25b-134">(Ausnahme von HRESULT: 0x80070020).</span><span class="sxs-lookup"><span data-stu-id="5a25b-134">(Exception from HRESULT: 0x80070020).'</span></span>  
  
## <a name="url-reservations-for-iis-60-70-80-85-with-sssql14-reporting-services"></a><span data-ttu-id="5a25b-135">URL-Reservierungen für IIS 6.0, 7.0, 8.0, 8.5 mit [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] Reporting Services</span><span class="sxs-lookup"><span data-stu-id="5a25b-135">URL Reservations for IIS 6.0, 7.0, 8.0, 8.5 with [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] Reporting Services</span></span>  
 <span data-ttu-id="5a25b-136">Anhand der im vorherigen Abschnitt beschriebenen Rangfolgeregeln wird deutlich, wie die für Reporting Services und IIS definierten URL-Reservierungen zur Interoperabilität beitragen.</span><span class="sxs-lookup"><span data-stu-id="5a25b-136">Given the precedence rules outlined in the previous section, you can begin to understand how URL reservations defined for Reporting Services and IIS promote interoperability.</span></span> <span data-ttu-id="5a25b-137">Reporting Services empfängt Anforderungen, die die Namen der virtuellen Verzeichnisse seiner Anwendungen explizit angeben; IIS empfängt alle verbleibenden Anforderungen, die dann an Anwendungen umgeleitet werden können, die innerhalb des IIS-Verarbeitungsmodells ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5a25b-137">Reporting Services receives requests that explicitly specify the virtual directory names for its applications; IIS receives all remaining requests, which can then be directed to applications that run within the IIS process model.</span></span>  
  
|<span data-ttu-id="5a25b-138">Application</span><span class="sxs-lookup"><span data-stu-id="5a25b-138">Application</span></span>|<span data-ttu-id="5a25b-139">URL-Reservierung</span><span class="sxs-lookup"><span data-stu-id="5a25b-139">URL reservation</span></span>|<span data-ttu-id="5a25b-140">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5a25b-140">Description</span></span>|<span data-ttu-id="5a25b-141">Anforderungsempfang</span><span class="sxs-lookup"><span data-stu-id="5a25b-141">Request receipt</span></span>|  
|-----------------|---------------------|-----------------|---------------------|  
|<span data-ttu-id="5a25b-142">Berichtsserver</span><span class="sxs-lookup"><span data-stu-id="5a25b-142">Report Server</span></span>|http://+:80/ReportServer|<span data-ttu-id="5a25b-143">Starker Platzhalter an Port 80, mit virtuellem Verzeichnis "ReportServer".</span><span class="sxs-lookup"><span data-stu-id="5a25b-143">Strong wildcard on port 80, with report server virtual directory.</span></span>|<span data-ttu-id="5a25b-144">Empfängt alle Anforderungen an Port 80, die das virtuelle Verzeichnis "ReportServer" angeben.</span><span class="sxs-lookup"><span data-stu-id="5a25b-144">Receives all requests on port 80 that specify the report server virtual directory.</span></span> <span data-ttu-id="5a25b-145">Der Report Server-Webdienst empfängt alle Anforderungen an http:// \<computername> /reportserver.</span><span class="sxs-lookup"><span data-stu-id="5a25b-145">The Report Server Web service receives all requests to http://\<computername>/reportserver.</span></span>|  
|<span data-ttu-id="5a25b-146">Berichts-Manager</span><span class="sxs-lookup"><span data-stu-id="5a25b-146">Report Manager</span></span>|http://+:80/Reports|<span data-ttu-id="5a25b-147">Starker Platzhalter an Port 80, mit virtuellem Verzeichnis "Reports".</span><span class="sxs-lookup"><span data-stu-id="5a25b-147">Strong wildcard on port 80, with Reports virtual directory.</span></span>|<span data-ttu-id="5a25b-148">Empfängt alle Anforderungen an Port 80, die das virtuelle Verzeichnis "reports" angeben.</span><span class="sxs-lookup"><span data-stu-id="5a25b-148">Receives all requests on port 80 that specify the reports virtual directory.</span></span> <span data-ttu-id="5a25b-149">Berichts-Manager empfängt alle Anforderungen an http:// \<computername> /Reports.</span><span class="sxs-lookup"><span data-stu-id="5a25b-149">Report Manager receives all requests to http://\<computername>/reports.</span></span>|  
|<span data-ttu-id="5a25b-150">IIS</span><span class="sxs-lookup"><span data-stu-id="5a25b-150">IIS</span></span>|<span data-ttu-id="5a25b-151">http://\*:80/</span><span class="sxs-lookup"><span data-stu-id="5a25b-151">http://\*:80/</span></span>|<span data-ttu-id="5a25b-152">Schwacher Platzhalter an Port 80.</span><span class="sxs-lookup"><span data-stu-id="5a25b-152">Weak wildcard on port 80.</span></span>|<span data-ttu-id="5a25b-153">Empfängt an Port 80 alle verbleibenden Anforderungen, die nicht von einer anderen Anwendung empfangen wurden.</span><span class="sxs-lookup"><span data-stu-id="5a25b-153">Receives any remaining requests on port 80 that are not received by another application.</span></span>|  
  
## <a name="side-by-side-deployments-of-sscurrent-and-sql-server-2005-reporting-services-on-iis-60-70-80-85"></a><span data-ttu-id="5a25b-154">Parallele Bereitstellungen von [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] und SQL Server 2005 Reporting Services auf IIS 6.0, 7.0, 8.0, 8.5</span><span class="sxs-lookup"><span data-stu-id="5a25b-154">Side-by-Side Deployments of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] and SQL Server 2005 Reporting Services on IIS 6.0, 7.0, 8.0, 8.5</span></span>  
 <span data-ttu-id="5a25b-155">Interoperabilitätsprobleme zwischen IIS und Reporting Services treten auf, wenn IIS-Websites und Reporting Services identische Namen virtueller Verzeichnisse aufweisen.</span><span class="sxs-lookup"><span data-stu-id="5a25b-155">Interoperability issues between IIS and Reporting Services occur when IIS Web sites have virtual directory names that are identical to those used by Reporting Services.</span></span> <span data-ttu-id="5a25b-156">Gehen wir beispielsweise von folgender Konfiguration aus:</span><span class="sxs-lookup"><span data-stu-id="5a25b-156">For example, suppose you have the following configuration:</span></span>  
  
-   <span data-ttu-id="5a25b-157">Eine Website in IIS, die Port 80 und einem virtuellen Verzeichnis mit dem Namen "Reports" zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="5a25b-157">A Web site in IIS that is assigned to port 80 and a virtual directory named "Reports".</span></span>  
  
-   <span data-ttu-id="5a25b-158">Eine [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] in der Standardkonfiguration installierte Berichts Serverinstanz, bei der die URL-Reservierung auch Port 80 angibt, und die Berichts-Manager Anwendung verwendet auch "Reports" als Namen des virtuellen Verzeichnisses.</span><span class="sxs-lookup"><span data-stu-id="5a25b-158">A [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] report server instance installed in the default configuration, where the URL reservation also specifies port 80 and the Report Manager application also uses "Reports" for the virtual directory name.</span></span>  
  
 <span data-ttu-id="5a25b-159">Bei dieser Konfiguration wird eine an http:// \<computername> : 80/reports gesendete Anforderung von Berichts-Manager empfangen.</span><span class="sxs-lookup"><span data-stu-id="5a25b-159">Given this configuration, a request that is sent to http://\<computername>:80/reports will be received by Report Manager.</span></span> <span data-ttu-id="5a25b-160">Die Anwendung, auf die über das virtuelle Verzeichnis „Reports“ in IIS zugegriffen wird, empfängt nach der Installation der [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] -Berichtsserverinstanz keine Anforderungen mehr.</span><span class="sxs-lookup"><span data-stu-id="5a25b-160">The application that is accessed through the Reports virtual directory in IIS will no longer receive requests after [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] report server instance is installed.</span></span>  
  
 <span data-ttu-id="5a25b-161">Wenn Sie die Bereitstellungen älterer und neuerer Versionen von [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]gleichzeitig ausführen, tritt unter Umständen das gerade beschriebene Routingproblem auf.</span><span class="sxs-lookup"><span data-stu-id="5a25b-161">If you are running side-by-side deployments of older and newer versions of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you are likely to encounter the routing problem just described.</span></span> <span data-ttu-id="5a25b-162">Dies liegt daran, dass alle [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]-Versionen "ReportServer" und "Reports" als Namen der virtuellen Verzeichnisse für den Berichtsserver und den Berichts-Manager verwenden und damit die Wahrscheinlichkeit erhöht wird, dass in IIS die virtuellen Verzeichnisse "reports" und "reportserver" vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="5a25b-162">This is because all versions of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] use "ReportServer" and "Reports" as virtual directory names for the report server and Report Manager applications, increasing the likelihood that you will have a "reports" and "reportserver" virtual directories in IIS.</span></span>  
  
 <span data-ttu-id="5a25b-163">Um sicherzustellen, dass alle Anwendungen Anforderungen empfangen, sollten Sie diesen Richtlinien folgen:</span><span class="sxs-lookup"><span data-stu-id="5a25b-163">To ensure that all applications receive requests, follow these guidelines:</span></span>  
  
-   <span data-ttu-id="5a25b-164">In Reporting Services-Installationen sollten Sie Namen für virtuelle Verzeichnisse angeben, die nicht bereits von einer IIS-Website an dem Port verwendet werden, den auch Reporting Services verwendet.</span><span class="sxs-lookup"><span data-stu-id="5a25b-164">For Reporting Services installations, use virtual directory names that are not already used by an IIS Web site on the same port as Reporting Services.</span></span> <span data-ttu-id="5a25b-165">Wenn ein Konflikt auftritt, müssen Sie Reporting Services im Dateimodus installieren (über die Option Server installieren, jedoch nicht konfigurieren im Installations-Assistenten), sodass Sie die virtuellen Verzeichnisse nach dem Setup konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="5a25b-165">If there is a conflict, install Reporting Services in "files-only" mode (using the Install but do not configure the server option in the Installation Wizard) so that you can configure the virtual directories after Setup is finished.</span></span> <span data-ttu-id="5a25b-166">Ein Zeichen für einen Konflikt in Ihrer Konfiguration ist die folgende Fehlermeldung: 'System.IO.FileLoadException: Der Prozess kann nicht auf die Datei zugreifen, da sie von einem anderen Prozess verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5a25b-166">One indication that your configuration has a conflict is you will see the error message: System.IO.FileLoadException: The process cannot access the file because it is being used by another process.</span></span> <span data-ttu-id="5a25b-167">(Ausnahme von HRESULT: 0x80070020).</span><span class="sxs-lookup"><span data-stu-id="5a25b-167">(Exception from HRESULT: 0x80070020).</span></span>  
  
-   <span data-ttu-id="5a25b-168">Übernehmen Sie für Installationen, die Sie manuell konfigurieren, die Standardnamenskonventionen in den URLs.</span><span class="sxs-lookup"><span data-stu-id="5a25b-168">For installations that you configure manually, adopt the default naming conventions in the URLs that configure.</span></span> <span data-ttu-id="5a25b-169">Wenn Sie [!INCLUDE[ssRSCurrent](../../includes/ssrscurrent-md.md)] als benannte Instanz installieren, müssen Sie beim Erstellen eines virtuellen Verzeichnisses den Instanznamen angeben.</span><span class="sxs-lookup"><span data-stu-id="5a25b-169">If you install [!INCLUDE[ssRSCurrent](../../includes/ssrscurrent-md.md)] as a named instance, include the instance name when creating a virtual directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a25b-170">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5a25b-170">See Also</span></span>  
 <span data-ttu-id="5a25b-171">[Konfigurieren von Berichtsserver-URLs &#40;SSRS-Konfigurations-Manager&#41;](configure-report-server-urls-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="5a25b-171">[Configure Report Server URLs  &#40;SSRS Configuration Manager&#41;](configure-report-server-urls-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="5a25b-172">[Konfigurieren einer URL &#40;SSRS-Configuration Manager&#41;](configure-a-url-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="5a25b-172">[Configure a URL  &#40;SSRS Configuration Manager&#41;](configure-a-url-ssrs-configuration-manager.md) </span></span>  
 [<span data-ttu-id="5a25b-173">Installieren des Reporting Services-Berichtsservers im einheitlichen Modus</span><span class="sxs-lookup"><span data-stu-id="5a25b-173">Install Reporting Services Native Mode Report Server</span></span>](install-reporting-services-native-mode-report-server.md)  
  
  