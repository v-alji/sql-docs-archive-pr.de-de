---
title: Ändern von Statistiken | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- statistics [SQL Server], modifying
- modifying statistics
ms.assetid: b06299ca-ed52-411a-b245-45eac4628c99
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6dd44da6d1a80050f37f08e49773f95af0e5a339
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621413"
---
# <a name="modify-statistics"></a><span data-ttu-id="b7865-102">Ändern von Statistiken</span><span class="sxs-lookup"><span data-stu-id="b7865-102">Modify Statistics</span></span>
  <span data-ttu-id="b7865-103">Sie können mit [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] oder [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] vorhandene Statistiken in [!INCLUDE[tsql](../../includes/tsql-md.md)]ändern.</span><span class="sxs-lookup"><span data-stu-id="b7865-103">You can modify existing statistics in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="b7865-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="b7865-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b7865-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="b7865-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b7865-106">Security</span><span class="sxs-lookup"><span data-stu-id="b7865-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b7865-107">**So ändern Sie Statistiken mit:**</span><span class="sxs-lookup"><span data-stu-id="b7865-107">**To modify statistics, using:**</span></span>  
  
     [<span data-ttu-id="b7865-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b7865-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b7865-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b7865-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b7865-110">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="b7865-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b7865-111">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="b7865-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b7865-112">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="b7865-112">Permissions</span></span>  
 <span data-ttu-id="b7865-113">Erfordert Folgendes:</span><span class="sxs-lookup"><span data-stu-id="b7865-113">Requires that:</span></span>  
  
-   <span data-ttu-id="b7865-114">Der Benutzer verfügt über die ALTER-Berechtigung für die Tabelle oder Sicht.</span><span class="sxs-lookup"><span data-stu-id="b7865-114">The user has ALTER permission on the table or view.</span></span>  
  
-   <span data-ttu-id="b7865-115">Der Benutzer kann Besitzer der Tabelle oder indizierten Sicht oder ein Mitglied einer der folgenden Rollen sein: feste Serverrolle **sysadmin** , feste Datenbankrolle **db_owner** oder feste Datenbankrolle **db_ddladmin** .</span><span class="sxs-lookup"><span data-stu-id="b7865-115">The user be the table or indexed view owner, or a member of one of the following roles: **sysadmin** fixed server role, **db_owner** fixed database role, or the **db_ddladmin** fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b7865-116">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b7865-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-statistics"></a><span data-ttu-id="b7865-117">So ändern Sie Statistiken</span><span class="sxs-lookup"><span data-stu-id="b7865-117">To modify statistics</span></span>  
  
1.  <span data-ttu-id="b7865-118">Klicken Sie im **Objekt-Explorer**auf das Pluszeichen, um die Datenbank zu erweitern, in der Sie eine Statistik ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="b7865-118">In **Object Explorer**, click the plus sign to expand the database in which you want to modify a statistic.</span></span>  
  
2.  <span data-ttu-id="b7865-119">Klicken Sie auf das Pluszeichen, um den Ordner **Tabellen** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="b7865-119">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="b7865-120">Klicken Sie auf das Pluszeichen, um die Tabelle zu erweitern, in der Sie die Statistik ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="b7865-120">Click the plus sign to expand the table in which you want to modify a statistic.</span></span>  
  
4.  <span data-ttu-id="b7865-121">Klicken Sie auf das Pluszeichen, um den Ordner **Statistik** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="b7865-121">Click the plus sign to expand the **Statistics** folder.</span></span>  
  
5.  <span data-ttu-id="b7865-122">Klicken Sie mit der rechten Maustaste auf das Statistikobjekt, das Sie ändern möchten, und wählen Sie **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="b7865-122">Right-click the statistics object that you wish to modify and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="b7865-123">Klicken Sie im Dialogfeld **Statistikeigenschaften –** *Name der Statistik* auf der Seite **Allgemein** auf **Hinzufügen**, **Entfernen**, **Nach oben** oder **Nach unten** oder irgendeine Kombination, um die Eigenschaften der Statistiken zu ändern.</span><span class="sxs-lookup"><span data-stu-id="b7865-123">In the **Statistics Properties -** *statistics_name* dialog box, on the **General** page, click **Add**, **Remove**, **Move Up**, or **Move Down**, or any combination, to alter the properties of the statistics.</span></span> <span data-ttu-id="b7865-124">Beachten Sie, dass sich die Position einer Spalte im Raster **Statistikspalten** erheblich auf die Nützlichkeit der Statistiken auswirken kann.</span><span class="sxs-lookup"><span data-stu-id="b7865-124">Remember that a column's location within the **Statistics Columns** grid can substantially impact the usefulness of the statistics.</span></span>  
  
7.  <span data-ttu-id="b7865-125">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b7865-125">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b7865-126">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b7865-126">Using Transact-SQL</span></span>  
 <span data-ttu-id="b7865-127">**So ändern Sie Statistiken**</span><span class="sxs-lookup"><span data-stu-id="b7865-127">**To modify statistics**</span></span>  
  
 <span data-ttu-id="b7865-128">Diese Aufgabe kann nicht mit Transact-SQL-Anweisungen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b7865-128">This task cannot be performed using Transact-SQL statements.</span></span> <span data-ttu-id="b7865-129">Um Statistiken mithilfe von Transact-SQL zu ändern, müssen Sie zuerst die vorhandene Statistik löschen und sie dann mit neuen Attributen neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b7865-129">To modify statistics using Transact-SQL, you must first delete the existing statistic and then re-create it with new attributes.</span></span>  
  
 <span data-ttu-id="b7865-130">Weitere Informationen finden Sie unter [DROP STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-statistics-transact-sql) und [CREATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-statistics-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b7865-130">For more information, see [DROP STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-statistics-transact-sql) and [CREATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-statistics-transact-sql).</span></span>  
  
  
