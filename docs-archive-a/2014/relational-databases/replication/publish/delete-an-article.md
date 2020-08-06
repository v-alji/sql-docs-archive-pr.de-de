---
title: Löschen eines Artikels | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- articles [SQL Server replication], dropping
- sp_droparticle
- sp_dropmergearticle
- deleting articles
- removing articles
- dropping articles
ms.assetid: 185b58fc-38c0-4abe-822e-6ec20066c863
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 082f90d33c2b8dedfae34dcada9b3935bed134ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609816"
---
# <a name="delete-an-article"></a><span data-ttu-id="25cf9-102">Löschen eines Artikels</span><span class="sxs-lookup"><span data-stu-id="25cf9-102">Delete an Article</span></span>
  <span data-ttu-id="25cf9-103">In diesem Thema wird beschrieben, wie ein Artikel in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mit [!INCLUDE[tsql](../../../includes/tsql-md.md)] oder Replikationsverwaltungsobjekten (RMO) gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="25cf9-103">This topic describes how to delete an article in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../../includes/tsql-md.md)] or Replication Management Objects (RMO).</span></span> <span data-ttu-id="25cf9-104">Informationen über die Bedingungen, unter denen Artikel gelöscht werden können, und darüber, ob das Löschen eines Artikels eine neue Momentaufnahme oder die erneute Initialisierung der Abonnements erforderlich macht, finden Sie unter [Hinzufügen und Löschen von Artikeln aus vorhandenen Veröffentlichungen](add-articles-to-and-drop-articles-from-existing-publications.md).</span><span class="sxs-lookup"><span data-stu-id="25cf9-104">For information about the conditions under which articles can be dropped and whether dropping an article requires a new snapshot or the reinitialization of subscriptions, see [Add Articles to and Drop Articles from Existing Publications](add-articles-to-and-drop-articles-from-existing-publications.md).</span></span>  
  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="25cf9-105">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="25cf9-105">Using Transact-SQL</span></span>  
 <span data-ttu-id="25cf9-106">Artikel können programmgesteuert mit gespeicherten Replikationsprozeduren gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="25cf9-106">Articles can be deleted programmatically using replication stored procedures.</span></span> <span data-ttu-id="25cf9-107">Die verwendeten gespeicherten Prozeduren hängen vom Typ der Veröffentlichung ab, zu der der Artikel gehört.</span><span class="sxs-lookup"><span data-stu-id="25cf9-107">The stored procedures that you use depend on the type of publication to which the article belongs.</span></span>  
  
#### <a name="to-delete-an-article-from-a-snapshot-or-transactional-publication"></a><span data-ttu-id="25cf9-108">So löschen Sie einen Artikel aus einer Momentaufnahme- oder Transaktionsveröffentlichung</span><span class="sxs-lookup"><span data-stu-id="25cf9-108">To delete an article from a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="25cf9-109">Führen Sie [sp_droparticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-droparticle-transact-sql) aus, um einen durch **\@article** angegebenen Artikel aus der durch **\@publication** angegebenen Veröffentlichung zu löschen.</span><span class="sxs-lookup"><span data-stu-id="25cf9-109">Execute [sp_droparticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-droparticle-transact-sql) to delete an article, specified by **\@article**, from a publication, specified by **\@publication**.</span></span> <span data-ttu-id="25cf9-110">Geben Sie für **\@force_invalidate_snapshot** den Wert **1** an.</span><span class="sxs-lookup"><span data-stu-id="25cf9-110">Specify a value of **1** for **\@force_invalidate_snapshot**.</span></span>  
  
2.  <span data-ttu-id="25cf9-111">(Optional) Um das veröffentlichte Objekt vollständig aus der Veröffentlichungsdatenbank zu löschen, führen Sie den Befehl `DROP <objectname>` auf dem Verleger für die Veröffentlichungsdatenbank aus.</span><span class="sxs-lookup"><span data-stu-id="25cf9-111">(Optional) To remove the published object from the database entirely, execute the `DROP <objectname>` command at the Publisher on the publication database.</span></span>  
  
#### <a name="to-delete-an-article-from-a-merge-publication"></a><span data-ttu-id="25cf9-112">So löschen Sie einen Artikel aus einer Mergeveröffentlichung</span><span class="sxs-lookup"><span data-stu-id="25cf9-112">To delete an article from a merge publication</span></span>  
  
1.  <span data-ttu-id="25cf9-113">Führen Sie [sp_dropmergearticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropmergearticle-transact-sql) aus, um einen durch **\@article** angegebenen Artikel aus der durch **\@publication** angegebenen Veröffentlichung zu löschen.</span><span class="sxs-lookup"><span data-stu-id="25cf9-113">Execute [sp_dropmergearticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropmergearticle-transact-sql) to delete an article, specified by **\@article**, from a publication, specified by **\@publication**.</span></span> <span data-ttu-id="25cf9-114">Geben Sie dafür ggf. für **\@force_invalidate_snapshot** den Wert **1** und für **\@force_reinit_subscription** den Wert **1** an.</span><span class="sxs-lookup"><span data-stu-id="25cf9-114">If necessary, specify a value of **1** for **\@force_invalidate_snapshot** and a value of **1** for **\@force_reinit_subscription**.</span></span>  
  
