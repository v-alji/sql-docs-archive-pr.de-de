---
title: Verschieben von Datenbankdateien | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- disaster recovery [SQL Server], moving database files
- files [SQL Server], moving
- data files [SQL Server], moving
- file moving [SQL Server]
- moving full-text catalogs
- moving databases
- full-text catalogs [SQL Server], moving
- moving database files
- scheduled disk maintenance [SQL Server]
- moving files
- relocating database files
- planned database relocations [SQL Server]
- databases [SQL Server], moving
ms.assetid: 89f01b10-5fae-4ed8-b0fb-a4b9f540fd28
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5491f3c4dfd47cac4047d0409c78001be80d6f13
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721474"
---
# <a name="move-database-files"></a><span data-ttu-id="351c6-102">Verschieben von Datenbankdateien</span><span class="sxs-lookup"><span data-stu-id="351c6-102">Move Database Files</span></span>
  <span data-ttu-id="351c6-103">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]können Sie System- und Benutzerdatenbanken durch Angeben des neuen Dateispeicherorts in der FILENAME-Klausel der [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) -Anweisung verschieben.</span><span class="sxs-lookup"><span data-stu-id="351c6-103">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you can move system and user databases by specifying the new file location in the FILENAME clause of the [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) statement.</span></span> <span data-ttu-id="351c6-104">Auf diese Weise können Daten-, Protokoll- und Volltextkatalogdateien verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="351c6-104">Data, log, and full-text catalog files can be moved in this way.</span></span> <span data-ttu-id="351c6-105">Dies kann in folgenden Situationen nützlich sein:</span><span class="sxs-lookup"><span data-stu-id="351c6-105">This may be useful in the following situations:</span></span>  
  
-   <span data-ttu-id="351c6-106">Bei der Wiederherstellung nach Fehlern.</span><span class="sxs-lookup"><span data-stu-id="351c6-106">Failure recovery.</span></span> <span data-ttu-id="351c6-107">Wenn z. B. die Datenbank aufgrund eines Hardwarefehlers als fehlerverdächtig eingestuft oder heruntergefahren wurde.</span><span class="sxs-lookup"><span data-stu-id="351c6-107">For example, the database is in suspect mode or has shut down, because of a hardware failure.</span></span>  
  
-   <span data-ttu-id="351c6-108">Bei geplanter Verschiebung.</span><span class="sxs-lookup"><span data-stu-id="351c6-108">Planned relocation.</span></span>  
  
-   <span data-ttu-id="351c6-109">Verschiebung aufgrund planmäßiger Datenträgerwartung.</span><span class="sxs-lookup"><span data-stu-id="351c6-109">Relocation for scheduled disk maintenance.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="351c6-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="351c6-110">In This Section</span></span>  
  
|<span data-ttu-id="351c6-111">Thema</span><span class="sxs-lookup"><span data-stu-id="351c6-111">Topic</span></span>|<span data-ttu-id="351c6-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="351c6-112">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="351c6-113">Verschieben von Benutzerdatenbanken</span><span class="sxs-lookup"><span data-stu-id="351c6-113">Move User Databases</span></span>](move-user-databases.md)|<span data-ttu-id="351c6-114">Beschreibt die Prozeduren, um Benutzerdatenbankdateien und Volltextkatalogdateien an einen neuen Speicherort zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="351c6-114">Describes the procedures for moving user database files and full-text catalog files to a new location.</span></span>|  
|[<span data-ttu-id="351c6-115">Verschieben von Systemdatenbanken</span><span class="sxs-lookup"><span data-stu-id="351c6-115">Move System Databases</span></span>](system-databases.md)|<span data-ttu-id="351c6-116">Beschreibt die Prozeduren, um Systemdatenbankdateien an einen neuen Speicherort zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="351c6-116">Describes the procedures for moving system database files to a new location.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="351c6-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="351c6-117">See Also</span></span>  
 <span data-ttu-id="351c6-118">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="351c6-118">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="351c6-119">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="351c6-119">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 [<span data-ttu-id="351c6-120">Anfügen und Trennen von Datenbanken &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="351c6-120">Database Detach and Attach &#40;SQL Server&#41;</span></span>](database-detach-and-attach-sql-server.md)  
  
  
