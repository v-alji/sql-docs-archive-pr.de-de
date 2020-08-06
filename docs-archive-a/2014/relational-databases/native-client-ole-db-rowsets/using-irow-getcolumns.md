---
title: Verwenden von IRow::GetColumns | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- fetching rows
- IRow interface
- single row fetching [SQL Server Native Client]
- OLE DB rowsets, fetching
- rowsets [OLE DB], fetching
- GetColumns method
ms.assetid: 1f5d2e03-e6fe-4ea1-b71d-55d02b5d59ae
author: rothja
ms.author: jroth
ms.openlocfilehash: f323dda790946565bc0dbd63c9e1f9d17ac7494b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615367"
---
# <a name="using-irowgetcolumns"></a><span data-ttu-id="0201b-102">Verwenden von IRow::GetColumns</span><span class="sxs-lookup"><span data-stu-id="0201b-102">Using IRow::GetColumns</span></span>
  <span data-ttu-id="0201b-103">Die **IRow**-Implementierung lässt sequenzielle Vorwärtszugriffe auf die Spalten zu.</span><span class="sxs-lookup"><span data-stu-id="0201b-103">The **IRow** implementation allows forward-only sequential access to the columns.</span></span> <span data-ttu-id="0201b-104">Sie können entweder mit einem einzigen Aufruf von **IRow::GetColumns** auf alle Spalten einer Zeile zugreifen oder **IRow::GetColumns** mehrmals aufrufen, um jeweils auf einige Spalten in der Zeile zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="0201b-104">You can either access all the columns in the row with a single call to **IRow::GetColumns** or call **IRow::GetColumns** multiple times every time that you access several columns in the row.</span></span>  
  
 <span data-ttu-id="0201b-105">Die verschiedenen Aufrufe von **IRow::GetColumns** sollten sich nicht überschneiden.</span><span class="sxs-lookup"><span data-stu-id="0201b-105">The multiple calls to **IRow::GetColumns** should not overlap.</span></span> <span data-ttu-id="0201b-106">Wenn beispielsweise mit dem ersten **IRow::GetColumns**-Aufruf die Spalten 1, 2 und 3 abgerufen werden, dann sollten mit dem zweiten **IRow::GetColumns**-Aufruf die Spalten 4, 5 und 6 abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="0201b-106">For example, if the first call to **IRow::GetColumns** retrieves columns 1, 2, and 3, the second call to **IRow::GetColumns** should call for columns 4, 5, and 6.</span></span> <span data-ttu-id="0201b-107">Wenn sich spätere Aufrufe von **IRow::GetColumns** mit früheren Aufrufen überschneiden, wird das Statusflag (dwstatus-Feld in der DBCOLUMNACCESS-Struktur) auf DBSTATUS_E_UNAVAILABLE festgelegt.</span><span class="sxs-lookup"><span data-stu-id="0201b-107">If later calls to **IRow::GetColumns** overlap, the status flag (dwstatus field in DBCOLUMNACCESS) is set to DBSTATUS_E_UNAVAILABLE.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0201b-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0201b-108">See Also</span></span>  
 [<span data-ttu-id="0201b-109">Abrufen einer einzelnen Zeile mit IRow</span><span class="sxs-lookup"><span data-stu-id="0201b-109">Fetching a Single Row with IRow</span></span>](fetching-a-single-row-with-irow.md)  
  
  
