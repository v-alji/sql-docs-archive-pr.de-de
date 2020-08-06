---
title: Zeitplaneigenschaften (Registerkarte Berichte) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.scheduleproperties.reports.f1
ms.assetid: 7db728bd-4b08-43ef-a49a-e8dcdd37cf89
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: da0b5255e73522572fa22da8668329a28f108104
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616362"
---
# <a name="schedule-properties-reports-page"></a><span data-ttu-id="c68ae-102">Zeitplaneigenschaften (Registerkarte Berichte)</span><span class="sxs-lookup"><span data-stu-id="c68ae-102">Schedule Properties (Reports Page)</span></span>
  <span data-ttu-id="c68ae-103">Verwenden Sie diese Seite, um eine Liste aller Berichte anzuzeigen, die diesen freigegebenen Zeitplan verwenden.</span><span class="sxs-lookup"><span data-stu-id="c68ae-103">Use this page to view a list of all reports that use this shared schedule.</span></span> <span data-ttu-id="c68ae-104">Zeitpläne können zum Aktualisieren von Berichtsmomentaufnahmen, zum Generieren des Berichtsverlaufs, zum Auslösen eines Abonnements oder zum Kennzeichnen einer zwischengespeicherten Kopie des Berichts als abgelaufen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c68ae-104">Schedules can be used to refresh report snapshots, generate report history, trigger a subscription, or expire a cached copy of the report.</span></span> <span data-ttu-id="c68ae-105">Wenn Sie herausfinden möchten, wie der Zeitplan verwendet wird, dann zeigen Sie die Eigenschaften- und Abonnementinformationen des Berichts an.</span><span class="sxs-lookup"><span data-stu-id="c68ae-105">To find out how the schedule is used, view the property and subscription information of the report.</span></span>  
  
 <span data-ttu-id="c68ae-106">Zwar wird auf dieser Seite jeder Bericht angezeigt, der den freigegebenen Zeitplan verwendet, jedoch wird nicht angegeben, wie oft der freigegebene Zeitplan von einem einzelnen Bericht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c68ae-106">Although this page shows each report that uses the shared schedule, it does not indicate how many times the shared schedule is used within that single report.</span></span> <span data-ttu-id="c68ae-107">Angenommen, 20 Abonnenten des Company Sales-Berichts verwenden alle den gleichen freigegebenen Zeitplan, um die Abonnementverarbeitung auszulösen.</span><span class="sxs-lookup"><span data-stu-id="c68ae-107">For example, suppose 20 different subscribers to the Company Sales report all use the same shared schedule to trigger subscription processing.</span></span> <span data-ttu-id="c68ae-108">In diesem Fall wird der Company Sales-Bericht nur einmal in dieser Liste angezeigt, obwohl der Bericht 20 Verweise auf den freigegebenen Zeitplan besitzt.</span><span class="sxs-lookup"><span data-stu-id="c68ae-108">In this case, the Company Sales report will only appear once in this list, even though the report has 20 references to the shared schedule.</span></span>  
  
 <span data-ttu-id="c68ae-109">Um diese Seite zu öffnen, starten Sie, stellen Sie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] eine Verbindung mit einem Berichts Server her, öffnen Sie den Ordner frei **gegebene Zeitpläne** , klicken Sie mit der rechten **Reports**Maustaste auf einen freigegebenen Zeitplan, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="c68ae-109">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server, open the **Shared Schedules** folder, right-click a shared schedule, select **Properties**, and then click **Reports**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c68ae-110">Diese Funktion ist nicht in jeder Edition von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c68ae-110">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c68ae-111">Eine Liste der Funktionen, die von den-Editionen unterstützt werden [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , finden Sie [unter von den-Editionen unterstützte Funktionen SQL Server 2012](https://go.microsoft.com/fwlink/?linkid=232473) () https://go.microsoft.com/fwlink/?linkid=232473) .</span><span class="sxs-lookup"><span data-stu-id="c68ae-111">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2012](https://go.microsoft.com/fwlink/?linkid=232473) (https://go.microsoft.com/fwlink/?linkid=232473).</span></span>  
  
## <a name="options"></a><span data-ttu-id="c68ae-112">Tastatur</span><span class="sxs-lookup"><span data-stu-id="c68ae-112">Options</span></span>  
 <span data-ttu-id="c68ae-113">**Ordner**</span><span class="sxs-lookup"><span data-stu-id="c68ae-113">**Folder**</span></span>  
 <span data-ttu-id="c68ae-114">Gibt den Pfad des Berichts an.</span><span class="sxs-lookup"><span data-stu-id="c68ae-114">Specifies the path of the report.</span></span>  
  
 <span data-ttu-id="c68ae-115">**Report**</span><span class="sxs-lookup"><span data-stu-id="c68ae-115">**Report**</span></span>  
 <span data-ttu-id="c68ae-116">Gibt den Namen des Berichts an, der den Zeitplan verwendet.</span><span class="sxs-lookup"><span data-stu-id="c68ae-116">Specifies the name of the report that uses the schedule.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c68ae-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c68ae-117">See Also</span></span>  
 <span data-ttu-id="c68ae-118">[Erstellen, Ändern oder Löschen von Zeitplänen](../subscriptions/create-modify-and-delete-schedules.md) </span><span class="sxs-lookup"><span data-stu-id="c68ae-118">[Create, Modify, and Delete Schedules](../subscriptions/create-modify-and-delete-schedules.md) </span></span>  
 <span data-ttu-id="c68ae-119">[Zeitpläne](../subscriptions/schedules.md) </span><span class="sxs-lookup"><span data-stu-id="c68ae-119">[Schedules](../subscriptions/schedules.md) </span></span>  
 <span data-ttu-id="c68ae-120">[Berichts Server in Management Studio F1-Hilfe](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="c68ae-120">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 <span data-ttu-id="c68ae-121">[Herstellen einer Verbindung mit einem Berichts Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="c68ae-121">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 [<span data-ttu-id="c68ae-122">Konfigurieren allgemeiner Eigenschaften für einen Bericht &#40;Berichts-Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="c68ae-122">Configure General Properties for a Report &#40;Report Manager&#41;</span></span>](../configure-general-properties-for-a-report-report-manager.md)  
  
  
