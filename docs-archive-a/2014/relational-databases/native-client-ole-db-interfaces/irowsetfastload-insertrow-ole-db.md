---
title: IRowsetFastLoad::InsertRow (OLE DB) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- IRowsetFastLoad::InsertRow (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- InsertRow method
ms.assetid: 594d3461-34d2-41e7-8ad4-bd2753601ab6
author: rothja
ms.author: jroth
ms.openlocfilehash: 4e9ea952f27574270ee333919f778814ff3de462
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621483"
---
# <a name="irowsetfastloadinsertrow-ole-db"></a><span data-ttu-id="9811a-102">IRowsetFastLoad::InsertRow (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="9811a-102">IRowsetFastLoad::InsertRow (OLE DB)</span></span>
  <span data-ttu-id="9811a-103">Fügt dem Rowset für das Massenkopieren eine Zeile hinzu.</span><span class="sxs-lookup"><span data-stu-id="9811a-103">Adds a row to the bulk copy rowset.</span></span> <span data-ttu-id="9811a-104">Beispiele finden Sie unter [Massenkopieren von Daten mithilfe von IRowsetFastLoad &#40;OLE DB&#41;](../native-client-ole-db-how-to/bulk-copy-data-using-irowsetfastload-ole-db.md) und [Senden von BLOB-Daten an SQL SERVER mit IROWSETFASTLOAD und ISEQUENTIALSTREAM &#40;OLE DB&#41;](../native-client-ole-db-how-to/send-blob-data-to-sql-server-using-irowsetfastload-and-isequentialstream-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="9811a-104">For samples, see [Bulk Copy Data Using IRowsetFastLoad &#40;OLE DB&#41;](../native-client-ole-db-how-to/bulk-copy-data-using-irowsetfastload-ole-db.md) and [Send BLOB Data to SQL SERVER Using IROWSETFASTLOAD and ISEQUENTIALSTREAM &#40;OLE DB&#41;](../native-client-ole-db-how-to/send-blob-data-to-sql-server-using-irowsetfastload-and-isequentialstream-ole-db.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9811a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9811a-105">Syntax</span></span>  
  
```  
  
HRESULT InsertRow(  
HACCESSOR  
hAccessor  
,  
void*  
pData  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="9811a-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="9811a-106">Arguments</span></span>  
 <span data-ttu-id="9811a-107">*hAccessor*[in]</span><span class="sxs-lookup"><span data-stu-id="9811a-107">*hAccessor*[in]</span></span>  
 <span data-ttu-id="9811a-108">Das Handle des Accessors, der die Zeilendaten für das Massenkopieren definiert.</span><span class="sxs-lookup"><span data-stu-id="9811a-108">The handle of the accessor defining the row data for bulk copy.</span></span> <span data-ttu-id="9811a-109">Der Accessor, auf den verwiesen wird, ist ein Zeilenaccessor, der den consumer-eigenen Speicher bindet, in dem sich die Datenwerte befinden.</span><span class="sxs-lookup"><span data-stu-id="9811a-109">The accessor referenced is a row accessor, binding consumer-owned memory containing data values.</span></span>  
  
 <span data-ttu-id="9811a-110">*pData*[in]</span><span class="sxs-lookup"><span data-stu-id="9811a-110">*pData*[in]</span></span>  
 <span data-ttu-id="9811a-111">Ein Zeiger zum consumer-eigenen Speicher, in dem sich die Datenwerte befinden.</span><span class="sxs-lookup"><span data-stu-id="9811a-111">A pointer to the consumer-owned memory containing data values.</span></span> <span data-ttu-id="9811a-112">Weitere Informationen finden Sie unter [DBBINDING-Strukturen](https://go.microsoft.com/fwlink/?LinkId=65955).</span><span class="sxs-lookup"><span data-stu-id="9811a-112">For more information, see [DBBINDING Structures](https://go.microsoft.com/fwlink/?LinkId=65955).</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="9811a-113">Rückgabecodewerte</span><span class="sxs-lookup"><span data-stu-id="9811a-113">Return Code Values</span></span>  
 <span data-ttu-id="9811a-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="9811a-114">S_OK</span></span>  
 <span data-ttu-id="9811a-115">Die Methode wurde erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9811a-115">The method succeeded.</span></span> <span data-ttu-id="9811a-116">Alle gebundenen Statuswerte für alle Spalten weisen den Wert DBSTATUS_S_OK oder DBSTATUS_S_NULL auf.</span><span class="sxs-lookup"><span data-stu-id="9811a-116">Any bound status values for all columns have value DBSTATUS_S_OK or DBSTATUS_S_NULL.</span></span>  
  
 <span data-ttu-id="9811a-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9811a-117">E_FAIL</span></span>  
 <span data-ttu-id="9811a-118">Es ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="9811a-118">An error occurred.</span></span> <span data-ttu-id="9811a-119">Fehlerinformationen sind über die Fehlerschnittstellen des Rowsets verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9811a-119">Error information is available from the rowset's error interfaces.</span></span>  
  
 <span data-ttu-id="9811a-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="9811a-120">E_INVALIDARG</span></span>  
 <span data-ttu-id="9811a-121">Das *pData* -Argument wurde auf einen NULL-Zeiger festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9811a-121">The *pData* argument was set to a NULL pointer.</span></span>  
  
 <span data-ttu-id="9811a-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="9811a-122">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="9811a-123">SQLNCLI11 konnte keinen ausreichenden Arbeitsspeicher zum Ausführen der Anforderung zuordnen.</span><span class="sxs-lookup"><span data-stu-id="9811a-123">SQLNCLI11 was unable to allocate sufficient memory to complete the request.</span></span>  
  
 <span data-ttu-id="9811a-124">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="9811a-124">E_UNEXPECTED</span></span>  
 <span data-ttu-id="9811a-125">Die Methode wurde für ein Rowset für das Massenkopieren aufgerufen, das zuvor von der [IRowsetFastLoad::Commit](irowsetfastload-commit-ole-db.md)-Methode für ungültig erklärt wurde.</span><span class="sxs-lookup"><span data-stu-id="9811a-125">The method was called on a bulk copy rowset previously invalidated by the [IRowsetFastLoad::Commit](irowsetfastload-commit-ole-db.md) method.</span></span>  
  
 <span data-ttu-id="9811a-126">DB_E_BADACCESSORHANDLE</span><span class="sxs-lookup"><span data-stu-id="9811a-126">DB_E_BADACCESSORHANDLE</span></span>  
 <span data-ttu-id="9811a-127">Das vom Consumer bereitgestellte *hAccessor* -Argument ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="9811a-127">The *hAccessor* argument provided by the consumer was invalid.</span></span>  
  
 <span data-ttu-id="9811a-128">DB_E_BADACCESSORTYPE</span><span class="sxs-lookup"><span data-stu-id="9811a-128">DB_E_BADACCESSORTYPE</span></span>  
 <span data-ttu-id="9811a-129">Der angegebene Accessor war kein Zeilenaccessor oder hat keinen consumer-eigenen Arbeitsspeicher angegeben.</span><span class="sxs-lookup"><span data-stu-id="9811a-129">The specified accessor was not a row accessor or did not specify consumer-owned memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9811a-130">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="9811a-130">Remarks</span></span>  
 <span data-ttu-id="9811a-131">Ein Fehler bei der Konvertierung der Consumerdaten in den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datentyp einer Spalte ruft eine E_FAIL-Rückgabe durch den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-OLE DB-Anbieter hervor.</span><span class="sxs-lookup"><span data-stu-id="9811a-131">An error converting consumer data to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type for a column causes an E_FAIL return from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span> <span data-ttu-id="9811a-132">Die Daten können entweder über eine beliebige [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]InsertRow \*\*-Methode oder nur über die \*\*Commit \*\*-Methode an \*\* übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="9811a-132">Data can be transmitted to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on any **InsertRow** method or only on **Commit** method.</span></span> <span data-ttu-id="9811a-133">lDie Consumer-Anwendung kann die **InsertRow** -Methode mehrere Male mit fehlerhaften Daten aufrufen, bevor eine Meldung eintrifft, dass die Daten nicht korrekt sind.</span><span class="sxs-lookup"><span data-stu-id="9811a-133">The consumer application can call the **InsertRow** method many times with erroneous data before it receives notice that a data type conversion error exists.</span></span> <span data-ttu-id="9811a-134">Die **Commit** -Methode gewährleistet, dass alle Daten ordnungsgemäß vom Consumer angegeben werden. Der Consumer kann die **Commit** -Methode gegebenenfalls verwenden, um die Daten zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="9811a-134">Because the **Commit** method ensures that all data is correctly specified by the consumer, the consumer can use the **Commit** method appropriately to validate data as necessary.</span></span>  
  
 <span data-ttu-id="9811a-135">Die Massenkopiervorgänge des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-OLE DB-Anbieters erlauben nur den Schreibzugriff.</span><span class="sxs-lookup"><span data-stu-id="9811a-135">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider bulk copy rowsets are write-only.</span></span> <span data-ttu-id="9811a-136">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-OLE DB-Anbieter macht keine Methoden verfügbar, die Abfragen von Consumern hinsichtlich des Rowsets verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="9811a-136">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes no methods allowing consumer query of the rowset.</span></span> <span data-ttu-id="9811a-137">Um die Verarbeitung zu beenden, kann der Consumer seine Verweise auf die [IRowsetFastLoad](irowsetfastload-ole-db.md)-Schnittstelle ohne die **Commit**-Methode senden.</span><span class="sxs-lookup"><span data-stu-id="9811a-137">To terminate processing, the consumer can release its reference on the [IRowsetFastLoad](irowsetfastload-ole-db.md) interface without calling the **Commit** method.</span></span> <span data-ttu-id="9811a-138">Es gibt keine Möglichkeit, auf von Consumern eingefügte Zeilen im Rowset zuzugreifen und deren Werte zu ändern oder diese einzeln aus dem Rowset zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="9811a-138">There are no facilities for accessing a consumer-inserted row in the rowset and changing its values, or removing it individually from the rowset.</span></span>  
  
 <span data-ttu-id="9811a-139">Massenkopierte Zeilen werden auf dem Server für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] formatiert.</span><span class="sxs-lookup"><span data-stu-id="9811a-139">Bulk copied rows are formatted on the server for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="9811a-140">Das Zeilenformat entspricht den Optionen, die eventuell für die Verbindung oder die Sitzung festgelegt wurden, wie z. B. ANSI_PADDING.</span><span class="sxs-lookup"><span data-stu-id="9811a-140">The row format is affected by any options that may have been set for the connection or session such as ANSI_PADDING.</span></span> <span data-ttu-id="9811a-141">Diese Option ist standardmäßig für alle über den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-OLE DB-Anbieter angebotenen Verbindungen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="9811a-141">This option is set on by default for any connection made through the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9811a-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9811a-142">See Also</span></span>  
 [<span data-ttu-id="9811a-143">IRowsetFastLoad &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="9811a-143">IRowsetFastLoad &#40;OLE DB&#41;</span></span>](irowsetfastload-ole-db.md)  
  
  
