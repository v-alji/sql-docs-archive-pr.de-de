---
title: Konfigurieren von E-Mail-Benachrichtigungen (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- e-mail [Master Data Services], configuring
- notifications [Master Data Services], configuring notifications
ms.assetid: 4241a6ab-7465-471b-9890-57c6b572037e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: baf60677435122af00f5ee5492e47bafaa45a3ac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630699"
---
# <a name="configure-email-notifications-master-data-services"></a><span data-ttu-id="bb36c-102">Konfigurieren von E-Mail-Benachrichtigungen (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="bb36c-102">Configure Email Notifications (Master Data Services)</span></span>
  <span data-ttu-id="bb36c-103">Konfigurieren Sie Benachrichtigungs-E-Mails, wenn E-Mail-Nachrichten von [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] automatisch gesendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="bb36c-103">Configure notification emails when you want [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] to send email messages automatically.</span></span>  
  
### <a name="to-configure-notifications"></a><span data-ttu-id="bb36c-104">So konfigurieren Sie Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="bb36c-104">To configure notifications</span></span>  
  
1.  <span data-ttu-id="bb36c-105">Wählen Sie in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)]auf der Seite **Datenbank** die [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] -Datenbank aus.</span><span class="sxs-lookup"><span data-stu-id="bb36c-105">In [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)], on the **Database** page, select your [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span>  
  
2.  <span data-ttu-id="bb36c-106">Klicken Sie im Abschnitt **Systemeinstellungen** auf **Profil erstellen**.</span><span class="sxs-lookup"><span data-stu-id="bb36c-106">In the **System Settings** section, click **Create Profile**.</span></span>  
  
3.  <span data-ttu-id="bb36c-107">Füllen Sie alle Pflichtfelder aus.</span><span class="sxs-lookup"><span data-stu-id="bb36c-107">Complete all required fields.</span></span> <span data-ttu-id="bb36c-108">Weitere Informationen finden Sie unter [Datenbank-E-Mail-Profil und -Konto erstellen &#40;Dialogfeld im Konfigurations-Manager für Master Data Services&#41;](../../2014/master-data-services/create-database-mail-profile-and-account-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="bb36c-108">For more information, see [Create Database Mail Profile and Account Dialog Box &#40;Master Data Services Configuration Manager&#41;](../../2014/master-data-services/create-database-mail-profile-and-account-dialog-box.md).</span></span>  
  
4.  <span data-ttu-id="bb36c-109">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="bb36c-109">Click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bb36c-110">Nachdem Sie Benachrichtigungen konfiguriert haben, können Sie keine Änderungen mithilfe von [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] vornehmen.</span><span class="sxs-lookup"><span data-stu-id="bb36c-110">After you configure notifications, you cannot use [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] to make changes.</span></span> <span data-ttu-id="bb36c-111">Sie müssen die Änderungen direkt in der [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] -Datenbank vornehmen.</span><span class="sxs-lookup"><span data-stu-id="bb36c-111">You must make changes directly in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="bb36c-112">Weitere Informationen finden Sie unter [Database Mail Configuration Objects](../relational-databases/database-mail/database-mail-configuration-objects.md).</span><span class="sxs-lookup"><span data-stu-id="bb36c-112">For more information, see [Database Mail Configuration Objects](../relational-databases/database-mail/database-mail-configuration-objects.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="bb36c-113">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="bb36c-113">Next Steps</span></span>  
  
-   <span data-ttu-id="bb36c-114">[!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] verfügt über Einstellungen, die sich auf Benachrichtigungen auswirken.</span><span class="sxs-lookup"><span data-stu-id="bb36c-114">There are settings in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] that affect notifications.</span></span> <span data-ttu-id="bb36c-115">Sie können diese Einstellungen in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] oder direkt in der Tabelle Systemeinstellungen der [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] -Datenbank anpassen.</span><span class="sxs-lookup"><span data-stu-id="bb36c-115">You can adjust these settings in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] or directly in the System Settings table in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="bb36c-116">Weitere Informationen finden Sie unter [Systemeinstellungen &#40;Master Data Services&#41;](system-settings-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="bb36c-116">For more information, see [System Settings &#40;Master Data Services&#41;](system-settings-master-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb36c-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bb36c-117">See Also</span></span>  
 <span data-ttu-id="bb36c-118">[Benachrichtigungen &#40;Master Data Services&#41;](../../2014/master-data-services/notifications-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="bb36c-118">[Notifications &#40;Master Data Services&#41;](../../2014/master-data-services/notifications-master-data-services.md) </span></span>  
 <span data-ttu-id="bb36c-119">[Problembehandlung bei e-Mail-Benachrichtigungen (Master Data Services](https://social.technet.microsoft.com/wiki/contents/articles/troubleshooting-email-notifications-master-data-services.aspx) </span><span class="sxs-lookup"><span data-stu-id="bb36c-119">[Troubleshooting Email Notifications (Master Data Services)](https://social.technet.microsoft.com/wiki/contents/articles/troubleshooting-email-notifications-master-data-services.aspx) </span></span>  
 [<span data-ttu-id="bb36c-120">Konfigurieren von Geschäftsregeln für das Senden von Benachrichtigungen &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="bb36c-120">Configure Business Rules to Send Notifications &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/configure-business-rules-to-send-notifications-master-data-services.md)  
  
  
