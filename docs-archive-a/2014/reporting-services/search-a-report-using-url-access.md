---
title: Durchsuchen eines Berichts mit URL-Zugriff | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- searching reports
- text searches [Reporting Services]
- URL access [Reporting Services], report searches
ms.assetid: 6f3410c4-7944-448f-bae8-bab3e8152d46
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b45f3fabf58a0980d41ee7b4b89a771655477d02
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723357"
---
# <a name="search-a-report-using-url-access"></a><span data-ttu-id="c45b0-102">Suchen eines Berichts mithilfe von URL-Zugriff</span><span class="sxs-lookup"><span data-stu-id="c45b0-102">Search a Report Using URL Access</span></span>
  <span data-ttu-id="c45b0-103">Mit einem URL-Zugriff können Sie einen Bericht nach einem bestimmten Textteil durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="c45b0-103">You can search a report for a specific set of text using URL access.</span></span> <span data-ttu-id="c45b0-104">Legen Sie dazu den Wert des *rc:FindString* -Parameters in der URL auf den Text fest, nach dem Sie suchen möchten.</span><span class="sxs-lookup"><span data-stu-id="c45b0-104">To search a report, set the value of the *rc:FindString* parameter on the URL equal to the text for which you want to search.</span></span> <span data-ttu-id="c45b0-105">Beschränken Sie außerdem mit dem *rc:StartFind* - und dem *rc:EndFind* -Parameter Ihre Suche auf bestimmte Seiten im Bericht.</span><span class="sxs-lookup"><span data-stu-id="c45b0-105">Additionally, use the *rc:StartFind* and *rc:EndFind* parameters to narrow your search to specific pages within the report.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c45b0-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c45b0-106">Example</span></span>  
 <span data-ttu-id="c45b0-107">In dem folgenden Beispiel für den URL-Zugriff wird nach dem ersten Vorkommen des Texts "Mountain-400" im Beispielbericht Product Catalog gesucht. Die Suche beginnt auf der ersten Seite und endet auf der fünften Seite:</span><span class="sxs-lookup"><span data-stu-id="c45b0-107">The following URL access example searches for the first occurrence of the text "Mountain-400" in the Product Catalog sample report starting with page one and ending with page five:</span></span>  
  
```  
http://server/Reportserver?/SampleReports/Product Catalog&rs:Command=Render&rc:StartFind=1&rc:EndFind=5&rc:FindString=Mountain-400  
```  
  
## <a name="see-also"></a><span data-ttu-id="c45b0-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c45b0-108">See Also</span></span>  
 <span data-ttu-id="c45b0-109">[URL-Zugriff &#40;SSRS&#41;](url-access-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c45b0-109">[URL Access &#40;SSRS&#41;](url-access-ssrs.md) </span></span>  
 [<span data-ttu-id="c45b0-110">URL Access Parameter Reference (URL-Zugriffsparameterverweis)</span><span class="sxs-lookup"><span data-stu-id="c45b0-110">URL Access Parameter Reference</span></span>](url-access-parameter-reference.md)  
  
  
