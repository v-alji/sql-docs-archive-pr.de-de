---
title: XML-Geräteinformationseinstellungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- XML [Reporting Services], rendering
- device information settings [Reporting Services], PDF rendering
ms.assetid: a32e83fe-c10e-4ebd-8975-5be7dcc422e7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: e642034d445e52485874c71df110bff81b9c1aaf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720929"
---
# <a name="xml-device-information-settings"></a><span data-ttu-id="92298-102">XML-Geräteinformationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="92298-102">XML Device Information Settings</span></span>
  <span data-ttu-id="92298-103">In der folgenden Tabelle werden die Geräteinformationseinstellungen zum Rendern in das XML-Format aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="92298-103">The following table lists the device information settings for rendering in XML format.</span></span>  
  
|<span data-ttu-id="92298-104">Einstellung</span><span class="sxs-lookup"><span data-stu-id="92298-104">Setting</span></span>|<span data-ttu-id="92298-105">Wert</span><span class="sxs-lookup"><span data-stu-id="92298-105">Value</span></span>|  
|-------------|-----------|  
|`XSLT`|<span data-ttu-id="92298-106">Der Pfad zum Berichtsserver-Namespace von XSLT, der auf die XML-Datei, z. B. `/Transforms/myxslt`, angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="92298-106">The path in the report server namespace of an XSLT to apply to the XML file, for example `/Transforms/myxslt`.</span></span> <span data-ttu-id="92298-107">Die XSL-Datei muss eine veröffentlichte Ressource auf einem Berichtsserver sein, und Sie müssen über einen Berichtsserver-Elementpfad darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="92298-107">The xsl file must be a published resource on the report server and you must access it through a report server item path.</span></span> <span data-ttu-id="92298-108">Der Wert dieser Einstellung wird nach jedem XSLT übernommen, das im Bericht angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="92298-108">The value of this setting is applied after any XSLT that is specified in the report.</span></span> <span data-ttu-id="92298-109">Wird die `XSLT`-Einstellung angewendet, wird die `OmitSchema`-Einstellung nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="92298-109">If the `XSLT` setting is applied, the `OmitSchema` setting is ignored.</span></span>|  
|<span data-ttu-id="92298-110">**MIMEType**</span><span class="sxs-lookup"><span data-stu-id="92298-110">**MIMEType**</span></span>|<span data-ttu-id="92298-111">MIME-Typ (Multipurpose Internet Mail Extensions) der XML-Datei</span><span class="sxs-lookup"><span data-stu-id="92298-111">The Multipurpose Internet Mail Extensions (MIME) type of the XML file.</span></span>|  
|<span data-ttu-id="92298-112">**UseFormattedValues**</span><span class="sxs-lookup"><span data-stu-id="92298-112">**UseFormattedValues**</span></span>|<span data-ttu-id="92298-113">Gibt an, ob der formatierte Wert eines Textfelds beim Generieren der XML-Daten gerendert werden soll.</span><span class="sxs-lookup"><span data-stu-id="92298-113">Indicates whether to render the formatted value of a text box when generating the XML data.</span></span> <span data-ttu-id="92298-114">Ein false-Wert gibt an, dass der zugrundeliegende Wert des Textfelds verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="92298-114">A value of false indicates that the underlying value of the text box is used.</span></span>|  
|<span data-ttu-id="92298-115">**Indented**</span><span class="sxs-lookup"><span data-stu-id="92298-115">**Indented**</span></span>|<span data-ttu-id="92298-116">Gibt an, ob XML-Dateien mit Einzug generiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="92298-116">Indicates whether to generate indented XML.</span></span> <span data-ttu-id="92298-117">Der Standardwert `false` generiert komprimierte XML-Dateien ohne Einzug.</span><span class="sxs-lookup"><span data-stu-id="92298-117">The default value of `false` generates non-indented, compressed XML.</span></span>|  
|`OmitNamespace`|<span data-ttu-id="92298-118">Gibt an, ob der Standardnamespace in der XML-Datei weggelassen werden soll.</span><span class="sxs-lookup"><span data-stu-id="92298-118">Indicates whether to omit the default namespace from the XML.</span></span><br /><br /> <span data-ttu-id="92298-119">Bei "true" wird kein Standardnamespace in der XML-Datei angegeben.</span><span class="sxs-lookup"><span data-stu-id="92298-119">If true, the XML does not specify a default namespace.</span></span><br /><br /> <span data-ttu-id="92298-120">Bei FALSE gibt die XML-Datei einen Standardnamespace mit dem Wert der DataSchema-Eigenschaft des Berichts an.</span><span class="sxs-lookup"><span data-stu-id="92298-120">If false, the XML specifies a default namespace with the value of the report's DataSchema property.</span></span> <span data-ttu-id="92298-121">Die DataSchema-Eigenschaft verwendet standardmäßig den Berichtsnamen.</span><span class="sxs-lookup"><span data-stu-id="92298-121">The DataSchema property defaults to the report name.</span></span><br /><br /> <span data-ttu-id="92298-122">Standardwert: `false`.</span><span class="sxs-lookup"><span data-stu-id="92298-122">The default value is `false`.</span></span>|  
|`OmitSchema`|<span data-ttu-id="92298-123">Gibt an, ob der Schemaspeicherort in der XML-Datei weggelassen werden soll.</span><span class="sxs-lookup"><span data-stu-id="92298-123">Indicates whether to omit the schema location from the XML.</span></span> <span data-ttu-id="92298-124">Der Speicherort ist das SchemaLocation-Attribut.</span><span class="sxs-lookup"><span data-stu-id="92298-124">The location is the SchemaLocation attribute.</span></span> <span data-ttu-id="92298-125">Der Standardwert von OmitSchema hängt vom OmitNamespace-Wert ab:</span><span class="sxs-lookup"><span data-stu-id="92298-125">The default value of OmitSchema depends on the value of OmitNamespace:</span></span><br /><br /> <span data-ttu-id="92298-126">Wenn OmitNamespace = False, gilt standardmäßig OmitSchema = `False`.</span><span class="sxs-lookup"><span data-stu-id="92298-126">If OmitNamespace = False, then OmitSchema = `False` by default.</span></span> <span data-ttu-id="92298-127">Der Benutzer kann den Standardwert überschreiben, indem OmitSchema = True festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="92298-127">The user can override the default by setting OmitSchema = True.</span></span><br /><br /> <span data-ttu-id="92298-128">Wenn OmitNamespace = True, gilt für OmitSchema `True` – unabhängig vom explizit für OmitShema konfigurierten Wert.</span><span class="sxs-lookup"><span data-stu-id="92298-128">If OmitNamespace = True, then OmitSchema will function as `True` regardless of the value explicitly configured for OmitShema.</span></span>|  
|<span data-ttu-id="92298-129">**Codierung**</span><span class="sxs-lookup"><span data-stu-id="92298-129">**Encoding**</span></span>|<span data-ttu-id="92298-130">Der Internet Assigned Numbers Authority (IANA)-Name einer Zeichencodierung, die von .NET Framework unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="92298-130">The Internet Assigned Numbers Authority (IANA) name of a character encoding that is supported by the .NET Framework.</span></span> <span data-ttu-id="92298-131">Standardwert: `UTF-8`.</span><span class="sxs-lookup"><span data-stu-id="92298-131">The default value is `UTF-8`.</span></span> <span data-ttu-id="92298-132">Beispiele für andere Werte: ASCII, UTF-7 und UTF-16.</span><span class="sxs-lookup"><span data-stu-id="92298-132">Examples of other values include ASCII, UTF-7, and UTF-16.</span></span>|  
|<span data-ttu-id="92298-133">**File extension**</span><span class="sxs-lookup"><span data-stu-id="92298-133">**FileExtension**</span></span>|<span data-ttu-id="92298-134">Die Dateierweiterung für die generierte Datei.</span><span class="sxs-lookup"><span data-stu-id="92298-134">The file extension to use for the generated file.</span></span>|  
|<span data-ttu-id="92298-135">**Schema**</span><span class="sxs-lookup"><span data-stu-id="92298-135">**Schema**</span></span>|<span data-ttu-id="92298-136">Gibt an, ob die XML-Schemadefinition (XSD) gerendert wird oder ob die tatsächlichen XML-Daten gerendert werden.</span><span class="sxs-lookup"><span data-stu-id="92298-136">Indicates whether the XML schema definition (XSD) is rendered or whether the actual XML data is rendered.</span></span> <span data-ttu-id="92298-137">Der Wert `true` gibt an, dass ein XML-Schema gerendert wird.</span><span class="sxs-lookup"><span data-stu-id="92298-137">A value of `true` indicates that an XML schema is rendered.</span></span> <span data-ttu-id="92298-138">Standardwert: `false`.</span><span class="sxs-lookup"><span data-stu-id="92298-138">The default value is `false`.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="92298-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="92298-139">See Also</span></span>  
 <xref:ReportExecution2005.ReportExecutionService.Render%2A>   
 <span data-ttu-id="92298-140">[Übergeben von Geräte Informationseinstellungen an Renderingerweiterungen](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="92298-140">[Passing Device Information Settings to Rendering Extensions](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span></span>  
 <span data-ttu-id="92298-141">[Anpassen von Renderingerweiterungsparametern in RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span><span class="sxs-lookup"><span data-stu-id="92298-141">[Customize Rendering Extension Parameters in RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span></span>  
 [<span data-ttu-id="92298-142">Technische Referenz (SSRS)</span><span class="sxs-lookup"><span data-stu-id="92298-142">Technical Reference &#40;SSRS&#41;</span></span>](../../2014/reporting-services/technical-reference-ssrs.md)  
  
  