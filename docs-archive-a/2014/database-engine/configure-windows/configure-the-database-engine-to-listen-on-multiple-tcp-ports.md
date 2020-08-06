---
title: Konfigurieren der Datenbank-Engine zum Überwachen mehrerer TCP-Ports | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- ports [SQL Server], multiple
- TDS
- listen on multiple ports
- endpoints [SQL Server], TDS
- adding ports
- tabular data stream
- multiple ports
ms.assetid: 8e955033-06ef-403f-b813-3d8241b62f1f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ab803bcaa5ab6b6187c1a994abef02f81ae105c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609442"
---
# <a name="configure-the-database-engine-to-listen-on-multiple-tcp-ports"></a><span data-ttu-id="1323a-102">Konfigurieren der Datenbank-Engine zum Überwachen mehrerer TCP-Ports</span><span class="sxs-lookup"><span data-stu-id="1323a-102">Configure the Database Engine to Listen on Multiple TCP Ports</span></span>
  <span data-ttu-id="1323a-103">In diesem Thema wird beschrieben, wie Sie [!INCLUDE[ssDE](../../includes/ssde-md.md)] konfigurieren können, um auf mehreren TCP-Ports in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe des SQL Server-Konfigurations-Managers lauschen zu können.</span><span class="sxs-lookup"><span data-stu-id="1323a-103">This topic describes how to configure the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to listen on multiple TCP ports in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="1323a-104">Wenn TCP/IP für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]aktiviert wird, überwacht der [!INCLUDE[ssDE](../../includes/ssde-md.md)] eingehende Verbindungen auf einem Verbindungspunkt, der aus der IP-Adresse und der TCP-Portnummer besteht. Die folgenden Prozeduren erstellen einen Tabular Data Stream-Endpunkt (TDS), damit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] auf einem zusätzlichen TCP-Port lauschen kann.</span><span class="sxs-lookup"><span data-stu-id="1323a-104">When TCP/IP is enabled for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the [!INCLUDE[ssDE](../../includes/ssde-md.md)] will listen for incoming connections on a connection point consisting of an IP address and TCP port number.The following procedures create a tabular data stream (TDS) endpoint, so that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will listen on an additional TCP port.</span></span>  
  
 <span data-ttu-id="1323a-105">Die folgenden Gründe kommen für das Erstellen eines zweiten TDS-Endpunkts in Betracht:</span><span class="sxs-lookup"><span data-stu-id="1323a-105">Possible reasons to create a second TDS endpoint include:</span></span>  
  
-   <span data-ttu-id="1323a-106">Erhöhen der Sicherheit durch Konfigurieren der Firewall zum Einschränken des Zugriffs auf den Standardendpunkt auf lokale Clientcomputer in einem bestimmten Teilnetz.</span><span class="sxs-lookup"><span data-stu-id="1323a-106">Increase security by configuring the firewall to restrict access to the default endpoint to local client computers on a specific subnet.</span></span> <span data-ttu-id="1323a-107">Verwalten des Internetzugriffs auf [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] durch Ihr Supportteam durch Erstellen eines neuen Endpunkts, den die Firewall im Internet verfügbar macht, und Einschränken der Verbindungsrechte für diesen Endpunkt auf Ihr Serversupportteam.</span><span class="sxs-lookup"><span data-stu-id="1323a-107">Maintain Internet access to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for your support team by creating a new endpoint that the firewall exposes to the Internet, and restricting connection rights to this endpoint to your server support team.</span></span>  
  
-   <span data-ttu-id="1323a-108">Zuordnen von Verbindungen zu bestimmten Prozessoren, wenn NUMA (Non-Uniform Memory Access) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1323a-108">Affinitizing connections to specific processors when using Non-Uniform Memory Access (NUMA).</span></span>  
  
 <span data-ttu-id="1323a-109">Das Konfigurieren eines TDS-Endpunkts besteht aus den folgenden Schritten, die in beliebiger Reihenfolge ausgeführt werden können:</span><span class="sxs-lookup"><span data-stu-id="1323a-109">Configuring a TDS endpoint consists of the following steps, which can be done in any order:</span></span>  
  
-   <span data-ttu-id="1323a-110">Erstellen des TDS-Endpunkts für den TCP-Port und ggf. Wiederherstellen des Zugriffs auf den Standardendpunkt.</span><span class="sxs-lookup"><span data-stu-id="1323a-110">Create the TDS endpoint for the TCP port, and restore access to the default endpoint if appropriate.</span></span>  
  
-   <span data-ttu-id="1323a-111">Erteilen des Zugriffs auf den Endpunkt für die gewünschten Serverprinzipale.</span><span class="sxs-lookup"><span data-stu-id="1323a-111">Grant access to the endpoint to the desired server principals.</span></span>  
  
