---
title: SetNumValue-Methode (SqlServiceAdvancedProperty-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetNumValue Method (SqlServiceAdvancedProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetNumValue method
ms.assetid: a5e1056b-0b75-4ad6-99c1-89246010d815
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 01388855a27dcf14754f677a42c13f8d29cbaacc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717578"
---
# <a name="setnumvalue-method-sqlserviceadvancedproperty-class"></a><span data-ttu-id="e8f13-102">SetNumValue-Methode (SqlServiceAdvancedProperty-Klasse)</span><span class="sxs-lookup"><span data-stu-id="e8f13-102">SetNumValue Method (SqlServiceAdvancedProperty Class)</span></span>
  <span data-ttu-id="e8f13-103">Legt den numerischen Wert einer Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="e8f13-103">Sets the numeric value of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8f13-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e8f13-104">Syntax</span></span>  
  
```  
  
object  
.SetNumValue(  
NumValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="e8f13-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="e8f13-105">Parts</span></span>  
 <span data-ttu-id="e8f13-106">*object*</span><span class="sxs-lookup"><span data-stu-id="e8f13-106">*object*</span></span>  
 <span data-ttu-id="e8f13-107">Ein Objekt der [SqlServiceAdvancedProperty-Klasse](sqlserviceadvancedproperty-class.md) , das eine erweiterte Eigenschaft darstellt.</span><span class="sxs-lookup"><span data-stu-id="e8f13-107">A [SqlServiceAdvancedProperty Class](sqlserviceadvancedproperty-class.md) object that represents an advanced property.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="e8f13-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="e8f13-108">Parameters</span></span>  
  
|<span data-ttu-id="e8f13-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="e8f13-109">Parameter</span></span>|<span data-ttu-id="e8f13-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e8f13-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e8f13-111">*NumValue*</span><span class="sxs-lookup"><span data-stu-id="e8f13-111">*NumValue*</span></span>|<span data-ttu-id="e8f13-112">Ein `uint32`-Wert, der den Wert der erweiterten Eigenschaft angibt.</span><span class="sxs-lookup"><span data-stu-id="e8f13-112">A `uint32` value that specifies the value of the advanced property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="e8f13-113">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e8f13-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="e8f13-114">Ein `uint32`-Wert, der 0 beträgt, wenn der Dienst erfolgreich geändert wurde. Der Wert beträgt 1, wenn die Anforderung nicht unterstützt wird; jede andere Zahl gibt einen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="e8f13-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e8f13-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e8f13-115">Remarks</span></span>  
 <span data-ttu-id="e8f13-116">Der Eigenschaftswert muss numerisch sein, damit die Eigenschaft auf einen numerischen Wert festgelegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="e8f13-116">The property value type must be numeric to be able to set the property to a numeric value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8f13-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e8f13-117">See Also</span></span>  
 <span data-ttu-id="e8f13-118">[Starten und Beenden von Diensten](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="e8f13-118">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
