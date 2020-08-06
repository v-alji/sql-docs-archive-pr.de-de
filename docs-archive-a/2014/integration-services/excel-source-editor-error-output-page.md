---
title: Quellen-Editor für Excel (Seite Fehlerausgabe) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.excelsourceadapter.erroroutput.f1
helpviewer_keywords:
- Excel Source Editor
ms.assetid: 8d14019e-cb60-4bc1-b71e-7f2326de8317
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 37b2291844aa690cfe4cd412a14569057adb9e85
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618794"
---
# <a name="excel-source-editor-error-output-page"></a><span data-ttu-id="dda45-102">Quellen-Editor für Excel (Seite Fehlerausgabe)</span><span class="sxs-lookup"><span data-stu-id="dda45-102">Excel Source Editor (Error Output Page)</span></span>
  <span data-ttu-id="dda45-103">Mithilfe der Seite **Fehlerausgabe** des Dialogfelds **Quellen-Editor für Excel** können Sie Fehlerbehandlungsoptionen auswählen und Eigenschaften für Fehlerausgabespalten festlegen.</span><span class="sxs-lookup"><span data-stu-id="dda45-103">Use the **Error Output** page of the **Excel Source Editor** dialog box to select error handling options and to set properties on error output columns.</span></span>  
  
 <span data-ttu-id="dda45-104">Weitere Informationen zur Excel-Quelle finden Sie unter [Excel Source](data-flow/excel-source.md).</span><span class="sxs-lookup"><span data-stu-id="dda45-104">To learn more about the Excel source, see [Excel Source](data-flow/excel-source.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="dda45-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="dda45-105">Options</span></span>  
 <span data-ttu-id="dda45-106">**Eingabe oder Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="dda45-106">**Input or Output**</span></span>  
 <span data-ttu-id="dda45-107">Zeigt den Namen der Datenquelle an.</span><span class="sxs-lookup"><span data-stu-id="dda45-107">View the name of the data source.</span></span>  
  
 <span data-ttu-id="dda45-108">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="dda45-108">**Column**</span></span>  
 <span data-ttu-id="dda45-109">Zeigt die externen (Quell-)Spalten an, die im Dialogfeld **Quellen-Editor für Excel** auf der Seite **Verbindungs-Manager**ausgewählt wurden.</span><span class="sxs-lookup"><span data-stu-id="dda45-109">View the external (source) columns that you selected on the **Connection Manager** page of the **Excel Source Editor**dialog box.</span></span>  
  
 <span data-ttu-id="dda45-110">**Fehler**</span><span class="sxs-lookup"><span data-stu-id="dda45-110">**Error**</span></span>  
 <span data-ttu-id="dda45-111">Gibt an, was bei Auftreten eines Fehlers geschehen soll: den Fehler ignorieren, die Zeile umleiten oder die Komponente mit einem Fehler abbrechen.</span><span class="sxs-lookup"><span data-stu-id="dda45-111">Specify what should happen when an error occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="dda45-112">**Verwandte Themen:** [Fehlerbehandlung in Daten](data-flow/error-handling-in-data.md)</span><span class="sxs-lookup"><span data-stu-id="dda45-112">**Related Topics:** [Error Handling in Data](data-flow/error-handling-in-data.md)</span></span>  
  
 <span data-ttu-id="dda45-113">**Abschneiden**</span><span class="sxs-lookup"><span data-stu-id="dda45-113">**Truncation**</span></span>  
 <span data-ttu-id="dda45-114">Gibt an, was im Falle einer Kürzung geschehen soll: den Fehler ignorieren, die Zeile umleiten oder die Komponente mit einem Fehler abbrechen.</span><span class="sxs-lookup"><span data-stu-id="dda45-114">Specify what should happen when a truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="dda45-115">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="dda45-115">**Description**</span></span>  
 <span data-ttu-id="dda45-116">Zeigt die Beschreibung des Fehlers an.</span><span class="sxs-lookup"><span data-stu-id="dda45-116">View the description of the error.</span></span>  
  
 <span data-ttu-id="dda45-117">**Diesen Wert für ausgewählte Zellen festlegen**</span><span class="sxs-lookup"><span data-stu-id="dda45-117">**Set this value to selected cells**</span></span>  
 <span data-ttu-id="dda45-118">Gibt an, was im Falle eines Fehlers oder einer Kürzung mit den ausgewählten Zellen geschehen soll: den Fehler ignorieren, die Zeile umleiten oder die Komponente mit einem Fehler abbrechen.</span><span class="sxs-lookup"><span data-stu-id="dda45-118">Specify what should happen to all the selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="dda45-119">**Anwenden**</span><span class="sxs-lookup"><span data-stu-id="dda45-119">**Apply**</span></span>  
 <span data-ttu-id="dda45-120">Wendet die Fehlerbehandlungsoption auf die ausgewählten Zellen an.</span><span class="sxs-lookup"><span data-stu-id="dda45-120">Apply the error handling option to the selected cells.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dda45-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dda45-121">See Also</span></span>  
 <span data-ttu-id="dda45-122">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="dda45-122">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="dda45-123">[Der Quellen-Editor für Excel &#40;Seite Verbindungs-Manager&#41;](../../2014/integration-services/excel-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="dda45-123">[Excel Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/excel-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="dda45-124">[Der Quellen-Editor für Excel &#40;Spalten&#41;](../../2014/integration-services/excel-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="dda45-124">[Excel Source Editor &#40;Columns Page&#41;](../../2014/integration-services/excel-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="dda45-125">[Excel-Verbindungs-Manager](connection-manager/excel-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="dda45-125">[Excel Connection Manager](connection-manager/excel-connection-manager.md) </span></span>  
 [<span data-ttu-id="dda45-126">Schleife durch Excel-Dateien und Tabellen mit einem Foreach-Schleifencontainer</span><span class="sxs-lookup"><span data-stu-id="dda45-126">Loop through Excel Files and Tables by Using a Foreach Loop Container</span></span>](control-flow/foreach-loop-container.md)  
  
  
