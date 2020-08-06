---
title: Transformations-Editor für Suche (Seite "Erweitert") | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.lookuptransformation.advanced.f1
helpviewer_keywords:
- Lookup Transformation Editor
ms.assetid: f3395c65-0320-47f9-8d83-daaa082d8713
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 23f235ef0506da7ac808d832db6ac36d53cfa604
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618105"
---
# <a name="lookup-transformation-editor-advanced-page"></a><span data-ttu-id="1e121-102">Transformations-Editor für Suche (Seite 'Erweitert')</span><span class="sxs-lookup"><span data-stu-id="1e121-102">Lookup Transformation Editor (Advanced Page)</span></span>
  <span data-ttu-id="1e121-103">Auf der Seite **Erweitert** des Dialogfelds **Transformations-Editor für Suche** können Sie die teilweise Zwischenspeicherung konfigurieren und die SQL-Anweisung für die Suchtransformation ändern.</span><span class="sxs-lookup"><span data-stu-id="1e121-103">Use the **Advanced** page of the **Lookup Transformation Editor** dialog box to configure partial caching and to modify the SQL statement for the Lookup transformation.</span></span>  
  
 <span data-ttu-id="1e121-104">Weitere Informationen zur Transformation für Suche finden Sie unter [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="1e121-104">To learn more about the Lookup transformation, see [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="1e121-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="1e121-105">Options</span></span>  
 <span data-ttu-id="1e121-106">**Cachegröße (32-Bit)**</span><span class="sxs-lookup"><span data-stu-id="1e121-106">**Cache size (32-bit)**</span></span>  
 <span data-ttu-id="1e121-107">Passen Sie die Cachegröße (in Megabytes) für 32-Bit-Computer an.</span><span class="sxs-lookup"><span data-stu-id="1e121-107">Adjust the  cache size (in megabytes) for 32-bit computers.</span></span> <span data-ttu-id="1e121-108">Der Standardwert ist 5 Megabytes.</span><span class="sxs-lookup"><span data-stu-id="1e121-108">The default value is 5 megabytes.</span></span>  
  
 <span data-ttu-id="1e121-109">**Cachegröße (64-Bit)**</span><span class="sxs-lookup"><span data-stu-id="1e121-109">**Cache size (64-bit)**</span></span>  
 <span data-ttu-id="1e121-110">Passen Sie die Cachegröße (in Megabytes) für 64-Bit-Computer an.</span><span class="sxs-lookup"><span data-stu-id="1e121-110">Adjust the cache size (in megabytes) for 64-bit computers.</span></span> <span data-ttu-id="1e121-111">Der Standardwert ist 5 Megabytes.</span><span class="sxs-lookup"><span data-stu-id="1e121-111">The default value is 5 megabytes.</span></span>  
  
 <span data-ttu-id="1e121-112">**Cache für Zeilen ohne übereinstimmende Einträge aktivieren**</span><span class="sxs-lookup"><span data-stu-id="1e121-112">**Enable cache for rows with no matching entries**</span></span>  
 <span data-ttu-id="1e121-113">Zeilen ohne übereinstimmende Einträge im Verweisdataset werden zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="1e121-113">Cache rows with no matching entries in the reference dataset.</span></span>  
  
 <span data-ttu-id="1e121-114">**Zuordnung von Cache**</span><span class="sxs-lookup"><span data-stu-id="1e121-114">**Allocation from cache**</span></span>  
 <span data-ttu-id="1e121-115">Geben Sie den Prozentsatz des Caches an, der für Zeilen ohne übereinstimmende Einträge im Verweisdataset zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="1e121-115">Specify the percentage of the cache to allocate for rows with no matching entries in the reference dataset.</span></span>  
  
 <span data-ttu-id="1e121-116">**SQL-Anweisung ändern**</span><span class="sxs-lookup"><span data-stu-id="1e121-116">**Modify the SQL statement**</span></span>  
 <span data-ttu-id="1e121-117">Hiermit ändern Sie die zum Generieren des Verweisdatasets verwendete SQL-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="1e121-117">Modify the SQL statement that is used to generate the reference dataset.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1e121-118">Durch die auf dieser Seite angegebene optionale SQL-Anweisung wird der auf der Seite **Verbindung** im **Transformations-Editor für Suche**angegebene Tabellenname überschrieben und ersetzt.</span><span class="sxs-lookup"><span data-stu-id="1e121-118">The optional SQL statement that you specify on this page overrides and replaces the table name that you specified on the **Connection** page of the **Lookup Transformation Editor**.</span></span> <span data-ttu-id="1e121-119">Weitere Informationen finden Sie unter [Transformations-Editor für Suche &#40;Seite „Verbindung“&#41;](../../2014/integration-services/lookup-transformation-editor-connection-page.md).</span><span class="sxs-lookup"><span data-stu-id="1e121-119">For more information, see [Lookup Transformation Editor &#40;Connection Page&#41;](../../2014/integration-services/lookup-transformation-editor-connection-page.md).</span></span>  
  
 <span data-ttu-id="1e121-120">**Abfrageparameter festlegen**</span><span class="sxs-lookup"><span data-stu-id="1e121-120">**Set Parameters**</span></span>  
 <span data-ttu-id="1e121-121">Ordnen Sie mithilfe des Dialogfelds **Abfrageparameter festlegen** die Eingabespalten den Parametern zu.</span><span class="sxs-lookup"><span data-stu-id="1e121-121">Map input columns to parameters by using the **Set Query Parameters** dialog box.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="1e121-122">Externe Ressourcen</span><span class="sxs-lookup"><span data-stu-id="1e121-122">External Resources</span></span>  
 <span data-ttu-id="1e121-123">Blogeintrag [Lookup cache modes](https://go.microsoft.com/fwlink/?LinkId=219518) (Suchcachemodi) auf blogs.msdn.com</span><span class="sxs-lookup"><span data-stu-id="1e121-123">Blog entry, [Lookup cache modes](https://go.microsoft.com/fwlink/?LinkId=219518) on blogs.msdn.com</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e121-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1e121-124">See Also</span></span>  
 <span data-ttu-id="1e121-125">[Transformations-Editor für Suche &#40;Seite "Allgemein"&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="1e121-125">[Lookup Transformation Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="1e121-126">[Transformations-Editor für Suche &#40;Verbindungs Seite&#41;](../../2014/integration-services/lookup-transformation-editor-connection-page.md) </span><span class="sxs-lookup"><span data-stu-id="1e121-126">[Lookup Transformation Editor &#40;Connection Page&#41;](../../2014/integration-services/lookup-transformation-editor-connection-page.md) </span></span>  
 <span data-ttu-id="1e121-127">[Transformations-Editor für Suche &#40;Seite "Spalten"&#41;](../../2014/integration-services/lookup-transformation-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="1e121-127">[Lookup Transformation Editor &#40;Columns Page&#41;](../../2014/integration-services/lookup-transformation-editor-columns-page.md) </span></span>  
 <span data-ttu-id="1e121-128">[Transformations-Editor für Suche &#40;Seite "Fehlerausgabe"&#41;](../../2014/integration-services/lookup-transformation-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="1e121-128">[Lookup Transformation Editor &#40;Error Output Page&#41;](../../2014/integration-services/lookup-transformation-editor-error-output-page.md) </span></span>  
 <span data-ttu-id="1e121-129">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="1e121-129">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="1e121-130">Transformation für Fuzzysuche</span><span class="sxs-lookup"><span data-stu-id="1e121-130">Fuzzy Lookup Transformation</span></span>](data-flow/transformations/fuzzy-lookup-transformation.md)  
  
  
