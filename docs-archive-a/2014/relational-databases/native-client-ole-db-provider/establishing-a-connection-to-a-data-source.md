---
title: Herstellen einer Verbindung zu einer Datenquelle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- data sources [SQL Server Native Client]
- connections [SQL Server Native Client]
- SQL Server Native Client OLE DB provider, data source connections
- CoCreateInstance method
- OLE DB data sources [SQL Server Native Client]
ms.assetid: 7ebd1394-cc8d-4bcf-92f3-c374a26e7ba0
author: rothja
ms.author: jroth
ms.openlocfilehash: f88454339ee932c38655819cce475ab52d79975f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620834"
---
# <a name="establishing-a-connection-to-a-data-source"></a><span data-ttu-id="324bf-102">Herstellen einer Verbindung zu einer Datenquelle</span><span class="sxs-lookup"><span data-stu-id="324bf-102">Establishing a Connection to a Data Source</span></span>
  <span data-ttu-id="324bf-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Der Consumer muss zunächst eine Instanz eines Datenquellen Objekts erstellen, indem er die **CoCreateInstance** -Methode aufrufen, um auf den Native Client OLE DB-Anbieter zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="324bf-103">To access the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider, the consumer must first create an instance of a data source object by calling the **CoCreateInstance** method.</span></span> <span data-ttu-id="324bf-104">Ein eindeutiger Klassenbezeichner (CLSID) identifiziert jeden OLE DB-Anbieter.</span><span class="sxs-lookup"><span data-stu-id="324bf-104">A unique class identifier (CLSID) identifies each OLE DB provider.</span></span> <span data-ttu-id="324bf-105">Für den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter ist der Klassen Bezeichner CLSID_SQLNCLI10.</span><span class="sxs-lookup"><span data-stu-id="324bf-105">For the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider, the class identifier is CLSID_SQLNCLI10.</span></span> <span data-ttu-id="324bf-106">Sie können auch das Symbol SQLNCLI_CLSID verwenden, das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in den Native Client OLE DB-Anbieter aufgelöst wird, der in der sqlncli. h verwendet wird, auf die Sie verweisen.</span><span class="sxs-lookup"><span data-stu-id="324bf-106">You can also use the symbol SQLNCLI_CLSID that will resolve to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider that is used in the sqlncli.h that you reference.</span></span>  
  
 <span data-ttu-id="324bf-107">Das Datenquellenobjekt macht die **IDBProperties**-Schnittstelle verfügbar, die der Consumer verwendet, um grundlegende Authentifizierungsinformationen wie Servername, Datenbankname, Benutzer-ID und Kennwort bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="324bf-107">The data source object exposes the **IDBProperties** interface, which the consumer uses to provide basic authentication information such as server name, database name, user ID, and password.</span></span> <span data-ttu-id="324bf-108">Die **IDBProperties::SetProperties**-Methode wird aufgerufen, um diese Eigenschaften festzulegen.</span><span class="sxs-lookup"><span data-stu-id="324bf-108">The **IDBProperties::SetProperties** method is called to set these properties.</span></span>  
  
 <span data-ttu-id="324bf-109">Wenn mehrere Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] auf dem Computer ausgeführt werden, wird der Servername als ServerName\InstanceName angegeben.</span><span class="sxs-lookup"><span data-stu-id="324bf-109">If there are multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on the computer, the server name is specified as ServerName\InstanceName.</span></span>  
  
 <span data-ttu-id="324bf-110">Das Datenquellenobjekt macht auch die **IDBInitialize**-Schnittstelle verfügbar.</span><span class="sxs-lookup"><span data-stu-id="324bf-110">The data source object also exposes the **IDBInitialize** interface.</span></span> <span data-ttu-id="324bf-111">Nachdem die Eigenschaften festgelegt wurden, wird die Verbindung zur Datenquelle durch Aufrufen der **IDBInitialize::Initialize**-Methode hergestellt.</span><span class="sxs-lookup"><span data-stu-id="324bf-111">After the properties are set, connection to the data source is established by calling the **IDBInitialize::Initialize** method.</span></span> <span data-ttu-id="324bf-112">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="324bf-112">For example:</span></span>  
  
