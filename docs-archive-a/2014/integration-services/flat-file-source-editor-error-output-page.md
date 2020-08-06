---
title: Quellen-Editor für Flatfiles (Seite Fehlerausgabe) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.flatfilesourceadapter.errorhandling.f1
helpviewer_keywords:
- Flat File Source Editor
ms.assetid: c50500e7-0c74-42a0-865f-301f03feffab
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 096de22c65d605fc1beea06cbb6ad5909788b408
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609347"
---
# <a name="flat-file-source-editor-error-output-page"></a><span data-ttu-id="ae0f3-102">Quellen-Editor für Flatfiles (Seite Fehlerausgabe)</span><span class="sxs-lookup"><span data-stu-id="ae0f3-102">Flat File Source Editor (Error Output Page)</span></span>
  <span data-ttu-id="ae0f3-103">Mithilfe der Seite **Fehlerausgabe** im Dialogfeld **Quellen-Editor für Flatfiles** können Sie Fehlerbehandlungsoptionen auswählen und Eigenschaften für Fehlerausgabespalten festlegen.</span><span class="sxs-lookup"><span data-stu-id="ae0f3-103">Use the **Error Output** page of the **Flat File Source Editor** dialog box to select error-handling options and to set properties on error output columns.</span></span>\  
  
 <span data-ttu-id="ae0f3-104">Weitere Informationen zur Flatfilequelle finden Sie unter [Flat File Source](data-flow/flat-file-source.md).</span><span class="sxs-lookup"><span data-stu-id="ae0f3-104">To learn more about the Flat File source, see [Flat File Source](data-flow/flat-file-source.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="ae0f3-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="ae0f3-105">Options</span></span>  
 <span data-ttu-id="ae0f3-106">**Eingabe/Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="ae0f3-106">**Input/Output**</span></span>  
 <span data-ttu-id="ae0f3-107">Zeigt den Namen der Datenquelle an.</span><span class="sxs-lookup"><span data-stu-id="ae0f3-107">View the name of the data source.</span></span>  
  
 <span data-ttu-id="ae0f3-108">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="ae0f3-108">**Column**</span></span>  
 <span data-ttu-id="ae0f3-109">Zeigt die externen (Quell-)Spalten an, die im Dialogfeld **Quellen-Editor für Flatfiles** auf der Seite **Verbindungs-Manager**ausgewählt wurden.</span><span class="sxs-lookup"><span data-stu-id="ae0f3-109">View the external (source) columns that you selected on the **Connection Manager** page of the **Flat File Source Editor**dialog box.</span></span>  
  
 <span data-ttu-id="ae0f3-110">**Fehler**</span><span class="sxs-lookup"><span data-stu-id="ae0f3-110">**Error**</span></span>  
 <span data-ttu-id="ae0f3-111">Gibt an, was bei Auftreten eines Fehlers geschehen soll: den Fehler ignorieren, die Zeile umleiten oder die Komponente mit einem Fehler abbrechen.</span><span class="sxs-lookup"><span data-stu-id="ae0f3-111">Specify what should happen when an error occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="ae0f3-112">**Verwandte Themen:** [Fehlerbehandlung in Daten](data-flow/error-handling-in-data.md)</span><span class="sxs-lookup"><span data-stu-id="ae0f3-112">**Related Topics:** [Error Handling in Data](data-flow/error-handling-in-data.md)</span></span>  
  
 <span data-ttu-id="ae0f3-113">**Abschneiden**</span><span class="sxs-lookup"><span data-stu-id="ae0f3-113">**Truncation**</span></span>  
 <span data-ttu-id="ae0f3-114">Gibt an, was im Falle einer Kürzung geschehen soll: den Fehler ignorieren, die Zeile umleiten oder die Komponente mit einem Fehler abbrechen.</span><span class="sxs-lookup"><span data-stu-id="ae0f3-114">Specify what should happen when a truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="ae0f3-115">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="ae0f3-115">**Description**</span></span>  
 <span data-ttu-id="ae0f3-116">Zeigt die Beschreibung des Fehlers an.</span><span class="sxs-lookup"><span data-stu-id="ae0f3-116">View the description of the error.</span></span>  
  
 <span data-ttu-id="ae0f3-117">**Diesen Wert für ausgewählte Zellen festlegen**</span><span class="sxs-lookup"><span data-stu-id="ae0f3-117">**Set this value to selected cells**</span></span>  
 <span data-ttu-id="ae0f3-118">Gibt an, was im Falle eines Fehlers oder einer Kürzung mit den ausgewählten Zellen geschehen soll: den Fehler ignorieren, die Zeile umleiten oder die Komponente mit einem Fehler abbrechen.</span><span class="sxs-lookup"><span data-stu-id="ae0f3-118">Specify what should happen to all the selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="ae0f3-119">**Anwenden**</span><span class="sxs-lookup"><span data-stu-id="ae0f3-119">**Apply**</span></span>  
 <span data-ttu-id="ae0f3-120">Wendet die Fehlerbehandlungsoption auf die ausgewählten Zellen an.</span><span class="sxs-lookup"><span data-stu-id="ae0f3-120">Apply the error handling option to the selected cells.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae0f3-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ae0f3-121">See Also</span></span>  
 <span data-ttu-id="ae0f3-122">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="ae0f3-122">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="ae0f3-123">[Quellen-Editor für Flatfiles &#40;Seite Verbindungs-Manager&#41;](../../2014/integration-services/flat-file-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="ae0f3-123">[Flat File Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/flat-file-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="ae0f3-124">[Quellen-Editor für Flatfiles &#40;Seite "Spalten"&#41;](../../2014/integration-services/flat-file-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="ae0f3-124">[Flat File Source Editor &#40;Columns Page&#41;](../../2014/integration-services/flat-file-source-editor-columns-page.md) </span></span>  
 [<span data-ttu-id="ae0f3-125">Verbindungs-Manager für Flatfiles</span><span class="sxs-lookup"><span data-stu-id="ae0f3-125">Flat File Connection Manager</span></span>](connection-manager/file-connection-manager.md)  
  
  
