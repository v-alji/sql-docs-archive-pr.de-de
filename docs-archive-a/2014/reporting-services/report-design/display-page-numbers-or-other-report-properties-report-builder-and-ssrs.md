---
title: Anzeigen von Seitenzahlen oder anderen Berichtseigenschaften (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c7d95245-4709-4d04-acb4-59bf71e60d97
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: efc3d5d5de11af1fcdfefc52ed12d5057ee12668
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617736"
---
# <a name="display-page-numbers-or-other-report-properties-report-builder-and-ssrs"></a><span data-ttu-id="80bde-102">Anzeigen von Seitenzahlen oder anderen Berichtseigenschaften (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="80bde-102">Display Page Numbers or Other Report Properties (Report Builder and SSRS)</span></span>
  <span data-ttu-id="80bde-103">Seitenkopf- oder –fußzeilen in dem Bericht können Seitenzahlen, Berichtstitel, Dateinamen und andere Berichtseigenschaften auf einfache Weise hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="80bde-103">It's easy to add page numbers, a report title, file name, and other report properties to the page headers or footers of your report.</span></span> <span data-ttu-id="80bde-104">Diese Eigenschaften werden als Felder im Ordner Integrierte Felder im Berichtsdatenbereich gespeichert:</span><span class="sxs-lookup"><span data-stu-id="80bde-104">These properties are stored as fields in the Built-in Fields folder in the Report Data pane:</span></span>  
  
-   <span data-ttu-id="80bde-105">Ausführungszeit</span><span class="sxs-lookup"><span data-stu-id="80bde-105">Execution time</span></span>  
  
-   <span data-ttu-id="80bde-106">Seitenzahl</span><span class="sxs-lookup"><span data-stu-id="80bde-106">Page number</span></span>  
  
-   <span data-ttu-id="80bde-107">Berichtsordner</span><span class="sxs-lookup"><span data-stu-id="80bde-107">Report folder</span></span>  
  
-   <span data-ttu-id="80bde-108">Berichtsname</span><span class="sxs-lookup"><span data-stu-id="80bde-108">Report name</span></span>  
  
-   <span data-ttu-id="80bde-109">Berichtsserver-URL</span><span class="sxs-lookup"><span data-stu-id="80bde-109">Report server URL</span></span>  
  
-   <span data-ttu-id="80bde-110">Seiten gesamt</span><span class="sxs-lookup"><span data-stu-id="80bde-110">Total pages</span></span>  
  
-   <span data-ttu-id="80bde-111">Benutzer-ID</span><span class="sxs-lookup"><span data-stu-id="80bde-111">User ID</span></span>  
  
-   <span data-ttu-id="80bde-112">Sprache</span><span class="sxs-lookup"><span data-stu-id="80bde-112">Language</span></span>  
  
 <span data-ttu-id="80bde-113">Für eine Seitenzahl können Sie gegebenenfalls das Wort "Seite" vor der Zahl hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="80bde-113">For a page number, you may want to add the word "Page" before the number.</span></span> <span data-ttu-id="80bde-114">Möglicherweise soll auch die Gesamtanzahl von Seiten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="80bde-114">You may also want to show the total number of pages.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="80bde-115">Wenn Sie die Gesamtanzahl von Seiten der Fußzeile hinzufügen, kann sich dies negativ auf die Leistung bei der Ausführung oder Vorschau des Berichts auswirken.</span><span class="sxs-lookup"><span data-stu-id="80bde-115">Adding the total number of pages to the footer may slow performance when you run or preview your report.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-page-number-or-other-report-properties"></a><span data-ttu-id="80bde-116">So fügen Sie eine Seitenzahl oder andere Berichtseigenschaften hinzu</span><span class="sxs-lookup"><span data-stu-id="80bde-116">To add a page number or other report properties</span></span>  
  
1.  <span data-ttu-id="80bde-117">Erweitern Sie im Berichtsdatenbereich den Knoten Integrierte Felder.</span><span class="sxs-lookup"><span data-stu-id="80bde-117">In the Report Data pane, expand the Built-in Fields folder.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="80bde-118">Zum Anzeigen des Berichtsdatenbereichs klicken Sie gegebenenfalls auf der Registerkarte „Ansicht“ auf **Berichtsdaten**.</span><span class="sxs-lookup"><span data-stu-id="80bde-118">If you don't see the Report Data pane, on the View tab, check **Report Data**.</span></span>  
  
2.  <span data-ttu-id="80bde-119">Ziehen Sie das Feld **Seitenzahl** aus dem Berichtsdatenbereich in die Berichtskopf- oder -fußzeile.</span><span class="sxs-lookup"><span data-stu-id="80bde-119">Drag the **Page Number** field from the Report Data pane to the report header or footer.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="80bde-120">Dem Bericht wird der Seitenfuß automatisch hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="80bde-120">The page footer is added to the report automatically.</span></span> <span data-ttu-id="80bde-121">Um einen Seitenkopf hinzuzufügen, klicken Sie auf der Registerkarte **Einfügen** auf **Kopfzeile**und danach auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="80bde-121">To add a page header, on the **Insert** tab, click **Header**, and then click **Add Header**.</span></span>  
    >   
    >  <span data-ttu-id="80bde-122">Ein Textfeld, das den einfachen Ausdruck [&PageNumber] enthält, wird hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="80bde-122">A text box that contains the simple expression [&PageNumber] is added.</span></span>  
  
### <a name="to-add-the-word-page-before-the-page-number"></a><span data-ttu-id="80bde-123">So fügen Sie das Wort "Seite" vor der Seitenzahl hinzu</span><span class="sxs-lookup"><span data-stu-id="80bde-123">To add the word "Page" before the page number</span></span>  
  
1.  <span data-ttu-id="80bde-124">Klicken Sie mit der rechten Maustaste auf das Textfeld, das [&PageNumber] enthält, und klicken Sie auf **Ausdrücke**.</span><span class="sxs-lookup"><span data-stu-id="80bde-124">Right-click the text box that contains [&PageNumber] and click **Expressions**.</span></span>  
  
     <span data-ttu-id="80bde-125">Das Textfeld **Ausdruck festlegen für: Wert** enthält den Ausdruck =Globals!PageNumber.</span><span class="sxs-lookup"><span data-stu-id="80bde-125">The **Set Expression for: Value** text box contains the expression =Globals!PageNumber.</span></span>  
  
2.  <span data-ttu-id="80bde-126">Setzen Sie den Cursor nach dem Gleichheitszeichen (=), und geben Sie `"Page " &` ein.</span><span class="sxs-lookup"><span data-stu-id="80bde-126">Place the cursor after the = sign and type `"Page " &`.</span></span>  
  
     <span data-ttu-id="80bde-127">Der Ausdruck ist jetzt "="Seite "&Globals!PageNumber".</span><span class="sxs-lookup"><span data-stu-id="80bde-127">The expression is now  ="Page "&Globals!PageNumber</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-add-total-number-of-pages-after-the-page-number"></a><span data-ttu-id="80bde-128">So fügen Sie Gesamtzahl von Seiten nach der Seitenzahl hinzu</span><span class="sxs-lookup"><span data-stu-id="80bde-128">To add total number of pages after the page number</span></span>  
  
1.  <span data-ttu-id="80bde-129">Klicken Sie mit der rechten Maustaste auf das Textfeld mit dem Ausdruck, und klicken Sie auf **Ausdrücke**.</span><span class="sxs-lookup"><span data-stu-id="80bde-129">Right click the text box with the expression and click **Expressions**.</span></span>  
  
2.  <span data-ttu-id="80bde-130">Geben Sie **&„von“&** am Ende des Ausdrucks ein.</span><span class="sxs-lookup"><span data-stu-id="80bde-130">Type **&" of "&** at the end of the expression.</span></span>  
  
3.  <span data-ttu-id="80bde-131">Erweitern Sie im Bereich „Kategorie“ die Option **Integrierte Felder** , und doppelklicken Sie auf **TotalPages**.</span><span class="sxs-lookup"><span data-stu-id="80bde-131">In the Category pane, expand **Built-in Fields** and double-click **TotalPages**.</span></span>  
  
     <span data-ttu-id="80bde-132">Der Ausdruck ist jetzt ="Page "&Globals! PageNumber &" von "&Globals!TotalPages".</span><span class="sxs-lookup"><span data-stu-id="80bde-132">The expression is now ="Page "&Globals!PageNumber &" of "&Globals!TotalPages</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="80bde-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="80bde-133">See Also</span></span>  
 <span data-ttu-id="80bde-134">[Seitenkopf- und Seitenfußzeilen &#40;Berichts-Generator und SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="80bde-134">[Page Headers and Footers &#40;Report Builder and SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="80bde-135">Formatieren von Text in einem Textfeld &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="80bde-135">Format Text in a Text Box &#40;Report Builder and SSRS&#41;</span></span>](format-text-in-a-text-box-report-builder-and-ssrs.md)  
  
  
