---
title: Ursachen und Lösungen für Reporting Service-Fehler | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- messages [Reporting Services]
- errors [Reporting Services]
- troubleshooting [Reporting Services], errors
ms.assetid: 3db0fef3-37f8-40d0-acc7-1928760dc0e9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fa98b9f760485b80f4fa4ac74f3b8008dc3bbec3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700652"
---
# <a name="cause-and-resolution-of-reporting-services-errors"></a><span data-ttu-id="6c791-102">Ursachen und Lösungen für Reporting Services-Fehler</span><span class="sxs-lookup"><span data-stu-id="6c791-102">Cause and Resolution of Reporting Services Errors</span></span>
  <span data-ttu-id="6c791-103">Dieses Thema enthält Informationen zu Ursachen und Lösungen für eine Reihe von Fehlern, die sich auf [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]beziehen.</span><span class="sxs-lookup"><span data-stu-id="6c791-103">This topic contains cause and resolution information for a number of errors related to [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="6c791-104">Die Themen zu Fehlermeldungen in diesem Abschnitt enthalten eine Erklärung der Fehlermeldung, mögliche Ursachen sowie Maßnahmen, die Sie ergreifen können, um das Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="6c791-104">The error message topics in this section provide an explanation of the error message, possible causes, and any actions you can take to correct the problem.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6c791-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="6c791-105">In This Section</span></span>  
  
|<span data-ttu-id="6c791-106">Fehler</span><span class="sxs-lookup"><span data-stu-id="6c791-106">Error</span></span>|<span data-ttu-id="6c791-107">`Message`</span><span class="sxs-lookup"><span data-stu-id="6c791-107">Message</span></span>|  
|-----------|-------------|  
|[<span data-ttu-id="6c791-108">rsAccessedDenied - Reporting Services Error (rsAccessedDenied: Reporting Services-Fehler)</span><span class="sxs-lookup"><span data-stu-id="6c791-108">rsAccessedDenied - Reporting Services Error</span></span>](rsaccesseddenied-reporting-services-error.md)|<span data-ttu-id="6c791-109">Die dem Benutzer 'mydomain\myAccount' erteilten Berechtigungen reichen zum Ausführen des Vorgangs nicht aus.</span><span class="sxs-lookup"><span data-stu-id="6c791-109">The permissions granted to user 'mydomain\myAccount' are insufficient for performing this operation.</span></span> <span data-ttu-id="6c791-110">(rsAccessDenied) (ReportingServicesLibrary).</span><span class="sxs-lookup"><span data-stu-id="6c791-110">(rsAccessDenied) (ReportingServicesLibrary).</span></span>|  
|[<span data-ttu-id="6c791-111">rsInternalError - Reporting Services Error (rsInternalError: Reporting Services-Fehler)</span><span class="sxs-lookup"><span data-stu-id="6c791-111">rsInternalError - Reporting Services Error</span></span>](rsinternalerror-reporting-services-error.md)|<span data-ttu-id="6c791-112">Interner Fehler beim Berichtsserver.</span><span class="sxs-lookup"><span data-stu-id="6c791-112">An internal error occurred on the report server.</span></span> <span data-ttu-id="6c791-113">Weitere Informationen finden Sie im Fehlerprotokoll.</span><span class="sxs-lookup"><span data-stu-id="6c791-113">See the error log for more details.</span></span>|  
|[<span data-ttu-id="6c791-114">rsModelGenerationError - Reporting Services Error (rsModelGenerationError: Reporting Services-Fehler)</span><span class="sxs-lookup"><span data-stu-id="6c791-114">rsModelGenerationError - Reporting Services Error</span></span>](rsmodelgenerationerror-reporting-services-error.md)|<span data-ttu-id="6c791-115">Fehler beim Generieren des Modells.</span><span class="sxs-lookup"><span data-stu-id="6c791-115">An error occurred while generating model.</span></span> <span data-ttu-id="6c791-116">(rsModelGenerationError) (ReportingServicesLibrary) %1.</span><span class="sxs-lookup"><span data-stu-id="6c791-116">(rsModelGenerationError) (ReportingServicesLibrary) %1.</span></span>|  
|[<span data-ttu-id="6c791-117">rsProcessingError - Reporting Services Error (rsProcessingError: Reporting Services-Fehler)</span><span class="sxs-lookup"><span data-stu-id="6c791-117">rsProcessingError - Reporting Services Error</span></span>](rsprocessingerror-reporting-services-error.md)|<span data-ttu-id="6c791-118">Fehler bei der Berichtsverarbeitung.</span><span class="sxs-lookup"><span data-stu-id="6c791-118">Errors have occurred in report processing.</span></span>|  
|[<span data-ttu-id="6c791-119">rsServerConfigurationError - Reporting Services Error (rsServerConfigurationError: Reporting Services-Fehler)</span><span class="sxs-lookup"><span data-stu-id="6c791-119">rsServerConfigurationError - Reporting Services Error</span></span>](rsserverconfigurationerror-reporting-services-error.md)|<span data-ttu-id="6c791-120">Konfigurationsfehler beim Berichtsserver.</span><span class="sxs-lookup"><span data-stu-id="6c791-120">The report server has encountered a configuration error.</span></span>|  
|[<span data-ttu-id="6c791-121">rrRenderingError - Reporting Services Error (rrRenderingError: Reporting Services-Fehler)</span><span class="sxs-lookup"><span data-stu-id="6c791-121">rrRenderingError - Reporting Services Error</span></span>](rrrenderingerror-reporting-services-error.md)|<span data-ttu-id="6c791-122">Fehler beim Rendern des Berichts.</span><span class="sxs-lookup"><span data-stu-id="6c791-122">An error occurred during rendering of the report.</span></span> <span data-ttu-id="6c791-123">(rrRenderingError) %1.</span><span class="sxs-lookup"><span data-stu-id="6c791-123">(rrRenderingError) %1.</span></span>|  
|[<span data-ttu-id="6c791-124">Report Server-Windows-Dienst &#40;MSSQLServer&#41; 107</span><span class="sxs-lookup"><span data-stu-id="6c791-124">Report Server Windows Service &#40;MSSQLServer&#41; 107</span></span>](../../relational-databases/errors-events/mssqlserver-107-database-engine-error.md)|<span data-ttu-id="6c791-125">Der Berichtsserver-Windows-Dienst (MSSQLSERVER) kann nicht mit der Berichtsserver-Datenbank verbunden werden.</span><span class="sxs-lookup"><span data-stu-id="6c791-125">Report Server Windows service (MSSQLSERVER) cannot connect to the report server database.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6c791-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6c791-126">See Also</span></span>  
 <span data-ttu-id="6c791-127">[Reporting Services-Protokolldateien und Quellen](../report-server/reporting-services-log-files-and-sources.md) </span><span class="sxs-lookup"><span data-stu-id="6c791-127">[Reporting Services Log Files and Sources](../report-server/reporting-services-log-files-and-sources.md) </span></span>  
 [<span data-ttu-id="6c791-128">Fehler- und Ereignisreferenz &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="6c791-128">Errors and Events Reference &#40;Reporting Services&#41;</span></span>](errors-and-events-reference-reporting-services.md)  
  
  
