---
title: Abrufen großer Datenmengen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- BLOBs, OLE objects
- DBPROP_ACCESSORDER property
- SQL Server Native Client OLE DB provider, BLOBs
- large data, OLE objects
ms.assetid: a31c5632-96aa-483f-a307-004c5149fbc0
author: rothja
ms.author: jroth
ms.openlocfilehash: 38602df026d2e752a758672dde23a59a26ad4917
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725606"
---
# <a name="getting-large-data"></a><span data-ttu-id="e6d30-102">Abrufen großer Datenmengen</span><span class="sxs-lookup"><span data-stu-id="e6d30-102">Getting Large Data</span></span>
  <span data-ttu-id="e6d30-103">Im Allgemeinen sollten Consumer Code isolieren, der ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB Speicher Objekt des Anbieters aus anderem Code erstellt, der Daten verarbeitet, auf die nicht über einen **ISequentialStream** -Schnittstellen Zeiger verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="e6d30-103">In general, consumers should isolate code that creates a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider storage object from other code that handles data not referenced through an **ISequentialStream** interface pointer.</span></span>  
  
 <span data-ttu-id="e6d30-104">In diesem Thema wird die mit folgenden Funktionen verfügbare Funktionalität behandelt:</span><span class="sxs-lookup"><span data-stu-id="e6d30-104">This topic refers to functionality available with the following functions:</span></span>  
  
-   <span data-ttu-id="e6d30-105">IRowset:GetData</span><span class="sxs-lookup"><span data-stu-id="e6d30-105">IRowset:GetData</span></span>  
  
-   <span data-ttu-id="e6d30-106">IRow::GetColumns</span><span class="sxs-lookup"><span data-stu-id="e6d30-106">IRow::GetColumns</span></span>  
  
-   <span data-ttu-id="e6d30-107">ICommand::Execute</span><span class="sxs-lookup"><span data-stu-id="e6d30-107">ICommand::Execute</span></span>  
  
 <span data-ttu-id="e6d30-108">Wenn die DBPROP_ACCESSORDER-Eigenschaft (in der Rowset-Eigenschaften Gruppe) auf einen der Werte DBPROPVAL_AO_SEQUENTIAL oder DBPROPVAL_AO_SEQUENTIALSTORAGEOBJECTS festgelegt ist, sollte der Consumer nur eine einzelne Daten Zeile in einem Aufrufen der **GetNextRows** -Methode abrufen, da die BLOB-Daten nicht gepuffert werden.</span><span class="sxs-lookup"><span data-stu-id="e6d30-108">If the DBPROP_ACCESSORDER property (in the rowset property group) is set to either of the values DBPROPVAL_AO_SEQUENTIAL or DBPROPVAL_AO_SEQUENTIALSTORAGEOBJECTS, the consumer should fetch only a single row of data in a call to the **GetNextRows** method because BLOB data is not buffered.</span></span> <span data-ttu-id="e6d30-109">Ist der Wert von DBPROP_ACCESSORDER auf DBPROPVAL_AO_RANDOM festgelegt, kann der Consumer mehrere Datenzeilen mit **GetNextRows** abrufen.</span><span class="sxs-lookup"><span data-stu-id="e6d30-109">If the value of DBPROP_ACCESSORDER is set to DBPROPVAL_AO_RANDOM, the consumer can fetch multiple rows of data in **GetNextRows**.</span></span>  
  
 <span data-ttu-id="e6d30-110">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter ruft große Daten von erst ab, wenn er [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vom Consumer dazu aufgefordert wird.</span><span class="sxs-lookup"><span data-stu-id="e6d30-110">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not retrieve large data from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] until requested to do so by the consumer.</span></span> <span data-ttu-id="e6d30-111">Der Consumer sollte alle kleinen Datenmengen in einem Accessor zusammenfassen und dann einen oder mehrere Accessoren zum Abrufen großer Datenwerte verwenden.</span><span class="sxs-lookup"><span data-stu-id="e6d30-111">The consumer should bind all short data in one accessor, and then use one or more temporary accessors to retrieve large data values as required.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6d30-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e6d30-112">Example</span></span>  
 <span data-ttu-id="e6d30-113">In diesem Beispiel wird ein großer Datenwert aus einer einzelnen Spalte abgerufen:</span><span class="sxs-lookup"><span data-stu-id="e6d30-113">This example retrieves a large data value from a single column:</span></span>  
  
