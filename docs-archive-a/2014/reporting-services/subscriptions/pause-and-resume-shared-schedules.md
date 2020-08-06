---
title: Anhalten und Fortsetzen von freigegebenen Zeitplänen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- pausing schedules
- report-specific schedules [Reporting Services]
- shared schedules [Reporting Services], resuming
- resuming schedules
- continuing schedules
- schedules [Reporting Services], resuming
- schedules [Reporting Services], pausing
ms.assetid: e416be75-5234-4aa6-a3de-77f60f25169a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f525a15b07b79b5c0d37f9a88ed9483b351af326
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618462"
---
# <a name="pause-and-resume-shared-schedules"></a><span data-ttu-id="747ac-102">Anhalten und Fortsetzen von freigegebenen Zeitplänen</span><span class="sxs-lookup"><span data-stu-id="747ac-102">Pause and Resume Shared Schedules</span></span>
  <span data-ttu-id="747ac-103">Es besteht die Möglichkeit, einen verwendeten freigegebenen Zeitplan anzuhalten und fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="747ac-103">You can pause and resume a shared schedule that is in use.</span></span> <span data-ttu-id="747ac-104">Durch das Anhalten eines freigegebenen Zeitplans kann ein Zeitplan vorübergehend eingefroren werden, mit dem die Berichtsverarbeitung und Abonnements ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="747ac-104">Pausing a shared schedule provides a way to temporarily freeze a schedule that is used to trigger report processing and subscriptions.</span></span> <span data-ttu-id="747ac-105">Nur freigegebene Zeitpläne können angehalten und fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="747ac-105">Only shared schedules can be paused and resumed.</span></span> <span data-ttu-id="747ac-106">Berichtsspezifische Zeitpläne können nicht angehalten werden.</span><span class="sxs-lookup"><span data-stu-id="747ac-106">You cannot pause report-specific schedules.</span></span>  
  
 <span data-ttu-id="747ac-107">Eine gerade ausgeführte Berichtsverarbeitung kann nicht angehalten und fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="747ac-107">You cannot pause and resume report processing that is in progress.</span></span> <span data-ttu-id="747ac-108">Es können nur die Zeitpläne angehalten und fortgesetzt werden, die sich in der Zeitplanwarteschlange des SQL Server-Agent-Dienstes befinden.</span><span class="sxs-lookup"><span data-stu-id="747ac-108">You can only pause and resume schedules that are in the scheduling queue of SQL Server Agent service.</span></span> <span data-ttu-id="747ac-109">Auf einen Auftrag, der verarbeitet wird, hat die Zeitplanungs-Engine keinen Einfluss.</span><span class="sxs-lookup"><span data-stu-id="747ac-109">A job that is in progress is outside the scope of the scheduling engine.</span></span> <span data-ttu-id="747ac-110">Weitere Informationen finden Sie unter [Verwalten eines ausgeführten Prozesses](manage-a-running-process.md).</span><span class="sxs-lookup"><span data-stu-id="747ac-110">For more information, see [Manage a Running Process](manage-a-running-process.md)</span></span>  
  
 <span data-ttu-id="747ac-111">Während ein freigegebener Zeitplan angehalten wird, werden alle Vorgänge, die stattgefunden hätten, versäumt.</span><span class="sxs-lookup"><span data-stu-id="747ac-111">While a shared schedule is paused, any operations that would have occurred are allowed to lapse.</span></span> <span data-ttu-id="747ac-112">Nachdem Sie einen freigegebenen Zeitplan fortsetzen, findet die Berichts- und Abonnementverarbeitung zum nächsten geplanten Zeitpunkt statt, wobei die Ortszeit des Servers verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="747ac-112">After you resume a shared schedule, report and subscription processing occurs at the next scheduled time, using the local time of the server.</span></span> <span data-ttu-id="747ac-113">Der Berichtsserver im einheitlichen Modus oder SharePoint-Dienstanwendungen holen keine geplanten Vorgänge nach, die stattgefunden hätten, wenn der Zeitplan nicht angehalten worden wäre.</span><span class="sxs-lookup"><span data-stu-id="747ac-113">The native mode report server or SharePoint service applications, do not make up scheduled operations that would have occurred had the schedule not been paused.</span></span>  
  
 <span data-ttu-id="747ac-114">In diesem Thema:</span><span class="sxs-lookup"><span data-stu-id="747ac-114">In this Topic:</span></span>  
  
