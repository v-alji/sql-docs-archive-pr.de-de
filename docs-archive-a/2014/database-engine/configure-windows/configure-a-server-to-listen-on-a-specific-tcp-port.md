---
title: Konfigurieren eines Servers für das lauschen an einem bestimmten TCP-Port (SQL Server-Konfigurations-Manager) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/22/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- fixed port
- static ports
- ports [SQL Server], assigning numbers
- assigning port numbers
- dynamic ports [SQL Server]
- TCP/IP [SQL Server], port numbers
ms.assetid: 2276a5ed-ae3f-4855-96d8-f5bf01890640
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4feb740910c65580e8ea3170d03481e6cb628860
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608853"
---
# <a name="configure-a-server-to-listen-on-a-specific-tcp-port-sql-server-configuration-manager"></a><span data-ttu-id="a4966-102">Konfigurieren eines Servers zur Überwachung eines bestimmten TCP-Ports (SQL Server-Konfigurations-Manager)</span><span class="sxs-lookup"><span data-stu-id="a4966-102">Configure a Server to Listen on a Specific TCP Port (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="a4966-103">In diesem Thema wird beschrieben, wie eine Instanz der [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] konfiguriert wird, um mit dem SQL Server-Konfigurations-Manager einen bestimmten festen Port zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="a4966-103">This topic describes how to configure an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] to listen on a specific fixed port by using the SQL Server Configuration Manager.</span></span> <span data-ttu-id="a4966-104">Falls aktiviert, überwacht die Standardinstanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] TCP-Port 1433.</span><span class="sxs-lookup"><span data-stu-id="a4966-104">If enabled, the default instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] listens on TCP port 1433.</span></span> <span data-ttu-id="a4966-105">Benannte Instanzen von [!INCLUDE[ssDE](../../includes/ssde-md.md)] und [!INCLUDE[ssEW](../../includes/ssew-md.md)] sind für dynamische Ports konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="a4966-105">Named instances of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and [!INCLUDE[ssEW](../../includes/ssew-md.md)] are configured for dynamic ports.</span></span> <span data-ttu-id="a4966-106">Dies bedeutet, dass sie einen verfügbaren Port auswählen, wenn der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Dienst gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="a4966-106">This means they select an available port when the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service is started.</span></span> <span data-ttu-id="a4966-107">Wenn Sie die Verbindung mit einer benannten Instanz über eine Firewall herstellen, konfigurieren Sie [!INCLUDE[ssDE](../../includes/ssde-md.md)] so, dass an einem bestimmten Port gelauscht wird, damit der entsprechende Port in der Firewall geöffnet werden kann.</span><span class="sxs-lookup"><span data-stu-id="a4966-107">When you are connecting to a named instance through a firewall, configure the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to listen on a specific port, so that the appropriate port can be opened in the firewall.</span></span>  
  
 <span data-ttu-id="a4966-108">Weitere Informationen zu den Standardeinstellungen der Windows-Firewall und eine Beschreibung der TCP-Ports, die sich auf Datenbank-Engine, Analysis Services, Reporting Services und Integration Services auswirken, finden Sie unter [Konfigurieren der Windows-Firewall für den SQL Server-Zugriff](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md).</span><span class="sxs-lookup"><span data-stu-id="a4966-108">For more information about the default Windows firewall settings, and a description of the TCP ports that affect the Database Engine, Analysis Services, Reporting Services, and Integration Services, see [Configure the Windows Firewall to Allow SQL Server Access](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md).</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="a4966-109">Beachten Sie bei der Auswahl von Portnummern die Liste registrierter Ports, die bestimmten Anwendungen fest zugeordnet sind. Diese Liste finden Sie auf der Website [http://www.iana.org/assignments/port-numbers](http://www.iana.org/assignments/port-numbers).</span><span class="sxs-lookup"><span data-stu-id="a4966-109">When selecting a port number, consult [http://www.iana.org/assignments/port-numbers](http://www.iana.org/assignments/port-numbers) for a list of port numbers that are assigned to specific applications.</span></span> <span data-ttu-id="a4966-110">Wählen Sie eine nicht zugewiesene Portnummer aus.</span><span class="sxs-lookup"><span data-stu-id="a4966-110">Select an unassigned port number.</span></span> <span data-ttu-id="a4966-111">Weitere Informationen finden Sie unter [Der dynamische Standardportbereich für TCP/IP hat sich in Windows Vista und Windows Server 2008 geändert](https://support.microsoft.com/kb/929851).</span><span class="sxs-lookup"><span data-stu-id="a4966-111">For more information, see [The default dynamic port range for TCP/IP has changed in Windows Vista and in Windows Server 2008](https://support.microsoft.com/kb/929851).</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="a4966-112">Nach einem Neustart lauscht die Datenbank-Engine an einem neuen Port.</span><span class="sxs-lookup"><span data-stu-id="a4966-112">The Database Engine begins listening on a new port when restarted.</span></span> <span data-ttu-id="a4966-113">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Browserdienst überwacht jedoch die Registrierung und meldet die neue Portnummer, sobald die Konfiguration geändert wird, obwohl die Portnummer von der Datenbank-Engine u. U. gar nicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a4966-113">However the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service monitors the registry and reports the new port number as soon as the configuration is changed, even though the Database Engine might not be using it.</span></span> <span data-ttu-id="a4966-114">Starten Sie die Datenbank-Engine erneut, um Konsistenz zu gewährleisten und Verbindungsfehler zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="a4966-114">Restart the Database Engine to ensure consistency and avoid connection failures.</span></span>  
  
 <span data-ttu-id="a4966-115">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="a4966-115">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a4966-116">**So konfigurieren Sie einen Server zum Lauschen an einem bestimmten TCP-Port**</span><span class="sxs-lookup"><span data-stu-id="a4966-116">**To configure a server to listen on a specific TCP port, using:**</span></span>  
  
     [<span data-ttu-id="a4966-117">SQL Server-Konfigurations-Manager</span><span class="sxs-lookup"><span data-stu-id="a4966-117">SQL Server Configuration Manager</span></span>](#SSMSProcedure)  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a4966-118">Verwenden des SQL Server-Konfigurations-Managers</span><span class="sxs-lookup"><span data-stu-id="a4966-118">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-assign-a-tcpip-port-number-to-the-sql-server-database-engine"></a><span data-ttu-id="a4966-119">So weisen Sie der SQL Server-Datenbank-Engine einen TCP/IP-Port zu</span><span class="sxs-lookup"><span data-stu-id="a4966-119">To assign a TCP/IP port number to the SQL Server Database Engine</span></span>  
  
1.  <span data-ttu-id="a4966-120">Erweitern Sie im Konsolenbereich des SQL Server-Konfigurations-Managers **SQL Server-Netzwerkkonfiguration** und **Protokolle für \<instance name>** . Klicken Sie dann doppelt auf **TCP/IP**.</span><span class="sxs-lookup"><span data-stu-id="a4966-120">In SQL Server Configuration Manager, in the console pane, expand **SQL Server Network Configuration**, expand **Protocols for \<instance name>**, and then double-click **TCP/IP**.</span></span>  
  
2.  <span data-ttu-id="a4966-121">Im Dialogfeld **TCP/IP-Eigenschaften** auf der Registerkarte **IP-Adressen** werden mehrere IP-Adressen im Format **IP1**, **IP2**und bis zu **IPAll**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a4966-121">In the **TCP/IP Properties** dialog box, on the **IP Addresses** tab, several IP addresses appear in the format **IP1**, **IP2**, up to **IPAll**.</span></span> <span data-ttu-id="a4966-122">Eine dieser Angaben ist die IP-Adresse des Loopbackadapters (127.0.0.1).</span><span class="sxs-lookup"><span data-stu-id="a4966-122">One of these is for the IP address of the loopback adapter, 127.0.0.1.</span></span> <span data-ttu-id="a4966-123">Bei den anderen IP-Adressen handelt es sich um die einzelnen IP-Adressen auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="a4966-123">Additional IP addresses appear for each IP Address on the computer.</span></span> <span data-ttu-id="a4966-124">Klicken Sie mit der rechten Maustaste auf die einzelnen Adressen, und klicken Sie dann auf **Eigenschaften**, um die IP-Adresse zu identifizieren, die Sie konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="a4966-124">Right-click each address, and then click **Properties** to identify the IP address that you want to configure.</span></span>  
  
3.  <span data-ttu-id="a4966-125">Wenn im Dialogfeld **Dynamische TCP-Ports** durch den Wert **0**angezeigt wird, dass [!INCLUDE[ssDE](../../includes/ssde-md.md)] dynamische Ports überwacht, löschen Sie die Null.</span><span class="sxs-lookup"><span data-stu-id="a4966-125">If the **TCP Dynamic Ports** dialog box contains **0**, indicating the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is listening on dynamic ports, delete the 0.</span></span>  
  
4.  <span data-ttu-id="a4966-126">Geben Sie im Dialogfeld **Eigenschaften** von **IP**_n_ im Feld **TCP-Port** die Portnummer ein, an der diese IP-Adresse lauschen soll, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a4966-126">In the **IP**_n_ **Properties** area box, in the **TCP Port** box, type the port number you want this IP address to listen on, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="a4966-127">Klicken Sie im linken Bereich auf **SQL Server-Dienste**.</span><span class="sxs-lookup"><span data-stu-id="a4966-127">In the console pane, click **SQL Server Services**.</span></span>  
  
6.  <span data-ttu-id="a4966-128">Klicken Sie im Detailbereich mit der rechten Maustaste auf **SQL Server (** \<instance name> **)** , und klicken Sie dann auf **Neu starten**, um den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Dienst zu beenden und neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="a4966-128">In the details pane, right-click **SQL Server (**\<instance name>**)** and then click **Restart**, to stop and restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="a4966-129">Nachdem Sie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] so konfiguriert haben, dass an einem bestimmten Port gelauscht wird, gibt es drei Möglichkeiten, um über die Clientanwendung eine Verbindung mit einem bestimmten Port herzustellen:</span><span class="sxs-lookup"><span data-stu-id="a4966-129">After you have configured [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to listen on a specific port, there are three ways to connect to a specific port with a client application:</span></span>  
  
-   <span data-ttu-id="a4966-130">Führen Sie auf dem Server den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Browser-Dienst aus, um die Verbindung zur Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)] nach dem Namen herzustellen.</span><span class="sxs-lookup"><span data-stu-id="a4966-130">Run the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service on the server to connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] instance by name.</span></span>  
  
-   <span data-ttu-id="a4966-131">Erstellen Sie einen Alias auf dem Client, und geben Sie die Portnummer an.</span><span class="sxs-lookup"><span data-stu-id="a4966-131">Create an alias on the client, specifying the port number.</span></span>  
  
-   <span data-ttu-id="a4966-132">Programmieren Sie den Client so, dass die Verbindung mithilfe einer benutzerdefinierten Verbindungszeichenfolge hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="a4966-132">Program the client to connect using a custom connection string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4966-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a4966-133">See Also</span></span>  
 [<span data-ttu-id="a4966-134">Erstellen oder Löschen eines Serveralias für die Verwendung durch einen Client &#40;SQL Server-Konfigurations-Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="a4966-134">Create or Delete a Server Alias for Use by a Client &#40;SQL Server Configuration Manager&#41;</span></span>](create-or-delete-a-server-alias-for-use-by-a-client.md)  
  
  
