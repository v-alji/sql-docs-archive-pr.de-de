---
title: Datamining-Abfrage | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dataminingquery.f1
ms.assetid: 948e358a-6245-429f-82c7-4cedc5e048fd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 657e4e173815fa25458e296f7eadb3d4d0696a02
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618854"
---
# <a name="data-mining-query"></a><span data-ttu-id="6580c-102">Data Mining-Abfrage</span><span class="sxs-lookup"><span data-stu-id="6580c-102">Data Mining Query</span></span>
  <span data-ttu-id="6580c-103">Im Entwurfsbereich befindet sich der Data Mining-Generator für Vorhersageabfragen, mit dem Sie Data Mining-Vorhersageabfragen erstellen können.</span><span class="sxs-lookup"><span data-stu-id="6580c-103">The design pane contains the data mining prediction query builder, which you can use to build data mining prediction queries.</span></span> <span data-ttu-id="6580c-104">Vorhersageabfragen können entweder auf der Grundlage von Eingabetabellen oder von SINGLETON-Vorhersageabfragen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="6580c-104">You can design either prediction queries based on input tables, or singleton prediction queries.</span></span> <span data-ttu-id="6580c-105">Wechseln Sie zur Ergebnissicht, um die Abfrage auszuführen und die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6580c-105">Switch to the result view to run the query and view the results.</span></span> <span data-ttu-id="6580c-106">Die Abfragesicht zeigt die vom Generator für Vorhersageabfragen erstellte DMX-Abfrage (Data Mining Extensions).</span><span class="sxs-lookup"><span data-stu-id="6580c-106">The query view displays the Data Mining Extensions (DMX) query created by the prediction query builder.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6580c-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="6580c-107">Options</span></span>  
 <span data-ttu-id="6580c-108">Schaltfläche Ansicht wechseln</span><span class="sxs-lookup"><span data-stu-id="6580c-108">Switch view button</span></span>  
 <span data-ttu-id="6580c-109">Klicken Sie auf ein Symbol, um zwischen dem Entwurfs- und Abfragebereich zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="6580c-109">Click an icon to switch between the design and query pane.</span></span> <span data-ttu-id="6580c-110">Standardmäßig ist der Entwurfsbereich geöffnet.</span><span class="sxs-lookup"><span data-stu-id="6580c-110">By default, the design pane is open.</span></span>  
  
 <span data-ttu-id="6580c-111">Klicken Sie auf das ![Design-Symbol](../media/ssis-designicon.gif "Entwurf (Symbol)"), um in den Entwurfsbereich zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="6580c-111">To switch to the design pane, click the ![Design icon](../media/ssis-designicon.gif "Design icon") icon.</span></span>  
  
 <span data-ttu-id="6580c-112">Klicken Sie auf das ![SQL-Symbol](../media/ssis-queryicon.gif "SQL (Symbol)"), um in den Abfragebereich zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="6580c-112">To switch to the query pane, click the ![SQL icon](../media/ssis-queryicon.gif "SQL icon") icon.</span></span>  
  
 <span data-ttu-id="6580c-113">**Miningmodell**</span><span class="sxs-lookup"><span data-stu-id="6580c-113">**Mining Model**</span></span>  
 <span data-ttu-id="6580c-114">Zeigt das Miningmodell an, auf dem Sie die Vorhersagen aufbauen wollen.</span><span class="sxs-lookup"><span data-stu-id="6580c-114">Displays the selected mining model on which you want to base predictions.</span></span>  
  
 <span data-ttu-id="6580c-115">**Modell auswählen**</span><span class="sxs-lookup"><span data-stu-id="6580c-115">**Select Model**</span></span>  
 <span data-ttu-id="6580c-116">Öffnet das Dialogfeld **Miningmodell auswählen** .</span><span class="sxs-lookup"><span data-stu-id="6580c-116">Opens the **Select Mining Model** dialog box.</span></span>  
  
 <span data-ttu-id="6580c-117">**Eingabespalten**</span><span class="sxs-lookup"><span data-stu-id="6580c-117">**Input Columns**</span></span>  
 <span data-ttu-id="6580c-118">Zeigt die zum Generieren der Vorhersagen ausgewählten Eingabespalten an.</span><span class="sxs-lookup"><span data-stu-id="6580c-118">Displays the selected input columns used to generate the predictions.</span></span>  
  
 <span data-ttu-id="6580c-119">**Quelle**</span><span class="sxs-lookup"><span data-stu-id="6580c-119">**Source**</span></span>  
 <span data-ttu-id="6580c-120">Wählen Sie in der Dropdownliste die Quelle aus, die das Feld enthält, das Sie für die Spalte verwenden wollen.</span><span class="sxs-lookup"><span data-stu-id="6580c-120">Select the source containing the field that you will use for the column from the dropdown list.</span></span> <span data-ttu-id="6580c-121">Sie können entweder das in der **Miningmodell** -Tabelle ausgewählte Miningmodell, die in der **Eingabetabelle(n) auswählen** -Tabelle ausgewählten Eingabetabellen, eine Vorhersagefunktion oder einen benutzerdefinierten Ausdruck verwenden.</span><span class="sxs-lookup"><span data-stu-id="6580c-121">You can either use the mining model selected in the **Mining Model** table, the input table(s) selected in the **Select Input Table(s)** table, a prediction function, or a custom expression.</span></span>  
  
 <span data-ttu-id="6580c-122">Spalten können aus den das Miningmodell enthaltenden Tabellen und den Eingabespalten auf die Zelle gezogen werden.</span><span class="sxs-lookup"><span data-stu-id="6580c-122">Columns can be dragged from the tables containing the mining model and input columns to the cell.</span></span>  
  
 <span data-ttu-id="6580c-123">**Feld**</span><span class="sxs-lookup"><span data-stu-id="6580c-123">**Field**</span></span>  
 <span data-ttu-id="6580c-124">Wählen Sie eine Spalte aus der Liste der aus der Quelltabelle abgeleiteten Spalten aus.</span><span class="sxs-lookup"><span data-stu-id="6580c-124">Select a column from the list of columns derived from the source table.</span></span> <span data-ttu-id="6580c-125">Wenn Sie unter **Quelle** die **Vorhersagefunktion**ausgewählt haben, enthält diese Zelle eine Dropdownliste der für das ausgewählte Miningmodell verfügbaren Vorhersagefunktionen.</span><span class="sxs-lookup"><span data-stu-id="6580c-125">If you selected **Prediction Function** in **Source**, this cell contains a drop-down list of the prediction functions available for the selected mining model.</span></span>  
  
 <span data-ttu-id="6580c-126">**Alias**</span><span class="sxs-lookup"><span data-stu-id="6580c-126">**Alias**</span></span>  
 <span data-ttu-id="6580c-127">Der Name der vom Server zurückgegebenen Spalte.</span><span class="sxs-lookup"><span data-stu-id="6580c-127">The name of the column returned by the server.</span></span>  
  
 <span data-ttu-id="6580c-128">**Anzeigen**</span><span class="sxs-lookup"><span data-stu-id="6580c-128">**Show**</span></span>  
 <span data-ttu-id="6580c-129">Wählen Sie aus, ob die Spalte zurückgegeben oder nur in der WHERE-Klausel verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="6580c-129">Select to return the column or to only use the column in the WHERE clause.</span></span>  
  
 <span data-ttu-id="6580c-130">**Gruppe**</span><span class="sxs-lookup"><span data-stu-id="6580c-130">**Group**</span></span>  
 <span data-ttu-id="6580c-131">Wird mit der **Und/Oder** -Spalte verwendet, um Ausdrücke zu gruppieren.</span><span class="sxs-lookup"><span data-stu-id="6580c-131">Use with the **And/Or** column to group expressions together.</span></span> <span data-ttu-id="6580c-132">Beispielsweise (expr1 OR expr2) AND expr3.</span><span class="sxs-lookup"><span data-stu-id="6580c-132">For example, (expr1 OR expr2) AND expr3.</span></span>  
  
 <span data-ttu-id="6580c-133">**Und/Oder**</span><span class="sxs-lookup"><span data-stu-id="6580c-133">**And/Or**</span></span>  
 <span data-ttu-id="6580c-134">Wird zum Erstellen einer logischen Abfrage verwendet.</span><span class="sxs-lookup"><span data-stu-id="6580c-134">Use to create a logical query.</span></span> <span data-ttu-id="6580c-135">Beispielsweise (expr1 OR expr2) AND expr3.</span><span class="sxs-lookup"><span data-stu-id="6580c-135">For example, (expr1 OR expr2) AND expr3.</span></span>  
  
 <span data-ttu-id="6580c-136">**Kriterium/Argument**</span><span class="sxs-lookup"><span data-stu-id="6580c-136">**Criteria/Argument**</span></span>  
 <span data-ttu-id="6580c-137">Geben Sie eine Bedingung oder einen benutzerdefinierten Ausdruck an, der auf die Spalte angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="6580c-137">Specify a condition or user expression that applies to the column.</span></span> <span data-ttu-id="6580c-138">Spalten können aus den das Miningmodell enthaltenden Tabellen und den Eingabespalten auf die Zelle gezogen werden.</span><span class="sxs-lookup"><span data-stu-id="6580c-138">Columns can be dragged from the tables containing the mining model and input columns to the cell.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6580c-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6580c-139">See Also</span></span>  
 <span data-ttu-id="6580c-140">[Schnittstellen für Data Mining-Abfragen](https://docs.microsoft.com/analysis-services/data-mining/data-mining-query-tools) </span><span class="sxs-lookup"><span data-stu-id="6580c-140">[Data Mining Query Interfaces](https://docs.microsoft.com/analysis-services/data-mining/data-mining-query-tools) </span></span>  
 [<span data-ttu-id="6580c-141">Data Mining-Erweiterungen &#40;DMX&#41; – Anweisungsreferenz</span><span class="sxs-lookup"><span data-stu-id="6580c-141">Data Mining Extensions &#40;DMX&#41; Statement Reference</span></span>](/sql/dmx/data-mining-extensions-dmx-statements)  
  
  
