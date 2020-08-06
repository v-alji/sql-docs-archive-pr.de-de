---
title: IRowsetFastLoad::Commit (OLE DB) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- IRowsetFastLoad::Commit (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- Commit method
ms.assetid: 19de9128-b91a-4626-847f-af721edaa24e
author: rothja
ms.author: jroth
ms.openlocfilehash: cfdf355919f65fd2cedacd09249e2aae59321390
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621487"
---
# <a name="irowsetfastloadcommit-ole-db"></a><span data-ttu-id="0390c-102">IRowsetFastLoad::Commit (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="0390c-102">IRowsetFastLoad::Commit (OLE DB)</span></span>
  <span data-ttu-id="0390c-103">Markiert das Ende eines Batches eingefügter Zeilen und schreibt die Zeilen in die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="0390c-103">Marks the end of a batch of inserted rows and writes the rows to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="0390c-104">Beispiele finden Sie unter [Massenkopieren von Daten mithilfe von IRowsetFastLoad &#40;OLE DB&#41;](irowsetfastload-ole-db.md) und [Senden von BLOB-Daten an SQL SERVER mit IROWSETFASTLOAD und ISEQUENTIALSTREAM &#40;OLE DB&#41;](../native-client-ole-db-how-to/send-blob-data-to-sql-server-using-irowsetfastload-and-isequentialstream-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="0390c-104">For samples, see [Bulk Copy Data Using IRowsetFastLoad &#40;OLE DB&#41;](irowsetfastload-ole-db.md) and [Send BLOB Data to SQL SERVER Using IROWSETFASTLOAD and ISEQUENTIALSTREAM &#40;OLE DB&#41;](../native-client-ole-db-how-to/send-blob-data-to-sql-server-using-irowsetfastload-and-isequentialstream-ole-db.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0390c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="0390c-105">Syntax</span></span>  
  
```  
  
HRESULT Commit(  
BOOL   
fDone  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="0390c-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="0390c-106">Arguments</span></span>  
 <span data-ttu-id="0390c-107">*fDone*[in]</span><span class="sxs-lookup"><span data-stu-id="0390c-107">*fDone*[in]</span></span>  
 <span data-ttu-id="0390c-108">Wenn FALSE angegeben wird, behält das Rowset seine Gültigkeit und kann vom Consumer zum Einfügen zusätzlicher Zeilen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0390c-108">If FALSE, the rowset maintains validity and can be used by the consumer for additional row insertion.</span></span> <span data-ttu-id="0390c-109">Wird TRUE angegeben, dann verliert das Rowset seine Gültigkeit, und der Consumer kann keine weiteren Einfügungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="0390c-109">If TRUE, the rowset loses validity and no further insertion can be done by the consumer.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="0390c-110">Rückgabecodewerte</span><span class="sxs-lookup"><span data-stu-id="0390c-110">Return Code Values</span></span>  
 <span data-ttu-id="0390c-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="0390c-111">S_OK</span></span>  
 <span data-ttu-id="0390c-112">Die Methode wurde erfolgreich ausgeführt, und alle eingefügten Daten wurden in die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Tabelle geschrieben.</span><span class="sxs-lookup"><span data-stu-id="0390c-112">The method succeeded and all inserted data has been written to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="0390c-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0390c-113">E_FAIL</span></span>  
 <span data-ttu-id="0390c-114">Es ist ein anbieterspezifischer Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0390c-114">A provider-specific error occurred.</span></span> <span data-ttu-id="0390c-115">Rufen Sie Fehlerinformationen für den betreffenden Fehlertext vom Anbieter ab.</span><span class="sxs-lookup"><span data-stu-id="0390c-115">Retrieve error information for the specific error text from the provider.</span></span>  
  
 <span data-ttu-id="0390c-116">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="0390c-116">E_UNEXPECTED</span></span>  
 <span data-ttu-id="0390c-117">Die Methode wurde für ein Rowset für das Massenkopieren aufgerufen, das zuvor von der **IRowsetFastLoad::Commit**-Methode für ungültig erklärt wurde.</span><span class="sxs-lookup"><span data-stu-id="0390c-117">The method was called on a bulk copy rowset previously invalidated by the **IRowsetFastLoad::Commit** method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0390c-118">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="0390c-118">Remarks</span></span>  
 <span data-ttu-id="0390c-119">Ein Rowset [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] für das Massen Kopieren eines Native Client OLE DB-Anbieters verhält sich als Rowset mit verzögertem Aktualisierungs Modus.</span><span class="sxs-lookup"><span data-stu-id="0390c-119">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider bulk copy rowset behaves as a delayed-update mode rowset.</span></span> <span data-ttu-id="0390c-120">Wenn der Benutzer Zeilendaten über das Rowset einfügt, dann werden die eingefügten Zeilen so behandelt wie ausstehende Einfügungen in einem Rowset, das **IRowsetUpdate** unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0390c-120">As the user inserts row data through the rowset, inserted rows are treated in the same fashion as pending inserts on a rowset supporting **IRowsetUpdate**.</span></span>  
  
 <span data-ttu-id="0390c-121">Der Consumer muss die **Commit**-Methode für das Rowset für das Massenkopieren ebenso aufrufen, um die eingefügten Zeilen in die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Tabelle zu schreiben, wie mithilfe der **IRowsetUpdate::Update-Methode** ausstehende Zeilen an eine Instanz von SQL Server gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="0390c-121">The consumer must call the **Commit** method on the bulk copy rowset to write inserted rows to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table in the same way as the **IRowsetUpdate::Update** method is used to submit pending rows to an instance of SQL Server.</span></span>  
  
 <span data-ttu-id="0390c-122">Wenn der Consumer seinen Verweis auf das Rowset für das Massenkopieren freigibt, ohne die **Commit**-Methode aufzurufen, gehen alle Zeilen verloren, die vorher nicht in die Tabelle geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="0390c-122">If the consumer releases its reference on the bulk copy rowset without calling the **Commit** method, all inserted rows not previously written are lost.</span></span>  
  
 <span data-ttu-id="0390c-123">Der Consumer kann die eingefügten Zeilen als Batch definieren, indem er die **Commit**-Methode aufruft und das *fDone*-Argument auf FALSE festlegt.</span><span class="sxs-lookup"><span data-stu-id="0390c-123">The consumer can batch inserted rows by calling the **Commit** method with the *fDone* argument set to FALSE.</span></span> <span data-ttu-id="0390c-124">Wenn *fDone* auf TRUE festgelegt wird, wird das Rowset ungültig.</span><span class="sxs-lookup"><span data-stu-id="0390c-124">When *fDone*is set to TRUE, the rowset becomes invalid.</span></span> <span data-ttu-id="0390c-125">Ein ungültiges Rowset für das Massenkopieren unterstützt nur die **ISupportErrorInfo**-Schnittstelle und die **IRowsetFastLoad::Release**-Methode.</span><span class="sxs-lookup"><span data-stu-id="0390c-125">An invalid bulk copy rowset supports only the **ISupportErrorInfo** interface and **IRowsetFastLoad::Release** method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0390c-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0390c-126">See Also</span></span>  
 [<span data-ttu-id="0390c-127">IRowsetFastLoad &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="0390c-127">IRowsetFastLoad &#40;OLE DB&#41;</span></span>](irowsetfastload-ole-db.md)  
  
  
