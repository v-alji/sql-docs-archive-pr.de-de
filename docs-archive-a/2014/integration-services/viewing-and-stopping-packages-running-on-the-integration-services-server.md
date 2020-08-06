---
title: Anzeigen und Beenden von Paketen, die auf dem Integration Services-Server ausgeführt werden | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- packages [Integration Services], managing
- managing running packages [Integration Services]
- packages [Integration Services], running
- running package [Integration Services], managing
ms.assetid: 11bf44e6-f6b0-475f-b816-40e914dbac80
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6e63839d4ab5d8d50f7d86eea05c8d58107d6799
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621567"
---
# <a name="viewing-and-stopping-packages-running-on-the-integration-services-server"></a><span data-ttu-id="a2086-102">Anzeigen und Beenden von auf dem Integration Services-Server ausgeführten Paketen</span><span class="sxs-lookup"><span data-stu-id="a2086-102">Viewing and Stopping Packages Running on the Integration Services Server</span></span>
  <span data-ttu-id="a2086-103">In der `SSISDB`-Datenbank wird der Ausführungsverlauf in internen Tabellen gespeichert, die für Benutzer nicht sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="a2086-103">The `SSISDB` database stores execution history in internal tables that are not visible to users.</span></span> <span data-ttu-id="a2086-104">Es werden jedoch Informationen verfügbar gemacht, die für öffentliche Sichten benötigt werden, die Sie abfragen können.</span><span class="sxs-lookup"><span data-stu-id="a2086-104">However it exposes the information that you need through public views that you can query.</span></span> <span data-ttu-id="a2086-105">Außerdem werden gespeicherte Prozeduren bereitgestellt, die Sie aufrufen können, um allgemeine Aufgaben im Zusammenhang mit Paketen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a2086-105">It also provides stored procedures that you can call to perform common tasks related to packages.</span></span>  
  
 <span data-ttu-id="a2086-106">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Objekte auf dem Server werden i. d. R. in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]verwaltet.</span><span class="sxs-lookup"><span data-stu-id="a2086-106">Typically you manage [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] objects on the server in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="a2086-107">Sie können jedoch auch die Datenbanksichten abfragen und gespeicherte Prozeduren direkt aufrufen oder benutzerdefinierten Code schreiben, mit dem die verwaltete API aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="a2086-107">However you can also query the database views and call the stored procedures directly, or write custom code that calls the managed API.</span></span> [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="a2086-108">und die verwaltete API führen zur Ausführung vieler Aufgaben eine Abfrage der Sichten durch und rufen gespeicherte Prozeduren auf.</span><span class="sxs-lookup"><span data-stu-id="a2086-108">and the managed API query the views and call the stored procedures to perform many of their tasks.</span></span> <span data-ttu-id="a2086-109">Sie können beispielsweise die Liste der [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Pakete anzeigen, die derzeit auf dem Server ausgeführt werden, und bei Bedarf einzelne Pakete anhalten.</span><span class="sxs-lookup"><span data-stu-id="a2086-109">For example, you can view the list of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages that are currently running on the server, and request packages to stop if you have to.</span></span>  
  
## <a name="viewing-the-list-of-running-packages"></a><span data-ttu-id="a2086-110">Anzeigen der Liste ausgeführter Pakete</span><span class="sxs-lookup"><span data-stu-id="a2086-110">Viewing the List of Running Packages</span></span>  
 <span data-ttu-id="a2086-111">Sie können die Liste der momentan auf dem Server ausgeführten Pakete im Dialogfeld **Aktive Vorgänge** anzeigen.</span><span class="sxs-lookup"><span data-stu-id="a2086-111">You can view the list of packages that are currently running on the server in the **Active Operations** dialog box.</span></span> <span data-ttu-id="a2086-112">Weitere Informationen finden Sie unter [Active Operations Dialog Box](../../2014/integration-services/active-operations-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="a2086-112">For more information, see [Active Operations Dialog Box](../../2014/integration-services/active-operations-dialog-box.md).</span></span>  
  
 <span data-ttu-id="a2086-113">Informationen zu weiteren Methoden, mit denen Sie die Liste der ausgeführten Pakete anzeigen können, finden Sie in den folgenden Themen.</span><span class="sxs-lookup"><span data-stu-id="a2086-113">For information about the other methods that you can use to view the list of running packages, see the following topics.</span></span>  
  
 [!INCLUDE[tsql](../includes/tsql-md.md)] <span data-ttu-id="a2086-114">-Zugriff</span><span class="sxs-lookup"><span data-stu-id="a2086-114">access</span></span>  
 <span data-ttu-id="a2086-115">Fragen Sie die Sicht [catalog.executions &#40;SSISDB-Datenbank&#41;](/sql/integration-services/system-views/catalog-executions-ssisdb-database) nach Paketen ab, die einen Status von 2 aufweisen, um die Liste der Pakete anzuzeigen, die auf dem Server ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a2086-115">To view the list of packages that are running on the server, query the view, [catalog.executions &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-executions-ssisdb-database) for packages that have a status of 2.</span></span>  
  
 <span data-ttu-id="a2086-116">Programmgesteuerter Zugriff auf die verwaltete API</span><span class="sxs-lookup"><span data-stu-id="a2086-116">Programmatic access through the managed API</span></span>  
 <span data-ttu-id="a2086-117">Weitere Details finden Sie in den Informationen zum <xref:Microsoft.SqlServer.Management.IntegrationServices>-Namespace und den zugehörigen Klassen.</span><span class="sxs-lookup"><span data-stu-id="a2086-117">See the <xref:Microsoft.SqlServer.Management.IntegrationServices> namespace and its classes.</span></span>  
  
## <a name="stopping-a-running-package"></a><span data-ttu-id="a2086-118">Beenden eines ausgeführten Pakets</span><span class="sxs-lookup"><span data-stu-id="a2086-118">Stopping a Running Package</span></span>  
 <span data-ttu-id="a2086-119">Sie können die Beendigung eines ausgeführten Pakets im Dialogfeld **Aktive Vorgänge** anfordern.</span><span class="sxs-lookup"><span data-stu-id="a2086-119">You can request a running package to stop in the **Active Operations** dialog box.</span></span> <span data-ttu-id="a2086-120">Weitere Informationen finden Sie unter [Active Operations Dialog Box](../../2014/integration-services/active-operations-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="a2086-120">For more information, see [Active Operations Dialog Box](../../2014/integration-services/active-operations-dialog-box.md).</span></span>  
  
 <span data-ttu-id="a2086-121">Informationen zu weiteren Methoden, mit denen Sie Pakete beenden können, die derzeit ausgeführt werden, finden Sie in den folgenden Themen.</span><span class="sxs-lookup"><span data-stu-id="a2086-121">For information about the other methods that you can use to stop a running package, see the following topics.</span></span>  
  
 [!INCLUDE[tsql](../includes/tsql-md.md)] <span data-ttu-id="a2086-122">-Zugriff</span><span class="sxs-lookup"><span data-stu-id="a2086-122">access</span></span>  
 <span data-ttu-id="a2086-123">Rufen Sie die gespeicherte Prozedur [catalog.stop_operation &#40;SSISDB-Datenbank&#41;](/sql/integration-services/system-stored-procedures/catalog-stop-operation-ssisdb-database) auf, um ein Paket zu beenden, das auf dem Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a2086-123">To stop a package that is running on the server, call the stored procedure, [catalog.stop_operation &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-stop-operation-ssisdb-database).</span></span>  
  
 <span data-ttu-id="a2086-124">Programmgesteuerter Zugriff auf die verwaltete API</span><span class="sxs-lookup"><span data-stu-id="a2086-124">Programmatic access through the managed API</span></span>  
 <span data-ttu-id="a2086-125">Weitere Details finden Sie in den Informationen zum <xref:Microsoft.SqlServer.Management.IntegrationServices>-Namespace und den zugehörigen Klassen.</span><span class="sxs-lookup"><span data-stu-id="a2086-125">See the <xref:Microsoft.SqlServer.Management.IntegrationServices> namespace and its classes.</span></span>  
  
## <a name="viewing-the-history-of-packages-that-have-run"></a><span data-ttu-id="a2086-126">Anzeigen des Verlaufs ausgeführter Pakete</span><span class="sxs-lookup"><span data-stu-id="a2086-126">Viewing the History of Packages That Have Run</span></span>  
 <span data-ttu-id="a2086-127">Verwenden Sie den Bericht [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)]Alle Ausführungen **, um den Verlauf der Pakete anzuzeigen, die in** ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="a2086-127">To view the history of packages that have run in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], use the **All Executions** report.</span></span> <span data-ttu-id="a2086-128">Weitere Informationen zum Bericht **Alle Ausführungen** und zu anderen Standardberichten finden Sie unter [Berichte für den Integration Services-Server](../../2014/integration-services/reports-for-the-integration-services-server.md).</span><span class="sxs-lookup"><span data-stu-id="a2086-128">For more information on the **All Executions** report and other standard reports, see [Reports for the Integration Services Server](../../2014/integration-services/reports-for-the-integration-services-server.md).</span></span>  
  
 <span data-ttu-id="a2086-129">Informationen zu weiteren Methoden, mit denen Sie den Verlauf der ausgeführten Pakete anzeigen können, finden Sie in den folgenden Themen.</span><span class="sxs-lookup"><span data-stu-id="a2086-129">For information about the other methods that you can use to view the history of running packages, see the following topics.</span></span>  
  
 [!INCLUDE[tsql](../includes/tsql-md.md)] <span data-ttu-id="a2086-130">-Zugriff</span><span class="sxs-lookup"><span data-stu-id="a2086-130">access</span></span>  
 <span data-ttu-id="a2086-131">Um Informationen zu Paketen anzuzeigen, die ausgeführt wurden, fragen Sie die Sicht [catalog.executions &#40;SSISDB-Datenbank&#41;](/sql/integration-services/system-views/catalog-executions-ssisdb-database) ab.</span><span class="sxs-lookup"><span data-stu-id="a2086-131">To view information about packages that have run, query the view, [catalog.executions &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-executions-ssisdb-database).</span></span>  
  
 <span data-ttu-id="a2086-132">Programmgesteuerter Zugriff auf die verwaltete API</span><span class="sxs-lookup"><span data-stu-id="a2086-132">Programmatic access through the managed API</span></span>  
 <span data-ttu-id="a2086-133">Weitere Details finden Sie in den Informationen zum <xref:Microsoft.SqlServer.Management.IntegrationServices>-Namespace und den zugehörigen Klassen.</span><span class="sxs-lookup"><span data-stu-id="a2086-133">See the <xref:Microsoft.SqlServer.Management.IntegrationServices> namespace and its classes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2086-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a2086-134">See Also</span></span>  
 <span data-ttu-id="a2086-135">[Ausführung von Projekten und Paketen](packages/run-integration-services-ssis-packages.md) </span><span class="sxs-lookup"><span data-stu-id="a2086-135">[Execution of Projects and Packages](packages/run-integration-services-ssis-packages.md) </span></span>  
 [<span data-ttu-id="a2086-136">Behandlung von Problemen in Berichten für die Paketausführung</span><span class="sxs-lookup"><span data-stu-id="a2086-136">Troubleshooting Reports for Package Execution</span></span>](troubleshooting/troubleshooting-reports-for-package-execution.md)  
  
  
