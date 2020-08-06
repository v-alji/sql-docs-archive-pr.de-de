---
title: Setstrevalue-Methode (SqlServiceAdvancedProperty-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetStrValue Method (SqlServiceAdvancedProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetStrValue method
ms.assetid: 1fededc3-81ba-4b08-83f9-189b96140799
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d977eb9845c820c4128d1d60337151eeb3893eb9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717569"
---
# <a name="setstrvalue-method-sqlserviceadvancedproperty-class"></a><span data-ttu-id="438db-102">SetStrValue-Methode (SqlServiceAdvancedProperty-Klasse)</span><span class="sxs-lookup"><span data-stu-id="438db-102">SetStrValue Method (SqlServiceAdvancedProperty Class)</span></span>
  <span data-ttu-id="438db-103">Legt den Zeichenfolgenwert einer Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="438db-103">Sets the string value of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="438db-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="438db-104">Syntax</span></span>  
  
```  
  
object  
.SetStrValue(  
StrValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="438db-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="438db-105">Parts</span></span>  
 <span data-ttu-id="438db-106">*object*</span><span class="sxs-lookup"><span data-stu-id="438db-106">*object*</span></span>  
 <span data-ttu-id="438db-107">Ein Objekt der [SqlServiceAdvancedProperty-Klasse](sqlserviceadvancedproperty-class.md) , das eine erweiterte Eigenschaft darstellt.</span><span class="sxs-lookup"><span data-stu-id="438db-107">A [SqlServiceAdvancedProperty Class](sqlserviceadvancedproperty-class.md) object that represents an advanced property.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="438db-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="438db-108">Parameters</span></span>  
  
|<span data-ttu-id="438db-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="438db-109">Parameter</span></span>|<span data-ttu-id="438db-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="438db-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="438db-111">*StrValue*</span><span class="sxs-lookup"><span data-stu-id="438db-111">*StrValue*</span></span>|<span data-ttu-id="438db-112">Ein Zeichenfolgenwert, der den Wert der erweiterten Eigenschaft angibt.</span><span class="sxs-lookup"><span data-stu-id="438db-112">A string value that specifies the value of the advanced property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="438db-113">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="438db-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="438db-114">Ein uint32-Wert, der 0 beträgt, wenn der Dienst erfolgreich geändert wurde. Der Wert beträgt 1, wenn die Anforderung nicht unterstützt wird; jede andere Zahl gibt einen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="438db-114">A uint32 value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="438db-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="438db-115">Remarks</span></span>  
 <span data-ttu-id="438db-116">Der Eigenschaftswert muss dem Typ *string* entsprechen, damit die Eigenschaft auf einen Zeichenfolgenwert festgelegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="438db-116">The property value type must be *string* to set the property to a string value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="438db-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="438db-117">See Also</span></span>  
 <span data-ttu-id="438db-118">[Starten und Beenden von Diensten](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="438db-118">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
