---
title: Spiegelserverinstanz (Assistent zum Konfigurieren der Sicherheit für die Datenbankspiegelung) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.configdbmsecurwiz.mirrorsrvr.f1
ms.assetid: 53223432-615e-440f-904d-925d33ec2144
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 889e62af592d8d23f2aca0d752f1c7f535df883a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726234"
---
# <a name="mirror-server-instance-configure-database-mirroring-security-wizard"></a><span data-ttu-id="82a41-102">Spiegelserverinstanz (Assistent zum Konfigurieren der Sicherheit für die Datenbankspiegelung)</span><span class="sxs-lookup"><span data-stu-id="82a41-102">Mirror Server Instance (Configure Database Mirroring Security Wizard)</span></span>
  <span data-ttu-id="82a41-103">Auf dieser Seite können Informationen zu der Serverinstanz der Spiegeldatenbank angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="82a41-103">Use this page to specify information about the server instance with the mirror database.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="82a41-104">Die Spiegelserverinstanz muss dieselbe Edition von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)](entweder Standard oder Enterprise) als Prinzipalserverinstanz ausführen.</span><span class="sxs-lookup"><span data-stu-id="82a41-104">The mirror server instance must be running the same edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], either Standard or Enterprise, as the principal server instance.</span></span> <span data-ttu-id="82a41-105">Darüber hinaus wird die Ausführung auf vergleichbaren Systemen empfohlen, die identische Arbeitsauslastungen bewältigen können.</span><span class="sxs-lookup"><span data-stu-id="82a41-105">Also, we strongly recommend that they run on comparable systems that can handle identical workloads.</span></span>  
  
 <span data-ttu-id="82a41-106">**So konfigurieren Sie die Datenbankspiegelung mithilfe von SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="82a41-106">**To configure database mirroring by using SQL Server Management Studio**</span></span>  
  
