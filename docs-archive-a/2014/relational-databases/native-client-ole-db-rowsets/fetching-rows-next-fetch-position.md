---
title: Nächste Fetch-Position | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- fetching rows
- OLE DB rowsets, fetching
- next fetch position
- rowsets [OLE DB], fetching
ms.assetid: 9ef74b3f-c9c0-492f-9b93-d65738a61abd
author: rothja
ms.author: jroth
ms.openlocfilehash: fcc771eef4acf603148bc4b4318e810b1bd72302
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696786"
---
# <a name="next-fetch-position"></a><span data-ttu-id="c814e-102">Nächste Abrufposition</span><span class="sxs-lookup"><span data-stu-id="c814e-102">Next Fetch Position</span></span>
  <span data-ttu-id="c814e-103">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter verfolgt die nächste Abruf Position nach, sodass eine Sequenz von Aufrufen der **GetNextRows** -Methode (ohne überspringen, Richtungsänderungen oder zwischengeschaltete Aufrufe der **FindNextRow**-, **Seek**-oder **RestartPosition** -Methoden) das gesamte Rowset liest, ohne eine Zeile zu überspringen oder zu wiederholen.</span><span class="sxs-lookup"><span data-stu-id="c814e-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider keeps track of the next fetch position so that a sequence of calls to the **GetNextRows** method (without skips, changes of direction, or intervening calls to the **FindNextRow**, **Seek**, or **RestartPosition** methods) reads the whole rowset without skipping or repeating any row.</span></span> <span data-ttu-id="c814e-104">Die nächste Abrufposition wird entweder durch Aufrufen von **IRowset::GetNextRows**, **IRowset::RestartPosition** oder **IRowsetIndex::Seek** oder durch Aufrufen von **FindNextRow** mit einem NULL-Wert für *pBookmark* geändert.</span><span class="sxs-lookup"><span data-stu-id="c814e-104">The next fetch position is changed either by calling **IRowset::GetNextRows**, **IRowset::RestartPosition**, or **IRowsetIndex::Seek**, or by calling **FindNextRow** with a null *pBookmark* value.</span></span> <span data-ttu-id="c814e-105">Das Aufrufen von **FindNextRow** mit einem *pBookmark*-Wert ungleich NULL beeinflusst die nächste Abrufposition nicht.</span><span class="sxs-lookup"><span data-stu-id="c814e-105">Calling **FindNextRow** with a nonnull *pBookmark* value does not affect the next fetch position.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c814e-106">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c814e-106">See Also</span></span>  
 [<span data-ttu-id="c814e-107">Abrufen von Zeilen</span><span class="sxs-lookup"><span data-stu-id="c814e-107">Fetching Rows</span></span>](fetching-rows.md)  
  
  
