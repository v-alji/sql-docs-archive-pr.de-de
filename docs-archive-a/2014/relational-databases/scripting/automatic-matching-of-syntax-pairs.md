---
title: Automatischer Vergleich von Syntaxpaaren
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- IntelliSense [SQL Server], delimiter highlighting
- IntelliSense [SQL Server], syntax pair matching
ms.assetid: bfc54cda-bfd6-4545-a5b9-f9db2ae13769
author: rothja
ms.author: jroth
ms.openlocfilehash: d1237eeb9aaec39e3210b00c880c0005ef3d95bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616462"
---
# <a name="automatic-matching-of-syntax-pairs"></a><span data-ttu-id="f0df3-102">Automatischer Vergleich von Syntaxpaaren</span><span class="sxs-lookup"><span data-stu-id="f0df3-102">Automatic Matching of Syntax Pairs</span></span>
  <span data-ttu-id="f0df3-103">Durch den automatischen Vergleich von Syntaxpaaren erhalten Sie unmittelbar Aufschluss darüber, ob Syntaxelemente, die paarweise codiert werden müssen, ordnungsgemäß miteinander kombiniert sind.</span><span class="sxs-lookup"><span data-stu-id="f0df3-103">Automatic matching of syntax pairs gives you immediate feedback on whether syntax elements that must be coded in pairs are correctly paired.</span></span> <span data-ttu-id="f0df3-104">Im Abfrage-Editor von [!INCLUDE[ssDE](../../includes/ssde-md.md)] wird dieser Vorgang als Trennzeichenvergleich, im XMLA-Abfrage-Editor von Analysis Services als Klammernvergleich und im MDX- sowie im DMX-Editor als Klammernvergleich bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="f0df3-104">This is known as delimiter matching in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor, brace matching in the Analysis Services XMLA Query Editor, and parenthesis matching in the MDX and DMX editors.</span></span>  
  
## <a name="database-engine-query-editor-delimiter-matching"></a><span data-ttu-id="f0df3-105">Trennzeichenvergleich im Datenbank-Engine-Abfrage-Editor</span><span class="sxs-lookup"><span data-stu-id="f0df3-105">Database Engine Query Editor Delimiter Matching</span></span>  
 <span data-ttu-id="f0df3-106">Der [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Abfrage-Editor vergleicht die Trennzeichen, die die Begrenzungen von Codeblöcken angeben.</span><span class="sxs-lookup"><span data-stu-id="f0df3-106">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor matches the delimiters that identify the boundaries of code blocks.</span></span> <span data-ttu-id="f0df3-107">Der Vergleich erfolgt auf zwei verschiedene Weisen:</span><span class="sxs-lookup"><span data-stu-id="f0df3-107">The matching is done in two ways:</span></span>  
  
-   <span data-ttu-id="f0df3-108">Der Editor hebt beide Trennzeichen in einem Paar hervor, sobald Sie das zweite Trennzeichen des Paars eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="f0df3-108">The editor highlights both delimiters in a pair when you finish typing the second delimiter in the pair.</span></span>  
  
-   <span data-ttu-id="f0df3-109">Immer, wenn sich der Cursor auf einem der Trennzeichen eines Paars befindet, können Sie mithilfe der Tastenkombination STRG+] zum entsprechenden Trennzeichen springen.</span><span class="sxs-lookup"><span data-stu-id="f0df3-109">Anytime the cursor is in one of the delimiters in a pair, you can use the CTRL+] keyboard shortcut to jump to the matching delimiter.</span></span>  
  
### <a name="delimiter-pairs"></a><span data-ttu-id="f0df3-110">Trennzeichenpaare</span><span class="sxs-lookup"><span data-stu-id="f0df3-110">Delimiter Pairs</span></span>  
 <span data-ttu-id="f0df3-111">Beim automatischen Trennzeichenvergleich werden die folgenden Trennzeichen erkannt:</span><span class="sxs-lookup"><span data-stu-id="f0df3-111">Automatic delimiter matching recognizes the following sets of delimiters:</span></span>  
  
