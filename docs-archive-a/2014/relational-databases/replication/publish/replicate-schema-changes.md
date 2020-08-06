---
title: Replizieren von Schemaänderungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], schema changes
- schemas [SQL Server replication], replicating changes
ms.assetid: c09007f0-9374-4f60-956b-8a87670cd043
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bec2f363cd8c4f7dea45935568a88722b19323fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618651"
---
# <a name="replicate-schema-changes"></a><span data-ttu-id="c21c2-102">Replizieren von Schemaänderungen</span><span class="sxs-lookup"><span data-stu-id="c21c2-102">Replicate Schema Changes</span></span>
  <span data-ttu-id="c21c2-103">In diesem Thema wird beschrieben, wie Schemaänderungen in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../../includes/tsql-md.md)]repliziert werden.</span><span class="sxs-lookup"><span data-stu-id="c21c2-103">This topic describes how to replicate schema changes in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="c21c2-104">Wenn Sie in einem veröffentlichten Artikel die folgenden Schemaänderungen vornehmen, werden diese standardmäßig an [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Abonnenten weitergegeben:</span><span class="sxs-lookup"><span data-stu-id="c21c2-104">If you make the following schema changes to a published article, they are propagated, by default, to [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Subscribers:</span></span>  
  
-   <span data-ttu-id="c21c2-105">ALTER TABLE</span><span class="sxs-lookup"><span data-stu-id="c21c2-105">ALTER TABLE</span></span>  
  
-   <span data-ttu-id="c21c2-106">ALTER VIEW</span><span class="sxs-lookup"><span data-stu-id="c21c2-106">ALTER VIEW</span></span>  
  
-   <span data-ttu-id="c21c2-107">ALTER PROCEDURE</span><span class="sxs-lookup"><span data-stu-id="c21c2-107">ALTER PROCEDURE</span></span>  
  
-   <span data-ttu-id="c21c2-108">ALTER FUNCTION</span><span class="sxs-lookup"><span data-stu-id="c21c2-108">ALTER FUNCTION</span></span>  
  
-   <span data-ttu-id="c21c2-109">ALTER TRIGGER</span><span class="sxs-lookup"><span data-stu-id="c21c2-109">ALTER TRIGGER</span></span>  
  
 <span data-ttu-id="c21c2-110">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="c21c2-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c21c2-111">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="c21c2-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c21c2-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="c21c2-112">Limitations and Restrictions</span></span>](#Restrictions)  
  
-   <span data-ttu-id="c21c2-113">**So replizieren Sie Schemaänderungen mit:**</span><span class="sxs-lookup"><span data-stu-id="c21c2-113">**To replicate schema changes, using:**</span></span>  
  
     [<span data-ttu-id="c21c2-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c21c2-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c21c2-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c21c2-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c21c2-116">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="c21c2-116">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="c21c2-117">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="c21c2-117">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="c21c2-118">Die ALTER TABLE ... Die DROP COLUMN-Anweisung wird grundsätzlich auf alle Abonnenten repliziert, deren Abonnement die Spalten enthält, die gelöscht werden, auch wenn Sie die Replikation von Schemaänderungen deaktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="c21c2-118">The ALTER TABLE ... DROP COLUMN statement is always replicated to all Subscribers whose subscription contains the columns being dropped, even if you disable the replication of schema changes.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c21c2-119">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c21c2-119">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="c21c2-120">Wenn die Schemaänderungen nicht auf eine Veröffentlichung repliziert werden sollen, deaktivieren Sie im Dialogfeld **Veröffentlichungseigenschaften – \<Publication>** die Replikation der Schemaänderungen.</span><span class="sxs-lookup"><span data-stu-id="c21c2-120">If you do not want to replicate schema changes for a publication, disable the replication of schema changes in the **Publication Properties - \<Publication>** dialog box.</span></span> <span data-ttu-id="c21c2-121">Weitere Informationen zum Zugreifen auf dieses Dialogfeld finden Sie unter [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="c21c2-121">For more information about accessing this dialog box, see [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span></span>  
  
#### <a name="to-disable-replication-of-schema-changes"></a><span data-ttu-id="c21c2-122">So deaktivieren Sie die Replikation von Schemaänderungen</span><span class="sxs-lookup"><span data-stu-id="c21c2-122">To disable replication of schema changes</span></span>  
  
1.  <span data-ttu-id="c21c2-123">Legen Sie auf der Seite **Abonnementoptionen** des Dialogfelds **Veröffentlichungseigenschaften – \<Publication>** die Eigenschaft **Schemaänderungen replizieren** auf **FALSE** fest.</span><span class="sxs-lookup"><span data-stu-id="c21c2-123">On the **Subscription Options** page of the **Publication Properties - \<Publication>** dialog box, set the value of the **Replicate schema changes** property to **False**.</span></span>  
  
2.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
     <span data-ttu-id="c21c2-124">Wenn nur bestimmte Schemaänderungen weitergegeben werden sollen, legen Sie für die Eigenschaft vor der Schemaänderung **Wahr** und danach **Falsch** fest.</span><span class="sxs-lookup"><span data-stu-id="c21c2-124">To propagate only specific schema changes, set the property to **True** before a schema change, and then set it to **False** after the change is made.</span></span> <span data-ttu-id="c21c2-125">Wenn umgekehrt die meisten Schemaänderungen weitergegeben werden sollen und nur eine bestimmte Änderung nicht repliziert werden soll, legen Sie für die Eigenschaft vor der entsprechenden Schemaänderung **Falsch** und anschließend wieder **Wahr** fest.</span><span class="sxs-lookup"><span data-stu-id="c21c2-125">Conversely, to propagate most schema changes, but not a given change, set the property to **False** before the schema change, and then set it to **True** after the change is made.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c21c2-126">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c21c2-126">Using Transact-SQL</span></span>  
 <span data-ttu-id="c21c2-127">Sie können mithilfe gespeicherter Replikationsprozeduren angeben, ob diese Schemaänderungen repliziert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c21c2-127">You can use replication stored procedures to specify whether these schema changes are replicated.</span></span> <span data-ttu-id="c21c2-128">Welche gespeicherte Prozedur Sie verwenden, hängt vom Typ der Veröffentlichung ab.</span><span class="sxs-lookup"><span data-stu-id="c21c2-128">The stored procedure that you use depends on the type of publication.</span></span>  
  
#### <a name="to-create-a-snapshot-or-transactional-publication-that-does-not-replicate-schema-changes"></a><span data-ttu-id="c21c2-129">So erstellen Sie eine Momentaufnahme- oder Transaktionsveröffentlichung, die keine Schemaänderungen repliziert</span><span class="sxs-lookup"><span data-stu-id="c21c2-129">To create a snapshot or transactional publication that does not replicate schema changes</span></span>  
  
1.  <span data-ttu-id="c21c2-130">Führen Sie auf dem Verleger für die Veröffentlichungs Datenbank [sp_addpublication &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql)aus, und geben Sie für \*\* \@ replicate_ddl\*\*den Wert **0** an.</span><span class="sxs-lookup"><span data-stu-id="c21c2-130">At the Publisher on the publication database, execute [sp_addpublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql), specifying a value of **0** for **\@replicate_ddl**.</span></span> <span data-ttu-id="c21c2-131">Weitere Informationen finden Sie unter [Create a Publication](create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="c21c2-131">For more information, see [Create a Publication](create-a-publication.md).</span></span>  
  
#### <a name="to-create-a-merge-publication-that-does-not-replicate-schema-changes"></a><span data-ttu-id="c21c2-132">So erstellen Sie eine Mergeveröffentlichung, die keine Schemaänderungen repliziert</span><span class="sxs-lookup"><span data-stu-id="c21c2-132">To create a merge publication that does not replicate schema changes</span></span>  
  
1.  <span data-ttu-id="c21c2-133">Führen Sie auf dem Verleger für die Veröffentlichungs Datenbank [sp_addmergepublication &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql)aus, und geben Sie für \*\* \@ replicate_ddl\*\*den Wert **0** an.</span><span class="sxs-lookup"><span data-stu-id="c21c2-133">At the Publisher on the publication database, execute [sp_addmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql), specifying a value of **0** for **\@replicate_ddl**.</span></span> <span data-ttu-id="c21c2-134">Weitere Informationen finden Sie unter [Create a Publication](create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="c21c2-134">For more information, see [Create a Publication](create-a-publication.md).</span></span>  
  
#### <a name="to-temporarily-disable-replicating-schema-changes-for-a-snapshot-or-transactional-publication"></a><span data-ttu-id="c21c2-135">So deaktivieren Sie vorübergehend die Replikation von Schemaänderungen in einer Momentaufnahme- oder Transaktionsveröffentlichung</span><span class="sxs-lookup"><span data-stu-id="c21c2-135">To temporarily disable replicating schema changes for a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="c21c2-136">Führen Sie für eine Veröffentlichung mit Replikation von Schema Änderungen [sp_changepublication &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql)aus, und geben Sie dabei den Wert **replicate_ddl** für die- \*\* \@ Eigenschaft\*\* und den Wert **0** für \*\* \@ value\*\*an.</span><span class="sxs-lookup"><span data-stu-id="c21c2-136">For a publication with replication of schema changes, execute [sp_changepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql), specifying a value of **replicate_ddl** for **\@property** and a value of **0** for **\@value**.</span></span>  
  
2.  <span data-ttu-id="c21c2-137">Führen Sie den DDL-Befehl für das veröffentlichte Objekt aus.</span><span class="sxs-lookup"><span data-stu-id="c21c2-137">Execute the DDL command on the published object.</span></span>  
  
3.  <span data-ttu-id="c21c2-138">Optionale Aktivieren Sie die Replikation von Schema Änderungen erneut, indem Sie [sp_changepublication &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql)ausführen, und geben Sie dabei den Wert **replicate_ddl** für die- \*\* \@ Eigenschaft\*\* und den Wert **1** für \*\* \@ value\*\*an.</span><span class="sxs-lookup"><span data-stu-id="c21c2-138">(Optional) Re-enable replicating schema changes by executing [sp_changepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql), specifying a value of **replicate_ddl** for **\@property** and a value of **1** for **\@value**.</span></span>  
  
#### <a name="to-temporarily-disable-replicating-schema-changes-for-a-merge-publication"></a><span data-ttu-id="c21c2-139">So deaktivieren Sie vorübergehend die Replikation von Schemaänderungen in einer Mergeveröffentlichung</span><span class="sxs-lookup"><span data-stu-id="c21c2-139">To temporarily disable replicating schema changes for a merge publication</span></span>  
  
1.  <span data-ttu-id="c21c2-140">Führen Sie für eine Veröffentlichung mit Replikation von Schema Änderungen [sp_changemergepublication &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql)aus, und geben Sie dabei den Wert **replicate_ddl** für die- \*\* \@ Eigenschaft\*\* und den Wert **0** für \*\* \@ value\*\*an.</span><span class="sxs-lookup"><span data-stu-id="c21c2-140">For a publication with replication of schema changes, execute [sp_changemergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql), specifying a value of **replicate_ddl** for **\@property** and a value of **0** for **\@value**.</span></span>  
  
2.  <span data-ttu-id="c21c2-141">Führen Sie den DDL-Befehl für das veröffentlichte Objekt aus.</span><span class="sxs-lookup"><span data-stu-id="c21c2-141">Execute the DDL command on the published object.</span></span>  
  
3.  <span data-ttu-id="c21c2-142">Optionale Aktivieren Sie die Replikation von Schema Änderungen erneut, indem Sie [sp_changemergepublication &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql)ausführen, und geben Sie dabei den Wert **replicate_ddl** für die- \*\* \@ Eigenschaft\*\* und den Wert **1** für \*\* \@ value\*\*an.</span><span class="sxs-lookup"><span data-stu-id="c21c2-142">(Optional) Re-enable replicating schema changes by executing [sp_changemergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql), specifying a value of **replicate_ddl** for **\@property** and a value of **1** for **\@value**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c21c2-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c21c2-143">See Also</span></span>  
 <span data-ttu-id="c21c2-144">[Vornehmen von Schemaänderungen in Veröffentlichungsdatenbanken](make-schema-changes-on-publication-databases.md) </span><span class="sxs-lookup"><span data-stu-id="c21c2-144">[Make Schema Changes on Publication Databases](make-schema-changes-on-publication-databases.md) </span></span>  
 [<span data-ttu-id="c21c2-145">Vornehmen von Schemaänderungen in Veröffentlichungsdatenbanken</span><span class="sxs-lookup"><span data-stu-id="c21c2-145">Make Schema Changes on Publication Databases</span></span>](make-schema-changes-on-publication-databases.md)  
  
  
