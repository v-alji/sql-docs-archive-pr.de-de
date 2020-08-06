---
title: Gebundene und ungebundene Text-und image-Spalten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- text columns [ODBC]
- SQL Server Native Client ODBC driver, image columns
- SQL Server Native Client ODBC driver, text columns
- data types [ODBC], image
- data types [ODBC], text
- columns [ODBC]
- ODBC data types, image columns
- ODBC data types, text columns
- image columns [ODBC]
ms.assetid: ffd3442e-d880-46e9-b848-2365a09a2406
author: rothja
ms.author: jroth
ms.openlocfilehash: 20a91d26ac8c2d1201386cb19bde13b49a3dbada
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725629"
---
# <a name="bound-vs-unbound-text-and-image-columns"></a><span data-ttu-id="1d021-102">Vergleich von gebundenen und ungebundenen Text- und Image-Spalten</span><span class="sxs-lookup"><span data-stu-id="1d021-102">Bound vs. Unbound Text and Image Columns</span></span>
  <span data-ttu-id="1d021-103">Bei der Verwendung von Server Cursorn [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] wird der Native Client-ODBC-Treiber so optimiert, dass die Daten für ungebundene **Text**-, **ntext**-oder **Image** -Spalten zum Zeitpunkt der Ausführung von **SQLFetch** nicht übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="1d021-103">When using server cursors, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver is optimized to not transmit the data for unbound **text**, **ntext**, or **image** columns at the time **SQLFetch** is performed.</span></span> <span data-ttu-id="1d021-104">Die **Text**-, **ntext**-oder **Image** -Daten werden erst dann vom Server abgerufen, wenn die Anwendung [SQLGetData](../native-client-odbc-api/sqlgetdata.md) für die Spalte ausgibt.</span><span class="sxs-lookup"><span data-stu-id="1d021-104">The **text**, **ntext**, or **image** data is not actually retrieved from the server until the application issues [SQLGetData](../native-client-odbc-api/sqlgetdata.md) for the column.</span></span>  
  
 <span data-ttu-id="1d021-105">Viele Anwendungen können so geschrieben werden, dass keine Text-, **ntext**-oder **Image** -Daten angezeigt werden, während ein Benutzer einfach einen **Bildlauf**nach oben und unten in einem Cursor durchführt.</span><span class="sxs-lookup"><span data-stu-id="1d021-105">Many applications can be written so that no **text**, **ntext**, or **image** data is displayed while a user is simply scrolling up and down in a cursor.</span></span> <span data-ttu-id="1d021-106">Wenn ein Benutzer eine Zeile auswählt, um weitere Details zu erhalten, kann die Anwendung **SQLGetData** aufrufen, um die **Text**-, **ntext**-oder **Image** -Daten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="1d021-106">When a user selects a row to get more detail, the application can then call **SQLGetData** to retrieve the **text**, **ntext**, or **image** data.</span></span> <span data-ttu-id="1d021-107">Dadurch wird verhindert, dass die **Text**-, **ntext**-oder **Image** -Daten für eine der Zeilen übertragen werden, die der Benutzer nicht ausgewählt hat, und daher kann die Übertragung sehr großer Datenmengen verhindert werden.</span><span class="sxs-lookup"><span data-stu-id="1d021-107">This will prevent transmitting the **text**, **ntext**, or **image** data for any of the rows the user does not select, and can therefore prevent the transmission of very large amounts of data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d021-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1d021-108">See Also</span></span>  
 <span data-ttu-id="1d021-109">[Verwalten von Text-und image-Spalten](managing-text-and-image-columns.md) </span><span class="sxs-lookup"><span data-stu-id="1d021-109">[Managing Text and Image Columns](managing-text-and-image-columns.md) </span></span>  
 [<span data-ttu-id="1d021-110">Cursorverhalten</span><span class="sxs-lookup"><span data-stu-id="1d021-110">Cursor Behaviors</span></span>](../native-client-odbc-cursors/cursor-behaviors.md)  
  
  
