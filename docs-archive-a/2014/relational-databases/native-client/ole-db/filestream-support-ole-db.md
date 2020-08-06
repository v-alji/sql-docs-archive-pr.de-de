---
title: FILESTREAM-Unterstützung (OLE DB) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB [FILESTREAM support]
- FILESTREAM [SQL Server], OLE DB
ms.assetid: c2bd3dfd-6103-43d1-859e-8ed8d19c58d3
author: rothja
ms.author: jroth
ms.openlocfilehash: cde3c2cd1b72773cfcf17eacedeb3276dd2f63da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619791"
---
# <a name="filestream-support-ole-db"></a><span data-ttu-id="c5826-102">FILESTREAM-Unterstützung (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="c5826-102">FILESTREAM Support (OLE DB)</span></span>
  <span data-ttu-id="c5826-103">Ab [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] und [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 10,0 unterstützt OLE DB die erweiterte FILESTREAM-Funktion.</span><span class="sxs-lookup"><span data-stu-id="c5826-103">Beginning with [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 10.0, OLE DB supports the enhanced FILESTREAM feature.</span></span> <span data-ttu-id="c5826-104">Weitere Informationen zu dieser Funktion finden Sie [unter FILESTREAM-Unterstützung](../features/filestream-support.md).</span><span class="sxs-lookup"><span data-stu-id="c5826-104">For more information about this feature, see [FILESTREAM Support](../features/filestream-support.md).</span></span> <span data-ttu-id="c5826-105">Beispiele finden Sie unter [FILESTREAM und OLE DB](../../native-client-ole-db-how-to/filestream/filestream-and-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="c5826-105">For samples, see [Filestream and OLE DB](../../native-client-ole-db-how-to/filestream/filestream-and-ole-db.md).</span></span>  
  
 <span data-ttu-id="c5826-106">Um `varbinary(max)`-Werte über 2 GB zu senden und zu empfangen, verwendet eine Anwendung `DBTYPE_IUNKNOWN` in Parameter- und Ergebnisbindungen.</span><span class="sxs-lookup"><span data-stu-id="c5826-106">To send and receive `varbinary(max)` values greater than 2 GB, an application uses `DBTYPE_IUNKNOWN` in parameter and result bindings.</span></span> <span data-ttu-id="c5826-107">Der Anbieter muss für Parameter IUnknown::QueryInterface für ISequentialStream und für Ergebnisse abrufen, die ISequentialStream zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="c5826-107">For parameters the provider must call IUnknown::QueryInterface for ISequentialStream and for results that return ISequentialStream.</span></span>  
  
 <span data-ttu-id="c5826-108">Für OLE DB wird die auf ISequentialStream-Werte bezogene Überprüfung gelockert.</span><span class="sxs-lookup"><span data-stu-id="c5826-108">For OLE DB, checking related to ISequentialStream values will be relaxed.</span></span> <span data-ttu-id="c5826-109">Wenn sich *wType* `DBTYPE_IUNKNOWN` in der `DBBINDING` Struktur befindet, kann die Längen Überprüfung entweder durch Weglassen `DBPART_LENGTH` von *dwPart* oder durch Festlegen der Länge der Daten (bei Offset *obLength* im Datenpuffer) auf ~ 0 deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="c5826-109">When *wType* is `DBTYPE_IUNKNOWN` in the `DBBINDING` struct, length checking can be disabled either by omitting `DBPART_LENGTH` from *dwPart* or by setting the length of the data (at offset *obLength* in the data buffer) to ~0.</span></span> <span data-ttu-id="c5826-110">In diesem Fall überprüft der Provider die Länge des Werts nicht und fordert alle Daten an (oder gibt sie zurück), die über den Datenstrom zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="c5826-110">In this case, the provider will not check the length of the value and will request and return all of the data available through the stream.</span></span> <span data-ttu-id="c5826-111">Diese Änderung wird auf alle LOB-Typen (Large Object) und auf XML angewendet, allerdings nur, wenn eine Verbindung zu [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)]-Servern (oder höher) besteht.</span><span class="sxs-lookup"><span data-stu-id="c5826-111">This change will be applied to all large object (LOB) types and XML, but only when connected to [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] (or later) servers.</span></span> <span data-ttu-id="c5826-112">Auf diese Weise erhalten Entwickler eine höhere Flexibilität, während sie die Konsistenz und Abwärtskompatibilität für vorhandene Anwendungen und Downlevelserver beibehalten.</span><span class="sxs-lookup"><span data-stu-id="c5826-112">This will provide greater flexibility for developers, while maintaining consistency and backwards compatibility for existing applications and downlevel servers.</span></span>  
  
 <span data-ttu-id="c5826-113">Diese Änderung wirkt sich auf alle Schnittstellen aus, die Daten übertragen (hauptsächlich IRowset::GetData, ICommand::Execute und IRowsetFastLoad::InsertRow).</span><span class="sxs-lookup"><span data-stu-id="c5826-113">This change affects all interfaces that transfer data, principally IRowset::GetData, ICommand::Execute, and IRowsetFastLoad::InsertRow.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5826-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c5826-114">See Also</span></span>  
 [<span data-ttu-id="c5826-115">Programmierung für SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="c5826-115">SQL Server Native Client Programming</span></span>](../sql-server-native-client-programming.md)  
  
  
