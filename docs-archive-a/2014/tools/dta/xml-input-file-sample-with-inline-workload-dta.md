---
title: Beispiel für eine XML-Eingabedatei mit Inlinearbeitsauslastung (DTA) | Microsoft-Dokumentation
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
ms.assetid: 7c04fe1d-6669-44a1-8b73-36d469e9b002
author: stevestein
ms.author: sstein
ms.openlocfilehash: 93b2ab4279378b4cd392d97a9b65f299d0e9c6dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616291"
---
# <a name="xml-input-file-sample-with-inline-workload-dta"></a><span data-ttu-id="ba55d-102">Beispiel für eine XML-Eingabedatei mit Inlinearbeitsauslastung (DTA)</span><span class="sxs-lookup"><span data-stu-id="ba55d-102">XML Input File Sample with Inline Workload (DTA)</span></span>
  <span data-ttu-id="ba55d-103">Kopieren Sie dieses Beispiel für eine XML-Eingabedatei, die eine Arbeitsauslastung mit dem **EventString** -Element angibt, und fügen Sie sie in Ihren XML-Editor oder Text-Editor ein.</span><span class="sxs-lookup"><span data-stu-id="ba55d-103">Copy and paste this sample of an XML input file that specifies a workload with the **EventString** element into your favorite XML editor or text editor.</span></span> <span data-ttu-id="ba55d-104">Mit dem **EventString** -Element können Sie eine auf einem [!INCLUDE[tsql](../../includes/tsql-md.md)] -Skript basierende Arbeitsauslastung in der XML-Eingabedatei angeben, anstatt eine separate Arbeitsauslastungsdatei zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ba55d-104">You can use the **EventString** element to specify a [!INCLUDE[tsql](../../includes/tsql-md.md)] script workload in the XML input file instead of using a separate workload file.</span></span> <span data-ttu-id="ba55d-105">Nach dem Kopieren dieses Beispiels in Ihr Bearbeitungstool ersetzen Sie die Werte für das **Server**-, **Database**-, **Schema**-, **Table**-, **Workload**-, **EventString**- und **TuningOptions** -Element durch die Werte für Ihre Optimierungssitzung.</span><span class="sxs-lookup"><span data-stu-id="ba55d-105">After copying this sample into your editing tool, replace the values specified for the **Server**, **Database**, **Schema**, **Table**, **Workload**, **EventString**, and **TuningOptions** elements with those for your specific tuning session.</span></span> <span data-ttu-id="ba55d-106">Weitere Informationen zu sämtlichen Attributen und untergeordneten Elementen, die Sie zusammen mit diesen Elementen verwenden können, finden Sie unter [XML-Eingabedateireferenz &#40;Datenbankoptimierungsratgeber&#41;](xml-input-file-reference-database-engine-tuning-advisor.md).</span><span class="sxs-lookup"><span data-stu-id="ba55d-106">For more information about all of the attributes and child elements that you can use with these elements, see the [XML Input File Reference &#40;Database Engine Tuning Advisor&#41;](xml-input-file-reference-database-engine-tuning-advisor.md).</span></span> <span data-ttu-id="ba55d-107">Im folgenden Beispiel wird nur eine Teilmenge der verfügbaren Optionen für Attribute und untergeordnete Elemente verwendet.</span><span class="sxs-lookup"><span data-stu-id="ba55d-107">The following sample uses only a subset of available attribute and child element options.</span></span>  
  
## <a name="code"></a><span data-ttu-id="ba55d-108">Code</span><span class="sxs-lookup"><span data-stu-id="ba55d-108">Code</span></span>  
 [!code-xml[InputFileSamples#InlineWorkloadInputFile](../../snippets/xml/SQL14/dta_xml/inputfilesamples/xml/dta_xml_input_file_samples.xml#inlineworkloadinputfile)]  
  
## <a name="comments"></a><span data-ttu-id="ba55d-109">Kommentare</span><span class="sxs-lookup"><span data-stu-id="ba55d-109">Comments</span></span>  
 <span data-ttu-id="ba55d-110">`USE database_name` -Anweisungen können in der Inlinearbeitsauslastung angegeben werden, die im **EventString** -Element enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="ba55d-110">`USE database_name` statements can be specified in the inline workload that is contained in the **EventString** element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba55d-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ba55d-111">See Also</span></span>  
 <span data-ttu-id="ba55d-112">[Starten und Verwenden des Datenbankoptimierungsratgebers](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="ba55d-112">[Start and Use the Database Engine Tuning Advisor](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md) </span></span>  
 <span data-ttu-id="ba55d-113">[Anzeigen und Verwenden der Ausgabe des Datenbankoptimierungsratgebers](../../relational-databases/performance/view-and-work-with-the-output-from-the-database-engine-tuning-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="ba55d-113">[View and Work with the Output from the Database Engine Tuning Advisor](../../relational-databases/performance/view-and-work-with-the-output-from-the-database-engine-tuning-advisor.md) </span></span>  
 [<span data-ttu-id="ba55d-114">XML-Eingabedateireferenz &#40;Datenbankoptimierungsratgeber&#41;</span><span class="sxs-lookup"><span data-stu-id="ba55d-114">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
