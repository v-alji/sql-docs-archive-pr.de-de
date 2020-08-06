---
title: Abhängigkeiten-Eigenschaft (SqlService-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- Dependencies Property (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- Dependencies property
ms.assetid: 92d54b7e-de2f-4978-b601-0196e37cbb41
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: b5b64aee371a41bc0d58ec4a52a1a1526bc13388
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722645"
---
# <a name="dependencies-property-sqlservice-class"></a><span data-ttu-id="0b58b-102">Dependencies-Eigenschaft (SqlService-Klasse)</span><span class="sxs-lookup"><span data-stu-id="0b58b-102">Dependencies Property (SqlService Class)</span></span>
  <span data-ttu-id="0b58b-103">Ruft eine Liste von Diensten ab, die von dem Dienst, auf den verwiesen wird, abhängig sind.</span><span class="sxs-lookup"><span data-stu-id="0b58b-103">Gets a list of services that are dependent on the referenced service.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b58b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0b58b-104">Syntax</span></span>  
  
```  
  
object  
.Dependencies [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="0b58b-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="0b58b-105">Parts</span></span>  
 <span data-ttu-id="0b58b-106">*object*</span><span class="sxs-lookup"><span data-stu-id="0b58b-106">*object*</span></span>  
 <span data-ttu-id="0b58b-107">Ein [SqlService-Klassenobjekt](sqlservice-class.md) , das den Dienst darstellt.</span><span class="sxs-lookup"><span data-stu-id="0b58b-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="0b58b-108">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0b58b-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="0b58b-109">Ein Zeichenfolgenarray, das eine Liste von Diensten enthält, die von dem Dienst, auf den verwiesen wird, abhängig sind.</span><span class="sxs-lookup"><span data-stu-id="0b58b-109">A string[] array that contains a list of services dependent on the referenced service.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0b58b-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="0b58b-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b58b-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0b58b-111">See Also</span></span>  
 <span data-ttu-id="0b58b-112">[Starten und Beenden von Diensten](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="0b58b-112">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
