---
title: SQL Server Native Client Unterstützung für localdb | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: 127569d1-a9f7-49bf-a561-c084986a8871
author: rothja
ms.author: jroth
ms.openlocfilehash: b08ea46e8db1b665280116a439b95748f69d03ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615360"
---
# <a name="sql-server-native-client-support-for-localdb"></a><span data-ttu-id="4080a-102">SQL Server Native Client-Unterstützung für LocalDB</span><span class="sxs-lookup"><span data-stu-id="4080a-102">SQL Server Native Client Support for LocalDB</span></span>
  <span data-ttu-id="4080a-103">Ab [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)]ist eine vereinfachte Version von SQL Server mit dem Namen LocalDB verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4080a-103">Beginning in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], a lightweight version of SQL Server, called LocalDB, will be available.</span></span> <span data-ttu-id="4080a-104">In diesem Thema wird erläutert, wie in einer LocalDB-Instanz eine Verbindung mit einer Datenbank hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="4080a-104">This topic discusses how to connect to a database in a LocalDB instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4080a-105">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="4080a-105">Remarks</span></span>  
 <span data-ttu-id="4080a-106">Weitere Informationen zu LocalDB, einschließlich der Installation von LocalDB und der Konfiguration der LocalDB-Instanz, finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="4080a-106">For more information about LocalDB, including how to install LocalDB and configure your LocalDB instance, see:</span></span>  
  
-   [<span data-ttu-id="4080a-107">SQL Server Express LocalDB-Verweis</span><span class="sxs-lookup"><span data-stu-id="4080a-107">SQL Server Express LocalDB Reference</span></span>](../../sql-server-express-localdb-reference.md)  
  
-   [<span data-ttu-id="4080a-108">SQL Server 2014 Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="4080a-108">SQL Server 2014 Express LocalDB</span></span>](../../../database-engine/configure-windows/sql-server-2016-express-localdb.md)  
  
 <span data-ttu-id="4080a-109">Zusammenfassend erlaubt LocalDB Ihnen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="4080a-109">To summarize, LocalDB allows you to:</span></span>  
  
-   <span data-ttu-id="4080a-110">Verwenden Sie `sqllocaldb.exe i`, um den Namen der Standardinstanz zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="4080a-110">Use `sqllocaldb.exe i` to discover the name of the default instance.</span></span>  
  
-   <span data-ttu-id="4080a-111">Verwenden Sie das Schlüsselwort der `AttachDBFilename`-Verbindungszeichenfolge, um anzugeben, welche Datenbankdatei der Server anfügen soll.</span><span class="sxs-lookup"><span data-stu-id="4080a-111">Use the `AttachDBFilename` connection string keyword to specify which database file the server should attach.</span></span> <span data-ttu-id="4080a-112">Wenn `AttachDBFilename` Sie verwenden, wenn Sie den Namen der Datenbank nicht mit dem Schlüsselwort für die **Daten bankverbindungs** Zeichenfolge angeben, wird die Datenbank aus der localdb-Instanz entfernt, wenn die Anwendung geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="4080a-112">When using `AttachDBFilename`, if you do not specify the name of the database with the **Database** connection string keyword, the database will be removed from the LocalDB instance when the application closes.</span></span>  
  
-   <span data-ttu-id="4080a-113">Geben Sie in der Verbindungszeichenfolge eine LocalDB-Instanz an:</span><span class="sxs-lookup"><span data-stu-id="4080a-113">Specify a LocalDB instance in your connection string:</span></span>  
  
```  
SERVER=(localdb)\v11.0  
```  
  
 <span data-ttu-id="4080a-114">Falls notwendig können Sie eine LocalDB-Instanz mit "sqllocaldb.exe" erstellen.</span><span class="sxs-lookup"><span data-stu-id="4080a-114">If necessary, you can create a LocalDB instance with sqllocaldb.exe.</span></span> <span data-ttu-id="4080a-115">Sie können auch "sqlcmd.exe" verwenden, um Datenbanken in einer LocalDB-Instanz hinzuzufügen und zu ändern.</span><span class="sxs-lookup"><span data-stu-id="4080a-115">You can also use sqlcmd.exe to add and modify databases in a LocalDB instance.</span></span> <span data-ttu-id="4080a-116">Beispiel: `sqlcmd -S (localdb)\v11.0`.</span><span class="sxs-lookup"><span data-stu-id="4080a-116">For example, `sqlcmd -S (localdb)\v11.0`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4080a-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4080a-117">See Also</span></span>  
 [<span data-ttu-id="4080a-118">SQL Server Native Client-Funktionen</span><span class="sxs-lookup"><span data-stu-id="4080a-118">SQL Server Native Client Features</span></span>](sql-server-native-client-features.md)  
  
  
