---
title: Verwalten von Servern mit SQL Server Management Studio | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Management Studio [SQL Server], servers
- servers [SQL Server], administering
ms.assetid: 938bb035-e07a-4082-9f93-229d9feb6b06
author: stevestein
ms.author: sstein
ms.openlocfilehash: fb2a6b9afba7d838cf71144f88ed7866c54ad796
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722242"
---
# <a name="administer-servers-with-sql-server-management-studio"></a><span data-ttu-id="3e246-102">Verwalten von Servern mit SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3e246-102">Administer Servers with SQL Server Management Studio</span></span>
  [!INCLUDE[msCoName](../includes/msconame-md.md)]<span data-ttu-id="3e246-103">[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]ist ein umfassender integrierter Verwaltungs Client, der auf die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Server Verwaltungsanforderungen des Administrators zugeschnitten ist.</span><span class="sxs-lookup"><span data-stu-id="3e246-103">[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] is a rich, integrated administrative client designed to meet the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] administrator's server management requirements.</span></span> <span data-ttu-id="3e246-104">In [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)]werden administrative Tasks mit dem Objekt-Explorer ausgeführt, mit dem Sie eine Verbindung mit einem beliebigen Server der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Produktfamilie herstellen und dessen Inhalt grafisch dargestellt durchsuchen können.</span><span class="sxs-lookup"><span data-stu-id="3e246-104">In [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], administrative tasks are accomplished using Object Explorer, which allows you to connect to any server in the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] family and graphically browse its contents.</span></span> <span data-ttu-id="3e246-105">Ein Server kann eine Instanz von [!INCLUDE[ssDE](../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] oder [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sein.</span><span class="sxs-lookup"><span data-stu-id="3e246-105">A server can be an instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], or [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="3e246-106">Zu den Toolkomponenten von [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] zählen registrierte Server, der Objekt-Explorer, der Projektmappen-Explorer, der Vorlagen-Explorer, die Seite Details zum Objekt-Explorer und das Dokumentenfenster.</span><span class="sxs-lookup"><span data-stu-id="3e246-106">The tool components of [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] include Registered Servers, Object Explorer, Solution Explorer, Template Explorer, the Object Explorer Details page, and the document window.</span></span> <span data-ttu-id="3e246-107">Um ein Tool anzuzeigen, klicken Sie im Menü **Ansicht** auf den Namen des Tools.</span><span class="sxs-lookup"><span data-stu-id="3e246-107">To display a tool, on the **View** menu, click the tool name.</span></span> <span data-ttu-id="3e246-108">Um den Abfrage-Editor anzuzeigen, klicken Sie auf der Symbolleiste auf die Schaltfläche **Neue Abfrage** .</span><span class="sxs-lookup"><span data-stu-id="3e246-108">To display the Query Editor tool, click the **New Query** button on the toolbar.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="3e246-109">Der Netzwerkverkehr zwischen [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] und [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ist standardmäßig unverschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="3e246-109">Network traffic between [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] and [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] is unencrypted by default.</span></span> <span data-ttu-id="3e246-110">Sie sollten in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] nur mit vertraulichen Daten (einschließlich Kennwörtern) arbeiten, wenn Sie eine verschlüsselte Verbindung hergestellt haben.</span><span class="sxs-lookup"><span data-stu-id="3e246-110">Do not work with sensitive data (including passwords) in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] unless you have established an encrypted connection.</span></span> <span data-ttu-id="3e246-111">Weitere Informationen finden Sie unter [Aktivieren von verschlüsselten Verbindungen zur Datenbank-Engine &#40;SQL Server-Konfigurations-Manager&#41;](../database-engine/configure-windows/enable-encrypted-connections-to-the-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="3e246-111">For more information, see [Enable Encrypted Connections to the Database Engine &#40;SQL Server Configuration Manager&#41;](../database-engine/configure-windows/enable-encrypted-connections-to-the-database-engine.md).</span></span>  
  
 <span data-ttu-id="3e246-112">Verwenden Sie [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] für Folgendes:</span><span class="sxs-lookup"><span data-stu-id="3e246-112">Use [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] to:</span></span>  
  
