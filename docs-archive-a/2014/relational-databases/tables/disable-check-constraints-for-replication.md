---
title: Deaktivieren von CHECK-Einschränkungen für die Replikation | Microsoft-Dokumentation
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
ms.assetid: af98fc70-24dd-4bd3-a0a3-f701dfa67b2c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 98b6ca7c3525edeffdb47f294db568d3c115b2c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607608"
---
# <a name="disable-check-constraints-for-replication"></a><span data-ttu-id="8a3b8-102">Deaktivieren von CHECK-Einschränkungen für die Replikation</span><span class="sxs-lookup"><span data-stu-id="8a3b8-102">Disable Check Constraints for Replication</span></span>
  <span data-ttu-id="8a3b8-103">CHECK-Einschränkungen können in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="8a3b8-103">You can disable check constraints in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="8a3b8-104">Sie können CHECK-Einschränkungen für die Replikation auch explizit deaktivieren. Dies ist vor allem nützlich, wenn Sie Daten aus einer früheren Version von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="8a3b8-104">You can also explicitly disable check constraints for replication, which can be useful if you are publishing data from a previous version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8a3b8-105">Wenn eine Tabelle mittels Replikation veröffentlicht wird, werden CHECK-Einschränkungen automatisch für die von Replikations-Agents ausgeführten Vorgänge deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="8a3b8-105">If a table is published using replication, check constraints are automatically disabled for operations performed by replication agents.</span></span> <span data-ttu-id="8a3b8-106">Wenn ein Replikations-Agent eine Einfügung, ein Update oder eine Löschung auf einem Abonnenten ausführt, wird die Einschränkung nicht überprüft; wenn ein Benutzer eine Einfügung, ein Update oder eine Löschung ausführt, wird die Einschränkung überprüft.</span><span class="sxs-lookup"><span data-stu-id="8a3b8-106">When a replication agent performs an insert, update, or delete at a Subscriber, the constraint is not checked; if a user performs an insert, update, or delete, the constraint is checked.</span></span> <span data-ttu-id="8a3b8-107">Die Einschränkung wird für den Replikations-Agent deaktiviert, da die Einschränkung bereits auf dem Verleger überprüft wurde, als die Daten ursprünglich eingefügt, aktualisiert oder gelöscht wurden.</span><span class="sxs-lookup"><span data-stu-id="8a3b8-107">The constraint is disabled for the replication agent because the constraint was already checked at the Publisher when the data was originally inserted, updated, or deleted.</span></span> <span data-ttu-id="8a3b8-108">Weitere Informationen finden Sie unter [Angeben von Schemaoptionen](../replication/publish/specify-schema-options.md).</span><span class="sxs-lookup"><span data-stu-id="8a3b8-108">For more information, see [Specify Schema Options](../replication/publish/specify-schema-options.md).</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8a3b8-109">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="8a3b8-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8a3b8-110">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="8a3b8-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8a3b8-111">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="8a3b8-111">Permissions</span></span>  
 <span data-ttu-id="8a3b8-112">Erfordert die ALTER-Berechtigung für die Tabelle.</span><span class="sxs-lookup"><span data-stu-id="8a3b8-112">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8a3b8-113">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8a3b8-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-a-check-constraint-for-replication"></a><span data-ttu-id="8a3b8-114">So deaktivieren Sie eine CHECK-Einschränkung für die Replikation</span><span class="sxs-lookup"><span data-stu-id="8a3b8-114">To disable a check constraint for replication</span></span>  
  
1.  <span data-ttu-id="8a3b8-115">Erweitern Sie im **Objekt-Explorer**die Tabelle mit der zu ändernden Einschränkung, und erweitern Sie dann den Ordner **Einschränkungen** .</span><span class="sxs-lookup"><span data-stu-id="8a3b8-115">In **Object Explorer**, expand the table with the check constraint you want to modify, and then expand the **Constraints** folder.</span></span>  
  
2.  <span data-ttu-id="8a3b8-116">Klicken Sie mit der rechten Maustaste auf die zu ändernde CHECK-Einschränkung, und klicken Sie dann auf **Ändern**.</span><span class="sxs-lookup"><span data-stu-id="8a3b8-116">Right-click the check constraint you wish to modify and then click **Modify**.</span></span>  
  
3.  <span data-ttu-id="8a3b8-117">Wählen Sie im Dialogfeld **Einschränkungen überprüfen** unter **Tabellen-Designer**für die Option **Für Replikation erzwingen** den Wert **Nein**aus.</span><span class="sxs-lookup"><span data-stu-id="8a3b8-117">In the **Check Constraints** dialog box, under **Table Designer**, select a value of **No** for **Enforce For Replication**.</span></span>  
  
4.  <span data-ttu-id="8a3b8-118">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="8a3b8-118">Click **Close**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8a3b8-119">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8a3b8-119">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-a-check-constraint-for-replication"></a><span data-ttu-id="8a3b8-120">So deaktivieren Sie eine CHECK-Einschränkung für die Replikation</span><span class="sxs-lookup"><span data-stu-id="8a3b8-120">To disable a check constraint for replication</span></span>  
  
1.  <span data-ttu-id="8a3b8-121">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="8a3b8-121">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8a3b8-122">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="8a3b8-122">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8a3b8-123">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="8a3b8-123">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="8a3b8-124">Im Beispiel wird eine Tabelle mit einer IDENTITY-Spalte und einer CHECK-Einschränkung für die Tabelle erstellt.</span><span class="sxs-lookup"><span data-stu-id="8a3b8-124">The example creates a table with an IDENTITY column and a CHECK constraint on the table.</span></span> <span data-ttu-id="8a3b8-125">Anschließend wird die Einschränkung gelöscht und mit der NOT FOR REPLICATION-Klausel neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="8a3b8-125">The example then drops the constraint and recreates it specifying the NOT FOR REPLICATION clause.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    CREATE TABLE dbo.doc_exd (column_a int IDENTITY (1,1)   
    CONSTRAINT exd_check CHECK (column_a > 1))   
  
    ALTER TABLE dbo.doc_exd   
    DROP CONSTRAINT exd_check;   
    GO  
    ALTER TABLE dbo.doc_exd    
    ADD CONSTRAINT exd_check CHECK NOT FOR REPLICATION (column_a > 1);  
    ```  
  
 <span data-ttu-id="8a3b8-126">Weitere Informationen finden Sie unter [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8a3b8-126">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>   
## <a name="see-also"></a><span data-ttu-id="8a3b8-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8a3b8-127">See Also</span></span>  
 [<span data-ttu-id="8a3b8-128">Angeben von Schemaoptionen</span><span class="sxs-lookup"><span data-stu-id="8a3b8-128">Specify Schema Options</span></span>](../replication/publish/specify-schema-options.md)  
  
  
