---
title: Quellen-Editor für OLE DB (Seite Fehlerausgabe) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.oledbsourceadapter.errorhandling.f1
helpviewer_keywords:
- OLE DB Source Editor
ms.assetid: 7737c6ae-c16b-4856-aa6e-5882640093b7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ded87747f041a4d8451048d4ef4671b029125873
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621589"
---
# <a name="ole-db-source-editor-error-output-page"></a><span data-ttu-id="1f2dd-102">Quellen-Editor für OLE DB (Seite Fehlerausgabe)</span><span class="sxs-lookup"><span data-stu-id="1f2dd-102">OLE DB Source Editor (Error Output Page)</span></span>
  <span data-ttu-id="1f2dd-103">Mithilfe der Seite **Fehlerausgabe** des Dialogfelds **Quellen-Editor für OLE DB** können Sie Fehlerbehandlungsoptionen auswählen und Eigenschaften für Fehlerausgabespalten festlegen.</span><span class="sxs-lookup"><span data-stu-id="1f2dd-103">Use the **Error Output** page of the **OLE DB Source Editor** dialog box to select error handling options and to set properties on error output columns.</span></span>  
  
 <span data-ttu-id="1f2dd-104">Weitere Informationen zur OLE DB-Quelle finden Sie unter [OLE DB Source](data-flow/ole-db-source.md).</span><span class="sxs-lookup"><span data-stu-id="1f2dd-104">To learn more about the OLE DB source, see [OLE DB Source](data-flow/ole-db-source.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="1f2dd-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="1f2dd-105">Options</span></span>  
 <span data-ttu-id="1f2dd-106">**Eingabe/Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="1f2dd-106">**Input/Output**</span></span>  
 <span data-ttu-id="1f2dd-107">Zeigt den Namen der Datenquelle an.</span><span class="sxs-lookup"><span data-stu-id="1f2dd-107">View the name of the data source.</span></span>  
  
 <span data-ttu-id="1f2dd-108">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="1f2dd-108">**Column**</span></span>  
 <span data-ttu-id="1f2dd-109">Zeigt die externen (Quell-)Spalten an, die im Dialogfeld **Quellen-Editor für OLE DB** auf der Seite **Verbindungs-Manager**ausgewählt wurden.</span><span class="sxs-lookup"><span data-stu-id="1f2dd-109">View the external (source) columns that you selected on the **Connection Manager** page of the **OLE DB Source Editor**dialog box.</span></span>  
  
 <span data-ttu-id="1f2dd-110">**Fehler**</span><span class="sxs-lookup"><span data-stu-id="1f2dd-110">**Error**</span></span>  
 <span data-ttu-id="1f2dd-111">Gibt an, was bei Auftreten eines Fehlers geschehen soll: den Fehler ignorieren, die Zeile umleiten oder die Komponente mit einem Fehler abbrechen.</span><span class="sxs-lookup"><span data-stu-id="1f2dd-111">Specify what should happen when an error occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="1f2dd-112">**Verwandte Themen:** [Fehlerbehandlung in Daten](data-flow/error-handling-in-data.md)</span><span class="sxs-lookup"><span data-stu-id="1f2dd-112">**Related Topics:** [Error Handling in Data](data-flow/error-handling-in-data.md)</span></span>  
  
 <span data-ttu-id="1f2dd-113">**Abschneiden**</span><span class="sxs-lookup"><span data-stu-id="1f2dd-113">**Truncation**</span></span>  
 <span data-ttu-id="1f2dd-114">Gibt an, was im Falle einer Kürzung geschehen soll: den Fehler ignorieren, die Zeile umleiten oder die Komponente mit einem Fehler abbrechen.</span><span class="sxs-lookup"><span data-stu-id="1f2dd-114">Specify what should happen when a truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="1f2dd-115">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="1f2dd-115">**Description**</span></span>  
 <span data-ttu-id="1f2dd-116">Zeigt die Beschreibung des Fehlers an.</span><span class="sxs-lookup"><span data-stu-id="1f2dd-116">View the description of the error.</span></span>  
  
 <span data-ttu-id="1f2dd-117">**Diesen Wert für ausgewählte Zellen festlegen**</span><span class="sxs-lookup"><span data-stu-id="1f2dd-117">**Set this value to selected cells**</span></span>  
 <span data-ttu-id="1f2dd-118">Gibt an, was im Falle eines Fehlers oder einer Kürzung mit den ausgewählten Zellen geschehen soll: den Fehler ignorieren, die Zeile umleiten oder die Komponente mit einem Fehler abbrechen.</span><span class="sxs-lookup"><span data-stu-id="1f2dd-118">Specify what should happen to all the selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="1f2dd-119">**Anwenden**</span><span class="sxs-lookup"><span data-stu-id="1f2dd-119">**Apply**</span></span>  
 <span data-ttu-id="1f2dd-120">Wendet die Fehlerbehandlungsoption auf die ausgewählten Zellen an.</span><span class="sxs-lookup"><span data-stu-id="1f2dd-120">Apply the error handling option to the selected cells.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f2dd-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1f2dd-121">See Also</span></span>  
 <span data-ttu-id="1f2dd-122">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="1f2dd-122">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="1f2dd-123">[OLE DB Quellen-Editor &#40;Seite Verbindungs-Manager&#41;](../../2014/integration-services/ole-db-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="1f2dd-123">[OLE DB Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/ole-db-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="1f2dd-124">[OLE DB &#40;Seite "Spalten" des Quellen-Editors&#41;](../../2014/integration-services/ole-db-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="1f2dd-124">[OLE DB Source Editor &#40;Columns Page&#41;](../../2014/integration-services/ole-db-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="1f2dd-125">[Extrahieren von Daten mithilfe der OLE DB Quelle](data-flow/extract-data-by-using-the-ole-db-source.md) </span><span class="sxs-lookup"><span data-stu-id="1f2dd-125">[Extract Data by Using the OLE DB Source](data-flow/extract-data-by-using-the-ole-db-source.md) </span></span>  
 [<span data-ttu-id="1f2dd-126">OLE DB-Verbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="1f2dd-126">OLE DB Connection Manager</span></span>](connection-manager/ole-db-connection-manager.md)  
  
  
