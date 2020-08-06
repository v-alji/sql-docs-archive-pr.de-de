---
title: Entfernen von Renderingerweiterungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- deleting rendering extensions
- removing rendering extensions
- rendering extensions [Reporting Services], removing
ms.assetid: 2abfebfb-065f-45cc-a904-c914394cf900
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 77a8a9ac44b35f338f978913985617e4f264ddb7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618529"
---
# <a name="removing-a-rendering-extension"></a><span data-ttu-id="78161-102">Entfernen von Renderingerweiterungen</span><span class="sxs-lookup"><span data-stu-id="78161-102">Removing a Rendering Extension</span></span>
  <span data-ttu-id="78161-103">Um eine [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Renderingerweiterung zu entfernen, entfernen Sie einfach das- `Extension` Element für Ihre Renderingerweiterung aus der rsreportserver.config-Datei, die sich im Verzeichnis **%ProgramFiles%\Microsoft SQL Server \ MSRS10_50 befindet. \<Instance Name> Ordner \Reporting Services\ReportServer** .</span><span class="sxs-lookup"><span data-stu-id="78161-103">To remove a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] rendering extension, simply remove the `Extension` element for your rendering extension from the rsreportserver.config file, located in **%ProgramFiles%\Microsoft SQL Server\MSRS10_50.\<Instance Name>\Reporting Services\ReportServer** folder.</span></span> <span data-ttu-id="78161-104">Wenn Sie Einträge für eine Berichts-Designer und einen Berichts Server erstellt haben, entfernen Sie auch das- `Extension` Element aus der [RSReportDesigner-Konfigurationsdatei](../../report-server/rsreportdesigner-configuration-file.md) .</span><span class="sxs-lookup"><span data-stu-id="78161-104">If you made entries for a Report Designer as well as a report server, remove the `Extension` element from the [RSReportDesigner Configuration File](../../report-server/rsreportdesigner-configuration-file.md) as well.</span></span> <span data-ttu-id="78161-105">Nachdem Sie die Konfigurationsdaten entfernt haben, steht die Renderingerweiterung nicht mehr für die Komponente zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="78161-105">After the configuration information is removed, the rendering extension is no longer available to the component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78161-106">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="78161-106">See Also</span></span>  
 <span data-ttu-id="78161-107">[Reporting Services-Konfigurationsdateien](../../report-server/reporting-services-configuration-files.md) </span><span class="sxs-lookup"><span data-stu-id="78161-107">[Reporting Services Configuration Files](../../report-server/reporting-services-configuration-files.md) </span></span>  
 <span data-ttu-id="78161-108">[Implementing a Rendering Extension (Implementieren von Renderingerweiterungen)](implementing-a-rendering-extension.md) </span><span class="sxs-lookup"><span data-stu-id="78161-108">[Implementing a Rendering Extension](implementing-a-rendering-extension.md) </span></span>  
 <span data-ttu-id="78161-109">[Übersicht über Renderingerweiterungen](rendering-extensions-overview.md) </span><span class="sxs-lookup"><span data-stu-id="78161-109">[Rendering Extensions Overview](rendering-extensions-overview.md) </span></span>  
 <span data-ttu-id="78161-110">[Implementieren der IRenderingExtension-Schnittstelle](implementing-the-irenderingextension-interface.md) </span><span class="sxs-lookup"><span data-stu-id="78161-110">[Implementing the IRenderingExtension Interface](implementing-the-irenderingextension-interface.md) </span></span>  
 <span data-ttu-id="78161-111">[Überlegungen zur Sicherheit von Erweiterungen](../security-considerations-for-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="78161-111">[Security Considerations for Extensions](../security-considerations-for-extensions.md) </span></span>  
 [<span data-ttu-id="78161-112">Bereitstellen von Renderingerweiterungen</span><span class="sxs-lookup"><span data-stu-id="78161-112">Deploying a Rendering Extension</span></span>](deploying-a-rendering-extension.md)  
  
  
