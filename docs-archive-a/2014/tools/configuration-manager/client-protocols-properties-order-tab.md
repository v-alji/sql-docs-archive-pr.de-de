---
title: Eigenschaften der Client Protokolle (Registerkarte Reihenfolge) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- client protocols [SQL Server]
ms.assetid: 64fd7135-1756-4885-bed9-9ab8997ecc6c
author: stevestein
ms.author: sstein
ms.openlocfilehash: a367cff3495389d1a707ed108ba75e1e736538b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697329"
---
# <a name="client-protocols-properties-order-tab"></a><span data-ttu-id="30d79-102">Eigenschaften der Clientprotokolle (Registerkarte Reihenfolge)</span><span class="sxs-lookup"><span data-stu-id="30d79-102">Client Protocols Properties (Order Tab)</span></span>
  <span data-ttu-id="30d79-103">Verwenden Sie die Seite **Reihenfolge**im Dialogfeld **Eigenschaften der Clientprotokolle** , um die Clientprotokolle anzuzeigen und zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="30d79-103">Use the **Order**page on the **Client Protocols Properties** dialog box to view and enable the client protocols.</span></span>  
  
 <span data-ttu-id="30d79-104">Klicken Sie auf ein Protokoll, und klicken Sie dann auf **Aktivieren** oder **Deaktivieren** , um das ausgewählte Protokoll in die Liste **Deaktivierte Protokolle** oder **Aktivierte Protokolle** zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="30d79-104">Click a protocol, and then click **Enable** or **Disable** to move the selected protocol to the **Disabled Protocols** or **Enabled Protocols** list.</span></span>  
  
 <span data-ttu-id="30d79-105">Protokolle werden in der Reihenfolge verwendet, in der sie aufgelistet sind, wobei zunächst das erste Protokoll in der Liste, dann das zweite Protokoll usw. verwendet wird. Verschieben Sie Protokolle in der Liste **Aktivierte Protokolle** nach oben oder nach unten, indem Sie auf die Schaltfläche mit dem Aufwärtspfeil bzw. Abwärtspfeil klicken.</span><span class="sxs-lookup"><span data-stu-id="30d79-105">Protocols are tried in the order listed, attempting to connect using the top protocol first, and then the second listed protocol, etc. Move protocols up or down the **Enabled Protocols** list, by clicking the up arrow and down arrow buttons.</span></span> <span data-ttu-id="30d79-106">Beim Herstellen einer Verbindung mit [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] von einem Client auf diesem Computer wird zuerst immer das **Shared Memory**-Protokoll verwendet, falls dieses aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="30d79-106">When connecting to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from a client on that computer, the **Shared Memory** protocol will always be tried first, if enabled.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="30d79-107">Diese Einstellungen werden nicht von [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET SqlClient verwendet.</span><span class="sxs-lookup"><span data-stu-id="30d79-107">These settings are not used by [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET SqlClient.</span></span> <span data-ttu-id="30d79-108">In der Protokollreihenfolge für .NET SqlClient steht TCP an der ersten Stelle, dann folgen Named Pipes. Dies kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="30d79-108">The protocol order for .NET SqlClient is first TCP, and then named pipes, which cannot be changed.</span></span>  
  
## <a name="options"></a><span data-ttu-id="30d79-109">Tastatur</span><span class="sxs-lookup"><span data-stu-id="30d79-109">Options</span></span>  
 <span data-ttu-id="30d79-110">**Deaktivierte Protokolle**</span><span class="sxs-lookup"><span data-stu-id="30d79-110">**Disabled Protocols**</span></span>  
 <span data-ttu-id="30d79-111">Führt Protokolle auf, die installiert sind, aber zum jetzigen Zeitpunkt nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="30d79-111">Lists protocols which are installed but are not currently used.</span></span>  
  
 <span data-ttu-id="30d79-112">**Aktivierte Protokolle**</span><span class="sxs-lookup"><span data-stu-id="30d79-112">**Enabled Protocols**</span></span>  
 <span data-ttu-id="30d79-113">Listet die Protokolle auf, die für- [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Clients auf diesem Computer verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="30d79-113">Lists protocols which are available for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] clients on this computer.</span></span>  
  
 **>**  
 <span data-ttu-id="30d79-114">Aktiviert das aktuell hervorgehobene Protokoll im Feld **Deaktivierte Protokolle** und verschiebt es in das Feld **Aktivierte Protokolle** .</span><span class="sxs-lookup"><span data-stu-id="30d79-114">Enables the currently highlighted protocol in the **Disabled Protocols** box, moving it to the **Enabled Protocols** box.</span></span>  
  
 **\<**  
 <span data-ttu-id="30d79-115">Deaktiviert das aktuell hervorgehobene Protokoll im Feld **Aktivierte Protokolle** und verschiebt es in das Feld **Deaktivierte Protokolle** .</span><span class="sxs-lookup"><span data-stu-id="30d79-115">Disables the currently highlighted protocol in the **Enabled Protocols** box, moving it to the **Disabled Protocols** box.</span></span>  
  
 <span data-ttu-id="30d79-116">Pfeil nach oben</span><span class="sxs-lookup"><span data-stu-id="30d79-116">Up arrow</span></span>  
 <span data-ttu-id="30d79-117">Verschiebt das markierte Protokoll in der Liste nach oben.</span><span class="sxs-lookup"><span data-stu-id="30d79-117">Moves the highlighted protocol up in the list.</span></span> <span data-ttu-id="30d79-118">Damit wird die Priorität erhöht, nach der von der Netzwerkbibliothek versucht wird, das ausgewählte Protokoll für Verbindungen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="30d79-118">This allows you to increase the priority in which the Net-Library will attempt to use the selected protocol for connections.</span></span>  
  
 <span data-ttu-id="30d79-119">Pfeil nach unten</span><span class="sxs-lookup"><span data-stu-id="30d79-119">Down arrow</span></span>  
 <span data-ttu-id="30d79-120">Verschiebt das markierte Protokoll in der Liste nach unten.</span><span class="sxs-lookup"><span data-stu-id="30d79-120">Moves the highlighted protocol down in the list.</span></span> <span data-ttu-id="30d79-121">Damit wird die Priorität herabgesetzt, nach der von der Netzwerkbibliothek versucht wird, das ausgewählte Protokoll für Verbindungen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="30d79-121">This allows you to decrease the priority in which the Net-Library will attempt to use the selected protocol for connections.</span></span>  
  
 <span data-ttu-id="30d79-122">**Shared Memory-Protokoll aktivieren**</span><span class="sxs-lookup"><span data-stu-id="30d79-122">**Enable Shared Memory Protocol**</span></span>  
 <span data-ttu-id="30d79-123">Aktiviert das Shared Memory-Protokoll. Dieses wird (falls aktiviert) immer zuerst herangezogen, wenn von einem Client eine Verbindung zu [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] auf diesem Computer hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="30d79-123">Enables the shared memory protocol which is always tried first (if enabled), when connecting to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from a client on that computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="30d79-124">Wenn das Protokoll mithilfe eines Präfix oder als Teil der Verbindungszeichenfolge angegeben ist, wird nur das angegebene Protokoll versucht.</span><span class="sxs-lookup"><span data-stu-id="30d79-124">If the protocol is specified through a prefix or as part of the connection string, only the specified protocol is attempted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30d79-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="30d79-125">See Also</span></span>  
 [<span data-ttu-id="30d79-126">Auswählen eines Netzwerkprotokolls</span><span class="sxs-lookup"><span data-stu-id="30d79-126">Choosing a Network Protocol</span></span>](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md)  
  
  
