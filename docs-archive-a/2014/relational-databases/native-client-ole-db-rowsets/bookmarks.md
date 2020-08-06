---
title: Lesezeichen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- bookmarks [OLE DB]
- SQL Server Native Client OLE DB provider, bookmarks
- rowsets [OLE DB], bookmarks
- OLE DB rowsets, bookmarks
ms.assetid: 7d9076f2-bf9c-452e-b816-70371a0c1644
author: rothja
ms.author: jroth
ms.openlocfilehash: be8e5486e5a442ddafa133a9cbd3f408d30a50d7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722733"
---
# <a name="bookmarks"></a><span data-ttu-id="8cd0e-102">Lesezeichen</span><span class="sxs-lookup"><span data-stu-id="8cd0e-102">Bookmarks</span></span>
  <span data-ttu-id="8cd0e-103">Lesezeichen ermöglichen es Consumern, schnell zu einer Zeile zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="8cd0e-103">Bookmarks let consumers quickly return to a row.</span></span> <span data-ttu-id="8cd0e-104">Mit Lesezeichen können Consumer auf der Grundlage des Lesezeichenwerts beliebig auf Zeilen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="8cd0e-104">With bookmarks, consumers can access rows randomly based on the bookmark value.</span></span> <span data-ttu-id="8cd0e-105">Die Lesezeichenspalte ist die Spalte 0 (null) im Rowset.</span><span class="sxs-lookup"><span data-stu-id="8cd0e-105">The bookmark column is column 0 in the rowset.</span></span> <span data-ttu-id="8cd0e-106">Der Consumer legt den Wert des Felds dwFlag der Bindungsstruktur auf DBCOLUMNSINFO_ISBOOKMARK fest, um anzugeben, dass die Spalte als Lesezeichen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8cd0e-106">The consumer sets the dwFlag field value of the binding structure to DBCOLUMNSINFO_ISBOOKMARK to indicate that the column is used as a bookmark.</span></span> <span data-ttu-id="8cd0e-107">Der Consumer legt zudem die Rowseteigenschaft DBPROP_BOOKMARKS auf VARIANT_TRUE fest.</span><span class="sxs-lookup"><span data-stu-id="8cd0e-107">The consumer also sets the rowset property DBPROP_BOOKMARKS to VARIANT_TRUE.</span></span> <span data-ttu-id="8cd0e-108">Dadurch kann die Spalte 0 im Rowset vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="8cd0e-108">This lets column 0 be present in the rowset.</span></span> <span data-ttu-id="8cd0e-109">Mit der **IRowsetLocate::GetRowsAt**-Methode werden dann Zeilen abgerufen. Dabei wird mit der Zeile begonnen, die in einem Lesezeichen als Offset angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="8cd0e-109">The **IRowsetLocate::GetRowsAt** method is then used to fetch rows, starting with the row specified as an offset from a bookmark.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cd0e-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8cd0e-110">See Also</span></span>  
 [<span data-ttu-id="8cd0e-111">Rowsets</span><span class="sxs-lookup"><span data-stu-id="8cd0e-111">Rowsets</span></span>](rowsets.md)  
  
  
