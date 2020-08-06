---
title: Erstellen eines Datenbankspiegelungs-Endpunkts für AlwaysOn-Verfügbarkeitsgruppen (SQL Server PowerShell) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], server instance
- Availability Groups [SQL Server], deploying
- Availability Groups [SQL Server], endpoint
ms.assetid: 6197bbe7-67d4-446d-ba5f-cabfa5df77f1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 56058ff8aa72d2471381dd87fb25a3b68356ed36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727113"
---
# <a name="create-a-database-mirroring-endpoint-for-alwayson-availability-groups-sql-server-powershell"></a><span data-ttu-id="4a9ed-102">Erstellen eines Datenbankspiegelungs-Endpunkts für AlwaysOn-Verfügbarkeitsgruppen (SQL Server PowerShell)</span><span class="sxs-lookup"><span data-stu-id="4a9ed-102">Create a Database Mirroring Endpoint for AlwaysOn Availability Groups (SQL Server PowerShell)</span></span>
  <span data-ttu-id="4a9ed-103">In diesem Thema wird beschrieben, wie ein Datenbankspiegelungs-Endpunkt zur Verwendung durch [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mit PowerShell erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="4a9ed-103">This topic describes how to create a database mirroring endpoint for use by [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using PowerShell.</span></span>  
  
 <span data-ttu-id="4a9ed-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="4a9ed-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4a9ed-105">**Vorbereitungen:**  [Sicherheit](#Security)</span><span class="sxs-lookup"><span data-stu-id="4a9ed-105">**Before you begin:**  [Security](#Security)</span></span>  
  
-   <span data-ttu-id="4a9ed-106">**So erstellen Sie einen Datenbankspiegelungs-Endpunkt mit:**  [PowerShell](#PowerShellProcedure)</span><span class="sxs-lookup"><span data-stu-id="4a9ed-106">**To create a database mirroring endpoint, using:**  [PowerShell](#PowerShellProcedure)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="4a9ed-107">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="4a9ed-107">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4a9ed-108">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="4a9ed-108">Security</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4a9ed-109">Der RC4-Algorithmus ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="4a9ed-109">The RC4 algorithm is deprecated.</span></span> [!INCLUDE[ssNoteDepFutureDontUse](../../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="4a9ed-110">Stattdessen wird die Verwendung von AES empfohlen.</span><span class="sxs-lookup"><span data-stu-id="4a9ed-110">We recommend that you use AES.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4a9ed-111">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="4a9ed-111">Permissions</span></span>  
 <span data-ttu-id="4a9ed-112">Erfordert die CREATE ENDPOINT-Berechtigung oder die Mitgliedschaft in der festen Serverrolle "sysadmin".</span><span class="sxs-lookup"><span data-stu-id="4a9ed-112">Requires CREATE ENDPOINT permission, or membership in the sysadmin fixed server role.</span></span> <span data-ttu-id="4a9ed-113">Weitere Informationen finden Sie unter [GRANT (Endpunktberechtigungen) &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4a9ed-113">For more information, see [GRANT Endpoint Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql).</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="4a9ed-114">Verwenden von PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a9ed-114">Using PowerShell</span></span>  
 <span data-ttu-id="4a9ed-115">**So erstellen Sie einen Datenbankspiegelungs-Endpunkt**</span><span class="sxs-lookup"><span data-stu-id="4a9ed-115">**To create a database mirroring endpoint**</span></span>  
  
1.  <span data-ttu-id="4a9ed-116">Ändern Sie das Verzeichnis (`cd`) zur Serverinstanz, für die Sie den Datenbankspiegelungs-Endpunkt erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="4a9ed-116">Change directory (`cd`) to the server instance for which you want to create the database mirroring endpoint.</span></span>  
  
2.  <span data-ttu-id="4a9ed-117">Verwenden Sie das `New-SqlHadrEndpoint`-Cmdlet, um den Endpunkt zu erstellen, und dann das `Set-SqlHadrEndpoint`-Cmdlet, um den Endpunkt zu starten.</span><span class="sxs-lookup"><span data-stu-id="4a9ed-117">Use the `New-SqlHadrEndpoint` cmdlet to create the endpoint and then use the `Set-SqlHadrEndpoint` to start the endpoint.</span></span>  
  
###  <a name="example-powershell"></a><a name="PShellExample"></a> <span data-ttu-id="4a9ed-118">Beispiel (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="4a9ed-118">Example (PowerShell)</span></span>  
 <span data-ttu-id="4a9ed-119">Mit den folgenden PowerShell-Befehlen wird ein Datenbankspiegelungs-Endpunkt auf einer Instanz von SQL Server (*Computer* \\ *Instanz*) erstellt.</span><span class="sxs-lookup"><span data-stu-id="4a9ed-119">The following PowerShell commands create a database mirroring endpoint on an instance of SQL Server (*Machine*\\*Instance*).</span></span> <span data-ttu-id="4a9ed-120">Der Endpunkt verwendet Port 5022.</span><span class="sxs-lookup"><span data-stu-id="4a9ed-120">The endpoint uses port 5022.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4a9ed-121">Dieses Beispiel funktioniert nur auf einer Serverinstanz, die derzeit keinen Datenbankspiegelungs-Endpunkt hat.</span><span class="sxs-lookup"><span data-stu-id="4a9ed-121">This example works only on a server instance that currently lack a database mirroring endpoint.</span></span>  
  
```powershell
# Create the endpoint.  
$endpoint = New-SqlHadrEndpoint MyMirroringEndpoint -Port 5022 -Path SQLSERVER:\SQL\Machine\Instance  
  
# Start the endpoint  
Set-SqlHadrEndpoint -InputObject $endpoint -State "Started"
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="4a9ed-122">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="4a9ed-122">Related Tasks</span></span>  
 <span data-ttu-id="4a9ed-123">**So konfigurieren Sie einen Datenbankspiegelungs-Endpunkt**</span><span class="sxs-lookup"><span data-stu-id="4a9ed-123">**To Configure a Database Mirroring Endpoint**</span></span>  
  
-   [<span data-ttu-id="4a9ed-124">Erstellen eines Endpunkts der Datenbankspiegelung für Windows-Authentifizierung &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4a9ed-124">Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md)  
  
-   [<span data-ttu-id="4a9ed-125">Verwenden von Zertifikaten für einen Datenbankspiegelungs-Endpunkt &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4a9ed-125">Use Certificates for a Database Mirroring Endpoint &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/use-certificates-for-a-database-mirroring-endpoint-transact-sql.md)  
  
    -   [<span data-ttu-id="4a9ed-126">Ermöglichen des Verwendens von Zertifikaten für ausgehende Verbindungen für einen Datenbankspiegelungs-Endpunkt &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4a9ed-126">Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/database-mirroring-use-certificates-for-outbound-connections.md)  
  
    -   [<span data-ttu-id="4a9ed-127">Ermöglichen des Verwendens von Zertifikaten für eingehende Verbindungen für einen Datenbankspiegelungs-Endpunkt &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4a9ed-127">Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/database-mirroring-use-certificates-for-inbound-connections.md)  
  
-   [<span data-ttu-id="4a9ed-128">Angeben einer Servernetzwerkadresse &#40;Datenbankspiegelung&#41;</span><span class="sxs-lookup"><span data-stu-id="4a9ed-128">Specify a Server Network Address &#40;Database Mirroring&#41;</span></span>](../../database-mirroring/specify-a-server-network-address-database-mirroring.md)  
  
-   [<span data-ttu-id="4a9ed-129">Angeben der Endpunkt-URL beim Hinzufügen oder Ändern eines Verfügbarkeitsreplikats &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4a9ed-129">Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;</span></span>](specify-endpoint-url-adding-or-modifying-availability-replica.md)  
  
 <span data-ttu-id="4a9ed-130">**So zeigen Sie Informationen zum Datenbankspiegelungs-Endpunkt an**</span><span class="sxs-lookup"><span data-stu-id="4a9ed-130">**To View Information About the Database Mirroring Endpoint**</span></span>  
  
-   [<span data-ttu-id="4a9ed-131">sys.database_mirroring_endpoints &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4a9ed-131">sys.database_mirroring_endpoints &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-mirroring-endpoints-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="4a9ed-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4a9ed-132">See Also</span></span>  
 <span data-ttu-id="4a9ed-133">[Erstellen einer Verfügbarkeits Gruppe &#40;Transact-SQL-&#41;](create-an-availability-group-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="4a9ed-133">[Create an Availability Group &#40;Transact-SQL&#41;](create-an-availability-group-transact-sql.md) </span></span>  
 [<span data-ttu-id="4a9ed-134">Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4a9ed-134">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
