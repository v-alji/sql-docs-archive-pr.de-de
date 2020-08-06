---
title: Ziel-Editor für Excel (Seite Fehlerausgabe) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.exceldestadapter.erroroutput.f1
helpviewer_keywords:
- Excel Destination Editor
ms.assetid: 72ae01cc-1774-4a36-9674-a0f2b2bf8c42
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bee679f563105cade3053a13eb122f6d482a7d86
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618799"
---
# <a name="excel-destination-editor-error-output-page"></a><span data-ttu-id="d5e47-102">Ziel-Editor für Excel (Seite Fehlerausgabe)</span><span class="sxs-lookup"><span data-stu-id="d5e47-102">Excel Destination Editor (Error Output Page)</span></span>
  <span data-ttu-id="d5e47-103">Auf der Seite **Erweitert** in **Ziel-Editor für Excel** können Sie die Optionen für die Fehlerbehandlung angeben.</span><span class="sxs-lookup"><span data-stu-id="d5e47-103">Use the **Advanced** page of the **Excel Destination Editor** dialog box to specify options for error handling.</span></span>  
  
 <span data-ttu-id="d5e47-104">Weitere Informationen zum Excel-Ziel finden Sie unter [Excel Destination](data-flow/excel-destination.md).</span><span class="sxs-lookup"><span data-stu-id="d5e47-104">To learn more about the Excel destination, see [Excel Destination](data-flow/excel-destination.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="d5e47-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="d5e47-105">Options</span></span>  
 <span data-ttu-id="d5e47-106">**Eingabe oder Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="d5e47-106">**Input or Output**</span></span>  
 <span data-ttu-id="d5e47-107">Zeigt den Namen der Datenquelle an.</span><span class="sxs-lookup"><span data-stu-id="d5e47-107">View the name of the data source.</span></span>  
  
 <span data-ttu-id="d5e47-108">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="d5e47-108">**Column**</span></span>  
 <span data-ttu-id="d5e47-109">Zeigt die externen (Quell-)Spalten an, die im Dialogfeld **Quellen-Editor für Excel** im Knoten **Verbindungs-Manager**ausgewählt wurden.</span><span class="sxs-lookup"><span data-stu-id="d5e47-109">View the external (source) columns that you selected in the **Connection Manager** node of the **Excel Source Editor**dialog box.</span></span>  
  
 <span data-ttu-id="d5e47-110">**Fehler**</span><span class="sxs-lookup"><span data-stu-id="d5e47-110">**Error**</span></span>  
 <span data-ttu-id="d5e47-111">Gibt an, was bei Auftreten eines Fehlers geschehen soll: den Fehler ignorieren, die Zeile umleiten oder die Komponente mit einem Fehler abbrechen.</span><span class="sxs-lookup"><span data-stu-id="d5e47-111">Specify what should happen when an error occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="d5e47-112">**Verwandte Themen:** [Fehlerbehandlung in Daten](data-flow/error-handling-in-data.md)</span><span class="sxs-lookup"><span data-stu-id="d5e47-112">**Related Topics:** [Error Handling in Data](data-flow/error-handling-in-data.md)</span></span>  
  
 <span data-ttu-id="d5e47-113">**Abschneiden**</span><span class="sxs-lookup"><span data-stu-id="d5e47-113">**Truncation**</span></span>  
 <span data-ttu-id="d5e47-114">Gibt an, was im Falle einer Kürzung geschehen soll: den Fehler ignorieren, die Zeile umleiten oder die Komponente mit einem Fehler abbrechen.</span><span class="sxs-lookup"><span data-stu-id="d5e47-114">Specify what should happen when a truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="d5e47-115">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="d5e47-115">**Description**</span></span>  
 <span data-ttu-id="d5e47-116">Zeigt die Beschreibung des Fehlers an.</span><span class="sxs-lookup"><span data-stu-id="d5e47-116">View the description of the error.</span></span>  
  
 <span data-ttu-id="d5e47-117">**Diesen Wert für ausgewählte Zellen festlegen**</span><span class="sxs-lookup"><span data-stu-id="d5e47-117">**Set this value to selected cells**</span></span>  
 <span data-ttu-id="d5e47-118">Gibt an, was im Falle eines Fehlers oder einer Kürzung mit den ausgewählten Zellen geschehen soll: den Fehler ignorieren, die Zeile umleiten oder die Komponente mit einem Fehler abbrechen.</span><span class="sxs-lookup"><span data-stu-id="d5e47-118">Specify what should happen to all the selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="d5e47-119">**Anwenden**</span><span class="sxs-lookup"><span data-stu-id="d5e47-119">**Apply**</span></span>  
 <span data-ttu-id="d5e47-120">Wendet die Fehlerbehandlungsoption auf die ausgewählten Zellen an.</span><span class="sxs-lookup"><span data-stu-id="d5e47-120">Apply the error handling option to the selected cells.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5e47-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d5e47-121">See Also</span></span>  
 <span data-ttu-id="d5e47-122">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="d5e47-122">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="d5e47-123">[Der Ziel-Editor für Excel &#40;Seite Verbindungs-Manager&#41;](../../2014/integration-services/excel-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="d5e47-123">[Excel Destination Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/excel-destination-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="d5e47-124">[Ziel-Editor für Excel &#40;Seite "Zuordnungen"&#41;](../../2014/integration-services/excel-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="d5e47-124">[Excel Destination Editor &#40;Mappings Page&#41;](../../2014/integration-services/excel-destination-editor-mappings-page.md) </span></span>  
 [<span data-ttu-id="d5e47-125">Schleife durch Excel-Dateien und Tabellen mit einem Foreach-Schleifencontainer</span><span class="sxs-lookup"><span data-stu-id="d5e47-125">Loop through Excel Files and Tables by Using a Foreach Loop Container</span></span>](control-flow/foreach-loop-container.md)  
  
  
