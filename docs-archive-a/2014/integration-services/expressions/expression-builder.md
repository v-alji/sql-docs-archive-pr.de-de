---
title: Ausdrucks-Generator | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.expressionbuilder.f1
helpviewer_keywords:
- Expression Builder dialog box
ms.assetid: 4717ce33-bd4e-44bc-81e0-002de075b4d1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 812b0d744d415d5419d54176359ddcd5837dd206
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617214"
---
# <a name="expression-builder"></a><span data-ttu-id="476cd-102">Ausdrucks-Generator</span><span class="sxs-lookup"><span data-stu-id="476cd-102">Expression Builder</span></span>
  <span data-ttu-id="476cd-103">Verwenden Sie das Dialogfeld **Ausdrucks-Generator** , um mithilfe einer grafischen Benutzeroberfläche einen Eigenschaftsausdruck zu erstellen und zu bearbeiten oder den Ausdruck zu schreiben, der den Wert einer Variablen festlegt. Diese grafische Benutzeroberfläche bietet Listen von Variablen sowie integrierte Verweise auf Funktionen, Typumwandlungen und Operatoren der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Ausdruckssprache.</span><span class="sxs-lookup"><span data-stu-id="476cd-103">Use the **Expression Builder** dialog box to create and edit a property expression or write the expression that sets the value of a variable using a graphical user interface that lists variables and provides a built-in reference to the functions, type casts, and operators that the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expression language includes.</span></span>  
  
 <span data-ttu-id="476cd-104">Ein Eigenschaftsausdruck ist ein einer Eigenschaft zugewiesener Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="476cd-104">A property expression is an expression that is assigned to a property.</span></span> <span data-ttu-id="476cd-105">Wenn der Ausdruck ausgewertet wird, wird die Eigenschaft dynamisch aktualisiert, damit das Auswertungsergebnis des Ausdrucks verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="476cd-105">When the expression is evaluated, the property is dynamically updated to use the evaluation result of the expression.</span></span> <span data-ttu-id="476cd-106">Genauso ermöglicht ein Ausdruck, der in einer Variablen verwendet wird, das Update des Variablenwerts mit dem Auswertungsergebnis des Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="476cd-106">Likewise, an expression that is used in a variable enables the variable value to be updated with the evaluation result of the expression.</span></span>  
  
 <span data-ttu-id="476cd-107">Es gibt mehrere Verwendungsmöglichkeiten für Ausdrücke:</span><span class="sxs-lookup"><span data-stu-id="476cd-107">There are many ways to use expressions:</span></span>  
  
-   <span data-ttu-id="476cd-108">**Tasks** Aktualisieren Sie die „An“-Zeile, die ein Task des Typs „Mail“ senden verwendet, indem eine in einer Variablen gespeicherte E-Mail-Adresse eingefügt wird, oder aktualisieren Sie die Betreffzeile, indem Sie eine Zeichenfolge, wie z.B. "Sales for:", und das aktuelle Datum verketten, das von der GETDATE-Funktion zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="476cd-108">**Tasks** Update the To line that a Send Mail task uses by inserting an e-mail address that is stored in a variable; or update the Subject line by concatenating a string such as "Sales for: " and the current date returned by the GETDATE function.</span></span>  
  
-   <span data-ttu-id="476cd-109">**Variablen** Legen Sie den Wert einer Variablen auf den aktuellen Monat fest, indem Sie einen Ausdruck wie `DATEPART("mm",GETDATE())`verwenden. Oder legen Sie den Wert einer Zeichenfolge fest, indem Sie das Zeichenfolgenliteral und das aktuelle Datum mithilfe des Ausdrucks `"Today's date is " + (DT_WSTR,30)(GETDATE())`verketten.</span><span class="sxs-lookup"><span data-stu-id="476cd-109">**Variables** Set the value of a variable to the current month by using an expression like `DATEPART("mm",GETDATE())`; or set the value of a string by concatenating the string literal and the current date by using the expression `"Today's date is " + (DT_WSTR,30)(GETDATE())`.</span></span>  
  
