---
title: Rendering- und Ausführungsmethoden | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- rendered reports [Reporting Services]
- reports [Reporting Services], execution options
- methods [Reporting Services], execution options
- methods [Reporting Services], rendering
ms.assetid: 12626aad-f0be-4653-87d0-60eb3a3fff78
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d0bc793e9a18e993989563fd3526ff12272f775c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721076"
---
# <a name="rendering-and-execution-methods"></a><span data-ttu-id="1a7d5-102">Rendering-Methode und Execution-Methode</span><span class="sxs-lookup"><span data-stu-id="1a7d5-102">Rendering and Execution Methods</span></span>
  <span data-ttu-id="1a7d5-103">Mit diesen Methoden können Sie das Ausführen und Zwischenspeichern von Elementen und das Rendern von Berichten verwalten.</span><span class="sxs-lookup"><span data-stu-id="1a7d5-103">You can use these methods to manage item execution and caching, and report rendering.</span></span>  
  
|<span data-ttu-id="1a7d5-104">Methode</span><span class="sxs-lookup"><span data-stu-id="1a7d5-104">Method</span></span>|<span data-ttu-id="1a7d5-105">Aktion</span><span class="sxs-lookup"><span data-stu-id="1a7d5-105">Action</span></span>|  
|------------|------------|  
|<xref:ReportService2010.ReportingService2010.FlushCache%2A>|<span data-ttu-id="1a7d5-106">Erklärt den Cache für ein Element für ungültig.</span><span class="sxs-lookup"><span data-stu-id="1a7d5-106">Invalidates the cache for an item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetCacheOptions%2A>|<span data-ttu-id="1a7d5-107">Gibt die Cachekonfiguration für ein Element und die Einstellungen zurück, die beschreiben, wann die zwischengespeicherte Kopie des Elements nicht mehr gültig ist.</span><span class="sxs-lookup"><span data-stu-id="1a7d5-107">Returns the cache configuration for an item and the settings that describe when the cached copy of the item expires.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetExecutionOptions%2A>|<span data-ttu-id="1a7d5-108">Gibt die Ausführungsoption und die zugehörigen Einstellungen für ein einzelnes Element zurück.</span><span class="sxs-lookup"><span data-stu-id="1a7d5-108">Returns the execution option and associated settings for an individual item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListExecutionSettings%2A>|<span data-ttu-id="1a7d5-109">Gibt eine Liste unterstützter Ausführungseinstellungen zurück.</span><span class="sxs-lookup"><span data-stu-id="1a7d5-109">Returns a list of supported execution settings.</span></span>|  
|<xref:ReportExecution2005.ReportExecutionService.Render%2A>|<span data-ttu-id="1a7d5-110">Verarbeitet den angegebenen Bericht und rendert ihn im angegebenen Format.</span><span class="sxs-lookup"><span data-stu-id="1a7d5-110">Processes the specified report and renders it in a specified format.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetCacheOptions%2A>|<span data-ttu-id="1a7d5-111">Konfiguriert ein Element für die Zwischenspeicherung und gibt Einstellungen an, die festlegen, wann die zwischengespeicherte Kopie des Elements nicht mehr gültig ist.</span><span class="sxs-lookup"><span data-stu-id="1a7d5-111">Configures an item to be cached and provides settings that specify when the cached copy of the item expires.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetExecutionOptions%2A>|<span data-ttu-id="1a7d5-112">Legt Ausführungsoptionen und zugeordnete Ausführungseigenschaften für ein angegebenes Element fest.</span><span class="sxs-lookup"><span data-stu-id="1a7d5-112">Sets execution options and associated execution properties for a specified item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.UpdateItemExecutionSnapshot%2A>|<span data-ttu-id="1a7d5-113">Generiert für ein angegebenes Element eine Momentaufnahme der Elementausführung.</span><span class="sxs-lookup"><span data-stu-id="1a7d5-113">Generates an item execution snapshot for a specified item.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1a7d5-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1a7d5-114">See Also</span></span>  
 <span data-ttu-id="1a7d5-115">[Erstellen von Anwendungen mit dem Webdienst und .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="1a7d5-115">[Building Applications Using the Web Service and the .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="1a7d5-116">[Berichtsserver-Webdienst](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="1a7d5-116">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 <span data-ttu-id="1a7d5-117">[Webdienstmethoden für Berichtsserver](report-server-web-service-methods.md) </span><span class="sxs-lookup"><span data-stu-id="1a7d5-117">[Report Server Web Service Methods](report-server-web-service-methods.md) </span></span>  
 [<span data-ttu-id="1a7d5-118">Technische Referenz (SSRS)</span><span class="sxs-lookup"><span data-stu-id="1a7d5-118">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
