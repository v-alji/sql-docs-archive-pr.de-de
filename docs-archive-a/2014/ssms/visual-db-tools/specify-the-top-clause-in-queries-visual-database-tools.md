---
title: Angeben der TOP-Klausel in Abfragen (Visual Database Tools)|Microsoft-Dokumente
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- TOP clause, queries
- percentage of rows returned [SQL Server]
- number of rows
- search conditions [SQL Server], TOP clause
- restricting rows returned
- search criteria [SQL Server], limiting rows returned
- inspecting portion of results
- limiting rows returned
- search criteria [SQL Server], TOP clause
ms.assetid: ba7d7c10-9bb3-4d9b-90b0-5fa94ecae59b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8228779703b1bbe3753f1e2728e83b4b5c3a3d17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724329"
---
# <a name="specify-the-top-clause-in-queries-visual-database-tools"></a><span data-ttu-id="1ccc3-102">Angeben der TOP-Klausel in Abfragen (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="1ccc3-102">Specify the TOP Clause in Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="1ccc3-103">Die TOP-Klausel gibt nur die ersten *n* oder *n Prozent* Zeilen aus einer Abfrage zurück.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-103">The TOP clause returns only the first *n* or *n percent* rows from a query.</span></span> <span data-ttu-id="1ccc3-104">Mithilfe einer TOP-Klausel können Sie ressourcenschonend nur einen Teil der Ergebnisse anstatt alle Abfrageergebnisse prüfen, um zu ermitteln, ob die Abfrage ordnungsgemäß arbeitet.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-104">The TOP clause is useful when you want to inspect a portion of your results to find out if your query does what you expect it to do, without taking the resources necessary to return all of the query results.</span></span>  
  
### <a name="to-specify-the-top-clause-in-queries"></a><span data-ttu-id="1ccc3-105">So geben Sie die TOP-Klausel in Abfragen an</span><span class="sxs-lookup"><span data-stu-id="1ccc3-105">To specify the TOP clause in queries</span></span>  
  
1.  <span data-ttu-id="1ccc3-106">Öffnen Sie im Projektmappen-Explorer eine Abfrage, oder erstellen Sie eine neue Abfrage.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-106">Open a query from Solution Explorer or create a new one.</span></span>  
  
2.  <span data-ttu-id="1ccc3-107">Klicken Sie im Menü **Ansicht** auf **Eigenschaftenfenster**.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-107">From the **View** menu, click **Properties Window**.</span></span>  
  
3.  <span data-ttu-id="1ccc3-108">Wechseln Sie in **Eigenschaftenfenster**zur Eigenschaft **Oberste Angabe** , und erweitern Sie diese.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-108">In the **Properties Window**, locate and expand the **Top Specification** property.</span></span>  
  
4.  <span data-ttu-id="1ccc3-109">Klicken Sie auf die untergeordnete Eigenschaft **(Oben)** , und legen Sie diese auf **Ja**fest.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-109">Click the **(Top)** child property and set it to **Yes**.</span></span>  
  
5.  <span data-ttu-id="1ccc3-110">Geben Sie in der untergeordneten Eigenschaft **Ausdruck** einen Ausdruck ein, der ein numerisches Ergebnis hat (zum Beispiel „10“ oder „2\*5“).</span><span class="sxs-lookup"><span data-stu-id="1ccc3-110">In the **Expression** child property, type an expression that has a numeric result (for example, "10" or "2\*5").</span></span>  
  
6.  <span data-ttu-id="1ccc3-111">Klicken Sie auf die untergeordnete Eigenschaft **Prozent** , und geben Sie an, ob die Eigenschaft **Ausdruck** als Prozentanteil aller zurückgegebenen Zeilen (Ja) oder als absolute Anzahl von zurückgegebenen Zeilen (Nein) behandelt werden soll.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-111">Click the **Percent** child property and indicate whether or not to treat the **Expression** property as a percentage of all rows returned (Yes) or as the absolute number of rows returned (No).</span></span>  
  
7.  <span data-ttu-id="1ccc3-112">Wenn bei der Abfrage die ORDER BY-Klausel verwendet wird, klicken Sie auf die untergeordnete Eigenschaft **WITH TIES** . Bei Auswahl von **Ja** werden alle Zeilen in einer Gruppe angezeigt, wenn nur ein Teil der Gruppe enthalten ist. Bei Auswahl von **Nein** werden die Zeilen abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-112">If your query uses the ORDER BY clause, click the **With Ties** child property and choose **Yes** to display all rows in a group if only part of the group is included or **No** to truncate them.</span></span>  
  
 <span data-ttu-id="1ccc3-113">Bei der Ausführung dieser Schritte werden Sie feststellen, dass die im SQL-Bereich angezeigte TOP-Klausel entsprechend den aktuellen Einstellungen der Eigenschaften geändert wird.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-113">As you work through the preceding procedure, notice that the TOP clause, displayed in the SQL pane, changes to reflect the current settings of the properties.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1ccc3-114">Sie können außerdem die Werte der untergeordneten Eigenschaften von **Oberste Angabe** ändern, indem Sie die TOP-Klausel im SQL-Bereich bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="1ccc3-114">You can also change the values of the child properties of the **Top Specification** by editing the TOP clause in the SQL pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ccc3-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1ccc3-115">See Also</span></span>  
 <span data-ttu-id="1ccc3-116">[Themen zur Vorgehensweise beim Entwerfen von Abfragen und Sichten &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="1ccc3-116">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="1ccc3-117">Abfrageeigenschaften &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="1ccc3-117">Query Properties &#40;Visual Database Tools&#41;</span></span>](query-properties-visual-database-tools.md)  
  
  
