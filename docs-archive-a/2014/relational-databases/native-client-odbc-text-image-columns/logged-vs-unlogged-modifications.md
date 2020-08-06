---
title: Protokollierte und nicht protokollierte Änderungen | Microsoft-Dokumentation
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
- data types [ODBC], image
- data types [ODBC], text
- logged vs. nonlogged modifications [SQL Server Native Client]
- columns [ODBC]
- ODBC data types, image columns
- nonlogged vs. logged modifications
- ODBC data types, text columns
- image columns [ODBC]
ms.assetid: 20aa5b27-4a2c-46e7-8356-beb0eebf4b7e
author: rothja
ms.author: jroth
ms.openlocfilehash: 8768acc75d18ea2236f0e9280e5d0c805e688107
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725621"
---
# <a name="logged-vs-unlogged-modifications"></a><span data-ttu-id="2f6ed-102">Vergleich von protokollierten und nicht protokollierten Änderungen</span><span class="sxs-lookup"><span data-stu-id="2f6ed-102">Logged vs. Unlogged Modifications</span></span>
  <span data-ttu-id="2f6ed-103">Eine Anwendung kann anfordern, dass der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber keine **Text**-, **ntext**-und **Image** -Änderungen protokolliert.</span><span class="sxs-lookup"><span data-stu-id="2f6ed-103">An application can request that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver not log **text**, **ntext**, and **image** modifications.</span></span> <span data-ttu-id="2f6ed-104">Diese Option sollte jedoch mit Vorsicht eingesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="2f6ed-104">Care should be used with this option, however.</span></span> <span data-ttu-id="2f6ed-105">Er sollte nur für Situationen verwendet werden, in denen die **Text**-, **ntext**-oder **Image** -Daten nicht von entscheidender Bedeutung sind und Daten Besitzer bereit sind, die Fähigkeit zum Wiederherstellen von Daten für eine höhere Leistung abzuwägen.</span><span class="sxs-lookup"><span data-stu-id="2f6ed-105">It should be used only for those situations where the **text**, **ntext**, or **image** data is not critical and data owners are willing to trade off the ability to recover data for higher performance.</span></span>  
  
 <span data-ttu-id="2f6ed-106">Die Protokollierung von **Text**-, **ntext**-und **Image** -Änderungen wird gesteuert, indem [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) aufgerufen wird, wobei der- *Attribut* Parameter auf SQL_SOPT_SS_ TEXTPTR_LOGGING und *ValuePtr* auf SQL_TL_ON oder SQL_TL_OFF festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="2f6ed-106">The logging of **text**, **ntext**, and **image** modifications is controlled by calling [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) with the *Attribute* parameter set to SQL_SOPT_SS_ TEXTPTR_LOGGING and *ValuePtr* set to either SQL_TL_ON or SQL_TL_OFF.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f6ed-107">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2f6ed-107">See Also</span></span>  
 [<span data-ttu-id="2f6ed-108">Verwalten von Text und Imagespalten</span><span class="sxs-lookup"><span data-stu-id="2f6ed-108">Managing Text and Image Columns</span></span>](managing-text-and-image-columns.md)  
  
  
