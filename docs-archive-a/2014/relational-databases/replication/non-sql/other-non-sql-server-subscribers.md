---
title: Andere Nicht-SQL Server-Abonnenten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- non-SQL Server Subscribers, other types
ms.assetid: 96b8beb9-38e8-4ce4-97ca-c0f8656b73b4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3849ca717e82bcf1bed5769190c9f898209a454a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607648"
---
# <a name="other-non-sql-server-subscribers"></a><span data-ttu-id="b259a-102">Andere Nicht-SQL Server-Abonnenten</span><span class="sxs-lookup"><span data-stu-id="b259a-102">Other Non-SQL Server Subscribers</span></span>
  <span data-ttu-id="b259a-103">Eine Liste der von[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] unterstützten Nicht- [!INCLUDE[msCoName](../../../includes/msconame-md.md)]-Abonnenten finden Sie unter [Non-SQL Server Subscribers](non-sql-server-subscribers.md).</span><span class="sxs-lookup"><span data-stu-id="b259a-103">For a list of non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Subscribers supported by [!INCLUDE[msCoName](../../../includes/msconame-md.md)], see [Non-SQL Server Subscribers](non-sql-server-subscribers.md).</span></span> <span data-ttu-id="b259a-104">Dieses Thema enthält Informationen zu den Anforderungen für ODBC-Treiber und OLE DB-Anbieter.</span><span class="sxs-lookup"><span data-stu-id="b259a-104">This topic includes information about requirements for ODBC drivers and OLE DB providers.</span></span>  
  
## <a name="odbc-driver-requirements"></a><span data-ttu-id="b259a-105">Anforderungen für ODBC-Treiber</span><span class="sxs-lookup"><span data-stu-id="b259a-105">ODBC Driver Requirements</span></span>  
 <span data-ttu-id="b259a-106">Der ODBC-Treiber muss folgende Voraussetzungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="b259a-106">The ODBC driver:</span></span>  
  
-   <span data-ttu-id="b259a-107">Er muss ODBC Level-1-kompatibel sein.</span><span class="sxs-lookup"><span data-stu-id="b259a-107">Must be ODBC level-1 compliant.</span></span>  
  
-   <span data-ttu-id="b259a-108">Er muss threadsicher sein und sich für die Prozessorarchitektur (Intel oder Alpha) und die Plattform (32 Bit oder 64 Bit) eignen, auf der der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Verteiler ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b259a-108">Must be thread-safe, and for the processor architecture (Intel or Alpha) and platform (32 bit or 64 bit) on which the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Distributor runs.</span></span>  
  
-   <span data-ttu-id="b259a-109">Er muss in der Lage sein, Transaktionen zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="b259a-109">Must be transaction capable.</span></span>  
  
-   <span data-ttu-id="b259a-110">Er muss die Datendefinitionssprache (Data Definition Language, DDL) unterstützen.</span><span class="sxs-lookup"><span data-stu-id="b259a-110">Must support the Data Definition Language (DDL).</span></span>  
  
-   <span data-ttu-id="b259a-111">Er darf nicht schreibgeschützt sein.</span><span class="sxs-lookup"><span data-stu-id="b259a-111">Cannot be read-only.</span></span>  
  
-   <span data-ttu-id="b259a-112">Er muss lange Tabellennamen unterstützen, wie z. B. **MSreplication_subscriptions**.</span><span class="sxs-lookup"><span data-stu-id="b259a-112">Must support long table names such as **MSreplication_subscriptions**.</span></span>  
  
## <a name="replicating-using-ole-db-interfaces"></a><span data-ttu-id="b259a-113">Replikation mithilfe von OLE DB-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="b259a-113">Replicating Using OLE DB Interfaces</span></span>  
 <span data-ttu-id="b259a-114">OLE DB-Anbieter müssen folgende Objekte für die Transaktionsreplikation unterstützen.</span><span class="sxs-lookup"><span data-stu-id="b259a-114">OLE DB providers must support these objects for transactional replication:</span></span>  
  
-   <span data-ttu-id="b259a-115">**DataSource** -Objekt</span><span class="sxs-lookup"><span data-stu-id="b259a-115">**DataSource** object</span></span>  
  
-   <span data-ttu-id="b259a-116">**Session** -Objekt</span><span class="sxs-lookup"><span data-stu-id="b259a-116">**Session** object</span></span>  
  
