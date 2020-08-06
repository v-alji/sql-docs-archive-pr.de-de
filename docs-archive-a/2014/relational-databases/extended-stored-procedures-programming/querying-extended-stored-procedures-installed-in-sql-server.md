---
title: Abfragen von in SQL Server installierten erweiterten gespeicherten Prozeduren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- extended stored procedures [SQL Server], querying
ms.assetid: e02348e6-dba6-438a-98b6-684244bb034d
author: rothja
ms.author: jroth
ms.openlocfilehash: 3f44db9053ad18c3a6902a30aaab4f81610c5a8c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615397"
---
# <a name="querying-extended-stored-procedures-installed-in-sql-server"></a><span data-ttu-id="41d01-102">Abfragen von in SQL Server installierten erweiterten gespeicherten Prozeduren</span><span class="sxs-lookup"><span data-stu-id="41d01-102">Querying Extended Stored Procedures Installed in SQL Server</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="41d01-103">Verwenden Sie stattdessen die CLR-Integration.</span><span class="sxs-lookup"><span data-stu-id="41d01-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="41d01-104">Ein [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] authentifizierter Benutzer kann die zurzeit definierten erweiterten gespeicherten Prozeduren und den Namen der dll, zu der jeder gehört, anzeigen, indem er die **sp_helpextendedproc** System Prozedur ausführen.</span><span class="sxs-lookup"><span data-stu-id="41d01-104">A [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] authenticated user can display the currently defined extended stored procedures and the name of the DLL to which each belongs by running the **sp_helpextendedproc** system procedure.</span></span> <span data-ttu-id="41d01-105">Im folgenden Beispiel wird z. b. die dll zurückgegeben, zu der **xp_hello** gehört:</span><span class="sxs-lookup"><span data-stu-id="41d01-105">For example, the following example returns the DLL to which **xp_hello** belongs:</span></span>  
  
```  
sp_helpextendedproc 'xp_hello'  
```  
  
 <span data-ttu-id="41d01-106">Wenn **sp_helpextendedproc** ohne Angabe einer erweiterten gespeicherten Prozedur ausgeführt wird, werden alle erweiterten gespeicherten Prozeduren und ihre DLLs angezeigt.</span><span class="sxs-lookup"><span data-stu-id="41d01-106">If **sp_helpextendedproc** is executed without specifying an extended stored procedure, all the extended stored procedures and their DLLs are displayed.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="41d01-107">Informationen werden nur für die erweiterten gespeicherten Prozeduren zurückgegeben, deren Besitzer der Benutzer ist oder für die dem Benutzer eine Berechtigung erteilt wurde.</span><span class="sxs-lookup"><span data-stu-id="41d01-107">Information will be returned for only those extended stored procedures that the logged in user owns or has permissions to.</span></span> <span data-ttu-id="41d01-108">Nur Mitglieder der festen Server Rolle **sysadmin** und der **db_owner**, **db_securityadmin**und der festen Daten Bank Rolle **db_ddladmin** können Informationen zu allen erweiterten gespeicherten Prozeduren anzeigen.</span><span class="sxs-lookup"><span data-stu-id="41d01-108">Only members of the **sysadmin** fixed server role and the **db_owner**, **db_securityadmin**, and the **db_ddladmin** fixed database roles can view information for all extended stored procedures.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41d01-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="41d01-109">See Also</span></span>  
 <span data-ttu-id="41d01-110">[sp_helpextendedproc &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-helpextendedproc-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="41d01-110">[sp_helpextendedproc &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpextendedproc-transact-sql) </span></span>  
 <span data-ttu-id="41d01-111">[sp_addextendedproc &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-addextendedproc-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="41d01-111">[sp_addextendedproc &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addextendedproc-transact-sql) </span></span>  
 [<span data-ttu-id="41d01-112">sp_dropextendedproc &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="41d01-112">sp_dropextendedproc &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-dropextendedproc-transact-sql)  
  
  
