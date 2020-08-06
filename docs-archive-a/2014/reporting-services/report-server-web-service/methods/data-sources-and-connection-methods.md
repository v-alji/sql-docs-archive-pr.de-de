---
title: Datenquellen- und Verbindungsmethoden | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- connections [Reporting Services], data sources
- reports [Reporting Services], data
- data sources [Reporting Services], methods
ms.assetid: 50999b52-fc7c-4333-9fb0-d04c37a4c90f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 29dd8dd1c002ab3b7d4594a4e25ec44bdb2cc8ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721097"
---
# <a name="data-sources-and-connection-methods"></a><span data-ttu-id="f4d9d-102">Datenquellen- und Verbindungsmethoden</span><span class="sxs-lookup"><span data-stu-id="f4d9d-102">Data Sources and Connection Methods</span></span>
  <span data-ttu-id="f4d9d-103">Mit diesen Methoden können Sie Datenquellenverbindungen und Anmeldeinformationen festlegen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="f4d9d-103">You can use these methods to set and manage data source connections and credentials.</span></span>  
  
|<span data-ttu-id="f4d9d-104">Methode</span><span class="sxs-lookup"><span data-stu-id="f4d9d-104">Method</span></span>|<span data-ttu-id="f4d9d-105">Aktion</span><span class="sxs-lookup"><span data-stu-id="f4d9d-105">Action</span></span>|  
|------------|------------|  
|<xref:ReportService2010.ReportingService2010.CreateDataSource%2A>|<span data-ttu-id="f4d9d-106">Erstellt eine neue Datenquelle in der Berichtsserver-Datenbank oder SharePoint-Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="f4d9d-106">Creates a new data source in the report server database or SharePoint library.</span></span>|  
|<xref:ReportService2010.ReportingService2010.DisableDataSource%2A>|<span data-ttu-id="f4d9d-107">Deaktiviert eine Datenquelle, die aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="f4d9d-107">Disables a data source that is enabled.</span></span>|  
|<xref:ReportService2010.ReportingService2010.EnableDataSource%2A>|<span data-ttu-id="f4d9d-108">Aktiviert eine Datenquelle, die deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="f4d9d-108">Enables a data source that is disabled.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetDataSourceContents%2A>|<span data-ttu-id="f4d9d-109">Gibt den Inhalt einer Datenquelle zurück.</span><span class="sxs-lookup"><span data-stu-id="f4d9d-109">Returns the contents of a data source.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetItemDataSourcePrompts%2A>|<span data-ttu-id="f4d9d-110">Ruft die Datenquellenaufforderungen für ein angegebenes Element ab.</span><span class="sxs-lookup"><span data-stu-id="f4d9d-110">Gets the data source prompts for a specified item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetItemDataSources%2A>|<span data-ttu-id="f4d9d-111">Gibt die Datenquellen für ein Element im Katalog zurück.</span><span class="sxs-lookup"><span data-stu-id="f4d9d-111">Returns the data sources for an item in the catalog.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListDependentItems%2A>|<span data-ttu-id="f4d9d-112">Gibt eine Liste von Katalogelementen zurück, die auf ein angegebenes Katalogelement verweisen.</span><span class="sxs-lookup"><span data-stu-id="f4d9d-112">Returns a list of catalog items that reference a specified catalog item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListSubscriptionsUsingDataSource%2A>|<span data-ttu-id="f4d9d-113">Gibt eine Liste von Abonnements zurück, die einer angegebenen Datenquelle zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="f4d9d-113">Returns a list of subscriptions that are associated with a given data source.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetDataSourceContents%2A>|<span data-ttu-id="f4d9d-114">Legt die Verbindungseigenschaften fest, die einer Datenquelle zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="f4d9d-114">Sets the connection properties that are associated with a data source.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetItemDataSources%2A>|<span data-ttu-id="f4d9d-115">Legt die Datenquellen für ein Element in einer Berichtsserver-Datenbank oder SharePoint-Bibliothek fest.</span><span class="sxs-lookup"><span data-stu-id="f4d9d-115">Sets the data sources for an item in a report server database or SharePoint library.</span></span>|  
|<xref:ReportService2010.ReportingService2010.TestConnectForDataSourceDefinition%2A>|<span data-ttu-id="f4d9d-116">Testet die Verbindung für eine Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="f4d9d-116">Tests the connection for a data source.</span></span> <span data-ttu-id="f4d9d-117">Diese Methode unterstützt direkte Datenquellentests.</span><span class="sxs-lookup"><span data-stu-id="f4d9d-117">This method supports the direct testing of the data source.</span></span>|  
|<xref:ReportService2010.ReportingService2010.TestConnectForItemDataSource%2A>|<span data-ttu-id="f4d9d-118">Testet die Verbindung für eine Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="f4d9d-118">Tests the connection for a data source.</span></span> <span data-ttu-id="f4d9d-119">Diese Methode unterstützt Tests von veröffentlichten Datenquellen, die von Berichten oder Modellen und freigegebenen Datenquellen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f4d9d-119">This method supports the testing of published data sources that are used by reports or models and shared data sources.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f4d9d-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f4d9d-120">See Also</span></span>  
 <span data-ttu-id="f4d9d-121">[Erstellen von Anwendungen mit dem Webdienst und .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="f4d9d-121">[Building Applications Using the Web Service and the .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="f4d9d-122">[Berichtsserver-Webdienst](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="f4d9d-122">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 <span data-ttu-id="f4d9d-123">[Webdienstmethoden für Berichtsserver](report-server-web-service-methods.md) </span><span class="sxs-lookup"><span data-stu-id="f4d9d-123">[Report Server Web Service Methods](report-server-web-service-methods.md) </span></span>  
 [<span data-ttu-id="f4d9d-124">Technische Referenz (SSRS)</span><span class="sxs-lookup"><span data-stu-id="f4d9d-124">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  