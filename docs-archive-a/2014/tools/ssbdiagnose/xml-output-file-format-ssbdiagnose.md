---
title: Format der XML-Ausgabedatei (ssbdiagnose) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- XML output file format [ssbdiagnose]
- ssbdiagnose
ms.assetid: 3ceb991b-6f15-4504-8828-de5adf448bc5
author: stevestein
ms.author: sstein
ms.openlocfilehash: 612b317f7220f502faf1adc82cf9c1dcc8bc20a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720587"
---
# <a name="xml-output-file-format-ssbdiagnose"></a><span data-ttu-id="9ec03-102">Format der XML-Ausgabedatei (ssbdiagnose)</span><span class="sxs-lookup"><span data-stu-id="9ec03-102">XML Output File Format (ssbdiagnose)</span></span>
  <span data-ttu-id="9ec03-103">Wenn Sie das Hilfsprogramm **ssbdiagnose** mit der Option **-XML** ausführen, wird die Ausgabe als XML-Datei bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="9ec03-103">The **ssbdiagnose** utility delivers its output as an XML file when you run it with the **-XML** switch.</span></span> <span data-ttu-id="9ec03-104">Die XML-Ausgabedatei enthält Headerinformationen und die Fehler, die in der analysierten [!INCLUDE[ssSB](../../includes/sssb-md.md)] -Konfiguration oder Konversation gefunden wurden.</span><span class="sxs-lookup"><span data-stu-id="9ec03-104">The XML output file lists header information and the errors that it found in the [!INCLUDE[ssSB](../../includes/sssb-md.md)] configuration or conversation that was analyzed.</span></span> <span data-ttu-id="9ec03-105">Sie können eine Anwendung schreiben, um die in der Datei aufgelisteten Fehler zu analysieren oder einen entsprechenden Bericht zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9ec03-105">You can write an application to analyze or report on the errors listed in the file.</span></span> <span data-ttu-id="9ec03-106">Die XML-Datei kann auch in einem allgemeinen XML-Editor wie XML Editor angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="9ec03-106">Or, you can view the XML file in a general XML editor, such as XML Notepad.</span></span>  
  
 <span data-ttu-id="9ec03-107">Eine **ssbdiangose** -Ausgabedatei enthält ein DiagnosticInformation-Stammelement mit zwei untergeordneten Typen:</span><span class="sxs-lookup"><span data-stu-id="9ec03-107">An **ssbdiangose** output file contains a DiagnosticInformation root element with two child types:</span></span>  
  
-   <span data-ttu-id="9ec03-108">Einem Banner-Element mit Headerinformationen</span><span class="sxs-lookup"><span data-stu-id="9ec03-108">A Banner element with header information.</span></span>  
  
-   <span data-ttu-id="9ec03-109">Einem Issue-Element für jedes Problem, das von **ssbdiagnose**gemeldet wird</span><span class="sxs-lookup"><span data-stu-id="9ec03-109">An Issue element for each issue that is reported by **ssbdiagnose**.</span></span>  
  
## <a name="diagnosticinformation-root-element"></a><span data-ttu-id="9ec03-110">DiagnosticInformation-Stammelement</span><span class="sxs-lookup"><span data-stu-id="9ec03-110">DiagnosticInformation Root Element</span></span>  
  
-   [<span data-ttu-id="9ec03-111">DiagnosticInformation-Element &#40;ssbdiagnose&#41;</span><span class="sxs-lookup"><span data-stu-id="9ec03-111">DiagnosticInformation Element &#40;ssbdiagnose&#41;</span></span>](diagnosticinformation-element-ssbdiagnose.md)  
  
## <a name="banner-element"></a><span data-ttu-id="9ec03-112">Banner-Element</span><span class="sxs-lookup"><span data-stu-id="9ec03-112">Banner Element</span></span>  
  
-   [<span data-ttu-id="9ec03-113">Banner-Element &#40;ssbdiagnose&#41;</span><span class="sxs-lookup"><span data-stu-id="9ec03-113">Banner Element &#40;ssbdiagnose&#41;</span></span>](banner-element-ssbdiagnose.md)  
  
## <a name="issue-element"></a><span data-ttu-id="9ec03-114">Issue-Element</span><span class="sxs-lookup"><span data-stu-id="9ec03-114">Issue Element</span></span>  
  
-   [<span data-ttu-id="9ec03-115">Issue-Element &#40;ssbdiagnose&#41;</span><span class="sxs-lookup"><span data-stu-id="9ec03-115">Issue Element &#40;ssbdiagnose&#41;</span></span>](issue-element-ssbdiagnose.md)  
  
## <a name="see-also"></a><span data-ttu-id="9ec03-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9ec03-116">See Also</span></span>  
 [<span data-ttu-id="9ec03-117">ssbdiagnose-Hilfsprogramm &#40;Service Broker&#41;</span><span class="sxs-lookup"><span data-stu-id="9ec03-117">ssbdiagnose Utility &#40;Service Broker&#41;</span></span>](ssbdiagnose-utility-service-broker.md)  
  
  
