---
title: Persistente Datenquellenobjekte | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB data source objects [SQL Server Native Client]
- data source objects [OLE DB]
- SQL Server Native Client OLE DB provider, persisted data source objects
- persisted data source objects
ms.assetid: dfdacc81-42fe-4f20-8969-bed1f743defe
author: rothja
ms.author: jroth
ms.openlocfilehash: d6d115b6640c910a70a9a29a36607a122f650c3c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609199"
---
# <a name="persisted-data-source-objects"></a><span data-ttu-id="0f836-102">Persistente Datenquellenobjekte</span><span class="sxs-lookup"><span data-stu-id="0f836-102">Persisted Data Source Objects</span></span>
  <span data-ttu-id="0f836-103">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter unterstützt persistente Datenquellen Objekte mit der **IPersistFile** -Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="0f836-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports persisted data source objects with the **IPersistFile** interface.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="0f836-104">Beispiele</span><span class="sxs-lookup"><span data-stu-id="0f836-104">Examples</span></span>  
 <span data-ttu-id="0f836-105">**A. Persistentes Speichern der Datenquelleninitialisierung:**</span><span class="sxs-lookup"><span data-stu-id="0f836-105">**A. Persist data source initialization:**</span></span>  
  
 <span data-ttu-id="0f836-106">Dieses Beispiel zeigt eine Funktion, die Eigenschaften zur Datenquelleninitialisierung, in denen ein Server, eine Datenbank und der Windows-Authentifizierungsmodus für die Verbindung definiert sind, persistent speichert.</span><span class="sxs-lookup"><span data-stu-id="0f836-106">This example shows a function that persists data source initialization properties defining a server, database, and the use of the Windows Authentication Mode for connection.</span></span> <span data-ttu-id="0f836-107">Der Server- und der Datenbankname werden in den Funktionsparametern *pLocation* und *pDatasource* empfangen.</span><span class="sxs-lookup"><span data-stu-id="0f836-107">The server name and database name are received in the *pLocation* and *pDatasource* parameters of the function.</span></span>  
  
```  
HRESULT SetAndSaveInitProps  
    (  
    IDBInitialize* pIDBInitialize,  
    WCHAR* pDataSource,  
    WCHAR* pCatalog,  
    BOOL bUseWinNTAuth  
    )  
    {  
    const ULONG     nProps = 4;  
    ULONG           nSSProps;  
    ULONG           nPropSets;  
    ULONG           nProp;  
    IDBProperties*  pIDBProperties  = NULL;  
    IPersistFile*   pIPersistFile   = NULL;  
    DBPROP          aInitProps[nProps];  
    DBPROP*         aSSInitProps    = NULL;  
    DBPROPSET*      aInitPropSets   = NULL;  
    HRESULT         hr;  
  
        nSSProps = 0;  
        nPropSets = 1;  
  
    aInitPropSets = new DBPROPSET[nPropSets];  
  
    // Initialize common property options.  
    for (nProp = 0; nProp < nProps; nProp++)  
        {  
        VariantInit(&aInitProps[nProp].vValue);  
        aInitProps[nProp].dwOptions = DBPROPOPTIONS_REQUIRED;  
        aInitProps[nProp].colid = DB_NULLID;  
        }  
  
    // Level of prompting that will be done to complete the connection  
    // process.  
    aInitProps[0].dwPropertyID = DBPROP_INIT_PROMPT;  
    aInitProps[0].vValue.vt = VT_I2;  
    aInitProps[0].vValue.iVal = DBPROMPT_NOPROMPT;       
  
    // Server name.  
    aInitProps[1].dwPropertyID = DBPROP_INIT_DATASOURCE;      
    aInitProps[1].vValue.vt = VT_BSTR;  
    aInitProps[1].vValue.bstrVal = SysAllocString(pDataSource);  
  
    // Database.  
    aInitProps[2].dwPropertyID = DBPROP_INIT_CATALOG;  
    aInitProps[2].vValue.vt = VT_BSTR;  
    aInitProps[2].vValue.bstrVal = SysAllocString(pCatalog);  
  
    aInitProps[3].dwPropertyID = DBPROP_AUTH_INTEGRATED;  
    if (bUseWinNTAuth == TRUE)  
    {  
        aInitProps[3].vValue.vt = VT_BSTR;  
        aInitProps[3].vValue.bstrVal = SysAllocString(L"SSPI");  
    } //end if  
  
    // Now that properties are set, construct the PropertySet array.  
    aInitPropSets[0].guidPropertySet = DBPROPSET_DBINIT;  
    aInitPropSets[0].cProperties = nProps;  
    aInitPropSets[0].rgProperties = aInitProps;  
  
    // Set initialization properties  
    pIDBInitialize->QueryInterface(IID_IDBProperties,  
        (void**) &pIDBProperties);  
    hr = pIDBProperties->SetProperties(nPropSets, aInitPropSets);  
    if (FAILED(hr))  
        {  
        // Display error from failed SetProperties.  
        }  
    pIDBProperties->Release();  
  
    // Free references on OLE known strings.  
    for (nProp = 0; nProp < nProps; nProp++)  
        {  
        if (aInitProps[nProp].vValue.vt == VT_BSTR)  
            SysFreeString(aInitProps[nProp].vValue.bstrVal);  
        }  
  
    for (nProp = 0; nProp < nSSProps; nProp++)  
        {  
        if (aSSInitProps[nProp].vValue.vt == VT_BSTR)  
            SysFreeString(aSSInitProps[nProp].vValue.bstrVal);  
        }  
  
    // Free dynamically allocated memory.  
    delete [] aInitPropSets;  
    delete [] aSSInitProps;  
  
    // On success, persist the data source.  
    if (SUCCEEDED(hr))  
        {  
        pIDBInitialize->QueryInterface(IID_IPersistFile,  
            (void**) &pIPersistFile);  
  
        hr = pIPersistFile->Save(OLESTR("MyDataSource.txt"), FALSE);  
  
        if (FAILED(hr))  
            {  
            // Display errors from IPersistFile interface.  
            }  
        pIPersistFile->Release();  
        }  
  
    return (hr);  
    }  
```  
  
 <span data-ttu-id="0f836-108">**B. Verwenden der persistenten Datenquelleninitialisierung:**</span><span class="sxs-lookup"><span data-stu-id="0f836-108">**B. Use persisted data source initialization:**</span></span>  
  
 <span data-ttu-id="0f836-109">Dieses Beispiel verwendet ein persistentes Datenquellenobjekt mit zusätzlichen Initialisierungseigenschaften für einen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Anmeldenamen und ein Kennwort.</span><span class="sxs-lookup"><span data-stu-id="0f836-109">This example uses a persisted data source object with additional initialization properties that provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login and password.</span></span>  
  
