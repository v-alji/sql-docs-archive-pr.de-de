---
title: 'Während des Herstellens einer Verbindung mit der externen Datenquelle ist ein Fehler aufgetreten. Die folgenden Verbindungen wurden nicht aktualisiert: Power Pivot-Daten | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 1b951da1-f62d-43d2-b40b-270a4a9ab92c
author: minewiskan
ms.author: owend
ms.openlocfilehash: eb4329440b69d1bdfdbb96fbcc3926fa000d8877
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700322"
---
# <a name="an-error-occurred-during-an-attempt-to-establish-a-connection-to-the-external-data-source-the-following-connections-failed-to-refresh-powerpivot-data"></a><span data-ttu-id="7b65d-103">Während des Herstellens einer Verbindung mit der externen Datenquelle ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="7b65d-103">An error occurred during an attempt to establish a connection to the external data source.</span></span> <span data-ttu-id="7b65d-104">Die folgenden Verbindungen wurden nicht aktualisiert: PowerPivot-Daten</span><span class="sxs-lookup"><span data-stu-id="7b65d-104">The following connections failed to refresh: PowerPivot Data</span></span>
  <span data-ttu-id="7b65d-105">Dieser Fehler tritt auf, wenn Sie PowerPivot-Daten auf einem Server abfragen, auf dem PowerPivot für SharePoint nicht installiert ist.</span><span class="sxs-lookup"><span data-stu-id="7b65d-105">This error occurs if you query PowerPivot data on a server that does not have PowerPivot for SharePoint installed.</span></span> <span data-ttu-id="7b65d-106">Er tritt auch auf, wenn der SQL Server Analysis Services (PowerPivot)-Dienst beendet wird, oder wenn Sie versuchen, PowerPivot-Daten von einer früheren Version anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7b65d-106">It also occurs if the SQL Server Analysis Services (PowerPivot) service is stopped, or if you are attempting to view PowerPivot data from an earlier version.</span></span>  
  
