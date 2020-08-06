---
title: SqlServiceType-Eigenschaft (SqlServiceAdvancedProperty-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SqlServiceType Property (SqlServiceAdvancedProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SqlServiceType property
ms.assetid: 20f1663a-9a14-4f14-8c1b-8aa133e272c3
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 774c8599fd21e330fa3228336ab1ed3c73d65c85
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622461"
---
# <a name="sqlservicetype-property-sqlserviceadvancedproperty-class"></a><span data-ttu-id="5228a-102">SqlServiceType-Eigenschaft (SqlServiceAdvancedProperty-Klasse)</span><span class="sxs-lookup"><span data-stu-id="5228a-102">SqlServiceType Property (SqlServiceAdvancedProperty Class)</span></span>
  <span data-ttu-id="5228a-103">Ruft den Typ des verwalteten Diensts ab, der der erweiterten Eigenschaft zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="5228a-103">Gets the type of the managed service associated with the advanced property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5228a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5228a-104">Syntax</span></span>  
  
```  
  
object  
.SetBoolValue(  
NumValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="5228a-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="5228a-105">Parts</span></span>  
 <span data-ttu-id="5228a-106">*object*</span><span class="sxs-lookup"><span data-stu-id="5228a-106">*object*</span></span>  
 <span data-ttu-id="5228a-107">Ein Objekt der [SqlServiceAdvancedProperty-Klasse](sqlserviceadvancedproperty-class.md) , das eine erweiterte Eigenschaft darstellt.</span><span class="sxs-lookup"><span data-stu-id="5228a-107">A [SqlServiceAdvancedProperty Class](sqlserviceadvancedproperty-class.md) object that represents an advanced property.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="5228a-108">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5228a-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="5228a-109">Ein uint32-Wert, der den [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Diensttyp angibt.</span><span class="sxs-lookup"><span data-stu-id="5228a-109">A uint32 value that specifies the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Service type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5228a-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="5228a-110">Remarks</span></span>  
 <span data-ttu-id="5228a-111">Folgenden Rückgabewerte sind möglich:</span><span class="sxs-lookup"><span data-stu-id="5228a-111">Return values can be one of the following:</span></span>  
  
|<span data-ttu-id="5228a-112">type</span><span class="sxs-lookup"><span data-stu-id="5228a-112">Type</span></span>|<span data-ttu-id="5228a-113">Definition</span><span class="sxs-lookup"><span data-stu-id="5228a-113">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="5228a-114">*1*</span><span class="sxs-lookup"><span data-stu-id="5228a-114">*1*</span></span>|<span data-ttu-id="5228a-115">MSSQLSERVER ist der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Dienst.</span><span class="sxs-lookup"><span data-stu-id="5228a-115">MSSQLSERVER is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="5228a-116">*2*</span><span class="sxs-lookup"><span data-stu-id="5228a-116">*2*</span></span>|<span data-ttu-id="5228a-117">SQLSERVERAGENT ist der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Agent-Dienst.</span><span class="sxs-lookup"><span data-stu-id="5228a-117">SQLSERVERAGENT is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent service.</span></span>|  
|<span data-ttu-id="5228a-118">*3*</span><span class="sxs-lookup"><span data-stu-id="5228a-118">*3*</span></span>|<span data-ttu-id="5228a-119">MSFTESQL ist der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Dienst für die Volltextsuch-Engine.</span><span class="sxs-lookup"><span data-stu-id="5228a-119">MSFTESQL is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Full-text Search Engine service.</span></span>|  
|<span data-ttu-id="5228a-120">*4*</span><span class="sxs-lookup"><span data-stu-id="5228a-120">*4*</span></span>|<span data-ttu-id="5228a-121">MsDtsServer ist der [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] -Dienst.</span><span class="sxs-lookup"><span data-stu-id="5228a-121">MsDtsServer is the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="5228a-122">*5*</span><span class="sxs-lookup"><span data-stu-id="5228a-122">*5*</span></span>|<span data-ttu-id="5228a-123">MSSQLServerOLAPService ist der [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] -Dienst.</span><span class="sxs-lookup"><span data-stu-id="5228a-123">MSSQLServerOLAPService is the [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="5228a-124">*6*</span><span class="sxs-lookup"><span data-stu-id="5228a-124">*6*</span></span>|<span data-ttu-id="5228a-125">ReportServer ist der [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] -Dienst.</span><span class="sxs-lookup"><span data-stu-id="5228a-125">ReportServer is the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="5228a-126">*7*</span><span class="sxs-lookup"><span data-stu-id="5228a-126">*7*</span></span>|<span data-ttu-id="5228a-127">SQLBrowser ist der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Browser-Dienst.</span><span class="sxs-lookup"><span data-stu-id="5228a-127">SQLBrowser is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Browser service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5228a-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5228a-128">See Also</span></span>  
 <span data-ttu-id="5228a-129">[Starten und Beenden von Diensten](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="5228a-129">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
