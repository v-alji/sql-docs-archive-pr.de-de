---
title: Microsoft SQL Server Reporting Services gemeinsamer gemeinsamer SharePoint-Dienst parallel (Upgrade Advisor) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 6ae1017e-129b-4702-9ea7-00ac9b024062
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: b8a26fedd892dfb26dea4616efd46d3b3748b508
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620117"
---
# <a name="microsoft-sql-server-reporting-services-sharepoint-shared-service-is-installed-side-by-side-upgrade-advisor"></a><span data-ttu-id="f3dcd-102">Gemeinsamer SharePoint-Dienst für Microsoft SQL Server Reporting Services wird parallel installiert (Upgrade Advisor)</span><span class="sxs-lookup"><span data-stu-id="f3dcd-102">Microsoft SQL Server Reporting Services SharePoint Shared Service is Installed Side by Side (Upgrade Advisor)</span></span>
  <span data-ttu-id="f3dcd-103">Der Upgrade Advisor hat festgestellt, dass der [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] gemeinsame SharePoint-Dienst parallel zu einer früheren Version von installiert ist [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f3dcd-103">Upgrade Advisor detected [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint Shared service is installed side by side with a previous version of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
||  
|-|  
|<span data-ttu-id="f3dcd-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Im SharePoint-Modus.</span><span class="sxs-lookup"><span data-stu-id="f3dcd-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="f3dcd-105">Komponente</span><span class="sxs-lookup"><span data-stu-id="f3dcd-105">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="f3dcd-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f3dcd-106">Description</span></span>  
 <span data-ttu-id="f3dcd-107">Der Upgrade Advisor hat erkannt [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , dass der gemeinsame SharePoint-Dienst parallel zu einer früheren Version von installiert ist [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , die nicht auf der Architektur des gemeinsamen SharePoint-Dienstanbieter basiert.</span><span class="sxs-lookup"><span data-stu-id="f3dcd-107">Upgrade Advisor detected [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint Shared service is installed side by side with a previous version of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] that is not based on the SharePoint shared service architecture.</span></span> <span data-ttu-id="f3dcd-108">Da sowohl die ältere als auch die neuere [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]-SharePoint-Technologie parallel auf dem Computer installiert sind, wird das Upgrade blockiert.</span><span class="sxs-lookup"><span data-stu-id="f3dcd-108">Because the computer has both older and newer [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint related technologies installed side by side, upgrade is blocked.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="f3dcd-109">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="f3dcd-109">Corrective Action</span></span>  
 <span data-ttu-id="f3dcd-110">Um das Upgrade fortzusetzen, muss eine der vorhandenen [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]-Installationen deinstalliert werden.</span><span class="sxs-lookup"><span data-stu-id="f3dcd-110">To continue with upgrade, you must uninstall one of the existing [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installations.</span></span> <span data-ttu-id="f3dcd-111">Nachdem Sie eine der [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]-Installationen entfernt haben, führen Sie den Upgrade Advisor erneut aus, um zu überprüfen, ob weitere Upgradeprobleme vorliegen.</span><span class="sxs-lookup"><span data-stu-id="f3dcd-111">After removing one of the installations of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], re-run Upgrade Advisor to confirm that there are no other upgrade issues.</span></span>  
  
  
