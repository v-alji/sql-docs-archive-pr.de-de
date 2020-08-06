---
title: Webserverinformationen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.webserverinformation.f1
ms.assetid: 86d72275-45c7-459f-98cf-f5a366ed279c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f7b461ed26b3e234f083add3312e256e164efc9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616471"
---
# <a name="web-server-information"></a><span data-ttu-id="f1969-102">Webserverinformationen</span><span class="sxs-lookup"><span data-stu-id="f1969-102">Web Server Information</span></span>
  <span data-ttu-id="f1969-103">Webserverinformationen sind erforderlich, um die Websynchronisierungsoption für die Mergereplikation zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f1969-103">Web server information is required to use the Web synchronization option for merge replication.</span></span> <span data-ttu-id="f1969-104">Informationen zur Konfiguration der Websynchronisierung finden Sie unter [Konfigurieren der Websynchronisierung](configure-web-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="f1969-104">For information about configuring Web synchronization, see [Configure Web Synchronization](configure-web-synchronization.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="f1969-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="f1969-105">Options</span></span>  
 <span data-ttu-id="f1969-106">**Webserveradresse**</span><span class="sxs-lookup"><span data-stu-id="f1969-106">**Web server address**</span></span>  
 <span data-ttu-id="f1969-107">Wenn Sie auf der Seite **FTP-Momentaufnahme und Internet** des Dialogfelds **Veröffentlichungseigenschaften** eine Webserveradresse angegeben haben, wird diese in diesem Feld als Standardwert angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f1969-107">If you specified a Web server address in the **FTP Snapshot andInternet** page of the **Publication Properties** dialog box, it appears in this text box as a default.</span></span> <span data-ttu-id="f1969-108">Übernehmen Sie entweder den Standardwert, oder geben Sie eine vollqualifizierte Webserveradresse für den Server für [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internetinformationsdienste (IIS, Internet Information Services) an, der diese Abonnements synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="f1969-108">Either accept the default or enter a fully qualified Web server address for the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Information Services (IIS) server that synchronizes this subscription.</span></span>  
  
 <span data-ttu-id="f1969-109">**Wie stellt der Abonnent eine Verbindung mit dem Webserver her?**</span><span class="sxs-lookup"><span data-stu-id="f1969-109">**How will each Subscriber connect to the Web server?**</span></span>  
 <span data-ttu-id="f1969-110">Geben Sie den für das Herstellen einer Verbindung mit dem Webserver verwendeten Authentifizierungstyp an.</span><span class="sxs-lookup"><span data-stu-id="f1969-110">Specify the type of authentication used to connect to the Web server.</span></span> <span data-ttu-id="f1969-111">Sie sollten für SSL-Verbindungen (Secure Sockets Layer) mit dem IIS-Server die Standardauthentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="f1969-111">It is recommended to use Basic Authentication for connections to the IIS server in conjunction with Secure Sockets Layer (SSL).</span></span> <span data-ttu-id="f1969-112">Geben Sie bei Auswahl der Standardauthentifizierung den Anmeldenamen und das Kennwort ein, die beim Herstellen der Verbindung vom Abonnenten zum IIS-Server verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f1969-112">If you select Basic Authentication, enter the login and password that will be used to connect from the Subscriber to the IIS server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1969-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f1969-113">See Also</span></span>  
 <span data-ttu-id="f1969-114">[Create a Pull Subscription](create-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="f1969-114">[Create a Pull Subscription](create-a-pull-subscription.md) </span></span>  
 <span data-ttu-id="f1969-115">[Anzeigen und Ändern der Eigenschaften von Pullabonnements](view-and-modify-pull-subscription-properties.md) </span><span class="sxs-lookup"><span data-stu-id="f1969-115">[View and Modify Pull Subscription Properties](view-and-modify-pull-subscription-properties.md) </span></span>  
 <span data-ttu-id="f1969-116">[Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md) </span><span class="sxs-lookup"><span data-stu-id="f1969-116">[Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md) </span></span>  
 <span data-ttu-id="f1969-117">[Abonnieren von Veröffentlichungen](subscribe-to-publications.md) </span><span class="sxs-lookup"><span data-stu-id="f1969-117">[Subscribe to Publications](subscribe-to-publications.md) </span></span>  
 [<span data-ttu-id="f1969-118">Websynchronisierung für die Mergereplikation</span><span class="sxs-lookup"><span data-stu-id="f1969-118">Web Synchronization for Merge Replication</span></span>](web-synchronization-for-merge-replication.md)  
  
  