-   <span data-ttu-id="1323a-112">Angeben der TCP-Portnummer für die ausgewählte IP-Adresse.</span><span class="sxs-lookup"><span data-stu-id="1323a-112">Specify the TCP port number for the selected IP address.</span></span>  
  
 <span data-ttu-id="1323a-113">Weitere Informationen zu den Standardeinstellungen der Windows-Firewall und eine Beschreibung der TCP-Ports, die sich auf Datenbank-Engine, Analysis Services, Reporting Services und Integration Services auswirken, finden Sie unter [Konfigurieren der Windows-Firewall für den SQL Server-Zugriff](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md).</span><span class="sxs-lookup"><span data-stu-id="1323a-113">For more information about the default Windows firewall settings, and a description of the TCP ports that affect the Database Engine, Analysis Services, Reporting Services, and Integration Services, see [Configure the Windows Firewall to Allow SQL Server Access](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md).</span></span>  
  
##  <a name="SSMSProcedure"></a>  
  
#### <a name="to-create-a-tds-endpoint"></a><span data-ttu-id="1323a-114">So erstellen Sie einen TDS-Endpunkt</span><span class="sxs-lookup"><span data-stu-id="1323a-114">To create a TDS endpoint</span></span>  
  
-   <span data-ttu-id="1323a-115">Geben Sie die folgende Anweisung aus, um einen Endpunkt namens **CustomConnection** für Port 1500 für alle verfügbaren TCP-Adressen auf dem Server zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1323a-115">Issue the following statement to create an endpoint named **CustomConnection** for port 1500 for all available TCP addresses on the server.</span></span>  
  
    ```  
    USE master;  
    GO  
    CREATE ENDPOINT [CustomConnection]  
    STATE = STARTED  
    AS TCP  
       (LISTENER_PORT = 1500, LISTENER_IP =ALL)  
    FOR TSQL() ;  
    GO  
    ```  
  
 <span data-ttu-id="1323a-116">Wenn Sie einen neuen [!INCLUDE[tsql](../../includes/tsql-md.md)] -Endpunkt erstellen, werden die Verbindungsberechtigungen für die **public** -Gruppe für den TDS-Standardendpunkt aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="1323a-116">When you create a new [!INCLUDE[tsql](../../includes/tsql-md.md)] endpoint, connect permissions for **public** are revoked for the default TDS endpoint.</span></span> <span data-ttu-id="1323a-117">Wenn der Zugriff auf die **public** -Gruppe für den Standardendpunkt erforderlich ist, wenden Sie diese Berechtigung mithilfe der `GRANT CONNECT ON ENDPOINT::[TSQL Default TCP] to [public];` -Anweisung erneut an.</span><span class="sxs-lookup"><span data-stu-id="1323a-117">If access to the **public** group is needed for the default endpoint, reapply this permission by using the `GRANT CONNECT ON ENDPOINT::[TSQL Default TCP] to [public];` statement.</span></span>  
  
#### <a name="to-grant-access-to-the-endpoint"></a><span data-ttu-id="1323a-118">So erteilen Sie Zugriff auf den Endpunkt</span><span class="sxs-lookup"><span data-stu-id="1323a-118">To grant access to the endpoint</span></span>  
  
-   <span data-ttu-id="1323a-119">Geben Sie die folgende Anweisung aus, um den Zugriff auf den **CustomConnection** -Endpunkt für die SQLSupport-Gruppe in der corp-Domäne zu erteilen.</span><span class="sxs-lookup"><span data-stu-id="1323a-119">Issue the following statement to grant access to the **CustomConnection** endpoint to the SQLSupport group in the corp domain.</span></span>  
  
    ```  
    GRANT CONNECT ON ENDPOINT::[CustomConnection] to [corp\SQLSupport] ;  
    GO  
    ```  
  
#### <a name="to-configure-the-sql-server-database-engine-to-listen-on-an-additional-tcp-port"></a><span data-ttu-id="1323a-120">So konfigurieren Sie die SQL Server-Datenbank-Engine zum Lauschen an einem zusätzlichen TCP-Port</span><span class="sxs-lookup"><span data-stu-id="1323a-120">To configure the SQL Server Database Engine to listen on an additional TCP port</span></span>  
  
1.  <span data-ttu-id="1323a-121">Erweitern Sie im SQL Server-Konfigurations-Manager den Eintrag **SQL Server-Netzwerkkonfiguration** und klicken Sie dann auf **Protokolle für** _<Instanzname>_ .</span><span class="sxs-lookup"><span data-stu-id="1323a-121">In SQL Server Configuration Manager, expand **SQL Server Network Configuration**, and then click **Protocols for**_<instance_name>_.</span></span>  
  
2.  <span data-ttu-id="1323a-122">Erweitern Sie **Protokolle für** _<Instanzname>_ , und klicken Sie dann auf **TCP/IP**.</span><span class="sxs-lookup"><span data-stu-id="1323a-122">Expand **Protocols for**_<instance_name>_, and then click **TCP/IP**.</span></span>  
  
