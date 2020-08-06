---
title: Verwalten von Text-und image-Spalten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- text columns [ODBC]
- SQL Server Native Client ODBC driver, image columns
- SQL Server Native Client ODBC driver, text columns
- data types [ODBC], text
- columns [ODBC]
- ODBC data types, image columns
- data types [ODBC], mapping
- ODBC data types, text columns
- image columns [ODBC]
ms.assetid: 7b543556-ff36-4d35-ac08-de96223d92cd
author: rothja
ms.author: jroth
ms.openlocfilehash: e9d7d5b0f48c68e8ac911f5e274c9afdb8cfe17d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725614"
---
# <a name="managing-text-and-image-columns"></a><span data-ttu-id="961ed-102">Verwalten von Text und Imagespalten</span><span class="sxs-lookup"><span data-stu-id="961ed-102">Managing Text and Image Columns</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="961ed-103">**Text**- **, ntext**-und **Image** -Daten (auch als Long Data bezeichnet) sind Zeichen-oder Binär Zeichenfolgendatentypen, die Datenwerte enthalten können, die für die Spalten **char**, **varchar**, **Binary**oder **varbinary** zu groß sind.</span><span class="sxs-lookup"><span data-stu-id="961ed-103">**text**, **ntext**, and **image** data (also referred to as long data) are character or binary string data types that can hold data values too large to fit into **char**, **varchar**, **binary**, or **varbinary** columns.</span></span> <span data-ttu-id="961ed-104">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **Text** Datentyp wird dem ODBC-SQL_LONGVARCHAR-Datentyp zugeordnet. **ntext** wird SQL_WLONGVARCHAR zugeordnet. und **Image** wird SQL_LONGVARBINARY zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="961ed-104">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **text** data type maps to the ODBC SQL_LONGVARCHAR data type; **ntext** maps to SQL_WLONGVARCHAR; and **image** maps to SQL_LONGVARBINARY.</span></span> <span data-ttu-id="961ed-105">Einige Datenelemente, wie z. B. lange Dokumente oder große Bitmaps, sind möglicherweise zu groß, um im Speicher gespeichert zu werden.</span><span class="sxs-lookup"><span data-stu-id="961ed-105">Some data items, such as long documents or large bitmaps, may be too large to store reasonably in memory.</span></span> <span data-ttu-id="961ed-106">Zum Abrufen von Long-Daten aus [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sequenziellen Teilen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ermöglicht der Native Client ODBC-Treiber einer Anwendung das Aufrufen von [SQLGetData](../native-client-odbc-api/sqlgetdata.md).</span><span class="sxs-lookup"><span data-stu-id="961ed-106">To retrieve long data from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in sequential parts, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver enables an application to call [SQLGetData](../native-client-odbc-api/sqlgetdata.md).</span></span> <span data-ttu-id="961ed-107">Um lange Daten in sequenziellen Teilen zu senden, kann die Anwendung [SQLPutData](../native-client-odbc-api/sqlputdata.md)abrufen.</span><span class="sxs-lookup"><span data-stu-id="961ed-107">To send long data in sequential parts, the application can call [SQLPutData](../native-client-odbc-api/sqlputdata.md).</span></span> <span data-ttu-id="961ed-108">Parameter, für die Daten zur Ausführungszeit gesendet werden, werden als Data-at-Execution-Parameter bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="961ed-108">Parameters for which data is sent at execution time are known as data-at-execution parameters.</span></span>  
  
 <span data-ttu-id="961ed-109">Eine Anwendung kann mit **SQLPutData** oder **SQLGetData**tatsächlich beliebige Datentypen (nicht nur mit langen Daten) schreiben oder abrufen, obwohl nur **Zeichen** -und **Binär** Daten in Teilen gesendet oder abgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="961ed-109">An application can actually write or retrieve any type of data (not just long data) with **SQLPutData** or **SQLGetData**, although only **character** and **binary** data can be sent or retrieved in parts.</span></span> <span data-ttu-id="961ed-110">Wenn die Daten jedoch klein genug für einen einzelnen Puffer sind, gibt es im Allgemeinen keinen Grund, **SQLPutData** oder **SQLGetData**zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="961ed-110">However, if the data is small enough to fit in a single buffer, there is generally no reason to use **SQLPutData** or **SQLGetData**.</span></span> <span data-ttu-id="961ed-111">Es ist viel leichter, den einzelnen Puffer an den Parameter oder die Spalte zu binden.</span><span class="sxs-lookup"><span data-stu-id="961ed-111">It is much easier to bind the single buffer to the parameter or column.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="961ed-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="961ed-112">In This Section</span></span>  
  
-   [<span data-ttu-id="961ed-113">Vergleich von gebundenen und ungebundenen Text- und Image-Spalten</span><span class="sxs-lookup"><span data-stu-id="961ed-113">Bound vs. Unbound Text and Image Columns</span></span>](bound-vs-unbound-text-and-image-columns.md)  
  
-   [<span data-ttu-id="961ed-114">Vergleich von protokollierten und nicht protokollierten Änderungen</span><span class="sxs-lookup"><span data-stu-id="961ed-114">Logged vs. Unlogged Modifications</span></span>](logged-vs-unlogged-modifications.md)  
  
-   [<span data-ttu-id="961ed-115">Data-at-Execution und Text-, ntext- oder Imagespalten</span><span class="sxs-lookup"><span data-stu-id="961ed-115">Data-at-Execution and Text, ntext, or Image Columns</span></span>](data-at-execution-and-text-ntext-or-image-columns.md)  
  
## <a name="see-also"></a><span data-ttu-id="961ed-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="961ed-116">See Also</span></span>  
 [<span data-ttu-id="961ed-117">SQL Server Native Client &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="961ed-117">SQL Server Native Client &#40;ODBC&#41;</span></span>](../native-client/odbc/sql-server-native-client-odbc.md)  
  
  
