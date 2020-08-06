---
title: SQLNativeSql | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLNativeSql function
ms.assetid: 2d999fec-9e22-4514-ad5f-22a64b82f95b
author: rothja
ms.author: jroth
ms.openlocfilehash: 433b086dc36a79cb82868edebac9f0a4814c21fe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622064"
---
# <a name="sqlnativesql"></a><span data-ttu-id="d1de4-102">SQLNativeSql</span><span class="sxs-lookup"><span data-stu-id="d1de4-102">SQLNativeSql</span></span>
  <span data-ttu-id="d1de4-103">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber erfüllt **SQLNativeSql** -Anforderungen, ohne auf den Server zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="d1de4-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver satisfies **SQLNativeSql** requests without visiting the server.</span></span> <span data-ttu-id="d1de4-104">Die Funktion testet die Syntax von SQL-Anweisungen effizient.</span><span class="sxs-lookup"><span data-stu-id="d1de4-104">The function efficiently tests the syntax of SQL statements.</span></span> <span data-ttu-id="d1de4-105">Durch die Syntaxüberprüfung wird nicht bestimmt, ob Bezeichner oder die Ergebnisse von Ausdrücken in den SQL-Anweisungen gültig sind, und systemeigene [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] SQL-Anweisungen, die von **SQLNativeSql** zurückgegeben werden, können möglicherweise nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d1de4-105">Syntax checking does not determine if identifiers or the results of expressions in the SQL statements are valid, and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native SQL returned by **SQLNativeSql** can fail to run.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1de4-106">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d1de4-106">See Also</span></span>  
 <span data-ttu-id="d1de4-107">[SQLNativeSql-Funktion](https://go.microsoft.com/fwlink/?LinkID=59358) </span><span class="sxs-lookup"><span data-stu-id="d1de4-107">[SQLNativeSql Function](https://go.microsoft.com/fwlink/?LinkID=59358) </span></span>  
 [<span data-ttu-id="d1de4-108">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="d1de4-108">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
