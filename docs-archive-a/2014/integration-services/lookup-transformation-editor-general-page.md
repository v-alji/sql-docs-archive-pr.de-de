---
title: Transformations-Editor für Suche (Seite "Allgemein") | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.lookuptransformation.general.f1
ms.assetid: 4bd15e48-0feb-4f95-be91-5df58105dbfb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: aa178118f7e090b6a3c15c7ab9347f322461f07b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696982"
---
# <a name="lookup-transformation-editor-general-page"></a><span data-ttu-id="447d6-102">Transformations-Editor für Suche (Seite 'Allgemein')</span><span class="sxs-lookup"><span data-stu-id="447d6-102">Lookup Transformation Editor (General Page)</span></span>
  <span data-ttu-id="447d6-103">Auf der Seite **Allgemein** des Dialogfelds Transformations-Editor für Suche können Sie den Cachemodus und den Verbindungstyp auswählen sowie angeben, wie Zeilen ohne übereinstimmende Einträge behandelt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="447d6-103">Use the **General** page of the Lookup Transformation Editor dialog box to select the cache mode, select the connection type, and specify how to handle rows with no matching entries.</span></span>  
  
 <span data-ttu-id="447d6-104">Weitere Informationen zur Transformation für Suche finden Sie unter [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="447d6-104">To learn more about the Lookup transformation, see [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="447d6-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="447d6-105">Options</span></span>  
 <span data-ttu-id="447d6-106">**Vollcache**</span><span class="sxs-lookup"><span data-stu-id="447d6-106">**Full cache**</span></span>  
 <span data-ttu-id="447d6-107">Das Verweisdataset wird generiert und in den Cache geladen, bevor die Transformation für Suche ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="447d6-107">Generate and load the reference dataset into cache before the Lookup transformation is executed.</span></span>  
  
 <span data-ttu-id="447d6-108">**Teilcache**</span><span class="sxs-lookup"><span data-stu-id="447d6-108">**Partial cache**</span></span>  
 <span data-ttu-id="447d6-109">Das Verweisdataset wird während der Ausführung der Transformation für Suche generiert.</span><span class="sxs-lookup"><span data-stu-id="447d6-109">Generate the reference dataset during the execution of the Lookup transformation.</span></span> <span data-ttu-id="447d6-110">Die Zeilen mit übereinstimmenden Einträgen im Verweisdataset und die Zeilen ohne übereinstimmende Einträge im Dataset werden in den Cache geladen.</span><span class="sxs-lookup"><span data-stu-id="447d6-110">Load the rows with matching entries in the reference dataset and the rows with no matching entries in the dataset into cache.</span></span>  
  
 <span data-ttu-id="447d6-111">**Kein Cache**</span><span class="sxs-lookup"><span data-stu-id="447d6-111">**No cache**</span></span>  
 <span data-ttu-id="447d6-112">Das Verweisdataset wird während der Ausführung der Transformation für Suche generiert.</span><span class="sxs-lookup"><span data-stu-id="447d6-112">Generate the reference dataset during the execution of the Lookup transformation.</span></span> <span data-ttu-id="447d6-113">Es werden keine Daten in den Zwischenspeicher geladen.</span><span class="sxs-lookup"><span data-stu-id="447d6-113">No data is loaded into cache.</span></span>  
  
 <span data-ttu-id="447d6-114">**Cacheverbindungs-Manager**</span><span class="sxs-lookup"><span data-stu-id="447d6-114">**Cache connection manager**</span></span>  
 <span data-ttu-id="447d6-115">Die Transformation für Suche wird für die Verwendung eines Cacheverbindungs-Managers konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="447d6-115">Configure the Lookup transformation to use a Cache connection manager.</span></span> <span data-ttu-id="447d6-116">Diese Option ist nur verfügbar, wenn die Option Vollcache ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="447d6-116">This option is available only if the Full cache option is selected.</span></span>  
  
 <span data-ttu-id="447d6-117">**Teilcache**</span><span class="sxs-lookup"><span data-stu-id="447d6-117">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="447d6-118">Die Transformation für Suche wird für die Verwendung eines OLE DB-Verbindungs-Managers konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="447d6-118">Configure the Lookup transformation to use an OLE DB connection manager.</span></span>  
  
 <span data-ttu-id="447d6-119">**Angeben, wie Zeilen ohne übereinstimmende Einträge behandelt werden sollen**</span><span class="sxs-lookup"><span data-stu-id="447d6-119">**Specify how to handle rows with no matching entries**</span></span>  
 <span data-ttu-id="447d6-120">Wählen Sie eine Option für die Behandlung von Zeilen aus, die nicht mindestens einem Eintrag im Verweisdataset entsprechen.</span><span class="sxs-lookup"><span data-stu-id="447d6-120">Select an option for handling rows that do not match at least one entry in the reference dataset.</span></span>  
  
 <span data-ttu-id="447d6-121">Wenn Sie **Zeilen an Ausgabe nicht übereinstimmender Einträge umleiten**auswählen, werden die Zeilen an eine Ausgabe nicht übereinstimmender Einträge weitergeleitet und nicht als Fehler behandelt.</span><span class="sxs-lookup"><span data-stu-id="447d6-121">When you select **Redirect rows to no match output**, the rows are redirected to a no match output and are not handled as errors.</span></span> <span data-ttu-id="447d6-122">Die Option **Fehler** auf der Seite **Fehlerausgabe** des Dialogfelds **Transformations-Editor für Suche** ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="447d6-122">The **Error** option on the **Error Output** page of the **Lookup Transformation Editor** dialog box is not available.</span></span>  
  
 <span data-ttu-id="447d6-123">Wenn Sie im Listenfeld **Angeben, wie Zeilen ohne übereinstimmende Einträge behandelt werden sollen** eine andere Option auswählen, werden die Zeilen als Fehler behandelt.</span><span class="sxs-lookup"><span data-stu-id="447d6-123">When you select any other option in the **Specify how to handle rows with no matching entries** list box, the rows are handled as errors.</span></span> <span data-ttu-id="447d6-124">In diesem Fall ist die Option **Fehler** auf der Seite **Fehlerausgabe** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="447d6-124">The **Error** option on the **Error Output** page is available.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="447d6-125">Externe Ressourcen</span><span class="sxs-lookup"><span data-stu-id="447d6-125">External Resources</span></span>  
 <span data-ttu-id="447d6-126">Blogeintrag [Lookup cache modes](https://go.microsoft.com/fwlink/?LinkId=219518) (Suchcachemodi) auf blogs.msdn.com</span><span class="sxs-lookup"><span data-stu-id="447d6-126">Blog entry, [Lookup cache modes](https://go.microsoft.com/fwlink/?LinkId=219518) on blogs.msdn.com</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="447d6-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="447d6-127">See Also</span></span>  
 <span data-ttu-id="447d6-128">[Cacheverbindungs-Manager](connection-manager/cache-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="447d6-128">[Cache Connection Manager](connection-manager/cache-connection-manager.md) </span></span>  
 <span data-ttu-id="447d6-129">[Transformations-Editor für Suche &#40;Verbindungs Seite&#41;](../../2014/integration-services/lookup-transformation-editor-connection-page.md) </span><span class="sxs-lookup"><span data-stu-id="447d6-129">[Lookup Transformation Editor &#40;Connection Page&#41;](../../2014/integration-services/lookup-transformation-editor-connection-page.md) </span></span>  
 <span data-ttu-id="447d6-130">[Transformations-Editor für Suche &#40;Seite "Spalten"&#41;](../../2014/integration-services/lookup-transformation-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="447d6-130">[Lookup Transformation Editor &#40;Columns Page&#41;](../../2014/integration-services/lookup-transformation-editor-columns-page.md) </span></span>  
 <span data-ttu-id="447d6-131">[Transformations-Editor für Suche &#40;Seite "Erweitert"&#41;](../../2014/integration-services/lookup-transformation-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="447d6-131">[Lookup Transformation Editor &#40;Advanced Page&#41;](../../2014/integration-services/lookup-transformation-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="447d6-132">Transformations-Editor für Suche &#40;Seite „Fehlerausgabe“&#41;</span><span class="sxs-lookup"><span data-stu-id="447d6-132">Lookup Transformation Editor &#40;Error Output Page&#41;</span></span>](../../2014/integration-services/lookup-transformation-editor-error-output-page.md)  
  
  
