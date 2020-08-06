---
title: Maximale Dateiuploadgröße konfigurieren (PowerPivot für SharePoint) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: ac516c63-1e79-4ae8-bca6-32d3c1a09c00
author: minewiskan
ms.author: owend
ms.openlocfilehash: 34a0adb2f22915289cccfa1f21c51038263acca0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694738"
---
# <a name="configure-maximum-file-upload-size-powerpivot-for-sharepoint"></a><span data-ttu-id="43434-102">Maximale Dateiuploadgröße konfigurieren (PowerPivot für SharePoint)</span><span class="sxs-lookup"><span data-stu-id="43434-102">Configure Maximum File Upload Size (PowerPivot for SharePoint)</span></span>
  <span data-ttu-id="43434-103">PowerPivot-Arbeitsmappen enthalten oft große Datenmengen, was dazu führt, dass Dateien die maximal für SharePoint-Uploads zulässige Dateigröße überschreiten.</span><span class="sxs-lookup"><span data-stu-id="43434-103">PowerPivot workbooks often contain large amounts of data that result in files that exceed the maximum file size allowed for SharePoint uploads.</span></span> <span data-ttu-id="43434-104">Wenn Sie versuchen, eine Datei hochzuladen, die die Obergrenze überschreitet, wird die folgende Fehlermeldung in SharePoint angezeigt:</span><span class="sxs-lookup"><span data-stu-id="43434-104">When you try to upload a file that exceeds the upper limit, you will get the following error on SharePoint:</span></span>  
  
-   <span data-ttu-id="43434-105">„Die angegebene Datei ist größer als die maximal unterstützte Dateigröße.“</span><span class="sxs-lookup"><span data-stu-id="43434-105">"The specified file is larger than the maximum supported file size."</span></span>  
  
 <span data-ttu-id="43434-106">Um die Dateigröße zu erhöhen, legen Sie zunächst die Maximale Arbeitsmappengröße für Excel Services auf 50 MB fest.</span><span class="sxs-lookup"><span data-stu-id="43434-106">To increase the file size, start by adjusting the Maximum Workbook Size for Excel Services to 50 megabytes.</span></span> <span data-ttu-id="43434-107">Dadurch werden die Grenzwerte für die maximale Dateigröße für Excel auf die der SharePoint-Webanwendungen festgelegt (standardmäßig 50 MB für SharePoint 2010 und 200 MB für SharePoint 2013).</span><span class="sxs-lookup"><span data-stu-id="43434-107">This aligns the maximum file size limits for Excel to those of SharePoint web applications (set to 50 megabytes by default in SharePoint 2010 and 200 in SharePoint 2013).</span></span> <span data-ttu-id="43434-108">Wenn Dateien 50 MB überschreiten, erhöhen Sie die Dateigrößenbeschränkungen sowohl für Excel Services als auch für die Webanwendung.</span><span class="sxs-lookup"><span data-stu-id="43434-108">If your files exceed 50 megabytes in size, increase the file size limits for both Excel Services and your web application.</span></span>  
  
 <span data-ttu-id="43434-109">Sie müssen SharePoint-Administrator sein, um die maximale Größe für Dateiuploads zu ändern.</span><span class="sxs-lookup"><span data-stu-id="43434-109">You must be a SharePoint administrator to change the maximum file upload size.</span></span>  
  
### <a name="configure-maximum-file-size-for-excel-services"></a><span data-ttu-id="43434-110">Konfigurieren der maximalen Dateigröße für Excel Services</span><span class="sxs-lookup"><span data-stu-id="43434-110">Configure maximum file size for Excel Services</span></span>  
  
1.  <span data-ttu-id="43434-111">Klicken Sie in der Zentraladministration unter Anwendungsverwaltung auf **Dienstanwendungen verwalten**.</span><span class="sxs-lookup"><span data-stu-id="43434-111">In Central Administration, in Application Management, click **Manage service applications**.</span></span>  
  
2.  <span data-ttu-id="43434-112">Klicken Sie auf den Namen der Excel Services-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="43434-112">Click the name of your Excel Services Application.</span></span>  
  
3.  <span data-ttu-id="43434-113">Klicken Sie auf **Vertrauenswürdige Dateispeicherorte**.</span><span class="sxs-lookup"><span data-stu-id="43434-113">Click **Trusted File Locations**.</span></span>  
  
4.  <span data-ttu-id="43434-114">Klicken Sie auf den Speicherort, um die Eigenschaften zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="43434-114">Click the location to edit the properties.</span></span> <span data-ttu-id="43434-115">Die Standardwebanwendung wird von Excel Services standardmäßig als vertrauenswürdige Website betrachtet.</span><span class="sxs-lookup"><span data-stu-id="43434-115">By default, Excel Services considers the default web application a trusted site.</span></span> <span data-ttu-id="43434-116">Wenn Sie die Standardwebanwendung verwenden, klicken Sie auf **http://** , um die Konfigurationsseite für diesen Speicherort zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="43434-116">If you are using the default web application, click **http://** to open the configuration page for this location.</span></span>  
  