-   [<span data-ttu-id="747ac-115">Anhalten und Fortsetzen von freigegebenen Zeitplänen (einheitlicher Modus)</span><span class="sxs-lookup"><span data-stu-id="747ac-115">Pause and Resume Shared Schedules (Native Mode)</span></span>](#bkmk_native)  
  
-   [<span data-ttu-id="747ac-116">Anhalten und Fortsetzen von freigegebenen Zeitplänen (SharePoint-Modus)</span><span class="sxs-lookup"><span data-stu-id="747ac-116">Pause and Resume Shared Schedules (SharePoint mode)</span></span>](#bkmk_sharepoint)  
  
##  <a name="pause-and-resume-shared-schedules-native-mode"></a><a name="bkmk_native"></a> <span data-ttu-id="747ac-117">Anhalten und Fortsetzen von freigegebenen Zeitplänen (einheitlicher Modus)</span><span class="sxs-lookup"><span data-stu-id="747ac-117">Pause and Resume Shared Schedules (Native Mode)</span></span>  
 <span data-ttu-id="747ac-118">Verwenden Sie die Seite "Zeitpläne" im Berichts-Manager zum Anhalten und Fortsetzen eines freigegebenen Zeitplans.</span><span class="sxs-lookup"><span data-stu-id="747ac-118">To pause and resume a shared schedule, use the Schedules page in Report Manager.</span></span> <span data-ttu-id="747ac-119">Sie können [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] nicht verwenden, da hier keine Optionen zum Anhalten und Fortsetzen von Zeitplänen zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="747ac-119">You cannot use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]; it does not provide options for pausing and resuming schedules.</span></span> <span data-ttu-id="747ac-120">Weitere Informationen finden Sie unter [Create, Modify, and Delete Schedules](create-modify-and-delete-schedules.md).</span><span class="sxs-lookup"><span data-stu-id="747ac-120">For more information, see [Create, Modify, and Delete Schedules](create-modify-and-delete-schedules.md).</span></span>  
  
#### <a name="to-pause-or-resume-a-shared-schedule"></a><span data-ttu-id="747ac-121">So halten Sie einen freigegebenen Zeitplan an oder setzen ihn fort</span><span class="sxs-lookup"><span data-stu-id="747ac-121">To pause or resume a shared schedule</span></span>  
  
1.  <span data-ttu-id="747ac-122">Klicken Sie im Berichts-Manager auf **Siteeinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="747ac-122">From Report Manager Click, **Site Settings**.</span></span>  
  
2.  <span data-ttu-id="747ac-123">Klicken Sie auf **Zeitpläne**.</span><span class="sxs-lookup"><span data-stu-id="747ac-123">Click **Schedules**.</span></span>  
  
3.  <span data-ttu-id="747ac-124">Wählen Sie den Zeitplan aus, und klicken Sie im Menüband auf **Anhalten** oder **Fortsetzen** .</span><span class="sxs-lookup"><span data-stu-id="747ac-124">Select the schedule, and click **Pause** or **Resume** in the ribbon.</span></span> <span data-ttu-id="747ac-125">Wenn ein Zeitplan derzeit angehalten wird, wird **Angehalten** in der Spalte **Status**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="747ac-125">If a Schedule is currently paused, the **Status** column will contain **Paused**.</span></span>  
  
##  <a name="pause-and-resume-shared-schedules-sharepoint-mode"></a><a name="bkmk_sharepoint"></a> <span data-ttu-id="747ac-126">Anhalten und Fortsetzen von freigegebenen Zeitplänen (SharePoint-Modus)</span><span class="sxs-lookup"><span data-stu-id="747ac-126">Pause and Resume Shared Schedules (SharePoint mode)</span></span>  
 <span data-ttu-id="747ac-127">Verwenden Sie die Seite "Siteeinstellungen" oder PowerShell, um einen freigegebenen Zeitplan anzuhalten und fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="747ac-127">To pause and resume a shared schedule, use the Site Settings page or PowerShell.</span></span> <span data-ttu-id="747ac-128">Zeitpläne werden pro SharePoint-Website verwaltet.</span><span class="sxs-lookup"><span data-stu-id="747ac-128">Schedules are managed per SharePoint site.</span></span>  
  
#### <a name="to-pause-or-resume-a-shared-schedule"></a><span data-ttu-id="747ac-129">So halten Sie einen freigegebenen Zeitplan an oder setzen ihn fort</span><span class="sxs-lookup"><span data-stu-id="747ac-129">To pause or resume a shared schedule</span></span>  
  
1.  <span data-ttu-id="747ac-130">Klicken Sie auf **Websiteaktionen**.</span><span class="sxs-lookup"><span data-stu-id="747ac-130">Click **Site Actions**.</span></span>  
  
2.  <span data-ttu-id="747ac-131">Klicken Sie auf **Siteeinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="747ac-131">Click **Site Settings**.</span></span>  
  
3.  <span data-ttu-id="747ac-132">Klicken Sie im Abschnitt **Reporting Services**auf Freigegebene Zeitpläne verwalten.</span><span class="sxs-lookup"><span data-stu-id="747ac-132">In the Reporting Services section, click **Manage Shared Schedules**.</span></span>  
  
4.  <span data-ttu-id="747ac-133">Wählen Sie den Zeitplan aus, und klicken Sie auf **Ausgewählte Zeitpläne anhalten** oder **Ausgewählte Zeitpläne ausführen**.</span><span class="sxs-lookup"><span data-stu-id="747ac-133">Select the schedule, and click **Pause Selected Schedules** or **Run Selected Schedules**.</span></span> <span data-ttu-id="747ac-134">Wenn ein Zeitplan derzeit angehalten wird, wird **Angehalten** in der Spalte **Status**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="747ac-134">If a Schedule is currently paused, the **Status** column will contain **Paused**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="747ac-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="747ac-135">See Also</span></span>  
 <span data-ttu-id="747ac-136">[Zeitpläne](schedules.md) </span><span class="sxs-lookup"><span data-stu-id="747ac-136">[Schedules](schedules.md) </span></span>  
 <span data-ttu-id="747ac-137">[Erstellen, Ändern oder Löschen von Zeitplänen](create-modify-and-delete-schedules.md) </span><span class="sxs-lookup"><span data-stu-id="747ac-137">[Create, Modify, and Delete Schedules](create-modify-and-delete-schedules.md) </span></span>  
 <span data-ttu-id="747ac-138">[Change Time Zones and Clock Settings on a Report Server (Ändern von Zeitzonen und Systemuhreinstellungen auf einem Berichtsserver)](change-time-zones-and-clock-settings-on-a-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="747ac-138">[Change Time Zones and Clock Settings on a Report Server](change-time-zones-and-clock-settings-on-a-report-server.md) </span></span>  
 [<span data-ttu-id="747ac-139">Verwalten eines ausgeführten Prozesses</span><span class="sxs-lookup"><span data-stu-id="747ac-139">Manage a Running Process</span></span>](manage-a-running-process.md)  
  
  
