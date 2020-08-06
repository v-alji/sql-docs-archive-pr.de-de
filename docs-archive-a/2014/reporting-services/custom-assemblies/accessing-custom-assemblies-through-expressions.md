---
title: Zugriff auf benutzerdefinierte Assemblys über Ausdrücke | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- expressions [Reporting Services], custom assemblies
- static member calls
- instance member calls [Reporting Services]
- calling class members
- custom assemblies [Reporting Services], expressions
ms.assetid: 917c4d47-1a95-4f54-98b1-e8cb2165d90f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 99497de0456d90fd522ce27c62fd5aa1b812059f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607543"
---
# <a name="accessing-custom-assemblies-through-expressions"></a><span data-ttu-id="285ba-102">Zugriff auf benutzerdefinierte Assemblys über Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="285ba-102">Accessing Custom Assemblies Through Expressions</span></span>
  <span data-ttu-id="285ba-103">Sobald Sie eine benutzerdefinierte Assembly erstellt, diese im Berichts-Designer oder Berichtsserver zur Verfügung gestellt, die entsprechende Sicherheitsrichtlinie und in der Berichtsdefinition einen Verweis auf die benutzerdefinierte Assembly hinzugefügt haben, können Sie mit Berichtsausdrücken auf Klassenelemente in der Assembly zugreifen.</span><span class="sxs-lookup"><span data-stu-id="285ba-103">Once you have created a custom assembly, made it available to Report Designer or the report server, added the appropriate security policy, and added a reference to your custom assembly in your report definition, you can access the members of the classes in your assembly using report expressions.</span></span> <span data-ttu-id="285ba-104">Wenn Sie in einem Ausdruck auf benutzerdefinierten Code verweisen möchten, müssen Sie das Klassenelement in der Assembly aufrufen.</span><span class="sxs-lookup"><span data-stu-id="285ba-104">To refer to custom code in an expression, you must call the member of a class within the assembly.</span></span> <span data-ttu-id="285ba-105">Die Vorgehensweise hängt davon ab, ob es sich um eine statische oder um eine instanzbasierte Methode handelt.</span><span class="sxs-lookup"><span data-stu-id="285ba-105">How you do this depends on whether the method is static or instance-based.</span></span>  
  
## <a name="calling-static-members-from-a-report-definition-file"></a><span data-ttu-id="285ba-106">Aufruf statischer Elemente aus einer Berichtsdefinitionsdatei</span><span class="sxs-lookup"><span data-stu-id="285ba-106">Calling Static Members from a Report Definition File</span></span>  
 <span data-ttu-id="285ba-107">Statische Elemente gehören zur Klasse oder zum Typ selbst und nicht zu einem instanziierten Objekt.</span><span class="sxs-lookup"><span data-stu-id="285ba-107">Static members belong to the class or type itself and not to an instantiated object.</span></span> <span data-ttu-id="285ba-108">Auf diese Elemente kann zugegriffen werden, indem sie direkt von der Klasse aus aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="285ba-108">These members can be accessed by directly calling them from the class.</span></span> <span data-ttu-id="285ba-109">Wenn möglich, sollten Sie statische Elemente verwenden, um benutzerdefinierte Funktionen in einem Bericht aufzurufen, da die Leistung von statischen Elementen am besten ist.</span><span class="sxs-lookup"><span data-stu-id="285ba-109">You should use static members to call custom functions in a report whenever possible, because static members perform best.</span></span> <span data-ttu-id="285ba-110">Um ein statisches Element aufzurufen, müssen Sie darauf als Ausdruck in der Form =*Namespace.Class.Method* verweisen.</span><span class="sxs-lookup"><span data-stu-id="285ba-110">To call a static member, you need to reference it as an expression that takes the form =*Namespace.Class.Method*.</span></span>  
  
#### <a name="to-call-static-members"></a><span data-ttu-id="285ba-111">So rufen Sie statische Elemente auf</span><span class="sxs-lookup"><span data-stu-id="285ba-111">To call static members</span></span>  
  
-   <span data-ttu-id="285ba-112">Um ein statisches Element aufzurufen, stellen Sie den Ausdruck auf den vollqualifizierten Namen des Elements ein, der Namespace, den Klassennamen und den Elementnamen umfasst.</span><span class="sxs-lookup"><span data-stu-id="285ba-112">To call a static member, set your expression equal to the fully qualified name of the member, which includes the namespace, class name, and member name.</span></span> <span data-ttu-id="285ba-113">Im folgenden Beispiel wird die **ToGBP**-Methode verwendet, bei der der Wert des Felds **StandardCost** von Dollar in britische Pund umgerechnet und in einem Bericht angezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="285ba-113">The following example calls the **ToGBP** method, which converts the **StandardCost** field value from dollars to pounds sterling and displays it in a report:</span></span>  
  
    ```  
    =CurrencyConversion.DollarCurrencyConversion.ToGBP(Fields!StandardCost.Value)  
    ```  
  
