---
title: Zuordnen von TCP/IP-Ports zu NUMA-Knoten (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- NUMA
- memory [SQL Server], NUMA
- affinity NUMA
- ports [SQL Server], working with NUMA
- CPU [SQL Server], NUMA support
- NUMA, How to map a port to a NUMA node
- NUMA affinity
- TCP/IP [SQL Server], NUMA support
- non-uniform memory access
ms.assetid: 07727642-0266-4cbc-8c55-3c367e4458ca
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: cf4a1bd7e02719d3884011ad3faa20a1ccc6466a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696053"
---
# <a name="map-tcp-ip-ports-to-numa-nodes-sql-server"></a><span data-ttu-id="7ebcd-102">Zuordnen von TCP/IP-Ports zu NUMA-Knoten (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7ebcd-102">Map TCP IP Ports to NUMA Nodes (SQL Server)</span></span>
  <span data-ttu-id="7ebcd-103">In diesem Thema wird beschrieben, wie TCP/IP-Ports mit dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager nicht einheitlichen Speicherzugriffsknoten (Non-Uniform Memory Access, NUMA) zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="7ebcd-103">This topic describes how to map TCP/IP ports to non-uniform memory access (NUMA) nodes by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="7ebcd-104">Beim Starten schreibt [!INCLUDE[ssDE](../../includes/ssde-md.md)] die Knotendaten in das Fehlerprotokoll.</span><span class="sxs-lookup"><span data-stu-id="7ebcd-104">On startup, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] writes the node information to the error log.</span></span>  
  
 <span data-ttu-id="7ebcd-105">Lesen Sie die Knotendaten entweder aus dem Fehlerprotokoll oder aus der **sys.dm_os_schedulers** -Sicht, um die Knotennummer des gewünschten Knotens zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="7ebcd-105">To determine the node number of the node you want to use, either read the node information from the error log, or from the **sys.dm_os_schedulers** view.</span></span> <span data-ttu-id="7ebcd-106">Hängen Sie eine Knoten-ID-Bitmap (eine Affinitätsmaske) in Klammern an die Portnummer an, um eine TCP/IP-Adresse und einen Port für einen oder mehrere Knoten festzulegen.</span><span class="sxs-lookup"><span data-stu-id="7ebcd-106">To set a TCP/IP address and port to single or multiple nodes, append a node identification bitmap (an affinity mask) in brackets after the port number.</span></span> <span data-ttu-id="7ebcd-107">Die Knoten können wahlweise im Dezimal- oder im Hexadezimalformat angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7ebcd-107">Nodes can be specified in either decimal or hexadecimal format.</span></span> <span data-ttu-id="7ebcd-108">Zum Erstellen der Bitmap nummerieren Sie die Knoten zunächst von rechts nach links, beginnend mit Null (z. B. 76543210).</span><span class="sxs-lookup"><span data-stu-id="7ebcd-108">To create the bitmap, first number the nodes from right to left starting with zero, as in 76543210.</span></span> <span data-ttu-id="7ebcd-109">Erstellen Sie eine binäre Darstellung der Knotenliste; geben Sie dabei den Wert 1 für die zu verwendenden Knoten an bzw. den Wert 0 für die Knoten, die nicht berücksichtigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7ebcd-109">Create a binary representation of the node list, providing 1 for nodes you want to use, and 0 for nodes you do not want to use.</span></span> <span data-ttu-id="7ebcd-110">Sollen z. B. die NUMA-Knoten 0, 2 und 5 verwendet werden, geben Sie 00100101 an.</span><span class="sxs-lookup"><span data-stu-id="7ebcd-110">For example, to use NUMA nodes 0, 2, and 5, specify 00100101.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7ebcd-111">NUMA-Knotennummer</span><span class="sxs-lookup"><span data-stu-id="7ebcd-111">NUMA node number</span></span>|<span data-ttu-id="7ebcd-112">76543210</span><span class="sxs-lookup"><span data-stu-id="7ebcd-112">76543210</span></span>|  
