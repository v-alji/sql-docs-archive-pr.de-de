---
title: Angeben der Endpunkt-URL beim Hinzufügen oder Ändern eines Verfügbarkeits Replikats (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- endpoints [SQL Server], AlwaysOn Availability Groups
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], endpoint
- Endpoint URLs (HADR)
ms.assetid: d7520c13-a8ee-4ddc-9e9a-54cd3d27ef1c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: da1eb2bacd4d5a2f7d0b2a623343f62b5e89597d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724978"
---
# <a name="specify-the-endpoint-url-when-adding-or-modifying-an-availability-replica-sql-server"></a><span data-ttu-id="71a98-102">Angeben der Endpunkt-URL beim Hinzufügen oder Ändern eines Verfügbarkeitsreplikats (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="71a98-102">Specify the Endpoint URL When Adding or Modifying an Availability Replica (SQL Server)</span></span>
  <span data-ttu-id="71a98-103">Um ein Verfügbarkeitsreplikat für eine Verfügbarkeitsgruppe zu hosten, muss eine Serverinstanz einen Datenbankspiegelungs-Endpunkt besitzen.</span><span class="sxs-lookup"><span data-stu-id="71a98-103">To host an availability replica for an availability group, a server instance must possess a database mirroring endpoint.</span></span> <span data-ttu-id="71a98-104">Die Serverinstanz überwacht [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] -Meldungen von Verfügbarkeitsreplikaten, die von anderen Serverinstanzen gehostet wurden, mithilfe dieses Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="71a98-104">The server instance uses this endpoint to listen for [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] messages from availability replicas hosted by other server instances.</span></span> <span data-ttu-id="71a98-105">Um ein Verfügbarkeitsreplikat für eine Verfügbarkeitsgruppe zu definieren, müssen Sie die Endpunkt-URL der Serverinstanz angeben, die das Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="71a98-105">To define an availability replica for an availability group, you must specify the endpoint URL of the server instance that will host the replica.</span></span> <span data-ttu-id="71a98-106">Die *Endpunkt-URL* identifiziert das Transportprotokoll des Datenbankspiegelungs-Endpunkt-TCP, die Systemadresse der Serverinstanz und die dem Endpunkt zugeordnete Portnummer.</span><span class="sxs-lookup"><span data-stu-id="71a98-106">The *endpoint URL* identifies the transport protocol of the database mirroring endpoint-TCP, the system address of the server instance, and the port number associated with the endpoint.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="71a98-107">Die Begriff "Endpunkt-URL" ist ein Synonym für den Begriff "Servernetzwerkadresse", der von der Datenbankspiegelungsbenutzeroberfläche und in der Dokumentation verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="71a98-107">The term "endpoint URL" is synonymous with the term "server network address" used by the database mirroring user interface and documentation.</span></span>  
  
