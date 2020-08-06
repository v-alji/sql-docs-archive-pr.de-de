---
title: Die Datei oder Assembly konnte nicht &#39;"Microsoft. AnalysisServices. SharePoint. Integration&#39;" geladen werden | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 6e350b67-5e18-4b90-8fb7-a0109cbb27b7
author: minewiskan
ms.author: owend
ms.openlocfilehash: b7ba75bdbd8e25f98d11d822c22fa7881352ad88
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620585"
---
# <a name="could-not-load-file-or-assembly-39microsoftanalysisservicessharepointintegration39"></a><span data-ttu-id="bb4b6-102">Datei-oder Assembly&#39;"Microsoft. AnalysisServices. SharePoint. Integration" konnte nicht geladen werden&#39;</span><span class="sxs-lookup"><span data-stu-id="bb4b6-102">Could not load file or assembly &#39;Microsoft.AnalysisServices.SharePoint.Integration&#39;</span></span>
  <span data-ttu-id="bb4b6-103">In SharePoint 2010-Umgebungen mit PowerPivot für SharePoint tritt dieser Fehler auf, wenn die Lösung auf Anwendungsebene für PowerPivot nicht ordnungsgemäß bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="bb4b6-103">In SharePoint 2010 environments that have PowerPivot for SharePoint, this error will occur if the application-level solution for PowerPivot did not deploy correctly.</span></span>  
  
## <a name="details"></a><span data-ttu-id="bb4b6-104">Details</span><span class="sxs-lookup"><span data-stu-id="bb4b6-104">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bb4b6-105">Gilt für:</span><span class="sxs-lookup"><span data-stu-id="bb4b6-105">Applies to</span></span>|<span data-ttu-id="bb4b6-106">PowerPivot für SharePoint</span><span class="sxs-lookup"><span data-stu-id="bb4b6-106">PowerPivot for SharePoint</span></span>|  
|<span data-ttu-id="bb4b6-107">Produktversion</span><span class="sxs-lookup"><span data-stu-id="bb4b6-107">Product Version</span></span>|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="bb4b6-108">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb4b6-108">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|<span data-ttu-id="bb4b6-109">Ursache</span><span class="sxs-lookup"><span data-stu-id="bb4b6-109">Cause</span></span>|<span data-ttu-id="bb4b6-110">Die Powerpivotwebapp-Lösung wurde nicht ordnungsgemäß oder überhaupt nicht bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="bb4b6-110">Powerpivotwebapp solution is not deployed or did not deploy correctly.</span></span>|  
|<span data-ttu-id="bb4b6-111">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="bb4b6-111">Message Text</span></span>|<span data-ttu-id="bb4b6-112">Datei oder Assembly "Microsoft.AnalysisServices.SharePoint.Integration" konnte nicht geladen werden</span><span class="sxs-lookup"><span data-stu-id="bb4b6-112">Could not load file or assembly 'Microsoft.AnalysisServices.SharePoint.Integration'</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bb4b6-113">Erklärung</span><span class="sxs-lookup"><span data-stu-id="bb4b6-113">Explanation</span></span>  
 <span data-ttu-id="bb4b6-114">PowerPivot für SharePoint stellt seine Funktionen mithilfe von Lösungspaketen auf einem SharePoint-Server bereit.</span><span class="sxs-lookup"><span data-stu-id="bb4b6-114">PowerPivot for SharePoint uses solution packages to deploy its features on a SharePoint server.</span></span> <span data-ttu-id="bb4b6-115">Eine der Lösungen wurde nicht ordnungsgemäß bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="bb4b6-115">One of the solutions is not deployed correctly.</span></span> <span data-ttu-id="bb4b6-116">Daher tritt dieser Fehler auf, wenn Sie versuchen, den PowerPivot-Katalog oder andere PowerPivot-Anwendungsseiten auf einer SharePoint-Website zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="bb4b6-116">As a result, this error appears whenever you try to open PowerPivot Gallery or other PowerPivot application pages on a SharePoint site.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bb4b6-117">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="bb4b6-117">User Action</span></span>  
 <span data-ttu-id="bb4b6-118">Stellen Sie das Lösungspaket bereit.</span><span class="sxs-lookup"><span data-stu-id="bb4b6-118">Deploy the solution package.</span></span>  
  
1.  <span data-ttu-id="bb4b6-119">Klicken Sie in der Zentraladministration unter Systemeinstellungen auf **Farmlösungen verwalten**.</span><span class="sxs-lookup"><span data-stu-id="bb4b6-119">In Central Administration, in System Settings, click **Manage farm solutions**.</span></span>  
  
2.  <span data-ttu-id="bb4b6-120">Klicken Sie auf **Powerpivotwebapp**.</span><span class="sxs-lookup"><span data-stu-id="bb4b6-120">Click **Powerpivotwebapp**.</span></span>  
  
3.  <span data-ttu-id="bb4b6-121">Klicken Sie auf **Lösung bereitstellen**.</span><span class="sxs-lookup"><span data-stu-id="bb4b6-121">Click **Deploy Solution**.</span></span>  
  
4.  <span data-ttu-id="bb4b6-122">Wählen Sie die Webanwendung aus, für die dieser Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="bb4b6-122">Choose the web application for which this error is occurring.</span></span> <span data-ttu-id="bb4b6-123">Bei mehr als einer Webanwendung stellen Sie die Lösung für alle Anwendungen erneut bereit.</span><span class="sxs-lookup"><span data-stu-id="bb4b6-123">If there is more than one web application, redeploy the solution for all of hem.</span></span>  
  
5.  <span data-ttu-id="bb4b6-124">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="bb4b6-124">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb4b6-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bb4b6-125">See Also</span></span>  
 [<span data-ttu-id="bb4b6-126">Bereitstellen von PowerPivot-Lösungen in SharePoint</span><span class="sxs-lookup"><span data-stu-id="bb4b6-126">Deploy PowerPivot Solutions to SharePoint</span></span>](deploy-power-pivot-solutions-to-sharepoint.md)  
  
  
