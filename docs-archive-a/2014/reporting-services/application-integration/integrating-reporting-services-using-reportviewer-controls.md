---
title: Integrieren von Reporting Services mithilfe der ReportViewer-Steuerelemente | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- ReportViewer controls
- integrating reports [Reporting Services]
ms.assetid: 3ba47fb4-73a9-4059-89fd-329adebe94a8
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 18e28dbf1557bf36106b454738d0c0bfc037f2a7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608416"
---
# <a name="integrating-reporting-services-using-the-reportviewer-controls"></a><span data-ttu-id="e0178-102">Integrieren von Reporting Services mit den ReportViewer-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="e0178-102">Integrating Reporting Services Using the ReportViewer Controls</span></span>
  [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="e0178-103">[!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)]bietet zwei Report Viewer-Steuerelemente für die Integration der Berichts Anzeigefunktionen in Ihre Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="e0178-103">[!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] provides two ReportViewer controls for integrating report viewing functionality into your applications.</span></span> <span data-ttu-id="e0178-104">Es gibt eine Version für Windows Forms-Anwendungen und eine für WebForms-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="e0178-104">There is a version for Windows Forms-based applications and one for Web Forms applications.</span></span> <span data-ttu-id="e0178-105">Jedes Steuerelement verfügt über ähnliche Funktionen, wurde jedoch im Hinblick auf deren individuelle Umgebung konzipiert.</span><span class="sxs-lookup"><span data-stu-id="e0178-105">Each control provides similar functionality but each is designed to target their individual environments.</span></span> <span data-ttu-id="e0178-106">Beide Steuerelemente können Berichte verarbeiten, die auf einem Berichts Server bereitgestellt wurden (Remote Verarbeitungsmodus) oder auf einen Computer kopiert wurden, auf dem [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] nicht installiert ist (lokaler Verarbeitungsmodus).</span><span class="sxs-lookup"><span data-stu-id="e0178-106">Both controls can process reports that have been deployed to a report server (remote processing mode) or have been copied to a computer where [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] has not been installed (local processing mode).</span></span>  
  
 <span data-ttu-id="e0178-107">DAs ReportViewer-Steuerelement enthält keine integrierte Unterstützung für dynamische Anpassung an verschiedene Geräte mit unterschiedlichen Bildschirmauflösungen.</span><span class="sxs-lookup"><span data-stu-id="e0178-107">The ReportViewer control does not include built-in support for dynamically adapting to different devices with different screen resolutions.</span></span>  
  
## <a name="remote-processing-mode"></a><span data-ttu-id="e0178-108">Remoteverarbeitungsmodus</span><span class="sxs-lookup"><span data-stu-id="e0178-108">Remote Processing Mode</span></span>  
 <span data-ttu-id="e0178-109">Der Remoteverarbeitungsmodus ist die bevorzugte Methode für die Anzeige von Berichten, die auf einen Berichtsserver übertragen wurden.</span><span class="sxs-lookup"><span data-stu-id="e0178-109">Remote processing mode is the preferred method for viewing reports that have been deployed to a report server.</span></span> <span data-ttu-id="e0178-110">Der Remoteverarbeitungsmodus bietet folgende Vorteile:</span><span class="sxs-lookup"><span data-stu-id="e0178-110">Remote processing mode provides the following advantages:</span></span>  
  
-   <span data-ttu-id="e0178-111">Remoteverarbeitung ist eine optimierte Lösung für die Ausführung von Berichten, da der Bericht vom Berichtsserver verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="e0178-111">Remote processing provides an optimized solution for running reports because the report is processed by the report server.</span></span>  
  
-   <span data-ttu-id="e0178-112">Da die gesamte Verarbeitung vom Berichtsserver gehandhabt wird, kann eine Berichtsanforderung von verschiedenen Berichtsservern in einer Anwendung für horizontales Skalieren oder auf einem Server mit mehreren Prozessoren für zentrales Skalieren verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="e0178-112">Because all processing is handled by the report server, a report request can be processed by multiple report servers in a scale-out deployment or a server that has multiple processors in a scale-up scenario.</span></span>  
  
 <span data-ttu-id="e0178-113">Außerdem können im Remotemodus ausgeführte Berichte die kompletten Funktionen des Berichtsservers nutzen, einschließlich aller Rendering- und Datenerweiterungen.</span><span class="sxs-lookup"><span data-stu-id="e0178-113">In addition, reports run in remote mode can utilize the full functionality of the report server including all rendering and data extensions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e0178-114">Die Liste der Erweiterungen, die für das Steuerelement ReportViewer im Remoteverarbeitungsmodus zur Verfügung stehen, hängt davon ab, welche Ausgabe von [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] auf dem Berichtsserver installiert ist.</span><span class="sxs-lookup"><span data-stu-id="e0178-114">The list of extensions available to the ReportViewer control when it is running in remote processing mode depends on the edition of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] that is installed on the report server.</span></span>  
  
## <a name="local-processing-mode"></a><span data-ttu-id="e0178-115">Lokaler Verarbeitungsmodus</span><span class="sxs-lookup"><span data-stu-id="e0178-115">Local Processing Mode</span></span>  
 <span data-ttu-id="e0178-116">Der lokale Verarbeitungsmodus stellt eine alternative Methode zum Anzeigen und Rendern von Berichten dar, wenn [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] nicht installiert ist.</span><span class="sxs-lookup"><span data-stu-id="e0178-116">Local processing mode provides an alternative method for viewing and rendering reports when [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is not installed.</span></span> <span data-ttu-id="e0178-117">Anders als bei der Remoteverarbeitung steht dem Steuerelement nur ein Teil der Funktionen zur Verfügung, die der Berichtsserver eigentlich enthält.</span><span class="sxs-lookup"><span data-stu-id="e0178-117">Unlike remote processing only a subset of the functionality provided by the report server is available in the control.</span></span> <span data-ttu-id="e0178-118">Im lokalen Verarbeitungsmodus wird die Datenverarbeitung nicht vom Steuerelement gehandhabt, sondern sie wird von der Hostinganwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="e0178-118">In local processing mode, data processing is not handled by the control but rather implemented by the hosting application.</span></span> <span data-ttu-id="e0178-119">Die Berichtsverarbeitung wird jedoch vom Steuerelement selbst gehandhabt.</span><span class="sxs-lookup"><span data-stu-id="e0178-119">However report processing is handled by the control itself.</span></span> <span data-ttu-id="e0178-120">Im lokalen Verarbeitungsmodus stehen nur die PDF-, Excel-, Word- und Bild-Renderingerweiterungen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="e0178-120">In local processing mode, only the PDF, Excel, Word, and Image rendering extensions are available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0178-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e0178-121">See Also</span></span>  
 <span data-ttu-id="e0178-122">[Integrieren von Reporting Services in Anwendungen](../application-integration/integrating-reporting-services-into-applications.md) </span><span class="sxs-lookup"><span data-stu-id="e0178-122">[Integrating Reporting Services into Applications](../application-integration/integrating-reporting-services-into-applications.md) </span></span>  
 [<span data-ttu-id="e0178-123">Erstellen von SSRS-Berichten mithilfe von Visual Studio (Blog)</span><span class="sxs-lookup"><span data-stu-id="e0178-123">Create SSRS Reports Using Visual Studio (Blog)</span></span>](https://jwcooney.com/2015/01/07/ssrs-basics-set-up-visual-studio-to-write-a-new-ssrs-report/)  
  
  
