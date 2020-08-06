---
title: Überwachen von Paket Ausführungen und anderen Vorgängen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: cbbcd79f-ab9b-46ec-84cb-4821c1d16b99
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 628b62d9c8e01d0dc0bf641551de67c3838a4504
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622775"
---
# <a name="monitoring-for-package-executions-and-other-operations"></a><span data-ttu-id="25101-102">Überwachen von Paketausführungen und anderen Vorgängen</span><span class="sxs-lookup"><span data-stu-id="25101-102">Monitoring for Package Executions and Other Operations</span></span>
  <span data-ttu-id="25101-103">Sie können [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Paketausführungen, Projektüberprüfungen und andere Vorgänge mit einem oder mehreren der folgenden Tools überwachen.</span><span class="sxs-lookup"><span data-stu-id="25101-103">You can monitor [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package executions, project validations, and other operations by using one of more of the following tools.</span></span> <span data-ttu-id="25101-104">Bestimmte Tools, z. B. Datenabzweigungen, sind nur für Projekte verfügbar, die auf dem [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Server bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="25101-104">Certain tools such as data taps are available only for projects that are deployed to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
-   <span data-ttu-id="25101-105">Protokolle</span><span class="sxs-lookup"><span data-stu-id="25101-105">Logs</span></span>  
  
     <span data-ttu-id="25101-106">Weitere Informationen finden Sie unter [Integration Services-Protokollierung &#40;SSIS&#41;](integration-services-ssis-logging.md).</span><span class="sxs-lookup"><span data-stu-id="25101-106">For more information, see [Integration Services &#40;SSIS&#41; Logging](integration-services-ssis-logging.md).</span></span>  
  
-   <span data-ttu-id="25101-107">Berichte</span><span class="sxs-lookup"><span data-stu-id="25101-107">Reports</span></span>  
  
     <span data-ttu-id="25101-108">Weitere Informationen finden Sie unter [Berichte für den Integration Services-Server](../reports-for-the-integration-services-server.md).</span><span class="sxs-lookup"><span data-stu-id="25101-108">For more information, see [Reports for the Integration Services Server](../reports-for-the-integration-services-server.md).</span></span>  
  
-   <span data-ttu-id="25101-109">Sichten</span><span class="sxs-lookup"><span data-stu-id="25101-109">Views</span></span>  
  
     <span data-ttu-id="25101-110">Weitere Informationen finden Sie unter [Sichten &#40;Integration Services-Katalog&#41;](/sql/integration-services/system-views/views-integration-services-catalog).</span><span class="sxs-lookup"><span data-stu-id="25101-110">For more information, see [Views &#40;Integration Services Catalog&#41;](/sql/integration-services/system-views/views-integration-services-catalog).</span></span>  
  
-   <span data-ttu-id="25101-111">Leistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="25101-111">Performance counters</span></span>  
  
     <span data-ttu-id="25101-112">Weitere Informationen finden Sie unter [Performance Counters](performance-counters.md).</span><span class="sxs-lookup"><span data-stu-id="25101-112">For more information, see [Performance Counters](performance-counters.md).</span></span>  
  
-   <span data-ttu-id="25101-113">Datenabzweigungen</span><span class="sxs-lookup"><span data-stu-id="25101-113">Data taps</span></span>  
  
## <a name="operation-types"></a><span data-ttu-id="25101-114">Vorgangstypen</span><span class="sxs-lookup"><span data-stu-id="25101-114">Operation Types</span></span>  
 <span data-ttu-id="25101-115">Mehrere verschiedene Typen von Vorgängen werden im `SSISDB`-Katalog auf dem [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Server überwacht.</span><span class="sxs-lookup"><span data-stu-id="25101-115">Several different types of operations are monitored in the `SSISDB` catalog, on the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="25101-116">Jeder Vorgang kann mehrere ihm zugeordnete Meldungen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="25101-116">Each operation can have multiple messages associated with it.</span></span> <span data-ttu-id="25101-117">Jede Meldung kann einem von mehreren Typklassen zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="25101-117">Each message can be classified into one of several different types.</span></span> <span data-ttu-id="25101-118">Eine Meldung kann z. B. vom Typ Information, Warnung oder Fehler sein.</span><span class="sxs-lookup"><span data-stu-id="25101-118">For example, a message can be of type Information, Warning, or Error.</span></span> <span data-ttu-id="25101-119">Die vollständige Liste von Meldungstypen finden Sie in der Dokumentation zur Transact-SQL-Sicht [catalog.operation_messages &#40;SSISDB-Datenbank&#41;](/sql/integration-services/system-views/catalog-operation-messages-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="25101-119">For the full list of message types, see the documentation for the Transact-SQL [catalog.operation_messages &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-operation-messages-ssisdb-database) view.</span></span> <span data-ttu-id="25101-120">Eine vollständige Liste der Vorgangstypen finden Sie unter [catalog.operations &#40;SSISDB-Datenbank&#41;](/sql/integration-services/system-views/catalog-operations-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="25101-120">For a full list of the operations types, see [catalog.operations &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-operations-ssisdb-database).</span></span>  
  
 <span data-ttu-id="25101-121">Neun verschiedene Statustypen werden verwendet, um den Status eines Vorgangs anzugeben.</span><span class="sxs-lookup"><span data-stu-id="25101-121">Nine different status types are used to indicate the status of an operation.</span></span> <span data-ttu-id="25101-122">Eine vollständige Liste der Statustypen finden Sie in der Sicht [catalog.operations &#40;SSISDB-Datenbank&#41;](/sql/integration-services/system-views/catalog-operations-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="25101-122">For a full list of the status types, see the [catalog.operations &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-operations-ssisdb-database) view.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="25101-123">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="25101-123">Related Content</span></span>  
 <span data-ttu-id="25101-124">Blogeintrag [SSIS T-SQL API Overview](https://go.microsoft.com/fwlink/?LinkId=249051)(Übersicht über die SSIS-T-SQL-API) auf blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="25101-124">Blog entry, [SSIS T-SQL API Overview](https://go.microsoft.com/fwlink/?LinkId=249051), on blogs.msdn.com.</span></span>  
  
  
