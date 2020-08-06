---
title: 'rrRenderingError: Reporting Services-Fehler | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- rrRenderingError
ms.assetid: 0751efc3-b81b-44ee-8aac-8560f86ca322
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b44b042c5f3c0cfdb9ffb99d3f45ed073beb972a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700640"
---
# <a name="rrrenderingerror---reporting-services-error"></a><span data-ttu-id="b7b9f-102">rrRenderingError – Reporting Services-Fehler</span><span class="sxs-lookup"><span data-stu-id="b7b9f-102">rrRenderingError - Reporting Services Error</span></span>
    
## <a name="details"></a><span data-ttu-id="b7b9f-103">Details</span><span class="sxs-lookup"><span data-stu-id="b7b9f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b7b9f-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="b7b9f-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="b7b9f-105">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="b7b9f-105">Event ID</span></span>|<span data-ttu-id="b7b9f-106">rrRenderingError</span><span class="sxs-lookup"><span data-stu-id="b7b9f-106">rrRenderingError</span></span>|  
|<span data-ttu-id="b7b9f-107">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="b7b9f-107">Event Source</span></span>|<span data-ttu-id="b7b9f-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings.resources.Strings</span><span class="sxs-lookup"><span data-stu-id="b7b9f-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings.resources.Strings</span></span>|  
|<span data-ttu-id="b7b9f-109">Komponente</span><span class="sxs-lookup"><span data-stu-id="b7b9f-109">Component</span></span>|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|  
|<span data-ttu-id="b7b9f-110">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="b7b9f-110">Message Text</span></span>|<span data-ttu-id="b7b9f-111">Fehler beim Rendern des Berichts.</span><span class="sxs-lookup"><span data-stu-id="b7b9f-111">An error occurred during rendering of the report.</span></span> <span data-ttu-id="b7b9f-112">(rrRenderingError) %1</span><span class="sxs-lookup"><span data-stu-id="b7b9f-112">(rrRenderingError) %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b7b9f-113">Erklärung</span><span class="sxs-lookup"><span data-stu-id="b7b9f-113">Explanation</span></span>  
 <span data-ttu-id="b7b9f-114">Diese Meldung wird zurückgegeben, wenn der Bericht von [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] nicht gerendert oder exportiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="b7b9f-114">This message is returned when [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] cannot render or export the report.</span></span>  
  
 <span data-ttu-id="b7b9f-115">Eine Meldung, in der angegeben wird, dass das Format nicht unterstützt wird, ist normalerweise darauf zurückzuführen, dass das angegebene RDL-Seitenformat nicht gültig ist.</span><span class="sxs-lookup"><span data-stu-id="b7b9f-115">A message that indicates that the size is not supported is typically caused when the specified RDL page size is not valid.</span></span> <span data-ttu-id="b7b9f-116">Geben Sie ein gültiges RDL-Seitenformat an, und versuchen Sie es dann erneut.</span><span class="sxs-lookup"><span data-stu-id="b7b9f-116">Specify a valid RDL page size and then try again.</span></span>  
  
 <span data-ttu-id="b7b9f-117">Eine Meldung, in der angegeben wird, dass ein RDL-Formatmaß nicht unterstützt wird, ist normalerweise darauf zurückzuführen, dass ein nicht unterstützter Einheitentyp angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="b7b9f-117">A message that indicates that an RDL size measurement is not supported is typically caused when an unsupported unit type is specified.</span></span> <span data-ttu-id="b7b9f-118">Gültige Einheitentypen sind cm, in, mm, pc und pt.</span><span class="sxs-lookup"><span data-stu-id="b7b9f-118">Valid unit types are cm, in, mm, pc, and pt.</span></span> <span data-ttu-id="b7b9f-119">Geben Sie einen gültigen Einheitentyp an, und versuchen Sie es dann erneut.</span><span class="sxs-lookup"><span data-stu-id="b7b9f-119">Specify a valid unit type and then try again.</span></span>  
  
 <span data-ttu-id="b7b9f-120">Eine Meldung, in der angegeben wird, dass ein negatives Format nicht unterstützt wird, ist normalerweise darauf zurückzuführen, dass für das Seitenformat ein negatives Maß angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="b7b9f-120">A message that indicates that a negative size is not supported is typically caused when a negative measurement for the page size, for example -5 cm, is specified.</span></span> <span data-ttu-id="b7b9f-121">Geben Sie eine positive Zahl für das Seitenformat an, und versuchen Sie es dann erneut.</span><span class="sxs-lookup"><span data-stu-id="b7b9f-121">Specify a positive number for the page size and then try again.</span></span>  
  
 <span data-ttu-id="b7b9f-122">Eine Meldung, in der angegeben wird, dass ein RDL-Format außerhalb des zulässigen Bereichs angegeben wurde, ist normalerweise darauf zurückzuführen, dass ein Maß des Papierformats außerhalb des zulässigen Seitenrandformats liegt.</span><span class="sxs-lookup"><span data-stu-id="b7b9f-122">A message that indicates that an RDL size is specified out of range is typically caused when a measurement for the page size is outside of the valid page margin size.</span></span> <span data-ttu-id="b7b9f-123">Geben Sie ein Maß für das Seitenformat an, das innerhalb der gültigen Seitenrandformate liegt.</span><span class="sxs-lookup"><span data-stu-id="b7b9f-123">Specify a measurement for the page size that is within the valid page margin sizes.</span></span>  
  
 <span data-ttu-id="b7b9f-124">Eine Meldung, in der angegeben wird, dass eine angegebene Farbe nicht unterstützt wird, ist normalerweise darauf zurückzuführen, dass eine in der RDL angegebene Farbe nicht gültig ist.</span><span class="sxs-lookup"><span data-stu-id="b7b9f-124">A message that indicates that a color specified is not supported is typically caused when a color specified in the RDL is not valid.</span></span> <span data-ttu-id="b7b9f-125">Wählen Sie eine von RDL unterstützte Farbe aus, und versuchen Sie es dann erneut.</span><span class="sxs-lookup"><span data-stu-id="b7b9f-125">Choose a color supported by RDL and then try again.</span></span>  
  
 <span data-ttu-id="b7b9f-126">Eine Meldung, in der angegeben wird, dass die Aktionsbezeichnung nur optional ist, wenn nur eine einzelne Aktion verwendet wird, und dass das Hinzufügen von mehreren Aktionen Bezeichnungen für die einzelnen Aktionen erfordert, ist normalerweise darauf zurückzuführen, dass zwar eine Aktionsbezeichnung angegeben wurde, diese aber ungültig ist.</span><span class="sxs-lookup"><span data-stu-id="b7b9f-126">A message that indicates that the action label is only optional when using a single action and that adding multiple actions requires labels for each action is typically caused when an action label is specified and it is not valid.</span></span> <span data-ttu-id="b7b9f-127">Geben Sie eine gültige Aktionsbezeichnung für jede Aktion an.</span><span class="sxs-lookup"><span data-stu-id="b7b9f-127">Specify a valid action label for each action.</span></span>  
  
 <span data-ttu-id="b7b9f-128">Eine Meldung, in der angegeben wird, dass ein Stilargument von einem bestimmten Typ sein muss, ist normalerweise darauf zurückzuführen, dass ein ungültiger Stilwert für den Datentyp angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="b7b9f-128">A message that indicates the style argument has to be of a specific type is typically caused when an incorrect style value for the data type is specified.</span></span> <span data-ttu-id="b7b9f-129">Die RDL-Spezifikation identifiziert die gültigen Typen, die Sie in den Stilwerten der verschiedenen RDL-Elemente verwenden können.</span><span class="sxs-lookup"><span data-stu-id="b7b9f-129">The RDL specification identifies the valid types that you can use in the style values of different RDL elements.</span></span> <span data-ttu-id="b7b9f-130">Beispielsweise ist ein falscher Stilwert für die Hintergrundfarbe "2pt" und ein falscher Wert für die Höhe "true".</span><span class="sxs-lookup"><span data-stu-id="b7b9f-130">For example, an incorrect style value for background color is "2pt" and incorrect value for height is "true".</span></span> <span data-ttu-id="b7b9f-131">Geben Sie einen richtigen Wert an, und versuchen Sie es dann erneut.</span><span class="sxs-lookup"><span data-stu-id="b7b9f-131">Specify a correct value and then try again.</span></span>  
  
 <span data-ttu-id="b7b9f-132">Eine Meldung, in der angegeben wird, dass eine Rahmenart nicht unterstützt wird, ist normalerweise darauf zurückzuführen, dass eine angegebene Rahmenart nicht gültig ist.</span><span class="sxs-lookup"><span data-stu-id="b7b9f-132">A message that indicates that the border style is not supported is typically caused when the border style specified is not valid.</span></span> <span data-ttu-id="b7b9f-133">Geben Sie eine unterstützte Rahmenart an, und versuchen Sie es dann erneut.</span><span class="sxs-lookup"><span data-stu-id="b7b9f-133">Specify a supported border style and then try again.</span></span>  
  
 <span data-ttu-id="b7b9f-134">Eine Meldung, in der angegeben wird, dass der Bild-Mimetyp nicht unterstützt wird, ist normalerweise darauf zurückzuführen, dass der für ein Bildberichtselement angegebene Mimetyp nicht gültig ist.</span><span class="sxs-lookup"><span data-stu-id="b7b9f-134">A message that indicates that the image mimetype is not supported is typically caused when the specified mimetype for an image report item is not valid.</span></span> <span data-ttu-id="b7b9f-135">Geben Sie einen unterstützten Mimetyp für das Berichtselement an, und versuchen Sie es dann erneut.</span><span class="sxs-lookup"><span data-stu-id="b7b9f-135">Specify a supported mimetype for the report item and then try again.</span></span>  
  
 <span data-ttu-id="b7b9f-136">Eine Meldung, in der angegeben wird, dass die Zeilenanzahl die maximal pro Blatt zulässigen Zeilen übersteigt, ist normalerweise darauf zurückzuführen, dass die Zeilenanzahl eines Excel-Arbeitsblatts überschritten wurde.</span><span class="sxs-lookup"><span data-stu-id="b7b9f-136">A message that indicates that the number of rows exceeds the maximum possible rows per sheet is typically caused when the number of rows in an Excel worksheet is exceeded.</span></span> <span data-ttu-id="b7b9f-137">Excel unterstützt bis zu 65.000 Zeilen.</span><span class="sxs-lookup"><span data-stu-id="b7b9f-137">Excel supports up to 65,000 rows.</span></span>  
  
 <span data-ttu-id="b7b9f-138">Eine Meldung, in der angegeben wird, dass die Spaltenanzahl die maximal pro Blatt zulässigen Spalten übersteigt, ist normalerweise darauf zurückzuführen, dass die Spaltenanzahl eines Excel-Arbeitsblatts überschritten wurde.</span><span class="sxs-lookup"><span data-stu-id="b7b9f-138">A message that indicates that the number of columns exceeds the maximum possible columns per sheet is typically caused when the number of columns in an Excel worksheet is exceeded.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b7b9f-139">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="b7b9f-139">User Action</span></span>  
  
## <a name="internal-only"></a><span data-ttu-id="b7b9f-140">Nur intern</span><span class="sxs-lookup"><span data-stu-id="b7b9f-140">Internal-Only</span></span>  
  
