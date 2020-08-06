---
title: Blobs und OLE-Objekte | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- BLOBs, OLE objects
- BLOBs
- storage object [OLE DB]
- SQL Server Native Client OLE DB provider, BLOBs
- large data, OLE objects
ms.assetid: 767fa2f6-9cd2-436f-add5-e760bed29a58
author: rothja
ms.author: jroth
ms.openlocfilehash: 15f8b4915ba9b05a5be19854a2e27a2e8ff3a346
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725605"
---
# <a name="blobs-and-ole-objects"></a><span data-ttu-id="3fe32-102">BLOBs und OLE-Objekte</span><span class="sxs-lookup"><span data-stu-id="3fe32-102">BLOBs and OLE Objects</span></span>
  <span data-ttu-id="3fe32-103">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter macht die **ISequentialStream** -Schnittstelle verfügbar, um den Consumerzugriff auf die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Datentypen **ntext**, **Text**, **Image**, **varchar (max)**, **nvarchar (max)**, **varbinary (max)** und XML als Binary Large Objects (BLOB) zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="3fe32-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **ISequentialStream** interface to support consumer access to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **ntext**, **text**, **image**, **varchar(max)**, **nvarchar(max)**, **varbinary(max)**, and xml data types as binary large objects (BLOBs).</span></span> <span data-ttu-id="3fe32-104">Die Methode **Read** für **ISequentialStream** ermöglicht dem Consumer, große Datenmengen in überschaubaren Abschnitten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="3fe32-104">The **Read** method on **ISequentialStream** lets the consumer retrieve much data in manageable chunks.</span></span>  
  
 <span data-ttu-id="3fe32-105">Ein Beispiel für diese Feature finden Sie unter [Festlegen von großen Daten &#40;OLE DB&#41;](../native-client-ole-db-how-to/set-large-data-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="3fe32-105">For a sample demonstrating this feature, see [Set Large Data &#40;OLE DB&#41;](../native-client-ole-db-how-to/set-large-data-ole-db.md).</span></span>  
  
 <span data-ttu-id="3fe32-106">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter kann eine vom Consumer implementierte **IStorage** -Schnittstelle verwenden, wenn der Consumer den Schnittstellen Zeiger in einem Accessor bereitstellt, der für die Datenänderung gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="3fe32-106">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider can use a consumer-implemented **IStorage** interface when the consumer provides the interface pointer in an accessor bound for data modification.</span></span>  
  
 <span data-ttu-id="3fe32-107">Bei Datentypen mit umfangreichen Werten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] überprüft der Native Client OLE DB-Anbieter die typgrößen Annahmen in **IRowset** und DDL-Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="3fe32-107">For large value data types, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider checks for type size assumptions in **IRowset** and DDL interfaces.</span></span> <span data-ttu-id="3fe32-108">Spalten mit den Datentypen **varchar**, **nvarchar**und **varbinary** , deren maximale Größe auf Unlimited festgelegt ist, werden durch die Schemarowsets und Schnittstellen, die Spaltendatentypen zurückgeben, als ISLONG dargestellt.</span><span class="sxs-lookup"><span data-stu-id="3fe32-108">Columns with **varchar**, **nvarchar**, and **varbinary** data types with max size set to unlimited will be represented as ISLONG through the schema rowsets and interfaces returning column data types.</span></span>  
  
 <span data-ttu-id="3fe32-109">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter macht die Typen **varchar (max)**, **varbinary (max)** und **nvarchar (max)** als DBTYPE_STR, DBTYPE_BYTES und DBTYPE_WSTR verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3fe32-109">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **varchar(max)**, **varbinary(max)** and **nvarchar(max)** types as DBTYPE_STR, DBTYPE_BYTES and DBTYPE_WSTR respectively.</span></span>  
  
 <span data-ttu-id="3fe32-110">Um mit diesen Typen zu arbeiten, hat eine Anwendung die folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="3fe32-110">To work with these types an application has the following options:</span></span>  
  
