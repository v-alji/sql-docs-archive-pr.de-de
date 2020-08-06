---
title: Verwenden von WQL und Skriptsprachen mit dem WMI-Anbieter für die Konfigurations Verwaltung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
helpviewer_keywords:
- queries [WMI]
- scripts [WMI]
- query language [WMI]
- WMI Query Language [WMI]
- WQL [WMI]
- WMI Provider for Configuration Management, WQL
- WMI Provider for Configuration Management, scripts
ms.assetid: c1e64905-3c2b-4974-88f4-abf17cf7e289
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d8c903cd0e993728865bce3371c349a2d0ba7485
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617840"
---
# <a name="using-wql-and-scripting-languages-with-the-wmi-provider-for-configuration-management"></a><span data-ttu-id="ab4c6-102">Verwenden von WQL und Skriptsprachen mit dem WMI-Anbieter für die Konfigurationsverwaltung</span><span class="sxs-lookup"><span data-stu-id="ab4c6-102">Using WQL and Scripting Languages with the WMI Provider for Configuration Management</span></span>
  <span data-ttu-id="ab4c6-103">Verwaltungsanwendungen greifen auf [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Dienste und -Netzwerkeinstellungen mithilfe des WMI-Anbieters (Windows Management Instrumentation) für Konfigurationsverwaltungsobjekte auf zwei verschiedene Arten zu:</span><span class="sxs-lookup"><span data-stu-id="ab4c6-103">Management applications access [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services and network settings using the Windows Management Instrumentation (WMI) Provider for Configuration Management objects in two ways:</span></span>  
  
-   <span data-ttu-id="ab4c6-104">Mithilfe eines WQL-Editors oder eines Abfragetools, wie beispielsweise WBEMTest.exe, zum Abfragen des Objektsatzes mit der WMI-Sprache (WQL)</span><span class="sxs-lookup"><span data-stu-id="ab4c6-104">Using a WQL editor or query tool, such as WBEMTest.exe to query the object set with the Windows Management Instrumentation Language (WQL).</span></span>  
  
-   <span data-ttu-id="ab4c6-105">Mithilfe einer Skriptsprache, z. B. VBScript</span><span class="sxs-lookup"><span data-stu-id="ab4c6-105">Using a scripting language, such as VBScript.</span></span>  
  
 <span data-ttu-id="ab4c6-106">Alternativ können [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Dienste und -Netzwerkeinstellungen programmgesteuert mithilfe von verwalteten WMI-Objekten in SMO verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="ab4c6-106">Alternatively, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services and network settings can be managed programmatically using the WMI managed objects in SMO.</span></span> <span data-ttu-id="ab4c6-107">Weitere Informationen zum Programmieren von WMI-verwalteten Objekten finden [Sie unter Verwalten von Diensten und Netzwerkeinstellungen mit dem WMI-Anbieter](../server-management-objects-smo/tasks/managing-services-and-network-settings-by-using-wmi-provider.md).</span><span class="sxs-lookup"><span data-stu-id="ab4c6-107">For more information about programming WMI managed objects, see [Managing Services and Network Settings by Using WMI Provider](../server-management-objects-smo/tasks/managing-services-and-network-settings-by-using-wmi-provider.md).</span></span>  
  
 <span data-ttu-id="ab4c6-108">Der Zugriff auf den WMI-Anbieter für die Konfigurationsverwaltung erfolgt über den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Konfigurations-Manager und über [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console.</span><span class="sxs-lookup"><span data-stu-id="ab4c6-108">The WMI provider for Configuration Management can be accessed by using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager and [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console.</span></span> <span data-ttu-id="ab4c6-109">Weitere Informationen zum Zugreifen auf den WMI-Anbieter über eine Benutzeroberfläche finden [Sie unter Verwalten von Diensten &#40;SQL Server-Konfigurations-Manager&#41;](../../database-engine/managing-services-how-to-topics-sql-server-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="ab4c6-109">For more information about accessing the WMI provider from a user interface, see [Managing Services How-to Topics &#40;SQL Server Configuration Manager&#41;](../../database-engine/managing-services-how-to-topics-sql-server-configuration-manager.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab4c6-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ab4c6-110">See Also</span></span>  
 <span data-ttu-id="ab4c6-111">[Zugreifen auf den WMI-Anbieter für die Konfigurations Verwaltung mit WQL](access-wmi-provider-for-configuration-management-using-wql.md) </span><span class="sxs-lookup"><span data-stu-id="ab4c6-111">[Access WMI Provider for Configuration Management using WQL](access-wmi-provider-for-configuration-management-using-wql.md) </span></span>  
 [<span data-ttu-id="ab4c6-112">Ändern der erweiterten Eigenschaften des SQL Server-Diensts mit VBScript</span><span class="sxs-lookup"><span data-stu-id="ab4c6-112">Modify SQL Server Service Advanced Properties using VBScript</span></span>](access-wmi-provider-for-configuration-management-using-vbscript.md)  
  
  