## <a name="details"></a><span data-ttu-id="7b65d-107">Details</span><span class="sxs-lookup"><span data-stu-id="7b65d-107">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7b65d-108">Gilt für:</span><span class="sxs-lookup"><span data-stu-id="7b65d-108">Applies to</span></span>|<span data-ttu-id="7b65d-109">PowerPivot für SharePoint</span><span class="sxs-lookup"><span data-stu-id="7b65d-109">PowerPivot for SharePoint</span></span>|  
|<span data-ttu-id="7b65d-110">Produktversion</span><span class="sxs-lookup"><span data-stu-id="7b65d-110">Product Version</span></span>|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="7b65d-111">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b65d-111">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|<span data-ttu-id="7b65d-112">Ursache</span><span class="sxs-lookup"><span data-stu-id="7b65d-112">Cause</span></span>|<span data-ttu-id="7b65d-113">Fehler beim Herstellen der Datenverbindung.</span><span class="sxs-lookup"><span data-stu-id="7b65d-113">The data connection failed.</span></span>|  
|<span data-ttu-id="7b65d-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="7b65d-114">Message Text</span></span>|<span data-ttu-id="7b65d-115">Während des Herstellens einer Verbindung mit der externen Datenquelle ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="7b65d-115">An error occurred during an attempt to establish a connection to the external data source.</span></span> <span data-ttu-id="7b65d-116">Die folgenden Verbindungen wurden nicht aktualisiert: PowerPivot-Daten</span><span class="sxs-lookup"><span data-stu-id="7b65d-116">The following connections failed to refresh: PowerPivot Data</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7b65d-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="7b65d-117">Explanation</span></span>  
 <span data-ttu-id="7b65d-118">Dieser Fehler wird in Excel Services zurückgegeben, wenn der SQL Server Analysis Services (PowerPivot)-Dienst beendet wurde oder wenn Sie PowerPivot-Daten in einer Excel-Arbeitsmappe abfragen, die in SharePoint veröffentlicht ist, und die SharePoint-Umgebung über keinen PowerPivot für SharePoint-Server verfügt.</span><span class="sxs-lookup"><span data-stu-id="7b65d-118">Excel Services returns this error when you query PowerPivot data in an Excel workbook that is published to SharePoint, and the SharePoint environment does not have a PowerPivot for SharePoint server, or the SQL Server Analysis Services (PowerPivot) service is stopped.</span></span>  
  
 <span data-ttu-id="7b65d-119">Der Fehler tritt auf, wenn Sie PowerPivot-Daten nach Slices aufteilen oder filtern, während keine Abfrage-Engine verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="7b65d-119">The error occurs when you slice or filter PowerPivot data when the query engine is not available.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7b65d-120">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="7b65d-120">User Action</span></span>  
 <span data-ttu-id="7b65d-121">Installieren Sie PowerPivot für SharePoint, oder verschieben Sie die PowerPivot-Arbeitsmappe in eine SharePoint-Umgebung, in der PowerPivot für SharePoint installiert ist.</span><span class="sxs-lookup"><span data-stu-id="7b65d-121">Install PowerPivot for SharePoint or move the PowerPivot workbook to a SharePoint environment that has PowerPivot for SharePoint installed.</span></span> <span data-ttu-id="7b65d-122">Weitere Informationen finden Sie unter [PowerPivot for SharePoint 2010 Installation](../../sql-server/install/powerpivot-for-sharepoint-2010-installation.md).</span><span class="sxs-lookup"><span data-stu-id="7b65d-122">For more information, see [PowerPivot for SharePoint 2010 Installation](../../sql-server/install/powerpivot-for-sharepoint-2010-installation.md).</span></span>  
  
 <span data-ttu-id="7b65d-123">Wenn die Software installiert ist, überprüfen Sie, ob die SQL Server Analysis Services (PowerPivot)-Instanz ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7b65d-123">If the software is installed, verify that the SQL Server Analysis Services (PowerPivot) instance is running.</span></span> <span data-ttu-id="7b65d-124">Prüfen Sie **Dienste auf dem Server verwalten** in der Zentraladministration.</span><span class="sxs-lookup"><span data-stu-id="7b65d-124">Check **Manage services on server** in Central Administration.</span></span> <span data-ttu-id="7b65d-125">Prüfen Sie auch die Dienste-Konsolenanwendung in der Verwaltung.</span><span class="sxs-lookup"><span data-stu-id="7b65d-125">Also check the Services console application in Administrative Tools.</span></span>  
  
 <span data-ttu-id="7b65d-126">Für PowerPivot-Arbeitsmappen, die in einer SQL Server 2008 R2-Version von PowerPivot für Excel erstellt wurden, muss die SQL Server 2008 R2-Version vom OLE DB-Anbieter für Analysis Services installiert werden.</span><span class="sxs-lookup"><span data-stu-id="7b65d-126">For PowerPivot workbooks that were created in a SQL Server 2008 R2 version of PowerPivot for Excel, you must install the SQL Server 2008 R2 version of the Analysis Services OLE DB provider.</span></span> <span data-ttu-id="7b65d-127">Dieser Fehler tritt auf, wenn Sie den Anbieter installiert, die Datei Microsoft.AnalysisServices.ChannelTransport.dll jedoch nicht registriert haben.</span><span class="sxs-lookup"><span data-stu-id="7b65d-127">This error will occur if you installed the provider, but did not register the Microsoft.AnalysisServices.ChannelTransport.dll file.</span></span> <span data-ttu-id="7b65d-128">Weitere Informationen zur Dateiregistrierung finden Sie unter [Installieren des OLE DB-Anbieters für Analysis Services auf SharePoint-Servern](../../sql-server/install/install-the-analysis-services-ole-db-provider-on-sharepoint-servers.md).</span><span class="sxs-lookup"><span data-stu-id="7b65d-128">For more information about file registration, see [Install the Analysis Services OLE DB Provider on SharePoint Servers](../../sql-server/install/install-the-analysis-services-ole-db-provider-on-sharepoint-servers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b65d-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7b65d-129">See Also</span></span>  
 [<span data-ttu-id="7b65d-130">Die Datenverbindung verwendet die Windows-Authentifizierung, und Benutzer Anmelde Informationen konnten nicht delegiert werden. Die folgenden Verbindungen wurden nicht aktualisiert: Power Pivot-Daten</span><span class="sxs-lookup"><span data-stu-id="7b65d-130">The data connection uses Windows Authentication and user credentials could not be delegated. The following connections failed to refresh: PowerPivot Data</span></span>](the-data-connection-user-could-not-be-delegated.md)  
  
  