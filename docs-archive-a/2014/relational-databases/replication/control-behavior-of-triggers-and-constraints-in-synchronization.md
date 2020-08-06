---
title: Steuern des Verhaltens von Triggern und Einschränkungen während der Synchronisierung (Replikations Programmierung mit Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- identities [SQL Server replication]
- constraints [SQL Server], replication
- triggers [SQL Server], replication
- triggers [SQL Server replication]
- constraints [SQL Server replication]
- NOT FOR REPLICATION option
- NFR option
ms.assetid: 7c4e0f0e-cadc-4c99-98f4-69799b9b356b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 88176f43295fe2ab1f5f5643a46db1ce6132c5f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608573"
---
# <a name="control-the-behavior-of-triggers-and-constraints-during-synchronization-replication-transact-sql-programming"></a><span data-ttu-id="e3817-102">Kontrollieren des Verhaltens von Triggern und Einschränkungen während der Synchronisierung (Replikationsprogrammierung mit Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e3817-102">Control the Behavior of Triggers and Constraints During Synchronization (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="e3817-103">Während der Synchronisierung führen Replikation-Agents [INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql)-Anweisungen und [UPDATE &#40;Transact-SQL&#41;](/sql/t-sql/queries/update-transact-sql) sowie [DELETE &#40;Transact-SQL&#41;](/sql/t-sql/statements/delete-transact-sql)-Anweisungen für replizierte Tabellen aus, was zur Ausführung von DML (Data Manipulation Language)-Triggern in diesen Tabellen führen kann.</span><span class="sxs-lookup"><span data-stu-id="e3817-103">During synchronization, replication agents execute [INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql), [UPDATE &#40;Transact-SQL&#41;](/sql/t-sql/queries/update-transact-sql), and [DELETE &#40;Transact-SQL&#41;](/sql/t-sql/statements/delete-transact-sql) statements on replicated tables, which can cause data manipulation language (DML) triggers on these tables to be executed.</span></span> <span data-ttu-id="e3817-104">Es gibt Fälle, in denen Sie verhindern müssen, dass Trigger während der Synchronisierung ausgelöst werden oder Einschränkungen während der Synchronisierung erzwungen werden.</span><span class="sxs-lookup"><span data-stu-id="e3817-104">There are cases when you may need to prevent these triggers from firing or constraints from being enforced during synchronization.</span></span> <span data-ttu-id="e3817-105">Dieses Verhalten hängt davon ab, wie der Trigger oder die Einschränkung erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="e3817-105">This behavior depends on how the trigger or constraint is created.</span></span>  
  
### <a name="to-prevent-triggers-from-executing-during-synchronization"></a><span data-ttu-id="e3817-106">So verhindern Sie, dass Trigger während der Synchronisierung ausgeführt werden</span><span class="sxs-lookup"><span data-stu-id="e3817-106">To prevent triggers from executing during synchronization</span></span>  
  
1.  <span data-ttu-id="e3817-107">Geben Sie bei der Erstellung eines neuen Triggers die Option NOT FOR REPLICATION für [CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) an.</span><span class="sxs-lookup"><span data-stu-id="e3817-107">When creating a new trigger, specify the NOT FOR REPLICATION option of [CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql).</span></span>  
  
2.  <span data-ttu-id="e3817-108">Für einen vorhandenen Trigger geben Sie die Option NOT FOR REPLICATION für [ALTER TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-trigger-transact-sql) an.</span><span class="sxs-lookup"><span data-stu-id="e3817-108">For an existing trigger, specify the NOT FOR REPLICATION option of [ALTER TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-trigger-transact-sql).</span></span>  
  
### <a name="to-prevent-constraints-from-being-enforced-during-synchronization"></a><span data-ttu-id="e3817-109">So verhindern Sie, dass Einschränkungen während der Synchronisierung erzwungen werden</span><span class="sxs-lookup"><span data-stu-id="e3817-109">To prevent constraints from being enforced during synchronization</span></span>  
  
1.  <span data-ttu-id="e3817-110">Beim Erstellen einer neuen CHECK- oder FOREIGN KEY-Einschränkung geben Sie in der Einschränkungsdefinition von [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) die Option CHECK NOT FOR REPLICATION an.</span><span class="sxs-lookup"><span data-stu-id="e3817-110">When creating a new CHECK or FOREIGN KEY constraint, specify CHECK NOT FOR REPLICATION option in the constraint definition of [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3817-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e3817-111">See Also</span></span>  
 [<span data-ttu-id="e3817-112">Erstellen von Tabellen &#40;Datenbank-Engine&#41;</span><span class="sxs-lookup"><span data-stu-id="e3817-112">Create Tables &#40;Database Engine&#41;</span></span>](../tables/create-tables-database-engine.md)  
  
  
