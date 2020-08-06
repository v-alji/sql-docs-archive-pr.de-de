---
title: Sitzungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- sessions [OLE DB]
- SQL Server Native Client OLE DB provider, sessions
ms.assetid: 3a980816-675c-4fba-acc9-429297d85bbd
author: rothja
ms.author: jroth
ms.openlocfilehash: 545f301a9a73691dd19bb11476d005219b2f982f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630639"
---
# <a name="sessions"></a><span data-ttu-id="bdfa0-102">Sitzungen</span><span class="sxs-lookup"><span data-stu-id="bdfa0-102">Sessions</span></span>
  <span data-ttu-id="bdfa0-103">Eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter Sitzung stellt eine einzelne Verbindung zu einer Instanz von dar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bdfa0-103">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider session represents a single connection to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="bdfa0-104">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter erfordert, dass Sitzungen den Transaktions Bereich für eine Datenquelle begrenzen.</span><span class="sxs-lookup"><span data-stu-id="bdfa0-104">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider requires that sessions delimit transaction space for a data source.</span></span> <span data-ttu-id="bdfa0-105">Alle mit einem bestimmten Sitzungsobjekt erstellten Befehlsobjekte nehmen an der lokalen oder verteilten Transaktion des Sitzungsobjekts teil.</span><span class="sxs-lookup"><span data-stu-id="bdfa0-105">All command objects created from a specific session object participate in the local or distributed transaction of the session object.</span></span>  
  
 <span data-ttu-id="bdfa0-106">Das erste für die initialisierte Datenquelle erstellte Sitzungsobjekt empfängt die bei Initialisierung hergestellte [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Verbindung.</span><span class="sxs-lookup"><span data-stu-id="bdfa0-106">The first session object created on the initialized data source receives the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connection established at initialization.</span></span> <span data-ttu-id="bdfa0-107">Wenn alle Verweise auf die Schnittstellen des Sitzungsobjekts freigegeben werden, wird die Verbindung zur Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] für ein anderes für die Datenquelle erstelltes Sitzungsobjekt verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bdfa0-107">When all references on the interfaces of the session object are released, the connection to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] becomes available to another session object created on the data source.</span></span>  
  
 <span data-ttu-id="bdfa0-108">Ein zusätzliches für die Datenquelle erstelltes Sitzungsobjekt stellt eine eigene Verbindung zur Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] her, wie von der Datenquelle angegeben.</span><span class="sxs-lookup"><span data-stu-id="bdfa0-108">An additional session object created on the data source establishes its own connection to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as specified by the data source.</span></span> <span data-ttu-id="bdfa0-109">Die Verbindung zur Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] wird unterbrochen, wenn die Anwendung alle Verweise auf Objekte freigibt, die in dieser Sitzung erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="bdfa0-109">The connection to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is dropped when the application releases all references to objects created that session.</span></span>  
  
 <span data-ttu-id="bdfa0-110">Im folgenden Beispiel wird veranschaulicht, wie der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter verwendet wird, um eine Verbindung mit einer- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Datenbank herzustellen:</span><span class="sxs-lookup"><span data-stu-id="bdfa0-110">The following example demonstrates how to use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider to connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database:</span></span>  
  
