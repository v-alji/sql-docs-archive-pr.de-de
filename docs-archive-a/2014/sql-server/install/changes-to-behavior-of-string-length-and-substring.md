---
title: Änderungen am Verhalten von String-length und Teil Zeichenfolge | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 2119b7ba-2e52-44bf-ac57-82c2d46a48ff
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 1188823a877b4c5dc9cef13431492dfe3b303e23
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617515"
---
# <a name="changes-to-behavior-of-string-length-and-substring"></a><span data-ttu-id="8f023-102">Änderungen am Verhalten von string-length und substring</span><span class="sxs-lookup"><span data-stu-id="8f023-102">Changes to behavior of string-length and substring</span></span>
  <span data-ttu-id="8f023-103">Die [String-length-Funktion &#40;XQuery-&#41;](/sql/xquery/functions-on-string-values-string-length) und die [Teil Zeichenfolge-Funktion &#40;XQuery-&#41;](/sql/xquery/functions-on-string-values-substring) Funktionen können unterschiedliche Ergebnisse zurückgeben, wenn Sie mit XML-Datenbanken mit Ersatz Zeichen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8f023-103">The [string-length Function &#40;XQuery&#41;](/sql/xquery/functions-on-string-values-string-length) and [substring Function &#40;XQuery&#41;](/sql/xquery/functions-on-string-values-substring) functions may return different results when used with XML databases that contain surrogate characters.</span></span>  
  
## <a name="description"></a><span data-ttu-id="8f023-104">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8f023-104">Description</span></span>  
 <span data-ttu-id="8f023-105">Wenn eine Datenbank für die Kompatibilität mit festgelegt ist [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , ändert sich das Verhalten der [String-length-Funktion &#40;XQuery-&#41;](/sql/xquery/functions-on-string-values-string-length) und die [Teil Zeichenfolge-Funktion &#40;XQuery-&#41;](/sql/xquery/functions-on-string-values-substring) Functions beim Umgang mit ergänzenden Unicode-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="8f023-105">When a database is set to be compatible with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], the behavior of the [string-length Function &#40;XQuery&#41;](/sql/xquery/functions-on-string-values-string-length) and [substring Function &#40;XQuery&#41;](/sql/xquery/functions-on-string-values-substring) functions changes when dealing with Unicode supplementary characters.</span></span> <span data-ttu-id="8f023-106">Jedes ergänzende Unicode-Zeichen, das definitionsgemäß um einen Codepunkt größer als U+FFFF ist, wird von diesen Funktionen als ein Zeichen statt als zwei Zeichen (wie in früheren Versionen) gezählt.</span><span class="sxs-lookup"><span data-stu-id="8f023-106">Each Unicode supplementary character, which is defined by having a code point larger than U+FFFF, is counted as one character by these functions rather than two, as it was in previous versions.</span></span>  
  
 <span data-ttu-id="8f023-107">Weitere Informationen zu Ersatz Zeichen finden Sie unter [Surrogates und ergänzende Zeichen](https://go.microsoft.com/fwlink/?LinkId=178317).</span><span class="sxs-lookup"><span data-stu-id="8f023-107">For more information about surrogate characters, see [Surrogates and Supplementary Characters](https://go.microsoft.com/fwlink/?LinkId=178317).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f023-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8f023-108">See Also</span></span>  
 <span data-ttu-id="8f023-109">[Datenbank-Engine Upgradeprobleme](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="8f023-109">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="8f023-110">SQL Server 2014 Upgrade Advisor &#91;neuen&#93;</span><span class="sxs-lookup"><span data-stu-id="8f023-110">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](https://docs.microsoft.com/sql/sql-server/install/sql-server-2014-upgrade-advisor)  
  
  
