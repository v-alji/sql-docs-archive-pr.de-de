---
title: Generieren von Skripts
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 9711c617-3c68-4e5a-aea3-befc64d51524
author: rothja
ms.author: jroth
ms.openlocfilehash: 199d5e0c98d220861ee0dfb48a44a71675d8ba87
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622018"
---
# <a name="generate-scripts-sql-server-management-studio"></a><span data-ttu-id="9dd8b-102">Erstellen von Skripts (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="9dd8b-102">Generate Scripts (SQL Server Management Studio)</span></span>
  [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="9dd8b-103">stellt zwei Mechanismen zum Generieren von [!INCLUDE[tsql](../../includes/tsql-md.md)] -Skripts bereit.</span><span class="sxs-lookup"><span data-stu-id="9dd8b-103">provides two mechanisms for generating [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts.</span></span> <span data-ttu-id="9dd8b-104">Mithilfe des **Assistenten zum Generieren und Veröffentlichen von Skripts**können Sie Skripts für mehrere Objekte erstellen.</span><span class="sxs-lookup"><span data-stu-id="9dd8b-104">You can create scripts for multiple objects by using the **Generate and Publish Scripts Wizard.**.</span></span> <span data-ttu-id="9dd8b-105">Sie können ein Skript für einzelne Objekte oder mehrere Objekte auch über das Menü **Skript für** im **Objekt-Explorer**generieren.</span><span class="sxs-lookup"><span data-stu-id="9dd8b-105">You can also generate a script for individual objects or multiple objects by using the **Script as** menu in **Object Explorer**.</span></span>  
  
1.  <span data-ttu-id="9dd8b-106">**Auswählen einer Methode:**  [Assistent zum Generieren und Veröffentlichen von Skripts](#GenPubScriptWiz), [Objekt-Explorer-Menü "Skript für Objekttyp als"](#OEScriptAsMenu)</span><span class="sxs-lookup"><span data-stu-id="9dd8b-106">**Choose a method:**  [Generate and Publish Scripts Wizard](#GenPubScriptWiz), [Object Explorer Script As Menu](#OEScriptAsMenu)</span></span>  
  
2.  <span data-ttu-id="9dd8b-107">**So verwenden Sie das Menü "Skript für":**  [Erstellen eines Skripts für ein einzelnes Objekt](#ScriptSingleObject), [Erstellen eines Skripts für zwei Objekte mithilfe des Objekt-Explorers](#ScriptTwoObjectsOE), [Erstellen eines Skripts für zwei Objekte mithilfe von "Details zum Objekt-Explorer"](#ScriptTwoObjectsOED)</span><span class="sxs-lookup"><span data-stu-id="9dd8b-107">**To use the Script As menu:**  [Script a Single Object](#ScriptSingleObject), [Script Two Objects Using Object Explorer](#ScriptTwoObjectsOE), [Script Two Objects Using Object Explorer Details](#ScriptTwoObjectsOED)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="9dd8b-108">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="9dd8b-108">Before You Begin</span></span>  
 <span data-ttu-id="9dd8b-109">Wählen Sie den Mechanismus aus, der Ihre Anforderungen am besten erfüllt.</span><span class="sxs-lookup"><span data-stu-id="9dd8b-109">Choose the mechanism that best meets your requirements.</span></span>  
  
###  <a name="generate-and-publish-scripts-wizard"></a><a name="GenPubScriptWiz"></a> <span data-ttu-id="9dd8b-110">Assistent zum Generieren und Veröffentlichen von Skripts</span><span class="sxs-lookup"><span data-stu-id="9dd8b-110">Generate and Publish Scripts Wizard</span></span>  
 <span data-ttu-id="9dd8b-111">Verwenden Sie den **Assistenten zum Generieren und Veröffentlichen von Skripts** , um ein [!INCLUDE[tsql](../../includes/tsql-md.md)] -Skript für zahlreiche Objekte zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9dd8b-111">Use the **Generate and Publish Scripts Wizard** to create a [!INCLUDE[tsql](../../includes/tsql-md.md)] script for many objects.</span></span> <span data-ttu-id="9dd8b-112">Der Assistent generiert ein Skript für alle in einer Datenbank enthaltenen Objekte bzw. für eine ausgewählte Teilmenge der Objekte.</span><span class="sxs-lookup"><span data-stu-id="9dd8b-112">The wizard generates a script of all the objects in a database, or a subset of the objects that you select.</span></span> <span data-ttu-id="9dd8b-113">Der Assistent verfügt über viele Optionen für Skripts, z. B. ob Berechtigungen, Sortierung, Einschränkungen usw. eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9dd8b-113">The wizard has many options for your scripts, such as whether to include permissions, collation, constraints, and so on.</span></span> <span data-ttu-id="9dd8b-114">Anweisungen zum Verwenden des Assistenten finden Sie unter [Generate and Publish Scripts Wizard](generate-and-publish-scripts-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="9dd8b-114">For instructions on using the wizard, see [Generate and Publish Scripts Wizard](generate-and-publish-scripts-wizard.md).</span></span>  
  
###  <a name="object-explorer-script-as-menu"></a><a name="OEScriptAsMenu"></a> <span data-ttu-id="9dd8b-115">Objekt-Explorer-Menü "Skript für Objekttyp als"</span><span class="sxs-lookup"><span data-stu-id="9dd8b-115">Object Explorer Script As Menu</span></span>  
 <span data-ttu-id="9dd8b-116">Sie können das Objekt-Explorer-Menü **Skript für Objekttyp als** verwenden, um ein Skript für ein einzelnes Objekt, für mehrere Objekte bzw. mehrere Anweisungen für einzelne Objekte zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9dd8b-116">You can use the **Object Explorer Script as** menu to script a single object, script multiple objects, or script multible statements for a single objects.</span></span> <span data-ttu-id="9dd8b-117">Sie können unter mehreren Skripttypen auswählen: z. B. zum Erstellen, Ändern oder Löschen des Objekts.</span><span class="sxs-lookup"><span data-stu-id="9dd8b-117">You can choose one of several types of scripts; for example to create, alter, or drop the object.</span></span> <span data-ttu-id="9dd8b-118">Sie können das Skript entweder im Abfrage-Editor-Fenster, in einer Datei oder in der Zwischenablage speichern.</span><span class="sxs-lookup"><span data-stu-id="9dd8b-118">You can save the script in a Query Editor window, to a file, or to the Clipboard.</span></span> <span data-ttu-id="9dd8b-119">Das Skript wird im Unicode-Format erstellt.</span><span class="sxs-lookup"><span data-stu-id="9dd8b-119">The script is created in Unicode format.</span></span>  
  
##  <a name="to-generate-a-script-of-a-single-object"></a><a name="ScriptSingleObject"></a> <span data-ttu-id="9dd8b-120">So generieren Sie ein Skript für ein einzelnes Objekt</span><span class="sxs-lookup"><span data-stu-id="9dd8b-120">To generate a script of a single object</span></span>  
 <span data-ttu-id="9dd8b-121">**So erstellen Sie ein Skript für ein einzelnes Objekt**</span><span class="sxs-lookup"><span data-stu-id="9dd8b-121">**To script a single object**</span></span>  
  
1.  <span data-ttu-id="9dd8b-122">Stellen Sie im Objekt-Explorer eine Verbindung mit einer Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] her, und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="9dd8b-122">In Object Explorer, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="9dd8b-123">Erweitern Sie **Datenbanken**, und erweitern Sie dann die Datenbank, die das Objekt enthält, das geschrieben werden soll.</span><span class="sxs-lookup"><span data-stu-id="9dd8b-123">Expand **Databases**, and then expand the database containing the object to be scripted.</span></span>  
  
3.  <span data-ttu-id="9dd8b-124">Erweitern Sie die Kategorie des Objekts.</span><span class="sxs-lookup"><span data-stu-id="9dd8b-124">Expand the category of the object.</span></span> <span data-ttu-id="9dd8b-125">Beispiel: Erweitern Sie den Knoten **Tabellen** oder **Sichten** .</span><span class="sxs-lookup"><span data-stu-id="9dd8b-125">For example, expand the **Tables** or **Views** node.</span></span>  
  
4.  <span data-ttu-id="9dd8b-126">Klicken Sie mit der rechten Maustaste auf das Objekt, zeigen Sie auf \*\*Skript \<object type> \*\*, und zeigen Sie z. b. auf **Skript für Tabelle als**.</span><span class="sxs-lookup"><span data-stu-id="9dd8b-126">Right-click the object, point to **Script \<object type> as**, For example, point to **Script Table as**.</span></span>  
  
5.  <span data-ttu-id="9dd8b-127">Zeigen Sie auf den Skripttyp, z. B. **CREATE in** oder **ALTER in**.</span><span class="sxs-lookup"><span data-stu-id="9dd8b-127">Point to the script type, such as **Create to** or **Alter to**.</span></span>  
  
6.  <span data-ttu-id="9dd8b-128">Wählen Sie den Speicherort zum Speichern des Skripts aus, z. B. **Neues Abfrage-Editor-Fenster** oder **Zwischenablage**.</span><span class="sxs-lookup"><span data-stu-id="9dd8b-128">Select the location to save the script, such as **New Query Editor Window** or **Clipboard**.</span></span>  
  
##  <a name="to-generate-a-script-of-two-objects-using-object-explorer"></a><a name="ScriptTwoObjectsOE"></a><span data-ttu-id="9dd8b-129">So generieren Sie ein Skript mit zwei Objekten mithilfe von Objekt-Explorer</span><span class="sxs-lookup"><span data-stu-id="9dd8b-129">To generate a script of two objects using Object Explorer</span></span>  
 <span data-ttu-id="9dd8b-130">**So erstellen Sie ein Skript für zwei Objekte mithilfe des Objekt-Explorers**</span><span class="sxs-lookup"><span data-stu-id="9dd8b-130">**To script two objects using Object Explorer**</span></span>  
  
 <span data-ttu-id="9dd8b-131">Möglicherweise benötigen Sie in einigen Fällen ein Skript mit mehreren Optionen, z. B. zum Löschen und anschließenden Erstellen einer Prozedur oder zum Erstellen und anschließenden Ändern einer Tabelle.</span><span class="sxs-lookup"><span data-stu-id="9dd8b-131">Sometimes you may want a script with multiple options, such as drop a procedure and then create a procedure, or create a table and then alter a table.</span></span> <span data-ttu-id="9dd8b-132">Die folgenden Verfahren zum Generieren von Skripts für mehrere Objekte sind auch erfolgreich, wenn Sie ein Skript erstellen müssen, das auf verschiedene Objekttypen verweist, z. B. Tabellen, Sichten und gespeicherte Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="9dd8b-132">The processes below for generating scripts of multiple objects also work if you need to create a script that references different types of objects, such as tables, views, and stored procedures.</span></span>  
  
1.  <span data-ttu-id="9dd8b-133">Stellen Sie im Objekt-Explorer eine Verbindung mit einer Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] her, und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="9dd8b-133">In Object Explorer, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="9dd8b-134">Erweitern Sie **Datenbanken**, und erweitern Sie dann die Datenbank, die die Objekte enthält, die geschrieben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9dd8b-134">Expand **Databases**, and then expand the database containing the objects to be scripted.</span></span>  
  
3.  <span data-ttu-id="9dd8b-135">Klicken Sie mit der rechten Maustaste auf das erste Objekt, für das ein Skript erstellt werden soll, zeigen Sie auf \*\*Skript \<object type> \*\*, und wählen Sie unter **Speichern** unter die Optionen **neues Abfrage-Editor-Fenster** als Ausgabeziel aus.</span><span class="sxs-lookup"><span data-stu-id="9dd8b-135">Right-click the first object to be scripted, point to **Script \<object type> as**, and in the **Save as** selections chooses **New Query Editor Window** as the output destination.</span></span>  
  
4.  <span data-ttu-id="9dd8b-136">Navigieren Sie zum zweiten Objekt, für das Sie ein Skript erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="9dd8b-136">Navigate to the second object you want to script.</span></span>  
  
5.  <span data-ttu-id="9dd8b-137">Klicken Sie mit der rechten Maustaste auf das Objekt, zeigen Sie auf **Skript \<object type> als**, und wählen Sie in der Auswahl **Speichern** unter die **Zwischenablage** als Ausgabeziel aus.</span><span class="sxs-lookup"><span data-stu-id="9dd8b-137">Right-click the object, point to **Script \<object type> as**, and in the **Save as** selections chooses **Clipboard** as the output destination.</span></span>  
  
6.  <span data-ttu-id="9dd8b-138">Fügen Sie in dem für das erste Objekt geöffneten Abfrage-Editor-Fenster das Skript für das zweite Objekt aus der Zwischenablage ein.</span><span class="sxs-lookup"><span data-stu-id="9dd8b-138">In the Query Editor window opened for the first object, paste the script for the second object from the clipboard.</span></span>  
  
##  <a name="to-generate-a-script-of-two-objects-using-object-explorer-details"></a><a name="ScriptTwoObjectsOED"></a><span data-ttu-id="9dd8b-139">So generieren Sie ein Skript mit zwei Objekten mithilfe von Objekt-Explorer Details</span><span class="sxs-lookup"><span data-stu-id="9dd8b-139">To generate a script of two objects using Object Explorer Details</span></span>  
 <span data-ttu-id="9dd8b-140">**So erstellen Sie ein Skript für zwei Objekte mithilfe von "Details zum Objekt-Explorer"**</span><span class="sxs-lookup"><span data-stu-id="9dd8b-140">**To script two objects using Object Explorer Details**</span></span>  
  
 <span data-ttu-id="9dd8b-141">Sie können den Bereich **Details zum Objekt-Explorer** verwenden, um ein Skript für mehrere Objekte der gleichen Kategorie zu generieren.</span><span class="sxs-lookup"><span data-stu-id="9dd8b-141">You can use the **Object Explorer Details** pane to generate a script for mutliple objects of the same category.</span></span>  
  
1.  <span data-ttu-id="9dd8b-142">Stellen Sie im Objekt-Explorer eine Verbindung mit einer Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] her, und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="9dd8b-142">In Object Explorer, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="9dd8b-143">Erweitern Sie **Datenbanken**, und erweitern Sie dann die Datenbank, die die Objekte enthält, die geschrieben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9dd8b-143">Expand **Databases**, and then expand the database containing the objects to be scripted.</span></span>  
  
3.  <span data-ttu-id="9dd8b-144">Erweitern Sie den Kategorieknoten der Objekttypen, für die Sie ein Skript erstellen möchten, z. B. den Knoten **Tabellen** .</span><span class="sxs-lookup"><span data-stu-id="9dd8b-144">Expand the category node of the types of object you want to script, such as the **Tables** node.</span></span>  
  
4.  <span data-ttu-id="9dd8b-145">Öffnen Sie den Bereich **Details zum Objekt-Explorer** durch Drücken von **F7**oder durch Öffnen des Menüs **Ansicht** und Auswahl der Option **Details zum Objekt-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="9dd8b-145">Open the **Object Explorer Details** pane by either selecting **F7**, or opening the **View** menu and selecting **Object Explorer Details**.</span></span>  
  
5.  <span data-ttu-id="9dd8b-146">Klicken Sie mit der linken Maustaste auf eines der Objekte, für das Sie ein Skript erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="9dd8b-146">Left-click one of the objects you want to script.</span></span>  
  
6.  <span data-ttu-id="9dd8b-147">Klicken Sie bei gedrückter STRG-TASTE mit der linken Maustaste auf das zweite Objekt, für das Sie ein Skript erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="9dd8b-147">Crtl + left-click the second object you want to script.</span></span>  
  
7.  <span data-ttu-id="9dd8b-148">Klicken Sie mit der rechten Maustaste auf eines der ausgewählten Objekte, und wählen Sie **Skript \<object type> als**aus.</span><span class="sxs-lookup"><span data-stu-id="9dd8b-148">Right-click one of the selected objects, and select **Script \<object type> as**.</span></span>  
  
  
