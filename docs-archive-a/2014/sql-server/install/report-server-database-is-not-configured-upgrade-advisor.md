---
title: Die Berichts Server-Datenbank ist nicht konfiguriert (Upgrade Advisor) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- report servers [Reporting Services], upgrade issues
ms.assetid: b964300c-b220-4244-9fa6-c0c6a57760f6
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 072e689da3f43222396f071e607214a2ec494749
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608243"
---
# <a name="report-server-database-is-not-configured-upgrade-advisor"></a><span data-ttu-id="9135e-102">Berichtsserver-Datenbank ist nicht konfiguriert (Upgrade Advisor)</span><span class="sxs-lookup"><span data-stu-id="9135e-102">Report server database is not configured (Upgrade Advisor)</span></span>
  <span data-ttu-id="9135e-103">Das Upgrade wird aufgrund einer unvollständigen Berichtsserverkonfiguration blockiert.</span><span class="sxs-lookup"><span data-stu-id="9135e-103">Upgrade is blocked due to an incomplete report server configuration.</span></span> <span data-ttu-id="9135e-104">Die Berichtsserver-Datenbank ist nicht konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="9135e-104">The report server database is not configured.</span></span>  
  
||  
|-|  
|<span data-ttu-id="9135e-105">**[!INCLUDE[applies](../../includes/applies-md.md)]** [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] im einheitlichen Modus &#124; [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] im SharePoint-Modus</span><span class="sxs-lookup"><span data-stu-id="9135e-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode &#124; [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="9135e-106">Komponente</span><span class="sxs-lookup"><span data-stu-id="9135e-106">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="9135e-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9135e-107">Description</span></span>  
 <span data-ttu-id="9135e-108">Setup kann nur eine vollständig konfigurierte Berichtsserverinstanz aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="9135e-108">Setup can only upgrade a fully configured report server instance.</span></span> <span data-ttu-id="9135e-109">Um den Vorgang fortzusetzen, müssen Sie entweder die Berichts Server-Datenbank konfigurieren oder die Microsoft Windows- **Systemsteuerung** verwenden, um die Berichts Server Funktion aus der-Installation zu entfernen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9135e-109">To continue, you must either configure the report server database, or use Microsoft Windows **Control Panel** to remove the report server feature from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation.</span></span> <span data-ttu-id="9135e-110">Nachdem Sie [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] entfernt haben, können Sie andere [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Komponenten aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="9135e-110">After you remove [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you can upgrade other [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="9135e-111">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="9135e-111">Corrective Action</span></span>  
 <span data-ttu-id="9135e-112">Wenn Sie die Berichtsserver-Datenbank nicht konfiguriert haben, ist der Berichtsserver nicht betriebsbereit und muss vor dem Upgrade entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="9135e-112">If you did not configure the report server database, the report server is not operational and should be removed prior to upgrade.</span></span>  
  
 <span data-ttu-id="9135e-113">Weitere Informationen zum [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Deinstallieren von finden Sie unter [Deinstallieren von Reporting Services 2012](https://technet.microsoft.com/library/hh479745.aspx\(v=sql.11\)).</span><span class="sxs-lookup"><span data-stu-id="9135e-113">For additional information on uninstalling [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , see [Uninstall Reporting Services 2012](https://technet.microsoft.com/library/hh479745.aspx\(v=sql.11\)).</span></span> <span data-ttu-id="9135e-114">Im Thema wird beschrieben, wie eine bestimmte Version deinstalliert wird; die Vorgehensweise dabei ist für frühere Versionen ähnlich.</span><span class="sxs-lookup"><span data-stu-id="9135e-114">the topic describes how to uninstall a specific version and the procedures are similar for previous versions as well.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9135e-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9135e-115">See Also</span></span>  
 [<span data-ttu-id="9135e-116">Reporting Services Upgradeprobleme &#40;Upgrade Advisor&#41;</span><span class="sxs-lookup"><span data-stu-id="9135e-116">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