-   <span data-ttu-id="476cd-110">**Verbindungs-Manager** Legen Sie die Codepage eines Flatfile-Verbindungs-Managers fest, indem Sie eine Variable verwenden, die einen anderen Codepagebezeichner enthält, oder geben Sie die Anzahl der auszulassenden Zeilen in der Datendatei an, indem Sie eine positive ganze Zahl, z. B. 3, in dem Ausdruck eingeben.</span><span class="sxs-lookup"><span data-stu-id="476cd-110">**Connection Managers** Set the code page of a Flat File connection manager by using a variable that contains a different code page identifier; or specify the number of rows in the data file to skip by entering a positive integer like 3 in the expression.</span></span>  
  
 <span data-ttu-id="476cd-111">Weitere Informationen zu Eigenschaftenausdrücken und zum Schreiben von Ausdrücken finden Sie unter [Verwenden von Eigenschaftsausdrücken in Paketen](use-property-expressions-in-packages.md) und [Integration Services-Ausdrücke &#40;SSIS&#41;](integration-services-ssis-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="476cd-111">To learn more about property expressions and writing expressions, see [Use Property Expressions in Packages](use-property-expressions-in-packages.md) and [Integration Services &#40;SSIS&#41; Expressions](integration-services-ssis-expressions.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="476cd-112">Tastatur</span><span class="sxs-lookup"><span data-stu-id="476cd-112">Options</span></span>  
  
|<span data-ttu-id="476cd-113">Begriff</span><span class="sxs-lookup"><span data-stu-id="476cd-113">Term</span></span>|<span data-ttu-id="476cd-114">Definition</span><span class="sxs-lookup"><span data-stu-id="476cd-114">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="476cd-115">**Variablen**</span><span class="sxs-lookup"><span data-stu-id="476cd-115">**Variables**</span></span>|<span data-ttu-id="476cd-116">Erweitern Sie den Ordner **Variablen** , und ziehen Sie die gewünschten Variablen in das Feld **Ausdruck** .</span><span class="sxs-lookup"><span data-stu-id="476cd-116">Expand the **Variables** folder and drag variables to the **Expression** box.</span></span>|  
|<span data-ttu-id="476cd-117">**Mathematische Funktionen**</span><span class="sxs-lookup"><span data-stu-id="476cd-117">**Mathematical Functions**</span></span><br /><br /> <span data-ttu-id="476cd-118">**Zeichenfolgenfunktionen**</span><span class="sxs-lookup"><span data-stu-id="476cd-118">**String Functions**</span></span><br /><br /> <span data-ttu-id="476cd-119">**Datum/Uhrzeit-Funktionen**</span><span class="sxs-lookup"><span data-stu-id="476cd-119">**Date/Time Functions**</span></span><br /><br /> <span data-ttu-id="476cd-120">**NULL-Funktionen**</span><span class="sxs-lookup"><span data-stu-id="476cd-120">**NULL Functions**</span></span><br /><br /> <span data-ttu-id="476cd-121">**Typumwandlungen**</span><span class="sxs-lookup"><span data-stu-id="476cd-121">**Type Casts**</span></span><br /><br /> <span data-ttu-id="476cd-122">**Operatoren**</span><span class="sxs-lookup"><span data-stu-id="476cd-122">**Operators**</span></span>|<span data-ttu-id="476cd-123">Erweitern Sie die entsprechenden Ordner, und ziehen Sie die gewünschten Funktionen, Typumwandlungen und Operatoren in das Feld **Ausdruck** .</span><span class="sxs-lookup"><span data-stu-id="476cd-123">Expand the folders and drag functions, type casts, and operators to the **Expression** box.</span></span>|  
|<span data-ttu-id="476cd-124">**Ausdruck**</span><span class="sxs-lookup"><span data-stu-id="476cd-124">**Expression**</span></span>|<span data-ttu-id="476cd-125">Geben Sie einen Ausdruck ein, oder bearbeiten Sie einen Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="476cd-125">Edit or type an expression.\`</span></span>|  
|<span data-ttu-id="476cd-126">**Ausgewerteter Wert**</span><span class="sxs-lookup"><span data-stu-id="476cd-126">**Evaluated value**</span></span>|<span data-ttu-id="476cd-127">Listet das Ergebnis der Ausdrucksauswertung auf.</span><span class="sxs-lookup"><span data-stu-id="476cd-127">Lists the evaluation result of the expression.</span></span>|  
|<span data-ttu-id="476cd-128">**Ausdruck auswerten**</span><span class="sxs-lookup"><span data-stu-id="476cd-128">**Evaluate Expression**</span></span>|<span data-ttu-id="476cd-129">Klicken Sie auf **Ausdruck auswerten** , um das Auswertungsergebnis des Ausdrucks anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="476cd-129">Click **Evaluate Expression** to view the evaluation result of the expression.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="476cd-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="476cd-130">See Also</span></span>  
 <span data-ttu-id="476cd-131">[Seite Ausdrücke](expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="476cd-131">[Expressions Page](expressions-page.md) </span></span>  
 <span data-ttu-id="476cd-132">[Eigenschaftsausdrucks-Editor](property-expressions-editor.md) </span><span class="sxs-lookup"><span data-stu-id="476cd-132">[Property Expressions Editor](property-expressions-editor.md) </span></span>  
 <span data-ttu-id="476cd-133">[Integration Services-Variablen &#40;SSIS&#41;](../integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="476cd-133">[Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) </span></span>  
 [<span data-ttu-id="476cd-134">Systemvariablen</span><span class="sxs-lookup"><span data-stu-id="476cd-134">System Variables</span></span>](../system-variables.md)  
  
  
