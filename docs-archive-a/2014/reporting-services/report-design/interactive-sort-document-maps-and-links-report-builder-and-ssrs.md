---
title: Interaktive Sortierung, Dokumentstrukturen und Links (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: cc6ef408-4a76-408a-9d3f-033481fe21cf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 35d88e89ed14a205153374d44562e6d3fda92e02
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723426"
---
# <a name="interactive-sort-document-maps-and-links-report-builder-and-ssrs"></a><span data-ttu-id="81d4d-102">Interaktive Sortierung, Dokumentstrukturen und Links (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="81d4d-102">Interactive Sort, Document Maps, and Links (Report Builder and SSRS)</span></span>
  <span data-ttu-id="81d4d-103">In webbasierten Umgebungen können Sie eine Reihe von Funktionen hinzufügen, über die Benutzer mit Berichten interagieren können.</span><span class="sxs-lookup"><span data-stu-id="81d4d-103">In Web-based environments, you can add a number of features that let your users interact with reports.</span></span> <span data-ttu-id="81d4d-104">Die Benutzer können die Sortierreihenfolge der Werte im Bericht ändern, Elemente im Bericht anzeigen oder ausblenden oder auf Links klicken, die zu anderen Berichten oder Webseiten führen.</span><span class="sxs-lookup"><span data-stu-id="81d4d-104">Your users can change the sort order of values in your report, show or hide items in the report, or click links that go to other reports or Web pages.</span></span> <span data-ttu-id="81d4d-105">Sie können auch ein Inhaltsverzeichnis oder eine Dokumentstruktur hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="81d4d-105">You can also add a table of contents or document map.</span></span> <span data-ttu-id="81d4d-106">Die Berichtsbenutzer können auf Elemente im Inhaltsverzeichnis oder in der Dokumentstruktur klicken, um zu Bereichen in einem Bericht zu springen.</span><span class="sxs-lookup"><span data-stu-id="81d4d-106">Your report users can click items in the table of contents or document map to jump to areas within a report.</span></span>  
  
 <span data-ttu-id="81d4d-107">Berichts-Generator und Berichts-Designer unterstützen drei Arten von Links mit den folgenden Aktionen:</span><span class="sxs-lookup"><span data-stu-id="81d4d-107">Report Builder and Report Designer support three types of links with the following actions:</span></span>  
  
-   <span data-ttu-id="81d4d-108">**Lesezeichenlinks:** Springen zu anderen Bereichen innerhalb des Berichts.</span><span class="sxs-lookup"><span data-stu-id="81d4d-108">**Bookmark links** Jump to other areas within the report.</span></span>  
  
-   <span data-ttu-id="81d4d-109">**Links:** Springen zu URLs, die die Adresse von Webseiten oder Berichten auf einem Berichtsserver per URL-Zugriff angeben.</span><span class="sxs-lookup"><span data-stu-id="81d4d-109">**Hyperlinks** Jump to URLs that specify the address of Web pages or reports on a report server by using URL access.</span></span>  
  
-   <span data-ttu-id="81d4d-110">**Drillthroughberichtslinks:** Wechseln zu anderen Berichten auf demselben Berichtsserver.</span><span class="sxs-lookup"><span data-stu-id="81d4d-110">**Drillthrough report links** Jump to other reports on the same report server.</span></span> <span data-ttu-id="81d4d-111">Weitere Informationen finden Sie unter [Drillthroughberichte (Berichts-Generator und SSRS)](drillthrough-reports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="81d4d-111">For more information, see [Drillthrough Reports &#40;Report Builder and SSRS&#41;](drillthrough-reports-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="81d4d-112">Links, die an Datasetfelder gebunden sind, sind unter Umständen anfällig für böswillige Manipulationen.</span><span class="sxs-lookup"><span data-stu-id="81d4d-112">Links that are bound to dataset fields can be vulnerable to tampering for malicious purposes.</span></span> <span data-ttu-id="81d4d-113">Weitere Informationen finden Sie unter [Sichern von Berichten und Ressourcen](../security/secure-reports-and-resources.md) in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-[Onlinedokumentation](https://go.microsoft.com/fwlink/?LinkId=154888) auf msdn.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="81d4d-113">For more information, see [Secure Reports and Resources](../security/secure-reports-and-resources.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][Books Online](https://go.microsoft.com/fwlink/?LinkId=154888) on msdn.microsoft.com.</span></span>  
  
 <span data-ttu-id="81d4d-114">Durch Entwerfen von Ausdrücken mit Parameterverweisen für Sortierung, Filter und Sichtbarkeit können Sie Benutzern das Anzeigen von Berichten und Inhalten ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="81d4d-114">You can also let your users control report display and content by designing expressions that include parameter references for sort, filter, and visibility.</span></span> <span data-ttu-id="81d4d-115">Weitere Informationen finden Sie unter [Berichtsparameter (Berichts-Generator und Berichts-Designer)](report-parameters-report-builder-and-report-designer.md), [Filtern, Gruppieren und Sortieren von Daten (Berichts-Generator und SSRS)](filter-group-and-sort-data-report-builder-and-ssrs.md) und [Hinzufügen von Datasetfiltern, Datenbereichsfiltern und Gruppenfiltern (Berichts-Generator und SSRS)](add-dataset-filters-data-region-filters-and-group-filters.md).</span><span class="sxs-lookup"><span data-stu-id="81d4d-115">For more information, see [Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md), [Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md), and [Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="in-this-section"></a><span data-ttu-id="81d4d-116">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="81d4d-116">In This Section</span></span>  
 [<span data-ttu-id="81d4d-117">Interaktive Sortierung &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="81d4d-117">Interactive Sort &#40;Report Builder and SSRS&#41;</span></span>](interactive-sort-report-builder-and-ssrs.md)  
 <span data-ttu-id="81d4d-118">Erläutert das Hinzufügen interaktiver Sortierschaltflächen zu Spaltenkopfzeilen.</span><span class="sxs-lookup"><span data-stu-id="81d4d-118">Explains how to add interactive sort buttons to column headers.</span></span>  
  
 [<span data-ttu-id="81d4d-119">Erstellen einer Dokumentstruktur &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="81d4d-119">Create a Document Map &#40;Report Builder and SSRS&#41;</span></span>](create-a-document-map-report-builder-and-ssrs.md)  
 <span data-ttu-id="81d4d-120">Beschreibt, wie Sie ein Inhaltsverzeichnis für die Navigation in einem umfangreichen Bericht hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="81d4d-120">Explains how to add a table of contents to support navigation in a large report.</span></span>  
  
 [<span data-ttu-id="81d4d-121">Hinzufügen eines Lesezeichens zu einem Bericht &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="81d4d-121">Add a Bookmark to a Report &#40;Report Builder and SSRS&#41;</span></span>](add-a-bookmark-to-a-report-report-builder-and-ssrs.md)  
 <span data-ttu-id="81d4d-122">Erläutert, wie Lesezeichen hinzugefügt werden, um in einem Bericht Links zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="81d4d-122">Explains how to add bookmarks to create links within a report.</span></span>  
  
 [<span data-ttu-id="81d4d-123">Hinzufügen eines Links zu einer URL &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="81d4d-123">Add a Hyperlink to a URL &#40;Report Builder and SSRS&#41;</span></span>](add-a-hyperlink-to-a-url-report-builder-and-ssrs.md)  
 <span data-ttu-id="81d4d-124">Erläutert, wie ein Link aus dem Bericht einer URL hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="81d4d-124">Explains how to add a link from your report to a URL</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81d4d-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="81d4d-125">See Also</span></span>  
 [<span data-ttu-id="81d4d-126">Drillthrough, Drilldown, Unterberichte und geschachtelte Datenbereiche &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="81d4d-126">Drillthrough, Drilldown, Subreports, and Nested Data Regions &#40;Report Builder and SSRS&#41;</span></span>](drillthrough-drilldown-subreports-and-nested-data-regions.md)  
  
  
