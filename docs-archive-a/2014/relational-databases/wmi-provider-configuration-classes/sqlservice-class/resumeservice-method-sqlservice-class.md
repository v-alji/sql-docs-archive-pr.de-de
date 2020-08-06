---
title: ResumeService-Methode (SqlService-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- ResumeService Method (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- ResumeService method
ms.assetid: 0b0a5f08-b95e-4626-bf81-309da7a0aacd
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 53d07c8697c6303bc371f442745e2d1864682e40
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616959"
---
# <a name="resumeservice-method-sqlservice-class"></a><span data-ttu-id="08e6c-102">ResumeService-Methode (SqlService-Klasse)</span><span class="sxs-lookup"><span data-stu-id="08e6c-102">ResumeService Method (SqlService Class)</span></span>
  <span data-ttu-id="08e6c-103">Versucht, den Dienst fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="08e6c-103">Attempts to place the service in the resumed state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08e6c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="08e6c-104">Syntax</span></span>  
  
```  
  
object  
.ResumeService()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="08e6c-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="08e6c-105">Parts</span></span>  
 <span data-ttu-id="08e6c-106">*object*</span><span class="sxs-lookup"><span data-stu-id="08e6c-106">*object*</span></span>  
 <span data-ttu-id="08e6c-107">Ein [SqlService-Klassenobjekt](sqlservice-class.md) , das den Dienst darstellt.</span><span class="sxs-lookup"><span data-stu-id="08e6c-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="08e6c-108">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="08e6c-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="08e6c-109">Ein uint32-Wert, der 0 beträgt, wenn die `ResumeService`-Anforderung angenommen wurde. Der Wert beträgt 1, wenn die Anforderung nicht unterstützt wird; jede andere Zahl gibt einen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="08e6c-109">A uint32 value, which is 0 if the `ResumeService` request was accepted, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08e6c-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="08e6c-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08e6c-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="08e6c-111">See Also</span></span>  
 <span data-ttu-id="08e6c-112">[Starten und Beenden von Diensten](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="08e6c-112">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
