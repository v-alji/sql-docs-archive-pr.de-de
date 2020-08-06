---
title: SetBoolValue-Methode (SqlServiceAdvancedProperty-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- SetBoolValue Method (SqlServiceAdvancedProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetBoolValue method
ms.assetid: 5252b439-fce5-446a-8e57-99e3054bee69
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f0c7142d6f192e94e9850b3c1a8a9481dc15a222
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697649"
---
# <a name="setboolvalue-method-sqlserviceadvancedproperty-class"></a><span data-ttu-id="7850c-102">SetBoolValue-Methode (SqlServiceAdvancedProperty-Klasse)</span><span class="sxs-lookup"><span data-stu-id="7850c-102">SetBoolValue Method (SqlServiceAdvancedProperty Class)</span></span>
  <span data-ttu-id="7850c-103">Legt den booleschen Wert einer Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="7850c-103">Sets the Boolean value of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7850c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7850c-104">Syntax</span></span>  
  
```  
  
object  
.SetBoolValue [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="7850c-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="7850c-105">Parts</span></span>  
 <span data-ttu-id="7850c-106">*object*</span><span class="sxs-lookup"><span data-stu-id="7850c-106">*object*</span></span>  
 <span data-ttu-id="7850c-107">Ein Objekt der [SqlServiceAdvancedProperty-Klasse](../wmi-provider-configuration-classes/sqlserviceadvancedproperty-class/sqlserviceadvancedproperty-class.md) , das eine erweiterte Eigenschaft darstellt.</span><span class="sxs-lookup"><span data-stu-id="7850c-107">A [SqlServiceAdvancedProperty Class](../wmi-provider-configuration-classes/sqlserviceadvancedproperty-class/sqlserviceadvancedproperty-class.md) object that represents an advanced property.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="7850c-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="7850c-108">Parameters</span></span>  
  
|<span data-ttu-id="7850c-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="7850c-109">Parameter</span></span>|<span data-ttu-id="7850c-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7850c-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7850c-111">*Booleer Wert*</span><span class="sxs-lookup"><span data-stu-id="7850c-111">*BoolValue*</span></span>|<span data-ttu-id="7850c-112">Ein boleescher Wert, der den Wert der erweiterten Eigenschaft angibt.</span><span class="sxs-lookup"><span data-stu-id="7850c-112">A Boolean value that specifies the value of the advanced property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="7850c-113">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7850c-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="7850c-114">Ein `uint32`-Wert, der 0 beträgt, wenn der Dienst erfolgreich geändert wurde. Der Wert beträgt 1, wenn die Anforderung nicht unterstützt wird; jede andere Zahl gibt einen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="7850c-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7850c-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="7850c-115">Remarks</span></span>  
 <span data-ttu-id="7850c-116">Der Eingenschaftswert muss ein boolescher Wert sein, damit die Eigenschaft auf einen boleeschen Wert festgelegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="7850c-116">The property value type must be Boolean to set the property to a Boolean value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7850c-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7850c-117">See Also</span></span>  
 <span data-ttu-id="7850c-118">[Starten und Beenden von Diensten](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="7850c-118">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
