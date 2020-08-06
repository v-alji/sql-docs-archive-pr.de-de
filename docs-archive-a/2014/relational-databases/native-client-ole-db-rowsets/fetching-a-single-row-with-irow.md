---
title: Abrufen einer einzelnen Zeile mit IRow | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- fetching rows
- IRow interface
- single row fetching [SQL Server Native Client]
- OLE DB rowsets, fetching
- rowsets [OLE DB], fetching
- SQL Server Native Client OLE DB provider, fetching
ms.assetid: 07c803ca-299a-42c5-ba02-360b9631d15f
author: rothja
ms.author: jroth
ms.openlocfilehash: b5573fe1fef39f29329e373323f5f8aaf15f2c58
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620829"
---
# <a name="fetching-a-single-row-with-irow"></a><span data-ttu-id="68c7c-102">Abrufen einer einzelnen Zeile mit IRow</span><span class="sxs-lookup"><span data-stu-id="68c7c-102">Fetching a Single Row with IRow</span></span>
  <span data-ttu-id="68c7c-103">Die Implementierung der **IRow** -Schnittstelle im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter wird vereinfacht, um die Leistung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="68c7c-103">The **IRow** interface implementation in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider is simplified to increase performance.</span></span> <span data-ttu-id="68c7c-104">**IRow** lässt den direkten Zugriff auf Spalten eines einzelnen Zeilenobjekts zu.</span><span class="sxs-lookup"><span data-stu-id="68c7c-104">**IRow** allows direct access to columns of a single row object.</span></span> <span data-ttu-id="68c7c-105">Wenn Sie vorab wissen, dass das Ergebnis einer Befehlsausführung genau eine Zeile erzeugt, dann lassen sich mit **IRow** die Spalten dieser Zeile abrufen.</span><span class="sxs-lookup"><span data-stu-id="68c7c-105">If you know beforehand that the result of a command execution will produce exactly one row, **IRow** will retrieve the columns of that row.</span></span> <span data-ttu-id="68c7c-106">Wenn das Resultset mehrere Zeilen umfasst, macht **IRow** nur die erste Zeile verfügbar.</span><span class="sxs-lookup"><span data-stu-id="68c7c-106">If the result set includes multiple rows, **IRow** will expose only the first row.</span></span>  
  
 <span data-ttu-id="68c7c-107">Die **IRow**-Implementierung lässt keine Navigation in der Zeile zu.</span><span class="sxs-lookup"><span data-stu-id="68c7c-107">The **IRow** implementation does not allow any navigation of the row.</span></span> <span data-ttu-id="68c7c-108">Mit folgender Ausnahme wird auf jede Spalte der Zeile nur ein einziges Mal zugegriffen: Einmal kann zur Ermittlung der Spaltenbreite auf eine Spalte zugegriffen werden, und dann kann nochmals zum Abruf der Daten auf die Spalte zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="68c7c-108">Each column in the row is accessed only one time with one exception: A column can be accessed one time to find the column size and again to fetch the data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="68c7c-109">**IRow::Open** unterstützt nur das Öffnen von Objekten des Typs DBGUID_STREAM und DBGUID_NULL.</span><span class="sxs-lookup"><span data-stu-id="68c7c-109">**IRow::Open** supports only DBGUID_STREAM and DBGUID_NULL type of objects to be opened.</span></span>  
  
 <span data-ttu-id="68c7c-110">IID_IRow muss übergeben werden, um ein Zeilenobjekt mithilfe der **ICommand::Execute**-Methode zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="68c7c-110">To obtain a row object using **ICommand::Execute** method, IID_IRow must be passed.</span></span> <span data-ttu-id="68c7c-111">Die **IMultipleResults**-Schnittstelle muss zur Behandlung mehrerer Resultsets verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="68c7c-111">The **IMultipleResults** interface must be used to handle multiple result sets.</span></span> <span data-ttu-id="68c7c-112">**IMultipleResults** unterstützt **IRow** und **IRowset**.</span><span class="sxs-lookup"><span data-stu-id="68c7c-112">**IMultipleResults** supports **IRow** and **IRowset**.</span></span> <span data-ttu-id="68c7c-113">**IRowset** wird für Massenvorgänge verwendet.</span><span class="sxs-lookup"><span data-stu-id="68c7c-113">**IRowset** is used for bulk operations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="68c7c-114">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="68c7c-114">In This Section</span></span>  
  
-   [<span data-ttu-id="68c7c-115">Verwenden von IRow::GetColumns</span><span class="sxs-lookup"><span data-stu-id="68c7c-115">Using IRow::GetColumns</span></span>](using-irow-getcolumns.md)  
  
-   [<span data-ttu-id="68c7c-116">Abrufen von BLOB-Daten mit IRow</span><span class="sxs-lookup"><span data-stu-id="68c7c-116">Fetching BLOB Data Using IRow</span></span>](../../database-engine/dev-guide/fetching-blob-data-using-irow.md)  
  
## <a name="see-also"></a><span data-ttu-id="68c7c-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="68c7c-117">See Also</span></span>  
 [<span data-ttu-id="68c7c-118">Rowsets</span><span class="sxs-lookup"><span data-stu-id="68c7c-118">Rowsets</span></span>](rowsets.md)  
  
  