-   <span data-ttu-id="3fe32-111">Als den betreffenden Typ binden (DBTYPE_STR, DBTYPE_BYTES, DBTYPE_WSTR).</span><span class="sxs-lookup"><span data-stu-id="3fe32-111">Bind as the type (DBTYPE_STR, DBTYPE_BYTES, DBTYPE_WSTR).</span></span> <span data-ttu-id="3fe32-112">Wenn der Puffer nicht groß genug ist, werden Daten abgeschnitten, wie dies auch in früheren Versionen der Fall war (obwohl jetzt umfangreichere Werte verfügbar sind).</span><span class="sxs-lookup"><span data-stu-id="3fe32-112">If the buffer is not big enough truncation will occur, exactly as for these types in previous releases (although larger values are now available).</span></span>  
  
-   <span data-ttu-id="3fe32-113">Als den betreffenden Typ binden und zudem DBTYPE_BYREF angeben</span><span class="sxs-lookup"><span data-stu-id="3fe32-113">Bind as the type and also specify DBTYPE_BYREF.</span></span>  
  
-   <span data-ttu-id="3fe32-114">Als DBTYPE_IUNKNOWN binden und Streaming verwenden</span><span class="sxs-lookup"><span data-stu-id="3fe32-114">Bind as DBTYPE_IUNKNOWN and use streaming.</span></span>  
  
 <span data-ttu-id="3fe32-115">Wenn die Bindung an DBTYPE_IUNKNOWN erfolgt, wird die Streamingfunktion ISequentialStream verwendet.</span><span class="sxs-lookup"><span data-stu-id="3fe32-115">If bound to DBTYPE_IUNKNOWN, ISequentialStream stream functionality is used.</span></span> <span data-ttu-id="3fe32-116">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter unterstützt das Binden von Ausgabeparametern als DBTYPE_IUNKNOWN für Datentypen mit großen Werten, um Szenarios zu vereinfachen, in denen eine gespeicherte Prozedur diese Datentypen als Rückgabewerte zurückgibt, die als DBTYPE_IUNKNOWN für den Client verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="3fe32-116">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports binding output parameters as DBTYPE_IUNKNOWN for large value data types to facilitate scenarios where a stored procedure returns these data types as return values which will be exposed as DBTYPE_IUNKNOWN to the client.</span></span>  
  
## <a name="storage-object-limitations"></a><span data-ttu-id="3fe32-117">Speicherobjekteinschränkungen</span><span class="sxs-lookup"><span data-stu-id="3fe32-117">Storage Object Limitations</span></span>  
  
-   <span data-ttu-id="3fe32-118">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter kann nur ein einzelnes geöffnetes Speicher Objekt unterstützen.</span><span class="sxs-lookup"><span data-stu-id="3fe32-118">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider can support only a single open storage object.</span></span> <span data-ttu-id="3fe32-119">Wenn versucht wird, mehrere Speicherobjekte zu öffnen (um einen Verweis auf mehrere **ISequentialStream**-Schnittstellenzeiger abzurufen), wird DBSTATUS_E_CANTCREATE zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3fe32-119">Attempts to open more than one storage object (to get a reference on more than one **ISequentialStream** interface pointer) return DBSTATUS_E_CANTCREATE.</span></span>  
  
-   <span data-ttu-id="3fe32-120">Im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter ist der Standardwert der DBPROP_BLOCKINGSTORAGEOBJECTS schreibgeschützten Eigenschaft VARIANT_TRUE.</span><span class="sxs-lookup"><span data-stu-id="3fe32-120">In the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider, the default value of the DBPROP_BLOCKINGSTORAGEOBJECTS read-only property is VARIANT_TRUE.</span></span> <span data-ttu-id="3fe32-121">Das zeigt an, dass einige Methoden (solche, die sich nicht in den Speicherobjekten befinden) mit E_UNEXPECTED fehlschlagen, wenn ein Speicherobjekt aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="3fe32-121">This indicates that if a storage object is active, some methods (other than those on the storage objects) will fail with E_UNEXPECTED.</span></span>  
  
