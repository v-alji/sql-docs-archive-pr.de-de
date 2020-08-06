---
title: Erneutes Synchronisieren von Zeilen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- synchronization [OLE DB]
- IRowsetResynch interface
- resynchronizing rows
- data updates [SQL Server], OLE DB
ms.assetid: d2d30505-a878-4aa9-b821-53d8118a45a5
author: rothja
ms.author: jroth
ms.openlocfilehash: 47c628ae583f3e635f422d5146f64508372a1114
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615372"
---
# <a name="resynchronizing-rows"></a><span data-ttu-id="dd5d5-102">Erneutes Synchronisieren von Zeilen</span><span class="sxs-lookup"><span data-stu-id="dd5d5-102">Resynchronizing Rows</span></span>
  <span data-ttu-id="dd5d5-103">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter unterstützt **IRowsetResynch** [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nur für Cursor unterstützte Rowsets.</span><span class="sxs-lookup"><span data-stu-id="dd5d5-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports **IRowsetResynch** on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cursor-supported rowsets only.</span></span> <span data-ttu-id="dd5d5-104">**IRowsetResynch** ist nicht bedarfsgesteuert verfügbar.</span><span class="sxs-lookup"><span data-stu-id="dd5d5-104">**IRowsetResynch** is not available on demand.</span></span> <span data-ttu-id="dd5d5-105">Der Consumer muss die Schnittstelle vor dem Öffnen des Rowsets anfordern.</span><span class="sxs-lookup"><span data-stu-id="dd5d5-105">The consumer must request the interface before opening the rowset.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd5d5-106">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dd5d5-106">See Also</span></span>  
 [<span data-ttu-id="dd5d5-107">Aktualisieren von Daten in Rowsets</span><span class="sxs-lookup"><span data-stu-id="dd5d5-107">Updating Data in Rowsets</span></span>](updating-data-in-rowsets.md)  
  
  
