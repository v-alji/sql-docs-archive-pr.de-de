---
title: Herstellen einer Verbindung mit einer beliebigen SQL Server Komponente von SQL Server Management Studio | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- connections [SQL Server], SQL Server Management Studio
- saving connections
- components [SQL Server], connections
- SQL Server Management Studio [SQL Server], connections
ms.assetid: 5eeb41bd-b25b-4d3b-a005-a7d9e4b5978e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9cd3e185ea6f289a2a6db46cdca2cb310fefbcf9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717254"
---
# <a name="connect-to-any-sql-server-component-from-sql-server-management-studio"></a><span data-ttu-id="b638e-102">Herstellen einer Verbindung mit einer beliebigen SQL Server-Komponente aus SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b638e-102">Connect to Any SQL Server Component from SQL Server Management Studio</span></span>
  [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="b638e-103">stellt die Funktionalität zum Verwalten aller Komponenten von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]bereit.</span><span class="sxs-lookup"><span data-stu-id="b638e-103">provides functionality for managing every component of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b638e-104">Mit [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] können Sie eine Verbindung zu folgenden Komponenten herstellen:</span><span class="sxs-lookup"><span data-stu-id="b638e-104">Use [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] to connect to:</span></span>  
  
-   <span data-ttu-id="b638e-105">Eine Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b638e-105">An instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="b638e-106">[https://login.microsoftonline.com/consumers/]([!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="b638e-106">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="b638e-107">[https://login.microsoftonline.com/consumers/]([!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="b638e-107">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="b638e-108">[https://login.microsoftonline.com/consumers/]([!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="b638e-108">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="b638e-109">Obwohl [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] es Ihnen ermöglicht, mit Abfragen zu arbeiten, ohne zuerst eine Verbindung mit einer Datenquelle herzustellen, ist für die meisten anderen Aufgaben eine Verbindung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b638e-109">Although [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] allows you to work with queries without first establishing a connection to a data source, most other tasks require a connection.</span></span> [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] <span data-ttu-id="b638e-110">stellt das Dialogfeld **Verbindung mit Server herstellen** bereit, um Verbindungseigenschaften für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Komponenten zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b638e-110">provides the **Connect to Server** dialog box to configure connection properties to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components.</span></span> <span data-ttu-id="b638e-111">Wenn [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] gestartet wird, wird das Dialogfeld **Verbindung mit Server herstellen** geöffnet, und Sie werden aufgefordert, eine Verbindung mit einem Server herzustellen.</span><span class="sxs-lookup"><span data-stu-id="b638e-111">When [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] starts, it opens the **Connect to Server** dialog box and prompts you to connect to a server.</span></span> <span data-ttu-id="b638e-112">Das Dialogfeld **Verbindung mit Server herstellen** behält die Verbindungseinstellungen vom vorherigen Mal bei.</span><span class="sxs-lookup"><span data-stu-id="b638e-112">The **Connect to Server** dialog box retains the connection settings from the last time it was used.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b638e-113">Diese Funktion lässt sich deaktivieren, sodass keine automatische Initialisierung einer Verbindung stattfindet.</span><span class="sxs-lookup"><span data-stu-id="b638e-113">This feature can be turned off so no connection is automatically initiated.</span></span> <span data-ttu-id="b638e-114">Weitere Informationen finden Sie unter [Startoptionen für den Datenbank-Engine-Dienst](../../database-engine/configure-windows/database-engine-service-startup-options.md).</span><span class="sxs-lookup"><span data-stu-id="b638e-114">For more information, see [Database Engine Service Startup Options](../../database-engine/configure-windows/database-engine-service-startup-options.md).</span></span>  
  
## <a name="saving-connections"></a><span data-ttu-id="b638e-115">Speichern von Verbindungen</span><span class="sxs-lookup"><span data-stu-id="b638e-115">Saving Connections</span></span>  
 <span data-ttu-id="b638e-116">Sie können Verbindungen mit bestimmten Servern in der Liste der registrierten Server speichern, oder Sie können mit dem Projektmappen-Explorer Verbindungen in Projekten speichern.</span><span class="sxs-lookup"><span data-stu-id="b638e-116">You can save connections to specific servers in Registered Servers, or you can save connections in projects with Solution Explorer.</span></span>  
  