5.  <span data-ttu-id="43434-117">Führen Sie einen Bildlauf zu **Arbeitsmappeneigenschaften**durch.</span><span class="sxs-lookup"><span data-stu-id="43434-117">Scroll to **Workbook Properties**.</span></span>  
  
6.  <span data-ttu-id="43434-118">Erhöhen Sie die Dateigröße in Maximale Arbeitsmappengröße von 10 (Standardwert) auf 50 oder einen höheren Wert, der für Ihre Arbeitsdateien geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="43434-118">In Maximum Workbook Size, increase the file size from 10 (the default value) to 50 or a larger size that accommodates the files you are working with.</span></span>  
  
     <span data-ttu-id="43434-119">Die maximale Dateiuploadgröße für SharePoint-Webanwendungen beträgt standardmäßig 50 MB.</span><span class="sxs-lookup"><span data-stu-id="43434-119">By default, 50 megabytes is the maximum file upload size for SharePoint web applications.</span></span> <span data-ttu-id="43434-120">Wenn Sie Maximale Arbeitsmappengröße auf einen Wert über 50 MB festlegen, führen Sie die Schritte im folgenden Verfahren aus, um Maximale Uploadgröße für die SharePoint-Webanwendung auf den gleichen Wert festzulegen.</span><span class="sxs-lookup"><span data-stu-id="43434-120">If you set Maximum Workbook Size to a number larger than 50 megabytes, follow the steps in the next procedure to increase the Maximum Upload Size for your SharePoint web application to the same value.</span></span>  
  
     <span data-ttu-id="43434-121">Der maximale Wert, den Sie angeben können, beträgt 2 Gigabytes (bzw. 2.047 Megabytes wie in der Zentraladministration angegeben).</span><span class="sxs-lookup"><span data-stu-id="43434-121">The maximum value that you can specify is 2 gigabytes (or 2047 megabytes as specified in Central Administration).</span></span>  
  
7.  <span data-ttu-id="43434-122">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="43434-122">Click **OK**.</span></span>  
  
### <a name="configure-maximum-file-size-for-a-sharepoint-web-application"></a><span data-ttu-id="43434-123">Konfigurieren der maximalen Dateigröße für eine SharePoint-Webanwendung</span><span class="sxs-lookup"><span data-stu-id="43434-123">Configure maximum file size for a SharePoint web application</span></span>  
  
1.  <span data-ttu-id="43434-124">Klicken Sie in der zentral Administration unter Anwendungs Verwaltung auf **Webanwendungen verwalten**.</span><span class="sxs-lookup"><span data-stu-id="43434-124">In Central Administration, in Application Management, click **Manage web applications**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="43434-125">Führen Sie die folgenden Schritte nur dann aus, wenn Sie die Maximale Arbeitsmappengröße in Excel Services hochgesetzt haben.</span><span class="sxs-lookup"><span data-stu-id="43434-125">Perform the following steps only if you increased the Maximum Workbook Size in Excel Services.</span></span>  
  
2.  <span data-ttu-id="43434-126">Wählen Sie die Anwendung (z.B. **SharePoint - 80**) aus.</span><span class="sxs-lookup"><span data-stu-id="43434-126">Select the application (for example, **SharePoint - 80**).</span></span>  
  
3.  <span data-ttu-id="43434-127">Klicken Sie im Menüband Webanwendungen auf der Schaltfläche Allgemeine Einstellungen auf den Pfeil nach unten.</span><span class="sxs-lookup"><span data-stu-id="43434-127">On the Web Applications ribbon, click the down arrow on the General Settings button.</span></span>  
  
4.  <span data-ttu-id="43434-128">Klicken Sie auf **Allgemeine Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="43434-128">Click **General Settings**.</span></span>  
  
5.  <span data-ttu-id="43434-129">Führen Sie einen Bildlauf zu **Maximale Uploadgröße**durch.</span><span class="sxs-lookup"><span data-stu-id="43434-129">Scroll to **Maximum Upload Size**.</span></span>  
  
6.  <span data-ttu-id="43434-130">Legen Sie die Eigenschaft auf den unter Maximale Arbeitsmappengröße in Excel Services angegebenen oder einen höheren Wert fest.</span><span class="sxs-lookup"><span data-stu-id="43434-130">Set the property to the same number, or larger as the Maximum Workbook Size in Excel Services.</span></span>  
  
7.  <span data-ttu-id="43434-131">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="43434-131">Click **OK**.</span></span>  
  
  
