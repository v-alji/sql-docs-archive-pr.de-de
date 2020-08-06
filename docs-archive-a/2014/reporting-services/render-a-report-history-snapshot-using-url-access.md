---
title: Rendern von Berichtsverlaufs-Momentaufnahmen mit URL-Zugriff | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- URL access [Reporting Services], report history
- history snapshots [Reporting Services]
- historical data [Reporting Services]
- snapshots [Reporting Services], URL access
- snapshots [Reporting Services], rendering report history
ms.assetid: 3f87f82d-0e61-4492-9c4b-f5238c39e8cd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 67854a39ab7e38289627d03ac00cc4b2a6dca6f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617789"
---
# <a name="render-a-report-history-snapshot-using-url-access"></a><span data-ttu-id="3f894-102">Rendern von Berichtsverlaufs-Momentaufnahmen mit URL-Zugriff</span><span class="sxs-lookup"><span data-stu-id="3f894-102">Render a Report History Snapshot Using URL Access</span></span>
  <span data-ttu-id="3f894-103">Sie können einen Bericht auf der Grundlage einer Berichtsverlaufs-Momentaufnahme rendern, indem Sie den Parameter *rs:Snapshot* angeben und seinen Wert auf eine gültige Momentaufnahme-ID festlegen.</span><span class="sxs-lookup"><span data-stu-id="3f894-103">You can render a report based on a report history snapshot by supplying the *rs:Snapshot* parameter and setting its value to a valid snapshot ID.</span></span> <span data-ttu-id="3f894-104">Der Parameterwert hat das Format YYYY-MM-DDTHH:MM:SS und basiert auf dem ISO-Standard 8601 (Standard International Organization for Standardization).</span><span class="sxs-lookup"><span data-stu-id="3f894-104">The parameter value is in the format YYYY-MM-DDTHH:MM:SS, based on the International Organization for Standardization (ISO) 8601 standard.</span></span>  
  
 <span data-ttu-id="3f894-105">Wenn Sie diesen Parameter weglassen, wird der Bericht gemäß den Optionseinstellungen für die Berichtsausführung und Cacheverwaltung des Berichtsservers gerendert.</span><span class="sxs-lookup"><span data-stu-id="3f894-105">If you omit this parameter, the report is rendered according to the report execution and cache management option settings of the report server.</span></span> <span data-ttu-id="3f894-106">Weitere Informationen zur Ausführung von Berichten finden Sie unter [Festlegen von Berichtsverarbeitungseigenschaften](report-server/set-report-processing-properties.md).</span><span class="sxs-lookup"><span data-stu-id="3f894-106">For more information about report execution, see [Set Report Processing Properties](report-server/set-report-processing-properties.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f894-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3f894-107">Example</span></span>  
 <span data-ttu-id="3f894-108">Das folgende Beispiel zeigt eine URL, die eine Berichtsverlaufs-Momentaufnahme abruft:</span><span class="sxs-lookup"><span data-stu-id="3f894-108">The following example shows a URL that retrieves a report history snapshot:</span></span>  
  
```  
http://myrshost/reportserver?/SampleReports/Company Sales&rs:Snapshot=2003-04-07T13:40:02  
```  
  
## <a name="see-also"></a><span data-ttu-id="3f894-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3f894-109">See Also</span></span>  
 <span data-ttu-id="3f894-110">[URL-Zugriff &#40;SSRS&#41;](url-access-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3f894-110">[URL Access &#40;SSRS&#41;](url-access-ssrs.md) </span></span>  
 [<span data-ttu-id="3f894-111">URL Access Parameter Reference (URL-Zugriffsparameterverweis)</span><span class="sxs-lookup"><span data-stu-id="3f894-111">URL Access Parameter Reference</span></span>](url-access-parameter-reference.md)  
  
  
