---
title: Client Protokolle-TCP-und IP-Eigenschaften (Registerkarte Protokoll) | Microsoft-Dokumentation
description: Erfahren Sie, wie Sie TCP/IP-Optionen in Microsoft SQL Server Configuration Manager angeben, z. b. den Keep-Alive-Parameter und die Standard Portnummer.
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- TCP/IP [SQL Server], client protocols
- client protocols [SQL Server]
ms.assetid: d04f1bce-069c-4a02-b561-c87c3282be36
author: rothja
ms.author: jroth
ms.openlocfilehash: dfcf0348dc863970384a40cc9e773481adeedb35
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722134"
---
# <a name="client-protocols---tcp-and-ip-properties-protocol-tab"></a><span data-ttu-id="207d9-103">Clientprotokolle – TCP- und IP-Eigenschaften (Registerkarte „Protokoll“)</span><span class="sxs-lookup"><span data-stu-id="207d9-103">Client Protocols - TCP and IP Properties (Protocol Tab)</span></span>
  <span data-ttu-id="207d9-104">Verwenden Sie die Registerkarte **Protokoll** im Dialogfeld **TCP/IP-Eigenschaften** des [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Konfigurations-Managers, um die folgenden Optionen anzuzeigen oder festzulegen.</span><span class="sxs-lookup"><span data-stu-id="207d9-104">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, use the **Protocol** tab on the **TCP/IP Properties** dialog box to view or specify the following options.</span></span> <span data-ttu-id="207d9-105">Zum Herstellen einer Verbindung mit einem anderen Port geben Sie die Portnummer im Dialogfeld **Standardport** ein.</span><span class="sxs-lookup"><span data-stu-id="207d9-105">To connect to a different port, type the port number in the **Default Port** box.</span></span> <span data-ttu-id="207d9-106">Weitere Informationen zu Verbindungszeichenfolgen finden Sie unter [Erstellen einer gültigen Verbindungszeichenfolge mithilfe von TCP/IP](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md).</span><span class="sxs-lookup"><span data-stu-id="207d9-106">For more information about connection strings, see [Creating a Valid Connection String Using TCP IP](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="207d9-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="207d9-107">Options</span></span>  
 <span data-ttu-id="207d9-108">**Standardport**</span><span class="sxs-lookup"><span data-stu-id="207d9-108">**Default Port**</span></span>  
 <span data-ttu-id="207d9-109">Gibt den Standardport an, der von der TCP/IP-Netzwerkbibliothek zum Herstellen einer Verbindung mit der Zielinstanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="207d9-109">Specifies the port that the TCP/IP Net-library will use to attempt to connect to the target instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="207d9-110">Der Standardport ist 1433.</span><span class="sxs-lookup"><span data-stu-id="207d9-110">The default value port is 1433.</span></span>  
  
 <span data-ttu-id="207d9-111">Beim Verbinden mit einer Standardinstanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)]verwendet der Client diesen Wert.</span><span class="sxs-lookup"><span data-stu-id="207d9-111">When connecting to a default instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)], the client uses this value.</span></span> <span data-ttu-id="207d9-112">Wenn die Standardinstanz zur Überwachung eines anderen Ports konfiguriert wurde, ändern Sie diesen Wert in diese Portnummer.</span><span class="sxs-lookup"><span data-stu-id="207d9-112">If a default instance has been configured to listen on a different port, change this value to that port number.</span></span>  
  
 <span data-ttu-id="207d9-113">Beim Herstellen einer Verbindung mit einer benannten Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)]versucht der Client, die Portnummer vom [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Browser-Dienst zu erhalten, der auf dem Servercomputer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="207d9-113">When connecting to a named instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)], the client will attempt to obtain the port number from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser Service running on the server computer.</span></span> <span data-ttu-id="207d9-114">Wenn der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Browser-Dienst nicht ausgeführt wird, muss die Portnummer über diese Einstellung oder in der Verbindungszeichenfolge angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="207d9-114">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser Service is not running, the port number must be provided through this setting, or as part of the connection string.</span></span>  
  
 <span data-ttu-id="207d9-115">**Aktiviert**</span><span class="sxs-lookup"><span data-stu-id="207d9-115">**Enabled**</span></span>  
 <span data-ttu-id="207d9-116">Mögliche Werte sind **Yes** und **No**.</span><span class="sxs-lookup"><span data-stu-id="207d9-116">Possible values are **Yes** and **No**.</span></span>  
  
 <span data-ttu-id="207d9-117">**Keep-Alive**</span><span class="sxs-lookup"><span data-stu-id="207d9-117">**Keep Alive**</span></span>  
 <span data-ttu-id="207d9-118">Dieser Parameter steuert, wie oft (in Millisekunden) TCP durch das Senden eines **KEEPALIVE** -Pakets zu überprüfen versucht, ob eine Verbindung im Leerlauf noch reagiert.</span><span class="sxs-lookup"><span data-stu-id="207d9-118">This parameter (in milliseconds) controls how often TCP attempts to verify that an idle connection is still intact by sending a **KEEPALIVE** packet.</span></span> <span data-ttu-id="207d9-119">Der Standardwert beträgt 30000 Millisekunden.</span><span class="sxs-lookup"><span data-stu-id="207d9-119">The default is 30000 milliseconds.</span></span>  
  
 <span data-ttu-id="207d9-120">**Erhaltungsintervall**</span><span class="sxs-lookup"><span data-stu-id="207d9-120">**Keep Alive Interval**</span></span>  
 <span data-ttu-id="207d9-121">Dieser Parameter bestimmt das Intervall (in Millisekunden), das **KEEPALIVE** -Pakete voneinander trennt, bis eine Antwort erhalten wird.</span><span class="sxs-lookup"><span data-stu-id="207d9-121">This parameter (in milliseconds) determines the interval separating **KEEPALIVE** retransmissions until a response is received.</span></span> <span data-ttu-id="207d9-122">Der Standardwert beträgt 1.000 Millisekunden.</span><span class="sxs-lookup"><span data-stu-id="207d9-122">The default is 1000 milliseconds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="207d9-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="207d9-123">See Also</span></span>  
 <span data-ttu-id="207d9-124">[Auswählen eines Netzwerk Protokolls](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md) </span><span class="sxs-lookup"><span data-stu-id="207d9-124">[Choosing a Network Protocol](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md) </span></span>  
 <span data-ttu-id="207d9-125">[Neuer Alias &#40;Registerkarte "Alias"&#41;](../../../2014/tools/configuration-manager/new-alias-alias-tab.md) </span><span class="sxs-lookup"><span data-stu-id="207d9-125">[New Alias &#40;Alias Tab&#41;](../../../2014/tools/configuration-manager/new-alias-alias-tab.md) </span></span>  
 [<span data-ttu-id="207d9-126">&#60;Alias&#62;-Eigenschaften &#40;Registerkarte „Alias“&#41;</span><span class="sxs-lookup"><span data-stu-id="207d9-126">&#60;Alias&#62; Properties &#40;Alias Tab&#41;</span></span>](../../../2014/tools/configuration-manager/alias-properties-alias-tab.md)  
  
  
