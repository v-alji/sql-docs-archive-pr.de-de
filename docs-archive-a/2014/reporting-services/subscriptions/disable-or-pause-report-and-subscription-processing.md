---
title: Anhalten der Berichts-und Abonnement Verarbeitung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- pausing schedules
- subscriptions [Reporting Services], pausing
- report processing [Reporting Services], pausing
- shared data sources [Reporting Services]
- pausing subscription processing
- pausing report processing
- temporarily stopping report processing
- disabling shared data sources
- roles [Reporting Services], modifying
- shared schedules [Reporting Services], pausing
ms.assetid: 3cf9a240-24cc-46d4-bec6-976f82d8f830
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1607637630c507588602dd7e566917ce1eeb6080
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721052"
---
# <a name="pause-report-and-subscription-processing"></a><span data-ttu-id="2e4ed-102">Anhalten der Berichts- und Abonnementverarbeitung</span><span class="sxs-lookup"><span data-stu-id="2e4ed-102">Pause Report and Subscription Processing</span></span>
  <span data-ttu-id="2e4ed-103">Es ist nicht möglich, einen Bericht oder ein Abonnement direkt anzuhalten.</span><span class="sxs-lookup"><span data-stu-id="2e4ed-103">You cannot pause a report or subscription directly.</span></span> <span data-ttu-id="2e4ed-104">Sie können die Berichts- und Abonnementverarbeitung jedoch vor Beginn der Verarbeitung oder beim Herstellen der Verbindung zu einer Datenquelle unterbrechen.</span><span class="sxs-lookup"><span data-stu-id="2e4ed-104">However, you can interrupt report and subscription processing prior to the process starting or when a data source connection is made.</span></span> <span data-ttu-id="2e4ed-105">Wenn Sie den Benutzern den Zugriff auf einen Bericht oder ein Abonnement verwehren, können Sie ebenfalls dessen Ausführung verhindern.</span><span class="sxs-lookup"><span data-stu-id="2e4ed-105">You can also prevent a report or subscription from processing by making it inaccessible to users.</span></span>  
  
 <span data-ttu-id="2e4ed-106">Mithilfe der folgenden Strategien kann die Ausführung eines Prozesses vorübergehend verhindert werden.</span><span class="sxs-lookup"><span data-stu-id="2e4ed-106">The following strategies can be used to temporarily prevent a process from occurring.</span></span>  
  
## <a name="modify-role-assignments-to-prevent-access"></a><span data-ttu-id="2e4ed-107">Ändern der Rollenzuweisungen zum Verhindern des Zugriffs</span><span class="sxs-lookup"><span data-stu-id="2e4ed-107">Modify Role Assignments to Prevent Access</span></span>  
 <span data-ttu-id="2e4ed-108">Die beste Möglichkeit, um einen Bericht nicht zur Verfügung zu stellen, ist das vorübergehende Entfernen der Rollenzuweisung, die den Zugriff auf den Bericht bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="2e4ed-108">The best way to make a report unavailable is to temporarily remove the role assignment that provides access to the report.</span></span> <span data-ttu-id="2e4ed-109">Diese Vorgehensweise kann für alle Berichte unabhängig von der Art der Datenquellenverbindung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2e4ed-109">This approach can be used on all reports regardless of how the data source connection is made.</span></span> <span data-ttu-id="2e4ed-110">Dabei ist nur der Bericht betroffen. Die Ausführung anderer Berichte oder Elemente ist davon nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="2e4ed-110">This approach targets only the report, without affecting the operation of other reports or items.</span></span>  
  
 <span data-ttu-id="2e4ed-111">Öffnen Sie die Eigenschaftenseite Sicherheit des Berichts im Berichts-Manager, um die Rollenzuweisung zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="2e4ed-111">To remove the role assignment, open the Security Properties page of the report in Report Manager.</span></span> <span data-ttu-id="2e4ed-112">Falls der Bericht die Sicherheit von einem übergeordneten Bericht erbt, können Sie auf **Elementsicherheit bearbeiten** klicken, um eine restriktive Sicherheitsrichtlinie zu erstellen, die Rollenzuweisungen für den Zugriff auf breiter Basis ausklammert (entfernen Sie z.B. eine Rollenzuweisung, die jedem Benutzer den Zugriff ermöglicht, und behalten Sie die Rollenzuweisung, die einer kleinen Benutzergruppe den Zugriff ermöglicht, wie z.B. Administratoren).</span><span class="sxs-lookup"><span data-stu-id="2e4ed-112">If the report inherits security from a parent, you can click **Edit Item Security** to create a restrictive security policy that omits role assignments that provide widespread access (for example, you can remove a role assignment that provides access to Everyone, and keep the role assignment that provides access to a small group of users, such as Administrators).</span></span>  
  
