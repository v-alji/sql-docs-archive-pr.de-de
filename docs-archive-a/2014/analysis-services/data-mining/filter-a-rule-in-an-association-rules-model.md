---
title: Filtern einer Regel in einem Zuordnungs Regel Modell | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- filtering rules [Analysis Services]
- Mining Model Viewer [Analysis Services], rules
- Rules Viewer
ms.assetid: 26cdba5b-5bf1-439e-80a3-8759774e918b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3c904713acc6eaf132e7cb1195186165f21d971a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619451"
---
# <a name="filter-a-rule-in-an-association-rules-model"></a><span data-ttu-id="9514b-102">Filtern einer Regel in einem Zuordnungsregelmodell</span><span class="sxs-lookup"><span data-stu-id="9514b-102">Filter a Rule in an Association Rules Model</span></span>
  <span data-ttu-id="9514b-103">Sie können Filterung mit Zuordnungsmodellen verwenden, um die Ergebnisse auf die Zuordnungen zu beschränken, die für Sie von Interesse sind.</span><span class="sxs-lookup"><span data-stu-id="9514b-103">You can use filtering with association models to restrict the results to just the associations that interest you.</span></span> <span data-ttu-id="9514b-104">Zum Beispiel können Sie die Regeln filtern, damit nur die Ergebnisse angezeigt werden, die ein bestimmtes Produkt enthalten.</span><span class="sxs-lookup"><span data-stu-id="9514b-104">For example, you might filter the rules to show only those that include a specific product.</span></span>  
  
 <span data-ttu-id="9514b-105">Im Data Mining-Designer verwenden Sie die Steuerelemente auf der Registerkarte **Regeln** des [!INCLUDE[msCoName](../../includes/msconame-md.md)] -Zuordnungsregeln-Viewers, um die angezeigten Regeln zu filtern.</span><span class="sxs-lookup"><span data-stu-id="9514b-105">In Data Mining Designer, you use the controls on the **Rules** tab of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association Rules Viewer to filter the rules that are displayed.</span></span>  <span data-ttu-id="9514b-106">Sie können auch eine Abfrage für das Modell erstellen, um nur Itemsets anzuzeigen, die einen bestimmten Wert enthalten.</span><span class="sxs-lookup"><span data-stu-id="9514b-106">You can also create a query on the model to see only itemset that contains a particular value.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9514b-107">Diese Option ist nur für Miningmodelle verfügbar, die mit dem Microsoft Association-Algorithmus erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="9514b-107">This option is available only for mining models that have been created by using the Microsoft Association Algorithm.</span></span>  
  
### <a name="filter-a-rule-in-an-association-model"></a><span data-ttu-id="9514b-108">Filtern einer Regel in einem Zuordnungsmodell</span><span class="sxs-lookup"><span data-stu-id="9514b-108">Filter a rule in an association model</span></span>  
  
1.  <span data-ttu-id="9514b-109">Öffnen Sie das Miningmodell mit dem **Zuordnungsregeln-Viewer**.</span><span class="sxs-lookup"><span data-stu-id="9514b-109">Open the mining model by using the **Association Rules Viewer**.</span></span> <span data-ttu-id="9514b-110">In SQL Server Management Studio müssen Sie hierzu mit der rechten Maustaste auf den Modellnamen klicken und **Durchsuchen**auswählen.</span><span class="sxs-lookup"><span data-stu-id="9514b-110">To do this in SQL Server Management Studio, right click the model name and select **Browse**.</span></span> <span data-ttu-id="9514b-111">Doppelklicken Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]auf die Miningstruktur, die das Modell enthält, und klicken Sie anschließend auf die Registerkarte **Miningmodell-Viewer** im **Data Mining-Designer**.</span><span class="sxs-lookup"><span data-stu-id="9514b-111">To do this in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], double-click the mining structure that contains the model, and then click the **Mining Model Viewer** tab of **Data Mining Designer**.</span></span>  
  
