---
title: ISSAbort (OLE DB) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- ISSAbort interface
ms.assetid: 7c4df482-4a83-4da0-802b-3637b507693a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 7195311fefe3f0f1b7b4d6d789aa8d8487bc3bfe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726166"
---
# <a name="issabort-ole-db"></a><span data-ttu-id="92d0a-102">'ISSAbort' (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="92d0a-102">ISSAbort (OLE DB)</span></span>
  <span data-ttu-id="92d0a-103">Die **ISSAbort** -Schnittstelle, die im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter verfügbar gemacht wird, stellt die [ISSAbort::Abort](../../relational-databases/native-client-ole-db-interfaces/issabort-abort-ole-db.md) -Methode bereit. Sie dient dazu, das aktuelle Rowset sowie Befehle abzubrechen, die mit dem Befehl, der das Rowset ursprünglich generierte, verknüpft sind und noch nicht ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="92d0a-103">The **ISSAbort** interface, which is exposed in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider, provides the [ISSAbort::Abort](../../relational-databases/native-client-ole-db-interfaces/issabort-abort-ole-db.md) method that is used to cancel the current rowset plus any commands batched with the command that initially generated the rowset, and that have not yet completed execution.</span></span>  
  
 <span data-ttu-id="92d0a-104">**ISSAbort** ist eine für den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-Anbieter spezifische Schnittstelle, die bei Verwendung von **QueryInterface** für das **IMultipleResults** -Objekt, das von **ICommand::Execute** oder **IOpenRowset::OpenRowset**zurückgegeben wird, verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="92d0a-104">**ISSAbort** is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client provider-specific interface available by using **QueryInterface** on the **IMultipleResults** object returned by **ICommand::Execute** or **IOpenRowset::OpenRowset**.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="92d0a-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="92d0a-105">In This Section</span></span>  
  
|<span data-ttu-id="92d0a-106">Methode</span><span class="sxs-lookup"><span data-stu-id="92d0a-106">Method</span></span>|<span data-ttu-id="92d0a-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="92d0a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="92d0a-108">ISSAbort:: Abort &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="92d0a-108">ISSAbort::Abort &#40;OLE DB&#41;</span></span>](../../relational-databases/native-client-ole-db-interfaces/issabort-abort-ole-db.md)|<span data-ttu-id="92d0a-109">Bricht das aktuelle Rowset sowie eventuell mit dem aktuellen Befehl verknüpfte Batchbefehle ab.</span><span class="sxs-lookup"><span data-stu-id="92d0a-109">Cancels the current rowset plus any batched commands associated with the current command.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="92d0a-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="92d0a-110">See Also</span></span>  
 [<span data-ttu-id="92d0a-111">Schnittstellen &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="92d0a-111">Interfaces &#40;OLE DB&#41;</span></span>](../../../2014/database-engine/dev-guide/interfaces-ole-db.md)  
  
  