|<span data-ttu-id="7ebcd-113">Maske für 0, 2 und 5, von rechts gezählt</span><span class="sxs-lookup"><span data-stu-id="7ebcd-113">Mask for 0, 2, and 5 counting from right</span></span>|<span data-ttu-id="7ebcd-114">00100101</span><span class="sxs-lookup"><span data-stu-id="7ebcd-114">00100101</span></span>|  
  
 <span data-ttu-id="7ebcd-115">Konvertieren Sie die binäre Darstellung (00100101) in eine Dezimalzahl `[37]`oder in eine Hexadezimalzahl `[0x25]`.</span><span class="sxs-lookup"><span data-stu-id="7ebcd-115">Convert the binary representation (00100101), into decimal `[37]`, or hexadecimal `[0x25]`.</span></span> <span data-ttu-id="7ebcd-116">Sollen alle Knoten überwacht werden, geben Sie keine Knoten-ID an.</span><span class="sxs-lookup"><span data-stu-id="7ebcd-116">To listen on all nodes, provide no node identifier.</span></span>  
  
 <span data-ttu-id="7ebcd-117">Wenn ein Port mehreren NUMA-Knoten zugeordnet ist, weist [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] den Knoten Verbindungen im Round-Robin-Verfahren zu, ohne zu versuchen, zwischen den Knoten einen Lastenausgleich durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="7ebcd-117">If a port is mapped to more than one NUMA node, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] assigns connections to nodes in a round-robin fashion without attempting to balance load across the nodes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7ebcd-118">Lesen Sie die Informationen unter [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Konfigurieren der Datenbank-Engine zum Überwachen mehrerer TCP-Ports [, um](configure-the-database-engine-to-listen-on-multiple-tcp-ports.md)zu ermöglichen, an mehreren TCP-Ports für jede IP-Adresse zu lauschen.</span><span class="sxs-lookup"><span data-stu-id="7ebcd-118">To enable [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to listen on multiple TCP ports for each IP address, see [Configure the Database Engine to Listen on Multiple TCP Ports](configure-the-database-engine-to-listen-on-multiple-tcp-ports.md).</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7ebcd-119">Verwenden des SQL Server-Konfigurations-Managers</span><span class="sxs-lookup"><span data-stu-id="7ebcd-119">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-map-a-tcpip-port-to-a-numa-node"></a><span data-ttu-id="7ebcd-120">So ordnen Sie einen TCP/IP-Port einem NUMA-Knoten zu</span><span class="sxs-lookup"><span data-stu-id="7ebcd-120">To map a TCP/IP port to a NUMA node</span></span>  
  
1.  <span data-ttu-id="7ebcd-121">Erweitern Sie im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Konfigurations-Manager den Eintrag **SQL Server-Netzwerkkonfiguration**, und klicken Sie dann auf **Protokolle für** *\<instance name>* .</span><span class="sxs-lookup"><span data-stu-id="7ebcd-121">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, expand **SQL Server Network Configuration**, and then click **Protocols for** *\<instance name>*.</span></span>  
  
2.  <span data-ttu-id="7ebcd-122">Doppelklicken Sie im Detailbereich auf **TCP/IP**.</span><span class="sxs-lookup"><span data-stu-id="7ebcd-122">In the details pane, double-click **TCP/IP**.</span></span>  
  
3.  <span data-ttu-id="7ebcd-123">Fügen Sie auf der Registerkarte **IP-Adressen** in dem der zu konfigurierenden IP-Adresse entsprechenden Abschnitt im Feld **TCP-Port** nach der Portnummer die NUMA-Knoten-ID in Klammern hinzu.</span><span class="sxs-lookup"><span data-stu-id="7ebcd-123">On the **IP Addresses** tab, in the section corresponding to the IP address to configure, in the **TCP Port** box, add the NUMA node identifier in brackets after the port number.</span></span> <span data-ttu-id="7ebcd-124">Verwenden Sie z. B. für den TCP-Port 1500 und die Knoten 0, 2 und 5 den Eintrag `1500[37]` oder `1500[0x25]`.</span><span class="sxs-lookup"><span data-stu-id="7ebcd-124">For example, for TCP port 1500 and nodes 0, 2, and 5, use `1500[37]`, or `1500[0x25]`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ebcd-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7ebcd-125">See Also</span></span>  
 [<span data-ttu-id="7ebcd-126">Konfigurieren Sie SQL Server für die Verwendung von Soft-NUMA-&#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7ebcd-126">Configure SQL Server to Use Soft-NUMA &#40;SQL Server&#41;</span></span>](soft-numa-sql-server.md)  
  
  
