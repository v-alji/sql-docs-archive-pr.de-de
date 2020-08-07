---
title: Deaktivieren oder erneutes Aktivieren einer Warnung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, alerts
- alerts [SQL Server], reactivating
- deleting alerts
- canceling alerts
- dropping alerts
- disabling alerts
- alerts [SQL Server], disabling
- reactivating alerts
- removing alerts
ms.assetid: 4cb37dc6-1134-405d-8590-58b44dcf63b2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3eec4ea7288f4847c0e9b861d80f23eb9c9ddba8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719420"
---
# <a name="disable-or-reactivate-an-alert"></a><span data-ttu-id="a586d-102">Disable or Reactivate an Alert</span><span class="sxs-lookup"><span data-stu-id="a586d-102">Disable or Reactivate an Alert</span></span>
  <span data-ttu-id="a586d-103">In diesem Thema wird beschrieben, wie Sie eine- [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent-Warnung in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)] deaktivieren oder erneut aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a586d-103">This topic describes how to disable or reactivate a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alert in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="a586d-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="a586d-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a586d-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="a586d-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a586d-106">Security</span><span class="sxs-lookup"><span data-stu-id="a586d-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a586d-107">**So deaktivieren oder aktivieren eine Warnung erneut mit**</span><span class="sxs-lookup"><span data-stu-id="a586d-107">**To disable or reactivate an alert, using:**</span></span>  
  
     [<span data-ttu-id="a586d-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a586d-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a586d-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a586d-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a586d-110">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="a586d-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a586d-111">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="a586d-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a586d-112">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="a586d-112">Permissions</span></span>  
 <span data-ttu-id="a586d-113">Standardmäßig können nur Mitglieder der festen Serverrolle **sysadmin** Information in einer Warnung bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="a586d-113">By default, members of the **sysadmin** fixed server role can edit information in an alert.</span></span> <span data-ttu-id="a586d-114">Andere Benutzer müssen Mitglieder der festen Datenbankrolle **SQLAgentOperatorRole** in der **msdb** -Datenbank sein.</span><span class="sxs-lookup"><span data-stu-id="a586d-114">Other users must be granted the **SQLAgentOperatorRole** fixed database role in the **msdb** database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a586d-115">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a586d-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-or-reactivate-an-alert"></a><span data-ttu-id="a586d-116">So deaktivieren oder reaktivieren Sie eine Warnung</span><span class="sxs-lookup"><span data-stu-id="a586d-116">To disable or reactivate an alert</span></span>  
  
1.  <span data-ttu-id="a586d-117">Klicken Sie im **Objekt-Explorer** auf das Pluszeichen, um den Server zu erweitern, der die Warnung enthält, die Sie deaktivieren oder erneut aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="a586d-117">In **Object Explorer**, click the plus sign to expand server that contains the alert you wish to disable or reactivate.</span></span>  
  
2.  <span data-ttu-id="a586d-118">Klicken Sie auf das Pluszeichen, um **SQL Server-Agent**zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="a586d-118">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="a586d-119">Klicken Sie auf das Pluszeichen, um den Ordner **Warnungen** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="a586d-119">Click the plus sign to expand the **Alerts** folder.</span></span>  
  
4.  <span data-ttu-id="a586d-120">Klicken Sie mit der rechten Maustaste auf die Warnung, die Sie aktivieren möchten, und wählen Sie **Aktivieren** aus. Klicken Sie demgegenüber mit der rechten Maustaste auf die Warnung, die Sie deaktivieren möchten, und wählen Sie **Deaktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="a586d-120">Right-click the alert you wish to enable and select **Enable** To disable an alert, right-click the alert you want to disable and select **Disable**.</span></span>  
  
5.  <span data-ttu-id="a586d-121">Die Dialogfelder **Warnungen deaktivieren** oder **Warnungen aktivieren** werden angezeigt. Außerdem wird der Status des Vorgangs angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a586d-121">The **Disable Alert** or **Enable Alert** dialog box displays showing the status of the process.</span></span> <span data-ttu-id="a586d-122">Wenn Sie fertig sind, klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="a586d-122">When finished, click **Close**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a586d-123">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a586d-123">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-or-reactivate-an-alert"></a><span data-ttu-id="a586d-124">So deaktivieren oder reaktivieren Sie eine Warnung</span><span class="sxs-lookup"><span data-stu-id="a586d-124">To disable or reactivate an alert</span></span>  
  
1.  <span data-ttu-id="a586d-125">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="a586d-125">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a586d-126">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="a586d-126">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a586d-127">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="a586d-127">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- changes the enabled setting of Test Alert to 0  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_update_alert  
        @name = N'Test Alert',  
        @enabled = 0 ;  
    GO  
    ```  
  
 <span data-ttu-id="a586d-128">Weitere Informationen finden Sie unter [sp_update_alert &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-update-alert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a586d-128">For more information, see [sp_update_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-alert-transact-sql).</span></span>  
  
  
