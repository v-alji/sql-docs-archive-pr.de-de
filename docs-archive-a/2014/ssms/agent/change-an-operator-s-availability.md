---
title: Ändern der Verfügbarkeit eines Operators | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, operators
- canceling operators
- reactivating operators
- removing operators
- deleting operators
- available operators [SQL Server]
- dropping operators
- jobs [SQL Server Agent], operators
- notifications [SQL Server], job status
- disabling operators
- operators (users) [Database Engine], changing availability with Management Studio
ms.assetid: 10d58b92-b67b-47e2-af9c-9f9fd6968bba
author: stevestein
ms.author: sstein
ms.openlocfilehash: fb369ea6a2d1edf1ed8f4377b627fb1ba7339a03
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622388"
---
# <a name="change-an-operator39s-availability"></a><span data-ttu-id="7ad91-102">Ändern der Verfügbarkeit eines Operators</span><span class="sxs-lookup"><span data-stu-id="7ad91-102">Change an Operator&#39;s Availability</span></span>
  <span data-ttu-id="7ad91-103">In diesem Thema wird beschrieben, wie der Zeitplan für den Empfang von Warnmeldungen für einen Operator in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]geändert wird.</span><span class="sxs-lookup"><span data-stu-id="7ad91-103">This topic describes how to change an operator's schedule for receiving alert notifications in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="7ad91-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="7ad91-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="7ad91-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="7ad91-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7ad91-106">Security</span><span class="sxs-lookup"><span data-stu-id="7ad91-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7ad91-107">**So ändern Sie die Verfügbarkeit eines Operators mit**</span><span class="sxs-lookup"><span data-stu-id="7ad91-107">**To change an operator's availability, using:**</span></span>  
  
     [<span data-ttu-id="7ad91-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7ad91-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="7ad91-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7ad91-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7ad91-110">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="7ad91-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7ad91-111">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="7ad91-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7ad91-112">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="7ad91-112">Permissions</span></span>  
 <span data-ttu-id="7ad91-113">Nur Mitglieder der festen Serverrolle **sysadmin** können Operatoren bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="7ad91-113">Only members of the **sysadmin** fixed server role can edit operators.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7ad91-114">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7ad91-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-change-an-operators-availability"></a><span data-ttu-id="7ad91-115">So ändern Sie die Verfügbarkeit eines Operators</span><span class="sxs-lookup"><span data-stu-id="7ad91-115">To change an operator's availability</span></span>  
  
1.  <span data-ttu-id="7ad91-116">Klicken Sie im **Objekt-Explorer**auf das Pluszeichen, um den Server zu erweitern, der den Operator enthält, auf dem Sie die Indizes aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="7ad91-116">In **Object Explorer**, click the plus sign to expand server that contains the operator that you want to enable or disable.</span></span>  
  
2.  <span data-ttu-id="7ad91-117">Klicken Sie auf das Pluszeichen, um **SQL Server-Agent**zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="7ad91-117">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="7ad91-118">Klicken Sie auf das Pluszeichen, um den Ordner **Operatoren** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="7ad91-118">Click the plus sign to expand the **Operators** folder.</span></span>  
  
4.  <span data-ttu-id="7ad91-119">Klicken Sie mit der rechten Maustaste auf den Operator, den Sie aktivieren oder deaktivieren möchten, wählen Sie **Eigenschaften**aus, und klicken Sie anschließend auf die Registerkarte **Allgemein** .</span><span class="sxs-lookup"><span data-stu-id="7ad91-119">Right-click the operator that you want to enable or disable and select **Properties**, then click the **General** tab.</span></span>  
  
5.  <span data-ttu-id="7ad91-120">Aktivieren bzw. deaktivieren Sie im Dialogfeld _operator_name_**Eigenschaften** das Kontrollkästchen **aktiviert** .</span><span class="sxs-lookup"><span data-stu-id="7ad91-120">In the _operator_name_**Properties** dialog box, select or clear the **Enabled** check box.</span></span>  
  
6.  <span data-ttu-id="7ad91-121">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="7ad91-121">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7ad91-122">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7ad91-122">Using Transact-SQL</span></span>  
  
#### <a name="to-change-an-operators-availability"></a><span data-ttu-id="7ad91-123">So ändern Sie die Verfügbarkeit eines Operators</span><span class="sxs-lookup"><span data-stu-id="7ad91-123">To change an operator's availability</span></span>  
  
1.  <span data-ttu-id="7ad91-124">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="7ad91-124">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7ad91-125">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="7ad91-125">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7ad91-126">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="7ad91-126">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- disables the 'Fran??ois Ajenstat' operator  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_update_operator   
        @name = N'Fran??ois Ajenstat',  
        @enabled = 0;  
    GO  
    ```  
  
 <span data-ttu-id="7ad91-127">Weitere Informationen finden Sie unter [sp_update_operator &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-update-operator-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7ad91-127">For more information, see [sp_update_operator &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-operator-transact-sql).</span></span>  
  
  