```  
CoCreateInstance(CLSID_SQLNCLI10,   
                 NULL,   
                 CLSCTX_INPROC_SERVER,  
                 IID_IDBInitialize,   
                 (void **) &pIDBInitialize)  
```  
  
 <span data-ttu-id="324bf-113">Dieser **cokreateinstance-Code** erstellt ein einzelnes-Objekt der-Klasse, die mit CLSID_SQLNCLI10 verknüpft ist (CSLID, das den Daten und dem Code zugeordnet ist, die zum Erstellen des-Objekts verwendet werden).</span><span class="sxs-lookup"><span data-stu-id="324bf-113">This call to **CoCreateInstance** creates a single object of the class associated with CLSID_SQLNCLI10 (CSLID associated with the data and code that will be used to create the object).</span></span> <span data-ttu-id="324bf-114">IID_IDBInitialize ist ein Verweis auf den Bezeichner der Schnittstelle (**IDBInitialize**), die zur Kommunikation mit dem Objekt verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="324bf-114">IID_IDBInitialize is a reference to the identifier of the interface (**IDBInitialize**) to be used to communicate with the object.</span></span>  
  
 <span data-ttu-id="324bf-115">Die folgende Funktion ist eine Beispielfunktion, die eine Verbindung zur Datenquelle initiiert und herstellt.</span><span class="sxs-lookup"><span data-stu-id="324bf-115">The following is a sample function that initializes and establishes a connection to the data source.</span></span>  
  
```  
void InitializeAndEstablishConnection() {  
   // Initialize the COM library.  
   CoInitialize(NULL);  
  
   // Obtain access to the SQL Server Native Client OLE DB provider.  
   hr = CoCreateInstance(CLSID_SQLNCLI10,   
                         NULL,   
                         CLSCTX_INPROC_SERVER,  
                         IID_IDBInitialize,   
                         (void **) &pIDBInitialize);  
   // Initialize property values needed to establish connection.  
   for (i = 0 ; i < 4 ; i++)   
      VariantInit(&InitProperties[i].vValue);  
  
   // Server name.  
   // See DBPROP structure for more information on InitProperties  
   InitProperties[0].dwPropertyID  = DBPROP_INIT_DATASOURCE;  
   InitProperties[0].vValue.vt    = VT_BSTR;  
   InitProperties[0].vValue.bstrVal=   
                     SysAllocString(L"Server");  
   InitProperties[0].dwOptions    = DBPROPOPTIONS_REQUIRED;  
   InitProperties[0].colid       = DB_NULLID;  
  
   // Database.  
   InitProperties[1].dwPropertyID  = DBPROP_INIT_CATALOG;  
   InitProperties[1].vValue.vt    = VT_BSTR;  
   InitProperties[1].vValue.bstrVal= SysAllocString(L"database");  
   InitProperties[1].dwOptions    = DBPROPOPTIONS_REQUIRED;  
   InitProperties[1].colid       = DB_NULLID;  
  
   // Username (login).  
   InitProperties[2].dwPropertyID  = DBPROP_AUTH_INTEGRATED;  
   InitProperties[2].vValue.vt    = VT_BSTR;  
   InitProperties[2].vValue.bstrVal= SysAllocString(L"SSPI");  
   InitProperties[2].dwOptions    = DBPROPOPTIONS_REQUIRED;  
   InitProperties[2].colid       = DB_NULLID;  
   InitProperties[3].dwOptions    = DBPROPOPTIONS_REQUIRED;  
   InitProperties[3].colid       = DB_NULLID;  
  
   // Construct the DBPROPSET structure(rgInitPropSet). The   
   // DBPROPSET structure is used to pass an array of DBPROP   
   // structures (InitProperties) to the SetProperties method.  
   rgInitPropSet[0].guidPropertySet = DBPROPSET_DBINIT;  
   rgInitPropSet[0].cProperties   = 4;  
   rgInitPropSet[0].rgProperties   = InitProperties;  
  
   // Set initialization properties.  
   hr = pIDBInitialize->QueryInterface(IID_IDBProperties,   
                           (void **)&pIDBProperties);  
   hr = pIDBProperties->SetProperties(1, rgInitPropSet);   
   pIDBProperties->Release();  
  
   // Now establish the connection to the data source.  
   pIDBInitialize->Initialize();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="324bf-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="324bf-116">See Also</span></span>  
 [<span data-ttu-id="324bf-117">Erstellen einer SQL Server Native Client OLE DB-Anbieteranwendung</span><span class="sxs-lookup"><span data-stu-id="324bf-117">Creating a SQL Server Native Client OLE DB Provider Application</span></span>](creating-a-sql-server-native-client-ole-db-provider-application.md)  
  
  
