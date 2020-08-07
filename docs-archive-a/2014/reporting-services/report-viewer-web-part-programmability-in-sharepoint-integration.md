---
title: Berichts-Viewer-Webpart-Programmierbarkeit in SharePoint-Integration | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
ms.assetid: 714017b7-1bd6-4950-a3c6-d0df8450a877
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 494ebc3e6668e4d95480019e522caf46b83a6c4d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719525"
---
# <a name="report-viewer-web-part-programmability-in-sharepoint-integration"></a><span data-ttu-id="a22f4-102">Berichts-Viewer-Webpart-Programmierbarkeit in SharePoint-Integration</span><span class="sxs-lookup"><span data-stu-id="a22f4-102">Report Viewer Web Part Programmability in SharePoint Integration</span></span>
  <span data-ttu-id="a22f4-103">Der Berichts-Viewer-Webpart ist ein `T:Microsoft.ReportingServices.SharePoint.UI.WebParts.ReportViewerWebPart`-Serversteuerelement, das einen Satz von öffentlichen Anwendungsprogrammierschnittstellen (API) enthält, der Entwicklern ermöglicht, benutzerdefinierte SharePoint-Anwendungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a22f4-103">The Report Viewer Web Part is a `T:Microsoft.ReportingServices.SharePoint.UI.WebParts.ReportViewerWebPart` server control, which contains a set of public application programming interfaces (API) that enables developers to create custom SharePoint applications.</span></span> <span data-ttu-id="a22f4-104">Sie können benutzerdefinierte Webparts erstellen, die Berichtspfad und Parameter mit Webpartverbindungen zu Berichts-Viewer-Webparts angeben.</span><span class="sxs-lookup"><span data-stu-id="a22f4-104">You can create custom Web Parts that supply report path and parameters to Report Viewer Web Part using Web Part connections.</span></span> <span data-ttu-id="a22f4-105">Sie können auch das Webpart in eine benutzerdefinierte SharePoint-Webpartseite einbetten und es mit der öffentlichen API anpassen.</span><span class="sxs-lookup"><span data-stu-id="a22f4-105">You can also embed the Web Part in a custom SharePoint Web Part page and customize it using the public API.</span></span>  
  
## <a name="connecting-to-report-viewer-web-part-with-custom-web-parts"></a><span data-ttu-id="a22f4-106">Herstellen einer Verbindung mit Berichts-Viewer-Webpart mit benutzerdefinierten Webparts</span><span class="sxs-lookup"><span data-stu-id="a22f4-106">Connecting to Report Viewer Web Part with Custom Web Parts</span></span>  
 <span data-ttu-id="a22f4-107">Der Berichts-Viewer-Webpart ist ein Verbindungsconsumer zu SharePoint-Webparts, die <xref:System.Web.UI.WebControls.WebParts.IWebPartRow> oder `T:Microsoft.SharePoint.WebPartPages.IFilterValues` implementieren.</span><span class="sxs-lookup"><span data-stu-id="a22f4-107">The Report Viewer Web Part is a connection consumer to SharePoint Web Parts that implement <xref:System.Web.UI.WebControls.WebParts.IWebPartRow> or `T:Microsoft.SharePoint.WebPartPages.IFilterValues`.</span></span> <span data-ttu-id="a22f4-108">Ein <xref:System.Web.UI.WebControls.WebParts.IWebPartRow>-Webpart wie das **Dokumente**-Webpart kann einen Berichtspfad zu einem Berichts-Viewer-Webpart angeben, wenn es auf der gleichen Webpartseite wie das Berichts-Viewer-Webpart platziert wird.</span><span class="sxs-lookup"><span data-stu-id="a22f4-108">An <xref:System.Web.UI.WebControls.WebParts.IWebPartRow> Web Part, such as the **Documents** Web Part can supply a report path to a Report Viewer Web Part when placed on the same Web Part page as the Report Viewer Web Part.</span></span> <span data-ttu-id="a22f4-109">Ebenso kann ein `T:Microsoft.SharePoint.WebPartPages.IFilterValues` Webpart, wie z. b. der **Text Filter** oder der **Auswahl Filter**, einen Berichts Parameter für ein Berichts-Viewer-Webpart angeben, wenn es auf der gleichen Webpartseite wie das Berichts-Viewer-Webpart platziert wird.</span><span class="sxs-lookup"><span data-stu-id="a22f4-109">Likewise, an `T:Microsoft.SharePoint.WebPartPages.IFilterValues` Web Part, such as the **Text Filter** or the **Choice Filter**, can supply a report parameter to a Report Viewer Web Part when placed on the same Web Part page as the Report Viewer Web Part.</span></span>  
  
