---
title: Aktive Vorgänge (Dialog Feld) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.ssms.isoperations.executions.f1
- sql12.ssis.ssms.isoperations.general.f1
ms.assetid: 5bb0fcd6-0ce9-488a-85b8-25dddaa03cda
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 49861de7be207875c554e02d3f3b1b2f941fff64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610026"
---
# <a name="active-operations-dialog-box"></a><span data-ttu-id="202b7-102">Aktive Vorgänge (Dialogfeld)</span><span class="sxs-lookup"><span data-stu-id="202b7-102">Active Operations Dialog Box</span></span>
  <span data-ttu-id="202b7-103">Verwenden Sie das Dialogfeld **Aktive Vorgänge** , um den Status der derzeit ausgeführten [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Vorgänge auf dem [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Server anzuzeigen, z. B. Bereitstellung, Überprüfung und Paketausführung.</span><span class="sxs-lookup"><span data-stu-id="202b7-103">Use the **Active Operations** dialog box to view the status of currently running [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] operations on the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server, such as deployment, validation, and package execution.</span></span> <span data-ttu-id="202b7-104">Diese Daten werden im SSISDB-Katalog gespeichert.</span><span class="sxs-lookup"><span data-stu-id="202b7-104">This data is stored in the SSISDB catalog.</span></span>  
  
 <span data-ttu-id="202b7-105">Weitere Informationen zu verwandten [!INCLUDE[tsql](../includes/tsql-md.md)]-Ansichten finden Sie unter [catalog.operations &#40;SSISDB-Datenbank&#41;](/sql/integration-services/system-views/catalog-operations-ssisdb-database), [catalog.validations &#40;SSISDB-Datenbank&#41;](/sql/integration-services/system-views/catalog-validations-ssisdb-database) und [catalog.executions &#40;SSISDB-Datenbank&#41;](/sql/integration-services/system-views/catalog-executions-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="202b7-105">For more information about related [!INCLUDE[tsql](../includes/tsql-md.md)] views, see [catalog.operations &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-operations-ssisdb-database), [catalog.validations &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-validations-ssisdb-database), and [catalog.executions &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-executions-ssisdb-database)</span></span>  
  
 <span data-ttu-id="202b7-106">**Was möchten Sie tun?**</span><span class="sxs-lookup"><span data-stu-id="202b7-106">**What do you want to do?**</span></span>  
  
1.  [<span data-ttu-id="202b7-107">Dialog Feld "aktive Vorgänge" öffnen</span><span class="sxs-lookup"><span data-stu-id="202b7-107">Open the Active Operations Dialog Box</span></span>](#open_dialog)  
  
2.  [<span data-ttu-id="202b7-108">Konfigurieren der Optionen</span><span class="sxs-lookup"><span data-stu-id="202b7-108">Configure the Options</span></span>](#options)  
  
##  <a name="open-the-active-operations-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="202b7-109">Dialogfeld "Aktive Vorgänge" öffnen</span><span class="sxs-lookup"><span data-stu-id="202b7-109">Open the Active Operations Dialog Box</span></span>  
  
1.  <span data-ttu-id="202b7-110">Öffnen Sie [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)][!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="202b7-110">Open [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)][!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span></span>  
  
2.  <span data-ttu-id="202b7-111">Stellen Sie eine Verbindung mit einer Microsoft SQL Server-Datenbank-Engine her.</span><span class="sxs-lookup"><span data-stu-id="202b7-111">Connect Microsoft SQL Server Database Engine</span></span>  
  
3.  <span data-ttu-id="202b7-112">Erweitern Sie im Objekt-Explorer den Knoten **Integration Services** , klicken Sie mit der rechten Maustaste auf den Knoten **SSISDB**, und klicken Sie dann auf **Aktive Vorgänge**.</span><span class="sxs-lookup"><span data-stu-id="202b7-112">In Object Explorer, expand the **Integration Services** node, right-click **SSISDB**, and then click **Active Operations**.</span></span>  
  
##  <a name="configure-the-options"></a><a name="options"></a> <span data-ttu-id="202b7-113">Konfigurieren der Optionen</span><span class="sxs-lookup"><span data-stu-id="202b7-113">Configure the Options</span></span>  
  
### <a name="options"></a><span data-ttu-id="202b7-114">Tastatur</span><span class="sxs-lookup"><span data-stu-id="202b7-114">Options</span></span>  
 <span data-ttu-id="202b7-115">**Typ**</span><span class="sxs-lookup"><span data-stu-id="202b7-115">**Type**</span></span>  
 <span data-ttu-id="202b7-116">Gibt den Vorgangstyp an.</span><span class="sxs-lookup"><span data-stu-id="202b7-116">Specifies the type of operation.</span></span> <span data-ttu-id="202b7-117">Im folgenden finden Sie die möglichen Werte für das **typanfeld** und die entsprechenden Werte in der operations_type-Spalte der Transact-SQL- `catalog.operations` Sicht.</span><span class="sxs-lookup"><span data-stu-id="202b7-117">The following are the possible values for the **Type** field and the corresponding values in the operations_type column of the Transact-SQL `catalog.operations` view.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="202b7-118">Initialisierung der Integration Services</span><span class="sxs-lookup"><span data-stu-id="202b7-118">Integration Services initialization</span></span>|<span data-ttu-id="202b7-119">1</span><span class="sxs-lookup"><span data-stu-id="202b7-119">1</span></span>|  
|<span data-ttu-id="202b7-120">Vorgangsbereinigung (SQL Agent-Auftrag)</span><span class="sxs-lookup"><span data-stu-id="202b7-120">Operations cleanup (SQL Agent job)</span></span>|<span data-ttu-id="202b7-121">2</span><span class="sxs-lookup"><span data-stu-id="202b7-121">2</span></span>|  
|<span data-ttu-id="202b7-122">Projektversions-Cleanup (SQL Agent-Auftrag)</span><span class="sxs-lookup"><span data-stu-id="202b7-122">Project versions cleanup (SQL Agent job)</span></span>|<span data-ttu-id="202b7-123">3</span><span class="sxs-lookup"><span data-stu-id="202b7-123">3</span></span>|  
|<span data-ttu-id="202b7-124">Projekt bereitstellen</span><span class="sxs-lookup"><span data-stu-id="202b7-124">Deploy project</span></span>|<span data-ttu-id="202b7-125">101</span><span class="sxs-lookup"><span data-stu-id="202b7-125">101</span></span>|  
|<span data-ttu-id="202b7-126">Projekt wiederherstellen</span><span class="sxs-lookup"><span data-stu-id="202b7-126">Restore project</span></span>|<span data-ttu-id="202b7-127">106</span><span class="sxs-lookup"><span data-stu-id="202b7-127">106</span></span>|  
|<span data-ttu-id="202b7-128">Paketausführung erstellen und starten</span><span class="sxs-lookup"><span data-stu-id="202b7-128">Create and start package execution</span></span>|<span data-ttu-id="202b7-129">200</span><span class="sxs-lookup"><span data-stu-id="202b7-129">200</span></span>|  
|<span data-ttu-id="202b7-130">Vorgang beenden (Beenden einer Überprüfung oder Ausführung)</span><span class="sxs-lookup"><span data-stu-id="202b7-130">Stop operation (stopping a validation or execution</span></span>|<span data-ttu-id="202b7-131">202</span><span class="sxs-lookup"><span data-stu-id="202b7-131">202</span></span>|  
|<span data-ttu-id="202b7-132">Projekt überprüfen</span><span class="sxs-lookup"><span data-stu-id="202b7-132">Validate project</span></span>|<span data-ttu-id="202b7-133">300</span><span class="sxs-lookup"><span data-stu-id="202b7-133">300</span></span>|  
|<span data-ttu-id="202b7-134">Paket überprüfen</span><span class="sxs-lookup"><span data-stu-id="202b7-134">Validate package</span></span>|<span data-ttu-id="202b7-135">301</span><span class="sxs-lookup"><span data-stu-id="202b7-135">301</span></span>|  
|<span data-ttu-id="202b7-136">Katalog konfigurieren</span><span class="sxs-lookup"><span data-stu-id="202b7-136">Configure catalog</span></span>|<span data-ttu-id="202b7-137">1000</span><span class="sxs-lookup"><span data-stu-id="202b7-137">1000</span></span>|  
  
 <span data-ttu-id="202b7-138">**Beenden**</span><span class="sxs-lookup"><span data-stu-id="202b7-138">**Stop**</span></span>  
 <span data-ttu-id="202b7-139">Klicken Sie, um einen gerade ausgeführten Vorgang zu beenden.</span><span class="sxs-lookup"><span data-stu-id="202b7-139">Click to stop a currently running operation.</span></span>  
  
  
