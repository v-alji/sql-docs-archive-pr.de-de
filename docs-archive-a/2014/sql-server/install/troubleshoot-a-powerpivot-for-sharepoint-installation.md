---
title: Problembehandlung bei einer PowerPivot für SharePoint Installation | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 97bc2ce7-af04-4372-ad79-c96b8c3417ab
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 3adc27132d976288c14ac702baae0b842e8aef0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617449"
---
# <a name="troubleshoot-a-powerpivot-for-sharepoint-installation"></a><span data-ttu-id="c23ed-102">Problembehandlung für eine PowerPivot für SharePoint-Installation</span><span class="sxs-lookup"><span data-stu-id="c23ed-102">Troubleshoot a PowerPivot for SharePoint Installation</span></span>
  <span data-ttu-id="c23ed-103">Wenn Sie anstelle der erwateten Seiten und Funktionen Fehler erhalten, gehen Sie wie folgt vor.</span><span class="sxs-lookup"><span data-stu-id="c23ed-103">If you get errors instead of the pages and features you expect, do the following.</span></span>  
  
-   <span data-ttu-id="c23ed-104">Lesen Sie die Versionsanmerkungen zu SharePoint sowie [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , um Problemumgehungen für bekannte Installationsprobleme zu finden.</span><span class="sxs-lookup"><span data-stu-id="c23ed-104">Review release notes for both SharePoint and [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] to get workarounds for known installation problems.</span></span> <span data-ttu-id="c23ed-105">Die Versionsanmerkungen werden mit den Installationsmedien sowie auf der Microsoft-Website bereitgestellt, von der Sie die Software heruntergeladen haben.</span><span class="sxs-lookup"><span data-stu-id="c23ed-105">Release notes are provided with the installation media or on the Microsoft site from which you downloaded the software.</span></span>  
  
    -   <span data-ttu-id="c23ed-106">[Anmerkungen zu dieser Version von SQL Server 2014](https://technet.microsoft.com/library/dn169381\(v=sql.15\).aspx).</span><span class="sxs-lookup"><span data-stu-id="c23ed-106">[SQL Server 2014 Release Notes](https://technet.microsoft.com/library/dn169381\(v=sql.15\).aspx).</span></span>  
  
-   <span data-ttu-id="c23ed-107">Weitere Informationen finden Sie im TechNet Wiki-Thema [Behandeln von Problemen mit PowerPivot-Installationen (und anderen Add-Ins)](https://social.technet.microsoft.com/wiki/contents/articles/13737.troubleshooting-installations-of-powerpivot-and-other-add-ins.aspx).</span><span class="sxs-lookup"><span data-stu-id="c23ed-107">See the Technet wiki topic, [Troubleshooting Installations of PowerPivot (and other add-ins)](https://social.technet.microsoft.com/wiki/contents/articles/13737.troubleshooting-installations-of-powerpivot-and-other-add-ins.aspx).</span></span>  
  
## <a name="issues"></a><span data-ttu-id="c23ed-108">Probleme</span><span class="sxs-lookup"><span data-stu-id="c23ed-108">Issues</span></span>  
  
### <a name="powerpivot-gallery-thumbnail-images-show-as-a-red-x"></a><span data-ttu-id="c23ed-109">Miniaturbilder werden im PowerPivot-Katalog als rotes X dargestellt</span><span class="sxs-lookup"><span data-stu-id="c23ed-109">PowerPivot Gallery Thumbnail images show as a red X</span></span>  
 <span data-ttu-id="c23ed-110">Eine Möglichkeit besteht darin, dass die **PowerPivot-Funktionsintegration für Websitesammlungen** nichtaktiv ist.</span><span class="sxs-lookup"><span data-stu-id="c23ed-110">One Possible cause is the **PowerPivot features Integration for Site Collections** is not active.</span></span> <span data-ttu-id="c23ed-111">Führen Sie folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="c23ed-111">Complete the following:</span></span>  
  
1.  <span data-ttu-id="c23ed-112">Klicken Sie in der Power Pivot-Katalog Bibliothek auf **Site Einstellungen** , entweder über das Zahnrad Symbol ![SharePoint-Einstellungen](https://docs.microsoft.com/analysis-services/analysis-services/media/as-sharepoint2013-settings-gear.gif "SharePoint-Einstellungen") oder die Liste **Home** .</span><span class="sxs-lookup"><span data-stu-id="c23ed-112">In the PowerPivot Gallery library, click **Site Settings** from either the gear icon ![SharePoint Settings](https://docs.microsoft.com/analysis-services/analysis-services/media/as-sharepoint2013-settings-gear.gif "SharePoint Settings") or the **Home** list.</span></span>  
  
2.  <span data-ttu-id="c23ed-113">Klicken Sie im Abschnitt **Websitesammlungsverwaltung** auf **Websitesammlungs-Features**.</span><span class="sxs-lookup"><span data-stu-id="c23ed-113">In the **Site Collection Administration** section, click **Site Collection Features**.</span></span>  
  
3.  <span data-ttu-id="c23ed-114">Klicken Sie auf **Websitesammlungs-Features**.</span><span class="sxs-lookup"><span data-stu-id="c23ed-114">Click **Site Collection Features**.</span></span>  
  
4.  <span data-ttu-id="c23ed-115">Stellen Sie sicher, dass die **PowerPivot-Funktionsintegration für Websitesammlungen** auf **Aktiv**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="c23ed-115">Verify **PowerPivot features Integration for Site Collections** is **Active**.</span></span>  
  
 <span data-ttu-id="c23ed-116">Weitere Informationen zu diesem Problem finden Sie unter [Power Pivot-Katalog zeigt rote X-Symbole für Symbole](https://support.microsoft.com/kb/2361559) ( https://support.microsoft.com/kb/2361559) .</span><span class="sxs-lookup"><span data-stu-id="c23ed-116">For additional causes of this issue, see [PowerPivot Gallery shows Red X's for Icons](https://support.microsoft.com/kb/2361559) (https://support.microsoft.com/kb/2361559).</span></span>  
  
  
