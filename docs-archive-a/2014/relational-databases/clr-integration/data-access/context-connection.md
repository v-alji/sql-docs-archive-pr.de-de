---
title: Kontext Verbindung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- context connections [CLR integration]
- database objects [CLR integration], connections
- connections [CLR integration]
- context [CLR integration]
ms.assetid: 67dd1925-d672-4986-a85f-bce4fe832ef7
author: rothja
ms.author: jroth
ms.openlocfilehash: 82c739aa9c1952c71e9a16aaa68ec999851b3202
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617118"
---
# <a name="context-connection"></a><span data-ttu-id="c75c7-102">Kontextverbindung</span><span class="sxs-lookup"><span data-stu-id="c75c7-102">Context Connection</span></span>
  <span data-ttu-id="c75c7-103">Der interne Datenzugriff ist ein verbreitetes Problem.</span><span class="sxs-lookup"><span data-stu-id="c75c7-103">The problem of internal data access is a fairly common scenario.</span></span> <span data-ttu-id="c75c7-104">Es tritt auf, wenn Sie auf denselben Server zugreifen möchten, auf dem auch die CLR-gespeicherte Prozedur (Common Language Runtime, CLR) oder -Funktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c75c7-104">That is, you wish to access the same server on which your common language runtime (CLR) stored procedure or function is executing.</span></span> <span data-ttu-id="c75c7-105">Eine der Optionen besteht darin, mithilfe von `System.Data.SqlClient.SqlConnection` eine Verbindung zu erstellen, eine Verbindungszeichenfolge anzugeben, die auf den lokalen Server zeigt, und die Verbindung anschließend zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="c75c7-105">One option is to create a connection using `System.Data.SqlClient.SqlConnection`, specify a connection string that points to the local server, and open the connection.</span></span> <span data-ttu-id="c75c7-106">Dies erfordert die Angabe von Anmeldeinformationen für die Anmeldung.</span><span class="sxs-lookup"><span data-stu-id="c75c7-106">This requires specifying credentials for logging in.</span></span> <span data-ttu-id="c75c7-107">Die Verbindung wurde in einer anderen Datenbanksitzung als die gespeicherte Prozedur oder Funktion hergestellt, sie verwendet möglicherweise andere `SET`-Optionen, befindet sich in einer separaten Transaktion, hat keinen Zugriff auf die temporären Tabellen usw.</span><span class="sxs-lookup"><span data-stu-id="c75c7-107">The connection is in a different database session than the stored procedure or function, it may have different `SET` options, it is in a separate transaction, it does not see your temporary tables, and so on.</span></span> <span data-ttu-id="c75c7-108">Wenn der Code Ihrer verwalteten gespeicherten Prozedur oder Funktion im SQL Serverprozess ausgeführt wird, liegt das daran, dass jemand eine Verbindung mit diesem Server hergestellt und eine SQL-Anweisung ausgeführt hat, um den Code aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="c75c7-108">If your managed stored procedure or function code is executing in the SQL Server process, it is because someone connected to that server and executed a SQL statement to invoke it.</span></span> <span data-ttu-id="c75c7-109">Nun möchten Sie eventuell die gespeicherte Prozedur oder Funktion im Kontext dieser Verbindung ausführen, zusammen mit deren Transaktion, `SET`-Optionen und so weiter.</span><span class="sxs-lookup"><span data-stu-id="c75c7-109">You probably want the stored procedure or function to execute in the context of that connection, along with its transaction, `SET` options, and so on.</span></span> <span data-ttu-id="c75c7-110">Dies wird als Kontextverbindung bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="c75c7-110">This is called the context connection.</span></span>  
  
 <span data-ttu-id="c75c7-111">Die Kontextverbindung ermöglicht, Transact-SQL-Anweisungen im selben Kontext auszuführen wie den Code, der anfänglich aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="c75c7-111">The context connection lets you execute Transact-SQL statements in the same context that your code was invoked in the first place.</span></span> <span data-ttu-id="c75c7-112">Um die Kontextverbindung herzustellen, müssen Sie "context connection", das Schlüsselwort für die Verbindungszeichenfolge der Kontextverbindung, verwenden, wie im nachstehenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="c75c7-112">In order to obtain the context connection, you must use the "context connection" connection string keyword, as in the example below:</span></span>  
  
 <span data-ttu-id="c75c7-113">[C#]</span><span class="sxs-lookup"><span data-stu-id="c75c7-113">[C#]</span></span>  
  
```  
using(SqlConnection connection = new SqlConnection("context connection=true"))   
{  
    connection.Open();  
    // Use the connection  
}  
```  
  
 <span data-ttu-id="c75c7-114">[Visual Basic]</span><span class="sxs-lookup"><span data-stu-id="c75c7-114">[Visual Basic]</span></span>  
  
```  
Using connection as new SqlConnection("context connection=true")  
    connection.Open()  
    ' Use the connection  
End Using  
  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="c75c7-115">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c75c7-115">In This Section</span></span>  
 [<span data-ttu-id="c75c7-116">Reguläre vs. Kontextverbindungen</span><span class="sxs-lookup"><span data-stu-id="c75c7-116">Regular vs. Context Connections</span></span>](context-connections-vs-regular-connections.md)  
 <span data-ttu-id="c75c7-117">Beschreibt die Unterschiede zwischen regulären Verbindungen und Kontextverbindungen.</span><span class="sxs-lookup"><span data-stu-id="c75c7-117">Describes the differences between regular and context connections.</span></span>  
  
 [<span data-ttu-id="c75c7-118">Einschränkungen hinsichtlich regulärer Verbindungen und Kontextverbindungen</span><span class="sxs-lookup"><span data-stu-id="c75c7-118">Restrictions on Regular and Context Connections</span></span>](context-connections-and-regular-connections-restrictions.md)  
 <span data-ttu-id="c75c7-119">Beschreibt die Einschränkungen hinsichtlich regulärer Verbindungen und Kontextverbindungen.</span><span class="sxs-lookup"><span data-stu-id="c75c7-119">Describes the restrictions on regular and context connections.</span></span>  
  
  
