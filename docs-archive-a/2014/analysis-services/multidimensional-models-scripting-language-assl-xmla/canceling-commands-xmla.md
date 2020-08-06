---
title: Abbrechen von Befehlen (XMLA) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- connections [XML for Analysis]
- associated connections [XML for Analysis]
- XML for Analysis, canceling
- associated sessions [XML for Analysis]
- canceling connections
- canceling commands
- canceling sessions
- SPID
- XMLA, canceling
- server process IDs [XML for Analysis]
- sessions [XML for Analysis]
ms.assetid: b59f8197-c33d-4e65-9022-848ccba540f5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 003c70362c38ae1838b4679abf6485fa031a9143
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696261"
---
# <a name="canceling-commands-xmla"></a><span data-ttu-id="5f7d3-102">Abbrechen von Befehlen (XMLA)</span><span class="sxs-lookup"><span data-stu-id="5f7d3-102">Canceling Commands (XMLA)</span></span>
  <span data-ttu-id="5f7d3-103">Abhängig von den administrativen Berechtigungen des Benutzers, der den Befehl ausgibt, kann der [Cancel](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/cancel-element-xmla) -Befehl in XML for Analysis (XMLA) einen Befehl für eine Sitzung, eine Sitzung, eine Verbindung, einen Server Prozess oder eine zugeordnete Sitzung oder Verbindung abbrechen.</span><span class="sxs-lookup"><span data-stu-id="5f7d3-103">Depending on the administrative permissions of the user issuing the command, the [Cancel](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/cancel-element-xmla) command in XML for Analysis (XMLA) can cancel a command on a session, a session, a connection, a server process, or an associated session or connection.</span></span>  
  
## <a name="canceling-commands"></a><span data-ttu-id="5f7d3-104">Abbrechen von Befehlen</span><span class="sxs-lookup"><span data-stu-id="5f7d3-104">Canceling Commands</span></span>  
 <span data-ttu-id="5f7d3-105">Ein Benutzer kann den zurzeit ausgeführten Befehl innerhalb der aktuellen expliziten Sitzung abbrechen, indem er einen `Cancel`-Befehl ohne festgelegte Eigenschaften sendet.</span><span class="sxs-lookup"><span data-stu-id="5f7d3-105">A user can cancel the currently executing command within the context of the current explicit session by sending a `Cancel` command with no specified properties.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5f7d3-106">Ein Befehl, der in einer impliziten Sitzung ausgeführt wird, kann von einem Benutzer nicht abgebrochen werden.</span><span class="sxs-lookup"><span data-stu-id="5f7d3-106">A command running in an implicit session cannot be canceled by a user.</span></span>  
  
### <a name="canceling-batch-commands"></a><span data-ttu-id="5f7d3-107">Abbrechen von Batch-Befehlen</span><span class="sxs-lookup"><span data-stu-id="5f7d3-107">Canceling Batch Commands</span></span>  
 <span data-ttu-id="5f7d3-108">Wenn ein Benutzer einen `Batch`-Befehl abbricht, werden alle noch nicht ausgeführten Befehle innerhalb des `Batch`-Befehls abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="5f7d3-108">If a user cancels a `Batch` command, then all remaining commands not yet executed within the `Batch` command are canceled.</span></span> <span data-ttu-id="5f7d3-109">Wenn es sich bei dem `Batch`-Befehl um eine Transaktionsreplikation handelt, werden alle Befehle, die vor der Ausführung des `Cancel`-Befehls ausgeführt wurden, rückgängig gemacht.</span><span class="sxs-lookup"><span data-stu-id="5f7d3-109">If the `Batch` command was transactional, any commands that were executed before the `Cancel` command runs are rolled back.</span></span>  
  
## <a name="canceling-sessions"></a><span data-ttu-id="5f7d3-110">Abbrechen von Sitzungen</span><span class="sxs-lookup"><span data-stu-id="5f7d3-110">Canceling Sessions</span></span>  
 <span data-ttu-id="5f7d3-111">Wenn Sie in der [SessionID](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/id-element-xmla) -Eigenschaft des Befehls eine Sitzungs-ID für eine explizite Sitzung angeben `Cancel` , kann ein Datenbankadministrator oder Server Administrator eine Sitzung abbrechen, einschließlich des aktuell ausgeführten Befehls.</span><span class="sxs-lookup"><span data-stu-id="5f7d3-111">By specifying a session identifier for an explicit session in the [SessionID](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/id-element-xmla) property of the `Cancel` command, a database administrator or server administrator can cancel a session, including the currently executing command.</span></span> <span data-ttu-id="5f7d3-112">Ein Datenbankadministrator kann nur Sitzungen für Datenbanken abbrechen, für die er über Administratorberechtigungen verfügt.</span><span class="sxs-lookup"><span data-stu-id="5f7d3-112">A database administrator can only cancel sessions for databases on which he or she has administrative permissions.</span></span>  
  
 <span data-ttu-id="5f7d3-113">Ein Datenbankadministrator kann die aktiven Sitzungen für eine festgelegte Datenbank abrufen, indem er das DISCOVER_SESSIONS-Schemarowset abruft.</span><span class="sxs-lookup"><span data-stu-id="5f7d3-113">A database administrator can retrieve the active sessions for a specified database by retrieving the DISCOVER_SESSIONS schema rowset.</span></span> <span data-ttu-id="5f7d3-114">Zum Abrufen des DISCOVER_SESSIONS Schemarowsets verwendet der Datenbankadministrator die XMLA `Discover` -Methode und gibt den entsprechenden Daten Bank Bezeichner für die SESSION_CURRENT_DATABASE Einschränkungs Spalte in der Eigenschaft [Einschränkungen](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/restrictions-element-xmla) der `Discover` Methode an.</span><span class="sxs-lookup"><span data-stu-id="5f7d3-114">To retrieve the DISCOVER_SESSIONS schema rowset, the database administrator uses the XMLA `Discover` method and specifies the appropriate database identifier for the SESSION_CURRENT_DATABASE restriction column in the [Restrictions](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/restrictions-element-xmla) property of the `Discover` method.</span></span>  
  
