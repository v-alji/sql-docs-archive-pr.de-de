---
title: Verarbeiten von Ergebnissen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, results processing
- OLE DB, processing results
- rowsets [SQL Server], results processing
- results [SQL Server Native Client]
ms.assetid: 20887ac4-f649-4e7f-92e6-f929e2e70952
author: rothja
ms.author: jroth
ms.openlocfilehash: b9e5bf00b4d2e554536c9f2ba1a328390b93a8a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620830"
---
# <a name="processing-results"></a><span data-ttu-id="61183-102">Ergebnisverarbeitung</span><span class="sxs-lookup"><span data-stu-id="61183-102">Processing Results</span></span>
  <span data-ttu-id="61183-103">Wenn ein Rowsetobjekt durch die Ausführung eines Befehls oder vom Anbieter direkt erzeugt wird, muss der Consumer die Daten im Rowset abrufen und darauf zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="61183-103">If a rowset object is produced by either the execution of a command or the generation of a rowset object directly from the provider, the consumer needs to retrieve and access data in the rowset.</span></span>  
  
 <span data-ttu-id="61183-104">Rowsets sind die zentralen Objekte, die es dem OLE DB-Anbieter von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ermöglichen, Daten in tabellarischer Form verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="61183-104">Rowsets are the central objects that enable the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider to expose data in tabular form.</span></span> <span data-ttu-id="61183-105">Grundsätzlich ist ein Rowset ein Satz von Zeilen, in dem jede Zeile Spaltendaten aufweist.</span><span class="sxs-lookup"><span data-stu-id="61183-105">Conceptually, a rowset is a set of rows in which each row has column data.</span></span> <span data-ttu-id="61183-106">Ein Rowsetobjekt macht Schnittstellen verfügbar, z.B. **IRowset** (enthält Methoden zum sequenziellen Abrufen von Zeilen aus dem Rowset), **IAccessor** (lässt die Definition einer Gruppe von Spaltenbindungen zu, die beschreibt, wie die Tabellendaten an die Programmvariablen des Consumers gebunden werden sollen), **IColumnsInfo** (stellt Information zu den Spalten im Rowset bereit) und **IRowsetInfo** (stellt Information zum Rowset bereit).</span><span class="sxs-lookup"><span data-stu-id="61183-106">A rowset object exposes interfaces such as **IRowset** (contains methods for fetching rows from the rowset sequentially), **IAccessor** (permits the definition of a group of column bindings describing the way tabular data is bound to consumer program variables), **IColumnsInfo** (provides information about columns in the rowset), and **IRowsetInfo** (provides information about rowset).</span></span>  
  
 <span data-ttu-id="61183-107">Ein Consumer kann die **IRowset::GetData**-Methode aufrufen, um eine Datenzeile aus dem Rowset abzurufen und in einen Puffer einzufügen.</span><span class="sxs-lookup"><span data-stu-id="61183-107">A consumer can call the **IRowset::GetData** method to retrieve a row of data from the rowset into a buffer.</span></span> <span data-ttu-id="61183-108">Bevor **GetData** aufgerufen wird, beschreibt der Consumer den Puffer mit mehreren DBBINDING-Strukturen.</span><span class="sxs-lookup"><span data-stu-id="61183-108">Before **GetData** is called, the consumer describes the buffer using a set of DBBINDING structures.</span></span> <span data-ttu-id="61183-109">Jede Bindung beschreibt, wie eine Spalte des Rowsets in einem Puffer des Consumer gespeichert werden soll, und enthält folgende Angaben:</span><span class="sxs-lookup"><span data-stu-id="61183-109">Each binding describes how a column in a rowset is stored in a consumer buffer and contains the following:</span></span>  
  
-   <span data-ttu-id="61183-110">Ordnungszahl der Spalte (oder des Parameters), auf den sich die Bindung bezieht</span><span class="sxs-lookup"><span data-stu-id="61183-110">Ordinal of the column (or parameter) to which the binding applies.</span></span>  
  
-   <span data-ttu-id="61183-111">Informationen darüber, was gebunden wird (z. B. Datenwert, Länge der Daten und Bindungsstatus)</span><span class="sxs-lookup"><span data-stu-id="61183-111">Information about what is bound (for example, data value, length of the data, and its binding status).</span></span>  
  
-   <span data-ttu-id="61183-112">Informationen zur Größe des Offsets im Puffer zu jedem dieser Teile</span><span class="sxs-lookup"><span data-stu-id="61183-112">Information about what is offset in the buffer to each of these parts.</span></span>  
  
-   <span data-ttu-id="61183-113">Länge und den Typ der Datenwerte, die im Puffer des Consumers vorhanden sind</span><span class="sxs-lookup"><span data-stu-id="61183-113">Length and type of the data values as they exist in the consumer buffer.</span></span>  
  
 <span data-ttu-id="61183-114">Beim Abruf der Daten bestimmt der Anbieter anhand der Informationen in jeder Bindung, wo und wie die Daten aus dem Puffer des Consumers abzurufen sind.</span><span class="sxs-lookup"><span data-stu-id="61183-114">When getting the data, the provider uses information in each binding to determine where and how to retrieve data from the consumer buffer.</span></span> <span data-ttu-id="61183-115">Beim Einfügen der Daten in den Puffer des Consumers bestimmt der Anbieter anhand der Informationen in jeder Bindung, wo und wie die Daten in diesen Puffer einzufügen sind.</span><span class="sxs-lookup"><span data-stu-id="61183-115">When setting data in the consumer buffer, the provider uses information in each binding to determine where and how to return data in the consumer's buffer.</span></span>  
  
 <span data-ttu-id="61183-116">Nachdem die DBBINDING-Strukturen angegeben wurden, wird ein Accessor (**IAccessor::CreateAccessor**) erstellt.</span><span class="sxs-lookup"><span data-stu-id="61183-116">After the DBBINDING structures are specified, an accessor is created (**IAccessor::CreateAccessor**).</span></span> <span data-ttu-id="61183-117">Ein Accessor ist eine Sammlung von Bindungen. Er dient zum Abrufen oder Einfügen von Daten in den Puffer des Consumers.</span><span class="sxs-lookup"><span data-stu-id="61183-117">An accessor is a collection of bindings and is used to get or set the data in the consumer buffer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61183-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="61183-118">See Also</span></span>  
 <span data-ttu-id="61183-119">[Erstellen einer SQL Server Native Client OLE DB-Anbieter Anwendung](creating-a-sql-server-native-client-ole-db-provider-application.md) </span><span class="sxs-lookup"><span data-stu-id="61183-119">[Creating a SQL Server Native Client OLE DB Provider Application](creating-a-sql-server-native-client-ole-db-provider-application.md) </span></span>  
 [<span data-ttu-id="61183-120">Vorgehensweisen für OLE DB</span><span class="sxs-lookup"><span data-stu-id="61183-120">OLE DB How-to Topics</span></span>](../native-client-ole-db-how-to/ole-db-how-to-topics.md)  
  
  
