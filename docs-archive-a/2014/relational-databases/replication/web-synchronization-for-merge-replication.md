---
title: Websynchronisierung für die Mergereplikation | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- merge replication synchronization [SQL Server replication]
- Internet [SQL Server replication], synchronization
- synchronization [SQL Server replication], Web Synchronization
- Web publishing [SQL Server replication], synchronization
- Web synchronization, about
- Web synchronization
ms.assetid: 84785aba-b2c1-4821-9e9d-a363c73dcb37
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ef7bf5a6f77d593a90508a0b69d02f8c0db04407
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621471"
---
# <a name="web-synchronization-for-merge-replication"></a><span data-ttu-id="9baf6-102">Websynchronisierung für die Mergereplikation</span><span class="sxs-lookup"><span data-stu-id="9baf6-102">Web Synchronization for Merge Replication</span></span>
  <span data-ttu-id="9baf6-103">Durch die Websynchronisierung für die Mergereplikation können Sie Daten mithilfe des HTTPS-Protokolls replizieren. Sie ist für die folgenden Szenarien hilfreich:</span><span class="sxs-lookup"><span data-stu-id="9baf6-103">Web synchronization for merge replication lets you replicate data by using the HTTPS protocol, and is useful for the following scenarios:</span></span>

-   <span data-ttu-id="9baf6-104">Synchronisieren von Daten mobiler Benutzer über das Internet.</span><span class="sxs-lookup"><span data-stu-id="9baf6-104">Synchronizing data from mobile users over the Internet.</span></span>