## <a name="canceling-connections"></a><span data-ttu-id="5f7d3-115">Abbrechen von Verbindungen</span><span class="sxs-lookup"><span data-stu-id="5f7d3-115">Canceling Connections</span></span>  
 <span data-ttu-id="5f7d3-116">Durch Angeben eines Verbindungs Bezeichners in der [ConnectionID](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/connectionid-element-xmla) -Eigenschaft des `Cancel` Befehls kann ein Server Administrator alle Sitzungen abbrechen, die einer bestimmten Verbindung zugeordnet sind, einschließlich aller Befehle, die ausgeführt werden, und die Verbindung abbrechen.</span><span class="sxs-lookup"><span data-stu-id="5f7d3-116">By specifying a connection identifier in the [ConnectionID](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/connectionid-element-xmla) property of the `Cancel` command, a server administrator can cancel all of the sessions associated with a given connection, including all running commands, and cancel the connection.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5f7d3-117">Wenn die Instanz von [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] die einer Verbindung zugeordneten Sitzungen nicht finden und Abbrechen kann, z. b. wenn die Daten Verschiebung beim Bereitstellen von http-Konnektivität mehrere Sitzungen öffnet, kann die Instanz die Verbindung nicht abbrechen.</span><span class="sxs-lookup"><span data-stu-id="5f7d3-117">If the instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] cannot locate and cancel the sessions associated with a connection, such as when the data pump opens multiple sessions while providing HTTP connectivity, the instance cannot cancel the connection.</span></span> <span data-ttu-id="5f7d3-118">Wenn dies während der Ausführung eines `Cancel`-Befehls passiert, tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="5f7d3-118">If this case is encountered during the execution of a `Cancel` command, an error occurs.</span></span>  
  
 <span data-ttu-id="5f7d3-119">Ein Serveradministrator kann die aktiven Verbindungen für eine [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]-Instanz abrufen, indem er das DISCOVER_CONNECTIONS-Schemarowset mithilfe der `Discover`-Methode von XMLA aufruft.</span><span class="sxs-lookup"><span data-stu-id="5f7d3-119">A server administrator can retrieve the active connections for an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance by retrieving the DISCOVER_CONNECTIONS schema rowset using the XMLA `Discover` method.</span></span>  
  
## <a name="canceling-server-processes"></a><span data-ttu-id="5f7d3-120">Abbrechen von Serverprozessen</span><span class="sxs-lookup"><span data-stu-id="5f7d3-120">Canceling Server Processes</span></span>  
 <span data-ttu-id="5f7d3-121">Durch Angeben eines Server Prozess Bezeichners (SPID) in der [SPID-](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/id-element-xmla) Eigenschaft des `Cancel` Befehls kann ein Server Administrator die Befehle abbrechen, die einer bestimmten SPID zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="5f7d3-121">By specifying a server process identifier (SPID) in the [SPID](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/id-element-xmla) property of the `Cancel` command, a server administrator can cancel the commands associated with a given SPID.</span></span>  
  
## <a name="canceling-associated-sessions-and-connections"></a><span data-ttu-id="5f7d3-122">Abbrechen von zugeordneten Sitzungen und Verbindungen</span><span class="sxs-lookup"><span data-stu-id="5f7d3-122">Canceling Associated Sessions and Connections</span></span>  
 <span data-ttu-id="5f7d3-123">Sie können die [CancelAssociated](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/cancelassociated-element-xmla) -Eigenschaft auf true festlegen, um die Verbindungen, Sitzungen und Befehle abzubrechen, die der im Befehl angegebenen Verbindung, Sitzung oder SPID zugeordnet sind `Cancel` .</span><span class="sxs-lookup"><span data-stu-id="5f7d3-123">You can set the [CancelAssociated](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/cancelassociated-element-xmla) property to true to cancel the connections, sessions, and commands associated with the connection, session, or SPID specified in the `Cancel` command.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f7d3-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5f7d3-124">See Also</span></span>  
 <span data-ttu-id="5f7d3-125">[Discover-Methode &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-discover) </span><span class="sxs-lookup"><span data-stu-id="5f7d3-125">[Discover Method &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-discover) </span></span>  
 [<span data-ttu-id="5f7d3-126">Entwickeln mit XMLA in Analysis Services</span><span class="sxs-lookup"><span data-stu-id="5f7d3-126">Developing with XMLA in Analysis Services</span></span>](developing-with-xmla-in-analysis-services.md)  
  
  
