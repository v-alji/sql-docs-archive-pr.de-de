---
title: Bereitstellen einer Datenverarbeitungserweiterung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- data processing extensions [Reporting Services], deploying
- Extension element
- deploying [Reporting Services], extensions
ms.assetid: e5c0b5a9-1386-47cb-aade-96653ecfaa54
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 84fc2d2853ce7a6aae77f313ef0f4026ad2f35cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725285"
---
# <a name="deploying-a-data-processing-extension"></a><span data-ttu-id="bca85-102">Bereitstellen von Datenverarbeitungserweiterungen</span><span class="sxs-lookup"><span data-stu-id="bca85-102">Deploying a Data Processing Extension</span></span>
  <span data-ttu-id="bca85-103">Wenn Sie die [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]-Datenverarbeitungserweiterung geschrieben und in eine [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]-Bibliothek kompiliert haben, müssen Sie sie für den Berichtsserver und den Berichts-Designer erkennbar machen.</span><span class="sxs-lookup"><span data-stu-id="bca85-103">Once you have written and compiled your [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] data processing extension into a [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] library, you need to make it discoverable by the report server and by Report Designer.</span></span> <span data-ttu-id="bca85-104">Dazu müssen Sie lediglich die Erweiterung in die entsprechenden Verzeichnisse kopieren und Einträge zu den zugehörigen [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]-Konfigurationsdateien hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="bca85-104">This is as easy as copying the extension to the appropriate directories and adding entries to the appropriate [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] configuration files.</span></span>  
  
## <a name="configuration-file-extension-element"></a><span data-ttu-id="bca85-105">Extension-Element für die Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="bca85-105">Configuration-File Extension Element</span></span>  
 <span data-ttu-id="bca85-106">Datenverarbeitungserweiterungen, die Sie für den Berichtsserver oder den Berichts-Designer bereitstellen, müssen in den Konfigurationsdateien als **Extension**-Elemente hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="bca85-106">Data processing extensions that you deploy to the report server or Report Designer need to be entered as **Extension** elements in the configuration files.</span></span> <span data-ttu-id="bca85-107">Bei diesen Dateien handelt es sich um RSReportServer.config für den Berichtsserver und RSReportDesigner.config für den Berichts-Designer.</span><span class="sxs-lookup"><span data-stu-id="bca85-107">These files are RSReportServer.config for the report server and RSReportDesigner.config for Report Designer.</span></span>  
  
 <span data-ttu-id="bca85-108">In der folgenden Tabelle werden die Attribute für das **Extension**-Element für Datenverarbeitungserweiterungen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bca85-108">The following table describes the attributes for the **Extension** element for data processing extensions.</span></span>  
  
|<span data-ttu-id="bca85-109">attribute</span><span class="sxs-lookup"><span data-stu-id="bca85-109">Attribute</span></span>|<span data-ttu-id="bca85-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="bca85-110">Description</span></span>|  
|---------------|-----------------|  
|`Name`|<span data-ttu-id="bca85-111">Ein eindeutiger Name für die Erweiterung, z. B. "SQL" für die [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Datenverarbeitungserweiterung oder "OLEDB" für die OLE DB-Datenverarbeitungserweiterung.</span><span class="sxs-lookup"><span data-stu-id="bca85-111">A unique name for the extension, for example, "SQL" for the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data processing extension or "OLEDB" for the OLE DB data processing extension.</span></span> <span data-ttu-id="bca85-112">Die maximale Länge für das `Name`-Attribut beträgt 255 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="bca85-112">The maximum length for the `Name` attribute is 255 characters.</span></span> <span data-ttu-id="bca85-113">Der Name muss für sämtliche Einträge im **Extension** -Element einer Konfigurationsdatei eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="bca85-113">The name must be unique among all entries within the **Extension** element of a configuration file.</span></span>|  
|`Type`|<span data-ttu-id="bca85-114">Eine durch Trennzeichen getrennte Liste, die den vollqualifizierten Namespace und den Namen der Assembly enthält</span><span class="sxs-lookup"><span data-stu-id="bca85-114">A comma-separated list that includes the fully qualified namespace along with the name of the assembly.</span></span>|  
|`Visible`|<span data-ttu-id="bca85-115">Der Wert `false` gibt an, dass die Datenverarbeitungserweiterung auf Benutzeroberflächen nicht sichtbar sein soll.</span><span class="sxs-lookup"><span data-stu-id="bca85-115">A value of `false` indicates that the data processing extension should not be visible in user interfaces.</span></span> <span data-ttu-id="bca85-116">Wenn das Attribut nicht enthalten ist, ist `true` der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="bca85-116">If the attribute is not included, the default value is `true`.</span></span>|  
  
 <span data-ttu-id="bca85-117">Weitere Informationen über die Dateien „RSReportServer.config“ und „RSReportDesigner.config“ finden Sie unter [Reporting Services-Konfigurationsdateien](../../report-server/reporting-services-configuration-files.md).</span><span class="sxs-lookup"><span data-stu-id="bca85-117">For more information about the RSReportServer.config or RSReportDesigner.config files, see [Reporting Services Configuration Files](../../report-server/reporting-services-configuration-files.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bca85-118">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="bca85-118">In This Section</span></span>  
  
|<span data-ttu-id="bca85-119">Thema</span><span class="sxs-lookup"><span data-stu-id="bca85-119">Topic</span></span>|<span data-ttu-id="bca85-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bca85-120">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="bca85-121">Gewusst wie: Bereitstellen einer Datenverarbeitungserweiterung für einen Berichtsserver</span><span class="sxs-lookup"><span data-stu-id="bca85-121">How to: Deploy a Data Processing Extension to a Report Server</span></span>](deploying-a-data-processing-extension-to-a-report-server.md)|<span data-ttu-id="bca85-122">Beschreibt, wie Sie eine Datenverarbeitungserweiterung auf einem Berichtsserver bereitstellen</span><span class="sxs-lookup"><span data-stu-id="bca85-122">Describes how to deploy your data processing extension to a report server.</span></span>|  
|[<span data-ttu-id="bca85-123">Gewusst wie: Bereitstellen einer Datenverarbeitungserweiterung für den Berichts-Designer</span><span class="sxs-lookup"><span data-stu-id="bca85-123">How to: Deploy a Data Processing Extension to Report Designer</span></span>](deploying-a-data-processing-extension-to-report-designer.md)|<span data-ttu-id="bca85-124">Beschreibt, wie Sie eine Datenverarbeitungserweiterung für den Berichts-Designer bereitstellen</span><span class="sxs-lookup"><span data-stu-id="bca85-124">Describes how to deploy your data processing extension to Report Designer.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bca85-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bca85-125">See Also</span></span>  
 <span data-ttu-id="bca85-126">[Reporting Services Erweiterungen](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="bca85-126">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 <span data-ttu-id="bca85-127">[Implementieren einer Datenverarbeitungs Erweiterung](implementing-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="bca85-127">[Implementing a Data Processing Extension](implementing-a-data-processing-extension.md) </span></span>  
 [<span data-ttu-id="bca85-128">Reporting Services-Erweiterungsbibliothek</span><span class="sxs-lookup"><span data-stu-id="bca85-128">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
