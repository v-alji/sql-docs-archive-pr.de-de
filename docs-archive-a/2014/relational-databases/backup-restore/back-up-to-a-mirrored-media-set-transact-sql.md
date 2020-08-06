---
title: Sichern auf einem gespiegelten Mediensatz (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: 5fc43a5d-dfd6-4c53-a4ef-3c8da23ccc81
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 255a3c190139c029f5211dcab9780b6d07d975a4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618736"
---
# <a name="back-up-to-a-mirrored-media-set-transact-sql"></a><span data-ttu-id="49c7f-102">Sichern auf einem gespiegelten Mediensatz (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="49c7f-102">Back Up to a Mirrored Media Set (Transact-SQL)</span></span>
  <span data-ttu-id="49c7f-103">In diesem Thema wird beschrieben, wie die [!INCLUDE[tsql](../../includes/tsql-md.md)] [Backup](/sql/t-sql/statements/backup-transact-sql) -Anweisung zum Angeben eines gespiegelten Medien Satzes beim Sichern einer-Datenbank verwendet wird [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="49c7f-103">This topic describes how to use the [!INCLUDE[tsql](../../includes/tsql-md.md)][BACKUP](/sql/t-sql/statements/backup-transact-sql) statement to specify a mirrored media set when backing up a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="49c7f-104">Geben Sie in der BACKUP-Anweisung den ersten Spiegel in der TO-Klausel an.</span><span class="sxs-lookup"><span data-stu-id="49c7f-104">In your BACKUP statement, specify the first mirror in the TO clause.</span></span> <span data-ttu-id="49c7f-105">Geben Sie anschließend jeden Spiegel in der MIRROR TO-Klausel des Spiegels an.</span><span class="sxs-lookup"><span data-stu-id="49c7f-105">Then, specify each mirror in its own MIRROR TO clause.</span></span> <span data-ttu-id="49c7f-106">In den TO- und MIRROR TO-Klauseln müssen die gleiche Anzahl und der gleiche Typ von Sicherungsmedien angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="49c7f-106">The TO and MIRROR TO clauses must specify the same number and type of backup devices.</span></span>  
  
## <a name="example"></a><span data-ttu-id="49c7f-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="49c7f-107">Example</span></span>  
 <span data-ttu-id="49c7f-108">Im folgenden Beispiel wird der in der vorherigen Abbildung dargestellte gespiegelte Mediensatz erstellt und die [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Datenbank auf beiden Spiegeln gesichert.</span><span class="sxs-lookup"><span data-stu-id="49c7f-108">The following example creates the mirrored media set illustrated in the previous illustration and backs up the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database to both mirrors.</span></span>  
  
```  
BACKUP DATABASE AdventureWorks2012  
TO TAPE = '\\.\tape0', TAPE = '\\.\tape1'  
MIRROR TO TAPE = '\\.\tape2', TAPE = '\\.\tape3'  
WITH  
    FORMAT,  
    MEDIANAME = 'AdventureWorks2012Set1';  
GO  
```  
  
## <a name="related-tasks"></a><span data-ttu-id="49c7f-109">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="49c7f-109">Related Tasks</span></span>  
 <span data-ttu-id="49c7f-110">**So stellen Sie Daten von einer gespiegelten Sicherung wieder her**</span><span class="sxs-lookup"><span data-stu-id="49c7f-110">**To restore from a mirrored backup**</span></span>  
  
-   [<span data-ttu-id="49c7f-111">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="49c7f-111">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="49c7f-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="49c7f-112">See Also</span></span>  
 <span data-ttu-id="49c7f-113">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="49c7f-113">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 [<span data-ttu-id="49c7f-114">Gespiegelte Sicherungsmediensätze &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="49c7f-114">Mirrored Backup Media Sets &#40;SQL Server&#41;</span></span>](mirrored-backup-media-sets-sql-server.md)  
  
  
