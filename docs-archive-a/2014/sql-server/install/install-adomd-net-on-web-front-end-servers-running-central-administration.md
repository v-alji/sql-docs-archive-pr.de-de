---
title: Installieren von ADOMD.net auf Web-Front-End-Servern, die die zentral Administration ausführen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: c2372180-e847-4cdb-b267-4befac3faf7e
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 0d9f52bf612c4878a8dacd4f5acfdcc135ae115e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609034"
---
# <a name="install-adomdnet-on-web-front-end-servers-running-central-administration"></a><span data-ttu-id="b7ca1-102">Installieren von ADOMD.NET auf Web-Front-End-Servern, auf denen die Zentraladministration ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="b7ca1-102">Install ADOMD.NET on Web Front-End Servers Running Central Administration</span></span>
  <span data-ttu-id="b7ca1-103">Wenn Sie PowerPivot für SharePoint in einer Farm installieren, die die Topologie "Zentraladministration ohne Excel Services oder PowerPivot für SharePoint" aufweist, laden Sie die Microsoft ADOMD.NET-Clientbibliothek herunter und installieren diese, wenn Sie Vollzugriff auf die integrierten Berichte im PowerPivot-Management-Dashboard erhalten möchten.</span><span class="sxs-lookup"><span data-stu-id="b7ca1-103">If you install PowerPivot for SharePoint into a farm that has the topology of Central Administration, without Excel Services or PowerPivot for SharePoint, download and install the Microsoft ADOMD.NET client library if you want full access to the built-in reports in the PowerPivot management dashboard.</span></span> <span data-ttu-id="b7ca1-104">Einige Berichte im Dashboard verwenden ADOMD.NET für den Zugriff auf interne Daten, die Berichtsdaten zur PowerPivot-Abfrageverarbeitung und zum Serverzustand in der Farm liefern.</span><span class="sxs-lookup"><span data-stu-id="b7ca1-104">Some reports in the dashboard use ADOMD.NET to access internal data that provides reporting data on PowerPivot query processing and server health in the farm.</span></span>  
  
 <span data-ttu-id="b7ca1-105">**[!INCLUDE[applies](../../includes/applies-md.md)]** SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="b7ca1-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  SharePoint 2010</span></span>  
  
 <span data-ttu-id="b7ca1-106">Bei SharePoint 2013 ist der Anbieter im SQL Server Feature Pack enthalten.</span><span class="sxs-lookup"><span data-stu-id="b7ca1-106">For SharePoint 2013, the provider is included in the SQL Server feature pack.</span></span> <span data-ttu-id="b7ca1-107">Informationen zum Herunterladen von spPowerPivot.msi finden Sie unter [Microsoft SQL Server 2014 Feature Pack](https://www.microsoft.com/download/details.aspx?id=35577) .</span><span class="sxs-lookup"><span data-stu-id="b7ca1-107">For information on how to download spPowerPivot.msi, see [Microsoft SQL Server 2014 Feature Pack](https://www.microsoft.com/download/details.aspx?id=35577)</span></span>  
  
### <a name="download-and-install-the-client-library"></a><span data-ttu-id="b7ca1-108">Herunterladen und Installieren der Clientbibliothek</span><span class="sxs-lookup"><span data-stu-id="b7ca1-108">Download and install the client library</span></span>  
  
1.  <span data-ttu-id="b7ca1-109">Suchen Sie auf der [Seite "SQL Server 2014 Feature Pack](https://go.microsoft.com/fwlink/?LinkID=296473)" nach Microsoft ADOMD.net.</span><span class="sxs-lookup"><span data-stu-id="b7ca1-109">On the [SQL Server 2014 Feature Pack page](https://go.microsoft.com/fwlink/?LinkID=296473), find Microsoft ADOMD.NET.</span></span>  
  
2.  <span data-ttu-id="b7ca1-110">Laden Sie das x64-Paket des `SQL_AS_ADOMD.msi`-Installationsprogramms herunter.</span><span class="sxs-lookup"><span data-stu-id="b7ca1-110">Download the x64 Package of the `SQL_AS_ADOMD.msi` installation program.</span></span>  
  
3.  <span data-ttu-id="b7ca1-111">Führen Sie die MSI-Datei aus, um die Bibliothek zu installieren.</span><span class="sxs-lookup"><span data-stu-id="b7ca1-111">Run the .msi to install the library.</span></span>  
  
4.  <span data-ttu-id="b7ca1-112">Setzen Sie IIS zurück, nachdem die Installation beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="b7ca1-112">Reset IIS after installation is finished.</span></span> <span data-ttu-id="b7ca1-113">Öffnen Sie eine Administrator Eingabeaufforderung, und geben Sie **iisreset**ein.</span><span class="sxs-lookup"><span data-stu-id="b7ca1-113">Open an administrative command prompt and type **IISRESET**.</span></span>  
  
### <a name="verify-installation"></a><span data-ttu-id="b7ca1-114">Überprüfen der Installation</span><span class="sxs-lookup"><span data-stu-id="b7ca1-114">Verify installation</span></span>  
  
1.  <span data-ttu-id="b7ca1-115">Wechseln Sie zu Windows\Assembly.</span><span class="sxs-lookup"><span data-stu-id="b7ca1-115">Go to Windows\Assembly.</span></span>  
  
2.  <span data-ttu-id="b7ca1-116">Klicken Sie mit der rechten Maustaste auf Microsoft. AnalysisServices. AdomdClient, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="b7ca1-116">Right-click Microsoft.AnalysisServices.AdomdClient and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="b7ca1-117">Klicken Sie auf **Version**.</span><span class="sxs-lookup"><span data-stu-id="b7ca1-117">Click **Version**.</span></span>  
  
4.  <span data-ttu-id="b7ca1-118">Vergewissern Sie sich, dass die Version 12,00 enthält.\<build number></span><span class="sxs-lookup"><span data-stu-id="b7ca1-118">Verify that the version includes 12.00.\<build number></span></span> <span data-ttu-id="b7ca1-119">und die Beschreibung lautet Microsoft. analysisservice. AdomdClient.</span><span class="sxs-lookup"><span data-stu-id="b7ca1-119">and that the description is Microsoft.AnalysisService.AdomdClient.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7ca1-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b7ca1-120">See Also</span></span>  
 [<span data-ttu-id="b7ca1-121">PowerPivot-Management-Dashboard und Verwendungsdaten</span><span class="sxs-lookup"><span data-stu-id="b7ca1-121">PowerPivot Management Dashboard and Usage Data</span></span>](https://docs.microsoft.com/analysis-services/power-pivot-sharepoint/power-pivot-management-dashboard-and-usage-data)  
  
  
