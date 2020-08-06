---
title: Eine Warnung bearbeiten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, alerts
- alerts [SQL Server], modifying
- modifying alerts
ms.assetid: f518e528-cc8f-446a-b37d-98505b86e430
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1eae606b3c2ca4c18d088e650e774986d4e31387
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618995"
---
# <a name="edit-an-alert"></a><span data-ttu-id="5807a-102">Edit an Alert</span><span class="sxs-lookup"><span data-stu-id="5807a-102">Edit an Alert</span></span>
  <span data-ttu-id="5807a-103">In diesem Thema wird beschrieben, wie Sie eine- [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent-Warnung in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von oder bearbeiten können [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5807a-103">This topic describes how to edit a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alert in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="5807a-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="5807a-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5807a-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="5807a-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5807a-106">Security</span><span class="sxs-lookup"><span data-stu-id="5807a-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5807a-107">**So bearbeiten Sie eine Warnung mit**</span><span class="sxs-lookup"><span data-stu-id="5807a-107">**To edit an alert, using:**</span></span>  
  
     [<span data-ttu-id="5807a-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5807a-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5807a-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5807a-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5807a-110">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="5807a-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5807a-111">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="5807a-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5807a-112">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="5807a-112">Permissions</span></span>  
 <span data-ttu-id="5807a-113">Standardmäßig können nur Mitglieder der festen Serverrolle **sysadmin** Information in einer Warnung bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="5807a-113">By default, members of the **sysadmin** fixed server role can edit information in an alert.</span></span> <span data-ttu-id="5807a-114">Andere Benutzer müssen Mitglieder der festen Datenbankrolle **SQLAgentOperatorRole** in der **msdb** -Datenbank sein.</span><span class="sxs-lookup"><span data-stu-id="5807a-114">Other users must be granted the **SQLAgentOperatorRole** fixed database role in the **msdb** database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5807a-115">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5807a-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-edit-an-alert"></a><span data-ttu-id="5807a-116">So bearbeiten Sie eine Warnung</span><span class="sxs-lookup"><span data-stu-id="5807a-116">To edit an alert</span></span>  
  
1.  <span data-ttu-id="5807a-117">Klicken Sie im **Objekt-Explorer** auf das Pluszeichen, um den Server zu erweitern, der die Warnung enthält, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="5807a-117">In **Object Explorer,** click the plus sign to expand the server containing the alert you want to edit.</span></span>  
  
2.  <span data-ttu-id="5807a-118">Klicken Sie auf das Pluszeichen, um **SQL Server-Agent**zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="5807a-118">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="5807a-119">Klicken Sie auf das Pluszeichen, um den Ordner **Warnungen** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="5807a-119">Click the plus sign to expand the **Alerts** folder.</span></span>  
  
4.  <span data-ttu-id="5807a-120">Klicken Sie mit der rechten Maustaste auf die Warnung, die Sie bearbeiten möchten, und wählen Sie dann **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="5807a-120">Right-click the alert you want to edit and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="5807a-121">Aktualisieren Sie die Warnungseigenschaften auf den Seiten **Allgemein**, **Antwort**und **Optionen** .</span><span class="sxs-lookup"><span data-stu-id="5807a-121">Update the alert properties on the **General**, **Response**, and **Options** pages.</span></span>  
  
6.  <span data-ttu-id="5807a-122">Wenn Sie fertig sind, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5807a-122">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5807a-123">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5807a-123">Using Transact-SQL</span></span>  
  
#### <a name="to-edit-an-alert"></a><span data-ttu-id="5807a-124">So bearbeiten Sie eine Warnung</span><span class="sxs-lookup"><span data-stu-id="5807a-124">To edit an alert</span></span>  
  
1.  <span data-ttu-id="5807a-125">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="5807a-125">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5807a-126">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="5807a-126">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5807a-127">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="5807a-127">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- changes the enabled setting of Test Alert to 0  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_update_alert  
        @name = N'Test Alert',  
        @enabled = 0 ;  
    GO  
    ```  
  
 <span data-ttu-id="5807a-128">Weitere Informationen finden Sie unter [sp_update_alert &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-update-alert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5807a-128">For more information, see [sp_update_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-alert-transact-sql).</span></span>  
  
  
