---
title: Löschen von Fremdschlüssel-Beziehungen | Microsoft Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- foreign keys [SQL Server], deleting
- removing foreign keys
- deleting foreign keys
ms.assetid: 9c9e9ae4-9e03-4137-acb6-b18928a0c4ca
author: stevestein
ms.author: sstein
ms.openlocfilehash: 86ae466b9fce53073bfc0645c753246023ff3269
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617874"
---
# <a name="delete-foreign-key-relationships"></a><span data-ttu-id="70e7e-102">Löschen von Primärschlüssel-Fremdschlüssel-Beziehungen</span><span class="sxs-lookup"><span data-stu-id="70e7e-102">Delete Foreign Key Relationships</span></span>
  <span data-ttu-id="70e7e-103">Sie können eine Fremdschlüsseleinschränkung in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]löschen.</span><span class="sxs-lookup"><span data-stu-id="70e7e-103">You can delete a foreign key constraint in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="70e7e-104">Beim Löschen einer Fremdschlüsseleinschränkung entfällt die Anforderung zum Erzwingen der referenziellen Integrität.</span><span class="sxs-lookup"><span data-stu-id="70e7e-104">Deleting a foreign key constraint removes the requirement to enforce referential integrity.</span></span>  
  
 <span data-ttu-id="70e7e-105">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="70e7e-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="70e7e-106">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="70e7e-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="70e7e-107">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="70e7e-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="70e7e-108">**So löschen Sie eine Fremdschlüsseleinschränkung mit:**</span><span class="sxs-lookup"><span data-stu-id="70e7e-108">**To delete a foreign key constraint, using:**</span></span>  
  
     [<span data-ttu-id="70e7e-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="70e7e-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="70e7e-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="70e7e-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="70e7e-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="70e7e-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="70e7e-112">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="70e7e-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="70e7e-113">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="70e7e-113">Permissions</span></span>  
 <span data-ttu-id="70e7e-114">Erfordert die ALTER-Berechtigung für die Tabelle.</span><span class="sxs-lookup"><span data-stu-id="70e7e-114">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="70e7e-115">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="70e7e-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-foreign-key-constraint"></a><span data-ttu-id="70e7e-116">So löschen Sie eine Fremdschlüsseleinschränkung</span><span class="sxs-lookup"><span data-stu-id="70e7e-116">To delete a foreign key constraint</span></span>  
  
1.  <span data-ttu-id="70e7e-117">Erweitern Sie im **Objekt-Explorer**die Tabelle mit der Einschränkung, und erweitern Sie dann die Option **Schlüssel**.</span><span class="sxs-lookup"><span data-stu-id="70e7e-117">In **Object Explorer**, expand the table with the constraint and then expand **Keys**.</span></span>  
  
2.  <span data-ttu-id="70e7e-118">Klicken Sie mit der rechten Maustaste auf die Einschränkung, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="70e7e-118">Right-click the constraint and then click **Delete**.</span></span>  
  
3.  <span data-ttu-id="70e7e-119">Klicken Sie im Dialogfeld **Objekt löschen** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="70e7e-119">In the **Delete Object** dialog box, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="70e7e-120">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="70e7e-120">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-foreign-key-constraint"></a><span data-ttu-id="70e7e-121">So löschen Sie eine Fremdschlüsseleinschränkung</span><span class="sxs-lookup"><span data-stu-id="70e7e-121">To delete a foreign key constraint</span></span>  
  
1.  <span data-ttu-id="70e7e-122">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="70e7e-122">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="70e7e-123">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="70e7e-123">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="70e7e-124">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="70e7e-124">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER TABLE dbo.DocExe   
    DROP CONSTRAINT FK_Column_B;   
    GO  
    ```  
  
 <span data-ttu-id="70e7e-125">Weitere Informationen finden Sie unter [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="70e7e-125">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
  