|<span data-ttu-id="f0df3-112">Vorangestelltes Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="f0df3-112">Lead Delimiter</span></span>|<span data-ttu-id="f0df3-113">Schließendes Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="f0df3-113">Closing Delimiter</span></span>|  
|--------------------|-----------------------|  
|<span data-ttu-id="f0df3-114">**(**</span><span class="sxs-lookup"><span data-stu-id="f0df3-114">**(**</span></span>|<span data-ttu-id="f0df3-115">**)**</span><span class="sxs-lookup"><span data-stu-id="f0df3-115">**)**</span></span>|  
|<span data-ttu-id="f0df3-116">**BEGIN**</span><span class="sxs-lookup"><span data-stu-id="f0df3-116">**BEGIN**</span></span>|<span data-ttu-id="f0df3-117">**END**</span><span class="sxs-lookup"><span data-stu-id="f0df3-117">**END**</span></span>|  
|<span data-ttu-id="f0df3-118">**BEGIN TRY**</span><span class="sxs-lookup"><span data-stu-id="f0df3-118">**BEGIN TRY**</span></span>|<span data-ttu-id="f0df3-119">**END TRY**</span><span class="sxs-lookup"><span data-stu-id="f0df3-119">**END TRY**</span></span>|  
|<span data-ttu-id="f0df3-120">**BEGIN CATCH**</span><span class="sxs-lookup"><span data-stu-id="f0df3-120">**BEGIN CATCH**</span></span>|<span data-ttu-id="f0df3-121">**END CATCH**</span><span class="sxs-lookup"><span data-stu-id="f0df3-121">**END CATCH**</span></span>|  
  
 <span data-ttu-id="f0df3-122">Beim automatischen Trennzeichenvergleich werden die Trennzeichen für Bezeichner in Klammern ([ObjectName]) oder Bezeichner in Anführungszeichen ("ObjectName") nicht erkannt.</span><span class="sxs-lookup"><span data-stu-id="f0df3-122">Automatic delimiter matching does not recognize the delimiters for bracketed identifiers ([ObjectName]), or quoted identifiers ("ObjectName").</span></span> <span data-ttu-id="f0df3-123">Beim Paarvergleich werden die einzelnen Anführungszeichen als Trennzeichen für Zeichenfolgenliterale ('string') nicht verglichen, weil die Farbcodierung bereits erkennen lässt, ob die Zeichenfolge ein Trennzeichen aufweist.</span><span class="sxs-lookup"><span data-stu-id="f0df3-123">Pair matching does not match the single quotation delimiters for string literals ('string') because color coding already gives a visual indication of whether the string has been delimited.</span></span>  
  
### <a name="delimiter-highlighting"></a><span data-ttu-id="f0df3-124">Hervorhebung von Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="f0df3-124">Delimiter Highlighting</span></span>  
 <span data-ttu-id="f0df3-125">Beim Vergleich werden sowohl das vorangestellte als auch das schließende Element eines Paars von Trennzeichen hervorgehoben.</span><span class="sxs-lookup"><span data-stu-id="f0df3-125">Matching highlights both the lead and closing element of a pair of delimiters.</span></span> <span data-ttu-id="f0df3-126">Auf diese Weise können Sie Codeblöcke visuell identifizieren und überprüfen, ob nicht übereinstimmende Paare von Trennzeichen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="f0df3-126">This lets you visually identify code blocks and check for mismatched pairs of delimiters.</span></span>  
  
 <span data-ttu-id="f0df3-127">Trennzeichen werden hervorgehoben, wenn Sie den letzten Buchstaben des Paars eingeben.</span><span class="sxs-lookup"><span data-stu-id="f0df3-127">Delimiters are highlighted when you type the final letter that completes the pair.</span></span> <span data-ttu-id="f0df3-128">Wenn Sie z. B. bei einem BEGIN…END-Paar zuerst BEGIN und dann END eingeben, wird die Hervorhebung aktiviert, sobald Sie den letzten Buchstaben von END eingeben.</span><span class="sxs-lookup"><span data-stu-id="f0df3-128">For example, for a BEGIN END pair where you type BEGIN first followed by END, highlighting turns on when you type the final letter in END.</span></span> <span data-ttu-id="f0df3-129">Es ist nicht erforderlich, zuerst das vorangestellte und dann das schließende Trennzeichen einzugeben, um die Hervorhebung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f0df3-129">You do not have to type the lead delimiter followed by the closing delimiter to turn on highlighting.</span></span> <span data-ttu-id="f0df3-130">Wenn Sie zuerst END eingeben und dann im Skript einen Bildlauf nach oben ausführen und BEGIN eingeben, wird die Hervorhebung aktiviert, sobald Sie den letzten Buchstaben von BEGIN eingeben.</span><span class="sxs-lookup"><span data-stu-id="f0df3-130">If you type END first, then scroll back up the script and type BEGIN, highlighting is turned on when you type the final letter in BEGIN.</span></span> <span data-ttu-id="f0df3-131">Der letzte eingegebene Buchstabe muss nicht der Buchstabe sein, mit dem das Trennzeichen endet.</span><span class="sxs-lookup"><span data-stu-id="f0df3-131">The final letter typed does not have to be the end letter in the delimiter.</span></span> <span data-ttu-id="f0df3-132">Wenn Sie z. B. BEGIN zuerst falsch schreiben und BEIN eingeben, wird das BEGIN…END-Paar hervorgehoben, sobald Sie das fehlende G eingeben.</span><span class="sxs-lookup"><span data-stu-id="f0df3-132">For example, you could misspell BEGIN as BEIN, when you insert the final G the BEGIN END pair is highlighted.</span></span>  
  
 <span data-ttu-id="f0df3-133">Das Trennzeichenpaar bleibt so lange hervorgehoben, bis Sie den Cursor verschieben.</span><span class="sxs-lookup"><span data-stu-id="f0df3-133">The delimiter pair remains highlighted until you move the cursor.</span></span> <span data-ttu-id="f0df3-134">Die Hervorhebung wird auch dann beim Verschieben des Cursors deaktiviert, wenn der Cursor an eine Position im gleichen Trennzeichen verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="f0df3-134">The highlighting is turned off when the cursor is moved, even if the new cursor position remains in the same delimiter.</span></span> <span data-ttu-id="f0df3-135">Sie können die Hervorhebung wieder aktivieren, indem Sie einen beliebigen Buchstaben in einem Element des Paars löschen und erneut eingeben.</span><span class="sxs-lookup"><span data-stu-id="f0df3-135">You can turn the highlighting back on by deleting and retyping any letter in either member of the pair.</span></span>  
  
