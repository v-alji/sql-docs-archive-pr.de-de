---
title: Meine Abonnements verwenden | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- subscriptions [Reporting Services], My Subscriptions page
- My Subscriptions page [Reporting Services]
ms.assetid: e96623ba-677e-4748-8787-f32bed3b5c12
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f3378a65637ad04151cc517fd9047363af954c31
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723293"
---
# <a name="use-my-subscriptions"></a><span data-ttu-id="0c4d1-102">Verwenden von "Meine Abonnements"</span><span class="sxs-lookup"><span data-stu-id="0c4d1-102">Use My Subscriptions</span></span>
  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]<span data-ttu-id="0c4d1-103">Berichts-Manager enthält die Seite **Meine Abonnements** , auf der alle Ihre Abonnements an einem Ort organisiert werden.</span><span class="sxs-lookup"><span data-stu-id="0c4d1-103">Report Manager includes a **My Subscriptions** page that organizes all of your subscriptions into one place.</span></span> <span data-ttu-id="0c4d1-104">Mithilfe von Meine Abonnements können Sie vorhandene Abonnements anzeigen, ändern und löschen.</span><span class="sxs-lookup"><span data-stu-id="0c4d1-104">You can use My Subscriptions to view, modify, and delete existing subscriptions.</span></span> <span data-ttu-id="0c4d1-105">Abonnements können damit jedoch nicht erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="0c4d1-105">However, you cannot use it to create subscriptions.</span></span>  
  
