---
title: Geräteinformationseinstellungen für Renderingerweiterungen (Reporting Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 947b0ee1-bb35-4b4e-9527-dc501566e7d1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f15e27e01cd43bafda3aede3deca7729f2c89756
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719660"
---
# <a name="device-information-settings-for-rendering-extensions-reporting-services"></a><span data-ttu-id="738c2-102">Geräteinformationseinstellungen für Renderingerweiterungen (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="738c2-102">Device Information Settings for Rendering Extensions (Reporting Services)</span></span>
  <span data-ttu-id="738c2-103">In [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]werden Geräteinformationseinstellungen zum Übergeben von Renderingparametern an eine Renderingerweiterung verwendet.</span><span class="sxs-lookup"><span data-stu-id="738c2-103">In [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], device information settings are used to pass rendering parameters to a rendering extension.</span></span> <span data-ttu-id="738c2-104">Jede Renderingerweiterung akzeptiert einen bestimmten Satz von Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="738c2-104">Each rendering extension accepts a specific set of settings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="738c2-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="738c2-105">In This Section</span></span>  
  
|<span data-ttu-id="738c2-106">Thema</span><span class="sxs-lookup"><span data-stu-id="738c2-106">Topic</span></span>|<span data-ttu-id="738c2-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="738c2-107">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="738c2-108">ATOM Device Information Settings (ATOM-Geräteinformationseinstellungen)</span><span class="sxs-lookup"><span data-stu-id="738c2-108">ATOM Device Information Settings</span></span>](../../2014/reporting-services/atom-device-information-settings.md)|<span data-ttu-id="738c2-109">Beschreibt die Geräteinformationseinstellungen, die der Atom-kompatiblen Renderingausgabe zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="738c2-109">Describes the device information settings that are associated with Atom compliant rendering output.</span></span>|  
|[<span data-ttu-id="738c2-110">CSV Device Information Settings (CSV-Geräteinformationseinstellungen)</span><span class="sxs-lookup"><span data-stu-id="738c2-110">CSV Device Information Settings</span></span>](csv-device-information-settings.md)|<span data-ttu-id="738c2-111">Beschreibt die Geräteinformationseinstellungen, die der CSV-Renderingausgabe zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="738c2-111">Describes the device information settings that are associated with CSV rendering output.</span></span>|  
|[<span data-ttu-id="738c2-112">Excel Device Information Settings (Geräteinformationseinstellungen für Excel)</span><span class="sxs-lookup"><span data-stu-id="738c2-112">Excel Device Information Settings</span></span>](excel-device-information-settings.md)|<span data-ttu-id="738c2-113">Beschreibt die Geräteinformationseinstellungen, die der Excel-Renderingausgabe zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="738c2-113">Describes the device information settings that are associated with Excel rendering output.</span></span>|  
|[<span data-ttu-id="738c2-114">Word Device Information Settings (Geräteinformationseinstellungen für Word)</span><span class="sxs-lookup"><span data-stu-id="738c2-114">Word Device Information Settings</span></span>](word-device-information-settings.md)|<span data-ttu-id="738c2-115">Beschreibt die Geräteinformationseinstellungen, die der Word-Renderingausgabe zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="738c2-115">Describes the device information settings that are associated with Word rendering output.</span></span>|  
|[<span data-ttu-id="738c2-116">HTML-Geräteinformationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="738c2-116">HTML Device Information Settings</span></span>](html-device-information-settings.md)|<span data-ttu-id="738c2-117">Beschreibt die Geräteinformationseinstellungen, die der HTML-Renderingausgabe zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="738c2-117">Describes the device information settings that are associated with HTML rendering output.</span></span>|  
|[<span data-ttu-id="738c2-118">Geräteinformationseinstellungen für Bilder</span><span class="sxs-lookup"><span data-stu-id="738c2-118">Image Device Information Settings</span></span>](image-device-information-settings.md)|<span data-ttu-id="738c2-119">Beschreibt die Geräteinformationseinstellungen, die der IMAGE-Renderingausgabe zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="738c2-119">Describes the device information settings that are associated with IMAGE rendering output.</span></span>|  
|[<span data-ttu-id="738c2-120">Geräteinformationseinstellungen für MHTML</span><span class="sxs-lookup"><span data-stu-id="738c2-120">MHTML Device Information Settings</span></span>](mhtml-device-information-settings.md)|<span data-ttu-id="738c2-121">Beschreibt die Geräteinformationseinstellungen, die der MHTML-Renderingausgabe zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="738c2-121">Describes the device information settings that are associated with MHTML rendering output.</span></span>|  
|[<span data-ttu-id="738c2-122">PDF Device Information Settings (PDF-Geräteinformationseinstellungen)</span><span class="sxs-lookup"><span data-stu-id="738c2-122">PDF Device Information Settings</span></span>](pdf-device-information-settings.md)|<span data-ttu-id="738c2-123">Beschreibt die Geräteinformationseinstellungen, die der PDF-Renderingausgabe zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="738c2-123">Describes the device information settings that are associated with PDF rendering output.</span></span>|  
|[<span data-ttu-id="738c2-124">XML Device Information Settings (XML-Geräteinformationseinstellungen)</span><span class="sxs-lookup"><span data-stu-id="738c2-124">XML Device Information Settings</span></span>](xml-device-information-settings.md)|<span data-ttu-id="738c2-125">Beschreibt die Geräteinformationseinstellungen, die der XML-Renderingausgabe zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="738c2-125">Describes the device information settings that are associated with XML rendering output.</span></span>|  
|[<span data-ttu-id="738c2-126">RGDI Device Information Settings (RGDI-Geräteinformationseinstellungen)</span><span class="sxs-lookup"><span data-stu-id="738c2-126">RGDI Device Information Settings</span></span>](rgdi-device-information-settings.md)|<span data-ttu-id="738c2-127">Beschreibt die Geräteinformationseinstellungen, die der RGDI-Renderingausgabe zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="738c2-127">Describes the device information settings that are associated with RGDI rendering output.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="738c2-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="738c2-128">See Also</span></span>  
 [<span data-ttu-id="738c2-129">Anpassen der Parameter für Renderingerweiterungen in der Datei RSReportServer.config</span><span class="sxs-lookup"><span data-stu-id="738c2-129">Customize Rendering Extension Parameters in RSReportServer.Config</span></span>](customize-rendering-extension-parameters-in-rsreportserver-config.md)  
  
  