### <a name="saving-connections-in-registered-servers"></a><span data-ttu-id="b638e-117">Speichern von Verbindungen in der Liste der registrierten Server</span><span class="sxs-lookup"><span data-stu-id="b638e-117">Saving Connections in Registered Servers</span></span>  
 <span data-ttu-id="b638e-118">Wenn Sie einen Server registrieren, speichert [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] die Verbindungsinformationen in der Liste der registrierten Server.</span><span class="sxs-lookup"><span data-stu-id="b638e-118">When you register a server, [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] saves the connection information in Registered Servers.</span></span> <span data-ttu-id="b638e-119">Um eine Verbindung mit einem registrierten Server herzustellen, doppelklicken Sie in der Liste der registrierten Server auf den Servernamen.</span><span class="sxs-lookup"><span data-stu-id="b638e-119">To connect to a registered server, double-click the server name in Registered Servers.</span></span> <span data-ttu-id="b638e-120">Daraufhin öffnet der Objekt-Explorer eine Verbindung zum Server.</span><span class="sxs-lookup"><span data-stu-id="b638e-120">Object Explorer then opens a connection to the server.</span></span>  
  
### <a name="saving-connections-in-solution-explorer"></a><span data-ttu-id="b638e-121">Speichern von Verbindungen im Projektmappen-Explorer</span><span class="sxs-lookup"><span data-stu-id="b638e-121">Saving Connections in Solution Explorer</span></span>  
 <span data-ttu-id="b638e-122">Mit dem Projektmappen-Explorer können Sie zugehörige Abfragen, Skripts, Verbindungen und andere Informationen in einem Projekt speichern.</span><span class="sxs-lookup"><span data-stu-id="b638e-122">Solution Explorer allows you to store related queries, scripts, connections, and other associated information in a project.</span></span> <span data-ttu-id="b638e-123">Jedes Skriptprojekt enthält einen Knoten namens **Verbindungen**, in dem Sie eine oder mehrere Verbindungen speichern können.</span><span class="sxs-lookup"><span data-stu-id="b638e-123">Each script project contains a node called **Connections**, where you can save one or more connections.</span></span> <span data-ttu-id="b638e-124">Klicken Sie zum Hinzufügen einer Verbindung mit der rechten Maustaste auf **Verbindungen**, und klicken Sie dann auf **Neue Verbindung**.</span><span class="sxs-lookup"><span data-stu-id="b638e-124">To add a connection, right-click **Connections**, and then click **New Connection**.</span></span> <span data-ttu-id="b638e-125">Erweitern Sie zum Zugreifen auf eine gespeicherte Verbindung **Verbindungen** , und doppelklicken Sie auf die Verbindung.</span><span class="sxs-lookup"><span data-stu-id="b638e-125">To access a saved connection, expand **Connections** and double-click the connection.</span></span> [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] <span data-ttu-id="b638e-126">öffnet ein dieser Verbindung zugeordnetes Abfragefenster.</span><span class="sxs-lookup"><span data-stu-id="b638e-126">opens a query window associated with that connection.</span></span> <span data-ttu-id="b638e-127">Beim Speichern behalten Skripts die Verknüpfung zu einer bestimmten Verbindung bei.</span><span class="sxs-lookup"><span data-stu-id="b638e-127">When saved, scripts retain their association to a specific connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b638e-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b638e-128">See Also</span></span>  
 <span data-ttu-id="b638e-129">[SQL Server Management Studio verwenden](../sql-server-management-studio-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="b638e-129">[Use SQL Server Management Studio](../sql-server-management-studio-ssms.md) </span></span>  
 [<span data-ttu-id="b638e-130">Objekt-Explorers</span><span class="sxs-lookup"><span data-stu-id="b638e-130">Object Explorer</span></span>](../object/object-explorer.md)  
  
  
