---
title: Hinzufügen von HTML in einem Bericht (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 30bd631a-f774-48e7-a13a-b6c2eb54d9bb
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 605c84843d62fb664a8a665a3fc3b024f8f87186
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722534"
---
# <a name="add-html-into-a-report-report-builder-and-ssrs"></a><span data-ttu-id="942fb-102">Hinzufügen von HTML in einem Bericht (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="942fb-102">Add HTML into a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="942fb-103">Mithilfe eines Platzhalters können Sie HTML aus einem Feld im Dataset in einen Bericht importieren.</span><span class="sxs-lookup"><span data-stu-id="942fb-103">Using a placeholder, you can import HTML from a field in your dataset for use in the report.</span></span> <span data-ttu-id="942fb-104">Standardmäßig steht ein Platzhalter für einfachen Text, daher müssen Sie den Markuptyp des Platzhalters zu HTML ändern.</span><span class="sxs-lookup"><span data-stu-id="942fb-104">By default, a placeholder represents plain text, so you will need to change the placeholder mark-up type to HTML.</span></span> <span data-ttu-id="942fb-105">Weitere Informationen finden Sie unter [Importieren von HTML in einen Bericht (Berichts-Generator und SSRS)](importing-html-into-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="942fb-105">For more information, see [Importing HTML into a Report &#40;Report Builder and SSRS&#41;](importing-html-into-a-report-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-html-from-a-field-in-your-dataset-into-a-text-box"></a><span data-ttu-id="942fb-106">So fügen Sie einem Textfeld HTML aus einem Datasetfeld hinzu</span><span class="sxs-lookup"><span data-stu-id="942fb-106">To add HTML from a field in your dataset into a text box</span></span>  
  
1.  <span data-ttu-id="942fb-107">Klicken Sie auf der Registerkarte **Einfügen** auf **Liste**.</span><span class="sxs-lookup"><span data-stu-id="942fb-107">On the **Insert** tab, click **List**.</span></span> <span data-ttu-id="942fb-108">Klicken Sie auf die Entwurfsoberfläche, und erstellen Sie dann durch Ziehen ein Feld mit der gewünschten Größe.</span><span class="sxs-lookup"><span data-stu-id="942fb-108">Click the design surface, and then drag to create a box that is the size you want.</span></span>  
  
     <span data-ttu-id="942fb-109">Das Dialogfeld **Dataseteigenschaften** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="942fb-109">The **Dataset Properties** dialog box opens.</span></span> <span data-ttu-id="942fb-110">Sie können ein freigegebenes Dataset oder ein im Bericht eingebettetes Dataset verwenden.</span><span class="sxs-lookup"><span data-stu-id="942fb-110">You can use a shared dataset or a dataset embedded in your report.</span></span> <span data-ttu-id="942fb-111">Weitere Informationen finden Sie unter [Dataseteigenschaften (Dialogfeld), Abfrage (Berichts-Generator)](../report-data/dataset-properties-dialog-box-query-report-builder.md) oder [Dataseteigenschaften (Dialogfeld), Abfrage](../dataset-properties-dialog-box-query.md).</span><span class="sxs-lookup"><span data-stu-id="942fb-111">For more information, click [Dataset Properties Dialog Box, Query &#40;Report Builder&#41;](../report-data/dataset-properties-dialog-box-query-report-builder.md) or [Dataset Properties Dialog Box, Query](../dataset-properties-dialog-box-query.md).</span></span>  
  
2.  <span data-ttu-id="942fb-112">Klicken Sie auf der Registerkarte **Einfügen** auf **Textfeld**.</span><span class="sxs-lookup"><span data-stu-id="942fb-112">On the **Insert** tab, click **Text Box**.</span></span> <span data-ttu-id="942fb-113">Klicken Sie in die Liste, und erstellen Sie dann durch Ziehen ein Feld mit der gewünschten Größe.</span><span class="sxs-lookup"><span data-stu-id="942fb-113">Click in the list, and then drag to create a box that is the size you want.</span></span>  
  
3.  <span data-ttu-id="942fb-114">Ziehen Sie ein HTML-Feld aus dem Dataset in das Textfeld.</span><span class="sxs-lookup"><span data-stu-id="942fb-114">Drag an HTML field from your dataset into the text box.</span></span> <span data-ttu-id="942fb-115">Es wird ein Platzhalter für das Feld erstellt.</span><span class="sxs-lookup"><span data-stu-id="942fb-115">A placeholder is created for your field.</span></span>  
  
4.  <span data-ttu-id="942fb-116">Klicken Sie mit der rechten Maustaste auf den Platzhalter, und klicken Sie anschließend auf **Platzhaltereigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="942fb-116">Right-click the placeholder, and then click **Placeholder Properties**.</span></span>  
  
5.  <span data-ttu-id="942fb-117">Vergewissern Sie sich, dass auf der Registerkarte **Allgemein** im Feld **Wert** ein Ausdruck steht, der anhand des in Schritt 3 eingefügten Felds ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="942fb-117">On the **General** tab, verify that the **Value** box contains an expression that evaluates to the field you dropped in step 3.</span></span>  
  
6.  <span data-ttu-id="942fb-118">Klicken Sie auf **HTML – HTML-Tags als Formate interpretieren**.</span><span class="sxs-lookup"><span data-stu-id="942fb-118">Click **HTML - Interpret HTML tags as styles**.</span></span> <span data-ttu-id="942fb-119">Hierdurch wird das Feld als HTML ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="942fb-119">This causes the field to be evaluated as HTML.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="942fb-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="942fb-120">See Also</span></span>  
 <span data-ttu-id="942fb-121">[Formatieren von Zahlen und Datumsangaben &#40;Berichts-Generator und SSRS&#41;](formatting-numbers-and-dates-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="942fb-121">[Formatting Numbers and Dates &#40;Report Builder and SSRS&#41;](formatting-numbers-and-dates-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="942fb-122">[Formatieren von Linien, Farben und Bildern (Berichts-Generator und SSRS)](images-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="942fb-122">[Formatting Lines, Colors, and Images &#40;Report Builder and SSRS&#41;](images-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="942fb-123">Platzhaltereigenschaften (Dialogfeld), Allgemein (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="942fb-123">Placeholder Properties Dialog Box, General &#40;Report Builder and SSRS&#41;</span></span>](../placeholder-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  