-   <span data-ttu-id="3e246-113">Registrieren von Servern.</span><span class="sxs-lookup"><span data-stu-id="3e246-113">Register servers.</span></span>  
  
-   <span data-ttu-id="3e246-114">Herstellen einer Verbindung mit einer Instanz von [!INCLUDE[ssDE](../includes/ssde-md.md)], [!INCLUDE[ssAS](../includes/ssas-md.md)], [!INCLUDE[ssRS](../includes/ssrs.md)] oder [!INCLUDE[ssIS](../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e246-114">Connect to an instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)], [!INCLUDE[ssAS](../includes/ssas-md.md)], [!INCLUDE[ssRS](../includes/ssrs.md)], or [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span>  
  
-   <span data-ttu-id="3e246-115">Konfigurieren von Servereigenschaften.</span><span class="sxs-lookup"><span data-stu-id="3e246-115">Configure server properties.</span></span>  
  
-   <span data-ttu-id="3e246-116">Verwalten von Datenbank- und [!INCLUDE[ssAS](../includes/ssas-md.md)] -Objekten wie Cubes, Dimensionen und Assemblys.</span><span class="sxs-lookup"><span data-stu-id="3e246-116">Manage database and [!INCLUDE[ssAS](../includes/ssas-md.md)] objects such as cubes, dimensions, and assemblies.</span></span>  
  
-   <span data-ttu-id="3e246-117">Erstellen von Objekten wie Datenbanken, Tabellen, Cubes, Datenbankbenutzer und Anmeldenamen.</span><span class="sxs-lookup"><span data-stu-id="3e246-117">Create objects, such as databases, tables, cubes, database users, and logins.</span></span>  
  
-   <span data-ttu-id="3e246-118">Verwalten von Dateien und Dateigruppen.</span><span class="sxs-lookup"><span data-stu-id="3e246-118">Manage files and filegroups.</span></span>  
  
-   <span data-ttu-id="3e246-119">Anfügen oder Trennen von Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="3e246-119">Attach or detach databases.</span></span>  
  
-   <span data-ttu-id="3e246-120">Starten von Skriptingtools.</span><span class="sxs-lookup"><span data-stu-id="3e246-120">Launch scripting tools.</span></span>  
  
-   <span data-ttu-id="3e246-121">Verwalten der Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="3e246-121">Manage security.</span></span>  
  
-   <span data-ttu-id="3e246-122">Anzeigen von Systemprotokollen.</span><span class="sxs-lookup"><span data-stu-id="3e246-122">View system logs.</span></span>  
  
-   <span data-ttu-id="3e246-123">Überwachen der aktuellen Aktivität.</span><span class="sxs-lookup"><span data-stu-id="3e246-123">Monitor current activity.</span></span>  
  
-   <span data-ttu-id="3e246-124">Konfigurieren der Replikation.</span><span class="sxs-lookup"><span data-stu-id="3e246-124">Configure replication.</span></span>  
  
-   <span data-ttu-id="3e246-125">Verwalten von Volltextindizes.</span><span class="sxs-lookup"><span data-stu-id="3e246-125">Manage full-text indexes.</span></span>  
  
 <span data-ttu-id="3e246-126">Um [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] oder den [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Agent zu starten und zu beenden, verwenden Sie den [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Konfigurations-Manager.</span><span class="sxs-lookup"><span data-stu-id="3e246-126">To start and stop [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] or [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent, use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e246-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3e246-127">See Also</span></span>  
 <span data-ttu-id="3e246-128">[SQL Server Management Studio verwenden](../database-engine/use-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="3e246-128">[Use SQL Server Management Studio](../database-engine/use-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="3e246-129">Anzeigen oder Ändern von Servereigenschaften &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3e246-129">View or Change Server Properties &#40;SQL Server&#41;</span></span>](../database-engine/configure-windows/view-or-change-server-properties-sql-server.md)  
  
  
