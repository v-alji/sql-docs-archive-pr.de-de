---
title: Datenquellenobjekte (OLE DB) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- data access [SQL Server Native Client], data source objects
- SQL Server Native Client, data source objects
- SQLNCLI, data source objects
- SQL Server Native Client OLE DB provider, data source objects
- OLE DB data source objects [SQL Server Native Client]
- data source objects [OLE DB]
- CLSID
ms.assetid: c1d4ed20-ad3b-4e33-a26b-38d7517237b7
author: rothja
ms.author: jroth
ms.openlocfilehash: 9cf3f0b0308d655b50149c174547c19966f550ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695589"
---
# <a name="data-source-objects-ole-db"></a><span data-ttu-id="fbebc-102">Datenquellenobjekte (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="fbebc-102">Data Source Objects (OLE DB)</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="fbebc-103">Native Client verwendet den Begriff Datenquelle für den Satz von OLE DB Schnittstellen, die zum Herstellen einer Verknüpfung mit einem Datenspeicher verwendet werden, z [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . b..</span><span class="sxs-lookup"><span data-stu-id="fbebc-103">Native Client uses the term data source for the set of OLE DB interfaces used to establish a link to a data store, such as [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="fbebc-104">Das Erstellen einer Instanz des Datenquellen Objekts des Anbieters ist die erste Aufgabe eines [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client Consumers.</span><span class="sxs-lookup"><span data-stu-id="fbebc-104">Creating an instance of the data source object of the provider is the first task of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client consumer.</span></span>  
  
 <span data-ttu-id="fbebc-105">Jeder OLE DB-Anbieter deklariert einen Klassenbezeichner (CLSID) für sich.</span><span class="sxs-lookup"><span data-stu-id="fbebc-105">Every OLE DB provider declares a class identifier (CLSID) for itself.</span></span> <span data-ttu-id="fbebc-106">Die CLSID für den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter ist die C/C++-GUID CLSID_SQLNCLI10 (das Symbol SQLNCLI_CLSID wird in die korrekte ProgID in der Datei sqlncli. h aufgelöst, auf die Sie verweisen).</span><span class="sxs-lookup"><span data-stu-id="fbebc-106">The CLSID for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider is the C/C++ GUID CLSID_SQLNCLI10 (the symbol SQLNCLI_CLSID will resolve to the correct progid in the sqlncli.h file that you reference).</span></span> <span data-ttu-id="fbebc-107">Mit der CLSID verwendet der Consumer die OLE-Funktion **CoCreateInstance** zum Erstellen einer Instanz des Datenquellenobjekts.</span><span class="sxs-lookup"><span data-stu-id="fbebc-107">With the CLSID, the consumer uses the OLE **CoCreateInstance** function to manufacture an instance of the data source object.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="fbebc-108">Native Client ist ein in-Process-Server.</span><span class="sxs-lookup"><span data-stu-id="fbebc-108">Native Client is an in-process server.</span></span> <span data-ttu-id="fbebc-109">Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter Objekten werden mithilfe des CLSCTX_INPROC_SERVER-Makros erstellt, um den ausführbaren Kontext anzugeben.</span><span class="sxs-lookup"><span data-stu-id="fbebc-109">Instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider objects are created using the CLSCTX_INPROC_SERVER macro to indicate the executable context.</span></span>  
  
 <span data-ttu-id="fbebc-110">Das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Datenquellen Objekt des Native Client OLE DB-Anbieters macht die OLE DB Initialisierungs Schnittstellen verfügbar, die es dem Consumer ermöglichen, eine Verbindung mit vorhandenen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Datenbanken herzustellen.</span><span class="sxs-lookup"><span data-stu-id="fbebc-110">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider data source object exposes the OLE DB initialization interfaces that allow the consumer to connect to existing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases.</span></span>  
  
 <span data-ttu-id="fbebc-111">Jede Verbindung, die über den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter hergestellt wird, legt diese Optionen automatisch fest:</span><span class="sxs-lookup"><span data-stu-id="fbebc-111">Every connection made through the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider sets these options automatically:</span></span>  
  
-   <span data-ttu-id="fbebc-112">SET ANSI_WARNINGS ON</span><span class="sxs-lookup"><span data-stu-id="fbebc-112">SET ANSI_WARNINGS ON</span></span>  
  
-   <span data-ttu-id="fbebc-113">SET ANSI_NULLS ON</span><span class="sxs-lookup"><span data-stu-id="fbebc-113">SET ANSI_NULLS ON</span></span>  
  
-   <span data-ttu-id="fbebc-114">SET ANSI_PADDING ON</span><span class="sxs-lookup"><span data-stu-id="fbebc-114">SET ANSI_PADDING ON</span></span>  
  
-   <span data-ttu-id="fbebc-115">SET ANSI_NULL_DFLT_ON ON</span><span class="sxs-lookup"><span data-stu-id="fbebc-115">SET ANSI_NULL_DFLT_ON ON</span></span>  
  
