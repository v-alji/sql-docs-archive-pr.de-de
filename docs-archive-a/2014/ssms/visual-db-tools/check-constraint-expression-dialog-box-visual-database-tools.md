---
title: CHECK-Einschränkungsausdruck (Dialogfeld) (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.checkconstraintexpression
ms.assetid: beb6ce43-3913-4d66-8826-8e885335b790
author: stevestein
ms.author: sstein
ms.openlocfilehash: 38268d4e49a9c674c100bc22c0782e3e61477967
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607495"
---
# <a name="check-constraint-expression-dialog-box-visual-database-tools"></a><span data-ttu-id="31e84-102">CHECK-Einschränkungsausdruck (Dialogfeld) (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="31e84-102">Check Constraint Expression Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="31e84-103">Wenn Sie eine CHECK-Einschränkung einer Tabelle oder Spalte anfügen, müssen Sie einen SQL-Ausdruck einschließen.</span><span class="sxs-lookup"><span data-stu-id="31e84-103">When you attach a check constraint to a table or column, you must include an SQL expression.</span></span> <span data-ttu-id="31e84-104">Geben Sie den CHECK-Einschränkungsausdruck in das zur Verfügung gestellte Feld ein.</span><span class="sxs-lookup"><span data-stu-id="31e84-104">Type the check constraint expression in the box provided.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="31e84-105">Liste der Benutzeroberflächenelemente</span><span class="sxs-lookup"><span data-stu-id="31e84-105">UI element list</span></span>  
 <span data-ttu-id="31e84-106">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="31e84-106">Expression</span></span>  
 <span data-ttu-id="31e84-107">Geben Sie den Ausdruck ein.</span><span class="sxs-lookup"><span data-stu-id="31e84-107">Enter the expression</span></span>  
  
 <span data-ttu-id="31e84-108">Sie können einen einfachen Einschränkungsausdruck erstellen, um Daten auf eine einfache Bedingung zu prüfen. Sie können aber auch einen komplexen Ausdruck mithilfe boolescher Operatoren erstellen, um Daten auf mehrere Bedingungen zu prüfen.</span><span class="sxs-lookup"><span data-stu-id="31e84-108">You can create a simple constraint expression to check data for a simple condition; or you can create a complex expression, using Boolean operators, to check data for several conditions.</span></span> <span data-ttu-id="31e84-109">Angenommen, die authors-Tabelle enthält eine zip-Spalte, in die nur Zeichenfolgen aus 5 Ziffern eingegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="31e84-109">For example, suppose the authors table has a zip column where a 5-digit character string is required.</span></span> <span data-ttu-id="31e84-110">Der folgende Einschränkungsausdruck stellt sicher, dass nur fünfstellige Zahlen zulässig sind:</span><span class="sxs-lookup"><span data-stu-id="31e84-110">This sample constraint expression guarantees that only 5-digit numbers are allowed:</span></span>  
  
```  
zip LIKE '[0-9][0-9][0-9][0-9][0-9]'  
```  
  
 <span data-ttu-id="31e84-111">Angenommen, die Tabelle sales enthält die Spalte qty, für die ein Wert größer als 0 erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="31e84-111">Or suppose the sales table has a column called qty which requires a value greater than 0.</span></span> <span data-ttu-id="31e84-112">Die folgende Einschränkung stellt sicher, dass nur positive Werte zulässig sind:</span><span class="sxs-lookup"><span data-stu-id="31e84-112">This sample constraint guarantees that only positive values are allowed:</span></span>  
  
```  
qty > 0  
```  
  
 <span data-ttu-id="31e84-113">Ein weiteres Beispiel: Die orders-Tabelle schränkt die Art der Kreditkarten ein, die für Kreditkartenaufträge akzeptiert werden.</span><span class="sxs-lookup"><span data-stu-id="31e84-113">Or suppose the orders table limits the type of credit cards accepted for all credit card orders.</span></span> <span data-ttu-id="31e84-114">Die folgende Einschränkung stellt sicher, dass nur Visa-, MasterCard- oder American Express-Kreditkarten akzeptiert werden, wenn als Zahlungsmittel für den Auftrag eine Kreditkarte verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="31e84-114">This sample constraint guarantees that if the order is placed on a credit card, then only Visa, MasterCard, or American Express is accepted:</span></span>  
  
```  
NOT (payment_method = 'credit card') OR  
   (card_type IN ('VISA', 'MASTERCARD', 'AMERICAN EXPRESS'))  
```  
  
## <a name="to-define-a-constraint-expression"></a><span data-ttu-id="31e84-115">So definieren Sie einen Einschränkungsausdruck</span><span class="sxs-lookup"><span data-stu-id="31e84-115">To define a constraint expression</span></span>  
 <span data-ttu-id="31e84-116">Geben Sie auf der Registerkarte Einschränkungen überprüfen der Eigenschaftenseiten einen Ausdruck in das Feld Einschränkungsausdruck ein. Verwenden Sie dabei die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="31e84-116">In the Check Constraints tab of the property pages, type an expression in the Constraint expression box using the following syntax:</span></span>  
  
 `{constant | column_name | function | (subquery)}`  
  
 `[{operator | AND | OR | NOT}`  
  
 `{constant | column_name | function | (subquery)}...]`  
  
 <span data-ttu-id="31e84-117">Die SQL-Syntax besteht aus folgenden Parametern:</span><span class="sxs-lookup"><span data-stu-id="31e84-117">The SQL syntax is made up of the following parameters:</span></span>  
  
|<span data-ttu-id="31e84-118">Parameter</span><span class="sxs-lookup"><span data-stu-id="31e84-118">Parameter</span></span>|<span data-ttu-id="31e84-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="31e84-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="31e84-120">Konstante</span><span class="sxs-lookup"><span data-stu-id="31e84-120">constant</span></span>|<span data-ttu-id="31e84-121">Ein Literalwert, wie numerische Daten oder Zeichendaten.</span><span class="sxs-lookup"><span data-stu-id="31e84-121">A literal value, such as numeric or character data.</span></span> <span data-ttu-id="31e84-122">Zeichendaten müssen in einfache Anführungszeichen (') eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="31e84-122">Character data must be enclosed within single quotation marks (').</span></span>|  
|<span data-ttu-id="31e84-123">column_name</span><span class="sxs-lookup"><span data-stu-id="31e84-123">column_name</span></span>|<span data-ttu-id="31e84-124">Gibt eine Spalte an.</span><span class="sxs-lookup"><span data-stu-id="31e84-124">Specifies a column.</span></span>|  
|<span data-ttu-id="31e84-125">Funktion</span><span class="sxs-lookup"><span data-stu-id="31e84-125">function</span></span>|<span data-ttu-id="31e84-126">Eine integrierte Funktion.</span><span class="sxs-lookup"><span data-stu-id="31e84-126">A built-in function.</span></span>|  
|<span data-ttu-id="31e84-127">Operator</span><span class="sxs-lookup"><span data-stu-id="31e84-127">operator</span></span>|<span data-ttu-id="31e84-128">Arithmetischer oder bitweiser Operator bzw. ein Vergleichs- oder Zeichenfolgenoperator.</span><span class="sxs-lookup"><span data-stu-id="31e84-128">Arithmetic, bitwise, comparison, or string operators.</span></span>|  
|<span data-ttu-id="31e84-129">AND</span><span class="sxs-lookup"><span data-stu-id="31e84-129">AND</span></span>|<span data-ttu-id="31e84-130">Wird in booleschen Ausdrücken verwendet, um zwei Ausdrücke miteinander zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="31e84-130">Use in Boolean expressions to connect two expressions.</span></span> <span data-ttu-id="31e84-131">Wenn beide Ausdrücke True sind, werden Ergebnisse zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="31e84-131">Results are returned when both expressions are true.</span></span><br /><br /> <span data-ttu-id="31e84-132">Wenn in einer Anweisung sowohl AND als auch OR verwendet werden, wird AND zuerst verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="31e84-132">When AND and OR are both used in a statement, AND is processed first.</span></span> <span data-ttu-id="31e84-133">Sie können die Reihenfolge der Ausführung ändern, indem Sie Klammern verwenden.</span><span class="sxs-lookup"><span data-stu-id="31e84-133">You can change the order of execution by using parentheses.</span></span>|  
|<span data-ttu-id="31e84-134">oder</span><span class="sxs-lookup"><span data-stu-id="31e84-134">OR</span></span>|<span data-ttu-id="31e84-135">Wird in booleschen Ausdrücken verwendet, um zwei oder mehr Bedingungen miteinander zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="31e84-135">Use in Boolean expressions to connect two or more conditions.</span></span> <span data-ttu-id="31e84-136">Wenn eine der beiden Bedingungen True ist, werden Ergebnisse zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="31e84-136">Results are returned when either condition is true.</span></span><br /><br /> <span data-ttu-id="31e84-137">Wenn in einer Anweisung sowohl AND als auch OR verwendet werden, wird zuerst AND und dann OR ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="31e84-137">When AND and OR are both used in a statement, OR is evaluated after AND.</span></span> <span data-ttu-id="31e84-138">Sie können die Reihenfolge der Ausführung ändern, indem Sie Klammern verwenden.</span><span class="sxs-lookup"><span data-stu-id="31e84-138">You can change the order of execution by using parentheses.</span></span>|  
|<span data-ttu-id="31e84-139">NICHT</span><span class="sxs-lookup"><span data-stu-id="31e84-139">NOT</span></span>|<span data-ttu-id="31e84-140">Negiert jeden booleschen Ausdruck (auch Schlüsselwörter wie LIKE, NULL, BETWEEN, IN und EXISTS).</span><span class="sxs-lookup"><span data-stu-id="31e84-140">Negates any Boolean expression (which can include keywords, such as LIKE, NULL, BETWEEN, IN, and EXISTS).</span></span><br /><br /> <span data-ttu-id="31e84-141">Wenn mehrere logische Operatoren in einer Anweisung verwendet werden, wird NOT zuerst verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="31e84-141">When more than one logical operator is used in a statement, NOT is processed first.</span></span> <span data-ttu-id="31e84-142">Sie können die Reihenfolge der Ausführung ändern, indem Sie Klammern verwenden.</span><span class="sxs-lookup"><span data-stu-id="31e84-142">You can change the order of execution by using parentheses.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="31e84-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="31e84-143">See Also</span></span>  
 <span data-ttu-id="31e84-144">[Unique-Einschränkungen und Check-Einschränkungen](../../relational-databases/tables/unique-constraints-and-check-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="31e84-144">[Unique Constraints and Check Constraints](../../relational-databases/tables/unique-constraints-and-check-constraints.md) </span></span>  
 [<span data-ttu-id="31e84-145">Erstellen von Unique-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="31e84-145">Create Unique Constraints</span></span>](../../relational-databases/tables/create-unique-constraints.md)  
  
  
