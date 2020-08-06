---
title: Anzeigen von Fremdschlüsseleigenschaften | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- foreign keys [SQL Server], attributes
- displaying foreign keys attributes
- viewing foreign keys attributes
ms.assetid: b0e57cb7-9b26-4b96-b76a-1f59f5f498c5
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5860a0cf26b983d75bab86862ee1e5fdd7737712
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609038"
---
# <a name="view-foreign-key-properties"></a><span data-ttu-id="aee01-102">Anzeigen von Fremdschlüsseleigenschaften</span><span class="sxs-lookup"><span data-stu-id="aee01-102">View Foreign Key Properties</span></span>
  <span data-ttu-id="aee01-103">Sie können die Fremdschlüsselattribute einer Beziehung in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]anzeigen.</span><span class="sxs-lookup"><span data-stu-id="aee01-103">You can view the foreign key attributes of a relationship in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="aee01-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="aee01-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="aee01-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="aee01-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="aee01-106">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="aee01-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="aee01-107">**So zeigen Sie die Fremdschlüsselattribute einer bestimmten Tabelle an mit:**</span><span class="sxs-lookup"><span data-stu-id="aee01-107">**To view the foreign key attributes of a specific table, using:**</span></span>  
  
     [<span data-ttu-id="aee01-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="aee01-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="aee01-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="aee01-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="aee01-110">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="aee01-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="aee01-111">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="aee01-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="aee01-112">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="aee01-112">Permissions</span></span>  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] <span data-ttu-id="aee01-113">Weitere Informationen finden Sie unter [Metadata Visibility Configuration](../security/metadata-visibility-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="aee01-113">For more information, see [Metadata Visibility Configuration](../security/metadata-visibility-configuration.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="aee01-114">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="aee01-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-foreign-key-attributes-of-a-relationship-in-a-specific-table"></a><span data-ttu-id="aee01-115">So zeigen Sie die Fremdschlüsselattribute einer Beziehung in einer bestimmten Tabelle an</span><span class="sxs-lookup"><span data-stu-id="aee01-115">To view the foreign key attributes of a relationship in a specific table</span></span>  
  
1.  <span data-ttu-id="aee01-116">Öffnen Sie den Tabellen-Designer für die Tabelle, in der der anzuzeigende Fremdschlüssel enthalten ist. Klicken Sie mit der rechten Maustaste in den Tabellen-Designer, und wählen Sie im Kontextmenü **Beziehungen** aus.</span><span class="sxs-lookup"><span data-stu-id="aee01-116">Open the Table Designer for the table containing the foreign key you want to view, right-click in the Table Designer, and choose **Relationships** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="aee01-117">Wählen Sie im Dialogfeld **Fremdschlüsselbeziehungen** diejenige Beziehung aus, deren Eigenschaften Sie betrachten möchten.</span><span class="sxs-lookup"><span data-stu-id="aee01-117">In the **Foreign Key Relationships** dialog box, select the relationship with properties you want to view.</span></span>  
  
 <span data-ttu-id="aee01-118">Wenn die Fremdschlüsselspalten mit einem Primärschlüssel verknüpft sind, werden die Primärschlüsselspalten in **Tabellen-Designer** durch ein Primärschlüsselsymbol gekennzeichnet, das im Zeilenselektor angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="aee01-118">If the foreign key columns are related to a primary key, the primary key columns are identified in **Table Designer** by a primary key symbol in the row selector.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="aee01-119">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="aee01-119">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-foreign-key-attributes-of-a-relationship-in-a-specific-table"></a><span data-ttu-id="aee01-120">So zeigen Sie die Fremdschlüsselattribute einer Beziehung in einer bestimmten Tabelle an</span><span class="sxs-lookup"><span data-stu-id="aee01-120">To view the foreign key attributes of a relationship in a specific table</span></span>  
  
1.  <span data-ttu-id="aee01-121">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="aee01-121">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="aee01-122">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="aee01-122">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="aee01-123">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="aee01-123">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="aee01-124">Im Beispiel werden alle Fremdschlüssel und ihre Eigenschaften für die Tabelle `HumanResources.Employee` in der Beispieldatenbank zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="aee01-124">The example returns all foreign keys and their properties for the table `HumanResources.Employee` in the sample database.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT   
        f.name AS foreign_key_name  
       ,OBJECT_NAME(f.parent_object_id) AS table_name  
       ,COL_NAME(fc.parent_object_id, fc.parent_column_id) AS constraint_column_name  
       ,OBJECT_NAME (f.referenced_object_id) AS referenced_object  
       ,COL_NAME(fc.referenced_object_id, fc.referenced_column_id) AS referenced_column_name  
       ,is_disabled  
       ,delete_referential_action_desc  
       ,update_referential_action_desc  
    FROM sys.foreign_keys AS f  
    INNER JOIN sys.foreign_key_columns AS fc   
       ON f.object_id = fc.constraint_object_id   
    WHERE f.parent_object_id = OBJECT_ID('HumanResources.Employee');  
    ```  
  
 <span data-ttu-id="aee01-125">Weitere Informationen finden Sie unter [sys.foreign_keys &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-foreign-keys-transact-sql) und [sys.foreign_key_columns &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-foreign-key-columns-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="aee01-125">For more information, see [sys.foreign_keys &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-foreign-keys-transact-sql) and [sys.foreign_key_columns &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-foreign-key-columns-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
