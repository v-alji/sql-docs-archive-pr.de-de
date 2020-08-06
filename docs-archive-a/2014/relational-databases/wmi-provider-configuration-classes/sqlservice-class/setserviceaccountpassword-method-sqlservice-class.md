---
title: SetServiceAccountPassword-Methode (SqlService-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetServiceAccountPassword Method (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetServiceAccountPassword method
ms.assetid: e577a1ac-985c-4799-bb38-9393efc3def2
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: e7a83a6d3686b2ec2df98ae79b4c9d3347f621ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696554"
---
# <a name="setserviceaccountpassword-method-sqlservice-class"></a><span data-ttu-id="173fe-102">SetServiceAccountPassword-Methode (SqlService-Klasse)</span><span class="sxs-lookup"><span data-stu-id="173fe-102">SetServiceAccountPassword Method (SqlService Class)</span></span>
  <span data-ttu-id="173fe-103">Ändert das Kennwort für das Konto, unter dem der referenzierte Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="173fe-103">Modifies the password for the account that the referenced service runs under.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="173fe-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="173fe-104">Syntax</span></span>  
  
```  
  
object  
.SetServiceAccountPassword(  
AccountOldPassword , ServiceStartPassword  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="173fe-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="173fe-105">Parts</span></span>  
 <span data-ttu-id="173fe-106">*object*</span><span class="sxs-lookup"><span data-stu-id="173fe-106">*object*</span></span>  
 <span data-ttu-id="173fe-107">Ein [SqlService-Klassenobjekt](sqlservice-class.md) , das den Dienst darstellt.</span><span class="sxs-lookup"><span data-stu-id="173fe-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="173fe-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="173fe-108">Parameters</span></span>  
 <span data-ttu-id="173fe-109">*Accountoldpassword*</span><span class="sxs-lookup"><span data-stu-id="173fe-109">*AccountOldPassword*</span></span>  
 <span data-ttu-id="173fe-110">Ein Zeichenfolgenwert, der das bestehende Kennwort für das Konto angibt.</span><span class="sxs-lookup"><span data-stu-id="173fe-110">A string value that specifies the existing password for the account.</span></span>  
  
 <span data-ttu-id="173fe-111">*Servicestartpassword*</span><span class="sxs-lookup"><span data-stu-id="173fe-111">*ServiceStartPassword*</span></span>  
 <span data-ttu-id="173fe-112">Ein Zeichenfolgenwert, der das neue Kennwort für das Konto angibt.</span><span class="sxs-lookup"><span data-stu-id="173fe-112">A string value that specifies the new password for the account.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="173fe-113">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="173fe-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="173fe-114">Ein `uint32`-Wert, der 0 beträgt, wenn der Dienst erfolgreich geändert wurde. Der Wert beträgt 1, wenn die Anforderung nicht unterstützt wird; jede andere Zahl gibt einen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="173fe-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="173fe-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="173fe-115">Remarks</span></span>  
  
