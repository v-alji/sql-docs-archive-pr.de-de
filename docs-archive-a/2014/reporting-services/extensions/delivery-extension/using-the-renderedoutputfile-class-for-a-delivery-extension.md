---
title: Verwenden der RenderedOutputFile-Klasse für eine Übermittlungserweiterung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- RenderedOutputFile class
- data streams [Reporting Services]
- delivery extensions [Reporting Services], data streams
ms.assetid: 8b591801-42d5-49fa-b710-bf7e6917accf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1dcbf250a367326e5cad528384e533a9ac9d945b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630533"
---
# <a name="using-the-renderedoutputfile-class-for-a-delivery-extension"></a><span data-ttu-id="66679-102">Verwenden der RenderedOutputFile-Klasse für eine Übermittlungserweiterung</span><span class="sxs-lookup"><span data-stu-id="66679-102">Using the RenderedOutputFile Class for a Delivery Extension</span></span>
  <span data-ttu-id="66679-103">Die <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile>-Klasse stellt einen Datenstrom und Informationen zu den zugehörigen Eigenschaften des Datenstroms dar.</span><span class="sxs-lookup"><span data-stu-id="66679-103">The <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> class represents a data stream and information about the data stream's associated properties.</span></span> <span data-ttu-id="66679-104">Die **Daten**-Eigenschaft der <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile>-Klasse wird verwendet, um einen gerenderten Bericht oder eine Berichtsressource als **Stream**-Objekt darzustellen.</span><span class="sxs-lookup"><span data-stu-id="66679-104">The **Data** property of the <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> class is used to represent a rendered report or report resource as a **Stream** object.</span></span>  
  
 <span data-ttu-id="66679-105">Die <xref:Microsoft.ReportingServices.Interfaces.Report.Render%2A>-Methode des **Bericht**-Objekts gibt ein Array von einem oder mehreren <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile>-Objekten zurück, die zusammen einen einzelnen gerenderten Bericht ausmachen.</span><span class="sxs-lookup"><span data-stu-id="66679-105">The <xref:Microsoft.ReportingServices.Interfaces.Report.Render%2A> method of the **Report** object returns an array of one or more <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> objects that together constitute a single rendered report.</span></span> <span data-ttu-id="66679-106">Das erste <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile>-Objekt ist der gerenderte Bericht.</span><span class="sxs-lookup"><span data-stu-id="66679-106">The first <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> object is the rendered report.</span></span> <span data-ttu-id="66679-107">Alle anderen <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile>-Objekte sind Ressourcen, die zusammen mit den Berichtsdaten geliefert werden müssen (z. B. eine HTML-Datei und zugehörige Bilder).</span><span class="sxs-lookup"><span data-stu-id="66679-107">Any other <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> objects are resources that must be delivered along with the report data (for example, an HTML file and associated images).</span></span> <span data-ttu-id="66679-108">Renderingerweiterungen mit einem einzigen Datenstrom (IMAGE, PDF, MHTML und EXCEL) geben nur ein <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile>-Objekt im Array zurück.</span><span class="sxs-lookup"><span data-stu-id="66679-108">Rendering extensions that are single-stream rendering extensions (IMAGE, PDF, MHTML, and EXCEL) return only one <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> object in the array.</span></span>  
  
 <span data-ttu-id="66679-109">Ein Beispiel zur Verwendungsweise der <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile>-Klasse finden Sie unter [SQL Server Reporting Services-Produktbeispiele](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="66679-109">For an example of how to use the <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> class, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66679-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="66679-110">See Also</span></span>  
 <span data-ttu-id="66679-111">[Implementieren von Übermittlungserweiterungen](implementing-a-delivery-extension.md) </span><span class="sxs-lookup"><span data-stu-id="66679-111">[Implementing a Delivery Extension](implementing-a-delivery-extension.md) </span></span>  
 [<span data-ttu-id="66679-112">Reporting Services Extension Library (Reporting Services-Erweiterungsbibliothek)</span><span class="sxs-lookup"><span data-stu-id="66679-112">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