```  
int main()  
{  
    // Interfaces used in the example.  
    IDBInitialize*      pIDBInitialize      = NULL;  
    IDBCreateSession*   pIDBCreateSession   = NULL;  
    IDBCreateCommand*   pICreateCmd1        = NULL;  
    IDBCreateCommand*   pICreateCmd2        = NULL;  
    IDBCreateCommand*   pICreateCmd3        = NULL;  
  
    // Initialize COM.  
    if (FAILED(CoInitialize(NULL)))  
    {  
        // Display error from CoInitialize.  
        return (-1);  
    }  
  
    // Get the memory allocator for this task.  
    if (FAILED(CoGetMalloc(MEMCTX_TASK, &g_pIMalloc)))  
    {  
        // Display error from CoGetMalloc.  
        goto EXIT;  
    }  
  
    // Create an instance of the data source object.  
    if (FAILED(CoCreateInstance(CLSID_SQLNCLI10, NULL,  
        CLSCTX_INPROC_SERVER, IID_IDBInitialize, (void**)  
        &pIDBInitialize)))  
    {  
        // Display error from CoCreateInstance.  
        goto EXIT;  
    }  
  
    // The InitFromPersistedDS function   
    // performs IDBInitialize->Initialize() establishing  
    // the first application connection to the instance of SQL Server.  
    if (FAILED(InitFromPersistedDS(pIDBInitialize, L"MyDataSource",  
        NULL, NULL)))  
    {  
        goto EXIT;  
    }  
  
    // The IDBCreateSession interface is implemented on the data source  
    // object. Maintaining the reference received maintains the   
    // connection of the data source to the instance of SQL Server.  
    if (FAILED(pIDBInitialize->QueryInterface(IID_IDBCreateSession,  
        (void**) &pIDBCreateSession)))  
    {  
        // Display error from pIDBInitialize.  
        goto EXIT;  
    }  
  
    // Releasing this has no effect on the SQL Server connection  
    // of the data source object because of the reference maintained by  
    // pIDBCreateSession.  
    pIDBInitialize->Release();  
    pIDBInitialize = NULL;  
  
    // The session created next receives the SQL Server connection of  
    // the data source object. No new connection is established.  
    if (FAILED(pIDBCreateSession->CreateSession(NULL,  
        IID_IDBCreateCommand, (IUnknown**) &pICreateCmd1)))  
    {  
        // Display error from pIDBCreateSession.  
        goto EXIT;  
    }  
  
    // A new connection to the instance of SQL Server is established to support the  
    // next session object created. On successful completion, the  
    // application has two active connections on the SQL Server.  
    if (FAILED(pIDBCreateSession->CreateSession(NULL,  
        IID_IDBCreateCommand, (IUnknown**) &pICreateCmd2)))  
    {  
        // Display error from pIDBCreateSession.  
        goto EXIT;  
    }  
  
    // pICreateCmd1 has the data source connection. Because the  
    // reference on the IDBCreateSession interface of the data source  
    // has not been released, releasing the reference on the session  
    // object does not terminate a connection to the instance of SQL Server.  
    // However, the connection of the data source object is now   
    // available to another session object. After a successful call to   
    // Release, the application still has two active connections to the   
    // instance of SQL Server.  
    pICreateCmd1->Release();  
    pICreateCmd1 = NULL;  
  
    // The next session created gets the SQL Server connection  
    // of the data source object. The application has two active  
    // connections to the instance of SQL Server.  
    if (FAILED(pIDBCreateSession->CreateSession(NULL,  
        IID_IDBCreateCommand, (IUnknown**) &pICreateCmd3)))  
    {  
        // Display error from pIDBCreateSession.  
        goto EXIT;  
    }  
  
EXIT:  
    // Even on error, this does not terminate a SQL Server connection   
    // because pICreateCmd1 has the connection of the data source   
    // object.  
    if (pICreateCmd1 != NULL)  
        pICreateCmd1->Release();  
  
    // Releasing the reference on pICreateCmd2 terminates the SQL  
    // Server connection supporting the session object. The application  
    // now has only a single active connection on the instance of SQL Server.  
    if (pICreateCmd2 != NULL)  
        pICreateCmd2->Release();  
  
    // Even on error, this does not terminate a SQL Server connection   
    // because pICreateCmd3 has the connection of the   
    // data source object.  
    if (pICreateCmd3 != NULL)  
        pICreateCmd3->Release();  
  
    // On release of the last reference on a data source interface, the  
    // connection of the data source object to the instance of SQL Server is broken.  
    // The example application now has no SQL Server connections active.  
    if (pIDBCreateSession != NULL)  
        pIDBCreateSession->Release();  
  
    // Called only if an error occurred while attempting to get a   
    // reference on the IDBCreateSession interface of the data source.  
    // If so, the call to IDBInitialize::Uninitialize terminates the   
    // connection of the data source object to the instance of SQL Server.  
    if (pIDBInitialize != NULL)  
    {  
        if (FAILED(pIDBInitialize->Uninitialize()))  
        {  
            // Uninitialize is not required, but it fails if an  
            // interface has not been released. Use it for  
            // debugging.  
        }  
        pIDBInitialize->Release();  
    }  
  
    if (g_pIMalloc != NULL)  
        g_pIMalloc->Release();  
  
    CoUninitialize();  
  
    return (0);  
}  
```  
  
 <span data-ttu-id="bdfa0-111">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Das Herstellen einer Verbindung von Native Client OLE DB-Anbieter Sitzungs Objekten mit einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] kann einen erheblichen mehr Aufwand für Anwendungen generieren, die Sitzungs Objekte ständig erstellen und freigeben.</span><span class="sxs-lookup"><span data-stu-id="bdfa0-111">Connecting [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider session objects to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can generate significant overhead for applications that continually create and release session objects.</span></span> <span data-ttu-id="bdfa0-112">Der Aufwand kann minimiert werden, indem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter Sitzungs Objekte effizient verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="bdfa0-112">The overhead can be minimized by managing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider session objects efficiently.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="bdfa0-113">Native Client OLE DB-Anbieter Anwendungen können die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Verbindung eines Sitzungs Objekts aktiv halten, indem Sie einen Verweis auf mindestens eine Schnittstelle des Objekts beibehalten.</span><span class="sxs-lookup"><span data-stu-id="bdfa0-113">Native Client OLE DB provider applications can keep the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connection of a session object active by maintaining a reference on at least one interface of the object.</span></span>  
  
 <span data-ttu-id="bdfa0-114">Durch Aufrechterhalten eines Pools von Verweisen auf Befehlserstellungsobjekte können aktive Verbindungen für diese Sitzungsobjekte im Pool aktiviert bleiben.</span><span class="sxs-lookup"><span data-stu-id="bdfa0-114">For example, maintaining a pool of command creation object references keeps active connections for those session objects in the pool.</span></span> <span data-ttu-id="bdfa0-115">Wenn Sitzungsobjekte angefordert werden, übergibt der Poolverwaltungscode einen gültigen **IDBCreateCommand**-Schnittstellenzeiger an die Anwendungsmethode, die die Sitzung anfordert.</span><span class="sxs-lookup"><span data-stu-id="bdfa0-115">As session objects are required, the pool maintenance code passes a valid **IDBCreateCommand** interface pointer to the application method requiring the session.</span></span> <span data-ttu-id="bdfa0-116">Wenn die Anwendungsmethode die Sitzung nicht mehr erfordert, gibt die Methode den Schnittstellenzeiger an den Poolverwaltungscode zurück, anstatt den Verweis der Anwendung auf das Befehlserstellungsobjekt freizugeben.</span><span class="sxs-lookup"><span data-stu-id="bdfa0-116">When the application method no longer requires the session, the method returns the interface pointer back to the pool maintenance code rather than releasing the application's reference to the command creation object.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bdfa0-117">Im vorherigen Beispiel wird die **IDBCreateCommand**-Schnittstelle verwendet, da die **ICommand**-Schnittstelle die **GetDBSession**-Methode implementiert. Dies ist die einzige Methode im Befehls- oder Rowsetbereich, mit der ein Objekt die Sitzung bestimmen kann, in der es erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="bdfa0-117">In the preceding example, the **IDBCreateCommand** interface is used because the **ICommand** interface implements the **GetDBSession** method, the only method in command or rowset scope that allows an object to determine the session on which it was created.</span></span> <span data-ttu-id="bdfa0-118">Daher ermöglicht einzig ein Befehlsobjekt einer Anwendung das Abrufen eines Datenquellobjekt-Zeigers, von dem aus weitere Sitzungen erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="bdfa0-118">Therefore, a command object, and only a command object, allows an application to retrieve a data source object pointer from which additional sessions can be created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdfa0-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bdfa0-119">See Also</span></span>  
 [<span data-ttu-id="bdfa0-120">Datenquellenobjekte &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="bdfa0-120">Data Source Objects &#40;OLE DB&#41;</span></span>](data-source-objects-ole-db.md)  
  
  
