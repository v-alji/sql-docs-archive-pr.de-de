---
title: Connect Filter or Documents Web Part (Reporting Services im integrierten SharePoint-Modus) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Filter Web Part [Reporting Services]
- SharePoint integration [Reporting Services], Web Parts
- Report Viewer Web Part [Reporting Services]
- Documents Web Part [Reporting Services]
ms.assetid: 6a303135-c0ef-44cd-a423-1cea8df3dcf3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5ea7b9f9aba128052ae6ac7f05ef40517eb50e6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615335"
---
# <a name="connect-filter-or-documents-web-part-reporting-services-in-sharepoint-integrated-mode"></a><span data-ttu-id="1a7d5-102">Verbinden eines Filters oder Dokumentwebparts (Reporting Services im integrierten SharePoint-Modus)</span><span class="sxs-lookup"><span data-stu-id="1a7d5-102">Connect Filter or Documents Web Part (Reporting Services in SharePoint Integrated Mode)</span></span>
  <span data-ttu-id="1a7d5-103">Wenn Sie ein SharePoint-Produkt verwenden, können Sie ein Dashboard oder eine Webpartseite erstellen, die ein Filterwebpart oder ein Dokumentewebpart und ein Berichts-Viewer-Webpart enthält.</span><span class="sxs-lookup"><span data-stu-id="1a7d5-103">If you are using a SharePoint product, you can create a dashboard or Web Part Page that includes a Filter Web Part or Documents Web part and a Report Viewer Web Part.</span></span> <span data-ttu-id="1a7d5-104">Unterstützte Versionen sind [!INCLUDE[SPF2010](../includes/spf2010-md.md)] oder [!INCLUDE[SPS2010](../includes/sps2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1a7d5-104">Supported versions are [!INCLUDE[SPF2010](../includes/spf2010-md.md)] or [!INCLUDE[SPS2010](../includes/sps2010-md.md)].</span></span> <span data-ttu-id="1a7d5-105">Ebenfalls unterstützt wird [!INCLUDE[winSPServ3](../includes/winspserv3-md.md)] oder [!INCLUDE[offSPServ](../includes/offspserv-md.md)] 2007.</span><span class="sxs-lookup"><span data-stu-id="1a7d5-105">Also supported are [!INCLUDE[winSPServ3](../includes/winspserv3-md.md)] or [!INCLUDE[offSPServ](../includes/offspserv-md.md)] 2007.</span></span> <span data-ttu-id="1a7d5-106">Durch Verbinden eines Filterwebparts können Benutzer, die Filterwerte in einem Filterwebpart auswählen, den Wert an einen parametrisierten Bericht auf derselben Seite senden.</span><span class="sxs-lookup"><span data-stu-id="1a7d5-106">By connecting a Filter Web Part, users who select filter values in a Filter Web Part can send the value to a parameterized report on the same page.</span></span> <span data-ttu-id="1a7d5-107">Durch Verbinden eines Dokumentewebparts können Benutzer, die auf Berichte in der Bibliothek Dokumente klicken, den Bericht in einem zugehörigen Berichts-Viewer-Webpart anzeigen.</span><span class="sxs-lookup"><span data-stu-id="1a7d5-107">By connecting a Documents Web Part, users who click on reports in the Documents library can view the report in an adjacent Report Viewer Web Part.</span></span>  
  
 <span data-ttu-id="1a7d5-108">Das Filterwebpart wird zum Senden von Werten an mindestens einen Parameter in einem Bericht verwendet.</span><span class="sxs-lookup"><span data-stu-id="1a7d5-108">The Filter Web Part is used to send values to one or more parameters on a report.</span></span> <span data-ttu-id="1a7d5-109">Wenn Sie ein Filterwebpart verwenden möchten, müssen für den Bericht Parameter definiert sein, die mit den vom Webpart gesendeten Werten, Datentypen und dem Format kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="1a7d5-109">To use a Filter Web Part, the report must have parameters defined for it that are compatible with the values, data type, and format sent by the Web Part.</span></span>  
  
 <span data-ttu-id="1a7d5-110">Das Dokumentewebpart ist der Bibliothek Dokumente der Website Home zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="1a7d5-110">The Documents Web Part is associated with the Documents library of the Home site.</span></span> <span data-ttu-id="1a7d5-111">Klicken Sie auf **Alle Websiteinhalte einblenden**, um Elemente aus der Bibliothek Dokumente anzuzeigen, hinzuzufügen oder zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="1a7d5-111">To view, add, or remove items from the Documents library, click **View All Site Content**.</span></span> <span data-ttu-id="1a7d5-112">Klicken Sie in Bibliotheken auf **Dokumente**.</span><span class="sxs-lookup"><span data-stu-id="1a7d5-112">In Libraries, click **Documents**.</span></span> <span data-ttu-id="1a7d5-113">Mit den Menüs **Neu**, **Upload**und **Aktionen** können Sie die Elemente in der Bibliothek Dokumente verwalten.</span><span class="sxs-lookup"><span data-stu-id="1a7d5-113">You can use the **New**, **Upload**, and **Actions** menu to manage the items in the Documents library.</span></span>  
  
### <a name="to-connect-a-filter-web-part"></a><span data-ttu-id="1a7d5-114">So verbinden Sie ein Filterwebpart</span><span class="sxs-lookup"><span data-stu-id="1a7d5-114">To connect a Filter Web Part</span></span>  
  
1.  <span data-ttu-id="1a7d5-115">Öffnen oder erstellen Sie eine Webpartseite oder ein Dashboard.</span><span class="sxs-lookup"><span data-stu-id="1a7d5-115">Open or create the Web Part page or dashboard.</span></span>  
  
2.  <span data-ttu-id="1a7d5-116">Klicken Sie im Menü **Websiteaktionen** auf **Seite bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="1a7d5-116">On the **Site Actions** menu, click **Edit Page**.</span></span>  
  
3.  <span data-ttu-id="1a7d5-117">Klicken Sie auf **Webpart hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="1a7d5-117">Click **Add a Web Part**.</span></span>  
  
4.  <span data-ttu-id="1a7d5-118">Wählen Sie in **allen Webparts**in der Kategorie **Verschiedenes** die Option **SQL Server Reporting Services Berichts-Viewer**aus.</span><span class="sxs-lookup"><span data-stu-id="1a7d5-118">In **All Web Parts**, in the **Miscellaneous** category, select **SQL Server Reporting Services Report Viewer**.</span></span>  
  
5.  <span data-ttu-id="1a7d5-119">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="1a7d5-119">Click **Add**.</span></span> <span data-ttu-id="1a7d5-120">Der Webpart wird oben in der Zone hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1a7d5-120">The Web Part is added at the top of the zone.</span></span>  
  
6.  <span data-ttu-id="1a7d5-121">Klicken Sie in einer anderen Zone auf derselben Webpartseite oder demselben Dashboard auf **Webpart hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="1a7d5-121">On another zone in the same Web Part page or dashboard, click **Add a Web Part**.</span></span>  
  
7.  <span data-ttu-id="1a7d5-122">Wählen Sie in **allen Webparts**im Abschnitt **Filter** ein Webpart aus.</span><span class="sxs-lookup"><span data-stu-id="1a7d5-122">In **All Web Parts**, in the **Filters** section, select a Web Part.</span></span>  
  
8.  <span data-ttu-id="1a7d5-123">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="1a7d5-123">Click **Add**.</span></span> <span data-ttu-id="1a7d5-124">Der Webpart wird oben in der Zone hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1a7d5-124">The Web Part is added at the top of the zone.</span></span>  
  
9. <span data-ttu-id="1a7d5-125">Klicken Sie in der Zone mit dem Webpart auf das Menü **bearbeiten** des Webparts, zeigen Sie auf **Verbindungen**, zeigen Sie auf **Filterwerte senden an**, und wählen Sie anschließend **Berichts-Viewer** - *Berichtsname*.</span><span class="sxs-lookup"><span data-stu-id="1a7d5-125">In the zone that contains the Web Part, click the Web Part **edit** menu, point to **Connections**, point to **Send Filter Values To**, and then select **Report Viewer** - *report name*.</span></span>  
  
10. <span data-ttu-id="1a7d5-126">Checken Sie Ihre Änderungen ein, und speichern Sie die Seite.</span><span class="sxs-lookup"><span data-stu-id="1a7d5-126">Check in your changes and save the page.</span></span>  
  
### <a name="to-connect-a-documents-web-part"></a><span data-ttu-id="1a7d5-127">So verbinden Sie ein Dokumentwebpart</span><span class="sxs-lookup"><span data-stu-id="1a7d5-127">To connect a Documents Web Part</span></span>  
  
1.  <span data-ttu-id="1a7d5-128">Öffnen oder erstellen Sie eine Webpartseite oder ein Dashboard.</span><span class="sxs-lookup"><span data-stu-id="1a7d5-128">Open or create the Web Part page or dashboard.</span></span>  
  
2.  <span data-ttu-id="1a7d5-129">Klicken Sie im Menü **Websiteaktionen** auf **Seite bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="1a7d5-129">On the **Site Actions** menu, click **Edit Page**.</span></span>  
  
3.  <span data-ttu-id="1a7d5-130">Klicken Sie auf **Webpart hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="1a7d5-130">Click **Add a Web Part**.</span></span>  
  
4.  <span data-ttu-id="1a7d5-131">Wählen Sie in **allen Webparts**im Abschnitt **Listen und Bibliotheken** die Option **Dokumente aus.**</span><span class="sxs-lookup"><span data-stu-id="1a7d5-131">In **All Web Parts**, in the **Lists and Library** section, select **Documents.**</span></span>  
  
5.  <span data-ttu-id="1a7d5-132">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="1a7d5-132">Click **Add**.</span></span> <span data-ttu-id="1a7d5-133">Der Webpart wird oben in der Zone hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1a7d5-133">The Web Part is added at the top of the zone.</span></span>  
  
6.  <span data-ttu-id="1a7d5-134">Klicken Sie unten im Toolbereich auf **Anwenden** , und klicken Sie anschließend auf **OK** , um den Bereich zu schließen.</span><span class="sxs-lookup"><span data-stu-id="1a7d5-134">Click **Apply** at the bottom of the tool pane, and then click **OK** to close the pane.</span></span>  
  
7.  <span data-ttu-id="1a7d5-135">Klicken Sie in einer anderen Zone auf derselben Webpartseite oder demselben Dashboard auf **Webpart hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="1a7d5-135">On another zone in the same Web Part page or dashboard, click **Add a Web Part**.</span></span>  
  
8.  <span data-ttu-id="1a7d5-136">Wählen Sie in **allen Webparts**in der Kategorie **Verschiedenes** die Option **SQL Server Reporting Services Berichts-Viewer aus.**</span><span class="sxs-lookup"><span data-stu-id="1a7d5-136">In **All Web Parts**, in the **Miscellaneous** category, select **SQL Server Reporting Services Report Viewer.**</span></span>  
  
9. <span data-ttu-id="1a7d5-137">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="1a7d5-137">Click **Add**.</span></span> <span data-ttu-id="1a7d5-138">Der Webpart wird oben in der Zone hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1a7d5-138">The Web Part is added at the top of the zone.</span></span>  
  
10. <span data-ttu-id="1a7d5-139">Klicken Sie in der Zone mit dem Webpart auf das Menü **Bearbeiten** des Webparts, zeigen Sie auf **Verbindungen**, zeigen Sie auf **Berichts Definitionen erhalten von**, und wählen Sie dann **Dokumente**aus.</span><span class="sxs-lookup"><span data-stu-id="1a7d5-139">In the zone that contains the Web Part, click the Web Part **edit** menu, point to **Connections**, point to **Get report definitions from**, and then select **Documents**.</span></span>  
  
11. <span data-ttu-id="1a7d5-140">Checken Sie Ihre Änderungen ein, und speichern Sie die Seite.</span><span class="sxs-lookup"><span data-stu-id="1a7d5-140">Check in your changes and save the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a7d5-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1a7d5-141">See Also</span></span>  
 <span data-ttu-id="1a7d5-142">[Fügen Sie das Berichts-Viewer-Webpart einer Webseite &#40;Reporting Services im integrierten SharePoint-Modus hinzu&#41;](report-server-sharepoint/add-reporting-services-content-types-to-a-sharepoint-library.md) </span><span class="sxs-lookup"><span data-stu-id="1a7d5-142">[Add the Report Viewer Web Part to a Web Page &#40;Reporting Services in SharePoint Integrated Mode&#41;](report-server-sharepoint/add-reporting-services-content-types-to-a-sharepoint-library.md) </span></span>  
 <span data-ttu-id="1a7d5-143">[Berichts-Viewer-Webpart auf einer SharePoint-Website](../../2014/reporting-services/report-viewer-web-part-on-a-sharepoint-site.md) </span><span class="sxs-lookup"><span data-stu-id="1a7d5-143">[Report Viewer Web Part on a SharePoint Site](../../2014/reporting-services/report-viewer-web-part-on-a-sharepoint-site.md) </span></span>  
 [<span data-ttu-id="1a7d5-144">Anpassen des Berichts-Viewer-Webparts</span><span class="sxs-lookup"><span data-stu-id="1a7d5-144">Customize the Report Viewer Web Part</span></span>](../../2014/reporting-services/customize-the-report-viewer-web-part.md)  
  
  
