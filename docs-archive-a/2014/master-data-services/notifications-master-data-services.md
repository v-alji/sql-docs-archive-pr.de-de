---
title: Benachrichtigungen (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- notifications [Master Data Services]
- notifications [Master Data Services], about notifications
- e-mail [Master Data Services]
- e-mail [Master Data Services], about e-mail notifications
ms.assetid: d7ad32d5-9fe5-48fd-8c61-0b00c0aff082
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: a61825f9450dd5b708aff8c3fc72f0f12732337b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622171"
---
# <a name="notifications-master-data-services"></a><span data-ttu-id="87456-102">Benachrichtigungen (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="87456-102">Notifications (Master Data Services)</span></span>
  [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]<span data-ttu-id="87456-103">kann konfiguriert werden, um eine e-Mail-Benachrichtigung zu senden, wenn die Geschäftsregel Überprüfung fehlschlägt oder sich der Status einer Modellversion ändert.</span><span class="sxs-lookup"><span data-stu-id="87456-103">can be configured to send an email notification when business rule validation fails or the status of a model version changes.</span></span>  
  
## <a name="how-notifications-are-sent"></a><span data-ttu-id="87456-104">Senden von Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="87456-104">How Notifications Are Sent</span></span>  
 <span data-ttu-id="87456-105">Benachrichtigungen werden in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)]konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="87456-105">You configure notifications in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)].</span></span> <span data-ttu-id="87456-106">Benachrichtigungen senden e-Mail-Nachrichten mithilfe von Datenbank-E-Mail auf der Instanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../includes/ssde-md.md)] , die die Datenbank hostet [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="87456-106">Notifications send email messages by using Database Mail on the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../includes/ssde-md.md)] that hosts the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="87456-107">Weitere Informationen zu Datenbank-E-Mails finden Sie unter [Konfigurationsobjekte für Datenbank-E-Mail](../relational-databases/database-mail/database-mail-configuration-objects.md) in der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="87456-107">For more information about Database Mail, see [Database Mail Configuration Objects](../relational-databases/database-mail/database-mail-configuration-objects.md) in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="when-notifications-are-sent"></a><span data-ttu-id="87456-108">Zeitpunkt des Sendens von Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="87456-108">When Notifications Are Sent</span></span>  
 <span data-ttu-id="87456-109">Nachdem Benachrichtigungen konfiguriert wurden, können automatisierte E-Mail-Benachrichtigungen in den folgenden Instanzen gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="87456-109">After notifications are configured, automated email notifications can be sent in the following instances.</span></span>  
  
|<span data-ttu-id="87456-110">Instanz</span><span class="sxs-lookup"><span data-stu-id="87456-110">Instance</span></span>|<span data-ttu-id="87456-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="87456-111">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="87456-112">Daten haben die Geschäftsregelüberprüfung nicht bestanden.</span><span class="sxs-lookup"><span data-stu-id="87456-112">Data fails business rule validation</span></span>|<span data-ttu-id="87456-113">Es müssen separate Geschäftsregeln konfiguriert werden, um E-Mails zu senden, wenn ein Attributwert die Geschäftsregelüberprüfung nicht besteht.</span><span class="sxs-lookup"><span data-stu-id="87456-113">Individual business rules must be configured to send email when an attribute value fails business rule validation.</span></span> <span data-ttu-id="87456-114">Weitere Informationen finden Sie unter [Konfigurieren von Geschäftsregeln für das Senden von Benachrichtigungen &#40;Master Data Services&#41;](configure-business-rules-to-send-notifications-master-data-services.md)konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="87456-114">For more information, see [Configure Business Rules to Send Notifications &#40;Master Data Services&#41;](configure-business-rules-to-send-notifications-master-data-services.md).</span></span>|  
|<span data-ttu-id="87456-115">Der Status einer Modellversion ändert sich.</span><span class="sxs-lookup"><span data-stu-id="87456-115">Model version status changes</span></span>|<span data-ttu-id="87456-116">Jedes Mal, wenn sich der Status einer Modellversion ändert, erhalten Modelladministratoren automatisch eine Benachrichtigung.</span><span class="sxs-lookup"><span data-stu-id="87456-116">Each time a model version's status changes, users that are model administrators receive notifications automatically.</span></span> <span data-ttu-id="87456-117">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="87456-117">For more information, see [Administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span></span>|  
  
## <a name="system-settings"></a><span data-ttu-id="87456-118">Systemeinstellungen</span><span class="sxs-lookup"><span data-stu-id="87456-118">System Settings</span></span>  
 <span data-ttu-id="87456-119">[!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] verfügt über Einstellungen, die sich auf Benachrichtigungen auswirken.</span><span class="sxs-lookup"><span data-stu-id="87456-119">There are settings in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] that affect notifications.</span></span> <span data-ttu-id="87456-120">Sie können diese Einstellungen in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] oder direkt in der Tabelle Systemeinstellungen der [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] -Datenbank anpassen.</span><span class="sxs-lookup"><span data-stu-id="87456-120">You can adjust these settings in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] or directly in the System Settings table in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="87456-121">Weitere Informationen finden Sie unter [Systemeinstellungen &#40;Master Data Services&#41;](../../2014/master-data-services/system-settings-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="87456-121">For more information, see [System Settings &#40;Master Data Services&#41;](../../2014/master-data-services/system-settings-master-data-services.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="87456-122">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="87456-122">Related Tasks</span></span>  
  
|<span data-ttu-id="87456-123">Taskbeschreibung</span><span class="sxs-lookup"><span data-stu-id="87456-123">Task Description</span></span>|<span data-ttu-id="87456-124">Thema</span><span class="sxs-lookup"><span data-stu-id="87456-124">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="87456-125">Konfigurieren Sie [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] , um E-Mail-Benachrichtigungen zu senden.</span><span class="sxs-lookup"><span data-stu-id="87456-125">Configure [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] to send email notifications.</span></span>|[<span data-ttu-id="87456-126">Konfigurieren von E-Mail-Benachrichtigungen &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="87456-126">Configure Email Notifications &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/configure-email-notifications-master-data-services.md)|  
|<span data-ttu-id="87456-127">Konfigurieren Sie [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , um Benachrichtigungen zu senden, wenn sich Attributwerte ändern.</span><span class="sxs-lookup"><span data-stu-id="87456-127">Configure [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] to send notifications when attribute values change.</span></span>|[<span data-ttu-id="87456-128">Konfigurieren von Geschäftsregeln für das Senden von Benachrichtigungen &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="87456-128">Configure Business Rules to Send Notifications &#40;Master Data Services&#41;</span></span>](configure-business-rules-to-send-notifications-master-data-services.md)|  
  
## <a name="related-content"></a><span data-ttu-id="87456-129">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="87456-129">Related Content</span></span>  
  
-   [<span data-ttu-id="87456-130">Geschäftsregeln &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="87456-130">Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/business-rules-master-data-services.md)  
  
-   [<span data-ttu-id="87456-131">Versionen &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="87456-131">Versions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/versions-master-data-services.md)  
  
-   [<span data-ttu-id="87456-132">Problembehandlung für E-Mail-Benachrichtigungen (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="87456-132">Troubleshooting Email Notifications (Master Data Services)</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/troubleshooting-email-notifications-master-data-services.aspx)  
  
  