## <a name="disable-a-shared-data-source"></a><span data-ttu-id="2e4ed-113">Deaktivieren einer freigegebenen Datenquelle</span><span class="sxs-lookup"><span data-stu-id="2e4ed-113">Disable a Shared Data Source</span></span>  
 <span data-ttu-id="2e4ed-114">Ein Vorteil des Verwendens freigegebener Datenquellen ist, dass Sie diese deaktivieren können, um die Ausführung eines Berichts oder eines datengesteuerten Abonnements zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="2e4ed-114">One advantage to using shared data sources is that you can disable it to prevent a report or data-driven subscription from running.</span></span> <span data-ttu-id="2e4ed-115">Durch das Deaktivieren einer freigegebenen Datenquelle wird die Verbindung des Berichts mit der externen Quelle getrennt.</span><span class="sxs-lookup"><span data-stu-id="2e4ed-115">Disabling a shared data source disconnects the report from its external source.</span></span> <span data-ttu-id="2e4ed-116">Die deaktivierte Datenquelle steht für keine Berichte und Abonnements zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="2e4ed-116">While it is disabled, the data source is unavailable to all reports and subscriptions that use it.</span></span> <span data-ttu-id="2e4ed-117">Zum Deaktivieren einer freigegebenen Datenquelle öffnen Sie in Berichts-Manager die Datenquelle, und deaktivieren Sie das Kontrollkästchen **diese Datenquelle aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="2e4ed-117">To disable a shared data source, open the data source in Report Manager and clear the **Enable this data source** check box.</span></span>  
  
 <span data-ttu-id="2e4ed-118">Beachten Sie, dass der Bericht weiterhin geladen wird, selbst wenn die Datenquelle nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="2e4ed-118">Note that the report still loads even if the data source is unavailable.</span></span> <span data-ttu-id="2e4ed-119">Der Bericht enthält keine Daten, aber Benutzer mit entsprechenden Berechtigungen haben Zugriff auf die Eigenschaftenseiten, Sicherheitseinstellungen, den Berichtsverlauf und die Abonnementinformationen für den Bericht.</span><span class="sxs-lookup"><span data-stu-id="2e4ed-119">The report does not contain data, but users with appropriate permissions can access the property pages, security settings, report history, and subscription information associated with the report.</span></span>  
  
## <a name="pause-a-shared-schedule"></a><span data-ttu-id="2e4ed-120">Anhalten eines freigegebenen Zeitplans</span><span class="sxs-lookup"><span data-stu-id="2e4ed-120">Pause a Shared Schedule</span></span>  
 <span data-ttu-id="2e4ed-121">Wenn ein Bericht oder ein Abonnement mit einem freigegebenen Zeitplan ausgeführt wird, können Sie den Zeitplan anhalten, um die Verarbeitung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="2e4ed-121">If a report or subscription runs from a shared schedule, you can pause the schedule to prevent processing.</span></span> <span data-ttu-id="2e4ed-122">Alle Berichts- und Abonnementverarbeitungen, die mit dem Zeitplan gesteuert werden, werden zurückgestellt, bis der Zeitplan fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="2e4ed-122">All report and subscription processing that is driven by the schedule is deferred until the schedule is resumed.</span></span> <span data-ttu-id="2e4ed-123">Weitere Informationen finden Sie unter Anhalten und Fortsetzen von frei [gegebenen Zeitplänen](schedules.md).</span><span class="sxs-lookup"><span data-stu-id="2e4ed-123">For more information, see [Pause and Resume Shared Schedules](schedules.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e4ed-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2e4ed-124">See Also</span></span>  
 <span data-ttu-id="2e4ed-125">[Reporting Services-Berichtsserver &#40;einheitlicher Modus&#41;](../report-server/reporting-services-report-server-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="2e4ed-125">[Reporting Services Report Server &#40;Native Mode&#41;](../report-server/reporting-services-report-server-native-mode.md) </span></span>  
 <span data-ttu-id="2e4ed-126">[Berichts-Manager &#40;einheitlicher SSRS-Modus&#41;](../report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="2e4ed-126">[Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md) </span></span>  
 [<span data-ttu-id="2e4ed-127">Sicherheit (Eigenschaftenseite), Elemente, (Berichts-Manager)</span><span class="sxs-lookup"><span data-stu-id="2e4ed-127">Security Properties Page, Items &#40;Report Manager&#41;</span></span>](../security-properties-page-items-report-manager.md)  
  
  
