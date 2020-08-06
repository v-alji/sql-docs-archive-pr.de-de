---
title: SetStringValue-Methode (SqlServiceAdvancedProperty-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetStringValue Method (SqlServiceAdvancedProperty Class )
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetStringValue method
ms.assetid: a02d05f6-1072-4709-9ecc-e23e51c8c898
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d7939c6af677ac77b9d8005571406315905bfd65
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717575"
---
# <a name="setstringvalue-method-sqlserviceadvancedproperty-class-"></a><span data-ttu-id="9fe78-102">SetStringValue-Methode (SqlServiceAdvancedProperty-Klasse)</span><span class="sxs-lookup"><span data-stu-id="9fe78-102">SetStringValue Method (SqlServiceAdvancedProperty Class )</span></span>
  <span data-ttu-id="9fe78-103">Legt den Zeichenfolgenwert einer Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="9fe78-103">Sets the string value of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fe78-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9fe78-104">Syntax</span></span>  
  
```  
  
object  
.SetStringValue(  
StrValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="9fe78-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="9fe78-105">Parts</span></span>  
 <span data-ttu-id="9fe78-106">*object*</span><span class="sxs-lookup"><span data-stu-id="9fe78-106">*object*</span></span>  
 <span data-ttu-id="9fe78-107">Ein Objekt der [SqlServiceAdvancedProperty-Klasse](sqlserviceadvancedproperty-class.md) , das eine erweiterte Eigenschaft darstellt.</span><span class="sxs-lookup"><span data-stu-id="9fe78-107">A [SqlServiceAdvancedProperty Class](sqlserviceadvancedproperty-class.md) object that represents an advanced property.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="9fe78-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="9fe78-108">Parameters</span></span>  
  
|<span data-ttu-id="9fe78-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="9fe78-109">Parameter</span></span>|<span data-ttu-id="9fe78-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9fe78-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9fe78-111">*StrValue*</span><span class="sxs-lookup"><span data-stu-id="9fe78-111">*StrValue*</span></span>|<span data-ttu-id="9fe78-112">Ein Zeichenfolgenwert, der den Wert der erweiterten Eigenschaft angibt.</span><span class="sxs-lookup"><span data-stu-id="9fe78-112">A string value that specifies the value of the advanced property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="9fe78-113">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9fe78-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="9fe78-114">Ein `uint32`-Wert, der 0 beträgt, wenn der Dienst erfolgreich geändert wurde. Der Wert beträgt 1, wenn die Anforderung nicht unterstützt wird; jede andere Zahl gibt einen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="9fe78-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9fe78-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="9fe78-115">Remarks</span></span>  
 <span data-ttu-id="9fe78-116">Der Eigenschaftswert muss dem Typ `string` entsprechen, damit die Eigenschaft auf einen Zeichenfolgenwert festgelegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="9fe78-116">The property value type must be `string` to be able to set the property to a string value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fe78-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9fe78-117">See Also</span></span>  
 <span data-ttu-id="9fe78-118">[Starten und Beenden von Diensten](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="9fe78-118">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
