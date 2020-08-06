---
title: Hinzufügen von Einzügen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 9dce05c1-c52f-455d-8b8d-6f303e242760
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2d0b7ee8819f98df5e5658321a3d950ca31083b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619503"
---
# <a name="adding-indentation"></a><span data-ttu-id="fa32c-102">Hinzufügen von Einzügen</span><span class="sxs-lookup"><span data-stu-id="fa32c-102">Adding Indentation</span></span>
  <span data-ttu-id="fa32c-103">Der Abfrage-Editor ermöglicht es Ihnen, mit nur einem Schritt einen Einzug für große Codeabschnitte festzulegen. Außerdem können Sie die Größe des Einzugs ändern.</span><span class="sxs-lookup"><span data-stu-id="fa32c-103">Query Editor allows you to indent large sections of code with a single step, and you can change the amount of the indentation.</span></span>  
  
## <a name="indenting-code"></a><span data-ttu-id="fa32c-104">Festlegen von Einzügen für Code</span><span class="sxs-lookup"><span data-stu-id="fa32c-104">Indenting Code</span></span>  
  
#### <a name="to-indent-multiple-lines-of-code"></a><span data-ttu-id="fa32c-105">So legen Sie einen Einzug für mehrere Codezeilen fest</span><span class="sxs-lookup"><span data-stu-id="fa32c-105">To indent multiple lines of code</span></span>  
  
1.  <span data-ttu-id="fa32c-106">Klicken Sie auf der Symbolleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="fa32c-106">On the toolbar, click **New Query**.</span></span>  
  
2.  <span data-ttu-id="fa32c-107">Erstellen Sie eine zweite Abfrage, über die die Spalten **BusinessEntityID**, FirstName, **MiddleName**und **LastName** aus der Tabelle **Person** der Schemas **Person** ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="fa32c-107">Create a second query that selects the **BusinessEntityID**, FirstName, **MiddleName**, and **LastName** columns from the **Person** table of the **Person** schema.</span></span> <span data-ttu-id="fa32c-108">Platzieren Sie jede Spalte in eine separate Zeile, sodass der Code wie folgt aussieht:</span><span class="sxs-lookup"><span data-stu-id="fa32c-108">Place each column on a separate line so the code looks like this:</span></span>  
  
    ```  
    -- Search for a contact  
    SELECT   
    BusinessEntityID,  
    FirstName,   
    MiddleName,   
    LastName  
    FROM Person.Person  
    WHERE LastName = 'Sanchez';  
    GO  
    ```  
  
3.  <span data-ttu-id="fa32c-109">Markieren Sie den gesamten Text von `BusinessEntityID` bis `LastName`.</span><span class="sxs-lookup"><span data-stu-id="fa32c-109">Select all text from `BusinessEntityID` to `LastName`.</span></span>  
  
4.  <span data-ttu-id="fa32c-110">Klicken Sie auf der Symbolleiste **SQL-Editor** auf **Einzug vergrößern** , um für alle Zeilen gleichzeitig einen Einzug festzulegen.</span><span class="sxs-lookup"><span data-stu-id="fa32c-110">On the **SQL Editor** toolbar, click **Increase Indent** to indent all the lines at once.</span></span>  
  
#### <a name="to-change-the-default-indentation"></a><span data-ttu-id="fa32c-111">So ändern Sie den Standardeinzug</span><span class="sxs-lookup"><span data-stu-id="fa32c-111">To change the default indentation</span></span>  
  
1.  <span data-ttu-id="fa32c-112">Klicken Sie im Menü **Extras** auf **Optionen**.</span><span class="sxs-lookup"><span data-stu-id="fa32c-112">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="fa32c-113">Erweitern Sie **Text-Editor**, erweitern Sie **Alle Sprachen**, und klicken Sie dann auf **Tabstopps** , um die gewünschten Werte für die Einzüge festzulegen.</span><span class="sxs-lookup"><span data-stu-id="fa32c-113">Expand **Text Editor**, expand **All Languages**, and click **Tabs** , and set indentation values as appropriate.</span></span> <span data-ttu-id="fa32c-114">Beachten Sie, dass Sie die Größe des Einzugs und der Tabstopps festlegen können und angeben können, ob Tabstopps in Leerzeichen umgewandelt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="fa32c-114">Note that you can change the size of the indent as well as the size of tabs, and whether tabs are converted to spaces.</span></span>  
  
     <span data-ttu-id="fa32c-115">![Darstellung des Dialogfelds 'Registerkarten'](media/tabsdialog.gif "Darstellung des Dialogfelds 'Registerkarten'")</span><span class="sxs-lookup"><span data-stu-id="fa32c-115">![Appearance of the Tabs dialog box](media/tabsdialog.gif "Appearance of the Tabs dialog box")</span></span>  
  
3.  <span data-ttu-id="fa32c-116">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="fa32c-116">Click **OK**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="fa32c-117">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="fa32c-117">Next Task in Lesson</span></span>  
 [<span data-ttu-id="fa32c-118">Maximieren des Abfrage-Editors</span><span class="sxs-lookup"><span data-stu-id="fa32c-118">Maximizing Query Editor</span></span>](lesson-2-3-maximizing-query-editor.md)  
  
  