-   <span data-ttu-id="b259a-117">**Command** -Objekt</span><span class="sxs-lookup"><span data-stu-id="b259a-117">**Command** object</span></span>  
  
-   <span data-ttu-id="b259a-118">**Rowset** -Objekt</span><span class="sxs-lookup"><span data-stu-id="b259a-118">**Rowset** object</span></span>  
  
-   <span data-ttu-id="b259a-119">**Error** -Objekt</span><span class="sxs-lookup"><span data-stu-id="b259a-119">**Error** object</span></span>  
  
### <a name="datasource-object-interfaces"></a><span data-ttu-id="b259a-120">Schnittstellen für DataSource-Objekte</span><span class="sxs-lookup"><span data-stu-id="b259a-120">DataSource Object Interfaces</span></span>  
 <span data-ttu-id="b259a-121">Die folgenden Schnittstellen sind erforderlich, um eine Verbindung mit einer Datenquelle herzustellen:</span><span class="sxs-lookup"><span data-stu-id="b259a-121">The following interfaces are required to connect to a data source:</span></span>  
  
-   `IDBInitialize`  
  
-   `IDBCreateSession`  
  
-   `IDBProperties`  
  
 <span data-ttu-id="b259a-122">Wenn der Anbieter die Schnittstelle **IDBInfo** unterstützt, wird sie von [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] verwendet, um Informationen wie den Bezeichner in Anführungszeichen, die maximale Länge einer SQL-Anweisung und die maximale Anzahl von Zeichen in Tabellen- und Spaltennamen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="b259a-122">If the provider supports the **IDBInfo** interface, [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] uses the interface to retrieve information such as the quoted identifier character, maximum SQL statement length, and maximum number of characters in table and column names.</span></span>  
  
### <a name="session-object-interfaces"></a><span data-ttu-id="b259a-123">Schnittstellen für Session-Objekte</span><span class="sxs-lookup"><span data-stu-id="b259a-123">Session Object Interfaces</span></span>  
 <span data-ttu-id="b259a-124">Die folgenden Schnittstellen sind erforderlich:</span><span class="sxs-lookup"><span data-stu-id="b259a-124">The following interfaces are required:</span></span>  
  
-   <span data-ttu-id="b259a-125">**IDBCreateCommand**</span><span class="sxs-lookup"><span data-stu-id="b259a-125">**IDBCreateCommand**</span></span>  
  
-   <span data-ttu-id="b259a-126">**ITransaction**</span><span class="sxs-lookup"><span data-stu-id="b259a-126">**ITransaction**</span></span>  
  
-   <span data-ttu-id="b259a-127">**ITransactionLocal**</span><span class="sxs-lookup"><span data-stu-id="b259a-127">**ITransactionLocal**</span></span>  
  
-   <span data-ttu-id="b259a-128">**IDBSchemaRowset**</span><span class="sxs-lookup"><span data-stu-id="b259a-128">**IDBSchemaRowset**</span></span>  
  
### <a name="command-object-interfaces"></a><span data-ttu-id="b259a-129">Schnittstellen für Command-Objekte</span><span class="sxs-lookup"><span data-stu-id="b259a-129">Command Object Interfaces</span></span>  
 <span data-ttu-id="b259a-130">Die folgenden Schnittstellen sind erforderlich:</span><span class="sxs-lookup"><span data-stu-id="b259a-130">The following interfaces are required:</span></span>  
  
-   <span data-ttu-id="b259a-131">**ICommand**</span><span class="sxs-lookup"><span data-stu-id="b259a-131">**ICommand**</span></span>  
  
-   <span data-ttu-id="b259a-132">**ICommandProperties**</span><span class="sxs-lookup"><span data-stu-id="b259a-132">**ICommandProperties**</span></span>  
  
-   <span data-ttu-id="b259a-133">**ICommandText**</span><span class="sxs-lookup"><span data-stu-id="b259a-133">**ICommandText**</span></span>  
  
-   <span data-ttu-id="b259a-134">**ICommandPrepare**</span><span class="sxs-lookup"><span data-stu-id="b259a-134">**ICommandPrepare**</span></span>  
  
-   <span data-ttu-id="b259a-135">**IColumnsInfo**</span><span class="sxs-lookup"><span data-stu-id="b259a-135">**IColumnsInfo**</span></span>  
  
