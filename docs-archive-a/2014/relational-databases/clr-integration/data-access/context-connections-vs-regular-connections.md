---
title: Reguläre und Kontext Verbindungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- context connections [CLR integration]
- regular connections [CLR integration]
ms.assetid: a1dead02-be88-4b16-8cb2-db1284856764
author: rothja
ms.author: jroth
ms.openlocfilehash: ce531129099a8f4908bdc4b29920696d4ba3c505
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622703"
---
# <a name="regular-vs-context-connections"></a><span data-ttu-id="624a6-102">Reguläre vs. Kontextverbindungen</span><span class="sxs-lookup"><span data-stu-id="624a6-102">Regular vs. Context Connections</span></span>
  <span data-ttu-id="624a6-103">Wenn Sie eine Verbindung mit einem Remoteserver herstellen, verwenden Sie stets reguläre Verbindungen anstelle von Kontextverbindungen.</span><span class="sxs-lookup"><span data-stu-id="624a6-103">If you are connecting to a remote server, always use regular connections rather than context connections.</span></span> <span data-ttu-id="624a6-104">Wenn Sie eine Verbindung mit dem Server herstellen müssen, auf dem die gespeicherte Prozedur oder Funktion ausgeführt wird, verwenden Sie in den meisten Fällen Kontextverbindungen.</span><span class="sxs-lookup"><span data-stu-id="624a6-104">If you need to connect to the same server on which the stored procedure or function is running, use the context connection in most cases.</span></span> <span data-ttu-id="624a6-105">Dies hat Vorteile, etwa das Ausführen im gleichen Transaktionsbereich, ohne dass eine erneute Authentifizierung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="624a6-105">This has benefits such as running in the same transaction space and not having to reauthenticate.</span></span>  
  
 <span data-ttu-id="624a6-106">Darüber hinaus führt das Verwenden der Kontextverbindung in der Regel zu einer höheren Leistung und geringeren Ressourcenverwendung.</span><span class="sxs-lookup"><span data-stu-id="624a6-106">Additionally, using the context connection typically results in better performance and less resource usage.</span></span> <span data-ttu-id="624a6-107">Bei der Kontext Verbindung handelt es sich um eine reine Prozess interne Verbindung, sodass Sie den Server direkt kontaktieren kann, indem Sie die Netzwerkprotokoll-und Transport Ebenen umgehen, um Transact-SQL-Anweisungen zu senden und Ergebnisse zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="624a6-107">The context connection is an in-process-only connection, so it can contact the server "directly" by bypassing the network protocol and transport layers to send Transact-SQL statements and receive results.</span></span> <span data-ttu-id="624a6-108">Der Authentifizierungsprozess wird ebenfalls umgangen.</span><span class="sxs-lookup"><span data-stu-id="624a6-108">The authentication process is bypassed, as well.</span></span> <span data-ttu-id="624a6-109">Die folgende Abbildung zeigt die primären Komponenten des `SqlClient`-verwalteten Anbieters und beschreibt, wie die verschiedenen Komponenten bei der Verwendung einer regulären und bei der Verwendung einer Kontextverbindung interagieren.</span><span class="sxs-lookup"><span data-stu-id="624a6-109">The following figure shows the primary components of the `SqlClient` managed provider, as well as how the different components interact with each other when using a regular connection, and when using the context connection.</span></span>  
  
 <span data-ttu-id="624a6-110">![Codepfade einer Kontext- und einer regulären Verbindung](../../../database-engine/dev-guide/media/clrintdataaccess.gif "Codepfade einer Kontext- und einer regulären Verbindung")</span><span class="sxs-lookup"><span data-stu-id="624a6-110">![Code paths of a context and a regular connnection.](../../../database-engine/dev-guide/media/clrintdataaccess.gif "Code paths of a context and a regular connnection.")</span></span>  
  
 <span data-ttu-id="624a6-111">Die Kontextverbindung folgt einem kürzeren Codepfad und schließt weniger Komponenten ein, sodass Sie mit schnelleren Anforderungen und Ergebnissen an den Server und vom Server rechnen können als bei einer regulären Verbindung.</span><span class="sxs-lookup"><span data-stu-id="624a6-111">The context connection follows a shorter code path and involves fewer components, so you can expect requests and results to get to and from the server faster than in a regular connection.</span></span> <span data-ttu-id="624a6-112">Die Abfrageausführungszeit auf dem Server ist bei Kontext- und reguläre Verbindungen die gleiche.</span><span class="sxs-lookup"><span data-stu-id="624a6-112">Query execution time on the server is the same for context and regular connections.</span></span>  
  
 <span data-ttu-id="624a6-113">In einigen Fällen müssen Sie möglicherweise eine separate reguläre Verbindung mit dem gleichen Server herstellen.</span><span class="sxs-lookup"><span data-stu-id="624a6-113">There are some cases in which you may need to open a separate regular connection to the same server.</span></span> <span data-ttu-id="624a6-114">Beispielsweise gibt es bestimmte Einschränkungen bei der Verwendung der Kontext Verbindung, die unter [Einschränkungen für reguläre und Kontext Verbindungen](context-connections-and-regular-connections-restrictions.md)beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="624a6-114">For example, there are certain restrictions on using the context connection, described in [Restrictions on Regular and Context Connections](context-connections-and-regular-connections-restrictions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="624a6-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="624a6-115">See Also</span></span>  
 [<span data-ttu-id="624a6-116">Kontextverbindung</span><span class="sxs-lookup"><span data-stu-id="624a6-116">Context Connection</span></span>](context-connection.md)  
  
  
