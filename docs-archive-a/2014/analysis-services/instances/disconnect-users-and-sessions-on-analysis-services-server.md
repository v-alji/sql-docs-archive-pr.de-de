---
title: Trennen von Benutzern und Sitzungen auf Analysis Services Server | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- ending user activity [Analysis Services]
- connections [Analysis Services]
- sessions [Analysis Services]
ms.assetid: 3b0145a2-f21d-4dd0-a09e-83afeb2ff4a9
author: minewiskan
ms.author: owend
ms.openlocfilehash: bac20b663b0a65902c70e7a3c3bfe3f27b7bf061
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698792"
---
# <a name="disconnect-users-and-sessions-on-analysis-services-server"></a><span data-ttu-id="796a3-102">Trennen von Benutzern und Sitzungen auf Analysis Services-Server</span><span class="sxs-lookup"><span data-stu-id="796a3-102">Disconnect Users and Sessions on Analysis Services Server</span></span>
  <span data-ttu-id="796a3-103">Ein Administrator von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] kann die Benutzeraktivität als Teil der Arbeitsauslastungsverwaltung beenden.</span><span class="sxs-lookup"><span data-stu-id="796a3-103">An administrator of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] may want to end user activity as part of workload management.</span></span> <span data-ttu-id="796a3-104">Hierzu werden Sitzungen und Verbindungen abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="796a3-104">You do this by canceling sessions and connections.</span></span> <span data-ttu-id="796a3-105">Sitzungen können automatisch (implizit) erstellt werden, wenn eine Abfrage ausgeführt wird, oder sie können (explizit) durch den Administrator erstellt und dabei benannt werden.</span><span class="sxs-lookup"><span data-stu-id="796a3-105">Sessions can be formed automatically when a query is run (implicit), or named at the time of creation by the administrator (explicit).</span></span> <span data-ttu-id="796a3-106">Bei Verbindungen handelt es sich um flexible Datenleitungen, über die Abfragen ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="796a3-106">Connections are open conduits over which queries can be run.</span></span> <span data-ttu-id="796a3-107">Sowohl Sitzungen als auch Verbindungen können beendet werden, während sie aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="796a3-107">Both sessions and connections can be ended while they are active.</span></span> <span data-ttu-id="796a3-108">Ein Administrator möchte z. B. die Verarbeitung einer Sitzung beenden, wenn diese zu lange dauert, oder wenn Zweifel bestehen, dass der ausgeführte Befehl richtig geschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="796a3-108">For example, an administrator may want to end processing for a session if the processing is taking too long or if some doubt has arisen as to whether the command being executed was written correctly.</span></span>  
  
## <a name="ending-sessions-and-connections"></a><span data-ttu-id="796a3-109">Beenden von Sitzungen und Verbindungen</span><span class="sxs-lookup"><span data-stu-id="796a3-109">Ending Sessions and Connections</span></span>  
 <span data-ttu-id="796a3-110">Sitzungen und Verbindungen können mithilfe von dynamischen Verwaltungssichten (DMVs) und XMLA verwaltet werden:</span><span class="sxs-lookup"><span data-stu-id="796a3-110">To manage sessions and connections, you can use Dynamic Management Views (DMVs) and XMLA:</span></span>  
  
1.  <span data-ttu-id="796a3-111">Stellen Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]eine Verbindung mit einer Analysis Services-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="796a3-111">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to an Analysis Services instance.</span></span>  
  
2.  <span data-ttu-id="796a3-112">Fügen Sie eine der folgenden DMV-Abfragen in ein MDX-Abfragefenster ein, um eine Liste aller momentan ausgeführten Sitzungen, Verbindungen und Befehle anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="796a3-112">Paste any one of the following DMV queries in an MDX query window to get a list of all sessions, connections, and commands that are currently executing:</span></span>  
  
     `Select * from $System.Discover_Sessions`  
  
     `Select * from $System.Discover_Connections`  
  
     `Select * from $System.Discover_Commands`  
  
3.  <span data-ttu-id="796a3-113">Drücken Sie F5, um die Abfrage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="796a3-113">Press F5 to execute the query.</span></span>  
  
     <span data-ttu-id="796a3-114">Die DMV-Abfrage gibt Sitzungs- und Verbindungsinformationen in einem tabellarischen Resultset zurück, das einfacher zu lesen und zu kopieren ist.</span><span class="sxs-lookup"><span data-stu-id="796a3-114">The DMV query returns session and connection information in a tabular result set that is easier read and copy from.</span></span>  
  
 <span data-ttu-id="796a3-115">Lassen Sie das Abfragefenster geöffnet.</span><span class="sxs-lookup"><span data-stu-id="796a3-115">Keep the query window open.</span></span> <span data-ttu-id="796a3-116">Im nächsten Schritt möchten Sie zu dieser Seite zurückkehren, um die SPIDs der Sitzung, die getrennt werden soll, zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="796a3-116">In the next step, you will want to return to this page to copy the SPIDs of the session you want to disconnect.</span></span>  
  
 <span data-ttu-id="796a3-117">Öffnen Sie zum Beenden einer Sitzung ein zweites XMLA-Abfragefenster.</span><span class="sxs-lookup"><span data-stu-id="796a3-117">To end a session, open a second XMLA query window.</span></span>  
  