-   <span data-ttu-id="b259a-136">**IAccessor**</span><span class="sxs-lookup"><span data-stu-id="b259a-136">**IAccessor**</span></span>  
  
-   <span data-ttu-id="b259a-137">**ICommandWithParameters**</span><span class="sxs-lookup"><span data-stu-id="b259a-137">**ICommandWithParameters**</span></span>  
  
 <span data-ttu-id="b259a-138">**IAccessor** ist zum Erstellen von Parameterzugriffen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b259a-138">**IAccessor** is necessary to create parameter accessors.</span></span> <span data-ttu-id="b259a-139">Wenn der Anbieter **IColumnRowset**unterstützt, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] verwendet diese Schnittstelle, um zu bestimmen, ob eine Spalte eine Identitäts Spalte ist.</span><span class="sxs-lookup"><span data-stu-id="b259a-139">If the provider supports **IColumnRowset**, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] uses that interface to determine whether a column is an identity column.</span></span>  
  
### <a name="rowset-object-interfaces"></a><span data-ttu-id="b259a-140">Schnittstellen für Rowset-Objekte</span><span class="sxs-lookup"><span data-stu-id="b259a-140">Rowset Object Interfaces</span></span>  
 <span data-ttu-id="b259a-141">Die folgenden Schnittstellen sind erforderlich:</span><span class="sxs-lookup"><span data-stu-id="b259a-141">The following interfaces are required:</span></span>  
  
-   <span data-ttu-id="b259a-142">**IRowset**</span><span class="sxs-lookup"><span data-stu-id="b259a-142">**IRowset**</span></span>  
  
-   <span data-ttu-id="b259a-143">**IAccessor**</span><span class="sxs-lookup"><span data-stu-id="b259a-143">**IAccessor**</span></span>  
  
-   <span data-ttu-id="b259a-144">**IColumnsInfo**</span><span class="sxs-lookup"><span data-stu-id="b259a-144">**IColumnsInfo**</span></span>  
  
 <span data-ttu-id="b259a-145">Eine Anwendung sollte ein Rowset für eine replizierte Tabelle öffnen, das in der Abonnementdatenbank erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="b259a-145">An application should open a rowset on a replicated table that is created in the subscription database.</span></span> <span data-ttu-id="b259a-146">**IColumnsInfo** und **IAccessor** werden zum Zugreifen auf Daten im Rowset benötigt.</span><span class="sxs-lookup"><span data-stu-id="b259a-146">**IColumnsInfo** and **IAccessor** are needed to access data in the rowset.</span></span>  
  
### <a name="error-object-interfaces"></a><span data-ttu-id="b259a-147">Schnittstellen für Error-Objekte</span><span class="sxs-lookup"><span data-stu-id="b259a-147">Error Object Interfaces</span></span>  
 <span data-ttu-id="b259a-148">Verwenden Sie die folgenden Schnittstellen zur Verwaltung von Fehlern:</span><span class="sxs-lookup"><span data-stu-id="b259a-148">Use the following interfaces to manage errors:</span></span>  
  
-   <span data-ttu-id="b259a-149">**IErrorRecords**</span><span class="sxs-lookup"><span data-stu-id="b259a-149">**IErrorRecords**</span></span>  
  
-   <span data-ttu-id="b259a-150">**IErrorInfo**</span><span class="sxs-lookup"><span data-stu-id="b259a-150">**IErrorInfo**</span></span>  
  
 <span data-ttu-id="b259a-151">Verwenden Sie **ISQLErrorInfo** , wenn diese Schnittstelle vom OLE DB-Anbieter unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="b259a-151">Use **ISQLErrorInfo** if it is supported by the OLE DB provider.</span></span>  
  
 <span data-ttu-id="b259a-152">Weitere Informationen zum OLE DB-Anbieter finden Sie in der Dokumentation zum jeweiligen OLE DB-Anbieter.</span><span class="sxs-lookup"><span data-stu-id="b259a-152">For more information about the OLE DB provider, see the documentation supplied with your OLE DB provider.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b259a-153">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b259a-153">See Also</span></span>  
 [<span data-ttu-id="b259a-154">Nicht-SQL Server-Abonnenten</span><span class="sxs-lookup"><span data-stu-id="b259a-154">Non-SQL Server Subscribers</span></span>](non-sql-server-subscribers.md)  
  
  
