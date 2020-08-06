---
title: Unzulässige Typen und Member in System.Data.dll | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- host protection attributes [CLR integration]
- common language runtime [SQL Server], host protection attributes
ms.assetid: ee5f55e9-fbef-401a-be18-a2e5873c8720
author: rothja
ms.author: jroth
ms.openlocfilehash: cd62f6f0a90bd167f20a33f8de749acc982f39b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616105"
---
# <a name="disallowed-types-and-members-in-systemdatadll"></a><span data-ttu-id="f2212-102">Unzulässige Typen und Elemente in "System.Data.dll"</span><span class="sxs-lookup"><span data-stu-id="f2212-102">Disallowed Types and Members in System.Data.dll</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="f2212-103">die CLR-Programmierung (Common Language Integration) lässt die Verwendung eines Typs oder Members mit einem nicht zu, das eine- `HostProtectionAttribute` `System.Security.Permissions.HostProtectionResource` Enumeration mit dem Wert, `ExternalProcessMgmt` `ExternalThreading` , `MayLeakOnAbort` , `SecurityInfrastructure` , `SelfAffectingProcessMgmnt` , `SelfAffectingThreading` , **SharedState**, `Synchronization` oder angibt `UI` .</span><span class="sxs-lookup"><span data-stu-id="f2212-103">common language integration (CLR) programming disallows the use of a type or member that has a `HostProtectionAttribute` that specifies a `System.Security.Permissions.HostProtectionResource` enumeration with a value of `ExternalProcessMgmt`, `ExternalThreading`, `MayLeakOnAbort`, `SecurityInfrastructure`, `SelfAffectingProcessMgmnt`, `SelfAffectingThreading`, **SharedState**, `Synchronization`, or `UI`.</span></span> <span data-ttu-id="f2212-104">In der folgenden Tabelle sind die Elemente und Typen der System.Data.dll-Assembly aufgeführt, deren Hostschutzattributwerte nicht zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="f2212-104">The following table lists the members and types of the System.Data.dll assembly whose Host Protection Attribute (HPA) values are disallowed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f2212-105">Diese Liste wurde von den unterstützten Assemblys generiert.</span><span class="sxs-lookup"><span data-stu-id="f2212-105">This list was generated from the supported assemblies.</span></span> <span data-ttu-id="f2212-106">Weitere Informationen finden Sie [unter Supported .NET Framework Libraries](../clr-integration/database-objects/supported-net-framework-libraries.md).</span><span class="sxs-lookup"><span data-stu-id="f2212-106">For more information, see [Supported .NET Framework Libraries](../clr-integration/database-objects/supported-net-framework-libraries.md).</span></span>  
  