-   <span data-ttu-id="9baf6-105">Synchronisieren von Daten zwischen [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datenbanken über eine Unternehmensfirewall hinweg.</span><span class="sxs-lookup"><span data-stu-id="9baf6-105">Synchronizing data between [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases across a corporate firewall.</span></span>

 <span data-ttu-id="9baf6-106">Ein Außendienstmitarbeiter kann z. B. die Websynchronisierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="9baf6-106">For example, a traveling sales representative can use Web synchronization.</span></span> <span data-ttu-id="9baf6-107">Einige Vertriebsmitarbeiter des Unternehmens, [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)], besuchen verschiedene Geschäfte und Lieferanten in ihren jeweiligen Regionen.</span><span class="sxs-lookup"><span data-stu-id="9baf6-107">The company, [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)], has sales representatives that travel to various stores and suppliers throughout their regions.</span></span> <span data-ttu-id="9baf6-108">Bei längeren Reisen übernachten die Mitarbeiter in Hotels und benötigen am Ende jeden Tages eine praktische Möglichkeit zum Hochladen der Verkaufsdaten und Herunterladen eventueller Produktupdates.</span><span class="sxs-lookup"><span data-stu-id="9baf6-108">On longer trips the representatives stay in hotels and need a convenient way to upload sales data and download any product updates at the end of each day.</span></span>

 <span data-ttu-id="9baf6-109">Die IT-Abteilung von [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] hat jeden Laptop mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] konfiguriert und die Mergereplikation für die Verwendung der Websynchronisierung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="9baf6-109">The [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] IT department has configured each portable computer with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and has enabled merge replication to use Web synchronization.</span></span> <span data-ttu-id="9baf6-110">Der Merge-Agent auf jedem Laptop verfügt über eine Internet-URL. Diese URL verweist auf die Replikationskomponenten, die auf einem Computer mit [!INCLUDE[msCoName](../../includes/msconame-md.md)] IIS (Internet Information Services) installiert sind.</span><span class="sxs-lookup"><span data-stu-id="9baf6-110">The Merge Agent on each portable computer has an Internet URL that points to the replication components that are installed on a computer that is running [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Information Services (IIS).</span></span> <span data-ttu-id="9baf6-111">Diese Komponenten synchronisieren den Abonnenten mit dem Verleger.</span><span class="sxs-lookup"><span data-stu-id="9baf6-111">These components synchronize the Subscriber with the Publisher.</span></span> <span data-ttu-id="9baf6-112">Jeder Mitarbeiter kann nun über jede verfügbare Internetverbindung ohne Verwendung einer Remote-DFÜ-Verbindung eine Verbindung herstellen und die entsprechenden Daten hoch- und herunterladen.</span><span class="sxs-lookup"><span data-stu-id="9baf6-112">Each representative can now connect through any available Internet connection without using a remote dial-up connection, and can upload and download the appropriate data.</span></span> <span data-ttu-id="9baf6-113">Die Internetverbindung verwendet SSL (Secure Sockets Layer). Somit ist kein virtuelles privates Netzwerk (VPN) erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9baf6-113">The Internet connection uses Secure Sockets Layer (SSL); therefore, a virtual private network (VPN) is not required.</span></span>

 <span data-ttu-id="9baf6-114">Informationen zum Konfigurieren der für die Websynchronisierung erforderlichen Komponenten finden Sie unter [Konfigurieren der Websynchronisierung](configure-web-synchronization.md), [Konfigurieren von IIS für die Websynchronisierung](configure-iis-for-web-synchronization.md) und[Konfigurieren von IIS 7 für die Websynchronisierung](configure-iis-7-for-web-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="9baf6-114">For information about how to configure the components that are required for Web synchronization, see [Configure Web Synchronization](configure-web-synchronization.md), [Configure IIS for Web Synchronization](configure-iis-for-web-synchronization.md), and [Configure IIS 7 for Web Synchronization](configure-iis-7-for-web-synchronization.md).</span></span>

> [!NOTE]
>  <span data-ttu-id="9baf6-115">Die Websynchronisierung ist für die Synchronisierung von Daten mit Laptops, Handhelds und anderen Clients entwickelt worden.</span><span class="sxs-lookup"><span data-stu-id="9baf6-115">Web synchronization is designed for synchronizing data with portable computers, handheld devices, and other clients.</span></span> <span data-ttu-id="9baf6-116">Sie eignet sich nicht für Server-zu-Server-Anwendungen für hohes Volumen.</span><span class="sxs-lookup"><span data-stu-id="9baf6-116">Web synchronization is not intended for high-volume server-to-server applications.</span></span>

## <a name="overview-of-how-web-synchronization-works"></a><span data-ttu-id="9baf6-117">Funktionsweise der Websynchronisierung (Übersicht)</span><span class="sxs-lookup"><span data-stu-id="9baf6-117">Overview of How Web Synchronization Works</span></span>
 <span data-ttu-id="9baf6-118">Wenn die Websynchronisierung verwendet wird, werden Updates auf dem Abonnenten verpackt und als XML-Nachricht mit dem HTTPS-Protokoll an den Computer mit IIS gesendet.</span><span class="sxs-lookup"><span data-stu-id="9baf6-118">When Web synchronization is used, updates at the Subscriber are packaged and sent as an XML message to the computer that is running IIS by using the HTTPS protocol.</span></span> <span data-ttu-id="9baf6-119">Der Computer mit IIS sendet dann die Befehle in einem Binärformat (in der Regel mit TCP/IP) an den Verleger.</span><span class="sxs-lookup"><span data-stu-id="9baf6-119">The computer that is running IIS then sends the commands to the Publisher in a binary format, typically by using TCP/IP.</span></span> <span data-ttu-id="9baf6-120">Updates auf dem Verleger werden an den Computer mit IIS gesendet und dann als XML-Nachricht zur Übermittlung an den Abonnenten verpackt.</span><span class="sxs-lookup"><span data-stu-id="9baf6-120">Updates at the Publisher are sent to the computer that is running IIS and then packaged as an XML message for delivery to the Subscriber.</span></span>

 <span data-ttu-id="9baf6-121">Die folgende Abbildung zeigt einige Komponenten der Websynchronisierung für die Mergereplikation.</span><span class="sxs-lookup"><span data-stu-id="9baf6-121">The following illustration shows some of the components that are involved in Web synchronization for merge replication.</span></span>

 <span data-ttu-id="9baf6-122">![Komponenten und Datenfluss für die Websynchronisierung](media/web-sync01.gif "Komponenten und Datenfluss für die Websynchronisierung")</span><span class="sxs-lookup"><span data-stu-id="9baf6-122">![Web synchronization components and data flow](media/web-sync01.gif "Web synchronization components and data flow")</span></span>

 <span data-ttu-id="9baf6-123">Die Websynchronisierung steht nur für Pullabonnements zur Verfügung. Ein Merge-Agent wird deshalb immer auf dem Abonnenten ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9baf6-123">Web synchronization is an option only for pull subscriptions; therefore, a Merge Agent will always run on the Subscriber.</span></span> <span data-ttu-id="9baf6-124">Dabei kann es sich um den Standard-Merge-Agent, das ActiveX-Steuerelement für den Merge-Agent oder eine Anwendung handeln, die die Synchronisierung über Replikationsverwaltungsobjekte (RMO) bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="9baf6-124">This Merge Agent can be the standard Merge Agent, the Merge Agent ActiveX control, or an application that provides synchronization through Replication Management Objects (RMO).</span></span> <span data-ttu-id="9baf6-125">Verwenden Sie zum Angeben des Speicher Orts des Computers, auf dem IIS ausgeführt wird, den **-internetturl-** Parameter für die Merge-Agent.</span><span class="sxs-lookup"><span data-stu-id="9baf6-125">To specify the location of the computer that is running IIS, use the **-InternetUrl** parameter for the Merge Agent.</span></span>

 <span data-ttu-id="9baf6-126">Die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Replikationsüberwachung (Replisapi.dll) ist auf dem Computer mit IIS konfiguriert und verarbeitet die Nachrichten, die vom Verleger und den Abonnenten an den Server gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="9baf6-126">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Replication Listener (Replisapi.dll) is configured on the computer that is running IIS and is responsible for handling messages that are sent to the server from the Publisher and Subscribers.</span></span> <span data-ttu-id="9baf6-127">Jeder Knoten in der Topologie verarbeitet den XML-Datenstrom mithilfe der SQL Server-Mergereplikationssynchronisierung (Replrec.dll).</span><span class="sxs-lookup"><span data-stu-id="9baf6-127">Each node in the topology handles the XML data stream by using the Merge Replication Reconciler (Replrec.dll).</span></span>

 <span data-ttu-id="9baf6-128">Für alle Computer, die an einer Websynchronisierung teilnehmen, ist[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] oder eine höhere Version erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9baf6-128">[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or a later version is required for all computers that participate in Web synchronization.</span></span>

### <a name="synchronization-process"></a><span data-ttu-id="9baf6-129">Synchronisierungsvorgang</span><span class="sxs-lookup"><span data-stu-id="9baf6-129">Synchronization Process</span></span>
 <span data-ttu-id="9baf6-130">Die folgenden Schritte erfolgen bei der Synchronisierung:</span><span class="sxs-lookup"><span data-stu-id="9baf6-130">The following steps occur during synchronization:</span></span>

1.  <span data-ttu-id="9baf6-131">Der Merge-Agent wird auf dem Abonnenten gestartet.</span><span class="sxs-lookup"><span data-stu-id="9baf6-131">The Merge Agent is started at the Subscriber.</span></span> <span data-ttu-id="9baf6-132">Dieser Agent führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="9baf6-132">The agent does the following:</span></span>

    1.  <span data-ttu-id="9baf6-133">Herstellen einer SQL-Verbindung zur Abonnementdatenbank.</span><span class="sxs-lookup"><span data-stu-id="9baf6-133">Makes an SQL connection to the subscription database.</span></span>

    2.  <span data-ttu-id="9baf6-134">Extrahieren von Änderungen aus der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="9baf6-134">Extracts any changes from the database.</span></span>

    3.  <span data-ttu-id="9baf6-135">Ausführen einer HTTPS-Anforderung an den Computer mit IIS.</span><span class="sxs-lookup"><span data-stu-id="9baf6-135">Makes an HTTPS request to the computer that is running IIS.</span></span>

    4.  <span data-ttu-id="9baf6-136">Hochladen von Datenänderungen als XML-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="9baf6-136">Uploads data changes as an XML message.</span></span>

2.  <span data-ttu-id="9baf6-137">Die Komponenten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Replikationsüberwachung und -Mergereplikationssynchronisierung, die auf dem Computer mit IIS gehostet werden, führen die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="9baf6-137">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Replication Listener and Merge Replication Reconciler that are hosted on the computer that is running IIS do the following:</span></span>

    1.  <span data-ttu-id="9baf6-138">Antworten auf die HTTPS-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="9baf6-138">Respond to the HTTPS request.</span></span>

    2.  <span data-ttu-id="9baf6-139">Herstellen einer SQL-Verbindung zur Veröffentlichungsdatenbank.</span><span class="sxs-lookup"><span data-stu-id="9baf6-139">Make an SQL connection to the publication database.</span></span>

    3.  <span data-ttu-id="9baf6-140">Anwenden der Uploadänderungen auf die Veröffentlichungsdatenbank.</span><span class="sxs-lookup"><span data-stu-id="9baf6-140">Apply the upload changes to the publication database.</span></span>

    4.  <span data-ttu-id="9baf6-141">Extrahieren der Downloadänderungen für den Abonnenten.</span><span class="sxs-lookup"><span data-stu-id="9baf6-141">Extract the download changes for the Subscriber.</span></span>

    5.  <span data-ttu-id="9baf6-142">Zurücksenden einer HTTPS-Antwort an den Merge-Agent.</span><span class="sxs-lookup"><span data-stu-id="9baf6-142">Send an HTTPS response back to the Merge Agent.</span></span>

3.  <span data-ttu-id="9baf6-143">Der Merge-Agent auf dem Abonnenten akzeptiert anschließend die HTTPS-Antwort und wendet die Downloadänderungen auf die Abonnementdatenbank an.</span><span class="sxs-lookup"><span data-stu-id="9baf6-143">The Merge Agent at the Subscriber then accepts the HTTPS response and applies the download changes to the subscription database.</span></span>

## <a name="see-also"></a><span data-ttu-id="9baf6-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9baf6-144">See Also</span></span>
 <span data-ttu-id="9baf6-145">[Websynchronisierungstopologien](configure-web-synchronization.md) [für die Websynchronisierung](topologies-for-web-synchronization.md) konfigurieren</span><span class="sxs-lookup"><span data-stu-id="9baf6-145">[Configure Web Synchronization](configure-web-synchronization.md) [Topologies for Web Synchronization](topologies-for-web-synchronization.md)</span></span>


