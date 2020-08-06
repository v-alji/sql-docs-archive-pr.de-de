---
title: Seite Ausdrücke | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.expressionspage.f1
helpviewer_keywords:
- Expressions Page dialog box
ms.assetid: c9016ec6-11c1-4ebd-b2a7-0fa6631fd9e4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ba4e73ea495456e8f9e452108ab09106a65543ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617215"
---
# <a name="expressions-page"></a><span data-ttu-id="dd988-102">Seite Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="dd988-102">Expressions Page</span></span>
  <span data-ttu-id="dd988-103">Mithilfe der Seite **Ausdrücke** können Sie Eigenschaftsausdrücke bearbeiten und auf die Dialogfelder **Eigenschaftsausdrucks-Editor** und **Eigenschaftsausdrucks-Generator** zugreifen.</span><span class="sxs-lookup"><span data-stu-id="dd988-103">Use the **Expressions** page to edit property expressions and to access the **Property Expressions Editor** and **Property Expression Builder** dialog boxes.</span></span>  
  
 <span data-ttu-id="dd988-104">Eigenschaftsausdrücke aktualisieren die Werte von Eigenschaften, wenn das Paket ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="dd988-104">Property expressions update the values of properties when the package is run.</span></span> <span data-ttu-id="dd988-105">Eigenschaftsausdrücke können mit den Eigenschaften von Paketen, Tasks, Containern, Verbindungs-Managern sowie einigen Datenflusskomponenten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dd988-105">Property expressions can be used with the properties of packages, tasks, containers, connection managers, as well as some data flow components.</span></span> <span data-ttu-id="dd988-106">Die Ausdrücke werden ausgewertet und ihre Ergebnisse werden anstelle der Werte verwendet, auf die Sie die Eigenschaften festgelegt haben, als Sie das Paket und die Paketobjekte konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="dd988-106">The expressions are evaluated and their results are used instead of the values to which you set the properties when you configured the package and package objects.</span></span> <span data-ttu-id="dd988-107">Die Ausdrücke können Variablen und die Funktionen und Operatoren enthalten, die die Ausdruckssprache bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="dd988-107">The expressions can include variables and the functions and operators that the expression language provides.</span></span> <span data-ttu-id="dd988-108">Beispielsweise können Sie die Betreffzeile für den Task Mail senden generieren, indem Sie den Wert einer Variablen, die die Zeichenfolge "Weather forecast for " enthält, und die zurückgegebenen Ergebnisse der GETDATE()-Funktion zu der Zeichenfolge "Weather forecast for 4/5/2006" verketten.</span><span class="sxs-lookup"><span data-stu-id="dd988-108">For example, you can generate the subject line for the Send Mail task by concatenating the value of a variable that contains the string "Weather forecast for " and the return results of the GETDATE() function to make the string "Weather forecast for 4/5/2006".</span></span>  
  
 <span data-ttu-id="dd988-109">Weitere Informationen zum Schreiben von Ausdrücken und zum Verwenden von Eigenschaftsausdrücken finden Sie unter [Integration Services-Ausdrücke &#40;SSIS&#41;](integration-services-ssis-expressions.md) und [Verwenden von Eigenschaftsausdrücken in Paketen](use-property-expressions-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="dd988-109">To learn more about writing expressions and using property expressions, see [Integration Services &#40;SSIS&#41; Expressions](integration-services-ssis-expressions.md) and [Use Property Expressions in Packages](use-property-expressions-in-packages.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="dd988-110">Tastatur</span><span class="sxs-lookup"><span data-stu-id="dd988-110">Options</span></span>  
 <span data-ttu-id="dd988-111">**Ausdrücke (...)**</span><span class="sxs-lookup"><span data-stu-id="dd988-111">**Expressions (...)**</span></span>  
 <span data-ttu-id="dd988-112">Klicken Sie auf die Auslassungspunkte (...), um das Dialogfeld **Eigenschaftsausdrucks-Editor** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="dd988-112">Click the ellipsis to open the **Property Expressions Editor** dialog box.</span></span> <span data-ttu-id="dd988-113">Weitere Informationen finden Sie unter [Property Expressions Editor](property-expressions-editor.md).</span><span class="sxs-lookup"><span data-stu-id="dd988-113">For more information, see [Property Expressions Editor](property-expressions-editor.md).</span></span>  
  
 **\<property name>**  
 <span data-ttu-id="dd988-114">Klicken Sie auf die Schaltfläche mit den drei Punkten, um das Dialogfeld **Ausdrucks-Generator** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="dd988-114">Click the ellipsis to open the **Expression Builder** dialog box.</span></span> <span data-ttu-id="dd988-115">Weitere Informationen finden Sie unter [Expression Builder](expression-builder.md).</span><span class="sxs-lookup"><span data-stu-id="dd988-115">For more information, see [Expression Builder](expression-builder.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd988-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dd988-116">See Also</span></span>  
 <span data-ttu-id="dd988-117">[Integration Services-Variablen &#40;SSIS&#41;](../integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="dd988-117">[Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) </span></span>  
 <span data-ttu-id="dd988-118">[Systemvariablen](../system-variables.md) </span><span class="sxs-lookup"><span data-stu-id="dd988-118">[System Variables](../system-variables.md) </span></span>  
 [<span data-ttu-id="dd988-119">Integration Services-Ausdrücke &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="dd988-119">Integration Services &#40;SSIS&#41; Expressions</span></span>](integration-services-ssis-expressions.md)  
  
  
