---
title: Analysieren von Daten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- parsing [Integration Services]
- data parsing [Integration Services]
ms.assetid: 8893ea9d-634c-4309-b52c-6337222dcb39
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3bd34cd83351e31313ae96ff5709ec999a60f2f4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615476"
---
# <a name="parsing-data"></a><span data-ttu-id="729cf-102">Analysieren von Daten</span><span class="sxs-lookup"><span data-stu-id="729cf-102">Parsing Data</span></span>
  <span data-ttu-id="729cf-103">Mit Datenflüssen in Paketen werden Daten zwischen heterogenen Datenspeichern extrahiert und geladen, die eine Reihe von standardmäßigen und benutzerdefinierten Datentypen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="729cf-103">Data flows in packages extract and load data between heterogeneous data stores, which may use a variety of standard and custom data types.</span></span> <span data-ttu-id="729cf-104">In einem Datenfluss werden mit [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Quellen Daten extrahiert, Zeichenfolgendaten analysiert und Daten in einen [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Datentyp konvertiert.</span><span class="sxs-lookup"><span data-stu-id="729cf-104">In a data flow, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sources do the work of extracting data, parsing string data, and converting data to an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] data type.</span></span> <span data-ttu-id="729cf-105">Nachfolgende Transformationen können Daten analysieren, um sie in einen anderen Datentyp zu konvertieren oder um Spaltenkopien mit anderen Datentypen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="729cf-105">Subsequent transformations may parse data to convert it to a different data type, or create column copies with different data types.</span></span> <span data-ttu-id="729cf-106">Mit Ausdrücken in Komponenten können außerdem Argumente und Operanden in andere Datentypen umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="729cf-106">Expressions used in components may also cast arguments and operands to different data types.</span></span> <span data-ttu-id="729cf-107">Wenn die Daten in einen Datenspeicher geladen werden, kann schließlich das Ziel die Daten analysieren, um sie in einen vom Ziel verwendeten Datentyp zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="729cf-107">Finally, when the data is loaded into a data store, the destination may parse the data to convert it to a data type that the destination uses.</span></span> <span data-ttu-id="729cf-108">Weitere Informationen finden Sie unter [Integration Services Datentypen](integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="729cf-108">For more information, see [Integration Services Data Types](integration-services-data-types.md).</span></span>  
  
## <a name="types-of-parsing"></a><span data-ttu-id="729cf-109">Analysetypen</span><span class="sxs-lookup"><span data-stu-id="729cf-109">Types of Parsing</span></span>  
 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="729cf-110">stellt zwei Analysemethoden zum Konvertieren von Daten bereit: schnelle Analyse und Standardanalyse.</span><span class="sxs-lookup"><span data-stu-id="729cf-110">provides two types of parsing for converting data: Fast parse and Standard parse.</span></span>  
  
-   <span data-ttu-id="729cf-111">Die schnelle Analyse besteht aus schnellen, einfachen Analyseroutinen, die keine gebietsschemaspezifischen Datentypkonvertierungen unterstützen, sondern nur die am häufigsten verwendeten Datums- und Zeitformate.</span><span class="sxs-lookup"><span data-stu-id="729cf-111">Fast parse is a fast, simple set of parsing routines that does not support locale-specific data type conversions, and supports only the most frequently used date and time formats.</span></span> <span data-ttu-id="729cf-112">Weitere Informationen finden Sie unter [Fast Parse](../fast-parse.md).</span><span class="sxs-lookup"><span data-stu-id="729cf-112">For more information, see [Fast Parse](../fast-parse.md).</span></span>  
  
-   <span data-ttu-id="729cf-113">Die Standardanalyse enthält viele Analyseroutinen, die alle Datentypkonvertierungen der APIs für die automatische Datentypkonvertierung in Oleaut32.dll und Ole2dsip.dll unterstützen.</span><span class="sxs-lookup"><span data-stu-id="729cf-113">Standard parse is a rich set of parsing routines that supports all the data type conversions that are provided by the Automation data type conversion APIs available in Oleaut32.dll and Ole2dsip.dll.</span></span> <span data-ttu-id="729cf-114">Weitere Informationen finden Sie unter [Standard Parse](../standard-parse.md).</span><span class="sxs-lookup"><span data-stu-id="729cf-114">For more information, see [Standard Parse](../standard-parse.md).</span></span>  
  
  
