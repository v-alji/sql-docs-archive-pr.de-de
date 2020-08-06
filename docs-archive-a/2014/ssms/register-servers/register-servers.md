---
title: Registrieren von Servern
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.sqlserverregisteredserver.dhelp
helpviewer_keywords:
- connections [SQL Server], registered servers
- registering servers
- servers [SQL Server], registering
- server management [SQL Server], registering servers
- server registration [SQL Server]
ms.assetid: c2a2513e-fa09-419c-99e7-a12d57c5a0db
author: markingmyname
ms.author: maghan
ms.openlocfilehash: f4b23ba127c6b000b0abbe832c4c072ada78c5e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616312"
---
# <a name="register-servers"></a><span data-ttu-id="0f978-102">Registrieren von Servern</span><span class="sxs-lookup"><span data-stu-id="0f978-102">Register Servers</span></span>
  <span data-ttu-id="0f978-103">Durch das Registrieren eines Servers in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] können Sie die Serververbindungsinformationen für zukünftige Verbindungen speichern. Es gibt drei Möglichkeiten, einen Server in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="0f978-103">Registering a server in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] allows you to store the server connection information for future connections.There are three ways to register a server in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
1.  <span data-ttu-id="0f978-104">Lokale Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] werden beim ersten Start von [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] nach der Installation automatisch registriert.</span><span class="sxs-lookup"><span data-stu-id="0f978-104">Local instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are automatically registered during the first launch of [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] after its installation.</span></span>  
  
2.  <span data-ttu-id="0f978-105">Der automatische Registrierungsprozess kann aber jederzeit gestartet werden, um die Registrierung von lokalen Serverinstanzen wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="0f978-105">You can also initiate the automatic registration process at any time, to restore the registration of local server instances.</span></span>  
  
3.  <span data-ttu-id="0f978-106">Und letztlich können Sie einen Server mit dem Tool für registrierte Server von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]registrieren.</span><span class="sxs-lookup"><span data-stu-id="0f978-106">Lastly, you can register a server using the Registered Servers tool in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="benefits-of-registered-servers"></a><span data-ttu-id="0f978-107">Vorteile von registrierten Servern</span><span class="sxs-lookup"><span data-stu-id="0f978-107">Benefits of Registered Servers</span></span>  
 <span data-ttu-id="0f978-108">Die Option "Registrierte Server" bietet folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="0f978-108">With Registered Servers you can:</span></span>  
  
-   <span data-ttu-id="0f978-109">Registrieren von Servern zum Beibehalten der Verbindungsinformationen.</span><span class="sxs-lookup"><span data-stu-id="0f978-109">Register servers to preserve the connection information.</span></span>  
  
-   <span data-ttu-id="0f978-110">Ermitteln, ob ein registrierter Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0f978-110">Determine if a registered server is running.</span></span>  
  
-   <span data-ttu-id="0f978-111">Einfaches Herstellen einer Verbindung zwischen dem Objekt-Explorer und dem Abfrage-Editor mit einem registrierten Server.</span><span class="sxs-lookup"><span data-stu-id="0f978-111">Easily connect Object Explorer and Query Editor to a registered server.</span></span>  
  
-   <span data-ttu-id="0f978-112">Bearbeiten oder Löschen der Registrierungsinformationen für einen registrierten Server.</span><span class="sxs-lookup"><span data-stu-id="0f978-112">Edit or delete the registration information for a registered server.</span></span>  
  
-   <span data-ttu-id="0f978-113">Erstellen von Servergruppen.</span><span class="sxs-lookup"><span data-stu-id="0f978-113">Create groups of servers.</span></span>  
  
-   <span data-ttu-id="0f978-114">Bereitstellen benutzerfreundlicher Namen für registrierte Server durch Angeben eines Werts im Feld **Name des registrierten Servers** , der von dem in der Liste **Servername** abweicht.</span><span class="sxs-lookup"><span data-stu-id="0f978-114">Provide user-friendly names for registered servers by providing a value in the **Registered server name** box that is different from the **Server name** list.</span></span>  
  
-   <span data-ttu-id="0f978-115">Bereitstellen detaillierter Beschreibungen für registrierte Server.</span><span class="sxs-lookup"><span data-stu-id="0f978-115">Provide detailed descriptions for registered servers.</span></span>  
  
