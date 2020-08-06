---
title: SqlServiceType-Eigenschaft (SqlService-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SqlServiceType Property (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SqlServiceType property
ms.assetid: dbff2968-3011-41d6-a141-52d814af0213
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 18e0fc741d19eefbb93dbcb7fb6fd4a221ce86d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717623"
---
# <a name="sqlservicetype-property-sqlservice-class"></a><span data-ttu-id="4effe-102">SqlServiceType-Eigenschaft (SqlService-Klasse)</span><span class="sxs-lookup"><span data-stu-id="4effe-102">SqlServiceType Property (SqlService Class)</span></span>
  <span data-ttu-id="4effe-103">Ruft den Typ des verwalteten Diensts ab.</span><span class="sxs-lookup"><span data-stu-id="4effe-103">Gets the type of the managed service.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4effe-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4effe-104">Syntax</span></span>  
  
```  
  
object  
.SqlServiceType [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="4effe-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="4effe-105">Parts</span></span>  
 <span data-ttu-id="4effe-106">*object*</span><span class="sxs-lookup"><span data-stu-id="4effe-106">*object*</span></span>  
 <span data-ttu-id="4effe-107">Ein [SqlService-Klassenobjekt](sqlservice-class.md) , das den Dienst darstellt.</span><span class="sxs-lookup"><span data-stu-id="4effe-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="4effe-108">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4effe-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="4effe-109">Ein uint32-Wert, der den [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Diensttyp angibt.</span><span class="sxs-lookup"><span data-stu-id="4effe-109">A uint32 value that specifies the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4effe-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="4effe-110">Remarks</span></span>  
 <span data-ttu-id="4effe-111">Folgenden Rückgabewerte sind möglich:</span><span class="sxs-lookup"><span data-stu-id="4effe-111">Return values can be one of the following:</span></span>  
  
|<span data-ttu-id="4effe-112">type</span><span class="sxs-lookup"><span data-stu-id="4effe-112">Type</span></span>|<span data-ttu-id="4effe-113">Definition</span><span class="sxs-lookup"><span data-stu-id="4effe-113">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="4effe-114">*1*</span><span class="sxs-lookup"><span data-stu-id="4effe-114">*1*</span></span>|<span data-ttu-id="4effe-115">MSSQLSERVER ist der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Dienst.</span><span class="sxs-lookup"><span data-stu-id="4effe-115">MSSQLSERVER is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="4effe-116">*2*</span><span class="sxs-lookup"><span data-stu-id="4effe-116">*2*</span></span>|<span data-ttu-id="4effe-117">SQLSERVERAGENT ist der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Agent-Dienst.</span><span class="sxs-lookup"><span data-stu-id="4effe-117">SQLSERVERAGENT is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent service.</span></span>|  
|<span data-ttu-id="4effe-118">*3*</span><span class="sxs-lookup"><span data-stu-id="4effe-118">*3*</span></span>|<span data-ttu-id="4effe-119">MSFTESQL ist der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Dienst für die Volltextsuch-Engine.</span><span class="sxs-lookup"><span data-stu-id="4effe-119">MSFTESQL is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Full-text Search Engine service.</span></span>|  
|<span data-ttu-id="4effe-120">*4*</span><span class="sxs-lookup"><span data-stu-id="4effe-120">*4*</span></span>|<span data-ttu-id="4effe-121">MsDtsServer ist der [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] -Dienst.</span><span class="sxs-lookup"><span data-stu-id="4effe-121">MsDtsServer is the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="4effe-122">*5*</span><span class="sxs-lookup"><span data-stu-id="4effe-122">*5*</span></span>|<span data-ttu-id="4effe-123">MSSQLServerOLAPService ist der [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] -Dienst.</span><span class="sxs-lookup"><span data-stu-id="4effe-123">MSSQLServerOLAPService is the [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="4effe-124">*6*</span><span class="sxs-lookup"><span data-stu-id="4effe-124">*6*</span></span>|<span data-ttu-id="4effe-125">ReportServer ist der [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] -Dienst.</span><span class="sxs-lookup"><span data-stu-id="4effe-125">ReportServer is the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="4effe-126">*7*</span><span class="sxs-lookup"><span data-stu-id="4effe-126">*7*</span></span>|<span data-ttu-id="4effe-127">SQLBrowser ist der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Browser-Dienst.</span><span class="sxs-lookup"><span data-stu-id="4effe-127">SQLBrowser is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Browser service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4effe-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4effe-128">See Also</span></span>  
 <span data-ttu-id="4effe-129">[Starten und Beenden von Diensten](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="4effe-129">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