-   <span data-ttu-id="fbebc-116">SET QUOTED_IDENTIFIER ON</span><span class="sxs-lookup"><span data-stu-id="fbebc-116">SET QUOTED_IDENTIFIER ON</span></span>  
  
-   <span data-ttu-id="fbebc-117">SET CONCAT_OF_NULL_YIELDS_NULL ON</span><span class="sxs-lookup"><span data-stu-id="fbebc-117">SET CONCAT_OF_NULL_YIELDS_NULL ON</span></span>  
  
 <span data-ttu-id="fbebc-118">In diesem Beispiel wird das Klassenbezeichnermakro verwendet, um ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Datenquellen Objekt des Native Client OLE DB-Anbieters zu erstellen und einen Verweis auf seine **IDBInitialize** -Schnittstelle zu erhalten</span><span class="sxs-lookup"><span data-stu-id="fbebc-118">This example uses the class identifier macro to create a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider data source object and get a reference to its **IDBInitialize** interface.</span></span>  
  
```  
IDBInitialize*   pIDBInitialize;  
HRESULT          hr;  
  
hr = CoCreateInstance(CLSID_SQLNCLI10, NULL, CLSCTX_INPROC_SERVER,  
    IID_IDBInitialize, (void**) &pIDBInitialize);  
  
if (SUCCEEDED(hr))  
{  
    //  Perform necessary processing with the interface.  
    pIDBInitialize->Uninitialize();  
    pIDBInitialize->Release();  
}  
else  
{  
    // Display error from CoCreateInstance.  
}  
```  
  
 <span data-ttu-id="fbebc-119">Bei erfolgreicher Erstellung einer Instanz eines [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Datenquellen Objekts des Native Client OLE DB Anbieters kann die Consumeranwendung fortgesetzt werden, indem die Datenquelle initialisiert und Sitzungen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="fbebc-119">With successful creation of an instance of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider data source object, the consumer application can continue by initializing the data source and creating sessions.</span></span> <span data-ttu-id="fbebc-120">OLE DB-Sitzungen präsentieren die Schnittstellen, die Datenzugriff und -bearbeitung ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="fbebc-120">OLE DB sessions present the interfaces that allow data access and manipulation.</span></span>  
  
 <span data-ttu-id="fbebc-121">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter stellt die erste Verbindung zu einer angegebenen Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] als Teil einer erfolgreichen Datenquellen Initialisierung her.</span><span class="sxs-lookup"><span data-stu-id="fbebc-121">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider makes its first connection to a specified instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as part of a successful data source initialization.</span></span> <span data-ttu-id="fbebc-122">Die Verbindung wird beibehalten, solange eine Referenz auf einer beliebigen Datenquellen-Initialisierungsschnittstelle beibehalten wird oder bis die Methode **IDBInitialize::Uninitialize** aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="fbebc-122">The connection is maintained as long as a reference is maintained on any data source initialization interface, or until the **IDBInitialize::Uninitialize** method is called.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fbebc-123">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="fbebc-123">In This Section</span></span>  
  
-   [<span data-ttu-id="fbebc-124">Datenquelleneigenschaften &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="fbebc-124">Data Source Properties &#40;OLE DB&#41;</span></span>](data-source-properties-ole-db.md)  
  
-   [<span data-ttu-id="fbebc-125">Eigenschaften von Datenquelleninformationen</span><span class="sxs-lookup"><span data-stu-id="fbebc-125">Data Source Information Properties</span></span>](data-source-information-properties.md)  
  
-   [<span data-ttu-id="fbebc-126">Initialisierungs- und Autorisierungseigenschaften</span><span class="sxs-lookup"><span data-stu-id="fbebc-126">Initialization and Authorization Properties</span></span>](initialization-and-authorization-properties.md)  
  
-   [<span data-ttu-id="fbebc-127">Sitzungen</span><span class="sxs-lookup"><span data-stu-id="fbebc-127">Sessions</span></span>](sessions.md)  
  
-   [<span data-ttu-id="fbebc-128">Sitzungseigenschaften</span><span class="sxs-lookup"><span data-stu-id="fbebc-128">Session Properties</span></span>](session-properties-sql-server-native-client-ole-db-provider.md)  
  
-   [<span data-ttu-id="fbebc-129">Persistente Datenquellenobjekte</span><span class="sxs-lookup"><span data-stu-id="fbebc-129">Persisted Data Source Objects</span></span>](persisted-data-source-objects.md)  
  
## <a name="see-also"></a><span data-ttu-id="fbebc-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fbebc-130">See Also</span></span>  
 [<span data-ttu-id="fbebc-131">SQL Server Native Client &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="fbebc-131">SQL Server Native Client &#40;OLE DB&#41;</span></span>](../native-client/ole-db/sql-server-native-client-ole-db.md)  
  
  
