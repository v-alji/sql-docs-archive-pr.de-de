---
title: Abfrageparameter (Dialogfeld) (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdtsql.chm:69645
- vdt.dlgbox.definequeryparameters
ms.assetid: 31cdaee2-d7cd-4d64-a45f-924b27e8b1f0
author: stevestein
ms.author: sstein
ms.openlocfilehash: 76052876ad2899fc959aa7fc49f4299e08bac713
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697362"
---
# <a name="query-parameters-dialog-box-visual-database-tools"></a><span data-ttu-id="601ef-102">Abfrageparameter (Dialogfeld) (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="601ef-102">Query Parameters Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="601ef-103">In diesem Dialogfeld können Sie Werte für in der Abfrage definierte Parameter eingeben.</span><span class="sxs-lookup"><span data-stu-id="601ef-103">This dialog allows you to enter values for the parameters defined in the query.</span></span> <span data-ttu-id="601ef-104">Dieses Dialogfeld wird angezeigt, wenn Sie eine Abfrage mit Parametern ausführen, für die eine Eingabe zur Laufzeit durch die Endbenutzer erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="601ef-104">This dialog box appears when you execute a query that contains parameters that require end-user input at run time.</span></span>  
  
## <a name="options"></a><span data-ttu-id="601ef-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="601ef-105">Options</span></span>  
 <span data-ttu-id="601ef-106">**Name**</span><span class="sxs-lookup"><span data-stu-id="601ef-106">**Name**</span></span>  
 <span data-ttu-id="601ef-107">Listet die Parameter auf, die für die auszuführende Abfrage definiert sind.</span><span class="sxs-lookup"><span data-stu-id="601ef-107">Lists the parameters defined for the query being executed.</span></span> <span data-ttu-id="601ef-108">Wenn die Abfrage benannte Parameter enthält, werden die Namen in der Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="601ef-108">If the query contains named parameters, the names appear in the list.</span></span> <span data-ttu-id="601ef-109">Falls die Abfrage unbenannte Parameter enthält, werden systemdefinierte Namen für die einzelnen Parameter in der Abfrage aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="601ef-109">If the query contains unnamed parameters, system-defined parameter names are listed for each parameter in the query.</span></span>  
  
 <span data-ttu-id="601ef-110">**Wert**</span><span class="sxs-lookup"><span data-stu-id="601ef-110">**Value**</span></span>  
 <span data-ttu-id="601ef-111">Geben Sie den Wert für jeden Parameter ein, der unter **Name**aufgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="601ef-111">Enter the value for each parameter listed under **Name**.</span></span> <span data-ttu-id="601ef-112">Der zuletzt verwendete Wert wird als Standardparameterwert angezeigt.</span><span class="sxs-lookup"><span data-stu-id="601ef-112">The value used most recently appears as the default parameter value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="601ef-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="601ef-113">Example</span></span>  
 <span data-ttu-id="601ef-114">Wenn die folgenden Abfrage im SQL-Bereich in der [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Datenbank ausgeführt wird, wird das Dialogfeld Abfrageparameter geöffnet.</span><span class="sxs-lookup"><span data-stu-id="601ef-114">The following query in the SQL Pane, opens the Query Parameters dialog box when executed in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
```  
SELECT   FirstName, LastName  
FROM    Person.Person AS Lastname  
WHERE   (LastName = @Param1);  
```  
  
## <a name="see-also"></a><span data-ttu-id="601ef-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="601ef-115">See Also</span></span>  
 [<span data-ttu-id="601ef-116">Erstellen von Abfragen mit Parametern &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="601ef-116">Query with Parameters &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