|<span data-ttu-id="f2212-107">Typ oder Element</span><span class="sxs-lookup"><span data-stu-id="f2212-107">Type or Member</span></span>|<span data-ttu-id="f2212-108">Hostschutzattribut-Wert(e)</span><span class="sxs-lookup"><span data-stu-id="f2212-108">HPA Value(s)</span></span>|  
|--------------------|--------------------|  
|<span data-ttu-id="f2212-109">System.Data.SqlClient.SqlCommand.BeginExecuteNonQuery()</span><span class="sxs-lookup"><span data-stu-id="f2212-109">System.Data.SqlClient.SqlCommand.BeginExecuteNonQuery()</span></span>|<span data-ttu-id="f2212-110">ExternalThreading</span><span class="sxs-lookup"><span data-stu-id="f2212-110">ExternalThreading</span></span>|  
|<span data-ttu-id="f2212-111">System.Data.SqlClient.SqlCommand.BeginExecuteReader()</span><span class="sxs-lookup"><span data-stu-id="f2212-111">System.Data.SqlClient.SqlCommand.BeginExecuteReader()</span></span>|<span data-ttu-id="f2212-112">ExternalThreading</span><span class="sxs-lookup"><span data-stu-id="f2212-112">ExternalThreading</span></span>|  
|<span data-ttu-id="f2212-113">System.Data.SqlClient.SqlCommand.BeginExecuteXmlReader()</span><span class="sxs-lookup"><span data-stu-id="f2212-113">System.Data.SqlClient.SqlCommand.BeginExecuteXmlReader()</span></span>|<span data-ttu-id="f2212-114">ExternalThreading</span><span class="sxs-lookup"><span data-stu-id="f2212-114">ExternalThreading</span></span>|  
|<span data-ttu-id="f2212-115">System.Data.SqlClient.SqlDependency..ctor()</span><span class="sxs-lookup"><span data-stu-id="f2212-115">System.Data.SqlClient.SqlDependency..ctor()</span></span>|<span data-ttu-id="f2212-116">ExternalThreading</span><span class="sxs-lookup"><span data-stu-id="f2212-116">ExternalThreading</span></span>|  
|<span data-ttu-id="f2212-117">System.Data.SqlClient.SqlDependency.Start()</span><span class="sxs-lookup"><span data-stu-id="f2212-117">System.Data.SqlClient.SqlDependency.Start()</span></span>|<span data-ttu-id="f2212-118">ExternalThreading</span><span class="sxs-lookup"><span data-stu-id="f2212-118">ExternalThreading</span></span>|  
|<span data-ttu-id="f2212-119">System.Data.SqlClient.SqlDependency.Stop()</span><span class="sxs-lookup"><span data-stu-id="f2212-119">System.Data.SqlClient.SqlDependency.Stop()</span></span>|<span data-ttu-id="f2212-120">ExternalThreading</span><span class="sxs-lookup"><span data-stu-id="f2212-120">ExternalThreading</span></span>|  
|<span data-ttu-id="f2212-121">System.Data.TypedDataSetGenerator</span><span class="sxs-lookup"><span data-stu-id="f2212-121">System.Data.TypedDataSetGenerator</span></span>|<span data-ttu-id="f2212-122">SharedState, Synchronization</span><span class="sxs-lookup"><span data-stu-id="f2212-122">SharedState, Synchronization</span></span>|  
|<span data-ttu-id="f2212-123">System.Xml.XmlDataDocument</span><span class="sxs-lookup"><span data-stu-id="f2212-123">System.Xml.XmlDataDocument</span></span>|<span data-ttu-id="f2212-124">Synchronization</span><span class="sxs-lookup"><span data-stu-id="f2212-124">Synchronization</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f2212-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f2212-125">See Also</span></span>  
 <span data-ttu-id="f2212-126">[Host Schutz Attribute und Programmierung der CLR-Integration](host-protection-attributes-and-clr-integration-programming.md) </span><span class="sxs-lookup"><span data-stu-id="f2212-126">[Host Protection Attributes and CLR Integration Programming](host-protection-attributes-and-clr-integration-programming.md) </span></span>  
 <span data-ttu-id="f2212-127">[Unzulässige Typen und Member in Microsoft.VisualBasic.dll](disallowed-types-and-members-in-microsoft-visualbasic-dll.md) </span><span class="sxs-lookup"><span data-stu-id="f2212-127">[Disallowed Types and Members in Microsoft.VisualBasic.dll](disallowed-types-and-members-in-microsoft-visualbasic-dll.md) </span></span>  
 <span data-ttu-id="f2212-128">[Unzulässige Typen und Member in mscorlib.dll](disallowed-types-and-members-in-mscorlib-dll.md) </span><span class="sxs-lookup"><span data-stu-id="f2212-128">[Disallowed Types and Members in mscorlib.dll](disallowed-types-and-members-in-mscorlib-dll.md) </span></span>  
 <span data-ttu-id="f2212-129">[Unzulässige Typen und Member in System.dll](disallowed-types-and-members-in-system-dll.md) </span><span class="sxs-lookup"><span data-stu-id="f2212-129">[Disallowed Types and Members in System.dll](disallowed-types-and-members-in-system-dll.md) </span></span>  
 [<span data-ttu-id="f2212-130">Unzulässige Typen und Elemente in 'System.Core.dll'</span><span class="sxs-lookup"><span data-stu-id="f2212-130">Disallowed Types and Members in System.Core.dll</span></span>](disallowed-types-and-members-in-system-core-dll.md)  
  
  
