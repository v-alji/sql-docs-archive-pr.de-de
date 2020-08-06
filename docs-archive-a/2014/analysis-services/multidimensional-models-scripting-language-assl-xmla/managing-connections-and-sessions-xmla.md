---
title: Verwalten von Verbindungen und Sitzungen (XMLA) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- statefulness [XML for Analysis]
- statelessness [XML for Analysis]
- XML for Analysis, sessions
- states [XML for Analysis]
- XMLA, sessions
- sessions [XML for Analysis]
ms.assetid: b83bb3ff-09be-4fda-9d1d-6248e04ffb21
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7bfe876f6874193fd0885f16d91caa9f6fe8b172
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616768"
---
# <a name="managing-connections-and-sessions-xmla"></a><span data-ttu-id="69d6b-102">Verwalten von Verbindungen und Sitzungen (XMLA)</span><span class="sxs-lookup"><span data-stu-id="69d6b-102">Managing Connections and Sessions (XMLA)</span></span>
  <span data-ttu-id="69d6b-103">*Status* Behaftung ist eine Bedingung, bei der der Server die Identität und den Kontext eines Clients zwischen Methoden aufrufen beibehält.</span><span class="sxs-lookup"><span data-stu-id="69d6b-103">*Statefulness* is a condition during which the server preserves the identity and context of a client between method calls.</span></span> <span data-ttu-id="69d6b-104">Die *Status losigkeit* ist eine Bedingung, bei der der Server die Identität und den Kontext eines Clients nicht speichert, nachdem ein Methoden aufrufwerk abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="69d6b-104">*Statelessness* is a condition during which the server does not remember the identity and context of a client after a method call finishes.</span></span>  
  
 <span data-ttu-id="69d6b-105">Zum Bereitstellen von Status Behaftung werden von XML for Analysis (XMLA) *Sitzungen* unterstützt, mit denen eine Reihe von Anweisungen gleichzeitig ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="69d6b-105">To provide statefulness, XML for Analysis (XMLA) supports *sessions* that allow a series of statements to be performed together.</span></span> <span data-ttu-id="69d6b-106">Ein Beispiel einer solchen Reihe von Anweisungen ist die Erstellung eines berechneten Elements, das in nachfolgenden Abfragen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="69d6b-106">An example of such a series of statements would be the creation of a calculated member that is to be used in subsequent queries.</span></span>  
  
 <span data-ttu-id="69d6b-107">Im Allgemeinen folgen Sitzungen in XMLA dem folgenden Verhalten gemäß der Spezifikation OLE DB 2.6:</span><span class="sxs-lookup"><span data-stu-id="69d6b-107">In general, sessions in XMLA follow the following behavior outlined by the OLE DB 2.6 specification:</span></span>  
  
-   <span data-ttu-id="69d6b-108">Sitzungen definieren Transaktion und Befehlskontextbereich.</span><span class="sxs-lookup"><span data-stu-id="69d6b-108">Sessions define transaction and command context scope.</span></span>  
  
-   <span data-ttu-id="69d6b-109">Mehrere Befehle können im Kontext einer einzelnen Sitzung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="69d6b-109">Multiple commands can be run in the context of a single session.</span></span>  
  
-   <span data-ttu-id="69d6b-110">Die Unterstützung für Transaktionen im XMLA-Kontext erfolgt über anbieterspezifische Befehle, die mit der [Execute](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) -Methode gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="69d6b-110">Support for transactions in the XMLA context is through provider-specific commands sent with the [Execute](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) method.</span></span>  
  
 <span data-ttu-id="69d6b-111">XMLA definiert eine Möglichkeit zur Unterstützung von Sitzungen in einer Webumgebung, deren Modus Ähnlichkeit hat mit dem Zugang, der von dem DAV-Protokoll (Distributed Authoring and Versioning) für die Implementierung von Sperrungen in einer lose verbundenen Umgebung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="69d6b-111">XMLA defines a way to support sessions in a Web environment in a mode similar to the approach used by the Distributed Authoring and Versioning (DAV) protocol to implement locking in a loosely coupled environment.</span></span> <span data-ttu-id="69d6b-112">Diese Implementierung entspricht DAV insofern, als der Anbieter die Möglichkeit hat, Sitzungen aus mehreren Gründen ablaufen zu lassen (beispielsweise bei Timeout oder Verbindungsfehlern).</span><span class="sxs-lookup"><span data-stu-id="69d6b-112">This implementation parallels DAV in that the provider is allowed to expire sessions for various reasons (for example, a timeout or connection error).</span></span> <span data-ttu-id="69d6b-113">Wenn Sitzungen unterstützt werden, müssen Webdienste in der Lage sein, unterbrochene Befehlssätze, die neu gestartet werden müssen, zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="69d6b-113">When sessions are supported, Web services must be aware and ready to handle interrupted sets of commands that must be restarted.</span></span>  
  
 <span data-ttu-id="69d6b-114">Die Spezifikation des Simple Object Access Protocol (SOAP) des World Wide Web Consortium (W3C) empfiehlt die Verwendung von SOAP-Headern für die Erstellung von neuen Protokollen auf der Grundlage von SOAP-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="69d6b-114">The World Wide Web Consortium (W3C) Simple Object Access Protocol (SOAP) specification recommends using SOAP headers for building up new protocols on top of SOAP messages.</span></span> <span data-ttu-id="69d6b-115">In der folgenden Tabelle werden die SOAP-Headerelemente und -attribute aufgeführt, die XMLA für die Initiierung, Erhaltung und Beendigung von Sitzungen definiert.</span><span class="sxs-lookup"><span data-stu-id="69d6b-115">The following table lists the SOAP header elements and attributes that XMLA defines for initiating, maintaining, and closing a session.</span></span>  
  
