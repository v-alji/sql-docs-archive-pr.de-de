---
title: Umbenennen von Anmeldungen, die mit Namen fester Server Rollen übereinstimmen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- user-defined login names [SQL Server]
- fixed server roles [SQL Server]
- renamed logins [SQL Server]
- logins [SQL Server], names
ms.assetid: 10a1d77c-3153-474f-a6a0-969556794467
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 296ae4d4051e79e3c5d3bc158ef3e87c9164ecd3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720839"
---
# <a name="rename-logins-matching-fixed-server-role-names"></a><span data-ttu-id="f5e4e-102">Umbenennen von Anmeldungen, die mit Namen fester Serverrollen identisch sind</span><span class="sxs-lookup"><span data-stu-id="f5e4e-102">Rename logins matching fixed server role names</span></span>
  <span data-ttu-id="f5e4e-103">Der Upgrade Advisor hat einen oder mehrere benutzerdefinierte Anmeldenamen erkannt, die mit den Namen fester Serverrollen identisch sind.</span><span class="sxs-lookup"><span data-stu-id="f5e4e-103">Upgrade Advisor detected one or more user-defined login names that match the names of fixed server roles.</span></span> <span data-ttu-id="f5e4e-104">Namen fester Serverrollen sind reserviert.</span><span class="sxs-lookup"><span data-stu-id="f5e4e-104">Fixed server role names are reserved.</span></span> <span data-ttu-id="f5e4e-105">Benennen Sie den Anmeldenamen um, bevor Sie ein Upgrade durchführen.</span><span class="sxs-lookup"><span data-stu-id="f5e4e-105">Rename the login before you upgrade.</span></span>  
  
## <a name="component"></a><span data-ttu-id="f5e4e-106">Komponente</span><span class="sxs-lookup"><span data-stu-id="f5e4e-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="f5e4e-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f5e4e-107">Description</span></span>  
 <span data-ttu-id="f5e4e-108">Die folgenden Namen von festen Serverrollen sind reserviert und können nicht als benutzerdefinierte Anmeldenamen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f5e4e-108">The following fixed server role names are reserved and cannot be used as user-defined login names.</span></span>  
  
-   <span data-ttu-id="f5e4e-109">**sysadmin**</span><span class="sxs-lookup"><span data-stu-id="f5e4e-109">**sysadmin**</span></span>  
  
-   <span data-ttu-id="f5e4e-110">**serveradmin**</span><span class="sxs-lookup"><span data-stu-id="f5e4e-110">**serveradmin**</span></span>  
  
-   <span data-ttu-id="f5e4e-111">**setupadmin**</span><span class="sxs-lookup"><span data-stu-id="f5e4e-111">**setupadmin**</span></span>  
  
-   <span data-ttu-id="f5e4e-112">**securityadmin**</span><span class="sxs-lookup"><span data-stu-id="f5e4e-112">**securityadmin**</span></span>  
  
-   <span data-ttu-id="f5e4e-113">**processadmin**</span><span class="sxs-lookup"><span data-stu-id="f5e4e-113">**processadmin**</span></span>  
  
-   <span data-ttu-id="f5e4e-114">**dbcreator**</span><span class="sxs-lookup"><span data-stu-id="f5e4e-114">**dbcreator**</span></span>  
  
-   <span data-ttu-id="f5e4e-115">**diskadmin**</span><span class="sxs-lookup"><span data-stu-id="f5e4e-115">**diskadmin**</span></span>  
  
-   <span data-ttu-id="f5e4e-116">**bulkadmin**</span><span class="sxs-lookup"><span data-stu-id="f5e4e-116">**bulkadmin**</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="f5e4e-117">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="f5e4e-117">Corrective Action</span></span>  
 <span data-ttu-id="f5e4e-118">Führen Sie vor dem Upgrade die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="f5e4e-118">Before upgrading, perform the following steps:</span></span>  
  
1.  <span data-ttu-id="f5e4e-119">Erfassen Sie die Sicherheits-IDs (SIDs) der Anmeldungen durch Ausführen der folgenden Anweisung.</span><span class="sxs-lookup"><span data-stu-id="f5e4e-119">Record the security identifiers (SIDs) of the logins by executing the following statement.</span></span>  
  
    ```  
    SELECT name, sid   
    FROM master.dbo.syslogins   
    WHERE name IN('sysadmin', 'serveradmin','setupadmin', 'securityadmin','processadmin', 'dbcreator','diskadmin','bulkadmin')  
    ```  
  
2.  <span data-ttu-id="f5e4e-120">Löschen Sie die Anmeldungen.</span><span class="sxs-lookup"><span data-stu-id="f5e4e-120">Drop the logins.</span></span>  
  
3.  <span data-ttu-id="f5e4e-121">Verwenden Sie das Verfahren **sp_addlogin** System, um neue Anmeldungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f5e4e-121">Use the **sp_addlogin** system procedure to create new logins.</span></span> <span data-ttu-id="f5e4e-122">Geben Sie die SID an, die in Schritt 1 im \*\* \@ sid\*\* -Parameter für jeden entsprechenden Anmelde Namen zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="f5e4e-122">Specify the SID returned in step 1 in the **\@sid** parameter for each corresponding login.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5e4e-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f5e4e-123">See Also</span></span>  
 <span data-ttu-id="f5e4e-124">[Datenbank-Engine Upgradeprobleme](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="f5e4e-124">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="f5e4e-125">SQL Server 2014 Upgrade Advisor &#91;neuen&#93;</span><span class="sxs-lookup"><span data-stu-id="f5e4e-125">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
