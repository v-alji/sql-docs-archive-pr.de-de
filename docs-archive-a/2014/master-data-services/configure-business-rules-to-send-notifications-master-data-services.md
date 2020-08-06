---
title: Konfigurieren von Geschäftsregeln für das Senden von Benachrichtigungen (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- business rules [Master Data Services], configuring notifications
- e-mail [Master Data Services], configuring business rules
- notifications [Master Data Services], configuring business rules
ms.assetid: b24f7b11-ab53-4642-999c-e17b543b3558
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: cb1a12167dffe123e55760f031e21499fe22a945
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630700"
---
# <a name="configure-business-rules-to-send-notifications-master-data-services"></a><span data-ttu-id="6f452-102">Konfigurieren von Geschäftsregeln für das Senden von Benachrichtigungen (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="6f452-102">Configure Business Rules to Send Notifications (Master Data Services)</span></span>
  <span data-ttu-id="6f452-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]konfigurieren Sie Geschäftsregeln für das Senden von Benachrichtigungen, wenn Sie Benutzer über Änderungen von Attributwerten in Kenntnis setzen möchten.</span><span class="sxs-lookup"><span data-stu-id="6f452-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], configure business rules to send notifications when you want to notify users about attribute value changes.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6f452-104">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="6f452-104">Prerequisites</span></span>  
 <span data-ttu-id="6f452-105">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="6f452-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="6f452-106">Sie müssen über die Berechtigung für den Zugriff auf die Funktionsbereiche **Systemverwaltung** und **Benutzer- und Gruppenberechtigungen** verfügen.</span><span class="sxs-lookup"><span data-stu-id="6f452-106">You must have permission to access the **System Administration** and **User and Group Permissions** functional areas.</span></span> <span data-ttu-id="6f452-107">Wenn Sie nicht über die Berechtigung für den Funktionsbereich **Benutzer- und Gruppenberechtigungen** verfügen, können Sie die Liste der Benutzer und Gruppen nicht anzeigen, an die Benachrichtigungen gesendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6f452-107">If you do not have permission to the **User and Group Permissions** functional area, you cannot view the list of users and groups to send notifications to.</span></span>  
  
-   <span data-ttu-id="6f452-108">Sie müssen ein Modelladministrator sein.</span><span class="sxs-lookup"><span data-stu-id="6f452-108">You must be a model administrator.</span></span> <span data-ttu-id="6f452-109">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="6f452-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="6f452-110">Es muss bereits eine Geschäftsregel vorhanden sein, die eine Überprüfungsaktion verwendet.</span><span class="sxs-lookup"><span data-stu-id="6f452-110">A business rule that uses a validation action must already exist.</span></span> <span data-ttu-id="6f452-111">Weitere Informationen finden Sie unter [Erstellen und Veröffentlichen einer Geschäftsregel &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="6f452-111">For more information, see [Create and Publish a Business Rule &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="6f452-112">Der Benutzer oder die Gruppe, der bzw. die die Benachrichtigung empfängt, muss mindestens die **Leseberechtigung** für das Attribut haben, dessen Überprüfung einen Fehler ergibt.</span><span class="sxs-lookup"><span data-stu-id="6f452-112">The user or group that receives the notification must have at least **Read-only** permission to the attribute that fails validation.</span></span> <span data-ttu-id="6f452-113">Benutzer oder Gruppen, denen die Berechtigung für das Attribut explizit oder implizit verweigert wird, empfangen die E-Mail, können jedoch in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]nicht auf das Attribut zugreifen.</span><span class="sxs-lookup"><span data-stu-id="6f452-113">Users or groups that are explicitly or implicitly denied permission to the attribute will receive the email but will not be able to access the attribute in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
-   <span data-ttu-id="6f452-114">Wenn eine E-Mail an eine Gruppe gesendet wird, wird die E-Mail nur Mitgliedern der Gruppe zugestellt, die auf den [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] zugegriffen haben.</span><span class="sxs-lookup"><span data-stu-id="6f452-114">If mail is sent to a group, only members of the group that have accessed [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] will get the email.</span></span>  
  
