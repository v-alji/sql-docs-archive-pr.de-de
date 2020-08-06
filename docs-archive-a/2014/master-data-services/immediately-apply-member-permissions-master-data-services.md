---
title: Sofortiges Anwenden von Elementberechtigungen (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- members [Master Data Services], applying permissions immediately
- permissions [Master Data Services], applying member permissions immediately
ms.assetid: 5b16de66-5c39-49f5-992f-402a9eb319aa
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: e960ad06213b7c5057a6249b72ce225a6abe35e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619174"
---
# <a name="immediately-apply-member-permissions-master-data-services"></a><span data-ttu-id="01b56-102">Sofortiges Anwenden von Elementberechtigungen (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="01b56-102">Immediately Apply Member Permissions (Master Data Services)</span></span>
  <span data-ttu-id="01b56-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]können Sie sofort Elementberechtigungen anwenden, statt zu warten, bis die Elementsicherheit in regelmäßigen Abständen angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="01b56-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], instead of waiting for member security to be applied at regular intervals, you can apply member permissions immediately.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="01b56-104">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="01b56-104">Prerequisites</span></span>  
 <span data-ttu-id="01b56-105">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="01b56-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="01b56-106">Sie müssen über die Berechtigung verfügen, die gespeicherte Prozedur mdm.udpSecurityMemberProcessRebuildModel in der [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] -Datenbank auszuführen.</span><span class="sxs-lookup"><span data-stu-id="01b56-106">You must have permission to execute the mdm.udpSecurityMemberProcessRebuildModel stored procedure in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="01b56-107">Weitere Informationen finden Sie unter [Sicherheit von Datenbankobjekten &#40;Master Data Services&#41;](database-object-security-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="01b56-107">For more information, see [Database Object Security &#40;Master Data Services&#41;](database-object-security-master-data-services.md).</span></span>  
  
### <a name="to-immediately-apply-hierarchy-member-permissions"></a><span data-ttu-id="01b56-108">So wenden Sie Hierarchieelementberechtigungen sofort an</span><span class="sxs-lookup"><span data-stu-id="01b56-108">To immediately apply hierarchy member permissions</span></span>  
  
1.  <span data-ttu-id="01b56-109">Öffnen Sie [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] , und stellen Sie eine Verbindung mit der [!INCLUDE[ssDE](../includes/ssde-md.md)] -Instanz für die [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] -Datenbank her.</span><span class="sxs-lookup"><span data-stu-id="01b56-109">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] instance for your [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span>  
  
2.  <span data-ttu-id="01b56-110">Erstellen Sie eine neue Abfrage.</span><span class="sxs-lookup"><span data-stu-id="01b56-110">Create a new query.</span></span>  
  
3.  <span data-ttu-id="01b56-111">Geben Sie den folgenden Text ein, und ersetzen Sie *Datenbank* durch den Namen Ihrer Datenbank und *Name des Modells* durch den Namen des Modells.</span><span class="sxs-lookup"><span data-stu-id="01b56-111">Type the following text, replacing *database* with the name of your database and *Model_Name* with the name of the model.</span></span>  
  
    ```  
    USE [database];  
    GO  
  
    DECLARE @Model_ID INT;  
    SELECT @Model_ID = ID FROM mdm.tblModel WHERE [Name] = N'Model_Name';  
    EXEC [mdm].[udpSecurityMemberProcessRebuildModel] @Model_ID=@Model_ID, @ProcessNow=1;  
    GO  
    ```  
  
4.  <span data-ttu-id="01b56-112">Führen Sie die Abfrage aus.</span><span class="sxs-lookup"><span data-stu-id="01b56-112">Run the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01b56-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="01b56-113">See Also</span></span>  
 <span data-ttu-id="01b56-114">[Hierarchie Element Berechtigungen &#40;Master Data Services zuweisen&#41;](../../2014/master-data-services/assign-hierarchy-member-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="01b56-114">[Assign Hierarchy Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/assign-hierarchy-member-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="01b56-115">Berechtigungen für Hierarchieelemente &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="01b56-115">Hierarchy Member Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/hierarchy-member-permissions-master-data-services.md)  
  
  
