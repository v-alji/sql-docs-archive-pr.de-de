---
title: ISQLServerErrorInfo::GetErrorInfo (OLE DB) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- ISQLServerErrorInfo::GetErrorInfo (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- GetErrorInfo method
ms.assetid: 83265c9c-eaf9-41f0-9f73-b0ae0972f0d5
author: rothja
ms.author: jroth
ms.openlocfilehash: c3e325cd99276e04a178b89c19b233289edc09fa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718130"
---
# <a name="isqlservererrorinfogeterrorinfo-ole-db"></a><span data-ttu-id="ea575-102">'ISQLServerErrorInfo::GetErrorInfo' (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="ea575-102">ISQLServerErrorInfo::GetErrorInfo (OLE DB)</span></span>
  <span data-ttu-id="ea575-103">Gibt einen Zeiger auf eine SSERRORINFO-Struktur des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieters zurück, die die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Fehlerdetails enthält.</span><span class="sxs-lookup"><span data-stu-id="ea575-103">Returns a pointer to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider SSERRORINFO structure containing the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error details.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea575-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ea575-104">Syntax</span></span>  
  
```  
  
   HRESULT GetErrorInfo(  
SSERRORINFO**ppSSErrorInfo,  
OLECHAR**ppErrorStrings);  
```  
  
## <a name="arguments"></a><span data-ttu-id="ea575-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="ea575-105">Arguments</span></span>  
 <span data-ttu-id="ea575-106">*ppSSErrorInfo*[out]</span><span class="sxs-lookup"><span data-stu-id="ea575-106">*ppSSErrorInfo*[out]</span></span>  
 <span data-ttu-id="ea575-107">Ein Zeiger auf eine SSERRORINFO-Struktur.</span><span class="sxs-lookup"><span data-stu-id="ea575-107">A pointer to a SSERRORINFO structure.</span></span> <span data-ttu-id="ea575-108">Wenn die Methode fehlschlägt oder dem Fehler keine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Informationen zugeordnet sind, teilt der Anbieter keinen Speicher zu und stellt sicher, dass das *ppSSErrorInfo*-Argument bei der Ausgabe ein NULL-Zeiger ist.</span><span class="sxs-lookup"><span data-stu-id="ea575-108">If the method fails or there is no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] information associated with the error, the provider does not allocate any memory, and ensures that the *ppSSErrorInfo* argument is a null pointer on output.</span></span>  
  
 <span data-ttu-id="ea575-109">*ppErrorStrings*[out]</span><span class="sxs-lookup"><span data-stu-id="ea575-109">*ppErrorStrings*[out]</span></span>  
 <span data-ttu-id="ea575-110">Ein Zeiger auf einen Unicode-Zeichenfolgenzeiger.</span><span class="sxs-lookup"><span data-stu-id="ea575-110">A pointer to a Unicode character-string pointer.</span></span> <span data-ttu-id="ea575-111">Wenn die Methode fehlschlägt oder dem Fehler keine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Informationen zugeordnet sind, teilt der Anbieter keinen Speicher zu und stellt sicher, dass das *ppErrorStrings*-Argument bei der Ausgabe ein NULL-Zeiger ist.</span><span class="sxs-lookup"><span data-stu-id="ea575-111">If the method fails or there is no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] information associated with an error, the provider does not allocate any memory, and ensures that the *ppErrorStrings* argument is a null pointer on output.</span></span> <span data-ttu-id="ea575-112">Durch die Freigabe des *ppErrorStrings* -Arguments mit der **IMalloc::Free** -Methode werden die drei einzelnen Zeichenfolgenelemente der zurückgegebenen SSERRORINFO-Struktur freigegeben, da der Speicher in einem Block zugeteilt wird.</span><span class="sxs-lookup"><span data-stu-id="ea575-112">Freeing the *ppErrorStrings* argument with the **IMalloc::Free** method frees the three individual string members of the returned SSERRORINFO structure, as the memory is allocated in a block.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="ea575-113">Rückgabecodewerte</span><span class="sxs-lookup"><span data-stu-id="ea575-113">Return Code Values</span></span>  
 <span data-ttu-id="ea575-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="ea575-114">S_OK</span></span>  
 <span data-ttu-id="ea575-115">Die Methode wurde erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ea575-115">The method succeeded.</span></span>  
  
 <span data-ttu-id="ea575-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="ea575-116">E_INVALIDARG</span></span>  
 <span data-ttu-id="ea575-117">Entweder das *ppSSErrorInfo* -Argument oder das *ppErrorStrings* -Argument war NULL.</span><span class="sxs-lookup"><span data-stu-id="ea575-117">Either the *ppSSErrorInfo* or the *ppErrorStrings* argument was NULL.</span></span>  
  
 <span data-ttu-id="ea575-118">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="ea575-118">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="ea575-119">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter konnte nicht genügend Arbeitsspeicher zuteilen, um die Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="ea575-119">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider could not allocate sufficient memory to complete the request.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea575-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ea575-120">Remarks</span></span>  
 <span data-ttu-id="ea575-121">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter teilt Arbeitsspeicher für die SSERRORINFO- und die OLECHAR-Zeichenfolgen zu, die durch die Zeiger zurückgegeben werden, die vom Consumer übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="ea575-121">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider allocates memory for the SSERRORINFO and OLECHAR strings returned through the pointers passed by the consumer.</span></span> <span data-ttu-id="ea575-122">Der Consumer muss diesen Arbeitsspeicher mithilfe der **IMalloc::Free** -Methode freigeben, wenn er keinen Zugriff auf die Fehlerdaten mehr benötigt.</span><span class="sxs-lookup"><span data-stu-id="ea575-122">The consumer must deallocate this memory by using the **IMalloc::Free** method when it no longer requires access to the error data.</span></span>  
  
 <span data-ttu-id="ea575-123">Die SSERRORINFO-Struktur ist folgendermaßen definiert:</span><span class="sxs-lookup"><span data-stu-id="ea575-123">The SSERRORINFO structure is defined as follows:</span></span>  
  
