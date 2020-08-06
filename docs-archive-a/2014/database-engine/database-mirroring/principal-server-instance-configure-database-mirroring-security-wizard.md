---
title: Prinzipalserverinstanz (Assistent zum Konfigurieren der Sicherheit für die Datenbankspiegelung) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.configdbmsecurwiz.principalsrvr.f1
ms.assetid: 58af27d7-c5dd-4669-be6b-b472bc2c8ef4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2632b5ffd5355065b4b5c1f905b3b6e5c5b6204d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701840"
---
# <a name="principal-server-instance-configure-database-mirroring-security-wizard"></a><span data-ttu-id="a852c-102">Prinzipalserverinstanz (Assistent zum Konfigurieren der Sicherheit für die Datenbankspiegelung)</span><span class="sxs-lookup"><span data-stu-id="a852c-102">Principal Server Instance (Configure Database Mirroring Security Wizard)</span></span>
  <span data-ttu-id="a852c-103">Auf dieser Seite können Informationen zur Serverinstanz der Prinzipaldatenbank angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a852c-103">Use this page to specify information about the server instance of the principal database.</span></span> <span data-ttu-id="a852c-104">Die Prinzipaldatenbank ist die Kopie der Datenbank, durch die die Spiegelungssitzung begonnen wird.</span><span class="sxs-lookup"><span data-stu-id="a852c-104">The principal database is the copy of the database that begins the mirroring session.</span></span> <span data-ttu-id="a852c-105">Nach Beginn der Sitzung ist die Prinzipaldatenbank die Kopie der Datenbank, von der Benutzeränderungen angenommen werden.</span><span class="sxs-lookup"><span data-stu-id="a852c-105">After the session has begun, the principal database is the copy of the database that accepts user changes.</span></span> <span data-ttu-id="a852c-106">(Im Falle eines Failovers werden die Prinzipal- und Spiegelungsrollen vertauscht, d. h. die ursprüngliche Prinzipaldatenbank bleibt möglicherweise nicht als Prinzipaldatenbank erhalten.)</span><span class="sxs-lookup"><span data-stu-id="a852c-106">(When a failover occurs, the principal and mirroring roles are swapped; therefore, the initial principal database might not remain the principal database.)</span></span>  
  
 <span data-ttu-id="a852c-107">**So konfigurieren Sie die Datenbankspiegelung mithilfe von SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="a852c-107">**To configure database mirroring by using SQL Server Management Studio**</span></span>  
  
-   [<span data-ttu-id="a852c-108">Einrichten einer Datenbank-Spiegelungssitzung mithilfe der Windows-Authentifizierung &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="a852c-108">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
-   [<span data-ttu-id="a852c-109">Starten des Assistenten zum Konfigurieren der Sicherheit für die Datenbankspiegelung &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="a852c-109">Start the Configuring Database Mirroring Security Wizard &#40;SQL Server Management Studio&#41;</span></span>](start-the-configuring-database-mirroring-security-wizard.md)  
  
## <a name="options"></a><span data-ttu-id="a852c-110">Tastatur</span><span class="sxs-lookup"><span data-stu-id="a852c-110">Options</span></span>  
 <span data-ttu-id="a852c-111">**Prinzipalserverinstanz**</span><span class="sxs-lookup"><span data-stu-id="a852c-111">**Principal server instance**</span></span>  
 <span data-ttu-id="a852c-112">Da eine Datenbankspiegelung in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] immer auf dem Prinzipalserver konfiguriert wird, handelt es sich bei der aktuellen Serverinstanz immer um die Prinzipalserverinstanz.</span><span class="sxs-lookup"><span data-stu-id="a852c-112">Because database mirroring in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] is always configured from the principal server, the current server instance is always the principal server instance.</span></span>  
  
 <span data-ttu-id="a852c-113">**Listenerport**</span><span class="sxs-lookup"><span data-stu-id="a852c-113">**Listener Port**</span></span>  
 <span data-ttu-id="a852c-114">Das Verhalten dieser Option hängt auf folgende Weise davon ab, ob für diese Serverinstanz der Spiegelungsendpunkt vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="a852c-114">The behavior of this option depends on whether the mirroring endpoint exists for this server instance, as follows:</span></span>  
  
