---
title: Rowsets | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- rowsets [OLE DB], about rowsets
- SQL Server Native Client OLE DB provider, rowsets
- OLE DB rowsets
- OLE DB rowsets, about rowsets
- rowsets [OLE DB]
ms.assetid: 5e7b3cbe-3670-4e18-8172-2226e0b6b142
author: rothja
ms.author: jroth
ms.openlocfilehash: 1245d17dc0f3757b3c212146c8c162de6e48a483
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615376"
---
# <a name="rowsets"></a><span data-ttu-id="68ccf-102">Rowsets</span><span class="sxs-lookup"><span data-stu-id="68ccf-102">Rowsets</span></span>
  <span data-ttu-id="68ccf-103">Ein Rowset ist ein Satz von Zeilen, die Spalten mit Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="68ccf-103">A rowset is a set of rows that contain columns of data.</span></span> <span data-ttu-id="68ccf-104">Rowsets sind die zentralen Objekte, die es allen OLE DB-Datenanbietern ermöglichen, Resultsetdaten in tabellarischer Form verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="68ccf-104">Rowsets are central objects that enable all OLE DB data providers to expose result set data in tabular form.</span></span>  
  
 <span data-ttu-id="68ccf-105">Nachdem ein Consumer mithilfe der **IDBCreateSession::CreateSession**-Methode eine Sitzung erstellt hat, kann er entweder mit der **IOpenRowset**-Schnittstelle oder der **IDBCreateCommand**-Schnittstelle ein Rowset erstellen.</span><span class="sxs-lookup"><span data-stu-id="68ccf-105">After a consumer creates a session by using the **IDBCreateSession::CreateSession** method, the consumer can use either the **IOpenRowset** or **IDBCreateCommand** interface on the session to create a rowset.</span></span> <span data-ttu-id="68ccf-106">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter unterstützt beide Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="68ccf-106">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports both of these interfaces.</span></span> <span data-ttu-id="68ccf-107">Diese beiden Methoden werden im Folgenden beschrieben.</span><span class="sxs-lookup"><span data-stu-id="68ccf-107">Both of these methods are described here.</span></span>  
  
-   <span data-ttu-id="68ccf-108">Erstellen Sie ein Rowset, indem Sie die **IOpenRowset::OpenRowset**-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="68ccf-108">Create a rowset by calling the **IOpenRowset::OpenRowset** method.</span></span>  
  
     <span data-ttu-id="68ccf-109">Dies entspricht dem Erstellen eines Rowsets über eine einzelne Tabelle.</span><span class="sxs-lookup"><span data-stu-id="68ccf-109">This is equivalent to creating a rowset over a single table.</span></span> <span data-ttu-id="68ccf-110">Die Methode öffnet ein Rowset, das alle Zeilen aus einer einzelnen Basistabelle enthält, und gibt es zurück.</span><span class="sxs-lookup"><span data-stu-id="68ccf-110">This method opens and returns a rowset that includes all of the rows from a single base table.</span></span> <span data-ttu-id="68ccf-111">Eines der Argumente von **OpenRowset** ist eine Tabellen-ID, die die Tabelle identifiziert, aus der das Rowset erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="68ccf-111">One of the arguments to **OpenRowset** is a table ID that identifies the table from which to create the rowset.</span></span>  
  
