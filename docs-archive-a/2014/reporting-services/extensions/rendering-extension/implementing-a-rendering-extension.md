---
title: Bereitstellen von Renderingerweiterungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- rendering extensions [Reporting Services]
- custom rendering extensions [Reporting Services]
- transformations [Reporting Services]
- extensions [Reporting Services], rendering
- rendering extensions [Reporting Services], implementing
ms.assetid: 4a5c64f5-2391-4597-ba3f-81d265b23703
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 03deb7c818de8d875f69b585ae6015fc178e707d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618531"
---
# <a name="implementing-a-rendering-extension"></a><span data-ttu-id="c8888-102">Implementieren von Renderingerweiterungen</span><span class="sxs-lookup"><span data-stu-id="c8888-102">Implementing a Rendering Extension</span></span>
  <span data-ttu-id="c8888-103">Eine Renderingerweiterung stellt eine Komponente oder ein Modul eines Berichtsservers dar, mit dem Daten- und Layoutinformationen in ein gerätespezifisches Format umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="c8888-103">A rendering extension is a component or module of a report server that transforms report data and layout information into a device-specific format.</span></span> <span data-ttu-id="c8888-104">SQL Server Reporting Services enthält sechs Renderingerweiterungen: HTML, Excel, Word, CSV oder Text, XML, Image und PDF.</span><span class="sxs-lookup"><span data-stu-id="c8888-104">SQL Server Reporting Services includes six rendering extensions: HTML, Excel, Word, CSV or Text, XML, Image, and PDF.</span></span> <span data-ttu-id="c8888-105">Sie können zusätzliche Renderingerweiterungen erstellen, um Berichte in anderen Formaten zu generieren.</span><span class="sxs-lookup"><span data-stu-id="c8888-105">You can create additional rendering extensions to generate reports in other formats.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c8888-106">Welche Renderingerweiterungen zur Verfügung stehen, sehen Sie auf der Liste der installierten Erweiterungen in der Datei RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="c8888-106">To determine which rendering extensions are available, you can view the list of installed extensions in the RSReportServer.config file.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c8888-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c8888-107">In This Section</span></span>  
 [<span data-ttu-id="c8888-108">Rendering Extensions Overview (Übersicht über Renderingerweiterungen)</span><span class="sxs-lookup"><span data-stu-id="c8888-108">Rendering Extensions Overview</span></span>](rendering-extensions-overview.md)  
 <span data-ttu-id="c8888-109">Erläutert, wie eine benutzerdefinierte Renderingerweiterung für [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="c8888-109">Introduces how to write a custom rendering extension for [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="c8888-110">Implementing the IRenderingExtension Interface (Implementieren der IRenderingExtension-Schnittstelle)</span><span class="sxs-lookup"><span data-stu-id="c8888-110">Implementing the IRenderingExtension Interface</span></span>](implementing-the-irenderingextension-interface.md)  
 <span data-ttu-id="c8888-111">Beschreibt die Attribute einer Renderingerweiterung.</span><span class="sxs-lookup"><span data-stu-id="c8888-111">Describes the attributes of a rendering extension.</span></span>  
  
 [<span data-ttu-id="c8888-112">Bereitstellen von Renderingerweiterungen</span><span class="sxs-lookup"><span data-stu-id="c8888-112">Deploying a Rendering Extension</span></span>](deploying-a-rendering-extension.md)  
 <span data-ttu-id="c8888-113">Beschreibt, wie Sie eine Renderingerweiterung auf einem Berichtsserver bereitstellen</span><span class="sxs-lookup"><span data-stu-id="c8888-113">Describes how to deploy a rendering extension on a report server.</span></span>  
  
 [<span data-ttu-id="c8888-114">Removing a Rendering Extension (Entfernen von Renderingerweiterungen)</span><span class="sxs-lookup"><span data-stu-id="c8888-114">Removing a Rendering Extension</span></span>](removing-a-rendering-extension.md)  
 <span data-ttu-id="c8888-115">Beschreibt, wie Sie eine Renderingerweiterung von einem Berichtsserver entfernen</span><span class="sxs-lookup"><span data-stu-id="c8888-115">Describes how to remove a rendering extension from a report server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8888-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c8888-116">See Also</span></span>  
 <span data-ttu-id="c8888-117">[Erweiterungen für Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="c8888-117">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 [<span data-ttu-id="c8888-118">Reporting Services Extension Library (Reporting Services-Erweiterungsbibliothek)</span><span class="sxs-lookup"><span data-stu-id="c8888-118">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
