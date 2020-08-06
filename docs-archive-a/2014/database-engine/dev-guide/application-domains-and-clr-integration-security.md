---
title: Anwendungs Domänen und Sicherheit der CLR-Integration | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- security [CLR integration]
- application domains [CLR integration]
ms.assetid: 54ee904e-e21a-4ee7-b4ad-a6f6f71bd473
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 85d6e66b1d51cc9d7c5829b8e83c510bea750e2a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615548"
---
# <a name="application-domains-and-clr-integration-security"></a><span data-ttu-id="7759a-102">Anwendungsdomänen und Sicherheit der CLR-Integration</span><span class="sxs-lookup"><span data-stu-id="7759a-102">Application Domains and CLR Integration Security</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="7759a-103">lädt Assemblys, die demselben Besitzer gehören, in dieselbe Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="7759a-103">loads assemblies belonging to the same owner in the same application domain.</span></span> <span data-ttu-id="7759a-104">Bei einem Assemblysatz, die in derselben Anwendungsdomäne ausgeführt wird, können sich Assemblys während der Ausführung untereinander erkennen, indem sie den Reflexions-APIs von .NET Framework oder andere Verfahren anwenden, und können sich so auf spät gebundene Weise aufrufen.</span><span class="sxs-lookup"><span data-stu-id="7759a-104">By virtue of a set of assemblies running in the same application domain, assemblies are able to discover each other at execution time using the.NET Framework reflection application programming interfaces or other means, and can call into them in late-bound fashion.</span></span> <span data-ttu-id="7759a-105">Da diese Aufrufe unter Assemblys stattfinden, die denselben Besitzer haben, werden dafür keine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Berechtigungen überprüft.</span><span class="sxs-lookup"><span data-stu-id="7759a-105">Because such calls are occurring against assemblies belonging to the same owner, there are no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] permissions checked for these calls.</span></span> <span data-ttu-id="7759a-106">Das Platzierungsschema von Assemblys in Anwendungsdomänen wurde hauptsächlich mit Blick auf Skalierbarkeit, Sicherheit und Isolierung konzipiert und wird möglicherweise in zukünftigen Versionen geändert.</span><span class="sxs-lookup"><span data-stu-id="7759a-106">The placement scheme of assemblies in application domains is designed primarily to achieve scalability, security, and isolation goals, and can potentially change in future releases.</span></span> <span data-ttu-id="7759a-107">Sie sollten sich daher nicht darauf verlassen, Assemblys mit später Bindung in derselben Anwendungsdomäne zu finden.</span><span class="sxs-lookup"><span data-stu-id="7759a-107">Hence, you should not rely on finding assemblies in the same application domain through late-bound mechanisms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7759a-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7759a-108">See Also</span></span>  
 [<span data-ttu-id="7759a-109">Sicherheit der CLR-Integration</span><span class="sxs-lookup"><span data-stu-id="7759a-109">CLR Integration Security</span></span>](../../relational-databases/clr-integration/security/clr-integration-security.md)  
  
  