-   <span data-ttu-id="68ccf-112">Erstellen Sie ein Befehlsobjekt, indem Sie die **IDBCreateCommand::CreateCommand**-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="68ccf-112">Create a command object by calling the **IDBCreateCommand::CreateCommand** method.</span></span>  
  
     <span data-ttu-id="68ccf-113">Das Befehlsobjekt führt Befehle aus, die der Anbieter unterstützt.</span><span class="sxs-lookup"><span data-stu-id="68ccf-113">The command object executes commands that the provider supports.</span></span> <span data-ttu-id="68ccf-114">Im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter kann der Consumer eine beliebige [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisung angeben, beispielsweise eine SELECT-Anweisung oder einen Aufruf einer gespeicherten Prozedur.</span><span class="sxs-lookup"><span data-stu-id="68ccf-114">With the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider, the consumer can specify any [!INCLUDE[tsql](../../includes/tsql-md.md)] statement, such as a SELECT statement or a call to a stored procedure.</span></span> <span data-ttu-id="68ccf-115">Die Schritte zum Erstellen eines Rowsets mit einem Befehlsobjekt sind folgende:</span><span class="sxs-lookup"><span data-stu-id="68ccf-115">The steps for creating a rowset by using a command object are:</span></span>  
  
    1.  <span data-ttu-id="68ccf-116">Der Consumer ruft die **IDBCreateCommand::CreateCommand**-Methode der Sitzung auf, um ein Befehlsobjekt zu erhalten, das die **ICommandText**-Schnittstelle für das Befehlsobjekt anfordert.</span><span class="sxs-lookup"><span data-stu-id="68ccf-116">The consumer calls the **IDBCreateCommand::CreateCommand** method on the session to get a command object requesting the **ICommandText** interface on the command object.</span></span> <span data-ttu-id="68ccf-117">Diese **ICommandText**-Schnittstelle legt den eigentlichen Befehlstext fest und ruft ihn ab.</span><span class="sxs-lookup"><span data-stu-id="68ccf-117">This **ICommandText** interface sets and retrieves the actual command text.</span></span> <span data-ttu-id="68ccf-118">Der Consumer gibt den Textbefehl ein, indem er die **ICommandText::SetCommandText**-Methode aufruft.</span><span class="sxs-lookup"><span data-stu-id="68ccf-118">The consumer fills in the text command by calling the **ICommandText::SetCommandText** method.</span></span>  
  
    2.  <span data-ttu-id="68ccf-119">Der Benutzer ruft die **ICommand::Execute**-Methode für den Befehl auf.</span><span class="sxs-lookup"><span data-stu-id="68ccf-119">The user calls the **ICommand::Execute** method on the command.</span></span> <span data-ttu-id="68ccf-120">Das Rowsetobjekt, das erstellt wird, wenn der Befehl ausgeführt wird, enthält das Resultset aus dem Befehl.</span><span class="sxs-lookup"><span data-stu-id="68ccf-120">The rowset object built when the command executes contains the result set from the command.</span></span>  
  
 <span data-ttu-id="68ccf-121">Der Consumer kann die **ICommandProperties**-Schnittstelle verwenden, um die Eigenschaften des Rowsets, das von dem in den **ICommand::Execute**-Schnittstellen ausgeführten Befehl zurückgegeben wurde, abzurufen oder festzulegen.</span><span class="sxs-lookup"><span data-stu-id="68ccf-121">The consumer can use the **ICommandProperties** interface to get or set the properties for the rowset returned by the command executed by the **ICommand::Execute** interfaces.</span></span> <span data-ttu-id="68ccf-122">Die am häufigsten angeforderten Eigenschaften sind die Schnittstellen, die das Rowset unterstützen muss.</span><span class="sxs-lookup"><span data-stu-id="68ccf-122">The most commonly requested properties are the interfaces the rowset must support.</span></span> <span data-ttu-id="68ccf-123">Zusätzlich zu Schnittstellen kann der Consumer Eigenschaften anfordern, die das Verhalten des Rowsets oder der Schnittstelle verändern.</span><span class="sxs-lookup"><span data-stu-id="68ccf-123">In addition to interfaces, the consumer can request properties that modify the behavior of the rowset or interface.</span></span>  
  
 <span data-ttu-id="68ccf-124">Consumer geben Rowsets mit der **IRowset::Release**-Methode frei.</span><span class="sxs-lookup"><span data-stu-id="68ccf-124">Consumers release rowsets with the **IRowset::Release** method.</span></span> <span data-ttu-id="68ccf-125">Mit der Freigabe eines Rowsets werden alle Zeilenhandles freigegeben, die der Consumer für dieses Rowset besitzt.</span><span class="sxs-lookup"><span data-stu-id="68ccf-125">Releasing a rowset releases any row handles held by the consumer on that rowset.</span></span> <span data-ttu-id="68ccf-126">Accessoren werden jedoch bei der Freigabe eines Rowsets nicht freigegeben.</span><span class="sxs-lookup"><span data-stu-id="68ccf-126">Releasing a rowset does not release the accessors.</span></span> <span data-ttu-id="68ccf-127">Wenn Sie über eine **IAccessor**-Schnittstelle verfügen, muss diese noch freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="68ccf-127">If you have an **IAccessor** interface, it still has to be released.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="68ccf-128">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="68ccf-128">In This Section</span></span>  
  
-   [<span data-ttu-id="68ccf-129">Erstellen eines Rowsets mit 'IopenRowset'</span><span class="sxs-lookup"><span data-stu-id="68ccf-129">Creating a Rowset with IOpenRowset</span></span>](creating-a-rowset-with-iopenrowset.md)  
  
-   [<span data-ttu-id="68ccf-130">Erstellen von Rowsets mit ' ICommand:: Execute '</span><span class="sxs-lookup"><span data-stu-id="68ccf-130">Creating Rowsets with ICommand::Execute</span></span>](creating-rowsets-with-icommand-execute.md)  
  
-   [<span data-ttu-id="68ccf-131">Eigenschaften und Verhaltensweisen von Rowsets</span><span class="sxs-lookup"><span data-stu-id="68ccf-131">Rowset Properties and Behaviors</span></span>](rowset-properties-and-behaviors.md)  
  
-   [<span data-ttu-id="68ccf-132">Rowsets und SQL Server Cursor</span><span class="sxs-lookup"><span data-stu-id="68ccf-132">Rowsets and SQL Server Cursors</span></span>](rowsets-and-sql-server-cursors.md)  
  
-   [<span data-ttu-id="68ccf-133">Abrufen von Zeilen</span><span class="sxs-lookup"><span data-stu-id="68ccf-133">Fetching Rows</span></span>](fetching-rows.md)  
  
-   [<span data-ttu-id="68ccf-134">Abrufen einer einzelnen Zeile mit IRow</span><span class="sxs-lookup"><span data-stu-id="68ccf-134">Fetching a Single Row with IRow</span></span>](fetching-a-single-row-with-irow.md)  
  
-   [<span data-ttu-id="68ccf-135">Bookmarks</span><span class="sxs-lookup"><span data-stu-id="68ccf-135">Bookmarks</span></span>](bookmarks.md)  
  
-   [<span data-ttu-id="68ccf-136">Aktualisieren von Daten in Rowsets</span><span class="sxs-lookup"><span data-stu-id="68ccf-136">Updating Data in Rowsets</span></span>](updating-data-in-rowsets.md)  
  
## <a name="see-also"></a><span data-ttu-id="68ccf-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="68ccf-137">See Also</span></span>  
 [<span data-ttu-id="68ccf-138">SQL Server Native Client &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="68ccf-138">SQL Server Native Client &#40;OLE DB&#41;</span></span>](../native-client/ole-db/sql-server-native-client-ole-db.md)  
  
  