### <a name="implementing-a-report-path-provider-with-iwebpartrow"></a><span data-ttu-id="a22f4-110">Implementieren eines Berichtspfadanbieters mit IWebPartRow</span><span class="sxs-lookup"><span data-stu-id="a22f4-110">Implementing a Report Path Provider with IWebPartRow</span></span>  
 <span data-ttu-id="a22f4-111">Um durch Webpartverbindungen einen Berichtspfad zum Berichts-Viewer-Webpart anzugeben, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="a22f4-111">To supply a report path to the Report Viewer Web Part through Web Part connections, do the following:</span></span>  
  
1.  <span data-ttu-id="a22f4-112">Erstellen Sie einen Webpart, der die <xref:System.Web.UI.WebControls.WebParts.IWebPartRow>-Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="a22f4-112">Create a Web Part that implements the <xref:System.Web.UI.WebControls.WebParts.IWebPartRow> interface.</span></span>  
  
2.  <span data-ttu-id="a22f4-113">Fügen Sie den Webpart zur selben Webpartseite wie den Berichts-Viewer-Webpart hinzu.</span><span class="sxs-lookup"><span data-stu-id="a22f4-113">Add the Web Part to the same Web Part page as the Report Viewer Web Part.</span></span>  
  
3.  <span data-ttu-id="a22f4-114">Verbinden Sie den Webpart mit dem Berichts-Viewer-Webpart in der webbasierten Webpart-Entwurfsbenutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="a22f4-114">Connect your Web Part to the Report Viewer Web Part in the Web-based Web Part design user interface.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a22f4-115">Sie können nur jeweils ein <xref:System.Web.UI.WebControls.WebParts.IWebPartRow>-Webpart mit dem Berichts-Viewer-Webpart verbinden, und Sie können nicht ein <xref:System.Web.UI.WebControls.WebParts.IWebPartRow>-Webpart und ein `T:Microsoft.SharePoint.WebPartPages.IFilterValues`-Webpart mit dem Berichts-Viewer-Webpart verbinden.</span><span class="sxs-lookup"><span data-stu-id="a22f4-115">You can only connect one <xref:System.Web.UI.WebControls.WebParts.IWebPartRow> Web Part to the Report Viewer Web Part at a time, and you cannot connect both an <xref:System.Web.UI.WebControls.WebParts.IWebPartRow> Web Part and an `T:Microsoft.SharePoint.WebPartPages.IFilterValues` Web Part to the Report Viewer Web Part at the same time.</span></span>  
  
 <span data-ttu-id="a22f4-116">Damit der <xref:System.Web.UI.WebControls.WebParts.IWebPartRow>-Webpart ordnungsgemäß mit dem `T:Microsoft.ReportingServices.SharePoint.UI.WebParts.ReportViewerWebPart`-Webpart funktioniert, müssen Sie Folgendes in der <xref:System.Web.UI.WebControls.WebParts.IWebPartRow.GetRowData%2A>-Methode durchführen:</span><span class="sxs-lookup"><span data-stu-id="a22f4-116">For your <xref:System.Web.UI.WebControls.WebParts.IWebPartRow> Web Part to work properly with the `T:Microsoft.ReportingServices.SharePoint.UI.WebParts.ReportViewerWebPart`, you must do the following in the <xref:System.Web.UI.WebControls.WebParts.IWebPartRow.GetRowData%2A> method:</span></span>  
  
-   <span data-ttu-id="a22f4-117">Rufen Sie die Rückrufmethode mit einem <xref:System.Data.DataRowView>-Objekt als Eingabeparameter auf.</span><span class="sxs-lookup"><span data-stu-id="a22f4-117">Invoke the callback method with a <xref:System.Data.DataRowView> object as the input parameter.</span></span>  
  
-   <span data-ttu-id="a22f4-118">Stellen Sie sicher, dass das <xref:System.Data.DataRowView>-Objekt eine Spalte mit dem Namen "DocUrl" enthält, die den Berichtspfad enthält.</span><span class="sxs-lookup"><span data-stu-id="a22f4-118">Make sure that the <xref:System.Data.DataRowView> object contains a column called "DocUrl" that contains the report path.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a22f4-119">Das Berichts-Viewer-Webpart im Add-In für [!INCLUDE[offSPServ](../includes/offspserv-md.md)] 2010 unterstützt auch das Empfangen von Berichtspfaden, die die Spalte "FileRef" verwenden.</span><span class="sxs-lookup"><span data-stu-id="a22f4-119">The Report Viewer Web Part in the add-in for [!INCLUDE[offSPServ](../includes/offspserv-md.md)] 2010 also supports receiving the report path using the "FileRef" column.</span></span>  
  
