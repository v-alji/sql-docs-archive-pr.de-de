---
title: SQL Server Native Client (OLE DB) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, about SQL Server Native Client OLE DB provider
- OLE DB, SQL Server Native Client OLE DB provider
- data access [SQL Server Native Client], OLE DB
- SQLNCLI, OLE DB
- OLE DB
- SQL Server Native Client OLE DB provider
- SQL Server Native Client, OLE DB
ms.assetid: da846da4-ec19-4a4f-81fb-7d5a2b2bf80a
author: rothja
ms.author: jroth
ms.openlocfilehash: 46b948eb1d075edc6000849dcb2d18ea372809d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616512"
---
# <a name="sql-server-native-client-ole-db"></a><span data-ttu-id="56117-102">SQL Server Native Client (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="56117-102">SQL Server Native Client (OLE DB)</span></span>
  <span data-ttu-id="56117-103">Der OLE DB-Anbieter von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ist eine untergeordnete COM-API für den Datenzugriff.</span><span class="sxs-lookup"><span data-stu-id="56117-103">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider is a low-level COM API that is used for accessing data.</span></span> <span data-ttu-id="56117-104">Der OLE DB-Anbieter von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client wird für die Entwicklung von Tools, Hilfsprogrammen oder untergeordneten Komponenten empfohlen, die eine hohe Leistung erfordern.</span><span class="sxs-lookup"><span data-stu-id="56117-104">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider is recommended for developing tools, utilities, or low-level components that need high performance.</span></span> <span data-ttu-id="56117-105">Der OLE DB-Anbieter von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ist ein systemeigener Hochleistungsanbieter, der direkt auf das [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-TDS-Protokoll (Tabular Data Stream) zugreift.</span><span class="sxs-lookup"><span data-stu-id="56117-105">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider is a native, high performance provider that accesses the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Tabular Data Stream (TDS) protocol directly.</span></span>  
  
 <span data-ttu-id="56117-106">Der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client stellt OLE DB-Unterstützung für Anwendungen zur Verfügung, die eine Verbindung zu [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] herstellen.</span><span class="sxs-lookup"><span data-stu-id="56117-106">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client provides OLE DB support to applications connecting to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="56117-107">Der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter ist ein OLE DB, Version 2,0-kompatibler Anbieter.</span><span class="sxs-lookup"><span data-stu-id="56117-107">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider is an OLE DB version 2.0-compliant provider.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="56117-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="56117-108">In This Section</span></span>  
  
-   [<span data-ttu-id="56117-109">Erstellen einer SQL Server Native Client OLE DB-Anbieteranwendung</span><span class="sxs-lookup"><span data-stu-id="56117-109">Creating a SQL Server Native Client OLE DB Provider Application</span></span>](../../native-client-ole-db-provider/creating-a-sql-server-native-client-ole-db-provider-application.md)  
  
-   [<span data-ttu-id="56117-110">Datenquellenobjekte &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="56117-110">Data Source Objects &#40;OLE DB&#41;</span></span>](../../native-client-ole-db-data-source-objects/data-source-objects-ole-db.md)  
  
-   [<span data-ttu-id="56117-111">Befehle</span><span class="sxs-lookup"><span data-stu-id="56117-111">Commands</span></span>](../../native-client-ole-db-commands/commands.md)  
  
-   [<span data-ttu-id="56117-112">Rowsets</span><span class="sxs-lookup"><span data-stu-id="56117-112">Rowsets</span></span>](../../native-client-ole-db-rowsets/rowsets.md)  
  
-   [<span data-ttu-id="56117-113">Gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="56117-113">Stored Procedures</span></span>](stored-procedures.md)  
  
-   [<span data-ttu-id="56117-114">BLOBs und OLE-Objekte</span><span class="sxs-lookup"><span data-stu-id="56117-114">BLOBs and OLE Objects</span></span>](../../native-client-ole-db-blobs/blobs-and-ole-objects.md)  
  
-   [<span data-ttu-id="56117-115">Tabellen und Indizes</span><span class="sxs-lookup"><span data-stu-id="56117-115">Tables and Indexes</span></span>](../../native-client-ole-db-tables-indexes/tables-and-indexes.md)  
  
-   [<span data-ttu-id="56117-116">Datentypen &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="56117-116">Data Types &#40;OLE DB&#41;</span></span>](../../native-client-ole-db-data-types/data-types-ole-db.md)  
  
-   [<span data-ttu-id="56117-117">Schema Rowset Support &#40;OLE DB&#41; (Schemarowset-Unterstützung &#40;OLE DB&#41;)</span><span class="sxs-lookup"><span data-stu-id="56117-117">Schema Rowset Support &#40;OLE DB&#41;</span></span>](schema-rowset-support-ole-db.md)  
  
-   [<span data-ttu-id="56117-118">Tabellenwertparameter &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="56117-118">Table-Valued Parameters &#40;OLE DB&#41;</span></span>](../../native-client-ole-db-table-valued-parameters/table-valued-parameters-ole-db.md)  
  
-   [<span data-ttu-id="56117-119">Date and Time Improvements &#40;OLE DB&#41; (Verbesserungen bei Datum und Uhrzeit &#40;OLE DB&#41;)</span><span class="sxs-lookup"><span data-stu-id="56117-119">Date and Time Improvements &#40;OLE DB&#41;</span></span>](../../native-client-ole-db-date-time/date-and-time-improvements-ole-db.md)  
  
-   [<span data-ttu-id="56117-120">Große benutzerdefinierte CLR-Typen &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="56117-120">Large CLR User-Defined Types &#40;OLE DB&#41;</span></span>](large-clr-user-defined-types-ole-db.md)  
  
-   [<span data-ttu-id="56117-121">FILESTREAM-Unterstützung &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="56117-121">FILESTREAM Support &#40;OLE DB&#41;</span></span>](filestream-support-ole-db.md)  
  
-   [<span data-ttu-id="56117-122">Transaktionen</span><span class="sxs-lookup"><span data-stu-id="56117-122">Transactions</span></span>](../../native-client-ole-db-transactions/transactions.md)  
  
-   [<span data-ttu-id="56117-123">Fehler</span><span class="sxs-lookup"><span data-stu-id="56117-123">Errors</span></span>](../../native-client-ole-db-errors/errors.md)  
  
-   [<span data-ttu-id="56117-124">Dienstprinzipalnamen (SPN) in Clientverbindungen (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="56117-124">Service Principal Names &#40;SPNs&#41; in Client Connections &#40;OLE DB&#41;</span></span>](service-principal-names-spns-in-client-connections-ole-db.md)  
  
-   [<span data-ttu-id="56117-125">Unterstützung für Sparsespalten &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="56117-125">Sparse Columns Support &#40;OLE DB&#41;</span></span>](sparse-columns-support-ole-db.md)  
  
-   [<span data-ttu-id="56117-126">SQL Server Native Client &#40;OLE DB&#41; Referenz</span><span class="sxs-lookup"><span data-stu-id="56117-126">SQL Server Native Client &#40;OLE DB&#41; Reference</span></span>](../../native-client-ole-db-interfaces/sql-server-native-client-ole-db-interfaces.md)  
  
-   [<span data-ttu-id="56117-127">Vorgehensweisen für OLE DB</span><span class="sxs-lookup"><span data-stu-id="56117-127">OLE DB How-to Topics</span></span>](../../native-client-ole-db-how-to/ole-db-how-to-topics.md)  
  
## <a name="see-also"></a><span data-ttu-id="56117-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="56117-128">See Also</span></span>  
 [<span data-ttu-id="56117-129">Programmierung für SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="56117-129">SQL Server Native Client Programming</span></span>](../sql-server-native-client-programming.md)  
  
  