2.  <span data-ttu-id="9514b-112">Klicken Sie im **Zuordnungsregeln-Viewer** auf die Registerkarte **Regeln**.</span><span class="sxs-lookup"><span data-stu-id="9514b-112">Click the **Rules** tab of the **Association Rules Viewer**.</span></span>  
  
3.  <span data-ttu-id="9514b-113">Geben Sie in das Feld **Filterregel** eine Regelbedingung ein.</span><span class="sxs-lookup"><span data-stu-id="9514b-113">Type a rule condition into the **Filter Rule** box.</span></span> <span data-ttu-id="9514b-114">Eine Regelbedingung könnte z. B. "Bike Stand" sein, die auch "Bike Stands" zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="9514b-114">For example, a rule condition might be "Bike Stand", which also returns "Bike Stands".</span></span>  
  
     <span data-ttu-id="9514b-115">Das Textfeld **Filterregel** unterstützt reguläre Ausdrücke, wie diese von der .NET-Sprache definiert werden.</span><span class="sxs-lookup"><span data-stu-id="9514b-115">The **Filter Rule** text box supports regular expressions as defined by the .NET language.</span></span> <span data-ttu-id="9514b-116">Daher können Sie z. B. folgende Ausdrücke verwenden: `((.Helmets.*Fenders.*)|(.*Fenders.*Helmets.*))`.</span><span class="sxs-lookup"><span data-stu-id="9514b-116">Therefore, you can use expressions such as the following: `((.Helmets.*Fenders.*)|(.*Fenders.*Helmets.*))`.</span></span> <span data-ttu-id="9514b-117">Dieser Ausdruck gibt alle Itemsets zurück, die Attribute mit den Wörtern Helmets und Fenders in beliebiger Reihenfolge enthalten.</span><span class="sxs-lookup"><span data-stu-id="9514b-117">This expression would return any itemsets that include attributes with the words Helmets and Fenders, in any order.</span></span>  
  
4.  <span data-ttu-id="9514b-118">Erhöhen Sie unter **Minimale Wahrscheinlichkeit**den Wert für die Wahrscheinlichkeit, um mehr Regeln anzuzeigen, und verringern Sie den Wert, um weniger Regeln anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9514b-118">For **Minimum probability**, increase the value of probability to see fewer rules, or decrease the value to see more rules.</span></span>  
  
5.  <span data-ttu-id="9514b-119">Erhöhen Sie unter **Minimale Wichtigkeit**den Wert für die Wichtigkeit, um mehr Regeln anzuzeigen, und verringern Sie den Wert, um weniger Regeln anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9514b-119">For **Minimum importance**, increase the value of importance to see fewer rules, or decrease the value to see more rules.</span></span>  
  
6.  <span data-ttu-id="9514b-120">Wählen Sie für **Anzeigen**eine der folgenden Optionen aus: **Attributnamen und Wert anzeigen**, **Nur Attributnamen anzeigen**oder **Nur Attributwert anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="9514b-120">For **Show**, select one of the following options: **Show attribute name and value**, **Show attribute name only**, or **Show attribute value only**.</span></span>  
  
7.  <span data-ttu-id="9514b-121">Erhöhen Sie den Wert für **Maximale Zeilenanzahl**, um die Gesamtzahl von Regeln zu erhöhen, die die angegebenen Bedingungen erfüllen, oder verringern Sie den Wert, um die Anzahl der zurückgegebenen Regeln zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="9514b-121">For **Maximum rows**, increase the value to increase the total number of rules that meet the specified conditions, or decrease the value to limit the number of rules returned.</span></span> <span data-ttu-id="9514b-122">Regeln werden nach Wahrscheinlichkeit sortiert. Daher können Sie zusätzliche Regeln ausschließen, die die angegebenen Bedingungen für Wahrscheinlichkeit oder Wichtigkeit erfüllen.</span><span class="sxs-lookup"><span data-stu-id="9514b-122">Rules are ordered by probability, so you might eliminate additional rules that meet the specified conditions for probability or importance.</span></span>  
  