## <a name="analysis-services-xmla-query-editor-brace-matching"></a><span data-ttu-id="f0df3-136">Klammernvergleich im XMLA-Abfrage-Editor von Analysis Services</span><span class="sxs-lookup"><span data-stu-id="f0df3-136">Analysis Services XMLA Query Editor Brace Matching</span></span>  
 <span data-ttu-id="f0df3-137">Beim Klammernvergleich im XMLA-Abfrage-Editor können Sie erkennen, ob Sie die Elemente geschlossen haben, da öffnende und schließende Klammern hervorgehoben werden.</span><span class="sxs-lookup"><span data-stu-id="f0df3-137">The XMLA Query Editor brace matching shows if you have closed elements by highlighting opening and closing braces.</span></span> <span data-ttu-id="f0df3-138">Sie können auch mithilfe der Tastenkombination STRG+] von einer Klammer zur jeweils entsprechenden Klammer springen.</span><span class="sxs-lookup"><span data-stu-id="f0df3-138">You can also use the CTRL+] keyboard shortcut to jump from one brace to the matching brace.</span></span>  
  
 <span data-ttu-id="f0df3-139">Im XMLA-Abfrage-Editor wird der Klammernvergleich für die folgenden Ausdrücke ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="f0df3-139">The XMLA Query Editor does brace matching for the following terms:</span></span>  
  
-   <span data-ttu-id="f0df3-140">Übereinstimmende Start- und Endtags</span><span class="sxs-lookup"><span data-stu-id="f0df3-140">Matching start and end tags.</span></span>  
  
-   <span data-ttu-id="f0df3-141">Ein beliebiges paar von " \<" and "> " Spitze Klammern.</span><span class="sxs-lookup"><span data-stu-id="f0df3-141">Any pair of "\<" and ">" angle brackets.</span></span>  
  
-   <span data-ttu-id="f0df3-142">Beginn und Ende von Kommentaren</span><span class="sxs-lookup"><span data-stu-id="f0df3-142">Start and end of comments.</span></span>  
  
-   <span data-ttu-id="f0df3-143">Beginn und Ende von Verarbeitungsanweisungen</span><span class="sxs-lookup"><span data-stu-id="f0df3-143">Start and end of processing instructions.</span></span>  
  
-   <span data-ttu-id="f0df3-144">Beginn und Ende von CDATA-Blöcken</span><span class="sxs-lookup"><span data-stu-id="f0df3-144">Start and end of CDATA blocks.</span></span>  
  
-   <span data-ttu-id="f0df3-145">Beginn und Ende von DTD-Deklarationen</span><span class="sxs-lookup"><span data-stu-id="f0df3-145">Start and end of DTD declarations.</span></span>  
  
-   <span data-ttu-id="f0df3-146">Öffnende und schließende Anführungszeichen bei Attributen</span><span class="sxs-lookup"><span data-stu-id="f0df3-146">Opening and closing quotes on attributes.</span></span>  
  
## <a name="mdx-and-dmx-editor-parenthesis-matching"></a><span data-ttu-id="f0df3-147">Klammernvergleich im MDX- und im DMX-Editor</span><span class="sxs-lookup"><span data-stu-id="f0df3-147">MDX and DMX Editor Parenthesis Matching</span></span>  
 <span data-ttu-id="f0df3-148">Der MDX-Editor (Multidimensional Expressions) und der DMX-Editor (Data Mining Expressions) gleichen automatisch Klammernpaare in Funktionen ab.</span><span class="sxs-lookup"><span data-stu-id="f0df3-148">The Multi-Dimensional Expressions (MDX) and Data Mining Expressions (DMX) Editors automatically match parenthesis pairs in functions.</span></span>  
  
  