2.  <span data-ttu-id="25cf9-115">(Optional) Um das veröffentlichte Objekt vollständig aus der Veröffentlichungsdatenbank zu löschen, führen Sie den Befehl `DROP <objectname>` auf dem Verleger für die Veröffentlichungsdatenbank aus.</span><span class="sxs-lookup"><span data-stu-id="25cf9-115">(Optional) To remove the published object from the database entirely, execute the `DROP <objectname>` command at the Publisher on the publication database.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="25cf9-116">Beispiele (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="25cf9-116">Examples (Transact-SQL)</span></span>  
 <span data-ttu-id="25cf9-117">Im folgenden Beispiel wird ein Artikel aus einer Transaktionsveröffentlichung gelöscht.</span><span class="sxs-lookup"><span data-stu-id="25cf9-117">The following example deletes an article from a transactional publication.</span></span> <span data-ttu-id="25cf9-118">Da durch diese Änderung die vorhandene Momentaufnahme ungültig wird, wird für den Parameter **\@force_invalidate_snapshot** der Wert **1** angegeben.</span><span class="sxs-lookup"><span data-stu-id="25cf9-118">Because this change invalidates the existing snapshot, a value of **1** is specified for the **\@force_invalidate_snapshot** parameter.</span></span>  
  
 [!code-sql[HowTo#sp_droparticle](../../../snippets/tsql/SQL15/replication/howto/tsql/droptranpub.sql#sp_droparticle)]  
  
 <span data-ttu-id="25cf9-119">Im folgenden Beispiel werden zwei Artikel aus einer Mergeveröffentlichung gelöscht.</span><span class="sxs-lookup"><span data-stu-id="25cf9-119">The following example deletes two articles from a merge publication.</span></span> <span data-ttu-id="25cf9-120">Da durch diese Änderungen die vorhandene Momentaufnahme ungültig wird, wird für den Parameter **\@force_invalidate_snapshot** der Wert **1** angegeben.</span><span class="sxs-lookup"><span data-stu-id="25cf9-120">Because these changes invalidate the existing snapshot, a value of **1** is specified for the **\@force_invalidate_snapshot** parameter.</span></span>  
  
 [!code-sql[HowTo#sp_dropmergearticle](../../../snippets/tsql/SQL15/replication/howto/tsql/dropmergepub.sql#sp_dropmergearticle)]
 [!code-sql[HowTo#sp_dropmergearticle](../../../snippets/tsql/SQL15/replication/howto/tsql/dropmergearticles.sql#sp_dropmergearticle)]  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="25cf9-121">Verwenden von Replikationsverwaltungsobjekten (RMO)</span><span class="sxs-lookup"><span data-stu-id="25cf9-121">Using Replication Management Objects (RMO)</span></span>  
 <span data-ttu-id="25cf9-122">Sie können Artikel mithilfe von Replikationsverwaltungsobjekten (RMO) programmgesteuert löschen.</span><span class="sxs-lookup"><span data-stu-id="25cf9-122">You can delete articles programmatically by using Replication Management Objects (RMO).</span></span> <span data-ttu-id="25cf9-123">Welche RMO-Klassen Sie zum Löschen eines Artikels verwenden, hängt vom Typ der Veröffentlichung ab, zu der der Artikel gehört.</span><span class="sxs-lookup"><span data-stu-id="25cf9-123">The RMO classes you use to delete an article depend on the type of publication to which the article belongs.</span></span>  
  
#### <a name="to-delete-an-article-that-belongs-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="25cf9-124">So löschen Sie einen Artikel, der zu einer Momentaufnahme- oder Transaktionsveröffentlichung gehört</span><span class="sxs-lookup"><span data-stu-id="25cf9-124">To delete an article that belongs to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="25cf9-125">Erstellen Sie eine Verbindung mit dem Verleger, indem Sie die <xref:Microsoft.SqlServer.Management.Common.ServerConnection> -Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="25cf9-125">Create a connection to the Publisher by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="25cf9-126">Erstellen Sie eine Instanz der <xref:Microsoft.SqlServer.Replication.TransArticle>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="25cf9-126">Create an instance of the <xref:Microsoft.SqlServer.Replication.TransArticle> class.</span></span>  
  
3.  <span data-ttu-id="25cf9-127">Legen Sie die Eigenschaften <xref:Microsoft.SqlServer.Replication.Article.Name%2A>, <xref:Microsoft.SqlServer.Replication.Article.PublicationName%2A>und <xref:Microsoft.SqlServer.Replication.Article.DatabaseName%2A> fest.</span><span class="sxs-lookup"><span data-stu-id="25cf9-127">Set the <xref:Microsoft.SqlServer.Replication.Article.Name%2A>, <xref:Microsoft.SqlServer.Replication.Article.PublicationName%2A>, and <xref:Microsoft.SqlServer.Replication.Article.DatabaseName%2A> properties.</span></span>  
  
4.  <span data-ttu-id="25cf9-128">Legen Sie die Verbindung aus Schritt 1 für die <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> -Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="25cf9-128">Set the connection from step 1 for the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property.</span></span>  
  
5.  <span data-ttu-id="25cf9-129">Überprüfen Sie die <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> -Eigenschaft, um festzustellen, ob der Artikel vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="25cf9-129">Check the <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> property to verify that the article exists.</span></span> <span data-ttu-id="25cf9-130">Wenn der Wert dieser Eigenschaft `false` lautet, wurden entweder die Artikeleigenschaften in Schritt 3 falsch definiert, oder der Artikel ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="25cf9-130">If the value of this property is `false`, either the article properties in step 3 were defined incorrectly or the article does not exist.</span></span>  
  
6.  <span data-ttu-id="25cf9-131">Rufen Sie die <xref:Microsoft.SqlServer.Replication.Article.Remove%2A> -Methode auf.</span><span class="sxs-lookup"><span data-stu-id="25cf9-131">Call the <xref:Microsoft.SqlServer.Replication.Article.Remove%2A> method.</span></span>  
  
7.  <span data-ttu-id="25cf9-132">Trennen Sie alle Verbindungen.</span><span class="sxs-lookup"><span data-stu-id="25cf9-132">Close all connections.</span></span>  
  
#### <a name="to-delete-an-article-that-belongs-to-a-merge-publication"></a><span data-ttu-id="25cf9-133">So löschen Sie einen Artikel, der zu einer Mergeveröffentlichung gehört</span><span class="sxs-lookup"><span data-stu-id="25cf9-133">To delete an article that belongs to a merge publication</span></span>  
  
1.  <span data-ttu-id="25cf9-134">Erstellen Sie eine Verbindung mit dem Verleger, indem Sie die <xref:Microsoft.SqlServer.Management.Common.ServerConnection> -Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="25cf9-134">Create a connection to the Publisher by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="25cf9-135">Erstellen Sie eine Instanz der <xref:Microsoft.SqlServer.Replication.MergeArticle>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="25cf9-135">Create an instance of the <xref:Microsoft.SqlServer.Replication.MergeArticle> class.</span></span>  
  
3.  <span data-ttu-id="25cf9-136">Legen Sie die Eigenschaften <xref:Microsoft.SqlServer.Replication.Article.Name%2A>, <xref:Microsoft.SqlServer.Replication.Article.PublicationName%2A>und <xref:Microsoft.SqlServer.Replication.Article.DatabaseName%2A> fest.</span><span class="sxs-lookup"><span data-stu-id="25cf9-136">Set the <xref:Microsoft.SqlServer.Replication.Article.Name%2A>, <xref:Microsoft.SqlServer.Replication.Article.PublicationName%2A>, and <xref:Microsoft.SqlServer.Replication.Article.DatabaseName%2A> properties.</span></span>  
  
4.  <span data-ttu-id="25cf9-137">Legen Sie die Verbindung aus Schritt 1 für die <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> -Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="25cf9-137">Set the connection from step 1 for the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property.</span></span>  
  
5.  <span data-ttu-id="25cf9-138">Überprüfen Sie die <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> -Eigenschaft, um festzustellen, ob der Artikel vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="25cf9-138">Check the <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> property to verify that the article exists.</span></span> <span data-ttu-id="25cf9-139">Wenn der Wert dieser Eigenschaft `false` lautet, wurden entweder die Artikeleigenschaften in Schritt 3 falsch definiert, oder der Artikel ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="25cf9-139">If the value of this property is `false`, either the article properties in step 3 were defined incorrectly or the article does not exist.</span></span>  
  
6.  <span data-ttu-id="25cf9-140">Rufen Sie die <xref:Microsoft.SqlServer.Replication.Article.Remove%2A> -Methode auf.</span><span class="sxs-lookup"><span data-stu-id="25cf9-140">Call the <xref:Microsoft.SqlServer.Replication.Article.Remove%2A> method.</span></span>  
  
7.  <span data-ttu-id="25cf9-141">Trennen Sie alle Verbindungen.</span><span class="sxs-lookup"><span data-stu-id="25cf9-141">Close all connections.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25cf9-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="25cf9-142">See Also</span></span>  
 <span data-ttu-id="25cf9-143">[Hinzufügen und Löschen von Artikeln aus vorhandenen Veröffentlichungen](add-articles-to-and-drop-articles-from-existing-publications.md) </span><span class="sxs-lookup"><span data-stu-id="25cf9-143">[Add Articles to and Drop Articles from Existing Publications](add-articles-to-and-drop-articles-from-existing-publications.md) </span></span>  
 [<span data-ttu-id="25cf9-144">Replication System Stored Procedures Concepts</span><span class="sxs-lookup"><span data-stu-id="25cf9-144">Replication System Stored Procedures Concepts</span></span>](../concepts/replication-system-stored-procedures-concepts.md)  
  
  