### <a name="important-information-regarding-static-fields-and-properties"></a><span data-ttu-id="285ba-114">Wichtige Informationen für statische Felder und Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="285ba-114">Important Information Regarding Static Fields and Properties</span></span>  
 <span data-ttu-id="285ba-115">Derzeit werden alle Berichte in der gleichen Anwendungsdomäne ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="285ba-115">Currently, all reports are executed in the same application domain.</span></span> <span data-ttu-id="285ba-116">Das bedeutet, dass Berichte mit benutzerdefinierten, statischen Daten diese Daten in anderen Instanzen desselben Berichts zur Verfügung stellen.</span><span class="sxs-lookup"><span data-stu-id="285ba-116">This means that reports with user-specific, static data expose this data to other instances of the same report.</span></span> <span data-ttu-id="285ba-117">Dies kann dazu führen, dass die statischen Daten eines Benutzers allen Benutzern, die einen bestimmten Bericht ausführen, zur Verfügung gestellt werden.</span><span class="sxs-lookup"><span data-stu-id="285ba-117">This condition might make it possible for the static data of one user to be available to all users currently running a particular report.</span></span> <span data-ttu-id="285ba-118">Aus diesem Grund empfiehlt es sich, keine statischen Felder oder Eigenschaften in benutzerdefinierten Assemblys oder im **Code-Element**, sondern stattdessen Instanzfelder bzw. -eigenschaften in Berichten zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="285ba-118">For this reason, it is highly recommended that you not use static fields or properties in custom assemblies or in the **Code** element; instead, use instance fields or properties in your reports.</span></span> <span data-ttu-id="285ba-119">Statische Methoden können trotzdem verwendet werden, da sie weder Status noch Daten speichern.</span><span class="sxs-lookup"><span data-stu-id="285ba-119">Static methods can still be used, because they do not store state or data.</span></span>  
  
## <a name="calling-instance-members-from-a-report-definition-file"></a><span data-ttu-id="285ba-120">Aufruf von Instanzelementen aus einer Berichtsdefinitionsdatei</span><span class="sxs-lookup"><span data-stu-id="285ba-120">Calling Instance Members from a Report Definition File</span></span>  
 <span data-ttu-id="285ba-121">Wenn die benutzerdefinierte Assembly Instanzelemente enthält, auf die Sie in einer Berichtsdefinition zugreifen müssen, müssen Sie einen Instanznamen für die Klasse des Berichts hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="285ba-121">If your custom assembly contains instance members that you need to access in a report definition, you must add an instance name for your class to the report.</span></span> <span data-ttu-id="285ba-122">Hierzu verwenden Sie die Registerkarte **Code** des Dialogfelds **Berichtseigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="285ba-122">You can add an instance name for a class using the **Code** tab of the **Report Properties** dialog.</span></span> <span data-ttu-id="285ba-123">Weitere Informationen zum Hinzufügen von Klasseninstanzen zu einem Bericht finden Sie unter [Benutzerdefinierter Code und Assemblyverweise in Ausdrücken in Berichts-Designer (SSRS)](../report-design/custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="285ba-123">For more information about adding instances of classes to a report, see [Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;](../report-design/custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span></span>  
  
 <span data-ttu-id="285ba-124">Um einen statischen Member aufzurufen, müssen Sie als Ausdruck mit der Form = Code darauf verweisen *. InstanceName. Method*.</span><span class="sxs-lookup"><span data-stu-id="285ba-124">To call a static member, you need to reference it as an expression that takes the form = Code *.InstanceName.Method*.</span></span>  
  
#### <a name="to-call-instance-members"></a><span data-ttu-id="285ba-125">So rufen Sie Instanzelemente auf</span><span class="sxs-lookup"><span data-stu-id="285ba-125">To call instance members</span></span>  
  
-   <span data-ttu-id="285ba-126">Um ein Instanzelement einer benutzerdefinierten Assembly aufzurufen, müssen Sie auf das Schlüsselwort **Code** gefolgt vom Instanznamen und der Methode verweisen.</span><span class="sxs-lookup"><span data-stu-id="285ba-126">To call an instance member of a custom assembly, you must reference the **Code** keyword followed by the instance name and the method.</span></span> <span data-ttu-id="285ba-127">Im folgenden Beispiel wird die Instanzmethode **ToEUR** verwendet, bei der der Wert des Felds **StandardCost** von Dollar in Euro umgerechnet und in einem Bericht angezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="285ba-127">The following example calls an instance method **ToEUR** which converts the **StandardCost** field value from dollars to euros and displays it in a report:</span></span>  
  
    ```  
    =Code.m_myDollarCoversion.ToEUR(Fields!StandardCost.Value)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="285ba-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="285ba-128">See Also</span></span>  
 [<span data-ttu-id="285ba-129">Verwenden benutzerdefinierter Assemblys mit Berichten</span><span class="sxs-lookup"><span data-stu-id="285ba-129">Using Custom Assemblies with Reports</span></span>](using-custom-assemblies-with-reports.md)  
  
  
