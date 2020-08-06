---
title: WMI-Anbieterbibliotheksreferenz für Reporting Services (SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- Reporting Services WMI Provider Library
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- WMI provider [Reporting Services], library
ms.assetid: 17ba711d-7eff-4423-9168-63dc425a3428
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2a98ca22f9d34627e484a698dcf540b31808d07e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616890"
---
# <a name="reporting-services-wmi-provider-library-reference-ssrs"></a><span data-ttu-id="4feb9-102">Reporting Services-WMI-Anbieterbibliotheksreferenz (SSRS)</span><span class="sxs-lookup"><span data-stu-id="4feb9-102">Reporting Services WMI Provider Library Reference (SSRS)</span></span>
  <span data-ttu-id="4feb9-103">Der Anbieter der [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Windows-Verwaltungsinstrumentation (Windows Management Instrumentation, WMI) unterstützt WMI-Vorgänge, die es Ihnen ermöglichen, Skripts und Code zum Ändern der Einstellungen des Berichtsservers und des Berichts-Managers zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4feb9-103">The [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Windows Management Instrumentation (WMI) provider supports WMI operations that enable you to write scripts and code to modify settings of the report server and Report Manager.</span></span>  
  
 <span data-ttu-id="4feb9-104">Wenn Sie zum Beispiel ändern möchten, ob die integrierte Sicherheit verwendet wird, wenn der Berichtsserver eine Verbindung zur Berichtsserver-Datenbank herstellt, erstellen Sie eine Instanz der MSReportServer_ConfigurationSetting-Klasse, und verwenden Sie die DatabaseIntegratedSecurity-Eigenschaft der Berichtsserverinstanz.</span><span class="sxs-lookup"><span data-stu-id="4feb9-104">For example, if you want to change whether integrated security is used when the report server connects to the report server database, create an instance of the MSReportServer_ConfigurationSetting class and use the DatabaseIntegratedSecurity property of the of the report server instance.</span></span> <span data-ttu-id="4feb9-105">Die in der folgenden Tabelle angezeigten Klassen stellen [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Komponenten dar.</span><span class="sxs-lookup"><span data-stu-id="4feb9-105">The classes shown in the following table represent [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] components.</span></span> <span data-ttu-id="4feb9-106">Die Klassen werden entweder im [!INCLUDE[ssRSWMInmspc](../../includes/ssrswminmspc-md.md)] -Namespace oder im [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)] -Namespace definiert.</span><span class="sxs-lookup"><span data-stu-id="4feb9-106">The classes are defined in either the [!INCLUDE[ssRSWMInmspc](../../includes/ssrswminmspc-md.md)] or the [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)] namespaces.</span></span> <span data-ttu-id="4feb9-107">Jede der Klassen unterstützt Lese- und Schreibvorgänge.</span><span class="sxs-lookup"><span data-stu-id="4feb9-107">Each of the classes support read and write operations.</span></span> <span data-ttu-id="4feb9-108">Erstellvorgänge werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4feb9-108">Create operations are not supported.</span></span>  
  
## <a name="classes"></a><span data-ttu-id="4feb9-109">Klassen</span><span class="sxs-lookup"><span data-stu-id="4feb9-109">Classes</span></span>  
 [<span data-ttu-id="4feb9-110">MSReportServer_Instance-Klasse</span><span class="sxs-lookup"><span data-stu-id="4feb9-110">MSReportServer_Instance Class</span></span>](msreportserver-instance-class.md)  
 <span data-ttu-id="4feb9-111">Stellt grundlegende Informationen bereit, die ein Client benötigt, um eine Verbindung mit einem installierten Berichtsserver herzustellen.</span><span class="sxs-lookup"><span data-stu-id="4feb9-111">Provides basic information required for a client to connect to an installed report server.</span></span>  
  
 [<span data-ttu-id="4feb9-112">MSReportServer_ConfigurationSetting Class (MSReportServer_ConfigurationSetting-Klasse)</span><span class="sxs-lookup"><span data-stu-id="4feb9-112">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
 <span data-ttu-id="4feb9-113">Stellt die Installationsparameter und die Laufzeitparameter einer Berichtsserverinstanz dar.</span><span class="sxs-lookup"><span data-stu-id="4feb9-113">Represents the installation and run-time parameters of a report server instance.</span></span> <span data-ttu-id="4feb9-114">Diese Parameter werden in der Konfigurationsdatei für den Berichtsserver gespeichert.</span><span class="sxs-lookup"><span data-stu-id="4feb9-114">These parameters are stored in the configuration file for the report server.</span></span>  
  
 <span data-ttu-id="4feb9-115">Weitere Informationen zu WMI-Vorgängen finden Sie in der WMI SDK-Dokumentation, die im SDK enthalten ist [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4feb9-115">For more information about WMI operations, see the WMI SDK documentation included with the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4feb9-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4feb9-116">See Also</span></span>  
 <span data-ttu-id="4feb9-117">[Zugreifen auf den Reporting Services WMI-Anbieter](../tools/access-the-reporting-services-wmi-provider.md) </span><span class="sxs-lookup"><span data-stu-id="4feb9-117">[Access the Reporting Services WMI Provider](../tools/access-the-reporting-services-wmi-provider.md) </span></span>  
 [<span data-ttu-id="4feb9-118">Technische Referenz (SSRS)</span><span class="sxs-lookup"><span data-stu-id="4feb9-118">Technical Reference &#40;SSRS&#41;</span></span>](../technical-reference-ssrs.md)  
  
  
