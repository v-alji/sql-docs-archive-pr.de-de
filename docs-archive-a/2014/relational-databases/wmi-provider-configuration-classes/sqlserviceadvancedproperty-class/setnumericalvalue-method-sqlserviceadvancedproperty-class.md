---
title: SetNumericalValue-Methode (SqlServiceAdvancedProperty-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetNumericalValue Method (SqlServiceAdvancedProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetNumericalValue method
ms.assetid: 950ed1e8-0538-4db4-807c-a2c36f43cf6b
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: db823938d77f4e2c67284cae0f11faca12aba6d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722618"
---
# <a name="setnumericalvalue-method-sqlserviceadvancedproperty-class"></a><span data-ttu-id="eb9b5-102">SetNumericalValue-Methode (SqlServiceAdvancedProperty-Klasse)</span><span class="sxs-lookup"><span data-stu-id="eb9b5-102">SetNumericalValue Method (SqlServiceAdvancedProperty Class)</span></span>
  <span data-ttu-id="eb9b5-103">Legt den numerischen Wert einer Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="eb9b5-103">Sets the numeric value of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb9b5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="eb9b5-104">Syntax</span></span>  
  
```  
  
object  
.SetNumericalValue(  
NumValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="eb9b5-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="eb9b5-105">Parts</span></span>  
 <span data-ttu-id="eb9b5-106">*object*</span><span class="sxs-lookup"><span data-stu-id="eb9b5-106">*object*</span></span>  
 <span data-ttu-id="eb9b5-107">Ein Objekt der [SqlServiceAdvancedProperty-Klasse](sqlserviceadvancedproperty-class.md) , das eine erweiterte Eigenschaft darstellt.</span><span class="sxs-lookup"><span data-stu-id="eb9b5-107">A [SqlServiceAdvancedProperty Class](sqlserviceadvancedproperty-class.md) object that represents an advanced property.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="eb9b5-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="eb9b5-108">Parameters</span></span>  
  
|<span data-ttu-id="eb9b5-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="eb9b5-109">Parameter</span></span>|<span data-ttu-id="eb9b5-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="eb9b5-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="eb9b5-111">*NumValue*</span><span class="sxs-lookup"><span data-stu-id="eb9b5-111">*NumValue*</span></span>|<span data-ttu-id="eb9b5-112">Ein `uint32`-Wert, der den Wert der erweiterten Eigenschaft angibt.</span><span class="sxs-lookup"><span data-stu-id="eb9b5-112">A `uint32` value that specifies the value of the advanced property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="eb9b5-113">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="eb9b5-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="eb9b5-114">Ein `uint32`-Wert, der 0 beträgt, wenn der Dienst erfolgreich geändert wurde. Der Wert beträgt 1, wenn die Anforderung nicht unterstützt wird; jede andere Zahl gibt einen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="eb9b5-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eb9b5-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="eb9b5-115">Remarks</span></span>  
 <span data-ttu-id="eb9b5-116">Der Eigenschaftswert muss numerisch sein, damit die Eigenschaft auf einen numerischen Wert festgelegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="eb9b5-116">The property value type must be numeric to be able to set the property to a numeric value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb9b5-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eb9b5-117">See Also</span></span>  
 <span data-ttu-id="eb9b5-118">[Starten und Beenden von Diensten](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="eb9b5-118">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