-   [<span data-ttu-id="82a41-107">Einrichten einer Datenbank-Spiegelungssitzung mithilfe der Windows-Authentifizierung &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="82a41-107">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
-   [<span data-ttu-id="82a41-108">Starten des Assistenten zum Konfigurieren der Sicherheit für die Datenbankspiegelung &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="82a41-108">Start the Configuring Database Mirroring Security Wizard &#40;SQL Server Management Studio&#41;</span></span>](start-the-configuring-database-mirroring-security-wizard.md)  
  
## <a name="options"></a><span data-ttu-id="82a41-109">Tastatur</span><span class="sxs-lookup"><span data-stu-id="82a41-109">Options</span></span>  
 <span data-ttu-id="82a41-110">**Spiegelserverinstanz**</span><span class="sxs-lookup"><span data-stu-id="82a41-110">**Mirror server instance**</span></span>  
 <span data-ttu-id="82a41-111">Wenn bereits eine Spiegelserverinstanz angegeben ist (auf der Seite **Spiegelung** im Dialogfeld **Datenbankeigenschaften** ), wird diese Instanz angezeigt. Weitere Informationen finden Sie unter [Datenbankeigenschaften &#40;Seite Wird gespiegelt&#41;](../../relational-databases/databases/database-properties-mirroring-page.md).</span><span class="sxs-lookup"><span data-stu-id="82a41-111">If a mirror server instance is already specified (on the **Mirroring** page of the **Database Properties** dialog box), that instance is displayed; for more information, see [Database Properties &#40;Mirroring Page&#41;](../../relational-databases/databases/database-properties-mirroring-page.md).</span></span>  
  
 <span data-ttu-id="82a41-112">Geben Sie andernfalls den Namen der Spiegelserverinstanz ein.</span><span class="sxs-lookup"><span data-stu-id="82a41-112">Otherwise, enter the name of the mirror server instance.</span></span> <span data-ttu-id="82a41-113">Beachten Sie, dass die Spiegelserverinstanz nicht mit der Prinzipalserverinstanz identisch sein kann.</span><span class="sxs-lookup"><span data-stu-id="82a41-113">Note that the mirror server instance cannot be the same as the principal server instance.</span></span>  
  
 <span data-ttu-id="82a41-114">**Herstellen einer Verbindung**</span><span class="sxs-lookup"><span data-stu-id="82a41-114">**Connect**</span></span>  
 <span data-ttu-id="82a41-115">Wenn keine Spiegelserverinstanz festgelegt wurde, klicken Sie auf **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="82a41-115">If a mirror server instance has not been specified, click **Connect**.</span></span> <span data-ttu-id="82a41-116">Dadurch wird das Dialogfeld **Verbindung mit Server herstellen** angezeigt, mit dem Sie die Serverinstanz festlegen und eine Verbindung herstellen können.</span><span class="sxs-lookup"><span data-stu-id="82a41-116">This displays the **Connect to Server** dialog box in which you can specify the server instance and establish a connection.</span></span>  
  
 <span data-ttu-id="82a41-117">Klicken Sie auf **Verbinden**, wenn eine Instanz angegeben wurde, der Assistent aber keine Verbindung mit ausreichenden Berechtigungen zum Überprüfen eines vorhandenen Endpunkts herstellen konnte.</span><span class="sxs-lookup"><span data-stu-id="82a41-117">If the instance has been specified, but the wizard lacks a connection with sufficient permission to check for the existence of the endpoint, click **Connect**.</span></span> <span data-ttu-id="82a41-118">Dadurch wird das Dialogfeld **Verbindung mit Server herstellen** mit einer vorausgewählten und nicht änderbaren Serverinstanz angezeigt.</span><span class="sxs-lookup"><span data-stu-id="82a41-118">This displays the **Connect to Server** dialog box with the server instance pre-selected and unchangeable.</span></span> <span data-ttu-id="82a41-119">Geben Sie ein Domänenkonto mit ausreichender Berechtigung an, und stellen Sie eine Verbindung zur Serverinstanz her.</span><span class="sxs-lookup"><span data-stu-id="82a41-119">Specify a domain account with sufficient permission, and connect to the server instance.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="82a41-120">Beim Herstellen der Verbindung mit der Serverinstanz verwendet der Assistent zum Konfigurieren der Sicherheit für die Datenbankspiegelung die Anmeldeinformationen, die im Dialogfeld **Verbindung mit Server herstellen** bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="82a41-120">When connecting to the server instance, the Configure Database Mirroring Security Wizard uses the credentials provided in the **Connect to Server** dialog box.</span></span> <span data-ttu-id="82a41-121">Diese unterscheiden sich von den Anmeldeinformationen einer Spiegelungssitzung, bei der die Anmeldeinformationen des Startkontos verwendet werden, unter dem die Serverinstanz als Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="82a41-121">These are different from the credentials of a mirroring session, which uses the credentials of the startup account where the server instance is running as a service.</span></span>  
  
 <span data-ttu-id="82a41-122">**Listenerport**</span><span class="sxs-lookup"><span data-stu-id="82a41-122">**Listener Port**</span></span>  
 <span data-ttu-id="82a41-123">Das Verhalten dieser Option hängt auf folgende Weise davon ab, ob für diese Serverinstanz der Spiegelungsendpunkt vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="82a41-123">The behavior of this option depends on whether the mirroring endpoint exists for this server instance, as follows:</span></span>  
  
-   <span data-ttu-id="82a41-124">Wenn für die Serverinstanz ein Überwachungsport nicht vorhanden ist, wird im Textfeld **Port** die Portnummer 5022 angezeigt.</span><span class="sxs-lookup"><span data-stu-id="82a41-124">If a listener port does not exist for the server instance, port number 5022 is displayed in the **Port** text box.</span></span> <span data-ttu-id="82a41-125">Sie können jede verfügbare Portnummer verwenden, wie z. B. 7022.</span><span class="sxs-lookup"><span data-stu-id="82a41-125">You can use any available port number, such as 7022.</span></span>  
  
-   <span data-ttu-id="82a41-126">Wenn der Spiegelungsendpunkt bereits vorhanden ist, wird die Portnummer dieses Endpunkts angezeigt.</span><span class="sxs-lookup"><span data-stu-id="82a41-126">When the mirroring endpoint already exists, the port number from that endpoint is displayed.</span></span> <span data-ttu-id="82a41-127">Wenn Sie diesen Port ändern müssen, verwenden Sie den Befehl ALTER ENDPOINT.</span><span class="sxs-lookup"><span data-stu-id="82a41-127">If you need to change the port, use an ALTER ENDPOINT command.</span></span> <span data-ttu-id="82a41-128">Weitere Informationen finden Sie unter [ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="82a41-128">For more information, see [ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="82a41-129">Eine Portnummer ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="82a41-129">A port number is required.</span></span>  
  
 <span data-ttu-id="82a41-130">**Endpunkt Name**</span><span class="sxs-lookup"><span data-stu-id="82a41-130">**Endpoint name**</span></span>  
 <span data-ttu-id="82a41-131">Wenn der Spiegelungsendpunkt für diese Serverinstanz vorhanden ist, wird der Endpunktname hier angezeigt.</span><span class="sxs-lookup"><span data-stu-id="82a41-131">If the mirroring endpoint exists for this server instance, the endpoint name is displayed here.</span></span> <span data-ttu-id="82a41-132">Ist der Endpunkt nicht vorhanden, dann können Sie den Namen für den Endpunkt hier festlegen.</span><span class="sxs-lookup"><span data-stu-id="82a41-132">If the endpoint does not exist, you can specify the name of the endpoint.</span></span>  
  
 <span data-ttu-id="82a41-133">**Durch diesen Endpunkt gesendete Daten verschlüsseln**</span><span class="sxs-lookup"><span data-stu-id="82a41-133">**Encrypt data sent through this endpoint**</span></span>  
 <span data-ttu-id="82a41-134">Standardmäßig ist die Verschlüsselung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="82a41-134">By default, encryption is enabled.</span></span> <span data-ttu-id="82a41-135">Wenn diese Option aktiviert ist, dann ist die Verschlüsselung erforderlich (nicht nur unterstützt), und es werden die Standardwerte für alle Verschlüsselungsoptionen verwendet.</span><span class="sxs-lookup"><span data-stu-id="82a41-135">When enabled, encryption is required (not merely supported) and uses the default values for all of the encryption options.</span></span> <span data-ttu-id="82a41-136">Weitere Informationen finden Sie unter [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="82a41-136">For more information, see [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span></span>  
  
 <span data-ttu-id="82a41-137">Um die Verschlüsselung zu deaktivieren, deaktivieren Sie das Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="82a41-137">To disable encryption, clear the check box.</span></span> <span data-ttu-id="82a41-138">Um die Verschlüsselung wieder zu aktivieren, aktivieren Sie das Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="82a41-138">To re-enable encryption, select the check box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82a41-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="82a41-139">See Also</span></span>  
 <span data-ttu-id="82a41-140">[Der Datenbankspiegelungs-Endpunkt &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="82a41-140">[The Database Mirroring Endpoint &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span></span>  
 <span data-ttu-id="82a41-141">[Datenbankeigenschaften &#40;Seite Wird gespiegelt&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span><span class="sxs-lookup"><span data-stu-id="82a41-141">[Database Properties &#40;Mirroring Page&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span></span>  
 <span data-ttu-id="82a41-142">[Erstellen eines Endpunkts der Datenbankspiegelung für Windows-Authentifizierung (Transact-SQL)](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="82a41-142">[Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span></span>  
 <span data-ttu-id="82a41-143">[Starten des Datenbankspiegelungs-Monitors &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="82a41-143">[Start Database Mirroring Monitor &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="82a41-144">Datenbankspiegelung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="82a41-144">Database Mirroring &#40;SQL Server&#41;</span></span>](database-mirroring-sql-server.md)  
  
  
