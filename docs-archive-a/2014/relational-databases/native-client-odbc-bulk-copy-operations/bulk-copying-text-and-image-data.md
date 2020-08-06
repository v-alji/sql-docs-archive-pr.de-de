---
title: Massen Kopieren von Text-und Bilddaten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- bulk copy [ODBC], text data
- SQL Server Native Client ODBC driver, bulk copy
- bulk copy [ODBC], image data
- ODBC, bulk copy operations
ms.assetid: 87155bfa-3a73-4158-9d4d-cb7435dac201
author: rothja
ms.author: jroth
ms.openlocfilehash: 9240fd0eb8c32ed39613824ea5a07764e277160c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622624"
---
# <a name="bulk-copying-text-and-image-data"></a><span data-ttu-id="0e0ee-102">Massenkopieren von Text- und Bilddaten</span><span class="sxs-lookup"><span data-stu-id="0e0ee-102">Bulk Copying Text and Image Data</span></span>
  <span data-ttu-id="0e0ee-103">Große **Text**-, **ntext**-und **Image** -Werte werden mithilfe der [bcp_moretext](../native-client-odbc-extensions-bulk-copy-functions/bcp-moretext.md) -Funktion Massen kopiert.</span><span class="sxs-lookup"><span data-stu-id="0e0ee-103">Large **text**, **ntext**, and **image** values are bulk copied using the [bcp_moretext](../native-client-odbc-extensions-bulk-copy-functions/bcp-moretext.md) function.</span></span> <span data-ttu-id="0e0ee-104">Sie codieren [bcp_bind](../native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md) für die **Text**-, **ntext**-oder **Image** -Spalte, wobei ein *pData* -Zeiger auf NULL festgelegt ist, um anzugeben, dass die Daten **bcp_moretext**bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="0e0ee-104">You code [bcp_bind](../native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md) for the **text**, **ntext**, or **image** column with a *pData* pointer set to NULL indicating the data will be provided with **bcp_moretext**.</span></span> <span data-ttu-id="0e0ee-105">Es ist wichtig, die genaue Länge der Daten anzugeben, die für jede **Text**-, **ntext**-oder **Image** -Spalte in jeder Massen kopierten Zeile angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="0e0ee-105">It is important to specify the exact length of data supplied for each **text**, **ntext**,or **image** column in each bulk-copied row.</span></span> <span data-ttu-id="0e0ee-106">Wenn sich die Länge der Daten für eine Spalte von der in [bcp_bind](../native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md)angegebenen Spaltenlänge unterscheidet, verwenden Sie [bcp_collen](../native-client-odbc-extensions-bulk-copy-functions/bcp-collen.md) , um die Länge auf den richtigen Wert festzulegen.</span><span class="sxs-lookup"><span data-stu-id="0e0ee-106">If the length of the data for a column is different from the column length specified in [bcp_bind](../native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md), use [bcp_collen](../native-client-odbc-extensions-bulk-copy-functions/bcp-collen.md) to set the length to the proper value.</span></span> <span data-ttu-id="0e0ee-107">Ein [bcp_sendrow](../native-client-odbc-extensions-bulk-copy-functions/bcp-sendrow.md) sendet alle nicht-**Text**-Daten, nicht-**ntext**-Daten und nicht-**Bilddaten** . Anschließend wird **bcp_moretext** aufgerufen, um die **Text**-, **ntext**-oder **Image** -Daten in separaten Einheiten zu senden.</span><span class="sxs-lookup"><span data-stu-id="0e0ee-107">A [bcp_sendrow](../native-client-odbc-extensions-bulk-copy-functions/bcp-sendrow.md) sends all the non-**text**, non-**ntext**, and non-**image** data; you then call **bcp_moretext** to send the **text**, **ntext**, or **image** data in separate units.</span></span> <span data-ttu-id="0e0ee-108">Massen Kopierfunktionen bestimmen, dass alle Daten für die aktuelle **Text**-, **ntext**-oder **Image** -Spalte gesendet wurden, wenn die Summe der Daten Längen, die über **bcp_moretext** gesendet werden, gleich der im letzten **bcp_collen** oder **bcp_bind**angegebenen Länge ist.</span><span class="sxs-lookup"><span data-stu-id="0e0ee-108">Bulk copy functions determine that all data has been sent for the current **text**, **ntext**, or **image** column when the sum of the lengths of data sent through **bcp_moretext** equals the length specified in the latest **bcp_collen** or **bcp_bind**.</span></span>  
  
 <span data-ttu-id="0e0ee-109">**bcp_moretext** hat keinen Parameter, um eine Spalte zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="0e0ee-109">**bcp_moretext** has no parameter to identify a column.</span></span> <span data-ttu-id="0e0ee-110">Wenn mehrere **Text**-, **ntext**-oder **Image** -Spalten in einer Zeile vorhanden sind, werden **bcp_moretext** für die **Text**-, **ntext**-oder **Image** -Spalten gestartet, beginnend mit der Spalte mit der niedrigsten Ordinalzahl und mit der Spalte mit der höchsten Ordinalzahl.</span><span class="sxs-lookup"><span data-stu-id="0e0ee-110">When there are multiple **text**, **ntext**, or **image** columns in a row, **bcp_moretext** operates on the **text**, **ntext**, or **image** columns starting with the column having the lowest ordinal number and proceeding to the column with the highest ordinal number.</span></span> <span data-ttu-id="0e0ee-111">**bcp_moretext** wechselt von einer Spalte zur nächsten, wenn die Summe der gesendeten Daten gleich der im letzten **bcp_collen** oder **bcp_bind** für die aktuelle Spalte angegebenen Länge ist.</span><span class="sxs-lookup"><span data-stu-id="0e0ee-111">**bcp_moretext** goes from one column to the next when the sum of the lengths of data sent equals the length specified in the latest **bcp_collen** or **bcp_bind** for the current column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e0ee-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0e0ee-112">See Also</span></span>  
 [<span data-ttu-id="0e0ee-113">Ausführen von Massen Kopier Vorgängen &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="0e0ee-113">Performing Bulk Copy Operations &#40;ODBC&#41;</span></span>](performing-bulk-copy-operations-odbc.md)  
  
  