1.  <span data-ttu-id="796a3-118">Fügen Sie die folgende Syntax in ein MDX-Abfragefenster ein, und ersetzen Sie dabei den ConnectionID-, SessionID- oder den SPID-Platzhalter durch einen gültigen Wert, den Sie im vorherigen Schritt kopiert haben.</span><span class="sxs-lookup"><span data-stu-id="796a3-118">Paste the following syntax into an MDX query window, replacing the ConnectionID, SessionID, or SPID placeholder with a valid value copied from the previous step.</span></span>  
  
    ```  
    <Cancel xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
  
       <ConnectionID>111</ConnectionID>  
       <SessionID>222</SessionID>  
       <SPID>333</SPID>  
  
    <CancelAssociated>1</CancelAssociated>  
    </Cancel>  
  
    ```  
  
2.  <span data-ttu-id="796a3-119">Drücken Sie F5, um den cancel-Befehl auszuführen.</span><span class="sxs-lookup"><span data-stu-id="796a3-119">Press F5 to execute the cancel command.</span></span>  
  
 <span data-ttu-id="796a3-120">Beim Beenden einer Verbindung werden alle Sitzungen und SPIDs abgebrochen und somit die Hostsitzung geschlossen.</span><span class="sxs-lookup"><span data-stu-id="796a3-120">Ending a connection cancels all sessions and SPIDs, closing the host session.</span></span>  
  
 <span data-ttu-id="796a3-121">Beim Beenden einer Sitzung werden alle Befehle (SPIDs), die als Teil dieser Sitzung ausgeführt werden, beendet.</span><span class="sxs-lookup"><span data-stu-id="796a3-121">Ending a session stops all commands (SPIDs) that are running as part of that session.</span></span>  
  
 <span data-ttu-id="796a3-122">Beim Beenden einer SPID wird ein bestimmter Befehl abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="796a3-122">Ending a SPID cancels a particular commend.</span></span>  
  
 <span data-ttu-id="796a3-123">In seltenen Fällen wird in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] eine Verbindung nicht geschlossen, wenn nicht alle mit der Verbindung verknüpften Sitzungen und SPIDs nachverfolgt werden können, z.B. wenn mehrere Sitzungen in einem HTTP-Szenario geöffnet sind.</span><span class="sxs-lookup"><span data-stu-id="796a3-123">In rare cases, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will not close a connection if it cannot track all the sessions and SPIDs associated with the connection (for example, when multiple sessions are open in an HTTP scenario).</span></span>  
  
 <span data-ttu-id="796a3-124">Weitere Informationen zu XMLA, auf die in diesem Thema verwiesen wird, finden Sie unter [Execute-Methode &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) und [Cancel-Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/cancel-element-xmla).</span><span class="sxs-lookup"><span data-stu-id="796a3-124">For more information about the XMLA referenced in this topic, see [Execute Method &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) and [Cancel Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/cancel-element-xmla).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="796a3-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="796a3-125">See Also</span></span>  
 <span data-ttu-id="796a3-126">[Verwalten von Verbindungen und Sitzungen &#40;XMLA&#41;](../multidimensional-models-scripting-language-assl-xmla/managing-connections-and-sessions-xmla.md) </span><span class="sxs-lookup"><span data-stu-id="796a3-126">[Managing Connections and Sessions &#40;XMLA&#41;](../multidimensional-models-scripting-language-assl-xmla/managing-connections-and-sessions-xmla.md) </span></span>  
 <span data-ttu-id="796a3-127">[BeginSession-Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-headers/beginsession-element-xmla) </span><span class="sxs-lookup"><span data-stu-id="796a3-127">[BeginSession Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-headers/beginsession-element-xmla) </span></span>  
 <span data-ttu-id="796a3-128">[EndSession-Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-headers/endsession-element-xmla) </span><span class="sxs-lookup"><span data-stu-id="796a3-128">[EndSession Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-headers/endsession-element-xmla) </span></span>  
 [<span data-ttu-id="796a3-129">Session-Element &#40;XMLA&#41;</span><span class="sxs-lookup"><span data-stu-id="796a3-129">Session Element &#40;XMLA&#41;</span></span>](https://docs.microsoft.com/bi-reference/xmla/xml-elements-headers/session-element-xmla)  
  
  