|<span data-ttu-id="69d6b-116">SOAP-Header</span><span class="sxs-lookup"><span data-stu-id="69d6b-116">SOAP header</span></span>|<span data-ttu-id="69d6b-117">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="69d6b-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="69d6b-118">BeginSession</span><span class="sxs-lookup"><span data-stu-id="69d6b-118">BeginSession</span></span>|<span data-ttu-id="69d6b-119">Dieser Header fordert bei dem Anbieter die Erstellung einer neuen Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="69d6b-119">This header requests the provider to create a new session.</span></span> <span data-ttu-id="69d6b-120">Der Anbieter sollte mit der Erstellung einer neuen Sitzung antworten und die Sitzungs-ID als Teil des Sitzungsheaders in der SOAP-Antwort zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="69d6b-120">The provider should respond by constructing a new session and returning the session ID as part of the Session header in the SOAP response.</span></span>|  
|<span data-ttu-id="69d6b-121">SessionID</span><span class="sxs-lookup"><span data-stu-id="69d6b-121">SessionId</span></span>|<span data-ttu-id="69d6b-122">Der Wertbereich enthält die Sitzungs-ID, die für den Rest der Sitzung in jedem Methodenaufruf verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="69d6b-122">The value area contains the session ID that must be used in each method call for the rest of the session.</span></span> <span data-ttu-id="69d6b-123">Der Anbieter sendet dieses Tag in der SOAP-Antwort, und der Client muss dieses Attribut ebenfalls mit jedem Sitzungsheaderelement senden.</span><span class="sxs-lookup"><span data-stu-id="69d6b-123">The provider in the SOAP response sends this tag and the client must also send this attribute with each Session header element.</span></span>|  
|<span data-ttu-id="69d6b-124">Sitzung</span><span class="sxs-lookup"><span data-stu-id="69d6b-124">Session</span></span>|<span data-ttu-id="69d6b-125">Dieser Header muss für jeden Methodenaufruf in der Sitzung verwendet werden, und die Sitzungs-ID muss im Wertbereich des Headers enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="69d6b-125">For every method call that occurs in the session, this header must be used, and the session ID must be included in the value area of the header.</span></span>|  
|<span data-ttu-id="69d6b-126">EndSession</span><span class="sxs-lookup"><span data-stu-id="69d6b-126">EndSession</span></span>|<span data-ttu-id="69d6b-127">Verwenden Sie diesen Header, um die Sitzung zu beenden.</span><span class="sxs-lookup"><span data-stu-id="69d6b-127">To terminate the session, use this header.</span></span> <span data-ttu-id="69d6b-128">Die Sitzungs-ID muss im Wertbereich enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="69d6b-128">The session ID must be included with the value area.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="69d6b-129">Eine Sitzungs-ID garantiert nicht, dass eine Sitzung gültig bleibt.</span><span class="sxs-lookup"><span data-stu-id="69d6b-129">A session ID does not guarantee that a session stays valid.</span></span> <span data-ttu-id="69d6b-130">Wenn eine Sitzung abläuft (beispielsweise bei einem Timeout oder wenn die Verbindung verloren geht), kann der Anbieter die Aktionen der Sitzung beenden und rückgängig machen.</span><span class="sxs-lookup"><span data-stu-id="69d6b-130">If the session expires (for example, if it times out or the connection is lost), the provider can choose to end and roll back that session's actions.</span></span> <span data-ttu-id="69d6b-131">Als Ergebnis führen alle nachfolgenden Methodenaufrufe des Clients mit der Sitzungs-ID zu einem Fehler, der angibt, dass die Sitzung ungültig ist.</span><span class="sxs-lookup"><span data-stu-id="69d6b-131">As a result, all subsequent method calls from the client on a session ID fail with an error signaling a session that is not valid.</span></span> <span data-ttu-id="69d6b-132">Ein Client sollte diese Bedingung handhaben können und in der Lage sein, die Methodenaufrufe der Sitzung von Anfang an erneut zu senden.</span><span class="sxs-lookup"><span data-stu-id="69d6b-132">A client should handle this condition and be prepared to resend the session method calls from the beginning.</span></span>  
  
