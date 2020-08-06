---
title: Definieren einer Dimension | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 112696db-3838-4b50-91bd-d2ce5fa04ee5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2eb7a695ffc2c0588396a4a9ea655983c26cc719
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608034"
---
# <a name="defining-a-dimension"></a><span data-ttu-id="99638-102">Definieren einer Dimension.</span><span class="sxs-lookup"><span data-stu-id="99638-102">Defining a Dimension</span></span>
  <span data-ttu-id="99638-103">In der folgenden Aufgabe verwenden Sie den Dimensions-Assistenten, um eine Date-Dimension zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="99638-103">In the following task, you will use the Dimension Wizard to build a Date dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="99638-104">Für diese Lektion ist es erforderlich, dass Sie alle Prozeduren in Lektion 1 abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="99638-104">This lesson requires that you have completed all the procedures in Lesson 1.</span></span>  
  
### <a name="to-define-a-dimension"></a><span data-ttu-id="99638-105">So definieren Sie eine Dimension</span><span class="sxs-lookup"><span data-stu-id="99638-105">To define a dimension</span></span>  
  
1.  <span data-ttu-id="99638-106">Klicken Sie im Projektmappen-Explorer (auf der rechten Seite von Microsoft Visual Studio) mit der rechten Maustaste auf **Dimensionen**, und klicken Sie anschließend auf **Neue Dimension**.</span><span class="sxs-lookup"><span data-stu-id="99638-106">In Solution Explorer (on the right side of Microsoft Visual Studio), right-click **Dimensions**, and then click **New Dimension**.</span></span> <span data-ttu-id="99638-107">Der Dimensions-Assistent wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="99638-107">The Dimension Wizard appears.</span></span>  
  
2.  <span data-ttu-id="99638-108">Klicken Sie auf der Seite **Willkommen beim Dimensions-Assistenten** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="99638-108">On the **Welcome to the Dimension Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="99638-109">Überprüfen Sie, ob die Option **Vorhandene Tabelle verwenden** auf der Seite **Erstellungsmethode auswählen** ausgewählt ist, und klicken Sie anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="99638-109">On the **Select Creation Method** page, verify that the **Use an existing table** option is selected, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="99638-110">Überprüfen Sie auf der Seite **Quellinformationen angeben** , ob die **Adventure Works DW 2012** -Datenquellensicht ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="99638-110">On the **Specify Source Information** page, verify that the **Adventure Works DW 2012** data source view is selected.</span></span>  
  
5.  <span data-ttu-id="99638-111">Wählen Sie in der Liste **Haupttabelle** den Eintrag **Date**aus.</span><span class="sxs-lookup"><span data-stu-id="99638-111">In the **Main table** list, select **Date**.</span></span>  
  
6.  <span data-ttu-id="99638-112">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="99638-112">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="99638-113">Aktivieren Sie auf der Seite **Dimensionsattribute auswählen** die Kontrollkästchen neben den folgenden Attributen:</span><span class="sxs-lookup"><span data-stu-id="99638-113">On the **Select Dimension Attributes** page, select the check boxes next to the following attributes:</span></span>  
  
    -   <span data-ttu-id="99638-114">**Date Key**</span><span class="sxs-lookup"><span data-stu-id="99638-114">**Date Key**</span></span>  
  
    -   <span data-ttu-id="99638-115">**Full Date Alternate Key**</span><span class="sxs-lookup"><span data-stu-id="99638-115">**Full Date Alternate Key**</span></span>  
  
    -   <span data-ttu-id="99638-116">**English Month Name**</span><span class="sxs-lookup"><span data-stu-id="99638-116">**English Month Name**</span></span>  
  
    -   <span data-ttu-id="99638-117">**Kalenderquartal**</span><span class="sxs-lookup"><span data-stu-id="99638-117">**Calendar Quarter**</span></span>  
  
    -   <span data-ttu-id="99638-118">**Kalenderjahr**</span><span class="sxs-lookup"><span data-stu-id="99638-118">**Calendar Year**</span></span>  
  
    -   <span data-ttu-id="99638-119">**Calendar Semester**</span><span class="sxs-lookup"><span data-stu-id="99638-119">**Calendar Semester**</span></span>  
  
