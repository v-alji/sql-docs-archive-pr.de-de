---
title: Konfigurieren von Clientprotokollen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- default protocols
- network protocols [SQL Server], client configuration
- TCP/IP [SQL Server], client protocols
- disabling client protocols
- ordering protocols [SQL Server]
- protocols [SQL Server], order for client computers
- configure client protocols
- client protocols [SQL Server]
- protocols [SQL Server], client configuration
ms.assetid: 3dfa2702-ba65-43b4-a777-6727846e133a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2eb223815c3e3af50813e02d3ded60573c327155
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622895"
---
# <a name="configure-client-protocols"></a><span data-ttu-id="d4f91-102">Konfigurieren von Clientprotokollen</span><span class="sxs-lookup"><span data-stu-id="d4f91-102">Configure Client Protocols</span></span>
  <span data-ttu-id="d4f91-103">In diesem Thema wird die Konfiguration von Clientprotokollen beschrieben, die mithilfe des [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]-Konfigurations-Managers von Clientanwendungen in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d4f91-103">This topic describes how to configure client protocols used by client applications in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="d4f91-104">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] unterstützt die Clientkommunikation mit TCP/IP und dem Named Pipes-Protokoll.</span><span class="sxs-lookup"><span data-stu-id="d4f91-104">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] supports client communication with the TCP/IP network protocol and the named pipes protocol.</span></span> <span data-ttu-id="d4f91-105">Auch das Shared Memory-Protokoll steht zur Verfügung, wenn der Client eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz auf demselben Computer herstellt.</span><span class="sxs-lookup"><span data-stu-id="d4f91-105">The shared memory protocol is also available if the client is connecting to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] on the same computer.</span></span> <span data-ttu-id="d4f91-106">Zum Auswählen des Protokolls stehen drei allgemeine Methoden zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="d4f91-106">There are three common methods of selecting the protocol.</span></span>  
  
