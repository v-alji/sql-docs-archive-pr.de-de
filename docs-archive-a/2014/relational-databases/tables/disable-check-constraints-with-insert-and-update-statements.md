---
title: Deaktivieren von CHECK-Einschränkungen mit den Anweisungen INSERT und UPDATE | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- CHECK constraints, disabling
- constraints [SQL Server], disabling
- disabling constraints
- constraints [SQL Server], check
ms.assetid: c7287ad1-50d2-4e80-bc0c-b5570f7e5f69
author: stevestein
ms.author: sstein
ms.openlocfilehash: 780a2c1bfd9f21c71367ad61f200ec19ab44a608
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617867"
---
# <a name="disable-check-constraints-with-insert-and-update-statements"></a><span data-ttu-id="3a01d-102">Deaktivieren von CHECK-Einschränkungen mit den Anweisungen INSERT und UPDATE</span><span class="sxs-lookup"><span data-stu-id="3a01d-102">Disable Check Constraints with INSERT and UPDATE Statements</span></span>
  <span data-ttu-id="3a01d-103">Sie können mit [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] oder [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] eine CHECK-Einschränkung für INSERT- und UPDATE-Transaktionen in [!INCLUDE[tsql](../../includes/tsql-md.md)]deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="3a01d-103">You can disable a check constraint for INSERT and UPDATE transactions in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="3a01d-104">Sobald die CHECK-Einschränkungen deaktiviert worden sind, wird die Spalte bei Einfügungen oder Aktualisierungen nicht mehr bezüglich der Einschränkungsbedingungen überprüft.</span><span class="sxs-lookup"><span data-stu-id="3a01d-104">After you disable the check constraints, future inserts or updates to the column will not be validated against the constraint conditions.</span></span> <span data-ttu-id="3a01d-105">Verwenden Sie diese Option, wenn Sie wissen, dass neue Daten gegen die vorhandene Einschränkung verstoßen, oder wenn die Einschränkung nur für die bereits in der Datenbank vorhandenen Daten gilt.</span><span class="sxs-lookup"><span data-stu-id="3a01d-105">Use this option if you know that new data will violate the existing constraint or if the constraint applies only to the data already in the database.</span></span>  
  
 <span data-ttu-id="3a01d-106">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="3a01d-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="3a01d-107">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="3a01d-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="3a01d-108">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="3a01d-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="3a01d-109">**So deaktivieren Sie eine CHECK-Einschränkung für INSERT- und UPDATE-Anweisungen mit:**</span><span class="sxs-lookup"><span data-stu-id="3a01d-109">**To disable a check constraint for INSERT and UPDATE statements, using:**</span></span>  
  
     [<span data-ttu-id="3a01d-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3a01d-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="3a01d-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3a01d-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3a01d-112">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="3a01d-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3a01d-113">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="3a01d-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3a01d-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="3a01d-114">Permissions</span></span>  
 <span data-ttu-id="3a01d-115">Erfordert die ALTER-Berechtigung für die Tabelle.</span><span class="sxs-lookup"><span data-stu-id="3a01d-115">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="3a01d-116">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3a01d-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-a-check-constraint-for-insert-and-update-statements"></a><span data-ttu-id="3a01d-117">So deaktivieren Sie eine CHECK-Einschränkung für INSERT- und UPDATE-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="3a01d-117">To disable a check constraint for INSERT and UPDATE statements</span></span>  
  
1.  <span data-ttu-id="3a01d-118">Erweitern Sie im **Objekt-Explorer**die Tabelle mit der Einschränkung, und erweitern Sie dann den Ordner **Einschränkungen** .</span><span class="sxs-lookup"><span data-stu-id="3a01d-118">In **Object Explorer**, expand the table with the constraint and then expand the **Constraints** folder.</span></span>  
  
2.  <span data-ttu-id="3a01d-119">Klicken Sie mit der rechten Maustaste auf die Einschränkung, und wählen Sie anschließend **Ändern**aus.</span><span class="sxs-lookup"><span data-stu-id="3a01d-119">Right-click the constraint and select **Modify**.</span></span>  
  
3.  <span data-ttu-id="3a01d-120">Klicken Sie im Raster unter dem **Tabellen-Designer**auf **Für INSERTs und UPDATEs erzwingen** , und wählen Sie im Dropdownmenü **Nein** aus.</span><span class="sxs-lookup"><span data-stu-id="3a01d-120">In the grid under **Table Designer**, click **Enforce For INSERTs And UPDATEs** and select **No** from the drop-down menu.</span></span>  
  
4.  <span data-ttu-id="3a01d-121">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="3a01d-121">Click **Close**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="3a01d-122">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3a01d-122">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-a-check-constraint-for-insert-and-update-statements"></a><span data-ttu-id="3a01d-123">So deaktivieren Sie eine CHECK-Einschränkung für INSERT- und UPDATE-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="3a01d-123">To disable a check constraint for INSERT and UPDATE statements</span></span>  
  
1.  <span data-ttu-id="3a01d-124">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="3a01d-124">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3a01d-125">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="3a01d-125">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3a01d-126">Kopieren Sie die folgenden Beispiele, fügen Sie sie in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="3a01d-126">Copy and paste the following examples into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER TABLE Purchasing.PurchaseOrderHeader  
    NOCHECK CONSTRAINT CK_PurchaseOrderHeader_Freight;   
    GO  
    ```  
  
 <span data-ttu-id="3a01d-127">Weitere Informationen finden Sie unter [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3a01d-127">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