### <a name="to-configure-business-rules-to-send-notifications"></a><span data-ttu-id="6f452-115">So konfigurieren Sie Geschäftsregeln für das Senden von Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="6f452-115">To configure business rules to send notifications</span></span>  
  
1.  <span data-ttu-id="6f452-116">Klicken Sie in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]auf **Systemverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="6f452-116">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="6f452-117">Zeigen Sie auf der Menüleiste auf **Verwalten** , und klicken Sie auf **Geschäftsregeln**.</span><span class="sxs-lookup"><span data-stu-id="6f452-117">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="6f452-118">Wählen Sie auf der Seite **Verwaltung von Geschäftsregeln** aus der Liste **Modell** ein Modell aus.</span><span class="sxs-lookup"><span data-stu-id="6f452-118">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="6f452-119">Wählen Sie aus der Liste **Entität** eine Entität aus.</span><span class="sxs-lookup"><span data-stu-id="6f452-119">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="6f452-120">Wählen Sie in der Liste **Elementtyp** einen Typ des Members aus.</span><span class="sxs-lookup"><span data-stu-id="6f452-120">From the **Member Type** list, select a type of member.</span></span>  
  
6.  <span data-ttu-id="6f452-121">Wählen Sie aus der Liste **Attribut** ein Attribut aus, oder behalten Sie die Standardeinstellung **Alle**bei.</span><span class="sxs-lookup"><span data-stu-id="6f452-121">From the **Attribute** list, select an attribute or leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="6f452-122">Doppelklicken Sie im Raster in der Zeile für die Geschäftsregel auf das **Benachrichtigungs** Feld.</span><span class="sxs-lookup"><span data-stu-id="6f452-122">In the grid, in the row for the business rule, double-click the **Notification** field.</span></span>  
  
8.  <span data-ttu-id="6f452-123">Klicken Sie im Untermenü auf einen Benutzer oder eine Gruppe, an den die e-Mail-Benachrichtigung gesendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="6f452-123">From the sub-menu, click a user or group to send the email notification to.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="6f452-124">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="6f452-124">Next Steps</span></span>  
  
-   <span data-ttu-id="6f452-125">Führen Sie zum Anwenden von Geschäftsregeln auf Daten eine der folgenden Prozeduren aus:</span><span class="sxs-lookup"><span data-stu-id="6f452-125">Apply business rules to data by following one of these procedures:</span></span>  
  
    -   [<span data-ttu-id="6f452-126">Überprüfen von bestimmten Elementen auf Geschäftsregeln &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="6f452-126">Validate Specific Members against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-specific-members-against-business-rules-master-data-services.md)  
  
    -   [<span data-ttu-id="6f452-127">Überprüfen einer Version anhand von Geschäftsregeln &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="6f452-127">Validate a Version against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-a-version-against-business-rules-master-data-services.md)  
  
-   <span data-ttu-id="6f452-128">Konfigurieren Sie das E-Mail-Protokoll wie folgt:</span><span class="sxs-lookup"><span data-stu-id="6f452-128">Configure the email protocol as follows:</span></span>  
  
    -   [<span data-ttu-id="6f452-129">Konfigurieren von E-Mail-Benachrichtigungen &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="6f452-129">Configure Email Notifications &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/configure-email-notifications-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="6f452-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6f452-130">See Also</span></span>  
 <span data-ttu-id="6f452-131">[Benachrichtigungen &#40;Master Data Services&#41;](../../2014/master-data-services/notifications-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="6f452-131">[Notifications &#40;Master Data Services&#41;](../../2014/master-data-services/notifications-master-data-services.md) </span></span>  
 [<span data-ttu-id="6f452-132">Konfigurieren von E-Mail-Benachrichtigungen &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="6f452-132">Configure Email Notifications &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/configure-email-notifications-master-data-services.md)  
  
  