8.  <span data-ttu-id="99638-120">Ändern Sie die Einstellung von der Spalte **Attributtyp** des **Full Date Alternate Key** -Attributs von **Regulär** in **Datum**.</span><span class="sxs-lookup"><span data-stu-id="99638-120">Change the setting of the **Full Date Alternate Key** attribute's **Attribute Type** column from **Regular** to **Date**.</span></span> <span data-ttu-id="99638-121">Klicken Sie hierzu auf **Regulär** in der Spalte **Attributtyp** .</span><span class="sxs-lookup"><span data-stu-id="99638-121">To do this, click **Regular** in the **Attribute Type** column.</span></span> <span data-ttu-id="99638-122">Klicken Sie anschließend auf den Pfeil, um die Optionen zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="99638-122">Then click the arrow to expand the options.</span></span> <span data-ttu-id="99638-123">Klicken Sie anschließend auf **Date**  >  **Calendar**  >  **Date**.</span><span class="sxs-lookup"><span data-stu-id="99638-123">Next, click **Date** > **Calendar** > **Date**.</span></span> <span data-ttu-id="99638-124">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="99638-124">Click **OK**.</span></span> <span data-ttu-id="99638-125">Wiederholen Sie diese Schritte, um den Attributtyp der Attribute wie folgt zu ändern:</span><span class="sxs-lookup"><span data-stu-id="99638-125">Repeat these steps to change the attribute type of the attributes as follows:</span></span>  
  
    -   <span data-ttu-id="99638-126">**English Month Name** in **Monat**</span><span class="sxs-lookup"><span data-stu-id="99638-126">**English Month Name** to **Month**</span></span>  
  
    -   <span data-ttu-id="99638-127">**Calendar Quarter** in **Quartal**</span><span class="sxs-lookup"><span data-stu-id="99638-127">**Calendar Quarter** to **Quarter**</span></span>  
  
    -   <span data-ttu-id="99638-128">**Calendar Year** zu **Jahr**</span><span class="sxs-lookup"><span data-stu-id="99638-128">**Calendar Year** to **Year**</span></span>  
  
    -   <span data-ttu-id="99638-129">**Calendar Semester** zu **Halbjahr**</span><span class="sxs-lookup"><span data-stu-id="99638-129">**Calendar Semester** to **Half Year**</span></span>  
  
9. <span data-ttu-id="99638-130">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="99638-130">Click **Next**.</span></span>  
  
10. <span data-ttu-id="99638-131">Auf der Seite **Assistenten abschließen** können Sie im Bereich Vorschau die **Date** -Dimension und ihre Attribute sehen.</span><span class="sxs-lookup"><span data-stu-id="99638-131">On the **Completing the Wizard** page, in the Preview pane, you can see the **Date** dimension and its attributes.</span></span>  
  
11. <span data-ttu-id="99638-132">Klicken Sie auf **Fertig stellen**, um den Assistenten abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="99638-132">Click **Finish** to complete the wizard.</span></span>  
  
     <span data-ttu-id="99638-133">Im Projektmappen-Explorer wird im [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial-Projekt die Date-Dimension im Ordner **Dimensionen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="99638-133">In Solution Explorer, in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project, the Date dimension appears in the **Dimensions** folder.</span></span> <span data-ttu-id="99638-134">Im Zentrum der Entwicklungsumgebung zeigt der Dimensions-Designer die Date-Dimension an.</span><span class="sxs-lookup"><span data-stu-id="99638-134">In the center of the development environment, Dimension Designer displays the Date dimension.</span></span>  
  
12. <span data-ttu-id="99638-135">Klicken Sie im Menü **File** (Datei) auf **Save All** (Alles speichern).</span><span class="sxs-lookup"><span data-stu-id="99638-135">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="99638-136">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="99638-136">Next Task in Lesson</span></span>  
 [<span data-ttu-id="99638-137">Definieren eines Cubes</span><span class="sxs-lookup"><span data-stu-id="99638-137">Defining a Cube</span></span>](lesson-2-2-defining-a-cube.md)  
  
## <a name="see-also"></a><span data-ttu-id="99638-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="99638-138">See Also</span></span>  
 <span data-ttu-id="99638-139">[Dimensionen in mehrdimensionalen Modellen](multidimensional-models/dimensions-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="99638-139">[Dimensions in Multidimensional Models](multidimensional-models/dimensions-in-multidimensional-models.md) </span></span>  
 <span data-ttu-id="99638-140">[Erstellen einer Dimension mithilfe einer vorhandenen Tabelle](multidimensional-models/create-a-dimension-by-using-an-existing-table.md) </span><span class="sxs-lookup"><span data-stu-id="99638-140">[Create a Dimension by Using an Existing Table](multidimensional-models/create-a-dimension-by-using-an-existing-table.md) </span></span>  
 [<span data-ttu-id="99638-141">Erstellen einer Dimension mit dem Dimensions-Assistenten</span><span class="sxs-lookup"><span data-stu-id="99638-141">Create a Dimension Using the Dimension Wizard</span></span>](multidimensional-models/create-a-dimension-using-the-dimension-wizard.md)  
  
  
