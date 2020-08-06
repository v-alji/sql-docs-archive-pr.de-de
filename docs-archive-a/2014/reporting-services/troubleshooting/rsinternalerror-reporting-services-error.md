---
title: 'rsInternalError: Reporting Services-Fehler | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- rsInternalError
ms.assetid: 52613d52-fc78-4870-93f0-7d393ab9c335
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 85b88519df810f60c580ad2d6eb355dde236d081
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618459"
---
# <a name="rsinternalerror---reporting-services-error"></a><span data-ttu-id="5b4b0-102">rsInternalError – Reporting Services-Fehler</span><span class="sxs-lookup"><span data-stu-id="5b4b0-102">rsInternalError - Reporting Services Error</span></span>
    
## <a name="details"></a><span data-ttu-id="5b4b0-103">Details</span><span class="sxs-lookup"><span data-stu-id="5b4b0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5b4b0-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="5b4b0-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="5b4b0-105">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="5b4b0-105">Event ID</span></span>|<span data-ttu-id="5b4b0-106">rsInternalError</span><span class="sxs-lookup"><span data-stu-id="5b4b0-106">rsInternalError</span></span>|  
|<span data-ttu-id="5b4b0-107">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="5b4b0-107">Event Source</span></span>|<span data-ttu-id="5b4b0-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings</span><span class="sxs-lookup"><span data-stu-id="5b4b0-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings</span></span>|  
|<span data-ttu-id="5b4b0-109">Komponente</span><span class="sxs-lookup"><span data-stu-id="5b4b0-109">Component</span></span>|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|  
|<span data-ttu-id="5b4b0-110">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="5b4b0-110">Message Text</span></span>|<span data-ttu-id="5b4b0-111">Interner Fehler beim Berichtsserver.</span><span class="sxs-lookup"><span data-stu-id="5b4b0-111">An internal error occurred on the report server.</span></span> <span data-ttu-id="5b4b0-112">Weitere Informationen finden Sie im Fehlerprotokoll.</span><span class="sxs-lookup"><span data-stu-id="5b4b0-112">See the error log for more details.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5b4b0-113">Erklärung</span><span class="sxs-lookup"><span data-stu-id="5b4b0-113">Explanation</span></span>  
 <span data-ttu-id="5b4b0-114">Dies ist eine generische Fehlermeldung, auf die häufig ein Fehler mit ausführlicher Beschreibung folgt, die weitere Informationen enthält.</span><span class="sxs-lookup"><span data-stu-id="5b4b0-114">This is a generic error message that is often followed by a more descriptive error that provides more detail.</span></span>  
  
 <span data-ttu-id="5b4b0-115">Interne Fehler treten nicht häufig auf.</span><span class="sxs-lookup"><span data-stu-id="5b4b0-115">Internal errors are uncommon.</span></span> <span data-ttu-id="5b4b0-116">Wenn dieser Fehler ausgegeben wird, finden Sie weitere Informationen in den Ablaufverfolgungsprotokollen des Berichtsservers.</span><span class="sxs-lookup"><span data-stu-id="5b4b0-116">If you get this error, more information is available in report server trace logs.</span></span> <span data-ttu-id="5b4b0-117">Wenn Sie an demselben Computer als lokaler Administrator angemeldet sind, können Sie zusätzlich die Aufrufliste anzeigen, um weitere Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="5b4b0-117">In addition, if you are running as local administrator on the same computer on which the error occurs, you can view the call stack for more information.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5b4b0-118">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="5b4b0-118">User Action</span></span>  
 <span data-ttu-id="5b4b0-119">Überprüfen Sie die Berichts Server-Protokolldateien, die sich unter \Microsoft SQL server\msrs12. \<instancename > befinden, um die spezifische Ursache für diese Nachricht zu ermitteln. \Reporting Services\LogFiles.</span><span class="sxs-lookup"><span data-stu-id="5b4b0-119">To determine the specific cause for this message, review the report server log files, which are located at \Microsoft SQL Server\MSRS12.\<instancename >\Reporting Services\LogFiles.</span></span> <span data-ttu-id="5b4b0-120">Weitere Informationen finden Sie unter [Reporting Services-Protokolldateien und Quellen](../report-server/reporting-services-log-files-and-sources.md).</span><span class="sxs-lookup"><span data-stu-id="5b4b0-120">For more information, see [Reporting Services Log Files and Sources](../report-server/reporting-services-log-files-and-sources.md).</span></span>  
  
 <span data-ttu-id="5b4b0-121">Um die Aufrufliste anzuzeigen, klicken Sie mit der rechten Maustaste auf die Seite, auf der der Fehler auftritt, und zeigen Sie auf **Quelle anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="5b4b0-121">To view the call stack, right-click the page on which the error occurs and point to **View Source**.</span></span> <span data-ttu-id="5b4b0-122">Um die Aufrufliste anzuzeigen, sind Administratorberechtigungen für den gleichen Computer erforderlich, auf dem der Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="5b4b0-122">Viewing the call stack requires administrator permissions on the same computer on which the error occurs.</span></span>  
  
 <span data-ttu-id="5b4b0-123">Wenn keine weiteren Informationen verfügbar sind, versuchen Sie erneut, die Anforderung durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="5b4b0-123">If there is no additional information available, you can try your request again.</span></span>  
  
## <a name="internal-only"></a><span data-ttu-id="5b4b0-124">Nur intern</span><span class="sxs-lookup"><span data-stu-id="5b4b0-124">Internal-Only</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b4b0-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5b4b0-125">See Also</span></span>  
 [<span data-ttu-id="5b4b0-126">Start and Stop the Report Server Service (Starten und Beenden des Berichtsserverdiensts)</span><span class="sxs-lookup"><span data-stu-id="5b4b0-126">Start and Stop the Report Server Service</span></span>](../report-server/start-and-stop-the-report-server-service.md)  
  
  
