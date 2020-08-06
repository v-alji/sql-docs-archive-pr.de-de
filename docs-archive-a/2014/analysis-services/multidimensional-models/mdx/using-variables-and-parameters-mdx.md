---
title: Verwenden von Variablen und Parametern (MDX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- parameters [MDX]
- queries [MDX], variables
- queries [MDX], parameters
- variables [MDX]
ms.assetid: a4754d16-d9c4-49f6-9be0-392180b912e4
author: minewiskan
ms.author: owend
ms.openlocfilehash: fd01cf78ea5e3284aa51cad7dc848176a5dc9298
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721889"
---
# <a name="using-variables-and-parameters-mdx"></a><span data-ttu-id="e2dd4-102">Verwenden von Variablen und Parametern (MDX)</span><span class="sxs-lookup"><span data-stu-id="e2dd4-102">Using Variables and Parameters (MDX)</span></span>
  <span data-ttu-id="e2dd4-103">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] können Sie eine MDX-Anweisung (Multidimensional Expressions) parametrisieren.</span><span class="sxs-lookup"><span data-stu-id="e2dd4-103">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], you can parameterize a Multidimensional Expressions (MDX) statement.</span></span> <span data-ttu-id="e2dd4-104">Eine parametrisierte Anweisung ermöglicht Ihnen das Erstellen von allgemeinen Anweisungen, die während der Laufzeit angepasst werden können.</span><span class="sxs-lookup"><span data-stu-id="e2dd4-104">A parameterized statement lets you create generic statements that can be customized at runtime.</span></span>  
  
 <span data-ttu-id="e2dd4-105">Beim Erstellen einer parametrisierten Anweisung kennzeichnen Sie den Parameternamen, indem Sie dem Namen das @-Zeichen voranstellen.</span><span class="sxs-lookup"><span data-stu-id="e2dd4-105">In creating a parameterized statement, you identify the parameter name by prefixing the name with the at sign (@).</span></span> <span data-ttu-id="e2dd4-106">Beispielsweise @Year wäre ein gültiger Parameter Name.</span><span class="sxs-lookup"><span data-stu-id="e2dd4-106">For example, @Year would be a valid parameter name</span></span>  
  
 <span data-ttu-id="e2dd4-107">MDX unterstützt Parameter nur für Literal- oder skalare Werte.</span><span class="sxs-lookup"><span data-stu-id="e2dd4-107">MDX supports only parameters for literal or scalar values.</span></span> <span data-ttu-id="e2dd4-108">Zum Erstellen eines Parameters, der auf ein Element, eine Menge oder ein Tupel verweist, müssen Sie eine Funktion verwenden (z. B. [StrToMember](/sql/mdx/strtomember-mdx) oder [StrToSet](/sql/mdx/strtoset-mdx)).</span><span class="sxs-lookup"><span data-stu-id="e2dd4-108">To create a parameter that references a member, set, or tuple, you would have to use a function such as [StrToMember](/sql/mdx/strtomember-mdx) or [StrToSet](/sql/mdx/strtoset-mdx).</span></span>  
  
 <span data-ttu-id="e2dd4-109">Im folgenden XML for Analysis (XMLA)-Beispiel enthält der- @CountryName Parameter das Land, für das Kundendaten abgerufen werden:</span><span class="sxs-lookup"><span data-stu-id="e2dd4-109">In the following XML for Analysis (XMLA) example, the @CountryName parameter will contain the country for which customer data is retrieved:</span></span>  
  
```  
<Envelope xmlns="http://schemas.xmlsoap.org/soap/envelope/">  
  <Body>  
    <Execute xmlns="urn:schemas-microsoft-com:xml-analysis">  
      <Command>  
        <Statement>  
select [Measures].members on 0,   
       Filter(Customer.[Customer Geography].Country.members,   
              Customer.[Customer Geography].CurrentMember.Name =  
              @CountryName) on 1  
from [Adventure Works]  
</Statement>  
      </Command>  
      <Properties />  
      <Parameters>  
        <Parameter>  
          <Name>CountryName</Name>  
          <Value>'United Kingdom'</Value>  
        </Parameter>  
      </Parameters>  
    </Execute>  
  </Body>  
</Envelope>  
```  
  
 <span data-ttu-id="e2dd4-110">Wenn Sie diese Funktionalität mit OLE DB verwenden möchten, verwenden Sie die `ICommandWithParameters`-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="e2dd4-110">To use this functionality with OLE DB, you would use the `ICommandWithParameters` interface.</span></span> <span data-ttu-id="e2dd4-111">Wenn Sie diese Funktionalität mit ADOMD.Net verwenden möchten, verwenden Sie die **AdomdCommand.Parameters** -Auflistung.</span><span class="sxs-lookup"><span data-stu-id="e2dd4-111">To use this functionality with ADOMD.Net, you would use the **AdomdCommand.Parameters** collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2dd4-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e2dd4-112">See Also</span></span>  
 [<span data-ttu-id="e2dd4-113">Grundlegendes zu MDX-Skripts &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="e2dd4-113">MDX Scripting Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-scripting-fundamentals-analysis-services.md)  
  
  
