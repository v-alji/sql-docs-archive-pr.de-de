---
title: Ändern des System Administrator Kontos (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- administrators [Master Data Services], changing
ms.assetid: cf30312e-4338-49a7-90f0-6e4f7b431ff8
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 1d13cdc19c70c9e16c92dfd290393739d7e4f5e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718370"
---
# <a name="change-the-system-administrator-account-master-data-services"></a><span data-ttu-id="592f4-102">Ändern Systemadministratorkontos (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="592f4-102">Change the System Administrator Account (Master Data Services)</span></span>
  <span data-ttu-id="592f4-103">Sie können das Benutzerkonto ändern, das als Systemadministrator festgelegt ist [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="592f4-103">You can change the user account that is designated as the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] system administrator.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="592f4-104">Wenn Sie diese Prozedur ausführen, wird das Benutzerkonto des vorherigen Systemadministrators gelöscht.</span><span class="sxs-lookup"><span data-stu-id="592f4-104">When you complete this procedure, the former system administrator user account is deleted.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="592f4-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="592f4-105">Prerequisites</span></span>  
 <span data-ttu-id="592f4-106">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="592f4-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="592f4-107">Sie müssen der Liste Benutzer in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] den Benutzernamen des neuen Administrators hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="592f4-107">You must add the new administrator's user name to the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] Users list.</span></span> <span data-ttu-id="592f4-108">Weitere Informationen finden Sie unter [Hinzufügen eines Benutzer &#40;Master Data Services&#41;](add-a-user-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="592f4-108">For more information, see [Add a User &#40;Master Data Services&#41;](add-a-user-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="592f4-109">Sie müssen berechtigt sein, die Tabelle mdm.tblUser anzuzeigen und die gespeicherte Prozedur mdm.udpSecurityMemberProcessRebuildModel in der [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]-Datenbank auszuführen.</span><span class="sxs-lookup"><span data-stu-id="592f4-109">You must have permission to view mdm.tblUser and to execute the mdm.udpSecurityMemberProcessRebuildModel stored procedure in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="592f4-110">Weitere Informationen finden Sie unter [Sicherheit von Datenbankobjekten &#40;Master Data Services&#41;](../../2014/master-data-services/database-object-security-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="592f4-110">For more information, see [Database Object Security &#40;Master Data Services&#41;](../../2014/master-data-services/database-object-security-master-data-services.md).</span></span>  
  
### <a name="to-change-the-administrator-account"></a><span data-ttu-id="592f4-111">So ändern Sie das Administratorkonto</span><span class="sxs-lookup"><span data-stu-id="592f4-111">To change the administrator account</span></span>  
  
1.  <span data-ttu-id="592f4-112">Öffnen Sie [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] , und stellen Sie eine Verbindung mit der [!INCLUDE[ssDE](../includes/ssde-md.md)] -Instanz für die [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] -Datenbank her.</span><span class="sxs-lookup"><span data-stu-id="592f4-112">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] instance for your [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span>  
  
2.  <span data-ttu-id="592f4-113">Suchen Sie in MDM. tbluser den Benutzer, der als neuer Administrator verwendet werden soll, und kopieren Sie den Wert in der `SID` Spalte.</span><span class="sxs-lookup"><span data-stu-id="592f4-113">In mdm.tblUser, find the user that will be the new administrator and copy the value in the `SID` column.</span></span>  
  
3.  <span data-ttu-id="592f4-114">Erstellen Sie eine neue Abfrage.</span><span class="sxs-lookup"><span data-stu-id="592f4-114">Create a new query.</span></span>  
  
4.  <span data-ttu-id="592f4-115">Geben Sie den folgenden Text ein, und ersetzen Sie dabei *Domain \ user_name* durch den Benutzernamen und die *sid* des neuen Administrators durch den Wert, den Sie in Schritt 2 kopiert haben.</span><span class="sxs-lookup"><span data-stu-id="592f4-115">Type the following text, replacing *DOMAIN\user_name* with the new administrator's user name and *SID* with the value you copied in step 2.</span></span>  
  
    ```  
    EXEC [mdm].[udpSecuritySetAdministrator] @UserName='DOMAIN\user_name', @SID = 'SID', @PromoteNonAdmin = 1  
    ```  
  
5.  <span data-ttu-id="592f4-116">Führen Sie die Abfrage aus.</span><span class="sxs-lookup"><span data-stu-id="592f4-116">Run the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="592f4-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="592f4-117">See Also</span></span>  
 [<span data-ttu-id="592f4-118">Administratoren &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="592f4-118">Administrators &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/administrators-master-data-services.md)  
  
  
