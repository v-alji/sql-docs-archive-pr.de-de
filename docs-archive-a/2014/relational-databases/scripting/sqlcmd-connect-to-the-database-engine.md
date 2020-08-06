---
title: Herstellen einer Verbindung mit der Datenbank-Engine mithilfe von sqlcmd
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- sqlcmd utility, Database Engine connections
- Named Pipes [SQL Server], sqlcmd utility
- TCP/IP [SQL Server], client protocols
- network protocols [SQL Server], sqlcmd utility
- protocols [SQL Server], sqlcmd utility
- VIA
- client protocols [SQL Server]
ms.assetid: 74b0fb71-7f8e-4171-9431-d07528532524
author: rothja
ms.author: jroth
ms.openlocfilehash: 3b409683b651e3e6508baced5eb3bc9fcc631e2c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609792"
---
# <a name="connect-to-the-database-engine-with-sqlcmd"></a><span data-ttu-id="e8340-102">Herstellen einer Verbindung mit der Datenbank-Engine mithilfe von sqlcmd</span><span class="sxs-lookup"><span data-stu-id="e8340-102">Connect to the Database Engine With sqlcmd</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e8340-103">unterstützt die Clientkommunikation mit dem TCP/IP-Netzwerkprotokoll (Standardeinstellung) und dem Named Pipes-Protokoll.</span><span class="sxs-lookup"><span data-stu-id="e8340-103">supports client communication with the TCP/IP network protocol (the default), and the named pipes protocol.</span></span> <span data-ttu-id="e8340-104">Auch das Shared Memory-Protokoll steht zur Verfügung, wenn der Client eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz auf demselben Computer herstellt.</span><span class="sxs-lookup"><span data-stu-id="e8340-104">The shared memory protocol is also available if the client is connecting to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] on the same computer.</span></span> <span data-ttu-id="e8340-105">Zum Auswählen des Protokolls stehen drei allgemeine Methoden zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="e8340-105">There are three common methods of selecting the protocol.</span></span> <span data-ttu-id="e8340-106">Das vom **sqlcmd** -Hilfsprogramm verwendete Protokoll wird in der folgenden Reihenfolge bestimmt:</span><span class="sxs-lookup"><span data-stu-id="e8340-106">The protocol used by the **sqlcmd** utility is determined in the following order:</span></span>  
  
-   <span data-ttu-id="e8340-107">**sqlcmd** verwendet das Protokoll, das wie unten beschrieben als Teil der Verbindungszeichenfolge angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="e8340-107">**sqlcmd** uses the protocol specified as part of the connection string as described below.</span></span>  
  
-   <span data-ttu-id="e8340-108">Wenn kein Protokoll als Teil der Verbindungszeichenfolge angegeben ist, verwendet **sqlcmd** das Protokoll, das als Teil des Alias definiert ist, mit dem eine Verbindung hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="e8340-108">If no protocol is specified as part the connection string, **sqlcmd** will use the protocol defined as part of the alias that it is connecting to.</span></span> <span data-ttu-id="e8340-109">Informationen dazu, wie Sie **sqlcmd** durch das Erstellen eines Alias für die Verwendung eines bestimmten Netzwerkprotokolls konfigurieren, finden Sie unter [Erstellen oder Löschen eines Serveralias für die Verwendung durch einen Client &#40;SQL Server-Konfigurations-Manager&#41;](../../database-engine/configure-windows/create-or-delete-a-server-alias-for-use-by-a-client.md).</span><span class="sxs-lookup"><span data-stu-id="e8340-109">To configure **sqlcmd** to use a specific network protocol by creating an alias, see [Create or Delete a Server Alias for Use by a Client &#40;SQL Server Configuration Manager&#41;](../../database-engine/configure-windows/create-or-delete-a-server-alias-for-use-by-a-client.md).</span></span>  
  
-   <span data-ttu-id="e8340-110">Wenn das Protokoll nicht auf andere Weise definiert ist, verwendet **sqlcmd** das Netzwerkprotokoll, das durch die Protokollreihenfolge im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="e8340-110">If the protocol is not specified in some other way, **sqlcmd** will use the network protocol determined by the protocol order in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
 <span data-ttu-id="e8340-111">In den folgenden Beispielen werden verschiedene Möglichkeiten für das Herstellen einer Verbindung mit der [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Standardinstanz über Port 1433 und mit benannten [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Instanzen veranschaulicht, die an Port 1691 lauschen sollen.</span><span class="sxs-lookup"><span data-stu-id="e8340-111">The following examples show various ways of connecting to the default instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] on port 1433, and named instances of [!INCLUDE[ssDE](../../includes/ssde-md.md)] presumed to be listening on port 1691.</span></span> <span data-ttu-id="e8340-112">In einigen dieser Beispiele wird die IP-Adresse des Loopbackadapters (127.0.0.1) verwendet.</span><span class="sxs-lookup"><span data-stu-id="e8340-112">Some of these examples use the IP address of the loopback adapter (127.0.0.1).</span></span> <span data-ttu-id="e8340-113">Testen Sie diese Einstellung mithilfe der IP-Adresse der Computer-Netzwerkschnittstellenkarte.</span><span class="sxs-lookup"><span data-stu-id="e8340-113">Test using the IP address of your computer network interface card.</span></span>  
  
 <span data-ttu-id="e8340-114">Stellen Sie eine Verbindung zu [!INCLUDE[ssDE](../../includes/ssde-md.md)] her, indem Sie den Namen der Instanz angeben:</span><span class="sxs-lookup"><span data-stu-id="e8340-114">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] by specifying the instance name:</span></span>  
  
```  
sqlcmd -S ComputerA  
sqlcmd -S ComputerA\instanceB  
```  
  
 <span data-ttu-id="e8340-115">Stellen Sie eine Verbindung mit [!INCLUDE[ssDE](../../includes/ssde-md.md)] her, indem Sie die IP-Adresse angeben:</span><span class="sxs-lookup"><span data-stu-id="e8340-115">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] by specifying the IP address:</span></span>  
  
