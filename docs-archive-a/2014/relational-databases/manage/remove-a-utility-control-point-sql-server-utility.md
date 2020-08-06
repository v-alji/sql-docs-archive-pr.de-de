---
title: Entfernen eines Steuerungspunkts für das Hilfsprogramm (SQL Server-Hilfsprogramm) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: c048a416-900e-4c77-8243-e0f0d8b94068
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: fe4ebb9de3f7644b4cff5c7dbfb34e50be7e8993
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622631"
---
# <a name="remove-a-utility-control-point-sql-server-utility"></a><span data-ttu-id="656a5-102">Entfernen eines Steuerungspunkts für das Hilfsprogramm (SQL Server-Hilfsprogramm)</span><span class="sxs-lookup"><span data-stu-id="656a5-102">Remove a Utility Control Point (SQL Server Utility)</span></span>
  <span data-ttu-id="656a5-103">In diesem Thema wird beschrieben, wie Sie einen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Steuerungspunkt für das Hilfsprogramm (UCP) von der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[tsql](../../includes/tsql-md.md)]entfernen können.</span><span class="sxs-lookup"><span data-stu-id="656a5-103">This topic describes how to remove a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utility control point (UCP) from the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="656a5-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="656a5-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="656a5-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="656a5-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="656a5-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="656a5-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="656a5-107">Security</span><span class="sxs-lookup"><span data-stu-id="656a5-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="656a5-108">**So entfernen Sie einen Steuerungspunkt für das Hilfsprogramm mit**</span><span class="sxs-lookup"><span data-stu-id="656a5-108">**To remove a Utility Control Point, using:**</span></span>  
  
     [<span data-ttu-id="656a5-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="656a5-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="656a5-110">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="656a5-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="656a5-111">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="656a5-111">Limitations and Restrictions</span></span>  
 <span data-ttu-id="656a5-112">Bevor Sie den UCP aus dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Hilfsprogramm entfernen, die folgenden Bedingungen erfüllt sein.</span><span class="sxs-lookup"><span data-stu-id="656a5-112">Before you use this procedure to remove the UCP from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility, note the following requirements.</span></span> <span data-ttu-id="656a5-113">Die gespeicherte Prozedur führt die erforderlichen Überprüfungen im Rahmen des Vorgangs aus.</span><span class="sxs-lookup"><span data-stu-id="656a5-113">The stored procedure will run prerequisite checks as part of the operation.</span></span>  
  
-   <span data-ttu-id="656a5-114">Vor dem Ausführen dieser Prozedur müssen alle verwalteten Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] aus dem UCP entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="656a5-114">Before you run this procedure, all managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be removed from the UCP.</span></span> <span data-ttu-id="656a5-115">Beachten Sie dabei, dass der UCP eine verwaltete Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ist.</span><span class="sxs-lookup"><span data-stu-id="656a5-115">Note that the UCP is a managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="656a5-116">Weitere Informationen finden Sie unter [Entfernen einer Instanz von SQL Server aus dem SQL Server-Hilfsprogramm](remove-an-instance-of-sql-server-from-the-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="656a5-116">From more information, see [Remove an Instance of SQL Server from the SQL Server Utility](remove-an-instance-of-sql-server-from-the-sql-server-utility.md).</span></span>  
  
-   <span data-ttu-id="656a5-117">Diese Prozedur muss auf einem Computer ausgeführt werden, der ein UCP ist.</span><span class="sxs-lookup"><span data-stu-id="656a5-117">This procedure must be run on a computer that is a UCP.</span></span>  
  
-   <span data-ttu-id="656a5-118">Wenn die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , aus der der UCP entfernt wurde, nur Datensammlungen enthält, die nicht von dem Hilfsprogramm stammen, wird die UMDW-Datenbank (sysutility_mdw) von der Prozedur nicht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="656a5-118">If the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] where the UCP was removed has a non-Utility data collection set, the UMDW database (sysutility_mdw) will not be dropped by the procedure.</span></span> <span data-ttu-id="656a5-119">In diesem Fall muss die UMDW-Datenbank (sysutility_mdw) manuell gelöscht werden, bevor der UCP erneut erstellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="656a5-119">If this is the case, the UMDW database (sysutility_mdw) must be dropped manually before the UCP can be created again.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="656a5-120">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="656a5-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="656a5-121">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="656a5-121">Permissions</span></span>  
 <span data-ttu-id="656a5-122">Die Prozedur muss von einem Benutzer mit `sysadmin`-Berechtigungen ausgeführt werden, d. h. den gleichen Berechtigungen, die auch zum Erstellen eines UCP erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="656a5-122">This procedure must be run by a user with `sysadmin` permissions; the same permissions required to create a UCP.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="656a5-123">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="656a5-123">Using Transact-SQL</span></span>  
  
#### <a name="to-remove-a-utility-control-point"></a><span data-ttu-id="656a5-124">So entfernen Sie einen Steuerungspunkt für das Hilfsprogramm</span><span class="sxs-lookup"><span data-stu-id="656a5-124">To remove a Utility Control Point</span></span>  
  
1.  <span data-ttu-id="656a5-125">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="656a5-125">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="656a5-126">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="656a5-126">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="656a5-127">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="656a5-127">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
```  
EXEC msdb.dbo.sp_sysutility_ucp_remove;  
```  
  
## <a name="see-also"></a><span data-ttu-id="656a5-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="656a5-128">See Also</span></span>  
 <span data-ttu-id="656a5-129">[Funktionen und Tasks im SQL Server-Hilfsprogramm](sql-server-utility-features-and-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="656a5-129">[SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md) </span></span>  
 <span data-ttu-id="656a5-130">[Verwenden des Hilfsprogramm-Explorers zum Verwalten des SQL Server-Hilfsprogramms](use-utility-explorer-to-manage-the-sql-server-utility.md) </span><span class="sxs-lookup"><span data-stu-id="656a5-130">[Use Utility Explorer to Manage the SQL Server Utility](use-utility-explorer-to-manage-the-sql-server-utility.md) </span></span>  
 [<span data-ttu-id="656a5-131">Problembehandlung beim SQL Server-Hilfsprogramm</span><span class="sxs-lookup"><span data-stu-id="656a5-131">Troubleshoot the SQL Server Utility</span></span>](../../database-engine/troubleshoot-the-sql-server-utility.md)  
  
  
