---
title: Datenzugriff von CLR-Datenbankobjekten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- common language runtime [SQL Server], data access
- routines [CLR integration]
- data access [CLR integration]
- ADO.NET [CLR integration]
- internal data access [CLR integration]
- common language runtime [SQL Server], ADO.NET
- database objects [CLR integration], data access
- managed code [SQL Server], database objects
- .NET Data Access Provider for SQL Server [CLR integration]
- managed code [SQL Server], data access
- SqlClient provider
- in-process data access providers [CLR integration]
ms.assetid: 9a0f4dee-71c1-42e9-a85e-52382807010f
author: rothja
ms.author: jroth
ms.openlocfilehash: d229d490a9f3a7bc6f613259ee0535218de47975
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621513"
---
# <a name="data-access-from-clr-database-objects"></a><span data-ttu-id="52939-102">Data Access from CLR Database Objects</span><span class="sxs-lookup"><span data-stu-id="52939-102">Data Access from CLR Database Objects</span></span>
  <span data-ttu-id="52939-103">Eine Common Language Runtime-Routine (CLR) kann problemlos auf Daten zugreifen, die in der Instanz von gespeichert [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] sind, in der Sie ausgeführt wird, sowie auf Daten, die in Remote Instanzen gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="52939-103">A common language runtime (CLR) routine may easily access data stored in the instance of [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] in which it runs, as well as data stored in remote instances.</span></span> <span data-ttu-id="52939-104">Auf welche Daten die Routine zugreifen kann, wird durch den Benutzerkontext bestimmt, in dem der Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="52939-104">Which particular data the routine can access is determined by the user context in which the code is running.</span></span> <span data-ttu-id="52939-105">Greifen Sie in einem CLR-Datenbankobjekt auf Daten zu, indem Sie die .NET Framework Datenanbieter für [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Daten von verwalteten Clients und Anwendungen der mittleren Ebene verwenden.</span><span class="sxs-lookup"><span data-stu-id="52939-105">Access data from within a CLR database object by using the .NET Framework Data Provider for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data from managed client and middle-tier applications.</span></span> <span data-ttu-id="52939-106">Daher können Sie Ihre ADO.NET- und `SqlClient`-Kenntnisse in Clientanwendungen und Anwendungen der mittleren Ebene nutzen.</span><span class="sxs-lookup"><span data-stu-id="52939-106">Because of this, you can leverage your knowledge of ADO.NET and `SqlClient` in client and middle-tier applications.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="52939-107">Benutzerdefinierten Typmethoden und benutzerdefinierten Funktionen wird nicht ermöglicht, standardmäßig auf Daten zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="52939-107">User-defined type methods and user-defined functions are not allowed to perform data access by default.</span></span> <span data-ttu-id="52939-108">Sie müssen die `DataAccess`-Eigenschaft von `SqlMethodAttribute` oder `SqlFunctionAttribute` auf `DataAccessKind.Read` festlegen, um schreibgeschützten Datenzugriff von benutzerdefinierten Typmethoden (User Defined Type, UDT) oder benutzerdefinierten Funktionen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="52939-108">You must set the `DataAccess` property of `SqlMethodAttribute` or `SqlFunctionAttribute` to `DataAccessKind.Read` to enable read-only data access from user-defined type (UDT) methods or user-defined functions.</span></span> <span data-ttu-id="52939-109">Datenänderungsvorgänge von UDTs oder benutzerdefinierten Funktionen ausgehend sind nicht zulässig. Ein solcher Versuch löst zur Ausführungszeit eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="52939-109">Data modification operations are not allowed from UDTs or user-defined functions, and throws exceptions at execution time if attempted.</span></span>  
  
 <span data-ttu-id="52939-110">In diesem Abschnitt werden nur die spezifischen Unterschiede der Funktionen und Verhaltensweisen beim Datenzugriff von einem CLR-Datenbankobjekt ausgehend beschrieben.</span><span class="sxs-lookup"><span data-stu-id="52939-110">This section discusses only the specific functional and behavioral differences when accessing data from within a CLR database object.</span></span> <span data-ttu-id="52939-111">Weitere Informationen zu Funktionen und Funktionalität von ADO.NET finden Sie in der ADO.NET-Dokumentation im .NET Framework SDK.</span><span class="sxs-lookup"><span data-stu-id="52939-111">For more information about the features and functionality of ADO.NET, see the ADO.NET documentation included in the .NET Framework SDK.</span></span>  
  
 <span data-ttu-id="52939-112">In der folgenden Tabelle sind die Themen dieses Abschnitts aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="52939-112">The following table lists the topics in this section.</span></span>  
  
 [<span data-ttu-id="52939-113">Kontextverbindung</span><span class="sxs-lookup"><span data-stu-id="52939-113">Context Connection</span></span>](context-connection.md)  
 <span data-ttu-id="52939-114">Beschreibt die Kontextverbindung zu SQL Server.</span><span class="sxs-lookup"><span data-stu-id="52939-114">Describes the context connection to SQL Server.</span></span>  
  
 [<span data-ttu-id="52939-115">Identitätswechsel und Anmeldeinformationen für Verbindungen</span><span class="sxs-lookup"><span data-stu-id="52939-115">Impersonation and Credentials for Connections</span></span>](impersonation-and-credentials-for-connections.md)  
 <span data-ttu-id="52939-116">Beschreibt die Annahme der Identität von Verbindungen und Verbindungsanmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="52939-116">Describes impersonating connections and connection credentials.</span></span>  
  
 [<span data-ttu-id="52939-117">Von SQL Server verwendete prozessinterne spezifische Erweiterungen für ADO.NET</span><span class="sxs-lookup"><span data-stu-id="52939-117">SQL Server In-Process Specific Extensions to ADO.NET</span></span>](../../clr-integration-data-access-in-process-ado-net/sql-server-in-process-specific-extensions-to-ado-net.md)  
 <span data-ttu-id="52939-118">Erläutert die prozessinternen spezifischen `SqlPipe`, `SqlContext`, `SqlTriggerContext` und `SqlDataRecord`-Objekte.</span><span class="sxs-lookup"><span data-stu-id="52939-118">Discusses the in-process specific `SqlPipe`, `SqlContext`, `SqlTriggerContext`, and `SqlDataRecord` objects.</span></span>  
  
 [<span data-ttu-id="52939-119">CLR-Integration und Transaktionen</span><span class="sxs-lookup"><span data-stu-id="52939-119">CLR Integration and Transactions</span></span>](../../native-client-ole-db-transactions/transactions.md)  
 <span data-ttu-id="52939-120">Beschreibt wie das neue vom System.Transactions-Namespace bereitgestellte Transaktionsframework in ADO.NET und [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-CLRIntegration einbezogen wird.</span><span class="sxs-lookup"><span data-stu-id="52939-120">Describes how the new transaction framework provided in the System.Transactions namespace integrates with ADO.NET and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] CLR integration.</span></span>  
  
 [<span data-ttu-id="52939-121">XML-Serialisierung auf Grundlage von CLR-Datenbankobjekten</span><span class="sxs-lookup"><span data-stu-id="52939-121">XML Serialization from CLR Database Objects</span></span>](../../../database-engine/dev-guide/xml-serialization-from-clr-database-objects.md)  
 <span data-ttu-id="52939-122">Erklärt, wie XML-Serialisierungsszenarien von CLR-Datenbankobjekten in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="52939-122">Explains how to enable XML serialization scenarios of CLR database objects inside [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
  
