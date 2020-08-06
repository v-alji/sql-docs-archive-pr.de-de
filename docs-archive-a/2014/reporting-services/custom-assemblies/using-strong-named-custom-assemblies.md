---
title: Verwenden von benutzerdefinierten Assemblys mit starken Namen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- AllowPartiallyTrustedCallersAttribute attribute
- strong-named custom assemblies [Reporting Services]
- strong names [Reporting Services]
- assemblies [Reporting Services], strong names
- custom assemblies [Reporting Services], strong-named
ms.assetid: ca9f19d7-6e86-46f2-b9ad-9bf807eaa52e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5e685ecda39e0487eb4b469920820fa6e4a10daa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608412"
---
# <a name="using-strong-named-custom-assemblies"></a><span data-ttu-id="e36a3-102">Verwenden von benutzerdefinierten Assemblys mit starken Namen</span><span class="sxs-lookup"><span data-stu-id="e36a3-102">Using Strong-Named Custom Assemblies</span></span>
  <span data-ttu-id="e36a3-103">Ein starker Name identifiziert eine Assembly und enthält den Textnamen der Assembly, die vierteilige Versionsnummer, Kulturinformationen (falls verfügbar), einen öffentlichen Schlüssel und eine digitale Signatur, die im Manifest der Assembly gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="e36a3-103">A strong name identifies an assembly and includes the assembly's text name, four-part version number, culture information (if provided), a public key, and a digital signature stored in the assembly's manifest.</span></span> <span data-ttu-id="e36a3-104">Ein starker Name identifiziert eine Assembly eindeutig für die Common Language Runtime (CLR) und stellt die binäre Integrität sicher.</span><span class="sxs-lookup"><span data-stu-id="e36a3-104">A strong name uniquely identifies an assembly to the common language runtime (CLR) and ensures binary integrity.</span></span>  
  
## <a name="using-allowpartiallytrustedcallersattribute"></a><span data-ttu-id="e36a3-105">Verwenden von AllowPartiallyTrustedCallersAttribute</span><span class="sxs-lookup"><span data-stu-id="e36a3-105">Using AllowPartiallyTrustedCallersAttribute</span></span>  
 <span data-ttu-id="e36a3-106">Um Assemblys mit starken Namen in Berichten verwenden zu können, müssen Sie zulassen, dass die Assembly mit dem starken Namen von zum Teil vertrauenswürdigem Code über das **AllowPartiallyTrustedCallers**-Attribut der Assembly aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="e36a3-106">To use strong-named assemblies with reports, you must allow your strong-named assembly to be called by partially trusted code using the assembly's **AllowPartiallyTrustedCallers** attribute.</span></span> <span data-ttu-id="e36a3-107">Sie können mithilfe von **AllowPartiallyTrustedCallersAttribute** zulassen, dass Assemblys mit starkem Namen vom Berichts-Designer oder dem Berichtsserver in Berichtsausdrücken aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="e36a3-107">You can use **AllowPartiallyTrustedCallersAttribute** to allow strong-named assemblies to be called by Report Designer or the report server in report expressions.</span></span> <span data-ttu-id="e36a3-108">Damit Assemblys mit starkem Namen von teilweise vertrauenswürdigem Code aufgerufen werden dürfen, müssen Sie folgendes Attribut auf Assemblyebene zu Ihrer Assemblyattributdatei hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e36a3-108">To allow partially trusted code to call strong-named assemblies, add the following assembly-level attribute to your assembly attribute file.</span></span>  
  
```vb  
<assembly:AllowPartiallyTrustedCallers>  
```  
  
```csharp  
[assembly:AllowPartiallyTrustedCallers]  
```  
  
 <span data-ttu-id="e36a3-109">**AllowPartiallyTrustedCallersAttribute** ist nur dann wirksam, wenn es von einer Assembly mit starkem Namen auf der Assemblyebene angewandt wird.</span><span class="sxs-lookup"><span data-stu-id="e36a3-109">**AllowPartiallyTrustedCallersAttribute** is effective only when applied by a strong-named assembly at the assembly level.</span></span> <span data-ttu-id="e36a3-110">Weitere Informationen zum Anwenden von Attributen auf Assemblyebene finden Sie unter "Anwenden von Attributen" in der [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="e36a3-110">For more information about applying attributes at the assembly level, see "Applying Attributes" in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK documentation.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="e36a3-111">Wenn **AllowPartiallyTrustedCallersAttribute** vorhanden ist, werden die Standardsicherheitsprüfungen von **FullTrustLinkDemand** verhindert. Dadurch kann die Assembly von einer anderen zum Teil vertrauenswürdigen Assembly aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="e36a3-111">When **AllowPartiallyTrustedCallersAttribute** is present, the default **FullTrustLinkDemand** security checks are prevented, making the assembly callable from any other partially trusted assembly.</span></span> <span data-ttu-id="e36a3-112">Alle Sicherheitsprüfungen, einschließlich der Attribute für die deklarative Sicherheit auf Klassen- oder Methodenebene, müssen explizit angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e36a3-112">All security checks, including class-level or method-level declarative security attributes, must be explicitly stated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e36a3-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e36a3-113">See Also</span></span>  
 [<span data-ttu-id="e36a3-114">Verwenden benutzerdefinierter Assemblys mit Berichten</span><span class="sxs-lookup"><span data-stu-id="e36a3-114">Using Custom Assemblies with Reports</span></span>](using-custom-assemblies-with-reports.md)  
  
  
