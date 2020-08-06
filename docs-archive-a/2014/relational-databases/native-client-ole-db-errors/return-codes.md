---
title: Rückgabecodes | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB error handling, return codes
- SQL Server Native Client OLE DB provider, errors
- failed function [OLE DB]
- successful function [OLE DB]
- S_FALSE
- IS_ERROR macro
- DB_S_ERRORSOCCURRED return
- return codes [OLE DB]
- S_OK
- FAILED macro
- errors [OLE DB], return codes
ms.assetid: 7f7457e9-fce4-400c-82e5-ee02e9e811c6
author: rothja
ms.author: jroth
ms.openlocfilehash: dd033d16b1e95773d2cab1c4e1fca733dc491b96
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620839"
---
# <a name="return-codes"></a><span data-ttu-id="c6e57-102">Rückgabecodes</span><span class="sxs-lookup"><span data-stu-id="c6e57-102">Return Codes</span></span>
  <span data-ttu-id="c6e57-103">Auf der grundlegenden Ebene wird eine Elementfunktion entweder erfolgreich ausgeführt, oder sie schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="c6e57-103">At the most basic level, a member function either succeeds or fails.</span></span> <span data-ttu-id="c6e57-104">Auf einer genaueren Ebene kann eine Funktion erfolgreich ausgeführt werden, ohne dass das Ergebnis dem entspricht, was vom Anwendungsentwickler beabsichtigt war.</span><span class="sxs-lookup"><span data-stu-id="c6e57-104">At a somewhat more precise level, a function can succeed, but its success may not be what the application developer intended.</span></span>  
  
 <span data-ttu-id="c6e57-105">Weitere Informationen zu OLE DB-Rückgabecodes finden Sie unter [Rückgabecodes (OLE DB)](https://go.microsoft.com/fwlink/?LinkId=101631).</span><span class="sxs-lookup"><span data-stu-id="c6e57-105">For more information about OLE DB return codes, see [Return Codes (OLE DB)](https://go.microsoft.com/fwlink/?LinkId=101631).</span></span>  
  
 <span data-ttu-id="c6e57-106">Wenn [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] die Member-Funktion eines Native Client OLE DB-Anbieters S_OK zurückgibt, wurde die Funktion erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c6e57-106">When a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider member function returns S_OK, the function succeeded.</span></span>  
  
 <span data-ttu-id="c6e57-107">Wenn eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Member des Native Client OLE DB-Anbieters S_OK nicht zurückgibt, kann das OLE/com HRESULT-entpacken fehlschlagen und IS_ERROR Makros den Gesamterfolg oder Misserfolg einer Funktion ermitteln.</span><span class="sxs-lookup"><span data-stu-id="c6e57-107">When a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider member function does not return S_OK, the OLE/COM HRESULT-unpacking FAILED and IS_ERROR macros can determine the overall success or failure of a function.</span></span>  
  
 <span data-ttu-id="c6e57-108">Wenn ein Fehler aufgetreten ist oder IS_ERROR "true" zurückgibt, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ist der Consumer des Native Client OLE DB Anbieters sicher, dass die Ausführung der Element Funktion</span><span class="sxs-lookup"><span data-stu-id="c6e57-108">If FAILED or IS_ERROR returns TRUE, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer is assured that member function execution failed.</span></span> <span data-ttu-id="c6e57-109">Wenn ein Fehler aufgetreten ist oder IS_ERROR false zurückgeben und das HRESULT nicht gleich S_OK ist, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] wird der Consumer des Native Client OLE DB Anbieters sicher sein, dass die Funktion in gewisser Hinsicht erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="c6e57-109">When FAILED or IS_ERROR return FALSE and the HRESULT does not equal S_OK, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer is assured that the function succeeded in some sense.</span></span> <span data-ttu-id="c6e57-110">Der Consumer kann ausführliche Informationen zu diesem "Erfolg mit Informationen" von den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-OLE DB Anbieter-Fehler Schnittstellen abrufen.</span><span class="sxs-lookup"><span data-stu-id="c6e57-110">The consumer can retrieve detailed information on this "success with information" return from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider error interfaces.</span></span> <span data-ttu-id="c6e57-111">Außerdem ist in dem Fall, in dem eine Funktion eindeutig fehlschlägt (das fehlgeschlagene Makro gibt true zurück), erweiterte Fehlerinformationen über die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Fehler Schnittstellen des Native Client OLE DB Anbieters verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c6e57-111">Also, in the case where a function clearly fails (the FAILED macro returns TRUE), extended error information is available from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider error interfaces.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="c6e57-112">Der Consumer des Native Client OLE DB-Anbieters stößt häufig auf die DB_S_ERRORSOCCURRED "Erfolg mit Informationen" HRESULT zurück.</span><span class="sxs-lookup"><span data-stu-id="c6e57-112">Native Client OLE DB provider consumers commonly encounter the DB_S_ERRORSOCCURRED "success with information" HRESULT return.</span></span> <span data-ttu-id="c6e57-113">In der Regel definieren Elementfunktionen, die DB_S_ERRORSOCCURRED zurückgeben, einen oder mehrere Parameter, die Statuswerte an den Consumer übermitteln.</span><span class="sxs-lookup"><span data-stu-id="c6e57-113">Typically, member functions that return DB_S_ERRORSOCCURRED define one or more parameters that deliver status values to the consumer.</span></span> <span data-ttu-id="c6e57-114">Möglicherweise stehen dem Consumer nur die Fehlerinformationen zur Verfügung, die in Statuswertparametern zurückgegeben werden. Daher sollten Consumer Anwendungslogik implementieren, um Statuswerte abzurufen, wenn diese verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="c6e57-114">No error information may be available to the consumer other than that returned in status-value parameters, so consumers should implement application logic to retrieve status values when they are available.</span></span>  
  
 <span data-ttu-id="c6e57-115">Die Element [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Funktionen des Native Client OLE DB-Anbieters geben den Erfolgs Code S_FALSE nicht zurück.</span><span class="sxs-lookup"><span data-stu-id="c6e57-115">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider member functions do not return the success code S_FALSE.</span></span> <span data-ttu-id="c6e57-116">Alle [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Member von Native Client OLE DB-Anbieter Membern geben immer S_OK zurück, um einen Erfolg anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c6e57-116">All [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider member functions always return S_OK to indicate success.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6e57-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c6e57-117">See Also</span></span>  
 [<span data-ttu-id="c6e57-118">Fehler</span><span class="sxs-lookup"><span data-stu-id="c6e57-118">Errors</span></span>](errors.md)  
  
  
