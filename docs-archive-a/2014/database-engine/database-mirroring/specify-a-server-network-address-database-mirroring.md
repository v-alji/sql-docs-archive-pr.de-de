---
title: Angeben einer Servernetzwerkadresse (Datenbankspiegelung) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], deployment
- database mirroring [SQL Server], endpoint
- endpoints [SQL Server], database mirroring
- server network addresses [SQL Server]
ms.assetid: a64d4b6b-9016-4f1e-a310-b1df181dd0c6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5c7db7ee6d321229205248059ce09a86f1da101f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618880"
---
# <a name="specify-a-server-network-address-database-mirroring"></a><span data-ttu-id="45d24-102">Angeben einer Servernetzwerkadresse (Datenbankspiegelung)</span><span class="sxs-lookup"><span data-stu-id="45d24-102">Specify a Server Network Address (Database Mirroring)</span></span>
  <span data-ttu-id="45d24-103">Beim Einrichten einer Datenbank-Spiegelungssitzung ist für jede Serverinstanz eine Server-Netzwerkadresse erforderlich.</span><span class="sxs-lookup"><span data-stu-id="45d24-103">Setting up a database mirroring session requires a server network address for each of the server instances.</span></span> <span data-ttu-id="45d24-104">Die Server-Netzwerkadresse der Serverinstanz muss die Instanz eindeutig identifizieren, indem sie eine Systemadresse und die Nummer des Ports angibt, den die Instanz überwacht.</span><span class="sxs-lookup"><span data-stu-id="45d24-104">The server network address of a server instance must unambiguously identify the instance by providing a system address and the number of the port on which the instance is listening.</span></span>  
  
 <span data-ttu-id="45d24-105">Bevor Sie einen Port in einer Server-Netzwerkadresse angeben können, muss der Endpunkt der Datenbankspiegelung auf der Serverinstanz vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="45d24-105">Before you can specify a port in a server network address, the database mirroring endpoint must exist on the server instance.</span></span> <span data-ttu-id="45d24-106">Weitere Informationen finden Sie unter [Erstellen eines Endpunkts der Datenbankspiegelung für Windows-Authentifizierung &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="45d24-106">For more information, see [Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span></span>  
  
  
  
##  <a name="syntax-for-a-server-network-address"></a><a name="Syntax"></a> <span data-ttu-id="45d24-107">Syntax für eine Server-Netzwerkadresse</span><span class="sxs-lookup"><span data-stu-id="45d24-107">Syntax for a Server Network Address</span></span>  
 <span data-ttu-id="45d24-108">Die Syntax für eine Server-Netzwerkadresse lautet:</span><span class="sxs-lookup"><span data-stu-id="45d24-108">The syntax for a server network address is of the form:</span></span>  
  
 <span data-ttu-id="45d24-109">TCP<strong>://</strong> *\<system-address>* <strong> :<strong>*\<port>*</span><span class="sxs-lookup"><span data-stu-id="45d24-109">TCP<strong>://</strong>*\<system-address>*<strong>:<strong>*\<port>*</span></span> 
  
 <span data-ttu-id="45d24-110">Hierbei gilt:</span><span class="sxs-lookup"><span data-stu-id="45d24-110">where</span></span>  
  
-   <span data-ttu-id="45d24-111">*\<system-address>* ist eine Zeichenfolge, die das Zielcomputersystem eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="45d24-111">*\<system-address>* is a string that unambiguously identifies the destination computer system.</span></span> <span data-ttu-id="45d24-112">In der Regel handelt es sich bei der Serveradresse um einen Systemnamen (wenn sich die Systeme in derselben Domäne befinden), einen vollqualifizierten Domänennamen oder eine IP-Adresse:</span><span class="sxs-lookup"><span data-stu-id="45d24-112">Typically, the server address is a system name (if the systems are in the same domain), a fully qualified domain name, or an IP address:</span></span>  
  
    -   <span data-ttu-id="45d24-113">Befinden sich die Systeme in derselben Domäne, können Sie den Namen des Computersystems verwenden, z. B. `SYSTEM46`.</span><span class="sxs-lookup"><span data-stu-id="45d24-113">If the systems are the same domain, you can use the name of the computer system; for example, `SYSTEM46`.</span></span>  
  
    -   <span data-ttu-id="45d24-114">Wenn Sie eine IP-Adresse verwenden möchten, muss diese in Ihrer Umgebung eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="45d24-114">To use an IP address, it must be unique in your environment.</span></span> <span data-ttu-id="45d24-115">Wir empfehlen die Verwendung einer IP-Adresse nur, wenn diese statisch ist.</span><span class="sxs-lookup"><span data-stu-id="45d24-115">We recommend that you use an IP address only if it is static.</span></span> <span data-ttu-id="45d24-116">Die IP-Adresse kann im IPv4-Format (IP Version 4) oder im IPv6-Format (IP Version) vorliegen.</span><span class="sxs-lookup"><span data-stu-id="45d24-116">The IP address can be IP Version 4 (IPv4) or IP Version 6 (IPv6).</span></span> <span data-ttu-id="45d24-117">Eine IPv6-Adresse muss in eckige Klammern gesetzt werden, z.B. **[** _<IPv6-Adresse>_ **]** .</span><span class="sxs-lookup"><span data-stu-id="45d24-117">An IPv6 address must be enclosed within square brackets, for example: **[**_<IPv6_address>_**]**.</span></span>  
  
         <span data-ttu-id="45d24-118">Um die IP-Adresse eines Systems zu ermitteln, geben Sie an der Windows-Eingabeaufforderung den Befehl **ipconfig** ein.</span><span class="sxs-lookup"><span data-stu-id="45d24-118">To learn the IP address of a system, at the Windows command prompt, enter the **ipconfig** command.</span></span>  
  
    -   <span data-ttu-id="45d24-119">Der vollqualifizierte Domänenname funktioniert auf alle Fälle.</span><span class="sxs-lookup"><span data-stu-id="45d24-119">The fully qualified domain name is guaranteed to work.</span></span> <span data-ttu-id="45d24-120">Hierbei handelt es sich um eine lokal definierte Adresszeichenfolge, die an unterschiedlichen Stellen unterschiedliche Formen annimmt.</span><span class="sxs-lookup"><span data-stu-id="45d24-120">This is a locally defined address string that different forms in different places.</span></span> <span data-ttu-id="45d24-121">Häufig, jedoch nicht immer, ist ein vollqualifizierter Domänenname ein zusammengesetzter Name, der den Computernamen und eine Reihe von Domänensegmenten enthält, die durch Punkte voneinander getrennt sind, z. B.:</span><span class="sxs-lookup"><span data-stu-id="45d24-121">Often, but not always, a fully qualified domain name is a compound name that includes the computer name and a series of period-separated domain segments of the form:</span></span>  
  
         <span data-ttu-id="45d24-122">_Computername_ **.**</span><span class="sxs-lookup"><span data-stu-id="45d24-122">_computer_name_ **.**</span></span> <span data-ttu-id="45d24-123">_Domänensegment_[... **.** _Domänensegment_]</span><span class="sxs-lookup"><span data-stu-id="45d24-123">_domain_segment_[...**.**_domain_segment_]</span></span>  
  
         <span data-ttu-id="45d24-124">Dabei steht *Computername*für den Netzwerknamen des Computers, auf dem die Serverinstanz ausgeführt wird, und *Domänensegment*[... **.** _Domänensegment_] für die übrigen Domäneninformationen des Servers. Beispiel: `localinfo.corp.Adventure-Works.com`.</span><span class="sxs-lookup"><span data-stu-id="45d24-124">where *computer_name i*s the network name of the computer running the server instance, and *domain_segment*[...**.**_domain_segment_] is the remaining domain information of the server; for example: `localinfo.corp.Adventure-Works.com`.</span></span>  
  
         <span data-ttu-id="45d24-125">Inhalt und Anzahl von Domänenelementen werden innerhalb des Unternehmens oder der Organisation bestimmt.</span><span class="sxs-lookup"><span data-stu-id="45d24-125">The content and number of domain segments are determined within the company or organization.</span></span> <span data-ttu-id="45d24-126">Wenn Sie den vollqualifizierten Domänennamen des Servers nicht kennen, wenden Sie sich an den Systemadministrator.</span><span class="sxs-lookup"><span data-stu-id="45d24-126">If you do not know the fully qualified domain name for your server, see your system administrator.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="45d24-127">Informationen zum Ermitteln eines vollqualifizierten Domänennamens finden Sie nachfolgend in diesem Thema unter "Ermitteln des vollqualifizierten Domänennamens".</span><span class="sxs-lookup"><span data-stu-id="45d24-127">For information about how to find a fully qualified domain name, see "Finding the Fully Qualified Domain Name," later in this topic.</span></span>  
  
-   <span data-ttu-id="45d24-128">*\<port>* ist die Portnummer, die vom Spiegelungsendpunkt der Partnerserverinstanz verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="45d24-128">*\<port>* is the port number used by the mirroring endpoint of the partner server instance.</span></span> <span data-ttu-id="45d24-129">Weitere Informationen zum Angeben eines Endpunkts finden Sie unter [Erstellen eines Endpunkts der Datenbankspiegelung für Windows-Authentifizierung &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="45d24-129">For information about specifying an endpoint, see [Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span></span>  
  
     <span data-ttu-id="45d24-130">Ein Datenbankspiegelungs-Endpunkt kann jeden verfügbaren Port im Computersystem verwenden.</span><span class="sxs-lookup"><span data-stu-id="45d24-130">A database mirroring endpoint can use any available port on the computer system.</span></span> <span data-ttu-id="45d24-131">Jede Portnummer in einem Computersystem darf nur einem Endpunkt zugeordnet werden, und jeder Endpunkt ist einer einzelnen Serverinstanz zugeordnet. Daher lauschen unterschiedliche Serverinstanzen auf dem gleichen Server an unterschiedliche Endpunkten mit unterschiedlichen Ports.</span><span class="sxs-lookup"><span data-stu-id="45d24-131">Each port number on a computer system must be associated with only one endpoint, and each endpoint is associated with a single server instance; thus, different server instances on the same server listen on different endpoints with different ports.</span></span> <span data-ttu-id="45d24-132">Aus diesem Grund leitet der Port, den Sie beim Einrichten einer Datenbank-Spiegelungssitzung in der Server-Netzwerkadresse angeben, die Sitzung immer an die Serverinstanz weiter, deren Endpunkt dem jeweiligen Port zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="45d24-132">Therefore, the port you specify in the server network address when you set up a database mirroring session will always direct the session to the server instance whose endpoint is associated with that port.</span></span>  
  
     <span data-ttu-id="45d24-133">In der Server-Netzwerkadresse einer Serverinstanz unterscheidet nur die Nummer des Ports, die ihrem Spiegelungsendpunkt zugeordnet ist, diese Instanz von anderen Instanzen auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="45d24-133">In the server network address of a server instance, only the number of the port associated with its mirroring endpoint distinguishes that instance from any other instances on the computer.</span></span> <span data-ttu-id="45d24-134">Die folgende Abbildung veranschaulicht die Server-Netzwerkadresse von zwei Serverinstanzen auf einem Computer.</span><span class="sxs-lookup"><span data-stu-id="45d24-134">The following figure illustrates the server network addresses of two server instances on a single computer.</span></span> <span data-ttu-id="45d24-135">In der Standardinstanz wird Port `7022` verwendet, und in der benannten Instanz wird Port `7033`verwendet.</span><span class="sxs-lookup"><span data-stu-id="45d24-135">The default instance uses port `7022` and the named instance uses port `7033`.</span></span> <span data-ttu-id="45d24-136">Die Server-Netzwerkadressen für diese beiden Serverinstanzen lauten `TCP://MYSYSTEM.Adventure-works.MyDomain.com:7022` bzw. `TCP://MYSYSTEM.Adventure-works.MyDomain.com:7033`.</span><span class="sxs-lookup"><span data-stu-id="45d24-136">The server network address for these two server instances are, respectively: `TCP://MYSYSTEM.Adventure-works.MyDomain.com:7022` and `TCP://MYSYSTEM.Adventure-works.MyDomain.com:7033`.</span></span> <span data-ttu-id="45d24-137">Beachten Sie, dass die Adresse nicht den Namen der Serverinstanz enthält.</span><span class="sxs-lookup"><span data-stu-id="45d24-137">Note that the address does not contain the name of the server instance.</span></span>  
  
     <span data-ttu-id="45d24-138">![Servernetzwerkadressen einer Standardinstanz](../media/dbm-2-instances-ports-1-system.gif "Servernetzwerkadressen einer Standardinstanz")</span><span class="sxs-lookup"><span data-stu-id="45d24-138">![Server network addresses of a default instance](../media/dbm-2-instances-ports-1-system.gif "Server network addresses of a default instance")</span></span>  
  
     <span data-ttu-id="45d24-139">Verwenden Sie die folgende [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung, um den Port zu identifizieren, der derzeit dem Endpunkt der Datenbankspiegelung einer Serverinstanz zugeordnet ist:</span><span class="sxs-lookup"><span data-stu-id="45d24-139">To identify the port currently associated with database mirroring endpoint of a server instance, use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
    ```  
    SELECT type_desc, port FROM sys.tcp_endpoints  
    ```  
  
     <span data-ttu-id="45d24-140">Suchen Sie die Zeile, deren **type_desc** -Wert „DATABASE_MIRRORING“ lautet, und verwenden Sie die entsprechende Portnummer.</span><span class="sxs-lookup"><span data-stu-id="45d24-140">Find the row whose **type_desc** value is "DATABASE_MIRRORING," and use the corresponding port number.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="45d24-141">Beispiele</span><span class="sxs-lookup"><span data-stu-id="45d24-141">Examples</span></span>  
  
#### <a name="a-using-a-system-name"></a><span data-ttu-id="45d24-142">A.</span><span class="sxs-lookup"><span data-stu-id="45d24-142">A.</span></span> <span data-ttu-id="45d24-143">Verwenden eines Systemnamens</span><span class="sxs-lookup"><span data-stu-id="45d24-143">Using a system name</span></span>  
 <span data-ttu-id="45d24-144">Die folgende Server-Netzwerkadresse gibt den Systemnamen `SYSTEM46`und Port `7022`an.</span><span class="sxs-lookup"><span data-stu-id="45d24-144">The following server network address specifies a system name, `SYSTEM46`, and port `7022`.</span></span>  
  
```  
ALTER DATABASE AdventureWorks SET PARTNER ='tcp://SYSTEM46:7022';  
```  
  
#### <a name="b-using-a-fully-qualified-domain-name"></a><span data-ttu-id="45d24-145">B.</span><span class="sxs-lookup"><span data-stu-id="45d24-145">B.</span></span> <span data-ttu-id="45d24-146">Verwenden eines vollqualifizierten Domänennamens</span><span class="sxs-lookup"><span data-stu-id="45d24-146">Using a fully qualified domain name</span></span>  
 <span data-ttu-id="45d24-147">Die folgende Server-Netzwerkadresse gibt den vollqualifizierten Domänennamen `DBSERVER8.manufacturing.Adventure-Works.com`und Port `7024`an.</span><span class="sxs-lookup"><span data-stu-id="45d24-147">The following server network address specifies a fully qualified domain name, `DBSERVER8.manufacturing.Adventure-Works.com`, and port `7024`.</span></span>  
  
```  
ALTER DATABASE AdventureWorks SET PARTNER ='tcp://DBSERVER8.manufacturing.Adventure-Works.com:7024';  
```  
  
#### <a name="c-using-ipv4"></a><span data-ttu-id="45d24-148">C.</span><span class="sxs-lookup"><span data-stu-id="45d24-148">C.</span></span> <span data-ttu-id="45d24-149">Verwenden von IPv4</span><span class="sxs-lookup"><span data-stu-id="45d24-149">Using IPv4</span></span>  
 <span data-ttu-id="45d24-150">Die folgende Server-Netzwerkadresse gibt die IPv4-Adresse `10.193.9.134`und Port `7023`an.</span><span class="sxs-lookup"><span data-stu-id="45d24-150">The following server network address specifies an IPv4 address, `10.193.9.134`, and port `7023`.</span></span>  
  
```  
ALTER DATABASE AdventureWorks SET PARTNER ='tcp://10.193.9.134:7023';  
```  
  
#### <a name="d-using-ipv6"></a><span data-ttu-id="45d24-151">D:</span><span class="sxs-lookup"><span data-stu-id="45d24-151">D.</span></span> <span data-ttu-id="45d24-152">Verwenden von IPv6</span><span class="sxs-lookup"><span data-stu-id="45d24-152">Using IPv6</span></span>  
 <span data-ttu-id="45d24-153">Die folgende Server-Netzwerkadresse gibt die IPv6-Adresse `2001:4898:23:1002:20f:1fff:feff:b3a3`und Port `7022`an.</span><span class="sxs-lookup"><span data-stu-id="45d24-153">The following server network address contains an IPv6 address, `2001:4898:23:1002:20f:1fff:feff:b3a3`, and port `7022`.</span></span>  
  
```  
ALTER DATABASE AdventureWorks SET PARTNER ='tcp://[2001:4898:23:1002:20f:1fff:feff:b3a3]:7022';  
```  
  
## <a name="finding-the-fully-qualified-domain-name"></a><span data-ttu-id="45d24-154">Ermitteln des vollqualifizierten Domänennamens</span><span class="sxs-lookup"><span data-stu-id="45d24-154">Finding the Fully Qualified Domain Name</span></span>  
 <span data-ttu-id="45d24-155">Um den vollqualifizierten Domänennamen eines Systems zu ermitteln, geben Sie an der Windows-Eingabeaufforderung des Systems den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="45d24-155">To find the fully qualified domain name of a system, at the Windows command prompt on that system, enter:</span></span>  
  
 <span data-ttu-id="45d24-156">**IPCONFIG /ALL**</span><span class="sxs-lookup"><span data-stu-id="45d24-156">**IPCONFIG /ALL**</span></span>  
  
 <span data-ttu-id="45d24-157">Wenn Sie den vollqualifizierten Domänennamen bilden möchten, verketten Sie die Werte von *<host_name>* bzw. *<Primary_Dns_Suffix>* wie folgt:</span><span class="sxs-lookup"><span data-stu-id="45d24-157">To form the fully qualified domain name, concatenate the values of *<host_name>* and *<Primary_Dns_Suffix>* as follows:</span></span>  
  
 <span data-ttu-id="45d24-158">_<host_name>_ **.**</span><span class="sxs-lookup"><span data-stu-id="45d24-158">_<host_name>_ **.**</span></span> <span data-ttu-id="45d24-159">_<Primary_Dns_Suffix>_</span><span class="sxs-lookup"><span data-stu-id="45d24-159">_<Primary_Dns_Suffix>_</span></span>  
  
 <span data-ttu-id="45d24-160">Beispielsweise entspricht die IP-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="45d24-160">For example, the IP configuration</span></span>  
  
 `Host Name  .  .  .  .  .  .  : MYSERVER`  
  
 `Primary Dns Suffix  .  .  .  : mydomain.Adventure-Works.com`  
  
 <span data-ttu-id="45d24-161">dem folgenden vollqualifizierten Domänennamen:</span><span class="sxs-lookup"><span data-stu-id="45d24-161">equates to the following fully qualified domain name:</span></span>  
  
 `MYSERVER.mydomain.Adventure-Works.com`  
  
##  <a name="examples"></a><a name="Examples"></a> <span data-ttu-id="45d24-162">Beispiele</span><span class="sxs-lookup"><span data-stu-id="45d24-162">Examples</span></span>  
 <span data-ttu-id="45d24-163">Im folgenden Beispiel wird die Server-Netzwerkadresse für eine Serverinstanz auf einem Computersystem namens `REMOTESYSTEM3` in einer anderen Domäne dargestellt.</span><span class="sxs-lookup"><span data-stu-id="45d24-163">The following example shows the server network address for a server instance on a computer system named `REMOTESYSTEM3` in another domain.</span></span> <span data-ttu-id="45d24-164">Die Domäneninformationen lauten `NORTHWEST.ADVENTURE-WORKS.COM`, und der Port des Datenbank-Spiegelungsendpunkts ist `7025`.</span><span class="sxs-lookup"><span data-stu-id="45d24-164">The domain information is `NORTHWEST.ADVENTURE-WORKS.COM`, and the port of the database mirroring endpoint is `7025`.</span></span> <span data-ttu-id="45d24-165">Auf der Grundlage dieser Beispielkomponenten lautet die Server-Netzwerkadresse:</span><span class="sxs-lookup"><span data-stu-id="45d24-165">Given these example components, the server network address is.</span></span>  
  
 `TCP://REMOTESYSTEM3.NORTHWEST.ADVENTURE-WORKS.COM:7025`  
  
 <span data-ttu-id="45d24-166">Im folgenden Beispiel wird die Server-Netzwerkadresse für eine Serverinstanz auf einem Computersystem namens `DBSERVER1`dargestellt.</span><span class="sxs-lookup"><span data-stu-id="45d24-166">The following example shows the server network address for a server instance on a computer system named `DBSERVER1`.</span></span> <span data-ttu-id="45d24-167">Dieses System befindet sich in der lokalen Domäne und wird durch seinen Systemnamen eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="45d24-167">This system is in the local domain and is unambiguously identified by its system name.</span></span> <span data-ttu-id="45d24-168">Der Port des Datenbank-Spiegelungsendpunkts ist `7022`.</span><span class="sxs-lookup"><span data-stu-id="45d24-168">The port of the database mirroring endpoint is `7022`.</span></span>  
  
 `TCP://DBSERVER1:7022`  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="45d24-169">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="45d24-169">Related Tasks</span></span>  
  
-   [<span data-ttu-id="45d24-170">Erstellen eines Endpunkts der Datenbankspiegelung für Windows-Authentifizierung &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="45d24-170">Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;</span></span>](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="45d24-171">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="45d24-171">See Also</span></span>  
 <span data-ttu-id="45d24-172">[Datenbankspiegelung &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="45d24-172">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="45d24-173">Der Datenbankspiegelungs-Endpunkt &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="45d24-173">The Database Mirroring Endpoint &#40;SQL Server&#41;</span></span>](the-database-mirroring-endpoint-sql-server.md)  
  
  
