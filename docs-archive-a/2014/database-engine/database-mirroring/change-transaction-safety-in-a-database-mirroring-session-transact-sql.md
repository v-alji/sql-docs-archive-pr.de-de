---
title: Ändern der Transaktionssicherheit in einer Datenbank-Spiegelungssitzung (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- transaction safety [SQL Server database mirroring]
ms.assetid: 8b03bb82-8589-4558-8545-9942fe008391
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d8bc9d0fb639770d33507c29a6ec67f60bd0434a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615582"
---
# <a name="change-transaction-safety-in-a-database-mirroring-session-transact-sql"></a><span data-ttu-id="4a528-102">Ändern der Transaktionssicherheit in einer Datenbank-Spiegelungssitzung (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4a528-102">Change Transaction Safety in a Database Mirroring Session (Transact-SQL)</span></span>
  <span data-ttu-id="4a528-103">Die Transaktionssicherheit ist das Attribut, das den Betriebsmodus der Sitzung steuert.</span><span class="sxs-lookup"><span data-stu-id="4a528-103">Transaction safety is the attribute that controls the operating mode of the session.</span></span> <span data-ttu-id="4a528-104">Der Datenbankbesitzer kann die Transaktionssicherheit jedoch jederzeit ändern.</span><span class="sxs-lookup"><span data-stu-id="4a528-104">At any time, however, the database owner can change the transaction safety.</span></span> <span data-ttu-id="4a528-105">Standardmäßig ist die Sicherheitsstufe für Transaktionen auf FULL (synchroner Betriebsmodus) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="4a528-105">By default, the level of transaction safety is set to FULL (synchronous operating mode).</span></span>  
  
 <span data-ttu-id="4a528-106">Wird die Transaktionssicherheit deaktiviert, geht die Sitzung in den asynchronen Betriebsmodus über, in dem die Leistung maximiert wird.</span><span class="sxs-lookup"><span data-stu-id="4a528-106">Turning off transaction safety shifts the session into asynchronous operating mode, which maximizes performance.</span></span> <span data-ttu-id="4a528-107">Falls der Prinzipal nicht mehr verfügbar ist, wird der Spiegel beendet, ist jedoch als betriebsbereit verfügbar (ein Failover erfordert das Erzwingen des Diensts bei möglichem Datenverlust).</span><span class="sxs-lookup"><span data-stu-id="4a528-107">If the principal becomes unavailable, the mirror stops but is available as a warm standby (failover requires forcing service with possible data loss).</span></span>  
  
### <a name="to-turn-on-transaction-safety"></a><span data-ttu-id="4a528-108">So aktivieren Sie die Transaktionssicherheit</span><span class="sxs-lookup"><span data-stu-id="4a528-108">To turn on transaction safety</span></span>  
  
1.  <span data-ttu-id="4a528-109">Stellen Sie eine Verbindung mit dem Prinzipalserver her.</span><span class="sxs-lookup"><span data-stu-id="4a528-109">Connect to the principal server.</span></span>  
  
2.  <span data-ttu-id="4a528-110">Führen Sie die folgende Transact-SQL-Anweisung aus:</span><span class="sxs-lookup"><span data-stu-id="4a528-110">Issue the following Transact-SQL statement:</span></span>  
  
    ```  
    ALTER DATABASE <database> SET PARTNER SAFETY FULL  
    ```  
  
     <span data-ttu-id="4a528-111">Dabei ist *\<database>* der Name der gespiegelten Datenbank.</span><span class="sxs-lookup"><span data-stu-id="4a528-111">where *\<database>* is the name of the mirrored database.</span></span>  
  
### <a name="to-turn-off-transaction-safety"></a><span data-ttu-id="4a528-112">So deaktivieren Sie die Transaktionssicherheit</span><span class="sxs-lookup"><span data-stu-id="4a528-112">To turn off transaction safety</span></span>  
  
1.  <span data-ttu-id="4a528-113">Stellen Sie eine Verbindung mit dem Prinzipalserver her.</span><span class="sxs-lookup"><span data-stu-id="4a528-113">Connect to the principal server.</span></span>  
  
2.  <span data-ttu-id="4a528-114">Führen Sie die folgende Anweisung aus:</span><span class="sxs-lookup"><span data-stu-id="4a528-114">Issue the following statement:</span></span>  
  
    ```  
    ALTER DATABASE <database> SET PARTNER SAFETY OFF  
    ```  
  
     <span data-ttu-id="4a528-115">Dabei ist *\<database>* die gespiegelte Datenbank.</span><span class="sxs-lookup"><span data-stu-id="4a528-115">where *\<database>* is the mirrored database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a528-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4a528-116">See Also</span></span>  
 <span data-ttu-id="4a528-117">[ALTER DATABASE-Datenbankspiegelung &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span><span class="sxs-lookup"><span data-stu-id="4a528-117">[ALTER DATABASE Database Mirroring &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span></span>  
 [<span data-ttu-id="4a528-118">Database Mirroring Operating Modes</span><span class="sxs-lookup"><span data-stu-id="4a528-118">Database Mirroring Operating Modes</span></span>](database-mirroring-operating-modes.md)  
  
  