```  
HRESULT InitFromPersistedDS  
    (  
    IDBInitialize* pIDBInitialize,  
    WCHAR* pPersistedDSN,  
    WCHAR* pUID,  
    WCHAR* pPWD  
    )  
    {  
    //const ULONG   nProps = 3;  
    const ULONG     nProps = 1;  
    const ULONG     nPropSets = 1;  
    ULONG           nProp;  
    IDBProperties*  pIDBProperties  = NULL;  
    IPersistFile*   pIPersistFile   = NULL;  
    DBPROP          aInitProps[nProps];  
    DBPROPSET       aInitPropSets[nPropSets];  
    HRESULT         hr;  
  
    // First load the persisted data source information.  
    pIDBInitialize->QueryInterface(IID_IPersistFile,  
        (void**) &pIPersistFile);  
  
    hr = pIPersistFile->Load(pPersistedDSN, STGM_DIRECT);  
  
    if (FAILED(hr))  
        {  
        // Display errors from IPersistFile interface.  
        }  
    pIPersistFile->Release();  
  
    if (FAILED(hr))  
        {  
        return (hr);  
        }  
  
    // Initialize common property options.  
    for (nProp = 0; nProp < nProps; nProp++)  
        {  
        VariantInit(&aInitProps[nProp].vValue);  
        aInitProps[nProp].dwOptions = DBPROPOPTIONS_REQUIRED;  
        aInitProps[nProp].colid = DB_NULLID;  
        }  
  
    // Level of prompting that will be done to complete the connection  
    // process.  
    aInitProps[0].dwPropertyID = DBPROP_INIT_PROMPT;  
    aInitProps[0].vValue.vt = VT_I2;  
    aInitProps[0].vValue.iVal = DBPROMPT_NOPROMPT;      
  
    // Now that properties are set, construct the PropertySet array.  
    aInitPropSets[0].guidPropertySet = DBPROPSET_DBINIT;  
    aInitPropSets[0].cProperties = nProps;  
    aInitPropSets[0].rgProperties = aInitProps;  
  
    // Set initialization properties  
    pIDBInitialize->QueryInterface(IID_IDBProperties,  
        (void**) &pIDBProperties);  
    hr = pIDBProperties->SetProperties(nPropSets, aInitPropSets);  
    if (SUCCEEDED(hr))  
        {  
        hr = pIDBInitialize->Initialize();  
        if (FAILED(hr))  
            {  
            DumpError(pIDBInitialize, IID_IDBInitialize);  
            }  
        }  
    else  
        {  
        // Display error from failed SetProperties.  
        }  
    pIDBProperties->Release();  
  
    // Free references on OLE known strings.  
    for (nProp = 0; nProp < nProps; nProp++)  
        {  
        if (aInitProps[nProp].vValue.vt == VT_BSTR)  
            SysFreeString(aInitProps[nProp].vValue.bstrVal);  
        }  
  
    return (hr);  
    }  
```  
  
 <span data-ttu-id="0f836-110">Die **IPersistFile::Save**-Methode kann vor oder nach dem Aufruf von **IDBInitialize::Initialize** aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="0f836-110">The **IPersistFile::Save** method can be called before or after calling **IDBInitialize::Initialize**.</span></span> <span data-ttu-id="0f836-111">Durch Aufruf der Methode nach einer erfolgreichen Rückgabe von **IDBInitialize::Initialize** wird sichergestellt, dass eine gültige Datenquellenspezifikation persistent gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="0f836-111">Calling the method after a successful return from **IDBInitialize::Initialize** ensures a valid data source specification is persisted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f836-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0f836-112">See Also</span></span>  
 [<span data-ttu-id="0f836-113">Datenquellenobjekte &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="0f836-113">Data Source Objects &#40;OLE DB&#41;</span></span>](data-source-objects-ole-db.md)  
  
  
