---
title: Umbenennen von Sichten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- views [SQL Server], renaming
- renaming views
ms.assetid: 5eed0488-81d2-40e8-8fdf-b0a640a591d0
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5cc76ced033a69788270c3fa9277bcca6972e080
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696681"
---
# <a name="rename-views"></a><span data-ttu-id="69c54-102">Umbenennen von Sichten</span><span class="sxs-lookup"><span data-stu-id="69c54-102">Rename Views</span></span>
  <span data-ttu-id="69c54-103">Sie können in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] eine Sicht mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]umbenennen.</span><span class="sxs-lookup"><span data-stu-id="69c54-103">You can rename a view in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="69c54-104">Wenn Sie eine Sicht umbenennen, kann es vorkommen, dass Code und Anwendungen, die von der Sicht abhängen, fehlerhaft ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="69c54-104">If you rename a view, code and applications that depend on the view may fail.</span></span> <span data-ttu-id="69c54-105">Dies schließt andere Sichten, Abfragen, gespeicherte Prozeduren, benutzerdefinierte Funktionen und Clientanwendungen ein.</span><span class="sxs-lookup"><span data-stu-id="69c54-105">These include other views, queries, stored procedures, user-defined functions, and client applications.</span></span> <span data-ttu-id="69c54-106">Beachten Sie, dass dabei ein Fehler durch Verkettung weitere Fehler nach sich ziehen kann.</span><span class="sxs-lookup"><span data-stu-id="69c54-106">Note that these failures will cascade.</span></span>  
  
 <span data-ttu-id="69c54-107">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="69c54-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="69c54-108">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="69c54-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="69c54-109">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="69c54-109">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="69c54-110">Security</span><span class="sxs-lookup"><span data-stu-id="69c54-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="69c54-111">**So benennen Sie eine Sicht um mit:**</span><span class="sxs-lookup"><span data-stu-id="69c54-111">**To rename a view, using:**</span></span>  
  
     [<span data-ttu-id="69c54-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="69c54-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="69c54-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="69c54-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="69c54-114">**Nachverfolgung:**  [Nach dem Umbenennen einer Ansicht](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="69c54-114">**Follow Up:**  [After renaming a view](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="69c54-115">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="69c54-115">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="69c54-116">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="69c54-116">Prerequisites</span></span>  
 <span data-ttu-id="69c54-117">Rufen Sie eine Liste aller Abhängigkeiten der Sicht ab.</span><span class="sxs-lookup"><span data-stu-id="69c54-117">Obtain a list of all dependencies on the view.</span></span> <span data-ttu-id="69c54-118">Für alle Objekte, Skripts oder Anwendungen, die auf die Sicht verweisen, muss der neue Name der Sicht festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="69c54-118">Any objects, scripts or applications that reference the view must be modified to reflect the new name of the view.</span></span> <span data-ttu-id="69c54-119">Weitere Informationen finden Sie unter [Get Information About a View](get-information-about-a-view.md).</span><span class="sxs-lookup"><span data-stu-id="69c54-119">For more information, see [Get Information About a View](get-information-about-a-view.md).</span></span> <span data-ttu-id="69c54-120">Es ist ratsam, die Sicht zu verwerfen und unter einem neuen Namen neu zu erstellen, anstatt die Sicht umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="69c54-120">We recommend that you drop the view and recreate it with a new name instead of renaming the view.</span></span> <span data-ttu-id="69c54-121">Indem Sie die Sicht neu erstellen, aktualisieren Sie die Abhängigkeitsinformationen für die Objekte, auf die in der Sicht verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="69c54-121">By recreating the view, you update the dependency information for the objects that are referenced in the view.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="69c54-122">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="69c54-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="69c54-123">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="69c54-123">Permissions</span></span>  
 <span data-ttu-id="69c54-124">Erfordert die ALTER-Berechtigung für SCHEMA oder die CONTROL-Berechtigung für OBJECT sowie die CREATE VIEW-Berechtigung in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="69c54-124">Requires ALTER permission on SCHEMA or CONTROL permission on OBJECT is required, and CREATE VIEW permission in the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="69c54-125">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="69c54-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rename-a-view"></a><span data-ttu-id="69c54-126">So benennen Sie eine Sicht um</span><span class="sxs-lookup"><span data-stu-id="69c54-126">To rename a view</span></span>  
  
1.  <span data-ttu-id="69c54-127">Erweitern Sie im **Objekt-Explorer**die Datenbank mit der Sicht, die Sie umbenennen möchten, und erweitern Sie dann den Ordner **Sicht** .</span><span class="sxs-lookup"><span data-stu-id="69c54-127">In **Object Explorer**, expand the database that contains the view you wish to rename and then expand the **View** folder.</span></span>  
  
2.  <span data-ttu-id="69c54-128">Klicken Sie mit der rechten Maustaste auf die Sicht, die Sie umbenennen möchten, und wählen Sie die Option **Umbenennen**.</span><span class="sxs-lookup"><span data-stu-id="69c54-128">Right-click the view you wish to rename and select **Rename**.</span></span>  
  
3.  <span data-ttu-id="69c54-129">Geben Sie den neuen Namen der Ansicht ein.</span><span class="sxs-lookup"><span data-stu-id="69c54-129">Enter the view's new name.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="69c54-130">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="69c54-130">Using Transact-SQL</span></span>  
 <span data-ttu-id="69c54-131">**So benennen Sie eine Sicht um**</span><span class="sxs-lookup"><span data-stu-id="69c54-131">**To rename a view**</span></span>  
  
 <span data-ttu-id="69c54-132">Sie können den Namen der Sicht zwar mit **sp_rename** ändern, aber es wird empfohlen, die vorhandene Sicht zu löschen und dann unter einem neuen Namen neu zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="69c54-132">While you can use **sp_rename** to change the name of the view, we recommend that you delete the existing view and then re-create it with the new name.</span></span>  
  
 <span data-ttu-id="69c54-133">Weitere Informationen finden Sie unter [CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql) und [DROP VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-view-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="69c54-133">For more information, see [CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql) and [DROP VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-view-transact-sql).</span></span>  
  
##  <a name="follow-up-after-renaming-a-view"></a><a name="FollowUp"></a><span data-ttu-id="69c54-134">Nächster Schritt: Nach dem Umbenennen einer Ansicht</span><span class="sxs-lookup"><span data-stu-id="69c54-134">Follow Up: After Renaming a View</span></span>  
 <span data-ttu-id="69c54-135">Stellen Sie sicher, dass alle Objekte, Skripts und Anwendungen, die auf den alten Namen der Ansicht verweisen, jetzt den neuen Namen verwenden.</span><span class="sxs-lookup"><span data-stu-id="69c54-135">Ensure that all objects, scripts, and applications that reference the view's old name now use the new name.</span></span>  
  
  
