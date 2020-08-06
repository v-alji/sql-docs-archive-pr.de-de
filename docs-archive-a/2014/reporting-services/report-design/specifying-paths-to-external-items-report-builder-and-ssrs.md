---
title: Angeben von Pfaden zu externen Elementen (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4fe513da-f3c5-479c-9fec-8662b91a0d6d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 097a3566f914e7810039ee07bc3d3bf3185d7f06
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608266"
---
# <a name="specifying-paths-to-external-items-report-builder-and-ssrs"></a><span data-ttu-id="8d89e-102">Angeben von Pfaden zu externen Elementen (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="8d89e-102">Specifying Paths to External Items (Report Builder and SSRS)</span></span>
  <span data-ttu-id="8d89e-103">Sie geben Pfade in Berichtselementeigenschaften an, um auf Elemente wie Drillthroughberichte, Unterberichte und Bilddateien zu verweisen, die nicht in der Berichtsdefinitionsdatei enthalten und auf einem Berichtsserver gespeichert sind (externe Elemente).</span><span class="sxs-lookup"><span data-stu-id="8d89e-103">You specify paths in report item properties to reference items such as drillthrough reports, subreports, and image files that are external to the report definition file and are stored on a report server.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
> [!NOTE]  
>  <span data-ttu-id="8d89e-104">Im Berichts-Generator müssen in den Pfaden zu Elementen Elemente auf einem Berichtsserver angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8d89e-104">In Report Builder, paths to items must specify items on a report server.</span></span> <span data-ttu-id="8d89e-105">Pfade zu Elementen in einem Dateisystem werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8d89e-105">Paths to items on a file system are not supported.</span></span> <span data-ttu-id="8d89e-106">Sie können einen Bericht mit diesen Elementen nur in der Vorschau anzeigen, wenn Sie mit dem Berichtsserver mit den Elementen verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="8d89e-106">You can preview a report that uses these items only if you are connected to the report server where the items are located.</span></span>  
  
 <span data-ttu-id="8d89e-107">Wenn Sie Pfade für ein externes Element in einem Dialogfeld für Aktionen, Unterberichte oder Bilder angeben, können Sie direkt zu dem Berichtsserver navigieren und das Element auswählen.</span><span class="sxs-lookup"><span data-stu-id="8d89e-107">When you specify a path for an external item in a dialog box for actions, subreports, or images, you can browse directly to the report server and select the item.</span></span> <span data-ttu-id="8d89e-108">Zum Angeben von Drillthroughberichten oder Unterberichten wird empfohlen, direkt zu einem Element zu navigieren und es auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="8d89e-108">Browsing to an item and selecting it directly is the recommended way to specify a drillthrough report or subreport.</span></span> <span data-ttu-id="8d89e-109">Auf diese Weise werden die richtigen Parameternamen in einer Dropdownliste angezeigt, wenn Sie Berichts- oder Unterberichtsparameter angeben.</span><span class="sxs-lookup"><span data-stu-id="8d89e-109">That way the correct parameter names will be available in a drop-down list when you specify report or subreport parameters.</span></span> <span data-ttu-id="8d89e-110">Wenn Sie einen Elementpfad ändern, damit er auf ein anderes Element zeigt, müssen Sie den korrekten Parameternamen und die Parameterwerte ggf. manuell aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="8d89e-110">When you change an item path to point to a different item, you must manually update the correct parameter names and values as needed.</span></span>  
  
 <span data-ttu-id="8d89e-111">Auf einem im einheitlichen Modus konfigurierten Berichtsserver geben Sie den Namen für einen Drillthroughbericht ohne die Dateinamenerweiterung ".rdl" an.</span><span class="sxs-lookup"><span data-stu-id="8d89e-111">On a report server configured in native mode, specify a drillthrough report name without the file extension .rdl.</span></span>  
  
 <span data-ttu-id="8d89e-112">Bei einem im integrierten SharePoint-Modus konfigurierten Berichtsserver müssen Sie die Dateinamenerweiterung ".rdl" einschließen.</span><span class="sxs-lookup"><span data-stu-id="8d89e-112">On a report server configured in SharePoint integrated mode, you must include the file extension .rdl.</span></span> <span data-ttu-id="8d89e-113">Folgende Pfade sind möglich:</span><span class="sxs-lookup"><span data-stu-id="8d89e-113">The path can be one of the following:</span></span>  
  
-   <span data-ttu-id="8d89e-114">**Ein relativer Pfad zu dem Element aus dem Hauptbericht.**</span><span class="sxs-lookup"><span data-stu-id="8d89e-114">**A relative path to the item from the main report.**</span></span> <span data-ttu-id="8d89e-115">Beispiel: ../AllSubreports/Subreport1.</span><span class="sxs-lookup"><span data-stu-id="8d89e-115">For example, ../AllSubreports/Subreport1.</span></span> <span data-ttu-id="8d89e-116">In diesem Beispiel gibt **..**</span><span class="sxs-lookup"><span data-stu-id="8d89e-116">In this example, the **..**</span></span> <span data-ttu-id="8d89e-117">den Ordner über dem Ordner an, in dem der Hauptbericht gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="8d89e-117">indicates the folder above the folder where the main report is located.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8d89e-118">Relative Pfade werden nicht unterstützt, wenn der Bericht in Berichts-Generator ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8d89e-118">Relative paths are not supported when the report is run inside Report Builder.</span></span> <span data-ttu-id="8d89e-119">Wenn Sie einen Bericht anzeigen möchten, in dem relative Pfade zu externen Elementen verwendet werden, speichern Sie den Bericht auf dem Berichtsserver, und führen Sie den Bericht von dort aus.</span><span class="sxs-lookup"><span data-stu-id="8d89e-119">To view a report that uses relative paths to external items, save the report to the report server, and run the report from there</span></span>  
  
-   <span data-ttu-id="8d89e-120">**Ein vollständiger Pfad zum Element.**</span><span class="sxs-lookup"><span data-stu-id="8d89e-120">**A full path to the item.**</span></span>  
  
    -   <span data-ttu-id="8d89e-121">**Auf einem Berichtsserver:** Der Pfad beginnt mit **/** , dem Basisordner.</span><span class="sxs-lookup"><span data-stu-id="8d89e-121">**On a report server:** The path starts from **/**, the Home folder.</span></span> <span data-ttu-id="8d89e-122">Beispiel: /Reports/AllSubreports/Subreport1.</span><span class="sxs-lookup"><span data-stu-id="8d89e-122">For example, /Reports/AllSubreports/Subreport1.</span></span>  
  
    -   <span data-ttu-id="8d89e-123">**Auf einer SharePoint-Website:** Sie müssen den Berichtsnamen in einem Ausdruck angeben, mit der vollständigen URL des Elements und der Dateierweiterung ".rdl".</span><span class="sxs-lookup"><span data-stu-id="8d89e-123">**On a SharePoint site:** You must specify the report name in an expression, with the full URL of the item and the file extension .rdl.</span></span> <span data-ttu-id="8d89e-124">Beispiel: `="http://server/site/library/folder/Report1.rdl"`.</span><span class="sxs-lookup"><span data-stu-id="8d89e-124">For example, `="http://server/site/library/folder/Report1.rdl"`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d89e-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8d89e-125">See Also</span></span>  
 <span data-ttu-id="8d89e-126">[Hinzufügen eines externen Bilds &#40;Berichts-Generator und SSRS&#41;](add-an-external-image-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8d89e-126">[Add an External Image &#40;Report Builder and SSRS&#41;](add-an-external-image-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="8d89e-127">[Hinzufügen eines Unterberichts und Hinzufügen von Parametern (Berichts-Generator und SSRS)](add-a-subreport-and-parameters-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8d89e-127">[Add a Subreport and Parameters &#40;Report Builder and SSRS&#41;](add-a-subreport-and-parameters-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="8d89e-128">Hinzufügen einer Drillthroughaktion für einen Bericht (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="8d89e-128">Add a Drillthrough Action on a Report &#40;Report Builder and SSRS&#41;</span></span>](add-a-drillthrough-action-on-a-report-report-builder-and-ssrs.md)  
  
  