-   [<span data-ttu-id="71a98-108">Syntax für eine Endpunkt-URL</span><span class="sxs-lookup"><span data-stu-id="71a98-108">Syntax for an Endpoint URL</span></span>](#SyntaxOfURL)  
  
-   [<span data-ttu-id="71a98-109">Ermitteln des voll qualifizierten Domänen Namens eines Systems</span><span class="sxs-lookup"><span data-stu-id="71a98-109">Finding the Fully Qualified Domain Name of A System</span></span>](#Finding_FQDN)  
  
-   [<span data-ttu-id="71a98-110">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="71a98-110">Related Tasks</span></span>](#RelatedTasks)  
  
-   [<span data-ttu-id="71a98-111">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="71a98-111">Related Content</span></span>](#RelatedContent)  
  
##  <a name="syntax-for-an-endpoint-url"></a><a name="SyntaxOfURL"></a> <span data-ttu-id="71a98-112">Syntax für eine Endpunkt-URL</span><span class="sxs-lookup"><span data-stu-id="71a98-112">Syntax for an Endpoint URL</span></span>  
 <span data-ttu-id="71a98-113">Die Syntax für eine Endpunkt-URL hat folgende Form:</span><span class="sxs-lookup"><span data-stu-id="71a98-113">The syntax for an endpoint URL is of the form:</span></span>  
  
 <span data-ttu-id="71a98-114">TCP<strong>://</strong> *\<system-address>* <strong>:</strong> *\<port>*</span><span class="sxs-lookup"><span data-stu-id="71a98-114">TCP<strong>://</strong>*\<system-address>*<strong>:</strong>*\<port>*</span></span>  
  
 <span data-ttu-id="71a98-115">Hierbei gilt:</span><span class="sxs-lookup"><span data-stu-id="71a98-115">where</span></span>  
  
-   <span data-ttu-id="71a98-116">*\<system-address>* ist eine Zeichenfolge, die das Zielcomputersystem eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="71a98-116">*\<system-address>* is a string that unambiguously identifies the target computer system.</span></span> <span data-ttu-id="71a98-117">In der Regel handelt es sich bei der Serveradresse um einen Systemnamen (wenn sich die Systeme in derselben Domäne befinden), einen vollqualifizierten Domänennamen oder eine IP-Adresse:</span><span class="sxs-lookup"><span data-stu-id="71a98-117">Typically, the server address is a system name (if the systems are in the same domain), a fully qualified domain name, or an IP address:</span></span>  
  
    -   <span data-ttu-id="71a98-118">Da die Knoten des WSFC-Clusters (Windows Server-Failoverclustering) sich in derselben Domäne befinden, können Sie den Namen des Computersystems verwenden, z. B. `SYSTEM46`.</span><span class="sxs-lookup"><span data-stu-id="71a98-118">Because the nodes of Windows Server Failover Clustering (WSFC) cluster are the same domain, you can use the name of the computer system; for example, `SYSTEM46`.</span></span>  
  
    -   <span data-ttu-id="71a98-119">Wenn Sie eine IP-Adresse verwenden möchten, muss diese in Ihrer Umgebung eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="71a98-119">To use an IP address, it must be unique in your environment.</span></span> <span data-ttu-id="71a98-120">Wir empfehlen die Verwendung einer IP-Adresse nur, wenn diese statisch ist.</span><span class="sxs-lookup"><span data-stu-id="71a98-120">We recommend that you use an IP address only if it is static.</span></span> <span data-ttu-id="71a98-121">Die IP-Adresse kann im IPv4-Format (IP Version 4) oder im IPv6-Format (IP Version) vorliegen.</span><span class="sxs-lookup"><span data-stu-id="71a98-121">The IP address can be IP Version 4 (IPv4) or IP Version 6 (IPv6).</span></span> <span data-ttu-id="71a98-122">Eine IPv6-Adresse muss in eckige Klammern gesetzt werden, z.B. **[** _<IPv6-Adresse>_ **]** .</span><span class="sxs-lookup"><span data-stu-id="71a98-122">An IPv6 address must be enclosed within square brackets, for example: **[**_<IPv6_address>_**]**.</span></span>  
  
         <span data-ttu-id="71a98-123">Um die IP-Adresse eines Systems zu ermitteln, geben Sie an der Windows-Eingabeaufforderung den Befehl **ipconfig** ein.</span><span class="sxs-lookup"><span data-stu-id="71a98-123">To learn the IP address of a system, at the Windows command prompt, enter the **ipconfig** command.</span></span>  
  
    -   <span data-ttu-id="71a98-124">Der vollqualifizierte Domänenname funktioniert auf alle Fälle.</span><span class="sxs-lookup"><span data-stu-id="71a98-124">The fully qualified domain name is guaranteed to work.</span></span> <span data-ttu-id="71a98-125">Hierbei handelt es sich um eine lokal definierte Adresszeichenfolge, die an unterschiedlichen Stellen unterschiedliche Formen annimmt.</span><span class="sxs-lookup"><span data-stu-id="71a98-125">This is a locally defined address string that takes different forms in different places.</span></span> <span data-ttu-id="71a98-126">Häufig, jedoch nicht immer, ist ein vollqualifizierter Domänenname ein zusammengesetzter Name, der den Computernamen und eine Reihe von Domänensegmenten enthält, die durch Punkte voneinander getrennt sind, z. B.:</span><span class="sxs-lookup"><span data-stu-id="71a98-126">Often, but not always, a fully qualified domain name is a compound name that includes the computer name and a series of period-separated domain segments of the form:</span></span>  
  
         <span data-ttu-id="71a98-127">_Computername_ **.**</span><span class="sxs-lookup"><span data-stu-id="71a98-127">_computer_name_ **.**</span></span> <span data-ttu-id="71a98-128">_Domänensegment_[... **.** _Domänensegment_]</span><span class="sxs-lookup"><span data-stu-id="71a98-128">_domain_segment_[...**.**_domain_segment_]</span></span>  
  
         <span data-ttu-id="71a98-129">Dabei steht *Computername*für den Netzwerknamen des Computers, auf dem die Serverinstanz ausgeführt wird, und *Domänensegment*[... **.** _Domänensegment_] für die übrigen Domäneninformationen des Servers. Beispiel: `localinfo.corp.Adventure-Works.com`.</span><span class="sxs-lookup"><span data-stu-id="71a98-129">where *computer_name i*s the network name of the computer running the server instance, and *domain_segment*[...**.**_domain_segment_] is the remaining domain information of the server; for example: `localinfo.corp.Adventure-Works.com`.</span></span>  
  
         <span data-ttu-id="71a98-130">Inhalt und Anzahl von Domänenelementen werden innerhalb des Unternehmens oder der Organisation bestimmt.</span><span class="sxs-lookup"><span data-stu-id="71a98-130">The content and number of domain segments are determined within the company or organization.</span></span> <span data-ttu-id="71a98-131">Weitere Informationen finden Sie in [Ermitteln des vollqualifizierten Domänennamens](#Finding_FQDN)weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="71a98-131">For more information, see [Finding the Fully Qualified Domain Name](#Finding_FQDN), later in this topic.</span></span>  
  
-   <span data-ttu-id="71a98-132">*\<port>* ist die Portnummer, die vom Spiegelungsendpunkt der Partnerserverinstanz verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="71a98-132">*\<port>* is the port number used by the mirroring endpoint of the partner server instance.</span></span>  
  
     <span data-ttu-id="71a98-133">Ein Datenbankspiegelungs-Endpunkt kann jeden verfügbaren Port im Computersystem verwenden.</span><span class="sxs-lookup"><span data-stu-id="71a98-133">A database mirroring endpoint can use any available port on the computer system.</span></span> <span data-ttu-id="71a98-134">Jede Portnummer darf nur einem Endpunkt zugeordnet werden, und jeder Endpunkt ist einer einzelnen Serverinstanz zugeordnet. Daher lauschen unterschiedliche Serverinstanzen auf dem gleichen Server an unterschiedliche Endpunkten mit unterschiedlichen Ports.</span><span class="sxs-lookup"><span data-stu-id="71a98-134">Each port number must be associated with only one endpoint, and each endpoint is associated with a single server instance; thus, different server instances on the same server listen on different endpoints with different ports.</span></span> <span data-ttu-id="71a98-135">Daher leitet der Port, den Sie in der Endpunkt-URL beim Festlegen eines Verfügbarkeitsreplikat angeben, eingehende Meldungen immer an die Serverinstanz weiter, deren Endpunkt diesem Port zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="71a98-135">Therefore, the port you specify in the endpoint URL when you specify an availability replica will always direct incoming messages to the server instance whose endpoint is associated with that port.</span></span>  
  
     <span data-ttu-id="71a98-136">In der Endpunkt-URL identifiziert nur die Nummer des Ports die Serverinstanz, die dem Spiegelungsendpunkt auf dem Zielcomputer zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="71a98-136">IIn the endpoint URL, only the number of the port identifies the server instance that is associated with the mirroring endpoint on the target computer.</span></span> <span data-ttu-id="71a98-137">Die folgende Abbildung veranschaulicht die Endpunkt-URLS von zwei Serverinstanzen auf einem Computer.</span><span class="sxs-lookup"><span data-stu-id="71a98-137">The following figure illustrates the endpoint URLs of two server instances on a single computer.</span></span> <span data-ttu-id="71a98-138">In der Standardinstanz wird Port `7022` verwendet, und in der benannten Instanz wird Port `7033`verwendet.</span><span class="sxs-lookup"><span data-stu-id="71a98-138">The default instance uses port `7022` and the named instance uses port `7033`.</span></span> <span data-ttu-id="71a98-139">Die Endpunkt-URL für diese beiden Serverinstanzen lauten `TCP://MYSYSTEM.Adventure-works.MyDomain.com:7022` bzw. `TCP://MYSYSTEM.Adventure-works.MyDomain.com:7033`.</span><span class="sxs-lookup"><span data-stu-id="71a98-139">The endpoint URL for these two server instances are, respectively: `TCP://MYSYSTEM.Adventure-works.MyDomain.com:7022` and `TCP://MYSYSTEM.Adventure-works.MyDomain.com:7033`.</span></span> <span data-ttu-id="71a98-140">Beachten Sie, dass die Adresse nicht den Namen der Serverinstanz enthält.</span><span class="sxs-lookup"><span data-stu-id="71a98-140">Note that the address does not contain the name of the server instance.</span></span>  
  
     <span data-ttu-id="71a98-141">![Servernetzwerkadressen einer Standardinstanz](../../media/dbm-2-instances-ports-1-system.gif "Servernetzwerkadressen einer Standardinstanz")</span><span class="sxs-lookup"><span data-stu-id="71a98-141">![Server network addresses of a default instance](../../media/dbm-2-instances-ports-1-system.gif "Server network addresses of a default instance")</span></span>  
  
     <span data-ttu-id="71a98-142">Verwenden Sie die folgende [!INCLUDE[tsql](../../../includes/tsql-md.md)] -Anweisung, um den Port zu identifizieren, der derzeit dem Endpunkt der Datenbankspiegelung einer Serverinstanz zugeordnet ist:</span><span class="sxs-lookup"><span data-stu-id="71a98-142">To identify the port currently associated with database mirroring endpoint of a server instance, use the following [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement:</span></span>  
  
    ```sql
    SELECT type_desc, port FROM sys.TCP_endpoints  
    ```  
  
     <span data-ttu-id="71a98-143">Suchen Sie die Zeile, deren **type_desc** -Wert „DATABASE_MIRRORING“ lautet, und verwenden Sie die entsprechende Portnummer.</span><span class="sxs-lookup"><span data-stu-id="71a98-143">Find the row whose **type_desc** value is "DATABASE_MIRRORING," and use the corresponding port number.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="71a98-144">Beispiele</span><span class="sxs-lookup"><span data-stu-id="71a98-144">Examples</span></span>  
  
#### <a name="a-using-a-system-name"></a><span data-ttu-id="71a98-145">A.</span><span class="sxs-lookup"><span data-stu-id="71a98-145">A.</span></span> <span data-ttu-id="71a98-146">Verwenden eines Systemnamens</span><span class="sxs-lookup"><span data-stu-id="71a98-146">Using a system name</span></span>  
 <span data-ttu-id="71a98-147">Die folgende Endpunkt-URL gibt einen Systemnamen, `SYSTEM46`und Port `7022`an.</span><span class="sxs-lookup"><span data-stu-id="71a98-147">The following endpoint URL specifies a system name, `SYSTEM46`, and port `7022`.</span></span>  
  
 `TCP://SYSTEM46:7022`  
  
#### <a name="b-using-a-fully-qualified-domain-name"></a><span data-ttu-id="71a98-148">B.</span><span class="sxs-lookup"><span data-stu-id="71a98-148">B.</span></span> <span data-ttu-id="71a98-149">Verwenden eines vollqualifizierten Domänennamens</span><span class="sxs-lookup"><span data-stu-id="71a98-149">Using a fully qualified domain name</span></span>  
 <span data-ttu-id="71a98-150">Die folgende Endpunkt-URL gibt den vollqualifizierten Domänennamen `DBSERVER8.manufacturing.Adventure-Works.com`und Port `7024`an.</span><span class="sxs-lookup"><span data-stu-id="71a98-150">The following endpoint URL specifies a fully qualified domain name, `DBSERVER8.manufacturing.Adventure-Works.com`, and port `7024`.</span></span>  
  
 `TCP://DBSERVER8.manufacturing.Adventure-Works.com:7024`  
  
#### <a name="c-using-ipv4"></a><span data-ttu-id="71a98-151">C.</span><span class="sxs-lookup"><span data-stu-id="71a98-151">C.</span></span> <span data-ttu-id="71a98-152">Verwenden von IPv4</span><span class="sxs-lookup"><span data-stu-id="71a98-152">Using IPv4</span></span>  
 <span data-ttu-id="71a98-153">Die folgende Endpunkt-URL gibt die IPv4-Adresse `10.193.9.134`und Port `7023`an.</span><span class="sxs-lookup"><span data-stu-id="71a98-153">The following endpoint URL specifies an IPv4 address, `10.193.9.134`, and port `7023`.</span></span>  
  
 `TCP://10.193.9.134:7023`  
  
#### <a name="d-using-ipv6"></a><span data-ttu-id="71a98-154">D:</span><span class="sxs-lookup"><span data-stu-id="71a98-154">D.</span></span> <span data-ttu-id="71a98-155">Verwenden von IPv6</span><span class="sxs-lookup"><span data-stu-id="71a98-155">Using IPv6</span></span>  
 <span data-ttu-id="71a98-156">Die folgende Endpunkt-URL gibt die IPv6-Adresse `2001:4898:23:1002:20f:1fff:feff:b3a3`und Port `7022`an.</span><span class="sxs-lookup"><span data-stu-id="71a98-156">The following endpoint URL contains an IPv6 address, `2001:4898:23:1002:20f:1fff:feff:b3a3`, and port `7022`.</span></span>  
  
 `TCP://[2001:4898:23:1002:20f:1fff:feff:b3a3]:7022`  
  
##  <a name="finding-the-fully-qualified-domain-name-of-a-system"></a><a name="Finding_FQDN"></a> <span data-ttu-id="71a98-157">Ermitteln des vollqualifizierten Domänennamens eines Systems</span><span class="sxs-lookup"><span data-stu-id="71a98-157">Finding the Fully Qualified Domain Name of A System</span></span>  
 <span data-ttu-id="71a98-158">Um den vollqualifizierten Domänennamen eines Systems zu ermitteln, geben Sie an der Windows-Eingabeaufforderung des Systems den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="71a98-158">To find the fully qualified domain name of a system, at the Windows command prompt on that system, enter:</span></span>  
  
 <span data-ttu-id="71a98-159">**IPCONFIG /ALL**</span><span class="sxs-lookup"><span data-stu-id="71a98-159">**IPCONFIG /ALL**</span></span>  
  
 <span data-ttu-id="71a98-160">Wenn Sie den vollqualifizierten Domänennamen bilden möchten, verketten Sie die Werte von *<host_name>* bzw. *<Primary_Dns_Suffix>* wie folgt:</span><span class="sxs-lookup"><span data-stu-id="71a98-160">To form the fully qualified domain name, concatenate the values of *<host_name>* and *<Primary_Dns_Suffix>* as follows:</span></span>  
  
 <span data-ttu-id="71a98-161">_<host_name>_ **.**</span><span class="sxs-lookup"><span data-stu-id="71a98-161">_<host_name>_ **.**</span></span> <span data-ttu-id="71a98-162">_<Primary_Dns_Suffix>_</span><span class="sxs-lookup"><span data-stu-id="71a98-162">_<Primary_Dns_Suffix>_</span></span>  
  
 <span data-ttu-id="71a98-163">Beispielsweise entspricht die IP-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="71a98-163">For example, the IP configuration</span></span>  
  
 `Host Name  .  .  .  .  .  .  : MYSERVER`  
  
 `Primary Dns Suffix  .  .  .  : mydomain.Adventure-Works.com`  
  
 <span data-ttu-id="71a98-164">dem folgenden vollqualifizierten Domänennamen:</span><span class="sxs-lookup"><span data-stu-id="71a98-164">equates to the following fully qualified domain name:</span></span>  
  
 `MYSERVER.mydomain.Adventure-Works.com`  
  
> [!NOTE]  
>  <span data-ttu-id="71a98-165">Wenn Sie weitere Informationen zu einem vollqualifizierten Domänennamen benötigen, wenden Sie sich an den Systemadministrator.</span><span class="sxs-lookup"><span data-stu-id="71a98-165">If you need more information about a fully qualified domain name, see your system administrator.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="71a98-166">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="71a98-166">Related Tasks</span></span>  
 <span data-ttu-id="71a98-167">**So konfigurieren Sie einen Datenbankspiegelungs-Endpunkt**</span><span class="sxs-lookup"><span data-stu-id="71a98-167">**To Configure a Database Mirroring Endpoint**</span></span>  
  
-   [<span data-ttu-id="71a98-168">Erstellen Sie einen Datenbankspiegelungs-Endpunkt für AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="71a98-168">Create a Database Mirroring Endpoint for AlwaysOn Availability Groups &#40;SQL Server PowerShell&#41;</span></span>](database-mirroring-always-on-availability-groups-powershell.md)  
  
-   [<span data-ttu-id="71a98-169">Erstellen eines Endpunkts der Datenbankspiegelung für Windows-Authentifizierung &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="71a98-169">Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md)  
  
-   [<span data-ttu-id="71a98-170">Verwenden von Zertifikaten für einen Datenbankspiegelungs-Endpunkt &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="71a98-170">Use Certificates for a Database Mirroring Endpoint &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/use-certificates-for-a-database-mirroring-endpoint-transact-sql.md)  
  
    -   [<span data-ttu-id="71a98-171">Ermöglichen des Verwendens von Zertifikaten für ausgehende Verbindungen für einen Datenbankspiegelungs-Endpunkt &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="71a98-171">Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/database-mirroring-use-certificates-for-outbound-connections.md)  
  
    -   [<span data-ttu-id="71a98-172">Ermöglichen des Verwendens von Zertifikaten für eingehende Verbindungen für einen Datenbankspiegelungs-Endpunkt &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="71a98-172">Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/database-mirroring-use-certificates-for-inbound-connections.md)  
  
-   [<span data-ttu-id="71a98-173">Angeben einer Servernetzwerkadresse &#40;Datenbankspiegelung&#41;</span><span class="sxs-lookup"><span data-stu-id="71a98-173">Specify a Server Network Address &#40;Database Mirroring&#41;</span></span>](../../database-mirroring/specify-a-server-network-address-database-mirroring.md)  
  
-   [<span data-ttu-id="71a98-174">Problembehandlung AlwaysOn-Verfügbarkeitsgruppen Konfigurations &#40;SQL Server&#41;gelöscht</span><span class="sxs-lookup"><span data-stu-id="71a98-174">Troubleshoot AlwaysOn Availability Groups Configuration &#40;SQL Server&#41;deleted</span></span>](troubleshoot-always-on-availability-groups-configuration-sql-server.md)  
  
 <span data-ttu-id="71a98-175">**So zeigen Sie Informationen zum Datenbankspiegelungs-Endpunkt an**</span><span class="sxs-lookup"><span data-stu-id="71a98-175">**To View Information About the Database Mirroring Endpoint**</span></span>  
  
-   [<span data-ttu-id="71a98-176">sys.database_mirroring_endpoints &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="71a98-176">sys.database_mirroring_endpoints &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-mirroring-endpoints-transact-sql)  
  
 <span data-ttu-id="71a98-177">**So fügen Sie ein Verfügbarkeitsreplikat hinzu**</span><span class="sxs-lookup"><span data-stu-id="71a98-177">**To add an availability replica**</span></span>  
  
-   [<span data-ttu-id="71a98-178">Hinzufügen eines sekundären Replikats zu einer Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="71a98-178">Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](add-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="71a98-179">Verknüpfen eines sekundären Replikats mit einer Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="71a98-179">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="71a98-180">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="71a98-180">Related Content</span></span>  
  
-   [<span data-ttu-id="71a98-181">Microsoft SQL Server AlwaysOn-Lösungshandbuch zu hoher Verfügbarkeit und Notfallwiederherstellung</span><span class="sxs-lookup"><span data-stu-id="71a98-181">Microsoft SQL Server AlwaysOn Solutions Guide for High Availability and Disaster Recovery</span></span>](https://go.microsoft.com/fwlink/?LinkId=227600)  
  
## <a name="see-also"></a><span data-ttu-id="71a98-182">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="71a98-182">See Also</span></span>  
 <span data-ttu-id="71a98-183">[Erstellung und Konfiguration von Verfügbarkeitsgruppen &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="71a98-183">[Creation and Configuration of Availability Groups &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="71a98-184">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="71a98-184">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="71a98-185">CREATE ENDPOINT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="71a98-185">CREATE ENDPOINT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-endpoint-transact-sql)  