3.  <span data-ttu-id="1323a-123">Klicken Sie im rechten Bereich mit der rechten Maustaste auf jede deaktivierte IP-Adresse, die Sie aktivieren möchten, und klicken Sie dann auf **Aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="1323a-123">In the right pane, right-click each disabled IP address that you want to enable, and then click **Enable**.</span></span>  
  
4.  <span data-ttu-id="1323a-124">Klicken Sie mit der rechten Maustaste auf **IPAll**, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="1323a-124">Right-click **IPAll**, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="1323a-125">Geben Sie im Feld **TCP-Port** die Ports ein, an denen [!INCLUDE[ssDE](../../includes/ssde-md.md)] lauschen soll; trennen Sie die einzelnen Werte dabei durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="1323a-125">In the **TCP Port** box, type the ports that you want the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to listen on, separated by commas.</span></span> <span data-ttu-id="1323a-126">Wenn in unserem Beispiel der Standardport 1433 aufgelistet ist, geben `,1500` `1433,1500` Sie ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="1323a-126">In our example, if the default port 1433 is listed, type `,1500` so the box reads `1433,1500`, and then click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1323a-127">Wenn Sie den Port nicht für alle IP-Adressen aktivieren möchten, konfigurieren Sie den zusätzlichen Port im Eigenschaftenfeld nur für die gewünschte Adresse.</span><span class="sxs-lookup"><span data-stu-id="1323a-127">If you are not enabling the port on all IP addresses, configure the additional port in the property box for only for the desired address.</span></span> <span data-ttu-id="1323a-128">Klicken Sie dann im Konsolenbereich mit der rechten Maustaste auf **TCP/IP**, klicken Sie auf **Eigenschaften**, und wählen Sie anschließend die Option **Nein** im Feld **Alle überwachen**.</span><span class="sxs-lookup"><span data-stu-id="1323a-128">Then, in the console pane, right-click **TCP/IP**, click **Properties**, and in the **Listen All** box, select **No**.</span></span>  
  
6.  <span data-ttu-id="1323a-129">Klicken Sie im linken Bereich auf **SQL Server-Dienste**.</span><span class="sxs-lookup"><span data-stu-id="1323a-129">In the left pane, click **SQL Server Services**.</span></span>  
  
7.  <span data-ttu-id="1323a-130">Klicken Sie im rechten Bereich mit der rechten Maustaste auf **SQL Server** _<Instanzname>_ , und klicken Sie dann auf **Neu starten**.</span><span class="sxs-lookup"><span data-stu-id="1323a-130">In the right pane, right-click **SQL Server**_<instance_name>_, and then click **Restart**.</span></span>  
  
     <span data-ttu-id="1323a-131">Wenn [!INCLUDE[ssDE](../../includes/ssde-md.md)] neu gestartet wird, führt das Fehlerprotokoll die Ports auf, die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] überwacht.</span><span class="sxs-lookup"><span data-stu-id="1323a-131">When the [!INCLUDE[ssDE](../../includes/ssde-md.md)] restarts, the Error log will list the ports on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is listening.</span></span>  
  
#### <a name="to-connect-to-the-new-endpoint"></a><span data-ttu-id="1323a-132">So stellen Sie eine Verbindung mit dem neuen Endpunkt her</span><span class="sxs-lookup"><span data-stu-id="1323a-132">To connect to the new endpoint</span></span>  
  
-   <span data-ttu-id="1323a-133">Geben Sie die folgende Anweisung aus, um eine Verbindung mit dem **CustomConnection** -Endpunkt der Standardinstanz von SQL Server auf dem Server namens ACCT mithilfe einer vertrauenswürdigen Verbindung herzustellen, wobei davon ausgegangen wird, dass der Benutzer ein Mitglied der [corp\SQLSupport]-Gruppe ist.</span><span class="sxs-lookup"><span data-stu-id="1323a-133">Issue the following statement to connect to the **CustomConnection** endpoint of the default instance of SQL Server on the server named ACCT, using a trusted connection, and assuming the user is a member of the [corp\SQLSupport] group.</span></span>  
  
    ```  
    sqlcmd -SACCT,1500  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1323a-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1323a-134">See Also</span></span>  
 <span data-ttu-id="1323a-135">[CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1323a-135">[CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql) </span></span>  
 <span data-ttu-id="1323a-136">[DROP ENDPOINT (Transact-SQL)](/sql/t-sql/statements/drop-endpoint-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1323a-136">[DROP ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-endpoint-transact-sql) </span></span>  
 <span data-ttu-id="1323a-137">[GRANT (Endpunktberechtigungen) (Transact-SQL)](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1323a-137">[GRANT Endpoint Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql) </span></span>  
 [<span data-ttu-id="1323a-138">Zuordnen von TCP/IP-Ports zu NUMA-Knoten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1323a-138">Map TCP IP Ports to NUMA Nodes &#40;SQL Server&#41;</span></span>](map-tcp-ip-ports-to-numa-nodes-sql-server.md)  
  
  
