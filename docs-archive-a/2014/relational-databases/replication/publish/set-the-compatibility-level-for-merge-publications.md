---
title: Festlegen des Kompatibilitätsgrads von Mergeveröffentlichungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- compatibility [SQL Server], replication
- backward compatibility [SQL Server], replication
- publications [SQL Server replication], backward compatibility
ms.assetid: db47ac73-948b-4d77-b272-bb3565135ea5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 04ad80b0c99e7282ff2acfa459a08665efbdee1c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622550"
---
# <a name="set-the-compatibility-level-for-merge-publications"></a><span data-ttu-id="362d5-102">Festlegen des Kompatibilitätsgrads von Mergeveröffentlichungen</span><span class="sxs-lookup"><span data-stu-id="362d5-102">Set the Compatibility Level for Merge Publications</span></span>
  <span data-ttu-id="362d5-103">In diesem Thema wird beschrieben, wie der Kompatibilitätsgrad für Mergeveröffentlichungen in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../../includes/tsql-md.md)]festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="362d5-103">This topic describes how to set the compatibility level for merge publications in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="362d5-104">Bei der Mergereplikation wird anhand des Kompatibilitätsgrades der Veröffentlichung bestimmt, welche Funktionen von Veröffentlichungen in der jeweiligen Datenbank verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="362d5-104">Merge replication uses the publication compatibility level to determine which features can be used by publications in a given database.</span></span>  
  
 <span data-ttu-id="362d5-105">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="362d5-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="362d5-106">**So legen Sie den Kompatibilitätsgrad von Mergeveröffentlichungen fest mit:**</span><span class="sxs-lookup"><span data-stu-id="362d5-106">**To set the compatibility level for merge publications, using:**</span></span>  
  
     [<span data-ttu-id="362d5-107">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="362d5-107">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="362d5-108">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="362d5-108">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="362d5-109">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="362d5-109">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="362d5-110">Der Kompatibilitätsgrad wird auf der Seite **Abonnententypen** des Assistenten für neue Veröffentlichung festgelegt.</span><span class="sxs-lookup"><span data-stu-id="362d5-110">Set the compatibility level on the **Subscriber Types** page of the New Publication Wizard.</span></span> <span data-ttu-id="362d5-111">Weitere Informationen zum Zugreifen auf diesen Assistenten finden Sie unter [Create a Publication](create-a-publication.md)festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="362d5-111">For more information on accessing this wizard, see [Create a Publication](create-a-publication.md).</span></span> <span data-ttu-id="362d5-112">Nach dem Erstellen einer Veröffentlichungsmomentaufnahme kann der Kompatibilitätsgrad zwar erhöht, nicht aber gesenkt werden.</span><span class="sxs-lookup"><span data-stu-id="362d5-112">After a publication snapshot is created, the compatibility level can be increased but cannot be decreased.</span></span> <span data-ttu-id="362d5-113">Sie können den Kompatibilitätsgrad auf der Seite **Allgemein** des Dialogfelds **Veröffentlichungseigenschaften – \<Publication>** erhöhen.</span><span class="sxs-lookup"><span data-stu-id="362d5-113">Increase the compatibility level on the **General** page of the **Publication Properties - \<Publication>** dialog box.</span></span> <span data-ttu-id="362d5-114">Weitere Informationen zum Zugreifen auf dieses Dialogfeld finden Sie unter [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="362d5-114">For more information about accessing this dialog box, see [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span></span> <span data-ttu-id="362d5-115">Wenn Sie den Veröffentlichungskompatibilitätsgrad erhöhen, können alle vorhandenen Abonnements auf Servern, auf denen eine Version vor diesem Kompatibilitätsgrad ausgeführt wird, nicht mehr synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="362d5-115">If you increase the publication compatibility level, any existing subscriptions at servers running versions prior to the compatibility level will no longer be able to synchronize.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="362d5-116">Da der Kompatibilitätsgrad Auswirkungen auf andere Veröffentlichungseigenschaften und darauf hat, welche Artikeleigenschaften gültig sind, dürfen Sie den Kompatibilitätsgrad nicht gleichzeitig mit anderen Eigenschaften im Dialogfeld ändern.</span><span class="sxs-lookup"><span data-stu-id="362d5-116">Because the compatibility level has implications for other publication properties and for which article properties are valid, do not change the compatibility level and other properties in the same use of the dialog box.</span></span> <span data-ttu-id="362d5-117">Die Momentaufnahme für die Veröffentlichung sollte nach dem Ändern der Eigenschaften neu generiert werden.</span><span class="sxs-lookup"><span data-stu-id="362d5-117">The snapshot for the publication should be regenerated after the property is changed.</span></span>  
  
#### <a name="to-set-the-publication-compatibility-level"></a><span data-ttu-id="362d5-118">So legen Sie den Veröffentlichungskompatibilitätsgrad fest</span><span class="sxs-lookup"><span data-stu-id="362d5-118">To set the publication compatibility level</span></span>  
  
-   <span data-ttu-id="362d5-119">Wählen Sie auf der Seite **Abonnementtypen** des Assistenten für neue Veröffentlichung die Abonnententypen aus, die die Veröffentlichung unterstützen soll.</span><span class="sxs-lookup"><span data-stu-id="362d5-119">On the **Subscriber Types** page of the New Publication Wizard, select the types of Subscribers that the publication should support.</span></span>  
  
#### <a name="to-increase-the-publication-compatibility-level"></a><span data-ttu-id="362d5-120">So erhöhen Sie den Veröffentlichungskompatibilitätsgrad</span><span class="sxs-lookup"><span data-stu-id="362d5-120">To increase the publication compatibility level</span></span>  
  
-   <span data-ttu-id="362d5-121">Wählen Sie auf der Seite **Allgemein** des Dialogfelds **Veröffentlichungseigenschaften – \<Publication>** die Option **Kompatibilitätsgrad** aus.</span><span class="sxs-lookup"><span data-stu-id="362d5-121">On the **General** page of the **Publication Properties - \<Publication>** dialog box, select for **Compatibility level**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="362d5-122">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="362d5-122">Using Transact-SQL</span></span>  
 <span data-ttu-id="362d5-123">Der Kompatibilitätsgrad einer Mergeveröffentlichung kann entweder programmgesteuert während der Erstellung der Veröffentlichung festgelegt oder zu einem späteren Zeitpunkt programmgesteuert geändert werden.</span><span class="sxs-lookup"><span data-stu-id="362d5-123">The compatibility level for a merge publication can either be set programmatically when a publication is created or modified programmatically at a later time.</span></span> <span data-ttu-id="362d5-124">Sie können gespeicherte Replikationsprozeduren verwenden, um diese Veröffentlichungseigenschaft festzulegen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="362d5-124">You can use replication stored procedures to set or change this publication property.</span></span>  
  
#### <a name="to-set-the-publication-compatibility-level-for-a-merge-publication"></a><span data-ttu-id="362d5-125">So legen Sie den Veröffentlichungskompatibilitätsgrad einer Mergeveröffentlichung fest</span><span class="sxs-lookup"><span data-stu-id="362d5-125">To set the publication compatibility level for a merge publication</span></span>  
  
1.  <span data-ttu-id="362d5-126">Führen Sie auf dem Verleger [sp_addmergepublication &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql)aus, und geben Sie dabei einen Wert für an, damit **@publication_compatibility_level** die Veröffentlichung mit älteren Versionen von kompatibel ist [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="362d5-126">At the Publisher, execute [sp_addmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql), specifying a value for **@publication_compatibility_level** to make the publication compatible with older versions of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="362d5-127">Weitere Informationen finden Sie unter [Create a Publication](create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="362d5-127">For more information, see [Create a Publication](create-a-publication.md).</span></span>  
  
#### <a name="to-change-the-publication-compatibility-level-of-a-merge-publication"></a><span data-ttu-id="362d5-128">So ändern Sie den Veröffentlichungskompatibilitätsgrad einer Mergeveröffentlichung</span><span class="sxs-lookup"><span data-stu-id="362d5-128">To change the publication compatibility level of a merge publication</span></span>  
  
1.  <span data-ttu-id="362d5-129">Führen Sie [sp_changemergepublication &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql)aus, und geben Sie **publication_compatibility_level** für **@property** und den entsprechenden Veröffentlichungs Kompatibilitäts Grad für an **@value** .</span><span class="sxs-lookup"><span data-stu-id="362d5-129">Execute [sp_changemergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql), specifying **publication_compatibility_level** for **@property** and the appropriate publication compatibility level for **@value**.</span></span>  
  
#### <a name="to-determine-the-publication-compatibility-level-of-a-merge-publication"></a><span data-ttu-id="362d5-130">So bestimmen Sie den Veröffentlichungskompatibilitätsgrad einer Mergeveröffentlichung</span><span class="sxs-lookup"><span data-stu-id="362d5-130">To determine the publication compatibility level of a merge publication</span></span>  
  
1.  <span data-ttu-id="362d5-131">Führen Sie [Sp_helpmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpmergepublication-transact-sql) unter Angabe der gewünschten Veröffentlichung aus.</span><span class="sxs-lookup"><span data-stu-id="362d5-131">Execute [sp_helpmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpmergepublication-transact-sql), specifying the desired publication.</span></span>  
  
2.  <span data-ttu-id="362d5-132">Suchen Sie den Veröffentlichungskompatibilitätsgrad im Resultset in der **backward_comp_level** -Spalte.</span><span class="sxs-lookup"><span data-stu-id="362d5-132">Locate the publication compatibility level in the **backward_comp_level** column in the result set.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="362d5-133">Beispiele (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="362d5-133">Examples (Transact-SQL)</span></span>  
 <span data-ttu-id="362d5-134">In diesem Beispiel wird eine Mergeveröffentlichung erstellt und der Veröffentlichungskompatibilitätsgrad festgelegt.</span><span class="sxs-lookup"><span data-stu-id="362d5-134">This example creates a merge publication and sets the publication compatibility level.</span></span>  
  
```  
-- To avoid storing the login and password in the script file, the values   
-- are passed into SQLCMD as scripting variables. For information about   
-- how to use scripting variables on the command line and in SQL Server  
-- Management Studio, see the "Executing Replication Scripts" section in  
-- the topic "Programming Replication Using System Stored Procedures".  
  
--Add a new merge publication.  
DECLARE @publicationDB AS sysname;  
DECLARE @publication AS sysname;  
DECLARE @login AS sysname;  
DECLARE @password AS sysname;  
SET @publicationDB = N'AdventureWorks2012';   
SET @publication = N'AdvWorksSalesOrdersMerge'   
SET @login = $(Login);  
SET @password = $(Password);  
  
-- Create a new merge publication.   
USE [AdventureWorks2012]  
EXEC sp_addmergepublication   
@publication = @publication,   
-- Set the compatibility level to SQL Server 2014.  
@publication_compatibility_level = '120RTM';   
  
-- Create the snapshot job for the publication.  
EXEC sp_addpublication_snapshot   
@publication = @publication,  
@job_login = @login,  
@job_password = @password;  
GO  
```  
  
 <span data-ttu-id="362d5-135">In diesem Beispiel wird der Veröffentlichungskompatibilitätsgrad einer Mergeveröffentlichung geändert.</span><span class="sxs-lookup"><span data-stu-id="362d5-135">This example changes the publication compatibility level for the merge publication.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="362d5-136">Wenn in der Veröffentlichung Funktionen verwendet werden, die einen bestimmten Kompatibilitätsgrad erfordern, darf der Veröffentlichungskompatibilitätsgrad möglicherweise nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="362d5-136">Changing the publication compatibility level might not be allowed if the publication uses any features that require a particular compatibility level.</span></span> <span data-ttu-id="362d5-137">Weitere Informationen finden Sie unter [Abwärtskompatibilität von Replikationen](../replication-backward-compatibility.md).</span><span class="sxs-lookup"><span data-stu-id="362d5-137">For more information, see [Replication Backward Compatibility](../replication-backward-compatibility.md).</span></span>  
  
```  
DECLARE @publication AS sysname;  
SET @publication = N'AdvWorksSalesOrdersMerge' ;  
  
-- Change the publication compatibility level to   
-- SQL Server 2012.  
EXEC sp_changemergepublication   
@publication = @publication,   
@property = N'publication_compatibility_level',   
@value = N'110RTM';  
GO  
  
```  
  
 <span data-ttu-id="362d5-138">In diesem Beispiel wird der aktuelle Veröffentlichungskompatibilitätsgrad einer Mergeveröffentlichung zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="362d5-138">This example returns the current publication compatibility level for the merge publication.</span></span>  
  
```  
DECLARE @publication AS sysname;  
SET @publication = N'AdvWorksSalesOrdersMerge' ;  
EXEC sp_helpmergepublication   
@publication = @publication;  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="362d5-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="362d5-139">See Also</span></span>  
 [<span data-ttu-id="362d5-140">Erstellen einer Veröffentlichung</span><span class="sxs-lookup"><span data-stu-id="362d5-140">Create a Publication</span></span>](create-a-publication.md)  
  
  