```  
sqlcmd -S 127.0.0.1  
sqlcmd -S 127.0.0.1\instanceB  
```  
  
 <span data-ttu-id="e8340-116">Stellen Sie eine Verbindung mit [!INCLUDE[ssDE](../../includes/ssde-md.md)] her, indem Sie die TCP/IP-Portnummer angeben:</span><span class="sxs-lookup"><span data-stu-id="e8340-116">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] by specifying the TCP\IP port number:</span></span>  
  
```  
sqlcmd -S ComputerA,1433  
sqlcmd -S ComputerA,1691  
sqlcmd -S 127.0.0.1,1433  
sqlcmd -S 127.0.0.1,1691  
```  
  
### <a name="to-connect-using-tcpip"></a><span data-ttu-id="e8340-117">So stellen Sie eine Verbindung über TCP/IP her</span><span class="sxs-lookup"><span data-stu-id="e8340-117">To connect using TCP/IP</span></span>  
  
-   <span data-ttu-id="e8340-118">Stellen Sie eine Verbindung mithilfe der folgenden allgemeinen Syntax her:</span><span class="sxs-lookup"><span data-stu-id="e8340-118">Connect using the following general syntax:</span></span>  
  
    ```  
    sqlcmd -S tcp:<computer name>,<port number>  
    ```  
  
-   <span data-ttu-id="e8340-119">Stellen Sie eine Verbindung mit der Standardinstanz her:</span><span class="sxs-lookup"><span data-stu-id="e8340-119">Connect to the default instance:</span></span>  
  
    ```  
    sqlcmd -S tcp:ComputerA,1433  
    sqlcmd -S tcp:127.0.0.1,1433  
    ```  
  
-   <span data-ttu-id="e8340-120">Stellen Sie eine Verbindung mit einer benannten Instanz her:</span><span class="sxs-lookup"><span data-stu-id="e8340-120">Connect to a named instance:</span></span>  
  
    ```  
    sqlcmd -S tcp:ComputerA,1691  
    sqlcmd -S tcp:127.0.0.1,1691  
    ```  
  
### <a name="to-connect-using-named-pipes"></a><span data-ttu-id="e8340-121">So stellen Sie eine Verbindung mithilfe von Named Pipes her</span><span class="sxs-lookup"><span data-stu-id="e8340-121">To connect using named pipes</span></span>  
  
-   <span data-ttu-id="e8340-122">Stellen Sie eine Verbindung mithilfe einer der folgenden allgemeinen Syntaxangaben her:</span><span class="sxs-lookup"><span data-stu-id="e8340-122">Connect using one of the following general syntax:</span></span>  
  
    ```  
    sqlcmd -S np:\\<computer name>\<pipe name>  
    ```  
  
-   <span data-ttu-id="e8340-123">Stellen Sie eine Verbindung mit der Standardinstanz her:</span><span class="sxs-lookup"><span data-stu-id="e8340-123">Connect to the default instance:</span></span>  
  
    ```  
    sqlcmd -S np:\\ComputerA\pipe\sql\query  
    sqlcmd -S np:\\127.0.0.1\pipe\sql\query  
    ```  
  
-   <span data-ttu-id="e8340-124">Stellen Sie eine Verbindung zu einer benannten Instanz her:</span><span class="sxs-lookup"><span data-stu-id="e8340-124">Connect to a named instance instance:</span></span>  
  
    ```  
    sqlcmd -S np:\\ComputerA\pipe\MSSQL$<instancename>\sql\query  
    sqlcmd -S np:\\127.0.0.1\pipe\MSSQL$<instancename>\sql\query  
    ```  
  
### <a name="to-connect-using-shared-memory-a-local-procedure-call-from-a-client-on-the-server"></a><span data-ttu-id="e8340-125">So stellen Sie eine Verbindung mithilfe des Shared Memory-Protokolls (einem lokalen Prozeduraufruf) von einem Client auf dem Server her</span><span class="sxs-lookup"><span data-stu-id="e8340-125">To connect using shared memory (a local procedure call) from a client on the server</span></span>  
  
-   <span data-ttu-id="e8340-126">Stellen Sie eine Verbindung mithilfe einer der folgenden allgemeinen Syntaxangaben her:</span><span class="sxs-lookup"><span data-stu-id="e8340-126">Connect using one of the following general syntax:</span></span>  
  
    ```  
    sqlcmd -S lpc:<computer name>  
    ```  
  
-   <span data-ttu-id="e8340-127">Stellen Sie eine Verbindung mit der Standardinstanz her:</span><span class="sxs-lookup"><span data-stu-id="e8340-127">Connect to the default instance:</span></span>  
  
    ```  
    sqlcmd -S lpc:ComputerA  
    ```  
  
-   <span data-ttu-id="e8340-128">Stellen Sie eine Verbindung mit einer benannten Instanz her:</span><span class="sxs-lookup"><span data-stu-id="e8340-128">Connect to a named instance:</span></span>  
  
    ```  
    sqlcmd -S lpc:ComputerA\<instancename>  
    ```  
  
  
