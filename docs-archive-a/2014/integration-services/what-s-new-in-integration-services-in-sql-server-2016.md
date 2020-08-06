---
title: Neuerungen&#39;s (Integration Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services, what's new
- what's new [Integration Services]
ms.assetid: da6999c7-e5e3-4a59-a284-1da635995af1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 84f0b668407c89e1d6acc3c8cfbda73f129ca19a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621561"
---
# <a name="what39s-new-integration-services"></a><span data-ttu-id="78e4f-102">Neues&#39;s (Integration Services)</span><span class="sxs-lookup"><span data-stu-id="78e4f-102">What&#39;s New (Integration Services)</span></span>
  [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]<span data-ttu-id="78e4f-103">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]ist gegenüber der vorherigen Version unverändert.</span><span class="sxs-lookup"><span data-stu-id="78e4f-103">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] is unchanged from the previous release.</span></span>  
  
 <span data-ttu-id="78e4f-104">Weitere Informationen zu anderen [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Produkten und Technologien finden Sie unter [What es New in SQL Server 2014](../sql-server/what-s-new-in-sql-server-2016.md).</span><span class="sxs-lookup"><span data-stu-id="78e4f-104">For information about other [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] products and technologies, see [What's New in SQL Server 2014](../sql-server/what-s-new-in-sql-server-2016.md).</span></span>  
  
 <span data-ttu-id="78e4f-105">Weitere Informationen zu Änderungen im Zusammenhang mit [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Business Intelligence finden Sie unter [Neues in Analysis Services und Business Intelligence](https://docs.microsoft.com/analysis-services/what-s-new-in-analysis-services).</span><span class="sxs-lookup"><span data-stu-id="78e4f-105">For more information about changes related to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Business Intelligence, see [What's New in Analysis Services and Business Intelligence](https://docs.microsoft.com/analysis-services/what-s-new-in-analysis-services).</span></span>  
  
##  <a name="rich-xml-validation-output-in-the-xml-task"></a><a name="ValidateXML"></a> <span data-ttu-id="78e4f-106">Umfangreiche Ausgabe der XML-Validierung im XML-Task</span><span class="sxs-lookup"><span data-stu-id="78e4f-106">Rich XML validation output in the XML Task</span></span>  
 <span data-ttu-id="78e4f-107">Validieren Sie XML-Dokumente und erhalten Sie eine umfangreiche Fehlerausgabe durch die Aktivierung der Eigenschaft `ValidationDetails` des XML-Tasks.</span><span class="sxs-lookup"><span data-stu-id="78e4f-107">Validate XML documents and get rich error output by enabling the `ValidationDetails` property of the XML Task.</span></span> <span data-ttu-id="78e4f-108">Bevor die Eigenschaft `ValidationDetails` verfügbar war, gab die XML-Validierung durch den XML-Task nur „true“ oder „false“ als Ergebnis zurück, ohne Informationen zu Fehlern oder wo diese auftraten.</span><span class="sxs-lookup"><span data-stu-id="78e4f-108">Before the `ValidationDetails` property was available, XML validation by the XML Task returned only a true or false result, with no information about errors or their locations.</span></span> <span data-ttu-id="78e4f-109">Wenn Sie jetzt die Eigenschaft `ValidationDetails` auf „true“ festlegen, enthält die Ausgabedatei ausführliche Informationen zu jedem Fehler, einschließlich der Zeilennummer und der Position.</span><span class="sxs-lookup"><span data-stu-id="78e4f-109">Now, when you set `ValidationDetails` to true, the output file contains detailed information about every error including the line number and the position.</span></span> <span data-ttu-id="78e4f-110">Sie können diese Informationen verwenden, um Fehler in XML-Dokumenten zu verstehen, zu finden und zu beheben.</span><span class="sxs-lookup"><span data-stu-id="78e4f-110">You can use this information to understand, locate, and fix errors in XML documents.</span></span> <span data-ttu-id="78e4f-111">Weitere Informationen finden Sie unter [Validate XML with the XML Task](control-flow/xml-task.md).</span><span class="sxs-lookup"><span data-stu-id="78e4f-111">For more info, see [Validate XML with the XML Task](control-flow/xml-task.md).</span></span>  
  
 [!INCLUDE[ssIS](../includes/ssis-md.md)] <span data-ttu-id="78e4f-112">führte die Eigenschaft `ValidationDetails` im [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] Service Pack 2 ein.</span><span class="sxs-lookup"><span data-stu-id="78e4f-112">introduced the `ValidationDetails` property in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] Service Pack 2.</span></span> <span data-ttu-id="78e4f-113">Diese neue Eigenschaft wurde zu diesem Zeitpunkt nicht angekündigt oder dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="78e4f-113">This new property was not announced or documented at that time.</span></span> <span data-ttu-id="78e4f-114">Die Eigenschaft `ValidationDetails` ist auch in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] und in SQL Server 2016 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="78e4f-114">The `ValidationDetails` property is also available in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] and in SQL Server 2016.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78e4f-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="78e4f-115">See Also</span></span>  
 [<span data-ttu-id="78e4f-116">Von den Editionen von SQL Server 2014 unterstützte Features</span><span class="sxs-lookup"><span data-stu-id="78e4f-116">Features Supported by the Editions of SQL Server 2014</span></span>](../getting-started/features-supported-by-the-editions-of-sql-server-2014.md)  
  
  
