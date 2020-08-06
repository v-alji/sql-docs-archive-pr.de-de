---
title: Erteilen von Berechtigungen für Benutzer und Warnungsadministratoren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 166808e1-ada7-48d2-bda8-8f7c017fb3aa
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5bf7f030871287379ce9fb32a1789b95cff0fc0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621881"
---
# <a name="grant-permissions-to-users-and-alerting-administrators"></a><span data-ttu-id="411a3-102">Gewähren von Berechtigungen an Benutzer und Warnungsadministratoren</span><span class="sxs-lookup"><span data-stu-id="411a3-102">Grant Permissions to Users and Alerting Administrators</span></span>
  <span data-ttu-id="411a3-103">Bevor Benutzer und Warnungsadministratoren Datenwarnungen erstellen, bearbeiten, löschen und anzeigen können, muss ihnen SharePoint-Berechtigungen gewährt werden.</span><span class="sxs-lookup"><span data-stu-id="411a3-103">Before users and alerting administrators can create, edit, delete, and view data alerts they must be granted SharePoint permissions.</span></span> <span data-ttu-id="411a3-104">Es gibt keine speziellen Berechtigungen für die Verwendung mit der [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Datenwarnungsfunktion. Verwenden Sie die integrierten SharePoint-Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="411a3-104">There are no special permissions to use with the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] data alerting feature, you use the built-in SharePoint permissions.</span></span>  
  
 <span data-ttu-id="411a3-105">**Information Worker**-Berechtigungen müssen die SharePoint-Berechtigungen „Warnung erstellen“ und „Elemente anzeigen“ beinhalten.</span><span class="sxs-lookup"><span data-stu-id="411a3-105">**Information workers**-Permissions must include the Create Alert and View Items SharePoint permissions.</span></span> <span data-ttu-id="411a3-106">Die integrierten SharePoint-Berechtigungensebenen namens Entwerfen, Mitwirken, Lesen und Nur anzeigen enthalten die SharePoint-Berechtigungen "Warnung erstellen" und "Elemente anzeigen".</span><span class="sxs-lookup"><span data-stu-id="411a3-106">The built-in SharePoint permission levels named Design, Contribute, Read, and View Only include the Create Alert and View Items SharePoint permissions.</span></span> <span data-ttu-id="411a3-107">Sie können auch eine benutzerdefinierte Berechtigungsebene mit den erforderlichen Berechtigungen erstellen, um Benutzer zu unterstützen, die Datenwarnungen erstellen, bearbeiten, ausführen und anzeigen.</span><span class="sxs-lookup"><span data-stu-id="411a3-107">You can also create a custom permission level with the permissions required to support users that create, edit, run, and view data alerts.</span></span>  
  
 <span data-ttu-id="411a3-108">**Warnungs Administratoren**: Berechtigungen müssen die SharePoint-Berechtigung "Warnung verwalten" einschließen.</span><span class="sxs-lookup"><span data-stu-id="411a3-108">**Alerting administrators**-Permissions must include the Manage Alert SharePoint permission.</span></span> <span data-ttu-id="411a3-109">Standardmäßig schließt nur die Berechtigungsstufe "Vollzugriff" diese Berechtigung für mit der Websitevorlage der Teamwebsite erstellte Websites ein.</span><span class="sxs-lookup"><span data-stu-id="411a3-109">By default only the Full Control permission level includes this permission for sites created with the Team Site site template.</span></span> <span data-ttu-id="411a3-110">Wenn Sie andere Websitevorlagen verwenden, sehen Sie andere Listen mit Standard-SharePoint-Gruppen.</span><span class="sxs-lookup"><span data-stu-id="411a3-110">If you use other site templates, you will see different lists of default SharePoint groups.</span></span> <span data-ttu-id="411a3-111">Sie können einer der integrierten Berechtigungsebenen die Berechtigung "Warnung verwalten" hinzufügen oder eine benutzerdefinierte Berechtigungsebene mit der erforderlichen Berechtigung erstellen, um Warnungsadministratoren zu unterstützen, die Datenwarnungen anzeigen und löschen.</span><span class="sxs-lookup"><span data-stu-id="411a3-111">You can add the Manage Alert permission to one of the built-in permission levels or create a custom permission level with the permission required to support alerting administrators that view and delete data alerts.</span></span>  
  
 <span data-ttu-id="411a3-112">Weitere Informationen zu SharePoint-Berechtigungen finden Sie im Thema zu [Benutzerberechtigungen und Berechtigungsstufen (SharePoint Server 2010)](https://technet.microsoft.com/library/cc721640.aspx).</span><span class="sxs-lookup"><span data-stu-id="411a3-112">To learn more about SharePoint permissions, see [User permissions and permission levels (SharePoint Server 2010)](https://technet.microsoft.com/library/cc721640.aspx).</span></span>  
  
### <a name="to-grant-permissions"></a><span data-ttu-id="411a3-113">So erteilen Sie Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="411a3-113">To grant permissions</span></span>  
  
1.  <span data-ttu-id="411a3-114">Wechseln Sie zu der SharePoint-Website, der Sie Berechtigungen erteilen möchten.</span><span class="sxs-lookup"><span data-stu-id="411a3-114">Go to the SharePoint site to which you want to grant permissions.</span></span>  
  
2.  <span data-ttu-id="411a3-115">Klicken Sie auf der Symbolleiste auf **Websiteaktionen** und dann auf **Websiteberechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="411a3-115">On the toolbar, click **Site Actions** and then click **Site Permissions**.</span></span>  
  
     <span data-ttu-id="411a3-116">Wenn diese Option nicht angezeigt wird, haben Sie keine ausreichende Berechtigung, um anderen Berechtigungen zu erteilen.</span><span class="sxs-lookup"><span data-stu-id="411a3-116">If you do not see this option, you do not sufficient permission to grant permissions to others.</span></span>  
  
3.  <span data-ttu-id="411a3-117">Klicken Sie auf **Berechtigungen erteilen**.</span><span class="sxs-lookup"><span data-stu-id="411a3-117">Click **Grant Permissions**.</span></span>  
  
4.  <span data-ttu-id="411a3-118">Geben Sie unter **Benutzer/Gruppen**die Benutzernamen, Gruppennamen oder E-Mail-Adressen ein, denen Sie Berechtigungen erteilen möchten.</span><span class="sxs-lookup"><span data-stu-id="411a3-118">In **Users/Groups**, type the user names, group names, or e-mail addresses you want grant permission to.</span></span>  
  
5.  <span data-ttu-id="411a3-119">Aktivieren Sie die Option **Benutzer einer SharePoint-Gruppe hinzufügen** oder **Benutzern eine Berechtigung direkt erteilen** .</span><span class="sxs-lookup"><span data-stu-id="411a3-119">Select the **Add users to a SharePoint group** or **Grant users permission directly** option.</span></span> <span data-ttu-id="411a3-120">Abhängig davon, ob Sie **Benutzer einer SharePoint-Gruppe hinzufügen** oder **Benutzern eine Berechtigung direkt erteilen** ausgewählt haben, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="411a3-120">Depending on whether you selected **Add users to a SharePoint group** or **Grant users permissions directly** do one of the following:</span></span>  
  
    -   <span data-ttu-id="411a3-121">Wenn Sie **Benutzer einer SharePoint-Gruppe hinzufügen**ausgewählt haben, wählen Sie in der Dropdownliste eine Berechtigungsebene aus.</span><span class="sxs-lookup"><span data-stu-id="411a3-121">If you selected **Add users to a SharePoint group**, select a permission level in the drop-down list.</span></span>  
  
    -   <span data-ttu-id="411a3-122">Wenn Sie **Benutzern eine Berechtigung direkt erteilen**ausgewählt haben, wählen Sie eine Berechtigungsebene aus.</span><span class="sxs-lookup"><span data-stu-id="411a3-122">If you selected **Grant users permissions directly**, select a permission level.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="411a3-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="411a3-123">See Also</span></span>  
 <span data-ttu-id="411a3-124">[Festlegen von Berechtigungen für Berichts Server Elemente auf einer SharePoint-Website &#40;Reporting Services im integrierten SharePoint-Modus&#41;](security/set-permissions-for-report-server-items-on-a-sharepoint-site.md) </span><span class="sxs-lookup"><span data-stu-id="411a3-124">[Set Permissions for Report Server Items on a SharePoint Site &#40;Reporting Services in SharePoint Integrated Mode&#41;](security/set-permissions-for-report-server-items-on-a-sharepoint-site.md) </span></span>  
 [<span data-ttu-id="411a3-125">Reporting Services-Datenwarnungen</span><span class="sxs-lookup"><span data-stu-id="411a3-125">Reporting Services Data Alerts</span></span>](../ssms/agent/alerts.md)  
  
  
