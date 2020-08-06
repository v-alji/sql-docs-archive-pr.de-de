---
title: Umbenennen von Benutzern in sys | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- sys user names [SQL Server]
ms.assetid: d622d646-83e4-4b6f-9a21-77b301af04b5
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 3af9d31a54adc5645cab6fcc7104ae7ff27a61b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608241"
---
# <a name="rename-user-sys"></a><span data-ttu-id="b991a-102">Benennen Sie den Benutzer 'sys' um</span><span class="sxs-lookup"><span data-stu-id="b991a-102">Rename user sys</span></span>
  <span data-ttu-id="b991a-103">Der Upgrade Advisor hat den Benutzernamen **sys** in einer Datenbank erkannt.</span><span class="sxs-lookup"><span data-stu-id="b991a-103">Upgrade Advisor detected the user name **sys** in a database.</span></span> <span data-ttu-id="b991a-104">Dieser Name ist reserviert.</span><span class="sxs-lookup"><span data-stu-id="b991a-104">This name is reserved.</span></span> <span data-ttu-id="b991a-105">Benennen Sie den Benutzer um, bevor Sie ein Upgrade durchführen.</span><span class="sxs-lookup"><span data-stu-id="b991a-105">Rename the user before you upgrade.</span></span> <span data-ttu-id="b991a-106">Wenn der Benutzer nicht umbenannt wird, ist die Datenbank nach dem Upgradevorgang fehlerverdächtig und nicht verfügbar, bis die Datenbank online geschaltet wird.</span><span class="sxs-lookup"><span data-stu-id="b991a-106">If the user is not renamed, the database will be in a suspect state after the upgrade process and will be unavailable until the database is brought online.</span></span>  
  
## <a name="component"></a><span data-ttu-id="b991a-107">Komponente</span><span class="sxs-lookup"><span data-stu-id="b991a-107">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="b991a-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b991a-108">Description</span></span>  
 <span data-ttu-id="b991a-109">Der Benutzer **sys** ist reserviert.</span><span class="sxs-lookup"><span data-stu-id="b991a-109">User **sys** is reserved.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="b991a-110">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="b991a-110">Corrective Action</span></span>  
  
### <a name="before-upgrade-procedure"></a><span data-ttu-id="b991a-111">Vorgehensweise vor dem Upgrade</span><span class="sxs-lookup"><span data-stu-id="b991a-111">Before Upgrade Procedure</span></span>  
 <span data-ttu-id="b991a-112">Führen Sie vor dem Upgrade in jeder Datenbank, die den Benutzer **sys**enthält, folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="b991a-112">Before you upgrade, in each database that contains user **sys**, do the following:</span></span>  
  
1.  <span data-ttu-id="b991a-113">Erstellen Sie einen neuen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="b991a-113">Create a new user.</span></span>  
  
2.  <span data-ttu-id="b991a-114">Verwenden Sie die folgenden Anweisungen, um alle Berechtigungen anzuzeigen, die vom Benutzer **sys** erteilt und für den Benutzer **sys**erteilt wurden.</span><span class="sxs-lookup"><span data-stu-id="b991a-114">Use the following statements to display all permissions that are granted by user **sys** and granted to user **sys**.</span></span>  
  
    ```  
    -- Return permissions granted by user sys.  
    SELECT * FROM sysprotects WHERE grantor = USER_ID('sys')  
    -- Return permissions granted to user sys.  
    SELECT * FROM sysprotects WHERE uid = USER_ID('sys')  
    ```  
  
3.  <span data-ttu-id="b991a-115">Verwenden Sie **sp_changeobjectowner**, um den Besitz aller Objekte im Besitz von **sys** auf den neuen Benutzer zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="b991a-115">To transfer ownership of all objects owned by **sys** to the new user, use **sp_changeobjectowner**.</span></span>  
  
4.  <span data-ttu-id="b991a-116">Löschen Sie den Benutzer **sys**.</span><span class="sxs-lookup"><span data-stu-id="b991a-116">Drop user **sys**.</span></span>  
  
5.  <span data-ttu-id="b991a-117">Verwenden Sie die as *new_user* -Klausel der GRANT-Anweisung, um die in Schritt 2 erfassten ursprünglichen Berechtigungen wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="b991a-117">To restore the original permissions captured in step 2, use the AS *new_user* clause of the GRANT statement.</span></span>  
  
6.  <span data-ttu-id="b991a-118">Ändern Sie die Skripts so, dass sie auf den neuen Benutzer verweisen.</span><span class="sxs-lookup"><span data-stu-id="b991a-118">Modify scripts to reference the new user.</span></span> <span data-ttu-id="b991a-119">So müssen z. B. Skripts, die Anweisungen wie `SELECT * FROM sys.my`_`table` enthalten, in `SELECT * FROM new_user.my_table` geändert werden.</span><span class="sxs-lookup"><span data-stu-id="b991a-119">For example, scripts that contain statements such as `SELECT * FROM sys.my`_`table` must be changed to `SELECT * FROM new_user.my_table`.</span></span>  
  
### <a name="after-upgrade-procedure"></a><span data-ttu-id="b991a-120">Vorgehensweise nach dem Upgrade</span><span class="sxs-lookup"><span data-stu-id="b991a-120">After Upgrade Procedure</span></span>  
 <span data-ttu-id="b991a-121">Wenn der Benutzer **sys** vor dem Upgrade nicht umbenannt wurde, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="b991a-121">If the user **sys** was not renamed prior to upgrading, do the following:</span></span>  
  
1.  <span data-ttu-id="b991a-122">Führen Sie die Anweisung `ALTER DATABASE db_name SET ONLINE` aus.</span><span class="sxs-lookup"><span data-stu-id="b991a-122">Execute the statement `ALTER DATABASE db_name SET ONLINE`.</span></span> <span data-ttu-id="b991a-123">Die Datenbank befindet sich im SINGLE_USER-Modus.</span><span class="sxs-lookup"><span data-stu-id="b991a-123">The database will be in SINGLE_USER mode.</span></span>  
  
2.  <span data-ttu-id="b991a-124">Führen Sie alle Schritte im Abschnitt "Vorgehensweise vor dem Upgrade" aus.</span><span class="sxs-lookup"><span data-stu-id="b991a-124">Follow all steps in the Before Upgrade Procedure section.</span></span>  
  
3.  <span data-ttu-id="b991a-125">Führen Sie die Anweisung `ALTER DATABASE db_name SET MULTI_USER` aus.</span><span class="sxs-lookup"><span data-stu-id="b991a-125">Execute the statement `ALTER DATABASE db_name SET MULTI_USER`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b991a-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b991a-126">See Also</span></span>  
 <span data-ttu-id="b991a-127">[Datenbank-Engine Upgradeprobleme](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="b991a-127">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="b991a-128">SQL Server 2014 Upgrade Advisor &#91;neuen&#93;</span><span class="sxs-lookup"><span data-stu-id="b991a-128">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
