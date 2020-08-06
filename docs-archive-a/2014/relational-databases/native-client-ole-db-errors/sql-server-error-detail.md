---
title: SQL Server-Fehlerdetail | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, errors
- errors [OLE DB], error details
- IErrorRecords interface
- IErrorInfo interface
- OLE DB error handling, error details
- ISQLServerErrorInfo interface
ms.assetid: 51500ee3-3d78-47ec-b90f-ebfc55642e06
author: rothja
ms.author: jroth
ms.openlocfilehash: 4c03cf62dd274f9bcca213d33fb8969b26c9d980
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620838"
---
# <a name="sql-server-error-detail"></a><span data-ttu-id="8312e-102">SQL Server-Fehlerdetail</span><span class="sxs-lookup"><span data-stu-id="8312e-102">SQL Server Error Detail</span></span>
  <span data-ttu-id="8312e-103">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter definiert die anbieterspezifische Fehler Schnittstelle [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="8312e-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider defines the provider-specific error interface [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md).</span></span> <span data-ttu-id="8312e-104">Diese Schnittstelle stellt Details zu [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Fehlern bereit und ist daher eine nützliche Informationsquelle, wenn Fehler bei der Ausführung von Befehlen oder Rowsetvorgängen auftreten.</span><span class="sxs-lookup"><span data-stu-id="8312e-104">The interface returns more detail about a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error and is valuable when command execution or rowset operations fail.</span></span>  
  
 <span data-ttu-id="8312e-105">Für den Zugriff auf die **ISQLServerErrorInfo**-Schnittstelle gibt es zwei Möglichkeiten.</span><span class="sxs-lookup"><span data-stu-id="8312e-105">There are two ways to obtain access to **ISQLServerErrorInfo** interface.</span></span>  
  
 <span data-ttu-id="8312e-106">Der Consumer kann **IErrorRecords::GetCustomerErrorObject** aufrufen, um wie im folgenden Codebeispiel gezeigt einen **ISQLServerErrorInfo**-Zeiger zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="8312e-106">The consumer may call **IErrorRecords::GetCustomerErrorObject** to obtain an **ISQLServerErrorInfo** pointer, as shown in the following code sample.</span></span> <span data-ttu-id="8312e-107">(Es ist nicht nötig, **ISQLErrorInfo** abzurufen.) Sowohl **ISQLErrorInfo** als auch **ISQLServerErrorInfo** sind benutzerdefinierte OLE DB-Fehlerobjekte. Dabei ist **ISQLServerErrorInfo** die Schnittstelle zum Abrufen von Informationen zu Serverfehlern, einschließlich Details wie Prozedurname und Zeilennummern.</span><span class="sxs-lookup"><span data-stu-id="8312e-107">(There is no need to obtain **ISQLErrorInfo.**) Both **ISQLErrorInfo** and **ISQLServerErrorInfo** are custom OLE DB error objects, with **ISQLServerErrorInfo** being the interface to use to obtain information of server errors, including such details as procedure name and line numbers.</span></span>  
  
```  
// Get the SQL Server custom error object.  
if(FAILED(hr=pIErrorRecords->GetCustomErrorObject(  
   nRec, IID_ISQLServerErrorInfo,  
   (IUnknown**)&pISQLServerErrorErrorInfo)))  
```  
  
 <span data-ttu-id="8312e-108">Eine andere Möglichkeit, einen **ISQLServerErrorInfo**-Zeiger zu erhalten, besteht im Aufrufen der **QueryInterface**-Methode für einen bereits erhaltenen **ISQLErrorInfo**-Zeiger.</span><span class="sxs-lookup"><span data-stu-id="8312e-108">Another way to get an **ISQLServerErrorInfo** pointer is to call the **QueryInterface** method on an already-obtained **ISQLErrorInfo** pointer.</span></span> <span data-ttu-id="8312e-109">Beachten Sie, dass **ISQLServerErrorInfo** eine Obermenge der Informationen enthält, die durch **ISQLErrorInfo** verfügbar sind. Daher ist es sinnvoll, direkt über **GetCustomerErrorObject** zu **ISQLServerErrorInfo** zu gehen.</span><span class="sxs-lookup"><span data-stu-id="8312e-109">Note that because **ISQLServerErrorInfo** contains a superset of the information available from **ISQLErrorInfo**, it makes sense to go directly to **ISQLServerErrorInfo** through **GetCustomerErrorObject**.</span></span>  
  
 <span data-ttu-id="8312e-110">Die **ISQLServerErrorInfo**-Schnittstelle macht eine Elementfunktion ([ISQLServerErrorInfo::GetErrorInfo](../native-client-ole-db-interfaces/isqlservererrorinfo-geterrorinfo-ole-db.md)) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8312e-110">The **ISQLServerErrorInfo** interface exposes one member function, [ISQLServerErrorInfo::GetErrorInfo](../native-client-ole-db-interfaces/isqlservererrorinfo-geterrorinfo-ole-db.md).</span></span> <span data-ttu-id="8312e-111">Die Funktion gibt einen Zeiger auf eine SSERRORINFO-Struktur und einen Zeiger auf einen Zeichenfolgenpuffer zurück.</span><span class="sxs-lookup"><span data-stu-id="8312e-111">The function returns a pointer to an SSERRORINFO structure and a pointer to a string buffer.</span></span> <span data-ttu-id="8312e-112">Beide Zeiger verweisen auf den Arbeitsspeicher, den der Consumer mithilfe der **IMalloc::Free**-Methode freigeben muss.</span><span class="sxs-lookup"><span data-stu-id="8312e-112">Both pointers reference memory the consumer must deallocate by using the **IMalloc::Free** method.</span></span>  
  
 <span data-ttu-id="8312e-113">SSERRORINFO-Strukturmember werden vom Consumer interpretiert wie folgt.</span><span class="sxs-lookup"><span data-stu-id="8312e-113">SSERRORINFO structure members are interpreted by the consumer as follows.</span></span>  
  
|<span data-ttu-id="8312e-114">Member</span><span class="sxs-lookup"><span data-stu-id="8312e-114">Member</span></span>|<span data-ttu-id="8312e-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8312e-115">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="8312e-116">*pwszMessage*</span><span class="sxs-lookup"><span data-stu-id="8312e-116">*pwszMessage*</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="8312e-117">-Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="8312e-117">error message.</span></span> <span data-ttu-id="8312e-118">Identisch mit der Zeichenfolge, die in **IErrorInfo::GetDescription** zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="8312e-118">Identical to the string returned in **IErrorInfo::GetDescription**.</span></span>|  
|<span data-ttu-id="8312e-119">*pwszServer*</span><span class="sxs-lookup"><span data-stu-id="8312e-119">*pwszServer*</span></span>|<span data-ttu-id="8312e-120">Name der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] für diese Sitzung.</span><span class="sxs-lookup"><span data-stu-id="8312e-120">Name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for the session.</span></span>|  
|<span data-ttu-id="8312e-121">*pwszProcedure*</span><span class="sxs-lookup"><span data-stu-id="8312e-121">*pwszProcedure*</span></span>|<span data-ttu-id="8312e-122">Falls zutreffend, der Name der Prozedur, in der der Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="8312e-122">If appropriate, the name of the procedure in which the error originated.</span></span> <span data-ttu-id="8312e-123">Andernfalls eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="8312e-123">An empty string otherwise.</span></span>|  
|<span data-ttu-id="8312e-124">*lNative*</span><span class="sxs-lookup"><span data-stu-id="8312e-124">*lNative*</span></span>|<span data-ttu-id="8312e-125">Systemeigene [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Fehlernummer.</span><span class="sxs-lookup"><span data-stu-id="8312e-125">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native error number.</span></span> <span data-ttu-id="8312e-126">Identisch mit dem Wert, der im *plNativeError*-Parameter von **ISQLErrorInfo::GetSQLInfo** zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="8312e-126">Identical to the value returned in the *plNativeError* parameter of **ISQLErrorInfo::GetSQLInfo**.</span></span>|  
|<span data-ttu-id="8312e-127">*bState*</span><span class="sxs-lookup"><span data-stu-id="8312e-127">*bState*</span></span>|<span data-ttu-id="8312e-128">Der Status einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="8312e-128">State of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error message.</span></span>|  
|<span data-ttu-id="8312e-129">*bClass*</span><span class="sxs-lookup"><span data-stu-id="8312e-129">*bClass*</span></span>|<span data-ttu-id="8312e-130">Schweregrad einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="8312e-130">Severity of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error message.</span></span>|  
|<span data-ttu-id="8312e-131">*wLineNumber*</span><span class="sxs-lookup"><span data-stu-id="8312e-131">*wLineNumber*</span></span>|<span data-ttu-id="8312e-132">Falls zutreffend, die Zeilennummer einer gespeicherten Prozedur, in der der Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="8312e-132">When applicable, the line number of a stored procedure on which the error occurred.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8312e-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8312e-133">See Also</span></span>  
 <span data-ttu-id="8312e-134">[Mern](errors.md) </span><span class="sxs-lookup"><span data-stu-id="8312e-134">[Errors](errors.md) </span></span>  
 [<span data-ttu-id="8312e-135">RAISERROR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8312e-135">RAISERROR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/raiserror-transact-sql)  
  
  
