---
title: DisplayName-Eigenschaft (SqlService-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- DisplayName Property (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- DisplayName property
ms.assetid: 49c408aa-6eb4-45cd-8d5c-60f065f24f5c
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 147fc298d6d263caf1e4ad6852d4b02f86911572
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722637"
---
# <a name="displayname-property-sqlservice-class"></a><span data-ttu-id="1a358-102">DisplayName-Eigenschaft (SqlService-Klasse)</span><span class="sxs-lookup"><span data-stu-id="1a358-102">DisplayName Property (SqlService Class)</span></span>
  <span data-ttu-id="1a358-103">Ruft den Anzeigenamen des Dienstes ab.</span><span class="sxs-lookup"><span data-stu-id="1a358-103">Gets the display name of the service.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a358-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1a358-104">Syntax</span></span>  
  
```  
  
object  
.DisplayName [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="1a358-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="1a358-105">Parts</span></span>  
 <span data-ttu-id="1a358-106">*object*</span><span class="sxs-lookup"><span data-stu-id="1a358-106">*object*</span></span>  
 <span data-ttu-id="1a358-107">Ein [SqlService-Klassenobjekt](sqlservice-class.md) , das den Dienst darstellt.</span><span class="sxs-lookup"><span data-stu-id="1a358-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="1a358-108">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1a358-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="1a358-109">Ein Zeichenfolgenwert, der den Anzeigenamen des Diensts angibt.</span><span class="sxs-lookup"><span data-stu-id="1a358-109">A string value that specifies the display name of the service.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1a358-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="1a358-110">Remarks</span></span>  
 <span data-ttu-id="1a358-111">Die maximale Länge der Zeichenfolge beträgt 256 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="1a358-111">This string has a maximum length of 256 characters.</span></span> <span data-ttu-id="1a358-112">Die Schreibweise des Namens wird im [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Konfigurations-Manager beibehalten.</span><span class="sxs-lookup"><span data-stu-id="1a358-112">The name is case-preserved in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="1a358-113">Jedoch wird bei Vergleichen des Anzeigenamens immer nach Groß- und Kleinschreibung unterschieden.</span><span class="sxs-lookup"><span data-stu-id="1a358-113">However, display name comparisons are always case-insensitive.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a358-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1a358-114">Example</span></span>  
  
```  
mysqlservice.DisplayName = "Atdisk"  
```  
  
## <a name="see-also"></a><span data-ttu-id="1a358-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1a358-115">See Also</span></span>  
 <span data-ttu-id="1a358-116">[Starten und Beenden von Diensten](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="1a358-116">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
