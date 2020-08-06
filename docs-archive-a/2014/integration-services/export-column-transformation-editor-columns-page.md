---
title: Transformations-Editor für das Exportieren von Spalten (Seite Spalten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fileextractortransformation.columns.f1
helpviewer_keywords:
- Export Column Transformation Editor
ms.assetid: b659a5c2-5509-4b5b-9c82-136c971d5c7f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 404b404e2328228049ae46fb1c3089b0b4089f0a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616121"
---
# <a name="export-column-transformation-editor-columns-page"></a><span data-ttu-id="eba82-102">Transformations-Editor für das Exportieren von Spalten (Seite Spalten)</span><span class="sxs-lookup"><span data-stu-id="eba82-102">Export Column Transformation Editor (Columns Page)</span></span>
  <span data-ttu-id="eba82-103">Auf der Seite **Spalten** des Dialogfelds **Transformations-Editor für das Exportieren von Spalten** können Sie die Spalten im Datenfluss angeben, die in Dateien extrahiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="eba82-103">Use the **Columns** page of the **Export Column Transformation Editor** dialog box to specify columns in the data flow to extract to files.</span></span> <span data-ttu-id="eba82-104">Sie können angeben, ob die Daten durch die Transformation für das Exportieren von Spalten an eine Datei angefügt werden, oder ob eine vorhandene Datei mit den Daten überschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="eba82-104">You can specify whether the Export Column transformation appends data to a file or overwrites an existing file.</span></span>  
  
 <span data-ttu-id="eba82-105">Weitere Informationen zur Transformation für das Exportieren von Spalten finden Sie unter [Export Column Transformation](data-flow/transformations/export-column-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="eba82-105">To learn more about the Export Column transformation, see [Export Column Transformation](data-flow/transformations/export-column-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="eba82-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="eba82-106">Options</span></span>  
 <span data-ttu-id="eba82-107">**Spalte extrahieren**</span><span class="sxs-lookup"><span data-stu-id="eba82-107">**Extract Column**</span></span>  
 <span data-ttu-id="eba82-108">Wählen Sie Spalten aus der Liste der Eingabespalten aus, die Text- oder Bilddaten enthalten.</span><span class="sxs-lookup"><span data-stu-id="eba82-108">Select from the list of input columns that contain text or image data.</span></span> <span data-ttu-id="eba82-109">Alle Zeilen sollten Definitionen für **Spalte extrahieren** und **Dateipfadspalte**aufweisen.</span><span class="sxs-lookup"><span data-stu-id="eba82-109">All rows should have definitions for **Extract Column** and **File Path Column**.</span></span>  
  
 <span data-ttu-id="eba82-110">**Dateipfadspalte**</span><span class="sxs-lookup"><span data-stu-id="eba82-110">**File Path Column**</span></span>  
 <span data-ttu-id="eba82-111">Wählen Sie Spalten aus der Liste der Eingabespalten aus, die Dateipfade und Dateinamen enthalten.</span><span class="sxs-lookup"><span data-stu-id="eba82-111">Select from the list of input columns that contain file paths and file names.</span></span> <span data-ttu-id="eba82-112">Alle Zeilen sollten Definitionen für **Spalte extrahieren** und **Dateipfadspalte**aufweisen.</span><span class="sxs-lookup"><span data-stu-id="eba82-112">All rows should have definitions for **Extract Column** and **File Path Column**.</span></span>  
  
 <span data-ttu-id="eba82-113">**Anfügen zulassen**</span><span class="sxs-lookup"><span data-stu-id="eba82-113">**Allow Append**</span></span>  
 <span data-ttu-id="eba82-114">Geben Sie an, ob Daten durch die Transformation an vorhandene Dateien angefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="eba82-114">Specify whether the transformation appends data to existing files.</span></span> <span data-ttu-id="eba82-115">Der Standardwert lautet `false`.</span><span class="sxs-lookup"><span data-stu-id="eba82-115">The default is `false`.</span></span>  
  
 <span data-ttu-id="eba82-116">**Abschneiden erzwingen**</span><span class="sxs-lookup"><span data-stu-id="eba82-116">**Force Truncate**</span></span>  
 <span data-ttu-id="eba82-117">Geben Sie an, ob die Inhalte vorhandener Dateien vor dem Schreiben der Daten durch die Transformation gelöscht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="eba82-117">Specify whether the transformation deletes the contents of existing files before writing data.</span></span> <span data-ttu-id="eba82-118">Der Standardwert lautet `false`.</span><span class="sxs-lookup"><span data-stu-id="eba82-118">The default is `false`.</span></span>  
  
 <span data-ttu-id="eba82-119">**Bytereihenfolge-Marke schreiben**</span><span class="sxs-lookup"><span data-stu-id="eba82-119">**Write BOM**</span></span>  
 <span data-ttu-id="eba82-120">Geben Sie an, ob eine Bytereihenfolge-Marke in die Datei geschrieben werden soll.</span><span class="sxs-lookup"><span data-stu-id="eba82-120">Specify whether to write a byte-order mark (BOM) to the file.</span></span> <span data-ttu-id="eba82-121">Eine Bytereihenfolge-Marke wird nur geschrieben, wenn die Daten den Datentyp `DT_NTEXT` oder DT_WSTR aufweisen und nicht an eine vorhandene Datendatei angefügt werden.</span><span class="sxs-lookup"><span data-stu-id="eba82-121">A BOM is only written if the data has the `DT_NTEXT` or DT_WSTR data type and is not appended to an existing data file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eba82-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eba82-122">See Also</span></span>  
 <span data-ttu-id="eba82-123">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="eba82-123">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="eba82-124">Transformations-Editor für das Exportieren von Spalten &#40;Seite „Fehlerausgabe“&#41;</span><span class="sxs-lookup"><span data-stu-id="eba82-124">Export Column Transformation Editor &#40;Error Output Page&#41;</span></span>](../../2014/integration-services/export-column-transformation-editor-error-output-page.md)  
  
  
