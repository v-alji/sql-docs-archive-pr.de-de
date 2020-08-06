---
title: Details zur Cursor Programmierung (ODBC) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, cursors
- ODBC applications, cursors
- ODBC cursors, programming
- cursors [ODBC], programming
ms.assetid: 6bae29c4-7f49-419c-8712-90db734f992e
author: rothja
ms.author: jroth
ms.openlocfilehash: 4108e195c16d321578a70852dd990f4f8d658832
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616061"
---
# <a name="cursor-programming-details-odbc"></a><span data-ttu-id="966b4-102">Details über das Programmieren von Cursorn (ODBC)</span><span class="sxs-lookup"><span data-stu-id="966b4-102">Cursor Programming Details (ODBC)</span></span>
  <span data-ttu-id="966b4-103">Sie können die Anwendungsleistung verbessern, indem Sie den richtigen Cursortyp auswählen.</span><span class="sxs-lookup"><span data-stu-id="966b4-103">Choosing the correct cursor type can improve application performance.</span></span> <span data-ttu-id="966b4-104">Unter bestimmten Bedingungen konvertiert [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] möglicherweise einen Cursortyp implizit, wenn Sie eine SQL-Anweisung ausführen, die nicht von dem von Ihnen ausgewählten Cursortyp unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="966b4-104">Under certain conditions, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] may implicitly convert a cursor type when you execute an SQL statement that is not supported by the cursor type you requested.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="966b4-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="966b4-105">In This Section</span></span>  
  
-   [<span data-ttu-id="966b4-106">Implizite Cursor Konvertierungen &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="966b4-106">Implicit Cursor Conversions &#40;ODBC&#41;</span></span>](implicit-cursor-conversions-odbc.md)  
  
-   [<span data-ttu-id="966b4-107">Verwenden von Autofetch mit ODBC-Cursorn</span><span class="sxs-lookup"><span data-stu-id="966b4-107">Using Autofetch with ODBC Cursors</span></span>](using-autofetch-with-odbc-cursors.md)  
  
-   [<span data-ttu-id="966b4-108">Schnelle Vorwärts Cursor &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="966b4-108">Fast Forward-Only Cursors &#40;ODBC&#41;</span></span>](fast-forward-only-cursors-odbc.md)  
  
## <a name="see-also"></a><span data-ttu-id="966b4-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="966b4-109">See Also</span></span>  
 [<span data-ttu-id="966b4-110">Verwenden von Cursorn &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="966b4-110">Using Cursors &#40;ODBC&#41;</span></span>](../using-cursors-odbc.md)  
  
  