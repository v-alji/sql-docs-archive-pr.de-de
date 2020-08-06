---
title: IRowsetFastLoad (OLE DB) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- IRowsetFastLoad interface
ms.assetid: d19a7097-48d9-409a-aff9-277891b7aca7
author: rothja
ms.author: jroth
ms.openlocfilehash: 7ecf72f0015d9ed197b3b7a33d4f9bb3246134b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621482"
---
# <a name="irowsetfastload-ole-db"></a><span data-ttu-id="8201f-102">IRowsetFastLoad (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="8201f-102">IRowsetFastLoad (OLE DB)</span></span>
  <span data-ttu-id="8201f-103">Die- `IRowsetFastLoad` Schnittstelle unterstützt [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] speicherbasierte Massen Kopiervorgänge.</span><span class="sxs-lookup"><span data-stu-id="8201f-103">The `IRowsetFastLoad` interface exposes support for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory-based bulk-copy operations.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="8201f-104">Native Client OLE DB-Anbieter Consumer verwenden die-Schnittstelle, um schnell Daten zu einer vorhandenen Tabelle hinzuzufügen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8201f-104">Native Client OLE DB provider consumers use the interface to rapidly add data to an existing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="8201f-105">Wenn Sie SSPROP_ENABLEFASTLOAD für eine Sitzung auf VARIANT_TRUE festlegen, können Sie keine Daten aus Rowsets lesen, die danach von dieser Sitzung zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8201f-105">If you set SSPROP_ENABLEFASTLOAD to VARIANT_TRUE for a session, you cannot read data from rowsets subsequently returned from that session.</span></span> <span data-ttu-id="8201f-106">Wenn SSPROP_ENABLEFASTLOAD auf VARIANT_TRUE festgelegt wird, sind alle Rowsets, die in dieser Sitzung erstellt werden, vom Typ „IRowsetFastLoad“.</span><span class="sxs-lookup"><span data-stu-id="8201f-106">When SSPROP_ENABLEFASTLOAD is set to VARIANT_TRUE, all rowsets created on the session will be of type IRowsetFastLoad.</span></span> <span data-ttu-id="8201f-107">IRowsetFastLoad-Rowsets unterstützen die Funktionalität zum Abrufen von Rowsets nicht. Daher können aus diesen Rowsets keine Daten gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="8201f-107">IRowsetFastLoad rowsets do not support rowset fetch functionality; therefore, data from these rowsets cannot be read.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8201f-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="8201f-108">In This Section</span></span>  
  
|<span data-ttu-id="8201f-109">Methode</span><span class="sxs-lookup"><span data-stu-id="8201f-109">Method</span></span>|<span data-ttu-id="8201f-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8201f-110">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8201f-111">IRowsetFastLoad::Commit &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="8201f-111">IRowsetFastLoad::Commit &#40;OLE DB&#41;</span></span>](irowsetfastload-commit-ole-db.md)|<span data-ttu-id="8201f-112">Markiert das Ende eines Batches eingefügter Zeilen und schreibt die Zeilen in die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="8201f-112">Marks the end of a batch of inserted rows and writes the rows to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>|  
|[<span data-ttu-id="8201f-113">IRowsetFastLoad::InsertRow &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="8201f-113">IRowsetFastLoad::InsertRow &#40;OLE DB&#41;</span></span>](irowsetfastload-insertrow-ole-db.md)|<span data-ttu-id="8201f-114">Fügt dem Rowset für das Massenkopieren eine Zeile hinzu.</span><span class="sxs-lookup"><span data-stu-id="8201f-114">Adds a row to the bulk copy rowset.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8201f-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8201f-115">See Also</span></span>  
 <span data-ttu-id="8201f-116">[Schnittstellen &#40;OLE DB&#41;](../../database-engine/dev-guide/interfaces-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="8201f-116">[Interfaces &#40;OLE DB&#41;](../../database-engine/dev-guide/interfaces-ole-db.md) </span></span>  
 <span data-ttu-id="8201f-117">[Massen Daten kopieren mithilfe der IRowsetFastLoad-&#40;OLE DB&#41;](../native-client-ole-db-how-to/bulk-copy-data-using-irowsetfastload-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="8201f-117">[Bulk Copy Data Using IRowsetFastLoad &#40;OLE DB&#41;](../native-client-ole-db-how-to/bulk-copy-data-using-irowsetfastload-ole-db.md) </span></span>  
 [<span data-ttu-id="8201f-118">Senden von BLOB-Daten an SQL SERVER mit IROWSETFASTLOAD und ISEQUENTIALSTREAM &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="8201f-118">Send BLOB Data to SQL SERVER Using IROWSETFASTLOAD and ISEQUENTIALSTREAM &#40;OLE DB&#41;</span></span>](../native-client-ole-db-how-to/send-blob-data-to-sql-server-using-irowsetfastload-and-isequentialstream-ole-db.md)  
  
  