-   <span data-ttu-id="a852c-115">Wenn für diese Serverinstanz der Überwachungsport nicht vorhanden ist, wird im Textfeld **Port** die Portnummer 5022 angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a852c-115">If the listener port does not exist for this server instance, port number 5022 is displayed in the **Port** text box.</span></span> <span data-ttu-id="a852c-116">Sie können jede verfügbare Portnummer verwenden, wie z. B. 7022.</span><span class="sxs-lookup"><span data-stu-id="a852c-116">You can use any available port number, such as, 7022.</span></span>  
  
-   <span data-ttu-id="a852c-117">Wenn der Spiegelungsendpunkt bereits vorhanden ist, wird die Portnummer dieses Endpunkts angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a852c-117">When the mirroring endpoint already exists, the port number from the endpoint is displayed.</span></span> <span data-ttu-id="a852c-118">Wenn Sie diesen Port ändern müssen, verwenden Sie den Befehl ALTER ENDPOINT.</span><span class="sxs-lookup"><span data-stu-id="a852c-118">If you need to change the port, use an ALTER ENDPOINT command.</span></span> <span data-ttu-id="a852c-119">Weitere Informationen finden Sie unter [ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a852c-119">For more information, see [ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a852c-120">Eine Portnummer ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a852c-120">A port number is required.</span></span>  
  
 <span data-ttu-id="a852c-121">**Endpunkt Name**</span><span class="sxs-lookup"><span data-stu-id="a852c-121">**Endpoint name**</span></span>  
 <span data-ttu-id="a852c-122">Wenn der Spiegelungsendpunkt für diese Serverinstanz vorhanden ist, wird der Endpunktname hier angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a852c-122">If the mirroring endpoint exists for this server instance, the endpoint name is displayed here.</span></span> <span data-ttu-id="a852c-123">Ist der Endpunkt nicht vorhanden, dann können Sie den Namen für den Endpunkt hier festlegen.</span><span class="sxs-lookup"><span data-stu-id="a852c-123">If the endpoint does not exist, you can specify the name of the endpoint.</span></span>  
  
 <span data-ttu-id="a852c-124">**Durch diesen Endpunkt gesendete Daten verschlüsseln**</span><span class="sxs-lookup"><span data-stu-id="a852c-124">**Encrypt data sent through this endpoint**</span></span>  
 <span data-ttu-id="a852c-125">Standardmäßig ist die Verschlüsselung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a852c-125">By default, encryption is enabled.</span></span> <span data-ttu-id="a852c-126">Wenn diese Option aktiviert ist, dann ist die Verschlüsselung erforderlich (nicht nur unterstützt), und es werden die Standardwerte für alle Verschlüsselungsoptionen verwendet.</span><span class="sxs-lookup"><span data-stu-id="a852c-126">When enabled, encryption is required (not merely supported) and uses the default values for all of the encryption options.</span></span> <span data-ttu-id="a852c-127">Weitere Informationen finden Sie unter [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a852c-127">For more information, see [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span></span>  
  
 <span data-ttu-id="a852c-128">Um die Verschlüsselung zu deaktivieren, deaktivieren Sie das Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="a852c-128">To disable encryption, clear the check box.</span></span> <span data-ttu-id="a852c-129">Um die Verschlüsselung wieder zu aktivieren, aktivieren Sie das Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="a852c-129">To re-enable encryption, select the check box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a852c-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a852c-130">See Also</span></span>  
 <span data-ttu-id="a852c-131">[Der Datenbankspiegelungs-Endpunkt &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a852c-131">[The Database Mirroring Endpoint &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span></span>  
 <span data-ttu-id="a852c-132">[Datenbankeigenschaften &#40;Seite Wird gespiegelt&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span><span class="sxs-lookup"><span data-stu-id="a852c-132">[Database Properties &#40;Mirroring Page&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span></span>  
 <span data-ttu-id="a852c-133">[Erstellen eines Endpunkts der Datenbankspiegelung für Windows-Authentifizierung (Transact-SQL)](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="a852c-133">[Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span></span>  
 <span data-ttu-id="a852c-134">[Starten des Datenbankspiegelungs-Monitors &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="a852c-134">[Start Database Mirroring Monitor &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="a852c-135">Datenbankspiegelung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a852c-135">Database Mirroring &#40;SQL Server&#41;</span></span>](database-mirroring-sql-server.md)  
  
  
