---
title: Verarbeiten der Ergebnisse der gespeicherten Prozedur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC, stored procedures
- SQL Server Native Client ODBC driver, stored procedures
- stored procedures [ODBC], results
ms.assetid: 788ef2a4-17de-4526-960b-46bf29aafc9f
author: rothja
ms.author: jroth
ms.openlocfilehash: 5f37a6d8beff88748fa944293bd67f449d29eff2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725637"
---
# <a name="processing-stored-procedure-results"></a><span data-ttu-id="0fed5-102">Verarbeiten von Ergebnissen gespeicherter Prozeduren</span><span class="sxs-lookup"><span data-stu-id="0fed5-102">Processing Stored Procedure Results</span></span>
  <span data-ttu-id="0fed5-103">Gespeicherte [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Prozeduren verfügen über vier Mechanismen für die Rückgabe von Daten:</span><span class="sxs-lookup"><span data-stu-id="0fed5-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedures have four mechanisms used to return data:</span></span>  
  
-   <span data-ttu-id="0fed5-104">Jede SELECT-Anweisung in der Prozedur generiert ein Resultset.</span><span class="sxs-lookup"><span data-stu-id="0fed5-104">Each SELECT statement in the procedure generates a result set.</span></span>  
  
-   <span data-ttu-id="0fed5-105">Die Prozedur kann Daten über Ausgabeparameter zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="0fed5-105">The procedure can return data through output parameters.</span></span>  
  
-   <span data-ttu-id="0fed5-106">Ein Cursorausgabeparameter kann einen [!INCLUDE[tsql](../../includes/tsql-md.md)]-Servercursor zurück übergeben.</span><span class="sxs-lookup"><span data-stu-id="0fed5-106">A cursor output parameter can pass back a [!INCLUDE[tsql](../../includes/tsql-md.md)] server cursor.</span></span>  
  
-   <span data-ttu-id="0fed5-107">Die Prozedur kann einen ganzzahligen Rückgabecode besitzen.</span><span class="sxs-lookup"><span data-stu-id="0fed5-107">The procedure can have an integer return code.</span></span>  
  
 <span data-ttu-id="0fed5-108">Anwendungen müssen alle diese Ausgaben gespeicherter Prozeduren verarbeiten können.</span><span class="sxs-lookup"><span data-stu-id="0fed5-108">Applications must be able to handle all these outputs from stored procedures.</span></span> <span data-ttu-id="0fed5-109">Die CALL-Anweisung bzw. die EXECUTE-Anweisung sollte Parametermarkierungen für den Rückgabecode und die Ausgabeparameter enthalten.</span><span class="sxs-lookup"><span data-stu-id="0fed5-109">The CALL or EXECUTE statement should include parameter markers for the return code and output parameters.</span></span> <span data-ttu-id="0fed5-110">Verwenden Sie [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) , um alle als Ausgabeparameter zu binden, und der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber überträgt die Ausgabewerte in die gebundenen Variablen.</span><span class="sxs-lookup"><span data-stu-id="0fed5-110">Use [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) to bind them all as output parameters and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver will transfer the output values to the bound variables.</span></span> <span data-ttu-id="0fed5-111">Ausgabeparameter und Rückgabecodes sind die letzten Elemente, die von an den Client zurückgegeben werden [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Sie werden erst an die Anwendung zurückgegeben, wenn [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md) SQL_NO_DATA zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="0fed5-111">Output parameters and return codes are the last items returned to the client by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]; they are not returned to the application until [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md) returns SQL_NO_DATA.</span></span>  
  
 <span data-ttu-id="0fed5-112">ODBC unterstützt das Binden von [!INCLUDE[tsql](../../includes/tsql-md.md)]-Cursorparametern nicht.</span><span class="sxs-lookup"><span data-stu-id="0fed5-112">ODBC does not support binding [!INCLUDE[tsql](../../includes/tsql-md.md)] cursor parameters.</span></span> <span data-ttu-id="0fed5-113">Da alle Ausgabeparameter vor der Ausführung einer Prozedur gebunden werden müssen, können gespeicherte [!INCLUDE[tsql](../../includes/tsql-md.md)]-Prozeduren, die einen Ausgabecursorparameter enthalten, nicht von ODBC-Anwendungen aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="0fed5-113">Because all output parameters must be bound before executing a procedure, any [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure that contains an output cursor parameter cannot be called by ODBC applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fed5-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0fed5-114">See Also</span></span>  
 [<span data-ttu-id="0fed5-115">Ausführen gespeicherter Prozeduren</span><span class="sxs-lookup"><span data-stu-id="0fed5-115">Running Stored Procedures</span></span>](running-stored-procedures.md)  
  
  