-   <span data-ttu-id="3fe32-122">Die Länge der Daten, die von einem vom Consumer implementierten Speicher Objekt vorgelegt werden, muss dem Native Client OLE DB-Anbieter bekannt gemacht werden, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Wenn der Zeilen Accessor erstellt wird, der auf das Speicher Objekt verweist.</span><span class="sxs-lookup"><span data-stu-id="3fe32-122">The length of data presented by a consumer-implemented storage object must be made known to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider when the row accessor that references the storage object is created.</span></span> <span data-ttu-id="3fe32-123">Der Consumer muss einen Längenindikator in der zur Accessorerstellung verwendeten DBBINDING-Struktur binden.</span><span class="sxs-lookup"><span data-stu-id="3fe32-123">The consumer must bind a length indicator in the DBBINDING structure used for accessor creation.</span></span>  
  
-   <span data-ttu-id="3fe32-124">Wenn eine Zeile mehr als einen einzelnen großen Datenwert enthält und DBPROP_ACCESSORDER nicht DBPROPVAL_AO_RANDOM ist, muss der Consumer entweder ein vom [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Cursor unterstütztes Native Client OLE DB Anbieter-Rowset verwenden, um Zeilendaten abzurufen oder alle großen Datenwerte zu verarbeiten, bevor andere Zeilen Werte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="3fe32-124">If a row contains more than a single large data value and DBPROP_ACCESSORDER is not DBPROPVAL_AO_RANDOM, the consumer must either use a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider cursor-supported rowset to retrieve row data or process all large data values before retrieving other row values.</span></span> <span data-ttu-id="3fe32-125">Wenn DBPROP_ACCESSORDER DBPROPVAL_AO_RANDOM ist, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] speichert der Native Client OLE DB-Anbieter alle XML-Datentypen als Binary Large Objects (BLOB) zwischen, sodass in beliebiger Reihenfolge auf ihn zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="3fe32-125">If DBPROP_ACCESSORDER is DBPROPVAL_AO_RANDOM, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider caches all the xml data types as binary large objects (BLOBs) so that it can be accessed in any order.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3fe32-126">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="3fe32-126">In This Section</span></span>  
  
-   [<span data-ttu-id="3fe32-127">Abrufen großer Datenmengen</span><span class="sxs-lookup"><span data-stu-id="3fe32-127">Getting Large Data</span></span>](getting-large-data.md)  
  
-   [<span data-ttu-id="3fe32-128">Festlegen großer Datenmengen</span><span class="sxs-lookup"><span data-stu-id="3fe32-128">Setting Large Data</span></span>](setting-large-data.md)  
  
-   [<span data-ttu-id="3fe32-129">Streamingunterstützung für BLOB-Ausgabeparameter</span><span class="sxs-lookup"><span data-stu-id="3fe32-129">Streaming Support for BLOB Output Parameters</span></span>](streaming-support-for-blob-output-parameters.md)  
  
## <a name="see-also"></a><span data-ttu-id="3fe32-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3fe32-130">See Also</span></span>  
 <span data-ttu-id="3fe32-131">[SQL Server Native Client &#40;OLE DB&#41;](../native-client/ole-db/sql-server-native-client-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="3fe32-131">[SQL Server Native Client &#40;OLE DB&#41;](../native-client/ole-db/sql-server-native-client-ole-db.md) </span></span>  
 [<span data-ttu-id="3fe32-132">Verwenden von Datentypen mit umfangreichen Werten</span><span class="sxs-lookup"><span data-stu-id="3fe32-132">Using Large Value Types</span></span>](../native-client/features/using-large-value-types.md)  
  
  
