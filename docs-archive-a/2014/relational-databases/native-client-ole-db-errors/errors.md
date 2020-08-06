---
title: Fehler | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, errors
- OLE/COM errors
- errors [OLE DB]
- OLE DB error handling, about error handling
- OLE DB error handling
ms.assetid: bd0612f4-96ef-4919-b0f9-b5447210fe93
author: rothja
ms.author: jroth
ms.openlocfilehash: 0560a31b60a10e278f621aa53f1c7fa038fe8039
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620847"
---
# <a name="errors"></a><span data-ttu-id="58e5b-102">Errors</span><span class="sxs-lookup"><span data-stu-id="58e5b-102">Errors</span></span>
  <span data-ttu-id="58e5b-103">OLE/COM-Objekte melden Fehler durch den HRESULT-Rückgabecode von Objektelementfunktionen.</span><span class="sxs-lookup"><span data-stu-id="58e5b-103">OLE/COM objects report errors through the HRESULT return code of object member functions.</span></span> <span data-ttu-id="58e5b-104">Ein OLE/COM HRESULT ist eine Bitgepackte Struktur.</span><span class="sxs-lookup"><span data-stu-id="58e5b-104">An OLE/COM HRESULT is a bit-packed structure.</span></span> <span data-ttu-id="58e5b-105">OLE stellt Makros bereit, die Strukturmember dereferenzieren.</span><span class="sxs-lookup"><span data-stu-id="58e5b-105">OLE provides macros that dereference structure members.</span></span>  
  
 <span data-ttu-id="58e5b-106">OLE/COM gibt die **IErrorInfo**-Schnittstelle an.</span><span class="sxs-lookup"><span data-stu-id="58e5b-106">OLE/COM specifies the **IErrorInfo** interface.</span></span> <span data-ttu-id="58e5b-107">Die Schnittstelle macht Methoden wie **GetDescription** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="58e5b-107">The interface exposes methods such as **GetDescription**.</span></span> <span data-ttu-id="58e5b-108">Dies ermöglicht es Clients, Fehlerdetails aus OLE/COM-Servern zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="58e5b-108">This allows clients to extract error details from OLE/COM servers.</span></span> <span data-ttu-id="58e5b-109">OLE DB erweitert **IErrorInfo**, um die Rückgabe von mehreren Fehlerinformationspaketen bei der Ausführung einer Einzelmemberfunktion zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="58e5b-109">OLE DB extends **IErrorInfo** to support the return of multiple error information packets on a single-member function execution.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="58e5b-110">kann mehrere Fehler zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="58e5b-110">can return multiple errors.</span></span> <span data-ttu-id="58e5b-111">Eine Anwendung kann Serverfehler einzeln abrufen, indem [IMultipleResults::GetResult](https://go.microsoft.com/fwlink/?LinkId=129630) in Kombination mit ISQLErrorInfo und IErrorRecords aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="58e5b-111">An application can retrieve server errors one at a time by calling [IMultipleResults::GetResult](https://go.microsoft.com/fwlink/?LinkId=129630) combined with ISQLErrorInfo and IErrorRecords.</span></span>  
  
 <span data-ttu-id="58e5b-112">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter macht die OLE DB Daten Satz erweiterten **IErrorInfo**-, benutzerdefinierten `ISQLErrorInfo` und anbieterspezifischen [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) -Fehler Objekt Schnittstellen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="58e5b-112">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the OLE DB record-enhanced **IErrorInfo**, the custom `ISQLErrorInfo`, and the provider-specific [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) error object interfaces.</span></span>  
  
 <span data-ttu-id="58e5b-113">Informationen zur Ablaufverfolgung von Fehlern finden Sie unter [Data Access Tracing (Ablaufverfolgung für den Datenzugriff)](https://go.microsoft.com/fwlink/?LinkId=125805).</span><span class="sxs-lookup"><span data-stu-id="58e5b-113">For information about tracing errors, see [Data Access Tracing](https://go.microsoft.com/fwlink/?LinkId=125805).</span></span> <span data-ttu-id="58e5b-114">Informationen zu Verbesserungen der in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] hinzugefügten Fehlerablaufverfolgung finden Sie unter [Zugreifen auf Diagnoseinformationen im Protokoll der erweiterten Ereignisse](../native-client/features/accessing-diagnostic-information-in-the-extended-events-log.md).</span><span class="sxs-lookup"><span data-stu-id="58e5b-114">For information about enhancements to error tracing added in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], see [Accessing Diagnostic Information in the Extended Events Log](../native-client/features/accessing-diagnostic-information-in-the-extended-events-log.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="58e5b-115">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="58e5b-115">In This Section</span></span>  
  
-   [<span data-ttu-id="58e5b-116">Rückgabecodes</span><span class="sxs-lookup"><span data-stu-id="58e5b-116">Return Codes</span></span>](return-codes.md)  
  
-   [<span data-ttu-id="58e5b-117">Informationen in Fehlerschnittstellen</span><span class="sxs-lookup"><span data-stu-id="58e5b-117">Information in Error Interfaces</span></span>](information-in-error-interfaces.md)  
  
-   [<span data-ttu-id="58e5b-118">SQL Server-Fehlerdetail</span><span class="sxs-lookup"><span data-stu-id="58e5b-118">SQL Server Error Detail</span></span>](sql-server-error-detail.md)  
  
-   [<span data-ttu-id="58e5b-119">Abrufen von Fehlerinformationen</span><span class="sxs-lookup"><span data-stu-id="58e5b-119">Retrieving Error Information</span></span>](retrieving-error-information.md)  
  
-   [<span data-ttu-id="58e5b-120">SQL Server-Meldungsergebnisse</span><span class="sxs-lookup"><span data-stu-id="58e5b-120">SQL Server Message Results</span></span>](sql-server-message-results.md)  
  
## <a name="see-also"></a><span data-ttu-id="58e5b-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="58e5b-121">See Also</span></span>  
 [<span data-ttu-id="58e5b-122">SQL Server Native Client &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="58e5b-122">SQL Server Native Client &#40;OLE DB&#41;</span></span>](../native-client/ole-db/sql-server-native-client-ole-db.md)  
  
  
