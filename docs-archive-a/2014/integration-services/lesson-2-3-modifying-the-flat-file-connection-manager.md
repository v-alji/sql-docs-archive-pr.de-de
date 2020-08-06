---
title: 'Schritt 3: Ändern des Flatfile-Verbindungs-Managers | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 459e3995-2116-4f15-aaa2-32f26113869c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b897f9412a8f2978ebe4137e3e79bf1d28c97844
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609316"
---
# <a name="step-3-modifying-the-flat-file-connection-manager"></a><span data-ttu-id="5931d-102">Schritt 3: Ändern des Flatfile-Verbindungs-Managers</span><span class="sxs-lookup"><span data-stu-id="5931d-102">Step 3: Modifying the Flat File Connection Manager</span></span>
  <span data-ttu-id="5931d-103">In dieser Aufgabe ändern Sie den in Lektion 1 konfigurierten und erstellten Flatfile-Verbindungs-Manager.</span><span class="sxs-lookup"><span data-stu-id="5931d-103">In this task, you will modify the Flat File connection manager that you created and configured in Lesson 1.</span></span> <span data-ttu-id="5931d-104">Bei der ursprünglichen Erstellung wurde der Flatfile-Verbindungs-Manager so konfiguriert, dass eine einzelne Datei statisch geladen wird.</span><span class="sxs-lookup"><span data-stu-id="5931d-104">When originally created, the Flat File connection manager was configured to statically load a single file.</span></span> <span data-ttu-id="5931d-105">Damit der Flatfile-Verbindungs-Manager Dateien iterativ laden kann, müssen Sie die ConnectionString-Eigenschaft des Verbindungs-Managers so ändern, dass die benutzerdefinierte Variable `User:varFileName`, die den Pfad der zur Laufzeit zu ladenden Datei enthält, akzeptiert wird.</span><span class="sxs-lookup"><span data-stu-id="5931d-105">To enable the Flat File connection manager to iteratively load files, you must modify the ConnectionString property of the connection manager to accept the user-defined variable `User:varFileName`, which contains the path of the file to be loaded at run time.</span></span>  
  
 <span data-ttu-id="5931d-106">Indem Sie den Verbindungs-Manager so ändern, dass er den Wert der benutzerdefinierten Variable `User::varFileName`verwendet, um die ConnectionString-Eigenschaft des Verbindungs-Managers aufzufüllen, kann der Verbindungs-Manager eine Verbindung mit verschiedenen Flatfiles herstellen.</span><span class="sxs-lookup"><span data-stu-id="5931d-106">By modifying the connection manager to use the value of the user-defined variable, `User::varFileName`, to populate the ConnectionString property of the connection manager, the connection manager will be able to connect to different flat files.</span></span> <span data-ttu-id="5931d-107">Zur Laufzeit aktualisiert dann jede Iteration des Foreach-Schleifencontainers die `User::varFileName` -Variable.</span><span class="sxs-lookup"><span data-stu-id="5931d-107">At run time, each iteration of the Foreach Loop container will dynamically update the `User::varFileName` variable.</span></span> <span data-ttu-id="5931d-108">Durch das Aktualisieren der Variable stellt der Verbindungs-Manager wiederum eine Verbindung zu einer anderen Flatfile her, und der Datenflusstask verarbeitet andere Daten.</span><span class="sxs-lookup"><span data-stu-id="5931d-108">Updating the variable, in turn, causes the connection manager to connect to a different flat file, and the data flow task to process a different set of data.</span></span>  
  
### <a name="to-configure-the-flat-file-connection-manager-to-use-a-variable-for-the-connection-string"></a><span data-ttu-id="5931d-109">So konfigurieren Sie den Flatfile-Verbindungs-Manager auf die Verwendung einer Variable für die Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="5931d-109">To configure the Flat File connection manager to use a variable for the connection string</span></span>  
  
1.  <span data-ttu-id="5931d-110">Klicken Sie im Bereich **Verbindungs-Manager** mit der rechten Maustaste auf **Sample Flat File Source Data**(Beispielquelldaten von Flatfiles), und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="5931d-110">In the **Connection Managers** pane, right-click **Sample Flat File Source Data**, and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="5931d-111">Klicken Sie im Eigenschaftenfenster für **Ausdrücke**in die leere Zelle, und klicken Sie dann auf die Schaltfläche mit den Auslassungs Punkten **(...)**.</span><span class="sxs-lookup"><span data-stu-id="5931d-111">In the Properties window, for **Expressions**, click in the empty cell, and then click the ellipsis button **(...)**.</span></span>  
  
3.  <span data-ttu-id="5931d-112">Geben Sie im Dialogfeld **Eigenschafts Ausdrucks-Editor** in der Spalte **Eigenschaft** den Text ein, oder wählen Sie ihn aus `ConnectionString` .</span><span class="sxs-lookup"><span data-stu-id="5931d-112">In the **Property Expressions Editor** dialog box, in the **Property** column, type or select `ConnectionString`.</span></span>  
  
4.  <span data-ttu-id="5931d-113">Klicken Sie in der Spalte **Ausdruck** auf die Schaltfläche mit den Auslassungs Punkten **(...)** , um das Dialogfeld **Ausdrucks** -Generator zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="5931d-113">In the **Expression** column, click the ellipsis button **(...)** to open the **Expression Builder** dialog box.</span></span>  
  
5.  <span data-ttu-id="5931d-114">Erweitern Sie im Dialogfeld **Ausdrucks-Generator** den Knoten **Variablen** .</span><span class="sxs-lookup"><span data-stu-id="5931d-114">In the **Expression Builder** dialog box, expand the **Variables** node.</span></span>  
  
6.  <span data-ttu-id="5931d-115">Ziehen Sie die Variable **User:: varFileName**in das Feld **Ausdruck** .</span><span class="sxs-lookup"><span data-stu-id="5931d-115">Drag the variable, **User::varFileName**, into the **Expression** box.</span></span>  
  
7.  <span data-ttu-id="5931d-116">Klicken Sie auf **OK** , um das Dialogfeld **Ausdrucks-Generator** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="5931d-116">Click **OK** to close the **Expression Builder** dialog box.</span></span>  
  
8.  <span data-ttu-id="5931d-117">Klicken Sie auf **OK** , um das Dialogfeld **Eigenschaftsausdrucks-Editor** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="5931d-117">Click **OK** again to close the **Property Expressions Editor** dialog box.</span></span>  
  
## <a name="next-lesson-task"></a><span data-ttu-id="5931d-118">Aufgabe in der nächsten Lektion</span><span class="sxs-lookup"><span data-stu-id="5931d-118">Next Lesson Task</span></span>  
 [<span data-ttu-id="5931d-119">Schritt 4: Testen des Tutorialpakets aus Lektion 2</span><span class="sxs-lookup"><span data-stu-id="5931d-119">Step 4: Testing the Lesson 2 Tutorial Package</span></span>](../integration-services/lesson-2-4-testing-the-lesson-2-tutorial-package.md)  
  
  