-   <span data-ttu-id="d4f91-107">Das Konfigurieren aller Clientanwendungen für dasselbe Netzwerkprotokoll durch Festlegen der Protokollreihenfolge im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager.</span><span class="sxs-lookup"><span data-stu-id="d4f91-107">Configure all client applications to use the same network protocol by setting the protocol order in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
-   <span data-ttu-id="d4f91-108">Das Konfigurieren einer einzelnen Clientanwendung zum Verwenden eines anderen Netzwerkprotokolls durch Erstellen eines Alias.</span><span class="sxs-lookup"><span data-stu-id="d4f91-108">Configure a single client application to use a different network protocol by creating an alias.</span></span> <span data-ttu-id="d4f91-109">Weitere Informationen finden Sie unter [Erstellen oder Löschen eines Serveralias für die Verwendung durch einen Client &#40;SQL Server-Konfigurations-Manager&#41;](create-or-delete-a-server-alias-for-use-by-a-client.md).</span><span class="sxs-lookup"><span data-stu-id="d4f91-109">For more information, see [Create or Delete a Server Alias for Use by a Client &#40;SQL Server Configuration Manager&#41;](create-or-delete-a-server-alias-for-use-by-a-client.md).</span></span>  
  
-   <span data-ttu-id="d4f91-110">In einigen Clientanwendungen, beispielsweise sqlcmd.exe, kann das Protokoll als Teil der Verbindungszeichenfolge angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d4f91-110">Some client applications, such as sqlcmd.exe, can specify the protocol as part of the connection string.</span></span> <span data-ttu-id="d4f91-111">Weitere Informationen finden Sie unter [Herstellen einer Verbindung mit der Datenbank-Engine mithilfe von sqlcmd](../../relational-databases/scripting/sqlcmd-connect-to-the-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="d4f91-111">For more information, see [Connect to the Database Engine With sqlcmd](../../relational-databases/scripting/sqlcmd-connect-to-the-database-engine.md).</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d4f91-112">Verwenden des SQL Server-Konfigurations-Managers</span><span class="sxs-lookup"><span data-stu-id="d4f91-112">Using SQL Server Configuration Manager</span></span>  
  
###  <a name="to-enable-or-disable-a-client-protocol"></a><a name="EnableDisable"></a> <span data-ttu-id="d4f91-113">So aktivieren oder deaktivieren Sie ein Clientprotokoll</span><span class="sxs-lookup"><span data-stu-id="d4f91-113">To enable or disable a client protocol</span></span>  
  
1.  <span data-ttu-id="d4f91-114">Erweitern Sie im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Konfigurations-Manager **SQL Server Native Client-Konfiguration**, klicken Sie mit der rechten Maustaste auf **Clientprotokolle**, und klicken Sie anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="d4f91-114">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, expand **SQL Server Native Client Configuration**, right-click **Client Protocols**, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="d4f91-115">Um ein Protokoll zu aktivieren, klicken Sie auf das gewünschte Protokoll im Feld **Deaktivierte Protokolle** , und klicken Sie dann auf **Aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="d4f91-115">Click a protocol in the **Disabled Protocols** box, and then click **Enable**, to enable a protocol.</span></span>  
  
3.  <span data-ttu-id="d4f91-116">Um ein Protokoll zu deaktivieren, klicken Sie auf das gewünschte Protokoll im Feld **Aktivierte Protokolle** , und klicken Sie dann auf **Deaktivieren**.</span><span class="sxs-lookup"><span data-stu-id="d4f91-116">Click a protocol in the **Enabled Protocols** box, and then click **Disable**, to disable a protocol.</span></span>  
  
###  <a name="to-change-the-default-protocol-or-the-protocol-order-for-client-computers"></a><a name="ChangeDefault"></a> <span data-ttu-id="d4f91-117">So ändern Sie das Standardprotokoll oder die Protokollreihenfolge für Clientcomputer</span><span class="sxs-lookup"><span data-stu-id="d4f91-117">To change the default protocol or the protocol order for client computers</span></span>  
  
1.  <span data-ttu-id="d4f91-118">Erweitern Sie im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Konfigurations-Manager **SQL Server Native Client-Konfiguration**, klicken Sie mit der rechten Maustaste auf **Clientprotokolle**, und klicken Sie anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="d4f91-118">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, expand **SQL Server Native Client Configuration**, right-click **Client Protocols**, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="d4f91-119">Soll die Reihenfolge der Protokolle beim Aufbauen einer Verbindung mit **geändert werden, klicken Sie im Feld** Aktivierte Protokolle **auf** Nach oben **bzw.** Nach unten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d4f91-119">In the **Enabled Protocols** box, click **Move Up** or **Move Down**, to change the order in which protocols are tried, when attempting to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d4f91-120">Das obere Protokoll im Feld **Aktivierte Protokolle** ist das Standardprotokoll.</span><span class="sxs-lookup"><span data-stu-id="d4f91-120">The top protocol in the **Enabled Protocols** box is the default protocol.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="d4f91-121">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Konfigurations-Manager erstellt Registrierungseinträge für die Serveraliaskonfigurationen und die Standard-Netzwerkbibliothek des Clients.</span><span class="sxs-lookup"><span data-stu-id="d4f91-121">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager creates registry entries for the server alias configurations and default client network library.</span></span> <span data-ttu-id="d4f91-122">Die Anwendung installiert jedoch weder die Clientnetzwerkbibliotheken noch die Netzwerkprotokolle von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d4f91-122">However, the application does not install either the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client network libraries or the network protocols.</span></span> <span data-ttu-id="d4f91-123">Die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Clientnetzwerkbibliotheken werden im Rahmen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup installiert. Die Netzwerkprotokolle werden im Rahmen von Microsoft Windows Setup installiert (oder über die Anwendung **Netzwerk** in der **Systemsteuerung**).</span><span class="sxs-lookup"><span data-stu-id="d4f91-123">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client network libraries are installed during [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup; the network protocols are installed as part of Microsoft Windows Setup (or through **Networks** in **Control Panel**).</span></span> <span data-ttu-id="d4f91-124">Als Teil von Windows Setup steht möglicherweise kein spezielles Netzwerkprotokoll zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="d4f91-124">A particular network protocol may not be available as part of Windows Setup.</span></span> <span data-ttu-id="d4f91-125">Weitere Informationen zum Installieren dieser Netzwerkprotokolle finden Sie in der Dokumentation des Herstellers.</span><span class="sxs-lookup"><span data-stu-id="d4f91-125">For more information about installing these network protocols, see the vendor documentation.</span></span>  
  
###  <a name="to-configure-a-client-to-use-tcpip"></a><a name="Configure"></a> <span data-ttu-id="d4f91-126">So konfigurieren Sie einen Client für die Verwendung von TCP/IP</span><span class="sxs-lookup"><span data-stu-id="d4f91-126">To configure a client to use TCP/IP</span></span>  
  
1.  <span data-ttu-id="d4f91-127">Erweitern Sie im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Konfigurations-Manager **SQL Server Native Client-Konfiguration**, klicken Sie mit der rechten Maustaste auf **Clientprotokolle**, und klicken Sie anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="d4f91-127">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, expand **SQL Server Native Client Configuration**, right-click **Client Protocols**, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="d4f91-128">Klicken Sie im Feld **Aktivierte Protokolle** auf die Pfeile, um die Reihenfolge zu ändern, in der mit den Protokollen versucht werden soll, eine Verbindung zu SQL Server herzustellen.</span><span class="sxs-lookup"><span data-stu-id="d4f91-128">In the **Enabled Protocols** box, click the up and down arrows to change the order in which protocols are tried, when attempting to connect to SQL Server.</span></span> <span data-ttu-id="d4f91-129">Das obere Protokoll im Feld **Aktivierte Protokolle** ist das Standardprotokoll.</span><span class="sxs-lookup"><span data-stu-id="d4f91-129">The top protocol in the **Enabled Protocols** box is the default protocol.</span></span>  
  
 <span data-ttu-id="d4f91-130">Das Shared Memory-Protokoll wird getrennt durch Aktivieren des Kästchens **Shared Memory-Protokoll aktivieren** aktiviert.</span><span class="sxs-lookup"><span data-stu-id="d4f91-130">The shared memory protocol is enabled separately by checking the **Enabled Shared Memory Protocol** box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4f91-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d4f91-131">See Also</span></span>  
 [<span data-ttu-id="d4f91-132">Konfigurieren des Timeouts für Remoteanmeldungen (Serverkonfigurationsoption)</span><span class="sxs-lookup"><span data-stu-id="d4f91-132">Configure the remote login timeout Server Configuration Option</span></span>](configure-the-remote-login-timeout-server-configuration-option.md)  
  
  
