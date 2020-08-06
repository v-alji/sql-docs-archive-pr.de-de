---
title: Große CLR-benutzerdefinierte Typen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- large CLR user-defined types
ms.assetid: b65eb61d-ccf6-49c0-98e7-9a4ef4b2f790
author: rothja
ms.author: jroth
ms.openlocfilehash: 27f0c13caea8c4aca63d78238509c6d05f1bf7bf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698079"
---
# <a name="large-clr-user-defined-types"></a><span data-ttu-id="a3e1e-102">Große benutzerdefinierte CLR-Typen</span><span class="sxs-lookup"><span data-stu-id="a3e1e-102">Large CLR User-Defined Types</span></span>
  <span data-ttu-id="a3e1e-103">In SQL Server 2005 waren benutzerdefinierte Typen (User-Defined Types, UDTs) in der Common Language Runtime (CLR) auf eine Größe von 8.000 Bytes beschränkt.</span><span class="sxs-lookup"><span data-stu-id="a3e1e-103">In SQL Server 2005, user-defined types (UDTs) in the common language runtime (CLR) were restricted to 8,000 bytes in size.</span></span> <span data-ttu-id="a3e1e-104">Diese Einschränkung wurde in [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] und höheren Versionen aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="a3e1e-104">This restriction has been lifted in [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] and later versions.</span></span> <span data-ttu-id="a3e1e-105">CLR-UDTs werden jetzt auf eine ähnliche Weise wie große Objekttypen (LOB) behandelt.</span><span class="sxs-lookup"><span data-stu-id="a3e1e-105">CLR UDTs are now treated in a similar way to large object (LOB) types.</span></span> <span data-ttu-id="a3e1e-106">UDTs mit genau oder weniger als 8.000 Byte verhalten sich also genau wie in SQL Server 2005. Größere UDTs werden aber unterstützt und zeigen ihre Größe als "unbegrenzt" an.</span><span class="sxs-lookup"><span data-stu-id="a3e1e-106">That is, UDTs less than or equal to 8,000 bytes behave the same way as in SQL Server 2005, but larger UDTs are supported and report their size as "unlimited".</span></span>  
  
 <span data-ttu-id="a3e1e-107">Weitere Informationen finden Sie unter [große benutzerdefinierte CLR-Typen &#40;OLE DB&#41;](../ole-db/large-clr-user-defined-types-ole-db.md) und [große CLR-benutzerdefinierte Typen &#40;ODBC-&#41;](../odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="a3e1e-107">For more information, see [Large CLR User-Defined Types &#40;OLE DB&#41;](../ole-db/large-clr-user-defined-types-ole-db.md) and [Large CLR User-Defined Types &#40;ODBC&#41;](../odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="use-cases"></a><span data-ttu-id="a3e1e-108">Anwendungsfälle</span><span class="sxs-lookup"><span data-stu-id="a3e1e-108">Use Cases</span></span>  
 <span data-ttu-id="a3e1e-109">Für ODBC umfasst die Unterstützung großer UDTs die Möglichkeit zum Versenden von UDT-Werten in Teilen als Data-at-Execution-Parameter.</span><span class="sxs-lookup"><span data-stu-id="a3e1e-109">For ODBC, support for large UDTs includes the ability to send UDT values in pieces as data-at-execution parameters.</span></span> <span data-ttu-id="a3e1e-110">Dies erfolgt mithilfe von SQLPutData.</span><span class="sxs-lookup"><span data-stu-id="a3e1e-110">This is done by using SQLPutData.</span></span>  
  
 <span data-ttu-id="a3e1e-111">Für OLE DB umfasst die Unterstützung großer UDTs die Möglichkeit zum Streamen von UDT-Werten zum und vom Server mithilfe der ISequentialStream-Bindung.</span><span class="sxs-lookup"><span data-stu-id="a3e1e-111">For OLE DB, support for large UDTs includes the ability to stream UDT values to and from the server by using ISequentialStream binding.</span></span>  
  
 <span data-ttu-id="a3e1e-112">UDTs kleiner oder gleich 8.000 Byte verhalten sich wie in SQL Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a3e1e-112">UDTs less than or equal to 8,000 bytes will behave as they did in SQL Server 2005.</span></span> <span data-ttu-id="a3e1e-113">Für OLE DB können Sie immer noch kleine UDTs mithilfe einer ISequentialStream-Bindung streamen.</span><span class="sxs-lookup"><span data-stu-id="a3e1e-113">For OLE DB, you can still stream small UDTs by using ISequentialStream binding.</span></span>  
  
 <span data-ttu-id="a3e1e-114">Manchmal muss systemeigener Code den Inhalt von CLR-UDTs verstehen, muss aber keine verwalteten Objekte instanziieren.</span><span class="sxs-lookup"><span data-stu-id="a3e1e-114">Sometimes native code will have to understand the contents of CLR UDTs, but will not have to instantiate managed objects.</span></span> <span data-ttu-id="a3e1e-115">In diesem Fall können Sie die benutzerdefinierte Serialisierung verwenden, um UDT-Werte auf dem Server in ein für die Clients bekanntes Format zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="a3e1e-115">If this is the case, you can use custom serialization to convert UDT values on the server into a well known format for clients.</span></span>  
  
 <span data-ttu-id="a3e1e-116">Bei Anwendungen, die über einen vorhandenen Datenzugriffscode verfügen, können Sie das CLR-UDT-Verhalten auf dem Client nutzen, indem Sie UDTs über systemeigene APIs abrufen und sie mithilfe von C++ CLI Interop in Anwendungen des gemischten Modus instanziieren.</span><span class="sxs-lookup"><span data-stu-id="a3e1e-116">For applications that have existing data access code, you can exploit CLR UDT behavior on the client by retrieving UDTs through native APIs and instantiating them by using C++ CLI interop in mixed mode applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3e1e-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a3e1e-117">See Also</span></span>  
 [<span data-ttu-id="a3e1e-118">SQL Server Native Client-Funktionen</span><span class="sxs-lookup"><span data-stu-id="a3e1e-118">SQL Server Native Client Features</span></span>](sql-server-native-client-features.md)  
  
  
