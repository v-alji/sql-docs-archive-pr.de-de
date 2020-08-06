---
title: Hinzufügen eines Unterberichts und Hinzufügen von Parametern (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10093"
- sql12.rtp.rptdesigner.subreportproperties.general.f1
ms.assetid: 94f960f8-a629-4f1e-8277-c3b8f0680d98
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3aeede343763ea5fc8fbdfde179208f98fa1a2ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608292"
---
# <a name="add-a-subreport-and-parameters-report-builder-and-ssrs"></a><span data-ttu-id="ff4c5-102">Hinzufügen eines Unterberichts und Hinzufügen von Parametern (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="ff4c5-102">Add a Subreport and Parameters (Report Builder and SSRS)</span></span>
  <span data-ttu-id="ff4c5-103">Fügen Sie einem Bericht Unterberichte hinzu, wenn Sie einen Hauptbericht erstellen möchten, der mehrere verwandte Berichte enthält.</span><span class="sxs-lookup"><span data-stu-id="ff4c5-103">Add subreports to a report when you want to create a main report that is a container for multiple related reports.</span></span> <span data-ttu-id="ff4c5-104">Ein Unterbericht ist ein Verweis auf einen anderen Bericht.</span><span class="sxs-lookup"><span data-stu-id="ff4c5-104">A subreport is a reference to another report.</span></span> <span data-ttu-id="ff4c5-105">Um die Berichte über Datenwerte zu verbinden (z. B. damit mehrere Berichte Daten für denselben Kunden anzeigen), müssen Sie einen parametrisierten Bericht erstellen (z. B. einen Bericht, der die Details für einen bestimmten Kunden enthält).</span><span class="sxs-lookup"><span data-stu-id="ff4c5-105">To relate the reports through data values (for example, to have multiple reports show data for the same customer), you must design a parameterized report (for example, a report that shows the details for a specific customer) as the subreport.</span></span> <span data-ttu-id="ff4c5-106">Wenn Sie dem Hauptbericht einen Unterbericht hinzufügen, können Sie Parameter angeben, die an den Unterbericht übergeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ff4c5-106">When you add a subreport to the main report, you can specify parameters to pass to the subreport.</span></span>  
  
 <span data-ttu-id="ff4c5-107">Sie können Unterberichte auch dynamischen Zeilen oder Spalten in einer Tabelle oder Matrix hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ff4c5-107">You can also add subreports to dynamic rows or columns in a table or matrix.</span></span> <span data-ttu-id="ff4c5-108">Bei der Verarbeitung des Hauptberichts wird der Unterbericht für jede Zeile verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="ff4c5-108">When the main report is processed, the subreport is processed for each row.</span></span> <span data-ttu-id="ff4c5-109">Überlegen Sie in diesem Fall, ob Sie den gewünschten Effekt mit Datenbereichen oder mit geschachtelten Datenbereichen erzielen können.</span><span class="sxs-lookup"><span data-stu-id="ff4c5-109">In this case, consider whether you can achieve the desired effect by using data regions or nested data regions.</span></span>  
  
 <span data-ttu-id="ff4c5-110">Um einem Bericht einen Unterbericht hinzuzufügen, müssen Sie zuerst den Bericht erstellen, der als Unterbericht fungiert.</span><span class="sxs-lookup"><span data-stu-id="ff4c5-110">To add a subreport to a report, you must first create the report that will act as the subreport.</span></span> <span data-ttu-id="ff4c5-111">Weitere Informationen zum Erstellen des Unterberichts finden Sie unter [Unterberichte &#40;Berichts-Generator und SSRS&#41;](subreports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="ff4c5-111">For more information on creating the subreport, see [Subreports &#40;Report Builder and SSRS&#41;](subreports-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-subreport"></a><span data-ttu-id="ff4c5-112">So fügen Sie einen Unterbericht hinzu</span><span class="sxs-lookup"><span data-stu-id="ff4c5-112">To add a subreport</span></span>  
  
1.  <span data-ttu-id="ff4c5-113">Klicken Sie auf der Registerkarte **Einfügen** auf **Unterbericht**.</span><span class="sxs-lookup"><span data-stu-id="ff4c5-113">On the **Insert** tab, click **Subreport**.</span></span>  
  
2.  <span data-ttu-id="ff4c5-114">Klicken Sie auf der Entwurfsoberfläche auf eine Stelle im Bericht, und ziehen Sie ein Feld, bis es die gewünschte Größe für den Unterbericht erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="ff4c5-114">On the design surface, click a location on the report and then drag a box to the desired size of the subreport.</span></span> <span data-ttu-id="ff4c5-115">Alternativ können Sie auf die Entwurfsoberfläche klicken, um einen Unterbericht mit der Standardgröße zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ff4c5-115">Alternatively, click the design surface to create a subreport of default size.</span></span>  
  
3.  <span data-ttu-id="ff4c5-116">Klicken Sie mit der rechten Maustaste auf den Unterbericht, und klicken Sie anschließend auf **Eigenschaften des Unterberichts**.</span><span class="sxs-lookup"><span data-stu-id="ff4c5-116">Right-click the subreport, and then click **Subreport Properties**.</span></span>  
  
4.  <span data-ttu-id="ff4c5-117">Geben Sie im Dialogfeld **Eigenschaften des Unterberichts** im Textfeld **Name** einen Namen ein, oder übernehmen Sie den Standardnamen.</span><span class="sxs-lookup"><span data-stu-id="ff4c5-117">In the **Subreport Properties** dialog box, type a name in the **Name** text box or accept the default.</span></span> <span data-ttu-id="ff4c5-118">Der Name muss innerhalb des Berichts eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="ff4c5-118">The name must be unique within the report.</span></span> <span data-ttu-id="ff4c5-119">Standardmäßig wird ein allgemeiner Name zugewiesen, z. B. Subreport1 oder Subreport2.</span><span class="sxs-lookup"><span data-stu-id="ff4c5-119">By default, a general name such as Subreport1 or Subreport2 is assigned.</span></span>  
  
5.  <span data-ttu-id="ff4c5-120">Klicken Sie im Feld **Diesen Bericht als Unterbericht verwenden** auf **Durchsuchen**, oder geben Sie den Namen des Berichts ein.</span><span class="sxs-lookup"><span data-stu-id="ff4c5-120">In the **Use this report as a subreport** box, click **Browse**, or type the name of the report.</span></span> <span data-ttu-id="ff4c5-121">Es wird empfohlen, auf **Durchsuchen** zu klicken, da der Pfad zum Unterbericht automatisch angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ff4c5-121">Clicking **Browse** is preferred because the path to the subreport will be specified automatically.</span></span> <span data-ttu-id="ff4c5-122">Zum Angeben des Berichts stehen Ihnen mehrere Möglichkeiten zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="ff4c5-122">You can specify the report in the several ways.</span></span> <span data-ttu-id="ff4c5-123">Weitere Informationen finden Sie unter [Angeben von Pfaden zu externen Elementen &#40;Berichts-Generator und SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="ff4c5-123">For more information, see [Specifying Paths to External Items &#40;Report Builder and SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span></span>  
  
6.  <span data-ttu-id="ff4c5-124">(Optional) Klicken Sie für **Rahmen an Seitenumbruch auslassen** auf **Ja** , damit in der Mitte des Unterberichts kein Rahmen gerendert wird, wenn der Unterbericht mehrere Seiten umfasst.</span><span class="sxs-lookup"><span data-stu-id="ff4c5-124">(Optional) Click **Yes** for **Omit border on page break** to prevent a border from being rendered in the middle of the subreport if the subreport spans more than one page.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-specify-parameters-to-pass-to-a-subreport"></a><span data-ttu-id="ff4c5-125">So geben Sie Parameter an, die an einen Unterbericht übergeben werden</span><span class="sxs-lookup"><span data-stu-id="ff4c5-125">To specify parameters to pass to a subreport</span></span>  
  
1.  <span data-ttu-id="ff4c5-126">Klicken Sie in der Entwurfsansicht mit der rechten Maustaste auf den Unterbericht, und klicken Sie anschließend auf **Eigenschaften des Unterberichts**.</span><span class="sxs-lookup"><span data-stu-id="ff4c5-126">In Design view, right-click the subreport and then click **Subreport Properties**.</span></span>  
  
2.  <span data-ttu-id="ff4c5-127">Klicken Sie im Dialogfeld **Eigenschaften des Unterberichts** auf **Parameter**.</span><span class="sxs-lookup"><span data-stu-id="ff4c5-127">In the **Subreport Properties** dialog box, click **Parameters**.</span></span>  
  
3.  <span data-ttu-id="ff4c5-128">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ff4c5-128">Click **Add**.</span></span> <span data-ttu-id="ff4c5-129">Dem Parameterraster wird eine neue Zeile hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ff4c5-129">A new row is added to the parameter grid.</span></span>  
  
4.  <span data-ttu-id="ff4c5-130">Geben Sie im Textfeld **Name** den Namen eines Parameters im Unterbericht ein, oder wählen Sie den Namen im Listenfeld.</span><span class="sxs-lookup"><span data-stu-id="ff4c5-130">In the **Name** text box, type the name of a parameter in the subreport or choose it from the list box.</span></span> <span data-ttu-id="ff4c5-131">Dieser Name muss mit dem Namen eines Berichtsparameters im Unterbericht übereinstimmen, nicht mit dem Namen eines Abfrageparameters.</span><span class="sxs-lookup"><span data-stu-id="ff4c5-131">This name must match a report parameter, not a query parameter, in the subreport.</span></span>  
  
5.  <span data-ttu-id="ff4c5-132">Geben Sie im Listenfeld **Wert** einen Wert ein, oder wählen Sie einen Wert aus. Dieser Wert wird an den Unterbericht übergeben.</span><span class="sxs-lookup"><span data-stu-id="ff4c5-132">In the **Value** list box, type or select a value to pass to the subreport.</span></span> <span data-ttu-id="ff4c5-133">Bei dem Wert kann es sich um statischen Text oder einen Ausdruck handeln, der auf ein Feld oder ein anderes Objekt im Hauptbericht verweist.</span><span class="sxs-lookup"><span data-stu-id="ff4c5-133">This value can be static text or an expression that references a field or other object in the main report.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ff4c5-134">In Berichts-Generator: Wenn ein Parameter in der Liste **Parameter** nicht vorhanden ist und für den Unterbericht ein Standardwert definiert ist, wird der Unterbericht korrekt verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="ff4c5-134">In Report Builder, if a parameter is missing from the **Parameters** list and the subreport has a default value defined, the subreport will be processed correctly.</span></span>  
    >   
    >  <span data-ttu-id="ff4c5-135">In Berichts-Designer müssen alle Parameter, die vom Unterbericht benötigt werden, in der Liste **Parameter** enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="ff4c5-135">In Report Designer, all parameters that are required by the subreport must be included in the **Parameters** list.</span></span> <span data-ttu-id="ff4c5-136">Fehlt ein benötigter Parameter, wird der Unterbericht nicht richtig im Hauptbericht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ff4c5-136">If a required parameter is missing, the subreport is not displayed correctly in the main report.</span></span>  
  
6.  <span data-ttu-id="ff4c5-137">Wiederholen Sie die Schritte 3 bis 5, um einen Namen und Wert für jeden Unterberichtsparameter anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ff4c5-137">Repeat steps 3-5 to specify a name and value for each subreport parameter.</span></span>  
  
7.  <span data-ttu-id="ff4c5-138">Klicken Sie auf den Parameter im Parameterraster, und klicken Sie dann auf **Löschen**, um einen Unterberichtsparameter zu löschen.</span><span class="sxs-lookup"><span data-stu-id="ff4c5-138">To delete a subreport parameter, click the parameter in the parameter grid, and then click **Delete**.</span></span>  
  
8.  <span data-ttu-id="ff4c5-139">Um die Reihenfolge eines Unterberichtsparameters zu ändern, klicken Sie auf den Parameter und klicken dann auf die Nach-oben- oder Nach-unten-Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="ff4c5-139">To change the order of a subreport parameter, click the parameter, and then click the up button or the down button.</span></span>  
  
     <span data-ttu-id="ff4c5-140">Wenn Sie die Reihenfolge eines Unterberichtsparameters ändern, wirkt sich dies nicht auf die Verarbeitung des Unterberichts aus.</span><span class="sxs-lookup"><span data-stu-id="ff4c5-140">Changing the order of a subreport parameter does not affect the processing of the subreport.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff4c5-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ff4c5-141">See Also</span></span>  
 <span data-ttu-id="ff4c5-142">[Unterberichte &#40;Berichts-Generator und SSRS&#41;](subreports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ff4c5-142">[Subreports &#40;Report Builder and SSRS&#41;](subreports-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="ff4c5-143">Renderingverhalten (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="ff4c5-143">Rendering Behaviors &#40;Report Builder  and SSRS&#41;</span></span>](rendering-behaviors-report-builder-and-ssrs.md)  
  
  