```  
typedef struct tagSSErrorInfo  
   {  
   LPOLESTR pwszMessage;  
   LPOLESTR pwszServer;  
   LPOLESTR pwszProcedure;  
   LONG lNative;  
   BYTE bState;  
   BYTE bClass;  
   WORD wLineNumber;  
   }  
SSERRORINFO;  
```  
  
|<span data-ttu-id="ea575-124">Member</span><span class="sxs-lookup"><span data-stu-id="ea575-124">Member</span></span>|<span data-ttu-id="ea575-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ea575-125">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="ea575-126">*pwszMessage*</span><span class="sxs-lookup"><span data-stu-id="ea575-126">*pwszMessage*</span></span>|<span data-ttu-id="ea575-127">Die Fehlermeldung aus [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea575-127">The error message from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ea575-128">Die Meldung wird durch die **IErrorInfo::GetDescription** -Methode zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ea575-128">The message is returned through the **IErrorInfo::GetDescription** method.</span></span>|  
|<span data-ttu-id="ea575-129">*pwszServer*</span><span class="sxs-lookup"><span data-stu-id="ea575-129">*pwszServer*</span></span>|<span data-ttu-id="ea575-130">Der Name der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], auf der der Fehler aufgetreten ist</span><span class="sxs-lookup"><span data-stu-id="ea575-130">The name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on which the error occurred.</span></span>|  
|<span data-ttu-id="ea575-131">*pwszProcedure*</span><span class="sxs-lookup"><span data-stu-id="ea575-131">*pwszProcedure*</span></span>|<span data-ttu-id="ea575-132">Der Name der gespeicherten Prozedur, die den Fehler generiert, wenn der Fehler in einer gespeicherten Prozedur aufgetreten ist; anderenfalls ist es eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="ea575-132">The name of the stored procedure generating the error if the error occurred in a stored procedure; otherwise, an empty string.</span></span>|  
|<span data-ttu-id="ea575-133">*lNative*</span><span class="sxs-lookup"><span data-stu-id="ea575-133">*lNative*</span></span>|<span data-ttu-id="ea575-134">Die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Fehlernummer.</span><span class="sxs-lookup"><span data-stu-id="ea575-134">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error number.</span></span> <span data-ttu-id="ea575-135">Die Fehlernummer ist mit der im *plNativeError* -Parameter der **ISQLErrorInfo::GetSQLInfo** -Methode zurückgegebenen identisch.</span><span class="sxs-lookup"><span data-stu-id="ea575-135">The error number is identical to that returned in the *plNativeError* parameter of the **ISQLErrorInfo::GetSQLInfo** method.</span></span>|  
|<span data-ttu-id="ea575-136">*bState*</span><span class="sxs-lookup"><span data-stu-id="ea575-136">*bState*</span></span>|<span data-ttu-id="ea575-137">Der Zustand des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Fehlers.</span><span class="sxs-lookup"><span data-stu-id="ea575-137">The state of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error.</span></span>|  
|<span data-ttu-id="ea575-138">*bClass*</span><span class="sxs-lookup"><span data-stu-id="ea575-138">*bClass*</span></span>|<span data-ttu-id="ea575-139">Der Schweregrad des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Fehlers.</span><span class="sxs-lookup"><span data-stu-id="ea575-139">The severity of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error.</span></span>|  
|<span data-ttu-id="ea575-140">*wLineNumber*</span><span class="sxs-lookup"><span data-stu-id="ea575-140">*wLineNumber*</span></span>|<span data-ttu-id="ea575-141">Das ist gegebenenfalls die Zeile einer gespeicherten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Prozedur, die die Fehlermeldung generiert hat.</span><span class="sxs-lookup"><span data-stu-id="ea575-141">When applicable, the line of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedure that generated the error message.</span></span> <span data-ttu-id="ea575-142">Wenn keine Prozedur betroffen ist, lautet der Standardwert 1.</span><span class="sxs-lookup"><span data-stu-id="ea575-142">If no procedure is involved, the default value is 1.</span></span>|  
  
 <span data-ttu-id="ea575-143">Zeiger auf die Strukturverweisadressen in der Zeichenfolge, die im *ppErrorStrings* -Argument zurückgegeben wird</span><span class="sxs-lookup"><span data-stu-id="ea575-143">Pointers in the structure reference addresses in the string returned in the *ppErrorStrings* argument.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea575-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ea575-144">See Also</span></span>  
 <span data-ttu-id="ea575-145">[ISQLServerErrorInfo-&#40;OLE DB&#41;](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="ea575-145">[ISQLServerErrorInfo &#40;OLE DB&#41;](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) </span></span>  
 [<span data-ttu-id="ea575-146">RAISERROR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ea575-146">RAISERROR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/raiserror-transact-sql)  
  
  
