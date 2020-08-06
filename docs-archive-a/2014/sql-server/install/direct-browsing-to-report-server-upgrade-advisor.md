---
title: Direktes Navigieren zum Berichts Server (Upgrade Advisor) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 3d2814a4-318a-45ed-b093-1e852fab561f
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: ab4d146bba4bd87de56b30ad100b57f79eb68de3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622406"
---
# <a name="direct-browsing-to-report-server-upgrade-advisor"></a><span data-ttu-id="575c7-102">Direktes Navigieren zum Berichtsserver (Upgrade Advisor)</span><span class="sxs-lookup"><span data-stu-id="575c7-102">Direct Browsing to Report Server (Upgrade Advisor)</span></span>
  <span data-ttu-id="575c7-103">Der Upgrade Advisor hat festgestellt, dass Ihre aktuelle Installation von [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] direkt zum virtuellen Verzeichnis des Berichts Servers durchsucht.</span><span class="sxs-lookup"><span data-stu-id="575c7-103">Upgrade Advisor detected your current installation of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is browsing directly to the report server virtual directory.</span></span>  
  
||  
|-|  
|<span data-ttu-id="575c7-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Im SharePoint-Modus.</span><span class="sxs-lookup"><span data-stu-id="575c7-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="575c7-105">Komponente</span><span class="sxs-lookup"><span data-stu-id="575c7-105">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="575c7-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="575c7-106">Description</span></span>  
 <span data-ttu-id="575c7-107">Der Upgrade Advisor hat festgestellt, dass Ihre aktuelle Installation von [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] direkt zum virtuellen Verzeichnis des Berichts Servers, z. b. **http:// \<server name> /ReportServer**, navigiert.</span><span class="sxs-lookup"><span data-stu-id="575c7-107">Upgrade Advisor detected your current installation of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is browsing directly to the report server virtual directory, for example **http://\<server name>/ReportServer**.</span></span> <span data-ttu-id="575c7-108">Dies wird in aktuellen Versionen von [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="575c7-108">This is not supported in current versions of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="575c7-109">Diese Regel stellt eine Warnung dar. Das Upgrade wird nicht blockiert.</span><span class="sxs-lookup"><span data-stu-id="575c7-109">This rule is a warning and upgrade is not blocked.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="575c7-110">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="575c7-110">Corrective Action</span></span>  
 <span data-ttu-id="575c7-111">Navigieren Sie über die SharePoint-Benutzeroberfläche für Dokument Bibliotheken, oder verwenden Sie **http:// \<server name> /SharePoint Site>/_vti_bin/ReportServer**.</span><span class="sxs-lookup"><span data-stu-id="575c7-111">Browse using the SharePoint user interface for document libraries or use **http://\<server name>/sharepoint site>/_vti_bin/reportserver**.</span></span>  
  
  