-   <span data-ttu-id="0f978-116">Bereitstellen detaillierter Beschreibungen registrierter Servergruppen.</span><span class="sxs-lookup"><span data-stu-id="0f978-116">Provide detailed descriptions of registered server groups.</span></span>  
  
-   <span data-ttu-id="0f978-117">Exportieren registrierter Servergruppen.</span><span class="sxs-lookup"><span data-stu-id="0f978-117">Export registered server groups.</span></span>  
  
-   <span data-ttu-id="0f978-118">Importieren registrierter Servergruppen.</span><span class="sxs-lookup"><span data-stu-id="0f978-118">Import registered server groups.</span></span>  
  
-   <span data-ttu-id="0f978-119">Anzeigen der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Protokolldateien für Online- oder Offlineinstanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f978-119">View the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log files for online or offline instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="0f978-120">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="0f978-120">Related Tasks</span></span>  
 <span data-ttu-id="0f978-121">Erste Schritte mit registrierten Servern finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="0f978-121">Use the following topics to get started with registered servers:</span></span>  
  
|<span data-ttu-id="0f978-122">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="0f978-122">**Description**</span></span>|<span data-ttu-id="0f978-123">**Thema**</span><span class="sxs-lookup"><span data-stu-id="0f978-123">**Topic**</span></span>|  
|---------------------|---------------|  
|<span data-ttu-id="0f978-124">Registrieren lokaler Serverinstanzen</span><span class="sxs-lookup"><span data-stu-id="0f978-124">Register local server instances</span></span>|[<span data-ttu-id="0f978-125">Registrieren eines verbundenen Servers &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="0f978-125">Register a Connected Server &#40;SQL Server Management Studio&#41;</span></span>](register-a-connected-server-sql-server-management-studio.md)|  
|<span data-ttu-id="0f978-126">Registrieren eines Servers</span><span class="sxs-lookup"><span data-stu-id="0f978-126">Register a server</span></span>|[<span data-ttu-id="0f978-127">Erstellen eines neuen registrierten Servers &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="0f978-127">Create a New Registered Server &#40;SQL Server Management Studio&#41;</span></span>](create-a-new-registered-server-sql-server-management-studio.md)|  
|<span data-ttu-id="0f978-128">Anzeigen registrierter Server</span><span class="sxs-lookup"><span data-stu-id="0f978-128">View registered servers</span></span>|[<span data-ttu-id="0f978-129">Anzeigen von registrierten Servern in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0f978-129">View Registered Servers in SQL Server Management Studio</span></span>](view-registered-servers-in-sql-server-management-studio.md)|  
|<span data-ttu-id="0f978-130">Entfernen eines registrierten Servers</span><span class="sxs-lookup"><span data-stu-id="0f978-130">Remove a registered server</span></span>|[<span data-ttu-id="0f978-131">Entfernen eines registrierten Servers &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="0f978-131">Remove a Registered Server &#40;SQL Server Management Studio&#41;</span></span>](remove-a-registered-server-sql-server-management-studio.md)|  
|<span data-ttu-id="0f978-132">Ändern der Registrierung eines Servers</span><span class="sxs-lookup"><span data-stu-id="0f978-132">Change a server's registration</span></span>|[<span data-ttu-id="0f978-133">Ändern der Registrierung eines Servers &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="0f978-133">Change a Server's Registration &#40;SQL Server Management Studio&#41;</span></span>](change-a-server-s-registration-sql-server-management-studio.md)|  
|<span data-ttu-id="0f978-134">Herstellen einer Verbindung zu einem registrierten Server</span><span class="sxs-lookup"><span data-stu-id="0f978-134">Connect to a registered server</span></span>|[<span data-ttu-id="0f978-135">Herstellen einer Verbindung zu einem registrierten Server &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="0f978-135">Connect to a Registered Server &#40;SQL Server Management Studio&#41;</span></span>](connect-to-a-registered-server-sql-server-management-studio.md)|  
|<span data-ttu-id="0f978-136">Trennen eines registrierten Servers</span><span class="sxs-lookup"><span data-stu-id="0f978-136">Disconnect from a registered server</span></span>|[<span data-ttu-id="0f978-137">Trennen der Verbindung mit einem registrierten Server &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="0f978-137">Disconnect from a Registered Server &#40;SQL Server Management Studio&#41;</span></span>](disconnect-from-a-registered-server-sql-server-management-studio.md)|  
|<span data-ttu-id="0f978-138">Verschieben eines registrierten Servers bzw. einer registrierte Servergruppe</span><span class="sxs-lookup"><span data-stu-id="0f978-138">Move a registered server or server group</span></span>|[<span data-ttu-id="0f978-139">Verschieben eines registrierten Servers oder einer registrierten Servergruppe &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="0f978-139">Move a Registered Server or Registered Server Group &#40;SQL Server Management Studio&#41;</span></span>](move-a-registered-server-or-registered-server-group.md)|  
|<span data-ttu-id="0f978-140">Ändern des Namens eines registrierten Servers oder einer Servergruppe</span><span class="sxs-lookup"><span data-stu-id="0f978-140">Change the name of a registered server or server group</span></span>|[<span data-ttu-id="0f978-141">Ändern des Namens eines registrierten Servers oder einer registrierten Servergruppe &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="0f978-141">Change the Name of a Registered Server or Registered Server Group &#40;SQL Server Management Studio&#41;</span></span>](change-the-name-of-registered-server-or-registered-server-group.md)|  
|<span data-ttu-id="0f978-142">Erstellen oder Bearbeiten einer Servergruppe</span><span class="sxs-lookup"><span data-stu-id="0f978-142">Create or edit a server group</span></span>|[<span data-ttu-id="0f978-143">Erstellen oder Bearbeiten einer Servergruppe &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="0f978-143">Create or Edit a Server Group &#40;SQL Server Management Studio&#41;</span></span>](create-or-edit-a-server-group-sql-server-management-studio.md)|  
|<span data-ttu-id="0f978-144">Entfernen einer Servergruppe</span><span class="sxs-lookup"><span data-stu-id="0f978-144">Remove a server group</span></span>|[<span data-ttu-id="0f978-145">Entfernen einer Servergruppe &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="0f978-145">Remove a Server Group &#40;SQL Server Management Studio&#41;</span></span>](remove-a-server-group-sql-server-management-studio.md)|  
|<span data-ttu-id="0f978-146">Exportieren von Informationen zum registrierten Server</span><span class="sxs-lookup"><span data-stu-id="0f978-146">Export registered server information</span></span>|[<span data-ttu-id="0f978-147">Exportieren von Informationen zum registrierten Server &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="0f978-147">Export Registered Server Information &#40;SQL Server Management Studio&#41;</span></span>](export-registered-server-information-sql-server-management-studio.md)|  
|<span data-ttu-id="0f978-148">Importieren von Informationen zum registrierten Server</span><span class="sxs-lookup"><span data-stu-id="0f978-148">Import registered server information</span></span>|[<span data-ttu-id="0f978-149">Importieren von Informationen zum registrierten Server &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="0f978-149">Import Registered Server Information &#40;SQL Server Management Studio&#41;</span></span>](import-registered-server-information-sql-server-management-studio.md)|  
|<span data-ttu-id="0f978-150">Erstellen eines zentralen Verwaltungsservers und einer Servergruppe</span><span class="sxs-lookup"><span data-stu-id="0f978-150">Create a Central Management Server and Server Group</span></span>|[<span data-ttu-id="0f978-151">Erstellen eines zentralen Verwaltungsservers und einer Servergruppe &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="0f978-151">Create a Central Management Server and Server Group &#40;SQL Server Management Studio&#41;</span></span>](create-a-central-management-server-and-server-group.md)|  
|<span data-ttu-id="0f978-152">Gleichzeitiges Ausführen von Anweisungen für mehrere Server</span><span class="sxs-lookup"><span data-stu-id="0f978-152">Execute statements against multiple servers simultaneously</span></span>|[<span data-ttu-id="0f978-153">Gleichzeitiges Ausführen von Anweisungen für mehrere Server &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="0f978-153">Execute Statements Against Multiple Servers Simultaneously &#40;SQL Server Management Studio&#41;</span></span>](execute-statements-against-multiple-servers-simultaneously.md)|  
  
## <a name="see-also"></a><span data-ttu-id="0f978-154">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0f978-154">See Also</span></span>  
 [<span data-ttu-id="0f978-155">Remoteserver</span><span class="sxs-lookup"><span data-stu-id="0f978-155">Remote Servers</span></span>](../../database-engine/configure-windows/remote-servers.md)  
  
  
