---
title: Beispiel für eine XML-Eingabedatei mit benutzerdefinierter Konfiguration (DTA) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- sample applications [DTA]
ms.assetid: b29c9716-e5c3-4003-9efb-3ade2197b630
author: stevestein
ms.author: sstein
ms.openlocfilehash: 121972518aa114e16cc81517d52a9d9656b067c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620087"
---
# <a name="xml-input-file-sample-with-user-specified-configuration-dta"></a><span data-ttu-id="f0ccc-102">Beispiel für eine XML-Eingabedatei mit benutzerdefinierter Konfiguration (DTA)</span><span class="sxs-lookup"><span data-stu-id="f0ccc-102">XML Input File Sample with User-specified Configuration (DTA)</span></span>
  <span data-ttu-id="f0ccc-103">Kopieren Sie dieses Beispiel für eine XML-Eingabedatei, die eine benutzerdefinierte Konfiguration mit dem **Configuration** -Element angibt, und fügen Sie sie in Ihren XML-Editor oder Text-Editor ein.</span><span class="sxs-lookup"><span data-stu-id="f0ccc-103">Copy and paste this sample of an XML input file that specifies a user-specified configuration with the **Configuration** element into your favorite XML editor or text editor.</span></span> <span data-ttu-id="f0ccc-104">Dadurch können Sie Was-wäre-wenn-Analysen ausführen.</span><span class="sxs-lookup"><span data-stu-id="f0ccc-104">This enables you to perform "what-if" analysis.</span></span> <span data-ttu-id="f0ccc-105">Bei Was-wäre-wenn-Analysen wird mit dem **Configuration** -Element eine Gruppe von hypothetischen physischen Entwurfsstrukturen für die Datenbank angegeben, die Sie optimieren möchten.</span><span class="sxs-lookup"><span data-stu-id="f0ccc-105">"What-if" analysis involves using the **Configuration** element to specify a set of hypothetical physical design structures for the database you want to tune.</span></span> <span data-ttu-id="f0ccc-106">Anschließend analysieren Sie mit dem Datenbankoptimierungsratgeber, welche Auswirkungen das Ausführen einer Arbeitsauslastung für diese hypothetische Konfiguration hat, um herauszufinden, ob dadurch die Abfrageverarbeitungsleistung verbessert werden kann.</span><span class="sxs-lookup"><span data-stu-id="f0ccc-106">Then you use Database Engine Tuning Advisor to analyze the effects of running a workload against this hypothetical configuration to find out whether it improves query processing performance.</span></span> <span data-ttu-id="f0ccc-107">Diese Art einer Analyse hat den Vorteil, dass die neue Konfiguration ausgewertet werden kann, ohne dass eine Implementierung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="f0ccc-107">This type of analysis provides the advantage of evaluating the new configuration without incurring the overhead of actually implementing it.</span></span> <span data-ttu-id="f0ccc-108">Wenn die hypothetische Konfiguration nicht die gewünschten Leistungssteigerungen erzielt, lässt sie sich auf einfache Weise ändern und erneut analysieren, bis Sie die Konfiguration haben, die die gewünschten Ergebnisse erzielt.</span><span class="sxs-lookup"><span data-stu-id="f0ccc-108">If your hypothetical configuration does not provide the performance improvements you want, it is easy to change it and analyze it again until you reach the configuration that produces the results you need.</span></span>  
  
 <span data-ttu-id="f0ccc-109">Nach dem Kopieren dieses Beispiels in Ihr Bearbeitungstool ersetzen Sie die Werte für das **Server**-, **Database**-, **Schema**-, **Table**-, **Workload**-, **TuningOptions**- und **Configuration** -Element durch die Werte für Ihre Optimierungssitzung.</span><span class="sxs-lookup"><span data-stu-id="f0ccc-109">After copying this sample into your editing tool, replace the values specified for the **Server**, **Database**, **Schema**, **Table**, **Workload**, **TuningOptions**, and **Configuration** elements with those for your specific tuning session.</span></span> <span data-ttu-id="f0ccc-110">Weitere Informationen zu sämtlichen Attributen und untergeordneten Elementen, die Sie zusammen mit diesen Elementen verwenden können, finden Sie unter [XML-Eingabedateireferenz &#40;Datenbankoptimierungsratgeber&#41;](xml-input-file-reference-database-engine-tuning-advisor.md).</span><span class="sxs-lookup"><span data-stu-id="f0ccc-110">For more information about all of the attributes and child elements that you can use with these elements, see the [XML Input File Reference &#40;Database Engine Tuning Advisor&#41;](xml-input-file-reference-database-engine-tuning-advisor.md).</span></span> <span data-ttu-id="f0ccc-111">Im folgenden Beispiel wird nur eine Teilmenge der verfügbaren Optionen für Attribute und untergeordnete Elemente verwendet.</span><span class="sxs-lookup"><span data-stu-id="f0ccc-111">The following sample uses only a subset of available attribute and child element options.</span></span>  
  
## <a name="code"></a><span data-ttu-id="f0ccc-112">Code</span><span class="sxs-lookup"><span data-stu-id="f0ccc-112">Code</span></span>  
 [!code-xml[InputFileSamples#UserSpecifiedConfigInputFile](../../snippets/xml/SQL14/dta_xml/inputfilesamples/xml/dta_xml_input_file_samples.xml#userspecifiedconfiginputfile)]  
  
## <a name="comments"></a><span data-ttu-id="f0ccc-113">Kommentare</span><span class="sxs-lookup"><span data-stu-id="f0ccc-113">Comments</span></span>  
  
-   <span data-ttu-id="f0ccc-114">Das Löschen von physischen Entwurfsstrukturen wird nicht unterstützt, wenn Sie den **Absolute** -Modus für das **Configuration** -Element angeben (`Configuration SpecificationMode="Absolute"`).</span><span class="sxs-lookup"><span data-stu-id="f0ccc-114">Dropping physical design structures is not supported if you specify the **Absolute** mode for the **Configuration** element (`Configuration SpecificationMode="Absolute"`).</span></span>  
  
-   <span data-ttu-id="f0ccc-115">Sie können die gleiche physische Entwurfsstruktur nicht in beiden Modi (**Relative** oder **Absolute**) des **Configuration** -Elements erstellen und löschen.</span><span class="sxs-lookup"><span data-stu-id="f0ccc-115">You cannot create and drop the same physical design structure in either mode (**Relative** or **Absolute**) of the **Configuration** element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0ccc-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f0ccc-116">See Also</span></span>  
 <span data-ttu-id="f0ccc-117">[Starten und Verwenden des Datenbankoptimierungsratgebers](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="f0ccc-117">[Start and Use the Database Engine Tuning Advisor](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md) </span></span>  
 <span data-ttu-id="f0ccc-118">[Anzeigen und Verwenden der Ausgabe des Datenbankoptimierungsratgebers](../../relational-databases/performance/view-and-work-with-the-output-from-the-database-engine-tuning-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="f0ccc-118">[View and Work with the Output from the Database Engine Tuning Advisor](../../relational-databases/performance/view-and-work-with-the-output-from-the-database-engine-tuning-advisor.md) </span></span>  
 [<span data-ttu-id="f0ccc-119">XML-Eingabedateireferenz &#40;Datenbankoptimierungsratgeber&#41;</span><span class="sxs-lookup"><span data-stu-id="f0ccc-119">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
