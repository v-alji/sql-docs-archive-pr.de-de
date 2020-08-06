---
title: Diese Arbeitsmappe enthält eine oder mehrere Abfragen, die externe Daten aktualisieren. | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: aa65c992-eb41-4032-9e11-a9ba871b6a3c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 25b2095e13d6151c68eb4a3507400dfdb1739564
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617310"
---
# <a name="this-workbook-contains-one-or-more-queries-that-refresh-external-data"></a><span data-ttu-id="7b15d-103">Diese Arbeitsmappe enthält eine oder mehrere Abfragen, die externe Daten aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="7b15d-103">This workbook contains one or more queries that refresh external data.</span></span>
  <span data-ttu-id="7b15d-104">Für Excel-Arbeitsmappen, die PowerPivot-Daten enthalten, zeigt Excel Services diese Warnung an, wenn Verbindungsinformationen erkannt werden, und fordert Sie auf, Abfragen für diese Arbeitsmappe zu aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="7b15d-104">For Excel workbooks that contain PowerPivot data, Excel Services shows this warning when it detects connection information and prompts you to enable or disable queries for this workbook.</span></span>  
  
## <a name="details"></a><span data-ttu-id="7b15d-105">Details</span><span class="sxs-lookup"><span data-stu-id="7b15d-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7b15d-106">Produktname</span><span class="sxs-lookup"><span data-stu-id="7b15d-106">Product Name</span></span>|<span data-ttu-id="7b15d-107">PowerPivot für SharePoint</span><span class="sxs-lookup"><span data-stu-id="7b15d-107">PowerPivot for SharePoint</span></span>|  
|<span data-ttu-id="7b15d-108">Produktversion</span><span class="sxs-lookup"><span data-stu-id="7b15d-108">Product Version</span></span>|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="7b15d-109">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b15d-109">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|<span data-ttu-id="7b15d-110">Ursache</span><span class="sxs-lookup"><span data-stu-id="7b15d-110">Cause</span></span>|<span data-ttu-id="7b15d-111">Excel Services ist so konfiguriert, dass bei Datenaktualisierungen Warnungen ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7b15d-111">Excel Services is configured to warn on data refresh.</span></span>|  
|<span data-ttu-id="7b15d-112">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="7b15d-112">Message Text</span></span>|<span data-ttu-id="7b15d-113">Diese Arbeitsmappe enthält eine oder mehrere Abfragen, die externe Daten aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="7b15d-113">This workbook contains one or more queries that refresh external data.</span></span> <span data-ttu-id="7b15d-114">Ein böswilliger Benutzer kann eine Abfrage entwerfen, um auf vertrauliche Informationen zuzugreifen und sie an andere Benutzer zu verteilen oder andere schädliche Aktionen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7b15d-114">A malicious user can design a query to access confidential information and distribute it to other users or perform other harmful actions.</span></span><br /><br /> <span data-ttu-id="7b15d-115">Wenn Sie der Quelle dieser Arbeitsmappe vertrauen, klicken Sie auf Ja, um Abfragen für externe Daten in dieser Arbeitsmappe zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="7b15d-115">If you trust the source of this workbook, click Yes to enable queries to external data in this workbook.</span></span> <span data-ttu-id="7b15d-116">Wenn Sie sich nicht sicher sind, klicken Sie auf Nein, damit Änderungen nicht für die Arbeitsmappe übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="7b15d-116">If you are not sure, click No so that changes are not applied to your workbook.</span></span><br /><br /> <span data-ttu-id="7b15d-117">Möchten Sie Abfragen für externe Daten in dieser Arbeitsmappe aktivieren?</span><span class="sxs-lookup"><span data-stu-id="7b15d-117">Do you want to enable queries to external data in this workbook?</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7b15d-118">Erklärung</span><span class="sxs-lookup"><span data-stu-id="7b15d-118">Explanation</span></span>  
 <span data-ttu-id="7b15d-119">PowerPivot-Arbeitsmappen enthalten eingebettete Datenverbindungszeichenfolgen, die von Excel verwendet werden, um mit einem externen PowerPivot-Server zu kommunizieren, der die Daten lädt und berechnet.</span><span class="sxs-lookup"><span data-stu-id="7b15d-119">PowerPivot workbooks contain embedded data connection strings that are used by Excel to communicate with an external PowerPivot server that loads and calculates the data.</span></span> <span data-ttu-id="7b15d-120">Wenn Warnungen bei Datenaktualisierungen aktiviert sind, erkennt Excel Services diese Verbindungszeichenfolge und warnt den Benutzer entsprechend.</span><span class="sxs-lookup"><span data-stu-id="7b15d-120">When warn on data refresh is enabled, Excel Services detects this connection string and warns the user accordingly.</span></span>  
  
 <span data-ttu-id="7b15d-121">Abfragen müssen aktiviert sein, um PowerPivot-Daten in der Arbeitsmappe zu filtern und sie in Slicer aufzuteilen.</span><span class="sxs-lookup"><span data-stu-id="7b15d-121">To filter and slice PowerPivot data in the workbook, queries must be enabled.</span></span> <span data-ttu-id="7b15d-122">Stellen Sie sicher, dass Sie Abfragen nur für jene PowerPivot-Arbeitsmappen aktivieren, denen Sie vertrauen.</span><span class="sxs-lookup"><span data-stu-id="7b15d-122">Be sure that you enable queries for only those PowerPivot workbooks that you trust.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7b15d-123">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="7b15d-123">User Action</span></span>  
 <span data-ttu-id="7b15d-124">Klicken Sie auf **Ja** , um Abfragen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="7b15d-124">Click **Yes** to enable queries.</span></span>  
  
 <span data-ttu-id="7b15d-125">Sie können auch die Konfigurationseinstellungen ändern, damit keine Warnungen bei Aktualisierungen mehr angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="7b15d-125">You can also change the configuration settings so that warn on refresh no longer occurs:</span></span>  
  
