---
title: SQL Server-Meldungsergebnisse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, errors
- errors [OLE DB], SQL Server message results
- OLE DB error handling, SQL Server message results
ms.assetid: 6663c6f9-def1-4d9e-845b-2085e5efc401
author: rothja
ms.author: jroth
ms.openlocfilehash: aa63445b81ec89b87523fa29c50817e128d48515
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620837"
---
# <a name="sql-server-message-results"></a><span data-ttu-id="683a0-102">SQL Server-Meldungsergebnisse</span><span class="sxs-lookup"><span data-stu-id="683a0-102">SQL Server Message Results</span></span>
  <span data-ttu-id="683a0-103">Die folgenden- [!INCLUDE[tsql](../../includes/tsql-md.md)] Anweisungen generieren keine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-anbietedatasets oder die Anzahl betroffener Zeilen, wenn Sie ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="683a0-103">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements do not generate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider rowsets or a count of affected rows when executed:</span></span>  
  
-   <span data-ttu-id="683a0-104">PRINT</span><span class="sxs-lookup"><span data-stu-id="683a0-104">PRINT</span></span>  
  
-   <span data-ttu-id="683a0-105">RAISERROR mit einem Schweregrad von 10 oder niedriger</span><span class="sxs-lookup"><span data-stu-id="683a0-105">RAISERROR with a severity of 10 or lower</span></span>  
  
-   <span data-ttu-id="683a0-106">DBCC</span><span class="sxs-lookup"><span data-stu-id="683a0-106">DBCC</span></span>  
  
-   <span data-ttu-id="683a0-107">SET SHOWPLAN</span><span class="sxs-lookup"><span data-stu-id="683a0-107">SET SHOWPLAN</span></span>  
  
-   <span data-ttu-id="683a0-108">SET STATISTICS</span><span class="sxs-lookup"><span data-stu-id="683a0-108">SET STATISTICS</span></span>  
  
 <span data-ttu-id="683a0-109">Diese Anweisungen geben entweder eine oder mehrere Informationsmeldungen zurück oder veranlassen, dass [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Informationsmeldungen anstelle von Rowset- oder Anzahlergebnissen zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="683a0-109">These statements either return one or more informational messages or cause [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to return informational messages in place of rowset or count results.</span></span> <span data-ttu-id="683a0-110">Bei erfolgreicher Ausführung gibt der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-OLE DB Anbieter S_OK zurück, und die Nachrichten sind für den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Consumer des Native Client-OLE DB Anbieters verfügbar.</span><span class="sxs-lookup"><span data-stu-id="683a0-110">On successful execution, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns S_OK, and the messages are available to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer.</span></span>  
  
 <span data-ttu-id="683a0-111">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter gibt S_OK zurück und verfügt über eine oder mehrere Informationsmeldungen, die nach der Ausführung vieler- [!INCLUDE[tsql](../../includes/tsql-md.md)] Anweisungen oder der Consumer-Ausführung einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB Provider-Member-Funktion verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="683a0-111">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns S_OK and has one or more informational messages available following the execution of many [!INCLUDE[tsql](../../includes/tsql-md.md)] statements or the consumer execution of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider member function.</span></span>  
  
 <span data-ttu-id="683a0-112">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Consumer des Native Client OLE DB-Anbieters, der die dynamische Angabe von Abfragetext zulässt, sollte Fehler Schnittstellen nach jeder Ausführung der Element Funktion unabhängig vom Wert des Rückgabecodes, dem vorhanden sein oder Fehlen eines zurückgegebenen **IRowset** -oder **IMultipleResults** -Schnittstellen Verweises oder der Anzahl betroffener Zeilen überprüfen.</span><span class="sxs-lookup"><span data-stu-id="683a0-112">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer allowing dynamic specification of query text should check error interfaces after every member function execution regardless of the value of the return code, the presence or absence of a returned **IRowset** or **IMultipleResults** interface reference, or a count of affected rows.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="683a0-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="683a0-113">See Also</span></span>  
 [<span data-ttu-id="683a0-114">Fehler</span><span class="sxs-lookup"><span data-stu-id="683a0-114">Errors</span></span>](errors.md)  
  
  