||  
|-|  
|<span data-ttu-id="0c4d1-106">**[!INCLUDE[applies](../../includes/applies-md.md)]** [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] im einheitlichen Modus</span><span class="sxs-lookup"><span data-stu-id="0c4d1-106">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Native mode</span></span>|  
  
 <span data-ttu-id="0c4d1-107">In Meine Abonnements können Sie Abonnements nach Ordner, Bericht, Beschreibung, Trigger, letzter Ausführung oder Status sortieren.</span><span class="sxs-lookup"><span data-stu-id="0c4d1-107">Within My Subscriptions, you can sort subscriptions by folder, report, description, trigger, last run, or status.</span></span> <span data-ttu-id="0c4d1-108">Alle Werte sind alphabetisch sortiert, außer bei Zuletzt ausgeführt, wo die Werte chronologisch sortiert sind.</span><span class="sxs-lookup"><span data-stu-id="0c4d1-108">All values are sorted alphabetically except for Last Run, which is in chronological order.</span></span>  
  
 <span data-ttu-id="0c4d1-109">Meine Abonnements zeigt nur die von Ihnen erstellten Abonnements.</span><span class="sxs-lookup"><span data-stu-id="0c4d1-109">My Subscriptions shows only the subscriptions that you create.</span></span> <span data-ttu-id="0c4d1-110">Abonnements anderer Benutzer werden nicht angezeigt, selbst wenn Sie als Abonnent zu diesen Abonnements hinzugefügt werden, und es werden auch keine datengesteuerten Abonnements angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0c4d1-110">It does not list subscriptions that are owned by other users, even if you are added as a subscriber to those subscriptions, nor does it show data-driven subscriptions.</span></span>  
  
 <span data-ttu-id="0c4d1-111">Sie können nicht basierend auf Besitzernamen, Triggerinformationen, Statusinformationen usw. nach Abonnements suchen.</span><span class="sxs-lookup"><span data-stu-id="0c4d1-111">You cannot search for subscriptions by name, nor can you search for subscriptions based on trigger information, status information, and so forth.</span></span> <span data-ttu-id="0c4d1-112">Weitere Informationen finden Sie unter [erstellen, ändern und Löschen von Standard Abonnements &#40;Reporting Services im einheitlichen Modus&#41;](create-and-manage-subscriptions-for-native-mode-report-servers.md).</span><span class="sxs-lookup"><span data-stu-id="0c4d1-112">For more information, see [Create, Modify, and Delete Standard Subscriptions &#40;Reporting Services in Native Mode&#41;](create-and-manage-subscriptions-for-native-mode-report-servers.md).</span></span>  
  
## <a name="how-to-use-my-subscriptions"></a><span data-ttu-id="0c4d1-113">Verwenden von Meine Abonnements</span><span class="sxs-lookup"><span data-stu-id="0c4d1-113">How to Use My Subscriptions</span></span>  
 <span data-ttu-id="0c4d1-114">Die Option Meine Abonnements ist im Berichts-Manager verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0c4d1-114">My Subscriptions is available through Report Manager.</span></span> <span data-ttu-id="0c4d1-115">Für den Zugriff auf **Meine Abonnements** klicken Sie auf die globale Symbolleiste des Berichts-Managers.</span><span class="sxs-lookup"><span data-stu-id="0c4d1-115">To access My Subscriptions, click **My Subscriptions** on the Report Manager global toolbar.</span></span>  
  
## <a name="use-windows-powershell-to-list-mysubscriptions"></a><span data-ttu-id="0c4d1-116">Verwenden von Windows PowerShell zum Auflisten von MySubscriptions</span><span class="sxs-lookup"><span data-stu-id="0c4d1-116">Use Windows PowerShell to list MySubscriptions</span></span>  
 <span data-ttu-id="0c4d1-117">![PowerShell-Inhalt](../media/rs-powershellicon.jpg "PowerShell-Inhalt")</span><span class="sxs-lookup"><span data-stu-id="0c4d1-117">![PowerShell related content](../media/rs-powershellicon.jpg "PowerShell related content")</span></span>  
  
 <span data-ttu-id="0c4d1-118">Mit dem folgenden PowerShell-Skript wird die Liste der Abonnements und Abonnementeigenschaften für den aktuellen Benutzer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0c4d1-118">The following PowerShell script will return the list of subscriptions and subscription properties for the current user.</span></span> <span data-ttu-id="0c4d1-119">Weitere Informationen finden Sie unter [ReportingService2010.ListMySubscriptions-Methode](https://technet.microsoft.com/library/reportservice2010.reportingservice2010.listmysubscriptions.aspx).</span><span class="sxs-lookup"><span data-stu-id="0c4d1-119">For more information, see [ReportingService2010.ListMySubscriptions Method](https://technet.microsoft.com/library/reportservice2010.reportingservice2010.listmysubscriptions.aspx).</span></span>  
  
```powershell
#server -  all subscriptions of the current user at the given server or site  
$server="[server name]/reportserver"  
$rs2010 = New-WebServiceProxy -Uri "http://$server/ReportService2010.asmx" -Namespace SSRS.ReportingService2010 -UseDefaultCredential ;  
  
$subscriptions=ListMySubscriptions(ItemPathOrSiteURL)  
$subscriptions | select Path, report, Description, Owner, SubscriptionID, lastexecuted,Status  
#uncomment the following to list all the subscription properties  
#$subscriptions
```  
  
## <a name="see-also"></a><span data-ttu-id="0c4d1-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0c4d1-120">See Also</span></span>  
 <span data-ttu-id="0c4d1-121">[Data-Driven Subscriptions](data-driven-subscriptions.md) </span><span class="sxs-lookup"><span data-stu-id="0c4d1-121">[Data-Driven Subscriptions](data-driven-subscriptions.md) </span></span>  
 <span data-ttu-id="0c4d1-122">[Abonnements und Übermittlung &#40;Reporting Services&#41;](subscriptions-and-delivery-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="0c4d1-122">[Subscriptions and Delivery &#40;Reporting Services&#41;](subscriptions-and-delivery-reporting-services.md) </span></span>  
 [<span data-ttu-id="0c4d1-123">Create and Manage Subscriptions for Native Mode Report Servers (Erstellen und Verwalten von Abonnements für Berichtsserver im einheitlichen Modus)</span><span class="sxs-lookup"><span data-stu-id="0c4d1-123">Create and Manage Subscriptions for Native Mode Report Servers</span></span>](../create-manage-subscriptions-native-mode-report-servers.md)  
