---
title: SMO-Objektmodell | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- object models [SMO]
- SMO [SQL Server], object model
- SQL Server Management Objects, object model
ms.assetid: bd6e59b6-ca46-42c0-adb2-c9d64cf6e00b
author: stevestein
ms.author: sstein
ms.openlocfilehash: c973e381a6cc7de44a0072d012147271eaa609ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695541"
---
# <a name="smo-object-model"></a><span data-ttu-id="91df6-102">SMO-Objektmodell</span><span class="sxs-lookup"><span data-stu-id="91df6-102">SMO Object Model</span></span>
  <span data-ttu-id="91df6-103">Das SMO-Objektmodell besteht aus einer Hierarchie von Objekten.</span><span class="sxs-lookup"><span data-stu-id="91df6-103">The SMO object model is made up of a hierarchy of objects.</span></span> <span data-ttu-id="91df6-104">Das <xref:Microsoft.SqlServer.Management.Smo.Server>-Objekt ist das Objekt oberster Ebene, und alle Instanzklassenobjekte befinden sich unter dem <xref:Microsoft.SqlServer.Management.Smo.Server>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="91df6-104">The <xref:Microsoft.SqlServer.Management.Smo.Server> object is the top level object and all instance class objects reside under the <xref:Microsoft.SqlServer.Management.Smo.Server> object.</span></span>  
  
 <span data-ttu-id="91df6-105">Die <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer>-Klasse ist eine Klasse oberster Ebene mit einer separaten Objekthierarchie.</span><span class="sxs-lookup"><span data-stu-id="91df6-105">The <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> class is a top level class with a separate object hierarchy.</span></span> <span data-ttu-id="91df6-106">Das <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> -Objekt stellt [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Dienste und Netzwerkeinstellungen dar, die über den WMI-Anbieter verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="91df6-106">The <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> object represents [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services and network settings available through the WMI Provider.</span></span>  
  
 <span data-ttu-id="91df6-107">Neben den <xref:Microsoft.SqlServer.Management.Smo.Server>- und <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer>-Objekten gibt es mehrere Hilfsklassen, die Tasks oder Vorgänge darstellen, beispielsweise <xref:Microsoft.SqlServer.Management.Smo.Transfer>, <xref:Microsoft.SqlServer.Management.Smo.Backup> und <xref:Microsoft.SqlServer.Management.Smo.Restore>.</span><span class="sxs-lookup"><span data-stu-id="91df6-107">Besides the <xref:Microsoft.SqlServer.Management.Smo.Server> and <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> objects, there are several utility classes that represent tasks or operations, such as <xref:Microsoft.SqlServer.Management.Smo.Transfer>, <xref:Microsoft.SqlServer.Management.Smo.Backup>, or <xref:Microsoft.SqlServer.Management.Smo.Restore></span></span>  
  
 <span data-ttu-id="91df6-108">Das SMO-Objektmodell besteht aus mehreren Namespaces.</span><span class="sxs-lookup"><span data-stu-id="91df6-108">The SMO object model is made up of several namespaces.</span></span> <span data-ttu-id="91df6-109">Weitere Informationen finden Sie unter [SMO-Namespaces](smo-object-model-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="91df6-109">For more information, see [SMO Namespaces](smo-object-model-namespaces.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91df6-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="91df6-110">See Also</span></span>  
 <span data-ttu-id="91df6-111">[SMO-Objektmodell Diagramm](smo-object-model-diagram.md) </span><span class="sxs-lookup"><span data-stu-id="91df6-111">[SMO Object Model Diagram](smo-object-model-diagram.md) </span></span>  
 <span data-ttu-id="91df6-112">[SMO-Namespaces](smo-object-model-namespaces.md) </span><span class="sxs-lookup"><span data-stu-id="91df6-112">[SMO Namespaces](smo-object-model-namespaces.md) </span></span>  
 [<span data-ttu-id="91df6-113">Konzepte des WMI-Anbieters für die Konfigurationsverwaltung</span><span class="sxs-lookup"><span data-stu-id="91df6-113">WMI Provider for Configuration Management Concepts</span></span>](../wmi-provider-configuration/wmi-provider-for-configuration-management.md)  
  
  
