---
title: Transformation für bedingtes Teilen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.conditionalsplittrans.f1
helpviewer_keywords:
- Conditional Split transformation
- route rows to different outputs [Integration Services]
ms.assetid: 3f8b5825-226f-413c-ba8f-0bb931ca3770
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 96ff4b177992c329908ebc93df8f6220168e634d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619242"
---
# <a name="conditional-split-transformation"></a><span data-ttu-id="e1917-102">Transformation für bedingtes Teilen</span><span class="sxs-lookup"><span data-stu-id="e1917-102">Conditional Split Transformation</span></span>
  <span data-ttu-id="e1917-103">Die Transformation für bedingtes Teilen kann Datenzeilen je nach Dateninhalt an andere Ausgaben routen.</span><span class="sxs-lookup"><span data-stu-id="e1917-103">The Conditional Split transformation can route data rows to different outputs depending on the content of the data.</span></span> <span data-ttu-id="e1917-104">Die Implementierung der Transformation für bedingtes Teilen ist mit einer CASE-Entscheidungsstruktur in einer Programmiersprache vergleichbar.</span><span class="sxs-lookup"><span data-stu-id="e1917-104">The implementation of the Conditional Split transformation is similar to a CASE decision structure in a programming language.</span></span> <span data-ttu-id="e1917-105">Diese Transformation wertet Ausdrücke aus und leitet dann basierend auf den Ergebnissen die Datenzeilen an die angegebene Ausgabe weiter.</span><span class="sxs-lookup"><span data-stu-id="e1917-105">The transformation evaluates expressions, and based on the results, directs the data row to the specified output.</span></span> <span data-ttu-id="e1917-106">Diese Transformation stellt zudem eine Standardausgabe bereit, damit eine Zeile, die mit keinem Ausdruck übereinstimmt, an die Standardausgabe weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="e1917-106">This transformation also provides a default output, so that if a row matches no expression it is directed to the default output.</span></span>  
  
## <a name="configuration-of-the-conditional-split-transformation"></a><span data-ttu-id="e1917-107">Konfiguration der Transformation für bedingtes Teilen</span><span class="sxs-lookup"><span data-stu-id="e1917-107">Configuration of the Conditional Split Transformation</span></span>  
 <span data-ttu-id="e1917-108">Es gibt folgende Möglichkeiten, um die Transformation für bedingtes Teilen zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="e1917-108">You can configure the Conditional Split transformation in the following ways:</span></span>  
  
-   <span data-ttu-id="e1917-109">Stellen Sie einen Ausdruck, der in einen booleschen Wert ausgewertet wird, für jede von der Transformation zu testende Bedingung bereit.</span><span class="sxs-lookup"><span data-stu-id="e1917-109">Provide an expression that evaluates to a Boolean for each condition you want the transformation to test.</span></span>  
  
-   <span data-ttu-id="e1917-110">Geben Sie die Reihenfolge an, in der die Bedingungen ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="e1917-110">Specify the order in which the conditions are evaluated.</span></span> <span data-ttu-id="e1917-111">Die Reihenfolge ist wichtig, weil eine Zeile entsprechend der ersten Bedingung, die zu true ausgewertet wird, an die Ausgabe gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="e1917-111">Order is significant, because a row is sent to the output corresponding to the first condition that evaluates to true.</span></span>  
  