1.  <span data-ttu-id="7b15d-126">Klicken Sie in der Zentraladministration unter Anwendungsverwaltung auf **Dienstanwendungen verwalten**.</span><span class="sxs-lookup"><span data-stu-id="7b15d-126">In Central Administration, in Application Management, click **Manage service applications**.</span></span>  
  
2.  <span data-ttu-id="7b15d-127">Klicken Sie auf **Excel Services-Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="7b15d-127">Click **Excel Services Application**.</span></span>  
  
3.  <span data-ttu-id="7b15d-128">Klicken Sie auf **Vertrauenswürdiger Dateispeicherort**.</span><span class="sxs-lookup"><span data-stu-id="7b15d-128">Click **Trusted File Location**.</span></span>  
  
4.  <span data-ttu-id="7b15d-129">Klicken Sie auf **http://** oder den Speicherort, den Sie konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="7b15d-129">Click **http://** or the location you want to configure.</span></span>  
  
5.  <span data-ttu-id="7b15d-130">Deaktivieren Sie in „Externe Daten“ das Kontrollkästchen **Beim Aktualisieren warnen**.</span><span class="sxs-lookup"><span data-stu-id="7b15d-130">In External Data, clear the checkbox for **Warn on data refresh**.</span></span>  
  
6.  <span data-ttu-id="7b15d-131">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="7b15d-131">Click **OK**.</span></span>  
  
 <span data-ttu-id="7b15d-132">Alternativ können Sie einen neuen vertrauenswürdigen Speicherort für Websites erstellen, die PowerPivot-Arbeitsmappen enthalten, und dann die Konfigurationseinstellungen nur für diese Website ändern.</span><span class="sxs-lookup"><span data-stu-id="7b15d-132">Alternatively, you can create a new trusted location for sites that contain PowerPivot workbooks, and then modify the configuration settings for just that site.</span></span> <span data-ttu-id="7b15d-133">Weitere Informationen finden Sie unter [Create a trusted location for PowerPivot sites in Central Administration](create-a-trusted-location-for-power-pivot-sites-in-central-administration.md).</span><span class="sxs-lookup"><span data-stu-id="7b15d-133">For more information, see [Create a trusted location for PowerPivot sites in Central Administration](create-a-trusted-location-for-power-pivot-sites-in-central-administration.md).</span></span>  
  
  
