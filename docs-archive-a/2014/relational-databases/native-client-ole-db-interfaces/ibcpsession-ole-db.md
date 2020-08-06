---
title: IBCPSession (OLE DB) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- IBCPSession interface
ms.assetid: 00d0311f-8b71-4ad6-824d-0e89119347a3
author: rothja
ms.author: jroth
ms.openlocfilehash: 0d32da9c06a200d5924dbae18d6b7513f46c88ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723769"
---
# <a name="ibcpsession-ole-db"></a><span data-ttu-id="cb166-102">IBCPSession (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="cb166-102">IBCPSession (OLE DB)</span></span>
  <span data-ttu-id="cb166-103">Die **IBCPSession**-Schnittstelle unterstützt dateibasierte Massenkopiervorgänge für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cb166-103">The **IBCPSession** interface exposes support for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] file-based bulk copy operations.</span></span> <span data-ttu-id="cb166-104">Die **IBCPSession** Schnittstelle wird im OLE DB-Anbieter von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client auf derselben Ebene wie Session-Objekte verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="cb166-104">The **IBCPSession** interface is exposed in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider under the same level as Sessions.</span></span> <span data-ttu-id="cb166-105">Im OLE DB-Anbieter von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client sind Datenquellenobjekte Factorys für Session-Objekte, und Massenkopiervorgänge werden in der Verbindungseigenschaft SSPROP_ENABLEBULKCOPY angegeben.</span><span class="sxs-lookup"><span data-stu-id="cb166-105">In the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider, data source objects are factories for Session objects, and bulk copy operations are specified in the connection property SSPROP_ENABLEBULKCOPY.</span></span> <span data-ttu-id="cb166-106">Außerdem sollte die SSPROP_ENABLEFASTLOAD-Eigenschaft auf true festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="cb166-106">In addition, the SSPROP_ENABLEFASTLOAD property should be set to true.</span></span>  
  
 <span data-ttu-id="cb166-107">Ein Aufruf der **IDBCreateSession::CreateSession** -Methode führt dann zur Erstellung eines **BulkCopySession** -Objekts.</span><span class="sxs-lookup"><span data-stu-id="cb166-107">Calling the **IDBCreateSession::CreateSession** method will then result in the creation of a **BulkCopySession** object.</span></span> <span data-ttu-id="cb166-108">Alle durch das **IBCPSession** -Objekt verfügbar gemachten dateibasierten Massenkopiermethoden sind mit einer ganz ähnlichen Syntax über die **IBCPSession** -Schnittstelle dieses **IBCPSession** -Objekts aufrufbar.</span><span class="sxs-lookup"><span data-stu-id="cb166-108">All the file-based bulk copy methods exposed through the **IBCPSession** object are then callable with nearly similar signatures on this **IBCPSession** object's **IBCPSession** interface.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cb166-109">Der OLE DB-Anbieter von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client unterstützt speicherbasierte Massenkopiervorgänge durch die [IRowsetFastLoad](irowsetfastload-ole-db.md) -Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="cb166-109">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports memory-based bulk copy operations through the [IRowsetFastLoad](irowsetfastload-ole-db.md) interface.</span></span>  
  
 <span data-ttu-id="cb166-110">Weitere Informationen zur Verwendung des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-OLE DB Anbieters für Massen Kopiervorgänge finden Sie unter [Durchführen von Massen Kopier Vorgängen](../native-client/features/performing-bulk-copy-operations.md).</span><span class="sxs-lookup"><span data-stu-id="cb166-110">For more information about using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider for bulk copy operations, see [Performing Bulk Copy Operations](../native-client/features/performing-bulk-copy-operations.md).</span></span>  
  
 <span data-ttu-id="cb166-111">Ein Beispiel für die Verwendung der **IBCPSession**-Schnittstelle finden Sie unter [IBCPSession::BCPDone &#40;OLE DB&#41;](ibcpsession-bcpdone-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="cb166-111">For a sample showing how to use the **IBCPSession** interface, see [IBCPSession::BCPDone &#40;OLE DB&#41;](ibcpsession-bcpdone-ole-db.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cb166-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="cb166-112">In This Section</span></span>  
  
|<span data-ttu-id="cb166-113">Methode</span><span class="sxs-lookup"><span data-stu-id="cb166-113">Method</span></span>|<span data-ttu-id="cb166-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cb166-114">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cb166-115">IBCPSession::BCPColFmt &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="cb166-115">IBCPSession::BCPColFmt &#40;OLE DB&#41;</span></span>](ibcpsession-bcpcolfmt-ole-db.md)|<span data-ttu-id="cb166-116">Erstellt eine Bindung zwischen Programmvariablen und [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Spalten.</span><span class="sxs-lookup"><span data-stu-id="cb166-116">Creates a binding between program variables and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] columns.</span></span>|  
|[<span data-ttu-id="cb166-117">IBCPSession::BCPColumns &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="cb166-117">IBCPSession::BCPColumns &#40;OLE DB&#41;</span></span>](ibcpsession-bcpcolumns-ole-db.md)|<span data-ttu-id="cb166-118">Legt die Anzahl von Feldern fest, die an die Spalten einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Tabelle gebunden werden sollen.</span><span class="sxs-lookup"><span data-stu-id="cb166-118">Sets the number of fields that are to be bound to the columns in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>|  
|[<span data-ttu-id="cb166-119">IBCPSession::BCPControl &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="cb166-119">IBCPSession::BCPControl &#40;OLE DB&#41;</span></span>](ibcpsession-bcpcontrol-ole-db.md)|<span data-ttu-id="cb166-120">Legt die Optionen für einen Massenkopiervorgang fest.</span><span class="sxs-lookup"><span data-stu-id="cb166-120">Sets the options for a bulk copy operation.</span></span>|  
|[<span data-ttu-id="cb166-121">IBCPSession::BCPDone &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="cb166-121">IBCPSession::BCPDone &#40;OLE DB&#41;</span></span>](ibcpsession-bcpdone-ole-db.md)|<span data-ttu-id="cb166-122">Führt einen Commit für die übrigen Zeilen aus, die an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]gesendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="cb166-122">Commits the remaining rows to be sent to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="cb166-123">IBCPSession::BCPExec &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="cb166-123">IBCPSession::BCPExec &#40;OLE DB&#41;</span></span>](ibcpsession-bcpexec-ole-db.md)|<span data-ttu-id="cb166-124">Führt den Massenkopiervorgang aus.</span><span class="sxs-lookup"><span data-stu-id="cb166-124">Performs the bulk copy operation.</span></span>|  
|[<span data-ttu-id="cb166-125">IBCPSession::BCPInit &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="cb166-125">IBCPSession::BCPInit &#40;OLE DB&#41;</span></span>](ibcpsession-bcpinit-ole-db.md)|<span data-ttu-id="cb166-126">Initialisiert die Massenkopierstruktur, führt einige Fehlerprüfungen durch, überprüft die korrekte Angabe der Daten- und Formatdateinamen und öffnet dann diese Dateien.</span><span class="sxs-lookup"><span data-stu-id="cb166-126">Initializes the bulk copy structure, performs some error checking, verifies that the data and format file names are correct, and then opens them.</span></span>|  
|[<span data-ttu-id="cb166-127">IBCPSession::BCPReadFmt &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="cb166-127">IBCPSession::BCPReadFmt &#40;OLE DB&#41;</span></span>](ibcpsession-bcpreadfmt-ole-db.md)|<span data-ttu-id="cb166-128">Liest für jede Spalte Formatinformationen aus der Formatdatei.</span><span class="sxs-lookup"><span data-stu-id="cb166-128">Reads format information for each column from the format file.</span></span>|  
|[<span data-ttu-id="cb166-129">IBCPSession::BCPWriteFmt &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="cb166-129">IBCPSession::BCPWriteFmt &#40;OLE DB&#41;</span></span>](ibcpsession-bcpwritefmt-ole-db.md)|<span data-ttu-id="cb166-130">Schreibt für jede Spalte Formatinformationen in die Formatdatei.</span><span class="sxs-lookup"><span data-stu-id="cb166-130">Writes format information for each column to the format file.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cb166-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cb166-131">See Also</span></span>  
 [<span data-ttu-id="cb166-132">Schnittstellen &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="cb166-132">Interfaces &#40;OLE DB&#41;</span></span>](../../database-engine/dev-guide/interfaces-ole-db.md)  
  
  