```  
HRESULT GetUnboundData  
    (  
    IRowset* pIRowset,  
    HROW hRow,  
    ULONG nCol,   
    BYTE* pUnboundData  
    )  
    {  
    UINT                cbRow = sizeof(IUnknown*) + sizeof(ULONG);  
    BYTE*               pRow = new BYTE[cbRow];  
  
    DBOBJECT            dbobject;  
  
    IAccessor*          pIAccessor = NULL;  
    HACCESSOR           haccessor;  
  
    DBBINDING           dbbinding;  
    ULONG               ulbindstatus;  
  
    ULONG               dwStatus;  
    ISequentialStream*  pISequentialStream;  
    ULONG               cbRead;  
  
    HRESULT             hr;  
  
    // Set up the DBOBJECT structure.  
    dbobject.dwFlags = STGM_READ;  
    dbobject.iid = IID_ISequentialStream;  
  
    // Create the DBBINDING, requesting a storage-object pointer from  
    // The SQL Server Native Client OLE DB provider.  
    dbbinding.iOrdinal = nCol;  
    dbbinding.obValue = 0;  
    dbbinding.obStatus = sizeof(IUnknown*);  
    dbbinding.obLength = 0;  
    dbbinding.pTypeInfo = NULL;  
    dbbinding.pObject = &dbobject;  
    dbbinding.pBindExt = NULL;  
    dbbinding.dwPart = DBPART_VALUE | DBPART_STATUS;  
    dbbinding.dwMemOwner = DBMEMOWNER_CLIENTOWNED;  
    dbbinding.eParamIO = DBPARAMIO_NOTPARAM;  
    dbbinding.cbMaxLen = 0;  
    dbbinding.dwFlags = 0;  
    dbbinding.wType = DBTYPE_IUNKNOWN;  
    dbbinding.bPrecision = 0;  
    dbbinding.bScale = 0;  
  
    if (FAILED(hr = pIRowset->  
        QueryInterface(IID_IAccessor, (void**) &pIAccessor)))  
        {  
        // Process QueryInterface failure.  
        return (hr);  
        }  
  
    // Create the accessor.  
    if (FAILED(hr = pIAccessor->CreateAccessor(DBACCESSOR_ROWDATA, 1,  
        &dbbinding, 0, &haccessor, &ulbindstatus)))  
        {  
        // Process error from CreateAccessor.  
        pIAccessor->Release();  
        return (hr);  
        }  
  
    // Read and process BLOCK_SIZE bytes at a time.  
    if (SUCCEEDED(hr = pIRowset->GetData(hRow, haccessor, pRow)))  
        {  
        dwStatus = *((ULONG*) (pRow + dbbinding.obStatus));  
  
        if (dwStatus == DBSTATUS_S_ISNULL)  
            {  
            // Process NULL data  
            }  
        else if (dwStatus == DBSTATUS_S_OK)  
            {  
            pISequentialStream = *((ISequentialStream**)   
                (pRow + dbbinding.obValue));  
  
            do  
                {  
                if (SUCCEEDED(hr =  
                    pISequentialStream->Read(pUnboundData,  
                    BLOCK_SIZE, &cbRead)))  
                    {  
                    pUnboundData += cbRead;  
                    }  
                }  
            while (SUCCEEDED(hr) && cbRead >= BLOCK_SIZE);  
  
            pISequentialStream->Release();  
            }  
        }  
    else  
        {  
        // Process error from GetData.  
        }  
  
    pIAccessor->ReleaseAccessor(haccessor, NULL);  
    pIAccessor->Release();  
    delete [] pRow;  
  
    return (hr);  
    }  
```  
  
## <a name="see-also"></a><span data-ttu-id="e6d30-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e6d30-114">See Also</span></span>  
 <span data-ttu-id="e6d30-115">[BLOB-und OLE-Objekte](blobs-and-ole-objects.md) </span><span class="sxs-lookup"><span data-stu-id="e6d30-115">[BLOBs and OLE Objects](blobs-and-ole-objects.md) </span></span>  
 [<span data-ttu-id="e6d30-116">Verwenden von Datentypen mit umfangreichen Werten</span><span class="sxs-lookup"><span data-stu-id="e6d30-116">Using Large Value Types</span></span>](../native-client/features/using-large-value-types.md)  
  
  
