---
title: Ändern des Timeout Werts für Data Mining-Abfragen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- time-out
ms.assetid: f1add4bc-e882-440a-a98b-333cfa274c3e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9dcdcdcbb6e2aef48dd8725f10f38180c73f5f6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619461"
---
# <a name="change-the-time-out-value-for-data-mining-queries"></a><span data-ttu-id="98b64-102">Ändern des Timeoutwerts für Data Mining-Abfragen</span><span class="sxs-lookup"><span data-stu-id="98b64-102">Change the Time-out Value for Data Mining Queries</span></span>
  <span data-ttu-id="98b64-103">Wenn Sie ein Prognosegütediagramm erstellen oder eine Vorhersageabfrage ausführen, kann es viel Zeit in Anspruch nehmen, alle für die Vorhersage erforderlichen Daten zu generieren.</span><span class="sxs-lookup"><span data-stu-id="98b64-103">When you build a lift chart or execute a prediction query, sometimes it can take a long time to generate all the data required for the prediction.</span></span> <span data-ttu-id="98b64-104">Um ein Timeout der Abfrage zu verhindern, können Sie den Wert ändern, der festlegt, wie lange der [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Server auf den Abschluss einer Abfrage wartet.</span><span class="sxs-lookup"><span data-stu-id="98b64-104">To prevent the query from timing out, you can change the value that controls how long the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] server waits to complete a query.</span></span>  
  
 <span data-ttu-id="98b64-105">Der Standardwert ist 15. Wenn Ihre Modelle komplex sind oder die Datenquelle umfangreich ist, reicht dies unter Umständen nicht aus.</span><span class="sxs-lookup"><span data-stu-id="98b64-105">The default value is 15; however, if your models are complex or the data source is large, this might not be enough.</span></span> <span data-ttu-id="98b64-106">Bei Bedarf können Sie den Wert heraufsetzen, um genügend Zeit für die Verarbeitung bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="98b64-106">If necessary, you can increase the value significantly, to enable enough time for processing.</span></span> <span data-ttu-id="98b64-107">Beispiel: wenn Sie **Abfragetimeout** auf 600 setzen, kann die Abfrage bis zu 10 Minuten lang ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="98b64-107">For example, if you set **Query Timeout** to 600, the query could continue to run for up to 10 minutes.</span></span>  
  
 <span data-ttu-id="98b64-108">Weitere Informationen zu Vorhersageabfragen finden Sie unter [Data Mining-Abfragetasks und Anweisungen](data-mining-query-tasks-and-how-tos.md).</span><span class="sxs-lookup"><span data-stu-id="98b64-108">For more information about prediction queries, see [Data Mining Query Tasks and How-tos](data-mining-query-tasks-and-how-tos.md).</span></span>  
  
### <a name="configure-the-time-out-value-for-data-mining-queries"></a><span data-ttu-id="98b64-109">Konfigurieren des Timeoutwerts für Data Mining-Abfragen</span><span class="sxs-lookup"><span data-stu-id="98b64-109">Configure the time-out value for data mining queries</span></span>  
  
1.  <span data-ttu-id="98b64-110">Klicken Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]im Menü **Extras** auf **Optionen**.</span><span class="sxs-lookup"><span data-stu-id="98b64-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], from the **Tools** menu, selection **Options**.</span></span>  
  
2.  <span data-ttu-id="98b64-111">Erweitern Sie im Bereich **Optionen\*\*\*\*Business Intelligence-Designer**.</span><span class="sxs-lookup"><span data-stu-id="98b64-111">In the **Options** pane, expand **Business Intelligence Designers**.</span></span>  
  
3.  <span data-ttu-id="98b64-112">Klicken Sie auf das Textfeld **Abfragetimeout** , und geben Sie einen Wert für die Anzahl der Sekunden ein.</span><span class="sxs-lookup"><span data-stu-id="98b64-112">Click the **Query Timeout** text box, and type a value for the number of seconds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98b64-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="98b64-113">See Also</span></span>  
 <span data-ttu-id="98b64-114">[Data Mining-Abfrage Tasks und Anleitungen](data-mining-query-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="98b64-114">[Data Mining Query Tasks and How-tos](data-mining-query-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="98b64-115">Data Mining-Abfragen</span><span class="sxs-lookup"><span data-stu-id="98b64-115">Data Mining Queries</span></span>](data-mining-queries.md)  
  
  