### <a name="implementing-a-report-parameter-provider-with-ifiltervalues"></a><span data-ttu-id="a22f4-120">Implementieren eines Berichtsparameteranbieters mit IFilterValues</span><span class="sxs-lookup"><span data-stu-id="a22f4-120">Implementing a Report Parameter Provider with IFilterValues</span></span>  
 <span data-ttu-id="a22f4-121">Ein Webpart, der `T:Microsoft.SharePoint.WebPartPages.IFilterValues` implementiert, kann einen Parameterwert für den Berichts-Viewer-Webpart bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="a22f4-121">A Web Part that implements `T:Microsoft.SharePoint.WebPartPages.IFilterValues` can provide one parameter value to the Report Viewer Web Part.</span></span> <span data-ttu-id="a22f4-122">Der an den Berichts-Viewer-Webpart gesendete Parameterwert unterliegt gemäß der Angabe in der Berichtsdefinition denselben Einschränkungen wie der Berichtsparameter, zum Beispiel Datentyp, gültige Werte usw.</span><span class="sxs-lookup"><span data-stu-id="a22f4-122">The parameter value sent to the Report Viewer Web Part is subject to the same restrictions placed on the report parameter as specified in the report definition, such as data type, valid values, and so on</span></span>  
  
 <span data-ttu-id="a22f4-123">Um dem Berichts-Viewer-Webpart einen Berichtsparameter bereitzustellen, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="a22f4-123">To supply a report parameter to the Report Viewer Web Part, do the following:</span></span>  
  
1.  <span data-ttu-id="a22f4-124">Erstellen Sie einen Webpart, der die `T:Microsoft.SharePoint.WebPartPages.IFilterValues`-Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="a22f4-124">Create a Web Part that implements the `T:Microsoft.SharePoint.WebPartPages.IFilterValues` interface.</span></span>  
  
2.  <span data-ttu-id="a22f4-125">Fügen Sie den Webpart zur selben Seite wie den `T:Microsoft.ReportingServices.SharePoint.UI.WebParts.ReportViewerWebPart`-Webpart hinzu.</span><span class="sxs-lookup"><span data-stu-id="a22f4-125">Add the Web Part to the same page as the `T:Microsoft.ReportingServices.SharePoint.UI.WebParts.ReportViewerWebPart`.</span></span>  
  
3.  <span data-ttu-id="a22f4-126">Verbinden Sie den `T:Microsoft.SharePoint.WebPartPages.IFilterValues`-Webpart mit dem Berichts-Viewer-Webpart in der webbasierten Webpart-Entwurfsbenutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="a22f4-126">Connect your `T:Microsoft.SharePoint.WebPartPages.IFilterValues` Web Part to the Report Viewer Web Part in the Web-based Web Part design user interface.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a22f4-127">Sie können mehrere `T:Microsoft.SharePoint.WebPartPages.IFilterValues`-Webparts gleichzeitig mit dem Berichts-Viewer-Webpart verbinden.</span><span class="sxs-lookup"><span data-stu-id="a22f4-127">You can connect multiple `T:Microsoft.SharePoint.WebPartPages.IFilterValues` Web Parts to the Report Viewer Web Part at a time.</span></span> <span data-ttu-id="a22f4-128">Sie können jedoch nicht sowohl ein <xref:System.Web.UI.WebControls.WebParts.IWebPartRow>-Webpart als auch ein `T:Microsoft.SharePoint.WebPartPages.IFilterValues`-Webpart gleichzeitig mit dem Berichts-Viewer-Webpart verbinden.</span><span class="sxs-lookup"><span data-stu-id="a22f4-128">However, you cannot connect both an <xref:System.Web.UI.WebControls.WebParts.IWebPartRow> Web Part and an `T:Microsoft.SharePoint.WebPartPages.IFilterValues` Web Part to the Report Viewer Web Part at the same time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a22f4-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a22f4-129">See Also</span></span>  
 <span data-ttu-id="a22f4-130">[IFilterValues-Schnittstelle](https://msdn.microsoft.com/library/office/microsoft.sharepoint.webpartpages.ifiltervalues\(v=office.15\).aspx)</span><span class="sxs-lookup"><span data-stu-id="a22f4-130">[IFilterValues interface](https://msdn.microsoft.com/library/office/microsoft.sharepoint.webpartpages.ifiltervalues\(v=office.15\).aspx)</span></span>  
  
  
