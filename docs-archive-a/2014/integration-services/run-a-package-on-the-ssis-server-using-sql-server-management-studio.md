---
title: Ausführen eines Pakets auf dem SSIS-Server mit SQL Server Management Studio | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 56dc1bf8-99d4-41dc-bdc4-f64f1ccfd688
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d17009988dea54621d4fd7ef542cf452bfe95c6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696918"
---
# <a name="run-a-package-on-the-ssis-server-using-sql-server-management-studio"></a><span data-ttu-id="4714a-102">Ausführen eines Pakets auf dem SSIS-Server mit SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4714a-102">Run a Package on the SSIS Server Using SQL Server Management Studio</span></span>
  <span data-ttu-id="4714a-103">Nachdem Sie das Projekt auf dem [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Server bereitgestellt haben, können Sie das Paket auf dem Server ausführen.</span><span class="sxs-lookup"><span data-stu-id="4714a-103">After you deploy your project to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server, you can run the package on the server.</span></span>  
  
 <span data-ttu-id="4714a-104">Sie können Vorgangsberichte verwenden, um Informationen über Pakete anzuzeigen, deren Ausführung abgeschlossen ist bzw. die derzeit auf dem Server ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4714a-104">You can use operations reports to view information about packages that have run, or are currently running, on the server.</span></span> <span data-ttu-id="4714a-105">Weitere Informationen finden Sie unter [Berichte für den Integration Services-Server](../../2014/integration-services/reports-for-the-integration-services-server.md).</span><span class="sxs-lookup"><span data-stu-id="4714a-105">For more information, see [Reports for the Integration Services Server](../../2014/integration-services/reports-for-the-integration-services-server.md).</span></span>  
  
### <a name="to-run-a-package-on-the-server-using-sql-server-management-studio"></a><span data-ttu-id="4714a-106">So führen Sie mit SQL Server Management Studio ein Paket auf dem Server aus</span><span class="sxs-lookup"><span data-stu-id="4714a-106">To run a package on the server using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="4714a-107">Öffnen Sie [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] , und stellen Sie eine Verbindung mit der Instanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] her, die den [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Katalog enthält.</span><span class="sxs-lookup"><span data-stu-id="4714a-107">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] and connect to the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that contains the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] catalog.</span></span>  
  
2.  <span data-ttu-id="4714a-108">Erweitern Sie im Objekt-Explorer den Knoten **Integration Services-Kataloge** und den Knoten **SSISDB** , und navigieren Sie zu dem Paket, das im bereitgestellten Projekt enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="4714a-108">In Object Explorer, expand the **Integration Services Catalogs** node, expand the **SSISDB** node, and navigate to the package contained in the project you deployed.</span></span>  
  
3.  <span data-ttu-id="4714a-109">Klicken Sie mit der rechten Maustaste auf den Paketnamen, und wählen Sie **Ausführen**aus.</span><span class="sxs-lookup"><span data-stu-id="4714a-109">Right-click the package name and select **Execute**.</span></span>  
  
4.  <span data-ttu-id="4714a-110">Konfigurieren Sie die Paketausführung mit den Einstellungen im Dialogfeld **Paket ausführen**auf den Registerkarten **Parameter**, **Verbindungs-Managern** und **Erweitert** .</span><span class="sxs-lookup"><span data-stu-id="4714a-110">Configure the package execution by using the settings on the **Parameters**, **Connection Managers**, and **Advanced** tabs in the **Execute Package** dialog box.</span></span>  
  
5.  <span data-ttu-id="4714a-111">Klicken Sie auf **OK** , um das Paket auszuführen.</span><span class="sxs-lookup"><span data-stu-id="4714a-111">Click **OK** to run the package.</span></span>  
  
     <span data-ttu-id="4714a-112">Oder</span><span class="sxs-lookup"><span data-stu-id="4714a-112">-or-</span></span>  
  
     <span data-ttu-id="4714a-113">Verwenden Sie gespeicherte Prozeduren zum Ausführen des Pakets.</span><span class="sxs-lookup"><span data-stu-id="4714a-113">Use stored procedures to run the package.</span></span> <span data-ttu-id="4714a-114">Klicken Sie auf **Skript** , um die Transact-SQL-Anweisung zu generieren, die eine Instanz der Ausführung erstellt und startet.</span><span class="sxs-lookup"><span data-stu-id="4714a-114">Click **Script** to generate the Transact-SQL statement that creates an instance of the execution and starts an instance of the execution.</span></span> <span data-ttu-id="4714a-115">Die Anweisung enthält einen Aufruf der gespeicherten Prozeduren catalog.create_execution, catalog.set_execution_parameter_value und catalog.start_execution.</span><span class="sxs-lookup"><span data-stu-id="4714a-115">The statement includes a call to the catalog.create_execution, catalog.set_execution_parameter_value, and catalog.start_execution stored procedures.</span></span> <span data-ttu-id="4714a-116">Weitere Informationen zu diesen gespeicherten Prozeduren finden Sie unter [catalog.create_execution &#40;SSISDB-Datenbank&#41;](/sql/integration-services/system-stored-procedures/catalog-create-execution-ssisdb-database), [catalog.set_execution_parameter_value &#40;SSISDB-Datenbank&#41;](/sql/integration-services/system-stored-procedures/catalog-set-execution-parameter-value-ssisdb-database) und [catalog.start_execution &#40;SSISDB-Datenbank&#41;](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="4714a-116">For more information about these stored procedures, see [catalog.create_execution &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-create-execution-ssisdb-database), [catalog.set_execution_parameter_value &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-set-execution-parameter-value-ssisdb-database), and [catalog.start_execution &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database).</span></span>  
  
  
