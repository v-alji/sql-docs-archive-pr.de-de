---
title: Prüfen der Integrität von Datenbanken mit fehlerverdächtigen Seiten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 3b1ec9fe-f6c5-46f7-aa63-6e671be1572d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3cc1f87917c78f34ec7722fa21a1a67fda40a8c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695581"
---
# <a name="check-integrity-of-database-with-suspect-pages"></a><span data-ttu-id="6e629-102">Prüfen der Integrität von Datenbanken mit fehlerverdächtigen Seiten</span><span class="sxs-lookup"><span data-stu-id="6e629-102">Check Integrity of Database with Suspect Pages</span></span>
  <span data-ttu-id="6e629-103">Diese Regel überprüft Benutzerdatenbanken, deren Datenbankstatus auf Fehlerverdächtig festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="6e629-103">This rule checks for user databases that have the database status set to suspect.</span></span> <span data-ttu-id="6e629-104">Wenn [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] eine Datenbankseite mit einem Fehler vom Typ 824 liest, wird die Seite als "fehlerverdächtig" betrachtet und ihre Seiten-ID in der suspect_pages-Tabelle der msdb-Datenbank aufgezeichnet. Der Status der Datenbank, die diese Seite enthält, wird auf Fehlerverdächtig festgelegt.</span><span class="sxs-lookup"><span data-stu-id="6e629-104">When the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] reads a database page that contains an 824 error, the page is considered suspect, its page ID is recorded in the suspect_pages table in msdb, and the database that contains the page is set to suspect.</span></span>  
  
 <span data-ttu-id="6e629-105">Der Fehler vom Typ 824 gibt an, dass ein logischer Konsistenzfehler während eines Lesevorgangs aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="6e629-105">Error 824 indicates that a logical consistency error was detected during a read operation.</span></span> <span data-ttu-id="6e629-106">Dieser Fehler gibt häufig eine von einer fehlerhaften E/A-Subsystem-Komponente verursachte Datenbeschädigung an.</span><span class="sxs-lookup"><span data-stu-id="6e629-106">This error frequently indicates data corruption caused by a faulty I/O subsystem component.</span></span> <span data-ttu-id="6e629-107">Dies ist ein schwerer Fehler, der die Datenbankintegrität bedroht und sofort behoben werden muss.</span><span class="sxs-lookup"><span data-stu-id="6e629-107">This is a severe error condition that threatens database integrity and must be corrected immediately.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="6e629-108">Empfehlungen zu Best Practices</span><span class="sxs-lookup"><span data-stu-id="6e629-108">Best Practices Recommendations</span></span>  
  
-   <span data-ttu-id="6e629-109">Weitere Details zum Fehler des Typs 824 finden Sie im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Fehlerprotokoll dieser Datenbank.</span><span class="sxs-lookup"><span data-stu-id="6e629-109">Review the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log for the details of the 824 error for this database.</span></span>  
  
-   <span data-ttu-id="6e629-110">Führen Sie eine vollständige Datenbankkonsistenzprüfung ([DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql)) aus.</span><span class="sxs-lookup"><span data-stu-id="6e629-110">Complete a full database consistency check ([DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql)).</span></span>  
  
-   <span data-ttu-id="6e629-111">Implementieren Sie die Benutzeraktionen, die in [MSSQLSERVER_824](https://go.microsoft.com/fwlink/?LinkId=81397)definiert werden.</span><span class="sxs-lookup"><span data-stu-id="6e629-111">Implement the user actions that are defined in [MSSQLSERVER_824](https://go.microsoft.com/fwlink/?LinkId=81397).</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="6e629-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6e629-112">For More Information</span></span>  
 [<span data-ttu-id="6e629-113">Verwalten der suspect_pages-Tabelle &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6e629-113">Manage the suspect_pages Table &#40;SQL Server&#41;</span></span>](../backup-restore/manage-the-suspect-pages-table-sql-server.md)  
  
  
