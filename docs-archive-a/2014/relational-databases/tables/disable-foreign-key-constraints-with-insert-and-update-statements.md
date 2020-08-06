---
title: Deaktivieren von Fremdschlüsseleinschränkungen mit INSERT- und UPDATE-Anweisungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- constraints [SQL Server], foreign keys
- foreign keys [SQL Server], disabling constraints
- disabling constraints
- UPDATE statement [SQL Server], foreign key constraints
- INSERT statement [SQL Server], foreign key constraints
ms.assetid: 029168d7-085e-4b13-9b86-5644b67c6e24
author: stevestein
ms.author: sstein
ms.openlocfilehash: e91328f4f12f2a0a27f397c7bd95390a505f3998
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616961"
---
# <a name="disable-foreign-key-constraints-with-insert-and-update-statements"></a><span data-ttu-id="8ae87-102">Deaktivieren von Fremdschlüsseleinschränkungen mit INSERT- und UPDATE-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="8ae87-102">Disable Foreign Key Constraints with INSERT and UPDATE Statements</span></span>
  <span data-ttu-id="8ae87-103">Sie können eine Fremdschlüsseleinschränkung während der Durchführung von INSERT- und UPDATE-Transaktionen in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="8ae87-103">You can disable a foreign key constraint during INSERT and UPDATE transactions in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="8ae87-104">Verwenden Sie diese Option, wenn Sie wissen, dass neue Daten gegen die vorhandene Einschränkung verstoßen, oder wenn die Einschränkung nur für die bereits in der Datenbank vorhandenen Daten gilt.</span><span class="sxs-lookup"><span data-stu-id="8ae87-104">Use this option if you know that new data will violate the existing constraint or if the constraint applies only to the data already in the database.</span></span>  
  
 <span data-ttu-id="8ae87-105">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="8ae87-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8ae87-106">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="8ae87-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8ae87-107">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="8ae87-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="8ae87-108">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="8ae87-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8ae87-109">**So deaktivieren Sie eine Fremdschlüsseleinschränkung für INSERT- und UPDATE-Anweisungen mit:**</span><span class="sxs-lookup"><span data-stu-id="8ae87-109">**To disable a foreign key constraint for INSERT and UPDATE statements, using:**</span></span>  
  
     [<span data-ttu-id="8ae87-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8ae87-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="8ae87-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8ae87-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8ae87-112">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="8ae87-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="8ae87-113">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="8ae87-113">Limitations and Restrictions</span></span>  
 <span data-ttu-id="8ae87-114">Sobald diese Einschränkungen deaktiviert worden sind, wird die Spalte bei Einfügungen oder Updates nicht mehr bezüglich der Einschränkungsbedingungen überprüft.</span><span class="sxs-lookup"><span data-stu-id="8ae87-114">After you disable these constraints, future inserts or updates to the column will not be validated against the constraint conditions.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8ae87-115">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="8ae87-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8ae87-116">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="8ae87-116">Permissions</span></span>  
 <span data-ttu-id="8ae87-117">Erfordert die ALTER-Berechtigung für die Tabelle.</span><span class="sxs-lookup"><span data-stu-id="8ae87-117">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8ae87-118">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8ae87-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-a-foreign-key-constraint-for-insert-and-update-statements"></a><span data-ttu-id="8ae87-119">So deaktivieren Sie eine Fremdschlüsseleinschränkung für die Anweisungen INSERT und UPDATE</span><span class="sxs-lookup"><span data-stu-id="8ae87-119">To disable a foreign key constraint for INSERT and UPDATE statements</span></span>  
  
1.  <span data-ttu-id="8ae87-120">Erweitern Sie im **Objekt-Explorer**die Tabelle mit der Einschränkung, und erweitern Sie dann den Ordner **Schlüssel** .</span><span class="sxs-lookup"><span data-stu-id="8ae87-120">In **Object Explorer**, expand the table with the constraint and then expand the **Keys** folder.</span></span>  
  
2.  <span data-ttu-id="8ae87-121">Klicken Sie mit der rechten Maustaste auf die Einschränkung, und wählen Sie anschließend **Ändern**aus.</span><span class="sxs-lookup"><span data-stu-id="8ae87-121">Right-click the constraint and select **Modify**.</span></span>  
  
3.  <span data-ttu-id="8ae87-122">Klicken Sie im Raster unter dem **Tabellen-Designer**auf **Fremdschlüsseleinschränkung erzwingen** , und wählen Sie im Dropdownmenü **Nein** aus.</span><span class="sxs-lookup"><span data-stu-id="8ae87-122">In the grid under **Table Designer**, click **Enforce Foreign Key Constraint** and select **No** from the drop-down menu.</span></span>  
  
4.  <span data-ttu-id="8ae87-123">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="8ae87-123">Click **Close**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8ae87-124">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8ae87-124">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-a-foreign-key-constraint-for-insert-and-update-statements"></a><span data-ttu-id="8ae87-125">So deaktivieren Sie eine Fremdschlüsseleinschränkung für die Anweisungen INSERT und UPDATE</span><span class="sxs-lookup"><span data-stu-id="8ae87-125">To disable a foreign key constraint for INSERT and UPDATE statements</span></span>  
  
1.  <span data-ttu-id="8ae87-126">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="8ae87-126">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8ae87-127">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="8ae87-127">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8ae87-128">Kopieren Sie die folgenden Beispiele, fügen Sie sie in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="8ae87-128">Copy and paste the following examples into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER TABLE Purchasing.PurchaseOrderHeader  
    NOCHECK CONSTRAINT FK_PurchaseOrderHeader_Employee_EmployeeID;  
    GO  
    ```  
  
 <span data-ttu-id="8ae87-129">Weitere Informationen finden Sie unter [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8ae87-129">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