## <a name="legacy-code-example"></a><span data-ttu-id="69d6b-133">Legacycodebeispiel</span><span class="sxs-lookup"><span data-stu-id="69d6b-133">Legacy Code Example</span></span>  
 <span data-ttu-id="69d6b-134">Im folgenden Beispiel wird gezeigt, wie Sitzungen unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="69d6b-134">The following example shows how sessions are supported.</span></span>  
  
1.  <span data-ttu-id="69d6b-135">Fügen Sie dem ausgehenden XMLA-Methodenaufruf des Clients einen BeginSession-Header in SOAP hinzu, um eine Sitzung zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="69d6b-135">To begin the session, add a BeginSession header in SOAP to the outbound XMLA method call from the client.</span></span> <span data-ttu-id="69d6b-136">Der Wertbereich ist zunächst leer, da die Sitzungs-ID noch nicht bekannt ist.</span><span class="sxs-lookup"><span data-stu-id="69d6b-136">The value area is initially blank because the session ID is not yet known.</span></span>  
  
    ```  
    <SOAP-ENV:Envelope  
       xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"  
       SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/">  
       <SOAP-ENV:Header>  
          <XA:BeginSession  
             xmlns:XA="urn:schemas-microsoft-com:xml-analysis"  
             xsi:type="xsd:int"  
             mustUnderstand="1"/>  
       </SOAP-ENV:Header>  
       <SOAP-ENV:Body>  
          ...<!-- Discover or Execute call goes here.-->  
       </SOAP-ENV:Body>  
    </SOAP-ENV:Envelope>  
    ```  
  
2.  <span data-ttu-id="69d6b-137">Die SOAP-Antwortnachricht vom Anbieter enthält die Sitzungs-ID im Rückgabe Header Bereich mithilfe des XMLA-Header Tags \<SessionId> .</span><span class="sxs-lookup"><span data-stu-id="69d6b-137">The SOAP response message from the provider includes the session ID in the return header area, using the XMLA header tag \<SessionId>.</span></span>  
  
    ```  
    <SOAP-ENV:Header>  
       <XA:Session  
          xmlns:XA="urn:schemas-microsoft-com:xml-analysis"  
          SessionId="581"/>  
    </SOAP-ENV:Header>  
    ```  
  
3.  <span data-ttu-id="69d6b-138">Für jeden Methodenaufruf in der Sitzung muss der Sitzungsheader hinzugefügt werden, der die vom Anbieter zurückgegebene Sitzungs-ID enthält.</span><span class="sxs-lookup"><span data-stu-id="69d6b-138">For each method call in the session, the Session header must be added, containing the session ID returned from the provider.</span></span>  
  
    ```  
    <SOAP-ENV:Header>  
       <XA:Session  
          xmlns:XA="urn:schemas-microsoft-com:xml-analysis"  
          mustUnderstand="1"  
          SessionId="581"/>  
    </SOAP-ENV:Header>  
    ```  
  
4.  <span data-ttu-id="69d6b-139">Wenn die Sitzung beendet ist, wird das- \<EndSession> Tag verwendet, das den zugehörigen Sitzungs-ID-Wert enthält.</span><span class="sxs-lookup"><span data-stu-id="69d6b-139">When the session is complete, the \<EndSession> tag is used, containing the related session ID value.</span></span>  
  
    ```  
    <SOAP-ENV:Header>  
       <XA:EndSession  
          xmlns:XA="urn:schemas-microsoft-com:xml-analysis"  
          xsi:type="xsd:int"  
          mustUnderstand="1"  
          SessionId="581"/>  
    </SOAP-ENV:Header>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="69d6b-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="69d6b-140">See Also</span></span>  
 [<span data-ttu-id="69d6b-141">Entwickeln mit XMLA in Analysis Services</span><span class="sxs-lookup"><span data-stu-id="69d6b-141">Developing with XMLA in Analysis Services</span></span>](developing-with-xmla-in-analysis-services.md)  
  
  
