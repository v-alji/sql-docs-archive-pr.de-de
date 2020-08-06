---
title: Vergleichbarkeit für IRowsetFind | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- IRowsetFind comparability [ODBC]
ms.assetid: 7d148b56-9bbe-4e55-b31f-43f115705402
author: rothja
ms.author: jroth
ms.openlocfilehash: 8ad359ca4957b434c3798d1a441eb0fd57644a59
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609875"
---
# <a name="comparability-for-irowsetfind"></a><span data-ttu-id="79f10-102">Vergleichbarkeit für 'IRowsetFind'</span><span class="sxs-lookup"><span data-stu-id="79f10-102">Comparability for IRowsetFind</span></span>
  <span data-ttu-id="79f10-103">Für die date/time-Typen unterstützt IRowsetFind die folgenden Vergleiche:</span><span class="sxs-lookup"><span data-stu-id="79f10-103">For date/time types only, IRowsetFind supports the following comparisons:</span></span>  
  
-   <span data-ttu-id="79f10-104">LT</span><span class="sxs-lookup"><span data-stu-id="79f10-104">LT</span></span>  
  
-   <span data-ttu-id="79f10-105">LE</span><span class="sxs-lookup"><span data-stu-id="79f10-105">LE</span></span>  
  
-   <span data-ttu-id="79f10-106">EQ</span><span class="sxs-lookup"><span data-stu-id="79f10-106">EQ</span></span>  
  
-   <span data-ttu-id="79f10-107">GE</span><span class="sxs-lookup"><span data-stu-id="79f10-107">GE</span></span>  
  
-   <span data-ttu-id="79f10-108">GT</span><span class="sxs-lookup"><span data-stu-id="79f10-108">GT</span></span>  
  
-   <span data-ttu-id="79f10-109">NE</span><span class="sxs-lookup"><span data-stu-id="79f10-109">NE</span></span>  
  
-   <span data-ttu-id="79f10-110">IGNORE</span><span class="sxs-lookup"><span data-stu-id="79f10-110">IGNORE</span></span>  
  
 <span data-ttu-id="79f10-111">Bei dem Versuch eines anderen Vergleichs wird DB_E_BADCOMPAREOP zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="79f10-111">If any other comparison is attempted, DB_E_BADCOMPAREOP is returned.</span></span> <span data-ttu-id="79f10-112">Dieses Verhalten stimmt mit der OLE DB-Spezifikation überein.</span><span class="sxs-lookup"><span data-stu-id="79f10-112">This is consistent with the OLE DB specification.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79f10-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="79f10-113">See Also</span></span>  
 [<span data-ttu-id="79f10-114">Date and Time Improvements &#40;OLE DB&#41; (Verbesserungen bei Datum und Uhrzeit &#40;OLE DB&#41;)</span><span class="sxs-lookup"><span data-stu-id="79f10-114">Date and Time Improvements &#40;OLE DB&#41;</span></span>](date-and-time-improvements-ole-db.md)  
  
  
