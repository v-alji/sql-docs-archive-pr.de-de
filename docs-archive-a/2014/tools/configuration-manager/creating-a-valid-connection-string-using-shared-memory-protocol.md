---
title: Erstellen einer gültigen Verbindungszeichenfolge mithilfe des Shared Memory-Protokolls | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- connection strings [Database Engine], shared memory
- aliases [SQL Server], shared memory
ms.assetid: 5fff42e8-377f-4b40-b0c8-b02393f8a1af
author: stevestein
ms.author: sstein
ms.openlocfilehash: ca97332a09a33fcfc15a3dbb2599af27dbe0e1db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695057"
---
# <a name="creating-a-valid-connection-string-using-shared-memory-protocol"></a><span data-ttu-id="519dd-102">Erstellen einer gültigen Verbindungszeichenfolge mithilfe des Shared Memory-Protokolls</span><span class="sxs-lookup"><span data-stu-id="519dd-102">Creating a Valid Connection String Using Shared Memory Protocol</span></span>
  <span data-ttu-id="519dd-103">Verbindungen mit [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] von einem Client auf dem gleichen Computer verwenden das Protokoll des gemeinsam genutzten Speicherbereichs.</span><span class="sxs-lookup"><span data-stu-id="519dd-103">Connections to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from a client running on the same computer use the shared memory protocol.</span></span> <span data-ttu-id="519dd-104">Shared Memory verfügt über keine konfigurierbaren Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="519dd-104">Shared memory has no configurable properties.</span></span> <span data-ttu-id="519dd-105">Es wird immer zuerst versucht, Shared Memory zu verwenden; es ist nicht möglich, dieses Protokoll von der obersten Position der Liste **Aktivierte Protokolle** in der Liste **Eigenschaften der Clientprotokolle** zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="519dd-105">Shared memory is always tried first, and cannot be moved from the top position of the **Enabled Protocols** list in the **Client Protocols Properties** list.</span></span> <span data-ttu-id="519dd-106">Das Shared Memory-Protokoll kann deaktiviert werden, was insbesondere bei der Problembehandlung eines der anderen Protokolle nützlich ist.</span><span class="sxs-lookup"><span data-stu-id="519dd-106">The Shared Memory protocol can be disabled, which is useful when troubleshooting one of the other protocols.</span></span>  
  
 <span data-ttu-id="519dd-107">Sie können keinen Alias mithilfe des Shared Memory-Protokolls erstellen. Allerdings wird bei aktiviertem Shared Memory über den namentlichen Verbindungsaufbau zu [!INCLUDE[ssDE](../../includes/ssde-md.md)] eine Shared Memory-Verbindung hergestellt.</span><span class="sxs-lookup"><span data-stu-id="519dd-107">You cannot create an alias using the shared memory protocol, but if shared memory is enabled, then connecting to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] by name, creates a shared memory connection.</span></span> <span data-ttu-id="519dd-108">Für Shared Memory-Verbindungszeichenfolgen wird das Format `lpc:<servername>[\instancename]`verwendet.</span><span class="sxs-lookup"><span data-stu-id="519dd-108">A shared memory connection string uses the format `lpc:<servername>[\instancename]`.</span></span>  
  
## <a name="connecting-to-the-local-server"></a><span data-ttu-id="519dd-109">Herstellen einer Verbindung mit dem lokalen Server</span><span class="sxs-lookup"><span data-stu-id="519dd-109">Connecting to the Local Server</span></span>  
 <span data-ttu-id="519dd-110">Beim Herstellen einer Verbindung mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , das auf dem gleichen Computer wie der Client ausgeführt wird, können Sie **(local)** als Servernamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="519dd-110">When connecting to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on the same computer as the client, you can use **(local)** as the server name.</span></span> <span data-ttu-id="519dd-111">Aus Gründen der Mehrdeutigkeit wird dies nicht empfohlen, kann aber nützlich sein, wenn vom Client bekannt ist, dass er auf dem vorgesehenen Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="519dd-111">This is not encouraged as it leads to ambiguity, however it can be useful when the client is known to be running on the intended computer.</span></span> <span data-ttu-id="519dd-112">Beim Erstellen einer Anwendung für mobile Benutzer mit getrennter Verbindung (beispielsweise für Verkaufspersonal, wobei [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] auf Laptops ausgeführt und zum Speichern von Projektdaten verwendet wird) würde beispielsweise die Verbindung eines Clients zu **(local)** immer zu dem auf dem Laptop ausgeführten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] hergestellt.</span><span class="sxs-lookup"><span data-stu-id="519dd-112">For instance, when creating an application for mobile disconnected users, such as a sales force, where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will run on laptop computers and store project data, a client connecting to **(local)** would always connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on the laptop.</span></span> <span data-ttu-id="519dd-113">Anstelle von **(local)** kann das Wort**localhost**oder ein Punkt ( **.** ) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="519dd-113">The word **localhost** or a period (**.**) can be used in place of **(local)**.</span></span>  
  
## <a name="verifying-your-connection-protocol"></a><span data-ttu-id="519dd-114">Überprüfen Ihres Verbindungsprotokolls</span><span class="sxs-lookup"><span data-stu-id="519dd-114">Verifying your Connection Protocol</span></span>  
 <span data-ttu-id="519dd-115">Von der folgenden Abfrage wird das Protokoll zurückgegeben, das für die aktuelle Verbindung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="519dd-115">The following query will return the protocol used for the current connection.</span></span>  
  
```  
SELECT net_transport   
FROM sys.dm_exec_connections   
WHERE session_id = @@SPID;  
  
```  
  
## <a name="examples"></a><span data-ttu-id="519dd-116">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="519dd-116">Examples:</span></span>  
 <span data-ttu-id="519dd-117">Die folgenden Namen werden mit dem lokalen Computer mithilfe des Shared Memory-Protokolls verbunden, falls dieses aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="519dd-117">The following names will connect to the local computer with the shared memory protocol if it is enabled:</span></span>  
  
 `<servername>`  
  
 `<servername>\<instancename>`  
  
 `(local)`  
  
 `localhost`  
  
 <span data-ttu-id="519dd-118">Sie können keinen Alias für eine Shared Memory-Verbindung erstellen.</span><span class="sxs-lookup"><span data-stu-id="519dd-118">You cannot create an alias for a shared memory connection.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="519dd-119">Die Angabe einer IP-Adresse im Feld **Server** führt zu einer TCP/IP-Verbindung.</span><span class="sxs-lookup"><span data-stu-id="519dd-119">Specifying an IP Address in the **Server** box will result in a TCP/IP connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="519dd-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="519dd-120">See Also</span></span>  
 <span data-ttu-id="519dd-121">[Erstellen einer gültigen Verbindungszeichenfolge mithilfe von TCP/IP](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md) </span><span class="sxs-lookup"><span data-stu-id="519dd-121">[Creating a Valid Connection String Using TCP IP](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md) </span></span>  
 <span data-ttu-id="519dd-122">[Erstellen einer gültigen Verbindungszeichenfolge mithilfe von Named Pipes](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md) </span><span class="sxs-lookup"><span data-stu-id="519dd-122">[Creating a Valid Connection String Using Named Pipes](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md) </span></span>  
 [<span data-ttu-id="519dd-123">Auswählen eines Netzwerkprotokolls</span><span class="sxs-lookup"><span data-stu-id="519dd-123">Choosing a Network Protocol</span></span>](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md)  
  
  
