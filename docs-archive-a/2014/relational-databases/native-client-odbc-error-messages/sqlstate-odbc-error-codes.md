---
title: SQLSTATE (ODBC-Fehler Codes) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, errors
- ODBC error handling, cause information
- messages [ODBC], cause information
- SQLSTATEs
- errors [ODBC], cause information
ms.assetid: 84cce528-edb0-473f-a85f-3eb87fbe2cf3
author: rothja
ms.author: jroth
ms.openlocfilehash: ff3ec0a5cdc8f24f34e42849f7c8f6d1d9d41478
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607742"
---
# <a name="sqlstate-odbc-error-codes"></a><span data-ttu-id="1dddd-102">SQLSTATE (ODBC-Fehlercodes)</span><span class="sxs-lookup"><span data-stu-id="1dddd-102">SQLSTATE (ODBC Error Codes)</span></span>
  <span data-ttu-id="1dddd-103">SQLSTATE stellt ausführliche Informationen über die Ursache einer Warnung oder eines Fehlers bereit.</span><span class="sxs-lookup"><span data-stu-id="1dddd-103">SQLSTATE provides detailed information about the cause of a warning or error.</span></span> <span data-ttu-id="1dddd-104">Bei Fehlern, die in der von der Datenquelle erkannten und von zurückgegebenen Datenquelle auftreten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , ordnet der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC-Treiber die zurückgegebene systemeigene Fehlernummer dem entsprechenden SQLSTATE zu.</span><span class="sxs-lookup"><span data-stu-id="1dddd-104">For errors that occur in the data source detected and returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver maps the returned native error number to the appropriate SQLSTATE.</span></span> <span data-ttu-id="1dddd-105">Wenn eine systemeigene Fehlernummer keinen ODBC-Fehlercode aufweist, der zugeordnet werden kann, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gibt der Native Client-ODBC-Treiber SQLSTATE 42000 ("Syntax Fehler oder Zugriffsverletzung") zurück.</span><span class="sxs-lookup"><span data-stu-id="1dddd-105">If a native error number does not have an ODBC error code to map to, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver returns SQLSTATE 42000 ("syntax error or access violation").</span></span> <span data-ttu-id="1dddd-106">Für Fehler, die vom Treiber erkannt werden, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] generiert der Native Client-ODBC-Treiber den entsprechenden SQLSTATE.</span><span class="sxs-lookup"><span data-stu-id="1dddd-106">For errors that are detected by the driver, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver generates the appropriate SQLSTATE.</span></span>  
  
 <span data-ttu-id="1dddd-107">Weitere Informationen über Statusfehlercodes finden Sie unter folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="1dddd-107">For more information about the state error codes, see the following topics:</span></span>  
  
-   [<span data-ttu-id="1dddd-108">Anhang A: ODBC-Fehlercodes</span><span class="sxs-lookup"><span data-stu-id="1dddd-108">Appendix A: ODBC Error Codes</span></span>](https://go.microsoft.com/fwlink/?LinkId=89356)  
  
-   [<span data-ttu-id="1dddd-109">SQLSTATE-Zuordnungen</span><span class="sxs-lookup"><span data-stu-id="1dddd-109">SQLSTATE Mappings</span></span>](https://go.microsoft.com/fwlink/?LinkId=89355)  
  
## <a name="see-also"></a><span data-ttu-id="1dddd-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1dddd-110">See Also</span></span>  
 [<span data-ttu-id="1dddd-111">Behandlung von Fehlern und Meldungen</span><span class="sxs-lookup"><span data-stu-id="1dddd-111">Handling Errors and Messages</span></span>](handling-errors-and-messages.md)  
  
  
