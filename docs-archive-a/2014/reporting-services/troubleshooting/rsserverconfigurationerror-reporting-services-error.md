---
title: 'rsServerConfigurationError: Reporting Services-Fehler | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- rsServerConfigurationError
ms.assetid: 0913afc2-34b4-4713-b570-cfd5718975ac
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 02f8a18c42715d1f118920614eb425820130dacb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722469"
---
# <a name="rsserverconfigurationerror---reporting-services-error"></a><span data-ttu-id="3f23f-102">rsServerConfigurationError – Reporting Services-Fehler</span><span class="sxs-lookup"><span data-stu-id="3f23f-102">rsServerConfigurationError - Reporting Services Error</span></span>
    
## <a name="details"></a><span data-ttu-id="3f23f-103">Details</span><span class="sxs-lookup"><span data-stu-id="3f23f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3f23f-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="3f23f-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="3f23f-105">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="3f23f-105">Event ID</span></span>|<span data-ttu-id="3f23f-106">rsServerConfiguration</span><span class="sxs-lookup"><span data-stu-id="3f23f-106">rsServerConfiguration</span></span>|  
|<span data-ttu-id="3f23f-107">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="3f23f-107">Event Source</span></span>|<span data-ttu-id="3f23f-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings</span><span class="sxs-lookup"><span data-stu-id="3f23f-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings</span></span>|  
|<span data-ttu-id="3f23f-109">Komponente</span><span class="sxs-lookup"><span data-stu-id="3f23f-109">Component</span></span>|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|  
|<span data-ttu-id="3f23f-110">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="3f23f-110">Message Text</span></span>|<span data-ttu-id="3f23f-111">Konfigurationsfehler beim Berichtsserver.</span><span class="sxs-lookup"><span data-stu-id="3f23f-111">The report server has encountered a configuration error.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3f23f-112">Erklärung</span><span class="sxs-lookup"><span data-stu-id="3f23f-112">Explanation</span></span>  
 <span data-ttu-id="3f23f-113">Dies ist ein allgemeiner Fehler, der auftritt, wenn der Berichtsserver oder ein Berichterstellungstool fehlerhaft konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="3f23f-113">This is a general purpose error that occurs when either the report server or a report authoring tool has invalid configuration settings.</span></span> <span data-ttu-id="3f23f-114">Der Fehler wird normalerweise mit einer zweiten Meldung ausgegeben, die die tatsächliche Ursache des Fehlers enthält.</span><span class="sxs-lookup"><span data-stu-id="3f23f-114">The error is usually accompanied by a second message that states the actual cause of the error.</span></span>  
  
 <span data-ttu-id="3f23f-115">Die folgende Liste enthält die möglichen Ursachen:</span><span class="sxs-lookup"><span data-stu-id="3f23f-115">The following list summarizes possible causes:</span></span>  
  
-   <span data-ttu-id="3f23f-116">Die RSReportServer.config-Datei oder die RSReportDesigner.config-Datei kann nicht gefunden oder gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="3f23f-116">The RSReportServer.config or RSReportDesigner.config file cannot be found or read.</span></span>  
  
-   <span data-ttu-id="3f23f-117">XML-Elemente in einer der beiden Konfigurationsdateien fehlen oder sind ungültig.</span><span class="sxs-lookup"><span data-stu-id="3f23f-117">XML elements in either configuration file are missing or invalid.</span></span>  
  
-   <span data-ttu-id="3f23f-118">Werte für einen oder mehrere XML-Elemente fehlen oder sind ungültig.</span><span class="sxs-lookup"><span data-stu-id="3f23f-118">Values for one or more XML elements are missing or invalid.</span></span>  
  
-   <span data-ttu-id="3f23f-119">Registrierungseinstellungen sind ungültig.</span><span class="sxs-lookup"><span data-stu-id="3f23f-119">Registry settings are invalid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3f23f-120">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="3f23f-120">User Action</span></span>  
 <span data-ttu-id="3f23f-121">Wenn dieser Fehler auftritt, nachdem Sie manuell eine Konfigurationsdatei bearbeitet haben, machen Sie die Änderungen rückgängig, indem Sie den ursprünglichen Wert wieder eingeben, oder stellen Sie eine vorherige Version wieder her, wenn eine Sicherung existiert.</span><span class="sxs-lookup"><span data-stu-id="3f23f-121">If this error began to occur after you manually edited a configuration file, remove your changes and enter the previous value, or restore a previous version if you have a backup.</span></span>  
  
 <span data-ttu-id="3f23f-122">Überprüfen Sie `rsServerConfiguration` die Ablauf Verfolgungs Protokolldateien des Berichts Servers unter \Microsoft SQL server\msrs12. \<instancename > , um zusätzliche Fehlermeldungs Informationen zu überprüfen, die mit dem Fehler zusammenarbeiten. \Reporting Services\LogFiles.</span><span class="sxs-lookup"><span data-stu-id="3f23f-122">To review additional error message information that accompanies the `rsServerConfiguration` error, review the report server trace log files, which are located at \Microsoft SQL Server\MSRS12.\<instancename >\Reporting Services\LogFiles.</span></span> <span data-ttu-id="3f23f-123">Weitere Informationen finden Sie unter [Reporting Services-Protokolldateien und Quellen](../report-server/reporting-services-log-files-and-sources.md).</span><span class="sxs-lookup"><span data-stu-id="3f23f-123">For more information, see [Reporting Services Log Files and Sources](../report-server/reporting-services-log-files-and-sources.md).</span></span>  
  
## <a name="internal-only"></a><span data-ttu-id="3f23f-124">Nur intern</span><span class="sxs-lookup"><span data-stu-id="3f23f-124">Internal-Only</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f23f-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3f23f-125">See Also</span></span>  
 <span data-ttu-id="3f23f-126">[Reporting Services-Konfigurationsdateien](../report-server/reporting-services-configuration-files.md) </span><span class="sxs-lookup"><span data-stu-id="3f23f-126">[Reporting Services Configuration Files](../report-server/reporting-services-configuration-files.md) </span></span>  
 [<span data-ttu-id="3f23f-127">Ändern einer Reporting Services-Konfigurationsdatei (RSreportserver.config)</span><span class="sxs-lookup"><span data-stu-id="3f23f-127">Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;</span></span>](../report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md)  
  
  