8.  <span data-ttu-id="9514b-123">Aktivieren oder deaktivieren Sie das Kontrollkästchen **Langen Namen anzeigen** , um umzuschalten, wie die Namen der Regeln angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="9514b-123">Select or deselect the **Show long name** check box to toggle the way that the rules names are displayed.</span></span>  
  
     <span data-ttu-id="9514b-124">Die Regeln werden daraufhin gefiltert und es werden nur Regeln angezeigt, die das angegebene Element enthalten.</span><span class="sxs-lookup"><span data-stu-id="9514b-124">The rules are now filtered to only display rules that contain the indicated item.</span></span> <span data-ttu-id="9514b-125">Die Filterbedingung gilt für Attributwerte, die entweder vor oder nach dem Regeltrennzeichen "->" stehen.</span><span class="sxs-lookup"><span data-stu-id="9514b-125">The filter condition applies to attribute values either before or after the rule delimiter, "->".</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9514b-126">Der Viewer speichert die ursprüngliche Liste der Regeln basierend auf einer Abfrage des Miningmodells und aktualisiert die Liste der Regeln nur, wenn Sie die Bedingungen für die Abfrage ändern, indem Sie die maximale Zeilenanzahl, die Wahrscheinlichkeit, die Wichtigkeit oder die Anzeige langer Namen festlegen.</span><span class="sxs-lookup"><span data-stu-id="9514b-126">The viewer caches the initial list of rules, based on a query to the mining model, and does not refresh the list of rules unless you change the conditions of the query by setting the maximum rows, the probability, importance, or the display of long names.</span></span> <span data-ttu-id="9514b-127">Wenn Sie eine Bedingung eingeben und die Anzeige nicht sofort aktualisiert wird, können Sie im Viewer daher eine Aktualisierung der Daten erzwingen, indem Sie das Kontrollkästchen **Langen Namen anzeigen** aktivieren und anschließend wieder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="9514b-127">Therefore, if you type a condition and the display does not immediately refresh, you can force the viewer to refresh the data by selecting and then deselecting the **Show long names** check box.</span></span>  
  
### <a name="create-a-query-on-the-itemsets-in-an-association-model"></a><span data-ttu-id="9514b-128">Erstellen einer Abfrage in den Itemsets in einem Zuordnungsmodell</span><span class="sxs-lookup"><span data-stu-id="9514b-128">Create a query on the itemsets in an association model</span></span>  
  
-   [<span data-ttu-id="9514b-129">Beispiele für Zuordnungsmodellabfragen</span><span class="sxs-lookup"><span data-stu-id="9514b-129">Association Model Query Examples</span></span>](association-model-query-examples.md)  
  
## <a name="see-also"></a><span data-ttu-id="9514b-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9514b-130">See Also</span></span>  
 <span data-ttu-id="9514b-131">[Tasks und Anleitungen des Mining Modell-Viewers](mining-model-viewer-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="9514b-131">[Mining Model Viewer Tasks and How-tos](mining-model-viewer-tasks-and-how-tos.md) </span></span>  
 <span data-ttu-id="9514b-132">[Durchsuchen eines Modells mit dem Microsoft Association Rules-Viewer](browse-a-model-using-the-microsoft-association-rules-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="9514b-132">[Browse a Model Using the Microsoft Association Rules Viewer](browse-a-model-using-the-microsoft-association-rules-viewer.md) </span></span>  
 [<span data-ttu-id="9514b-133">Lektion 3: Erstellen eines Warenkorbszenarios &#40;Data Mining-Tutorial für Fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="9514b-133">Lesson 3: Building a Market Basket Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../tutorials/lesson-3-building-a-market-basket-scenario-intermediate-data-mining-tutorial.md)  
  
  