-   <span data-ttu-id="e1917-112">Geben Sie die Standardausgabe für die Transformation an.</span><span class="sxs-lookup"><span data-stu-id="e1917-112">Specify the default output for the transformation.</span></span> <span data-ttu-id="e1917-113">Für die Transformation muss eine Standardausgabe angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e1917-113">The transformation requires that a default output be specified.</span></span>  
  
 <span data-ttu-id="e1917-114">Jede Eingabezeile kann nur an eine Ausgabe gesendet werden, nämlich an die Ausgabe für die erste Bedingung, die zu true ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="e1917-114">Each input row can be sent to only one output, that being the output for the first condition that evaluates to true.</span></span> <span data-ttu-id="e1917-115">Beispielsweise leiten die folgenden Bedingungen Zeilen in der **FirstName** -Spalte, die mit dem Buchstaben *A* beginnen, an eine bestimmte Ausgabe weiter. Zeilen, die mit dem Buchstaben *B* beginnen, werden an eine andere Ausgabe weitergeleitet. Alle anderen Zeilen werden an die Standardausgabe weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="e1917-115">For example, the following conditions direct any rows in the **FirstName** column that begin with the letter *A* to one output, rows that begin with the letter *B* to a different output, and all other rows to the default output.</span></span>  
  
 <span data-ttu-id="e1917-116">Output 1</span><span class="sxs-lookup"><span data-stu-id="e1917-116">Output 1</span></span>  
  
 `SUBSTRING(FirstName,1,1) == "A"`  
  
 <span data-ttu-id="e1917-117">Output 2</span><span class="sxs-lookup"><span data-stu-id="e1917-117">Output 2</span></span>  
  
 `SUBSTRING(FirstName,1,1) == "B"`  
  
 [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] <span data-ttu-id="e1917-118">schließt Funktionen und Operatoren ein, mit denen Sie die Ausdrücke erstellen können, die Eingabedaten auswerten und Ausgabedaten weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="e1917-118">includes functions and operators that you can use to create the expressions that evaluate input data and direct output data.</span></span> <span data-ttu-id="e1917-119">Weitere Informationen finden Sie unter [Integration Services-Ausdrücke &#40;SSIS&#41;](../../expressions/integration-services-ssis-expressions.md)ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="e1917-119">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../../expressions/integration-services-ssis-expressions.md).</span></span>  
  
 <span data-ttu-id="e1917-120">Die Transformation für bedingtes Teilen schließt die benutzerdefinierte Eigenschaft `FriendlyExpression` ein.</span><span class="sxs-lookup"><span data-stu-id="e1917-120">The Conditional Split transformation includes the `FriendlyExpression` custom property.</span></span> <span data-ttu-id="e1917-121">Diese Eigenschaft kann beim Laden des Pakets mithilfe eines Eigenschaftsausdrucks aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="e1917-121">This property can be updated by a property expression when the package is loaded.</span></span> <span data-ttu-id="e1917-122">Weitere Informationen finden Sie unter [Verwenden von Eigenschaftsausdrücken in Paketen](../../expressions/use-property-expressions-in-packages.md) und [Benutzerdefinierte Eigenschaften von Transformationen](transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="e1917-122">For more information, see [Use Property Expressions in Packages](../../expressions/use-property-expressions-in-packages.md) and [Transformation Custom Properties](transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="e1917-123">Diese Transformation weist eine Eingabe, mindestens eine Ausgabe und eine Fehlerausgabe auf.</span><span class="sxs-lookup"><span data-stu-id="e1917-123">This transformation has one input, one or more outputs, and one error output.</span></span>  
  
 <span data-ttu-id="e1917-124">Sie können Eigenschaften mit dem [!INCLUDE[ssIS](../../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="e1917-124">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="e1917-125">Weitere Informationen zu den Eigenschaften, die Sie im Dialogfeld **Transformations-Editor für bedingtes Teilen** festlegen können, finden Sie unter [Conditional Split Transformation Editor](../../conditional-split-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="e1917-125">For more information about the properties that you can set in the **Conditional Split Transformation Editor** dialog box, see [Conditional Split Transformation Editor](../../conditional-split-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="e1917-126">Das Dialogfeld **Erweiterter Editor** enthält die Eigenschaften, die programmgesteuert festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="e1917-126">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="e1917-127">Klicken Sie auf eines der folgenden Themen, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im Dialogfeld **Erweiterter Editor** oder programmgesteuert festlegen können:</span><span class="sxs-lookup"><span data-stu-id="e1917-127">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="e1917-128">Common Properties</span><span class="sxs-lookup"><span data-stu-id="e1917-128">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="e1917-129">Benutzerdefinierte Eigenschaften von Transformationen</span><span class="sxs-lookup"><span data-stu-id="e1917-129">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
 <span data-ttu-id="e1917-130">Klicken Sie auf eines der folgenden Themen, um weitere Informationen zum Festlegen von Eigenschaften anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="e1917-130">For more information about how to set properties, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="e1917-131">Teilen eines Datasets mithilfe der Transformation für bedingtes Teilen</span><span class="sxs-lookup"><span data-stu-id="e1917-131">Split a Dataset by Using the Conditional Split Transformation</span></span>](conditional-split-transformation.md)  
  
-   [<span data-ttu-id="e1917-132">Festlegen der Eigenschaften einer Datenflusskomponente</span><span class="sxs-lookup"><span data-stu-id="e1917-132">Set the Properties of a Data Flow Component</span></span>](../set-the-properties-of-a-data-flow-component.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="e1917-133">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="e1917-133">Related Tasks</span></span>  
 [<span data-ttu-id="e1917-134">Teilen eines Datasets mithilfe der Transformation für bedingtes Teilen</span><span class="sxs-lookup"><span data-stu-id="e1917-134">Split a Dataset by Using the Conditional Split Transformation</span></span>](conditional-split-transformation.md)  
  
## <a name="see-also"></a><span data-ttu-id="e1917-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e1917-135">See Also</span></span>  
 <span data-ttu-id="e1917-136">[Datenfluss](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="e1917-136">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="e1917-137">SQL Server Integration Services-Transformationen</span><span class="sxs-lookup"><span data-stu-id="e1917-137">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
