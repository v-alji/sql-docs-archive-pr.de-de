---
title: Eigenschaften von Reporting Services | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- report servers [Reporting Services], properties
- properties [Reporting Services], about properties
- reports [Reporting Services], properties
- Report Server Web service, properties
- report properties [Reporting Services]
- XML Web service [Reporting Services], properties
- Web service [Reporting Services], properties
- properties [Reporting Services]
ms.assetid: 8c855194-4c20-4ecc-a328-5137d54b560c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 61f1f50ea7a49acc616a36a4eaf1d3d5fcdf269a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697465"
---
# <a name="reporting-services-properties"></a><span data-ttu-id="770cd-102">Eigenschaften von Reporting Services</span><span class="sxs-lookup"><span data-stu-id="770cd-102">Reporting Services Properties</span></span>
  <span data-ttu-id="770cd-103">Der Berichtsserver definiert eine Reihe von Systemeigenschaften, die global für den Berichtsserver gelten, und eine Reihe von Elementeigenschaften, die zu einem in der Berichtsserver-Datenbank gespeicherten Einzelelement gehören.</span><span class="sxs-lookup"><span data-stu-id="770cd-103">The report server defines a set of system properties that are global to the report server and a set of item properties that are associated with an individual item stored in the report server database.</span></span> <span data-ttu-id="770cd-104">Vom Berichtsserver definierte Eigenschaften können nicht gelöscht werden, und in einigen Fällen sind sie schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="770cd-104">Properties defined by the report server cannot be deleted, and in some cases they are read-only.</span></span> <span data-ttu-id="770cd-105">In einer Anwendung können die System- und Elementeigenschaften erweitert werden, indem zusätzliche benutzerdefinierte Eigenschaften zu den System- und den Elementeigenschaften hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="770cd-105">An application can extend system properties and item properties by adding additional user-defined properties to the system and item properties.</span></span>  
  
 <span data-ttu-id="770cd-106">Die folgenden Webdienst Methoden rufen-Eigenschaften ab und legen Sie fest [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="770cd-106">The following Web service methods retrieve and set [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] properties.</span></span>  
  
|<span data-ttu-id="770cd-107">Methode</span><span class="sxs-lookup"><span data-stu-id="770cd-107">Method</span></span>|<span data-ttu-id="770cd-108">Aktion</span><span class="sxs-lookup"><span data-stu-id="770cd-108">Action</span></span>|  
|------------|------------|  
|<xref:ReportService2010.ReportingService2010.GetProperties%2A>|<span data-ttu-id="770cd-109">Gibt die Werte von einer oder mehreren Eigenschaften eines Elements in der Berichtsserver-Datenbank zurück.</span><span class="sxs-lookup"><span data-stu-id="770cd-109">Returns the values of one or more properties on an item in the report server database.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetSystemProperties%2A>|<span data-ttu-id="770cd-110">Gibt eine oder mehrere Systemeigenschaften zurück.</span><span class="sxs-lookup"><span data-stu-id="770cd-110">Returns one or more system properties.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetProperties%2A>|<span data-ttu-id="770cd-111">Legt eine oder mehrere Eigenschaften eines Elements in der Berichtsserver-Datenbank fest.</span><span class="sxs-lookup"><span data-stu-id="770cd-111">Sets one or more properties of an item in the report server database.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetSystemProperties%2A>|<span data-ttu-id="770cd-112">Legt eine oder mehrere Systemeigenschaften fest.</span><span class="sxs-lookup"><span data-stu-id="770cd-112">Sets one or more system properties.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="770cd-113">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="770cd-113">In This Section</span></span>  
  
|<span data-ttu-id="770cd-114">Thema</span><span class="sxs-lookup"><span data-stu-id="770cd-114">Topic</span></span>|<span data-ttu-id="770cd-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="770cd-115">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="770cd-116">Eigenschaften der Berichtsserverelemente</span><span class="sxs-lookup"><span data-stu-id="770cd-116">Report Server Item Properties</span></span>](reporting-services-properties-report-server-item-properties.md)|<span data-ttu-id="770cd-117">Beschreibt die elementspezifischen Eigenschaften in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="770cd-117">Describes the item-specific properties in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="770cd-118">Berichtsserver-Systemeigenschaften</span><span class="sxs-lookup"><span data-stu-id="770cd-118">Report Server System Properties</span></span>](reporting-services-properties-report-server-system-properties.md)|<span data-ttu-id="770cd-119">Beschreibt die systemspezifischen Eigenschaften in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="770cd-119">Describes the system-specific properties in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="770cd-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="770cd-120">See Also</span></span>  
 <span data-ttu-id="770cd-121">[Erstellen von Anwendungen mit dem Webdienst und .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="770cd-121">[Building Applications Using the Web Service and the .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="770cd-122">[Berichtsserver-Webdienst](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="770cd-122">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 [<span data-ttu-id="770cd-123">Technische Referenz (SSRS)</span><span class="sxs-lookup"><span data-stu-id="770cd-123">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
