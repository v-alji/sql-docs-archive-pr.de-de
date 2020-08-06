---
title: Deaktivieren von Fremdschlüsseleinschränkungen für die Replikation | Microsoft-Dokumentation
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
ms.assetid: 4211f2fd-d16a-4081-995c-43f1f0827f0b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4ee7f2fb7b0a27870a09a9d99b723b7faf739aeb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616965"
---
# <a name="disable-foreign-key-constraints-for-replication"></a><span data-ttu-id="5b60c-102">Deaktivieren von Fremdschlüsseleinschränkungen für die Replikation</span><span class="sxs-lookup"><span data-stu-id="5b60c-102">Disable Foreign Key Constraints for Replication</span></span>
  <span data-ttu-id="5b60c-103">Sie können Fremdschlüsseleinschränkungen für die Replikation in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="5b60c-103">You can disable foreign key constraints for replication in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="5b60c-104">Dies kann nützlich sein, wenn Sie Daten einer früheren Version von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="5b60c-104">This can be useful if you are publishing data from a previous version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5b60c-105">Wird eine Tabelle mithilfe einer Replikation veröffentlicht, werden Fremdschlüsseleinschränkungen automatisch für die Operationen deaktiviert, die von Replikations-Agents ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5b60c-105">If a table is published using replication, foreign key constraints are automatically disabled for operations performed by replication agents.</span></span> <span data-ttu-id="5b60c-106">Wenn ein Replikations-Agent eine Einfügung, ein Update oder eine Löschung auf einem Abonnenten ausführt, wird die Einschränkung nicht überprüft; wenn ein Benutzer eine Einfügung, ein Update oder eine Löschung ausführt, wird die Einschränkung überprüft.</span><span class="sxs-lookup"><span data-stu-id="5b60c-106">When a replication agent performs an insert, update, or delete at a Subscriber, the constraint is not checked; if a user performs an insert, update, or delete, the constraint is checked.</span></span> <span data-ttu-id="5b60c-107">Die Einschränkung wird für den Replikations-Agent deaktiviert, da die Einschränkung bereits auf dem Verleger überprüft wurde, als die Daten ursprünglich eingefügt, aktualisiert oder gelöscht wurden.</span><span class="sxs-lookup"><span data-stu-id="5b60c-107">The constraint is disabled for the replication agent because the constraint was already checked at the Publisher when the data was originally inserted, updated, or deleted.</span></span>  
  
 <span data-ttu-id="5b60c-108">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="5b60c-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5b60c-109">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="5b60c-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5b60c-110">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="5b60c-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5b60c-111">**So deaktivieren Sie eine Fremdschlüsseleinschränkung für die Replikation mit:**</span><span class="sxs-lookup"><span data-stu-id="5b60c-111">**To disable a foreign key constraint for replication, using:**</span></span>  
  
     [<span data-ttu-id="5b60c-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5b60c-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5b60c-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5b60c-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5b60c-114">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="5b60c-114">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5b60c-115">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="5b60c-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5b60c-116">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="5b60c-116">Permissions</span></span>  
 <span data-ttu-id="5b60c-117">Erfordert die ALTER-Berechtigung für die Tabelle.</span><span class="sxs-lookup"><span data-stu-id="5b60c-117">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5b60c-118">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5b60c-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-a-foreign-key-constraint-for-replication"></a><span data-ttu-id="5b60c-119">So deaktivieren Sie eine Fremdschlüsseleinschränkung für die Replikation</span><span class="sxs-lookup"><span data-stu-id="5b60c-119">To disable a foreign key constraint for replication</span></span>  
  
1.  <span data-ttu-id="5b60c-120">Erweitern Sie im **Objekt-Explorer**die Tabelle mit der Fremdschlüsseleinschränkung, die geändert werden soll, und erweitern Sie dann den Ordner **Schlüssel** .</span><span class="sxs-lookup"><span data-stu-id="5b60c-120">In **Object Explorer**, expand the table with the foreign key constraint you want to modify, and then expand the **Keys** folder.</span></span>  
  
2.  <span data-ttu-id="5b60c-121">Klicken Sie mit der rechten Maustaste auf die Fremdschlüsseleinschränkung, und klicken Sie anschließend auf **Ändern**.</span><span class="sxs-lookup"><span data-stu-id="5b60c-121">Right-click the foreign key constraint and then click **Modify**.</span></span>  
  
3.  <span data-ttu-id="5b60c-122">Wählen Sie im Dialogfeld **Fremdschlüsselbeziehungen** den Wert **Nein** für **Für Replikation erzwingen**aus.</span><span class="sxs-lookup"><span data-stu-id="5b60c-122">In the **Foreign Key Relationships** dialog box, select a value of **No** for **Enforce For Replication**.</span></span>  
  
4.  <span data-ttu-id="5b60c-123">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="5b60c-123">Click **Close**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5b60c-124">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5b60c-124">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-a-foreign-key-constraint-for-replication"></a><span data-ttu-id="5b60c-125">So deaktivieren Sie eine Fremdschlüsseleinschränkung für die Replikation</span><span class="sxs-lookup"><span data-stu-id="5b60c-125">To disable a foreign key constraint for replication</span></span>  
  
1.  <span data-ttu-id="5b60c-126">Um diesen Task in [!INCLUDE[tsql](../../includes/tsql-md.md)]auszuführen, löschen Sie die Fremdschlüsseleinschränkung.</span><span class="sxs-lookup"><span data-stu-id="5b60c-126">To perform this task in [!INCLUDE[tsql](../../includes/tsql-md.md)], drop the foreign key constraint.</span></span> <span data-ttu-id="5b60c-127">Fügen Sie dann eine neue Fremdschlüsseleinschränkung hinzu, und geben Sie die Option NOT FOR REPLICATION an.</span><span class="sxs-lookup"><span data-stu-id="5b60c-127">Then add a new foreign key constraint and specify the NOT FOR REPLICATION option.</span></span>  
  
 <span data-ttu-id="5b60c-128">Weitere Informationen finden Sie unter [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5b60c-128">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
