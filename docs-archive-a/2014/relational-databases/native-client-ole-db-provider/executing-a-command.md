---
title: Ausführen eines Befehls | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- commands [SQL Server Native Client]
- OLE DB, executing commands
- sessions [SQL Server Native Client]
- OLE DB extensions for XML
- SQL Server Native Client OLE DB provider, command execution
ms.assetid: bb0b3cbf-fe45-46ba-b2ec-c5a39e3c7081
author: rothja
ms.author: jroth
ms.openlocfilehash: 41e8da036d5a4b6469a31213247ad7d4edb7dbfe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620831"
---
# <a name="executing-a-command"></a><span data-ttu-id="c5dd1-102">Ausführen eines Befehls</span><span class="sxs-lookup"><span data-stu-id="c5dd1-102">Executing a Command</span></span>
  <span data-ttu-id="c5dd1-103">Nachdem die Verbindung zu einer Datenquelle hergestellt wurde, ruft der Consumer die **IDBCreatSession::CreateSession**-Methode auf, um eine Sitzung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c5dd1-103">After the connection to a data source is established, the consumer calls the **IDBCreateSession::CreateSession** method to create a session.</span></span> <span data-ttu-id="c5dd1-104">Die Sitzung fungiert als Befehl, Rowset oder Transaktionsfactory.</span><span class="sxs-lookup"><span data-stu-id="c5dd1-104">The session acts as a command, rowset, or transaction factory.</span></span>  
  
 <span data-ttu-id="c5dd1-105">Um mit einzelnen Tabellen oder Indizes direkt zu arbeiten, fordert der Consumer die `IOpenRowset`-Schnittstelle an.</span><span class="sxs-lookup"><span data-stu-id="c5dd1-105">To work directly with individual tables or indexes, the consumer requests the `IOpenRowset` interface.</span></span> <span data-ttu-id="c5dd1-106">Die `IOpenRowset::OpenRowset`-Methode öffnet ein Rowset und gibt es zurück, das alle Zeilen aus einer einzelnen Basistabelle oder einem einzelnen Index enthält.</span><span class="sxs-lookup"><span data-stu-id="c5dd1-106">The `IOpenRowset::OpenRowset` method opens and returns a rowset that includes all rows from a single base table or index.</span></span>  
  
 <span data-ttu-id="c5dd1-107">Um einen Befehl auszuführen (z. b. Select \* FROM Authors), fordert der Consumer die- `IDBCreateCommand` Schnittstelle an.</span><span class="sxs-lookup"><span data-stu-id="c5dd1-107">To execute a command (such as SELECT \* FROM Authors), the consumer requests the `IDBCreateCommand` interface.</span></span> <span data-ttu-id="c5dd1-108">Der Consumer kann die `IDBCreateCommand::CreateCommand`-Methode ausführen, um ein Befehlsobjekt und eine Anforderung für die `ICommandText`-Schnittstelle zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c5dd1-108">The consumer can execute the `IDBCreateCommand::CreateCommand` method to create a command object and request for the `ICommandText` interface.</span></span> <span data-ttu-id="c5dd1-109">Die `ICommandText::SetCommandText`-Methode wird verwendet, um den Befehl anzugeben, der ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c5dd1-109">The `ICommandText::SetCommandText` method is used to specify the command that is to be executed.</span></span>  
  
 <span data-ttu-id="c5dd1-110">Der `Execute`-Befehl wird zum Ausführen des Befehls verwendet.</span><span class="sxs-lookup"><span data-stu-id="c5dd1-110">The `Execute` command is used to execute the command.</span></span> <span data-ttu-id="c5dd1-111">Bei dem Befehl kann es sich um jede SQL-Anweisung oder jeden Prozedurnamen handeln.</span><span class="sxs-lookup"><span data-stu-id="c5dd1-111">The command can be any SQL statement or procedure name.</span></span> <span data-ttu-id="c5dd1-112">Nicht alle Befehle erzeugen ein Resultsetobjekt (Rowset).</span><span class="sxs-lookup"><span data-stu-id="c5dd1-112">Not all commands produce a result set (rowset) object.</span></span> <span data-ttu-id="c5dd1-113">Befehle, wie z. B. SELECT \* FROM Authors, erzeugen ein Resultset.</span><span class="sxs-lookup"><span data-stu-id="c5dd1-113">Commands such as SELECT \* FROM Authors produce a result set.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5dd1-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c5dd1-114">See Also</span></span>  
 [<span data-ttu-id="c5dd1-115">Erstellen einer SQL Server Native Client OLE DB-Anbieteranwendung</span><span class="sxs-lookup"><span data-stu-id="c5dd1-115">Creating a SQL Server Native Client OLE DB Provider Application</span></span>](creating-a-sql-server-native-client-ole-db-provider-application.md)  
  
  
