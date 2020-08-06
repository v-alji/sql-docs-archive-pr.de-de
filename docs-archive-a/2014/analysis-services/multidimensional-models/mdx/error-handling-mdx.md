---
title: Fehlerbehandlung (MDX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- scripts [MDX], exceptions
- exceptions [MDX]
ms.assetid: bc6ff0af-9fe6-44d6-bc3c-801d71ea41a9
author: minewiskan
ms.author: owend
ms.openlocfilehash: 357194b9f789fdeacfb65ce3c894d4747867eafb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620617"
---
# <a name="error-handling-mdx"></a><span data-ttu-id="2a440-102">Fehlerbehandlung (MDX)</span><span class="sxs-lookup"><span data-stu-id="2a440-102">Error Handling (MDX)</span></span>
  <span data-ttu-id="2a440-103">Jeder Cube kann steuern, wie Fehler in einem MDX-Skript (Multidimensional Expressions) behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="2a440-103">Each cube can control how errors within a Multidimensional Expressions (MDX) script are handled.</span></span> <span data-ttu-id="2a440-104">Die Fehlerbehandlung erfolgt über den `ScriptErrorHandlingMode`-Enumerator.</span><span class="sxs-lookup"><span data-stu-id="2a440-104">Error handling is done through the `ScriptErrorHandlingMode` enumerator.</span></span> <span data-ttu-id="2a440-105">Für diesen Enumerator sind folgende Werte möglich:</span><span class="sxs-lookup"><span data-stu-id="2a440-105">The possible values for this enumerator are:</span></span>  
  
 `IgnoreNone`  
 <span data-ttu-id="2a440-106">Bewirkt, dass der Server einen Fehler auslöst, wenn [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] einen beliebigen Fehler im MDX-Skript findet.</span><span class="sxs-lookup"><span data-stu-id="2a440-106">Causes the server to raise an error when [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] finds any error in the MDX script.</span></span>  
  
 `IgnoreAll`  
 <span data-ttu-id="2a440-107">Veranlasst den Server dazu, alle Befehle im MDX-Skript zu ignorieren, die einen Fehler (Syntaxfehler, Fehler bei der Namensauflösung usw.) enthalten.</span><span class="sxs-lookup"><span data-stu-id="2a440-107">Causes the server to ignore all commands in the MDX script that contain an error, including syntax errors, name resolution errors, and more.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a440-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2a440-108">See Also</span></span>  
 <xref:Microsoft.AnalysisServices.Cube.ScriptErrorHandlingMode%2A>  
  
  
