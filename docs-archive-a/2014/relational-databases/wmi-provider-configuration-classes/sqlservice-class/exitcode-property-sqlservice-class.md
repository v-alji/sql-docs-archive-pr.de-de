---
title: ExitCode-Eigenschaft (SqlService-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- ExitCode Property (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- ExitCode property
ms.assetid: e6b8bff2-946f-4abe-bd50-1f7bb11fdddf
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: f7f5414afd8507a1fc9c592d6b8226692e9683a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615879"
---
# <a name="exitcode-property-sqlservice-class"></a><span data-ttu-id="e2dcf-102">ExitCode-Eigenschaft (SqlService-Klasse)</span><span class="sxs-lookup"><span data-stu-id="e2dcf-102">ExitCode Property (SqlService Class)</span></span>
  <span data-ttu-id="e2dcf-103">Ruft den [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Win32-Fehlercode ab, der beim Starten und Beenden des Diensts aufgetretene Probleme definiert, oder legt diesen fest.</span><span class="sxs-lookup"><span data-stu-id="e2dcf-103">Gets or sets the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Win32 error code that defines problems encountered when starting and stopping the service.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2dcf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e2dcf-104">Syntax</span></span>  
  
```  
  
object  
.ExitCode [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="e2dcf-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="e2dcf-105">Parts</span></span>  
 <span data-ttu-id="e2dcf-106">*object*</span><span class="sxs-lookup"><span data-stu-id="e2dcf-106">*object*</span></span>  
 <span data-ttu-id="e2dcf-107">Ein [SqlService-Klassenobjekt](sqlservice-class.md) , das den Dienst darstellt.</span><span class="sxs-lookup"><span data-stu-id="e2dcf-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="e2dcf-108">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e2dcf-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="e2dcf-109">Ein `uint32`-Wert, der den Exitcode angibt.</span><span class="sxs-lookup"><span data-stu-id="e2dcf-109">A `uint32` value that specifies the exit code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2dcf-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e2dcf-110">Remarks</span></span>  
 <span data-ttu-id="e2dcf-111">Diese Eigenschaft wird auf ERROR_SERVICE_SPECIFIC_ERROR (1066) festgelegt, wenn der Fehler eindeutig in Bezug auf den Dienst ist, der durch diese Klasse dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="e2dcf-111">This property is set to ERROR_SERVICE_SPECIFIC_ERROR (1066) when the error is unique to the service represented by this class.</span></span> <span data-ttu-id="e2dcf-112">Vom Dienst wird dieser Wert bei der Ausführung und erneut bei normaler Beendigung auf NO_ERROR festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e2dcf-112">The service sets this value to NO_ERROR when running, and again upon normal termination.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2dcf-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e2dcf-113">See Also</span></span>  
 <span data-ttu-id="e2dcf-114">[Starten und Beenden von Diensten](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="e2dcf-114">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
