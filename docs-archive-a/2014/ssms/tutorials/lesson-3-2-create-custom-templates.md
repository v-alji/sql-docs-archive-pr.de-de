---
title: Erstellen von benutzerdefinierten Vorlagen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- tql
- templates [Transact-SQL], creating
- templates [Transact-SQL]
ms.assetid: 41098e78-b482-410e-bfe8-2ac10769ac4a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 771547b9c47672d2c075b5e7215d78744fe5f18e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717140"
---
# <a name="create-custom-templates"></a><span data-ttu-id="aaa81-102">Erstellen von benutzerdefinierten Vorlagen</span><span class="sxs-lookup"><span data-stu-id="aaa81-102">Create Custom Templates</span></span>
  [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="aaa81-103">kommt mit einer Reihe von Vorlagen für viele häufig ausgeführten Aufgaben. Der größte Vorteil von Vorlagen besteht jedoch darin, dass Sie für ein komplexes Skript, das Sie häufig erstellen müssen, eine benutzerdefinierte Vorlage anlegen können.</span><span class="sxs-lookup"><span data-stu-id="aaa81-103">comes with templates for many common tasks, but the real power of templates lies in the ability to create a custom template for a complex script that you must create frequently.</span></span> <span data-ttu-id="aaa81-104">Sie werden nun ein einfaches Skript mit wenigen Parametern erstellen. Vorlagen sind jedoch auch bei umfangreichen Skripts mit vielen Wiederholungen nützlich.</span><span class="sxs-lookup"><span data-stu-id="aaa81-104">In this practice you will create a simple script with few parameters, but templates are useful for long, repetitive scripts, too.</span></span>  
  
## <a name="using-custom-templates"></a><span data-ttu-id="aaa81-105">Verwenden benutzerdefinierter Vorlagen</span><span class="sxs-lookup"><span data-stu-id="aaa81-105">Using Custom Templates</span></span>  
  
#### <a name="to-create-a-custom-template"></a><span data-ttu-id="aaa81-106">So erstellen Sie eine benutzerdefinierte Vorlage</span><span class="sxs-lookup"><span data-stu-id="aaa81-106">To create a custom template</span></span>  
  
1.  <span data-ttu-id="aaa81-107">Erweitern Sie **SQL Server-Vorlagen**im Vorlagen-Explorer, klicken Sie mit der rechten Maustaste auf **Gespeicherte Prozedur**, zeigen Sie auf **Neu**, und klicken Sie anschließend auf **Ordner**.</span><span class="sxs-lookup"><span data-stu-id="aaa81-107">In Template Explorer, expand **SQL Server Templates**, right-click **Stored Procedure**, point to **New**, and then click **Folder**.</span></span>  
  
2.  <span data-ttu-id="aaa81-108">Geben Sie **Custom** als Namen für den neuen Vorlagenordner ein, und drücken Sie anschließend die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="aaa81-108">Type **Custom** as the name of your new template folder, and then press ENTER.</span></span>  
  
3.  <span data-ttu-id="aaa81-109">Klicken Sie mit der rechten Maustaste auf **Custom**, zeigen Sie auf **Neu**, und klicken Sie anschließend auf **Vorlage**.</span><span class="sxs-lookup"><span data-stu-id="aaa81-109">Right-click **Custom**, point to **New**, and then click **Template**.</span></span>  
  
4.  <span data-ttu-id="aaa81-110">Geben Sie **WorkOrdersProc** als Namen für die neue Vorlage ein, und drücken Sie anschließend die **EINGABETASTE**.</span><span class="sxs-lookup"><span data-stu-id="aaa81-110">Type **WorkOrdersProc** as the name of your new template, and then press **Enter**.</span></span>  
  
5.  <span data-ttu-id="aaa81-111">Klicken Sie mit der rechten Maustaste auf **WorkOrdersProc**und anschließend auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="aaa81-111">Right-click **WorkOrdersProc**, and then click **Edit**.</span></span>  
  
6.  <span data-ttu-id="aaa81-112">Überprüfen Sie im Dialogfeld **Verbindung mit Datenbank-Engine herstellen** die Verbindungseinstellungen, und klicken Sie anschließend auf **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="aaa81-112">In the **Connect to Database Engine** dialog box, verify the connection information and then click **Connect**.</span></span>  
  
7.  <span data-ttu-id="aaa81-113">Geben Sie im Abfrage-Editor das folgende Skript ein, um eine gespeicherte Prozedur zu erstellen, über die Bestellungen für ein bestimmtes Teil gesucht werden. In diesem Fall handelt es sich um Klingen (Blade).</span><span class="sxs-lookup"><span data-stu-id="aaa81-113">In Query Editor, type the following script to create a stored procedure that looks up orders for a particular part, in this case the Blade.</span></span> <span data-ttu-id="aaa81-114">(Sie können den Code im Fenster des Lernprogramms kopieren und dann einfügen.)</span><span class="sxs-lookup"><span data-stu-id="aaa81-114">(You can copy and paste the code from the Tutorial window.)</span></span>  
  
    ```  
    USE AdventureWorks20012;  
    GO  
    IF EXISTS (  
    SELECT *   
       FROM INFORMATION_SCHEMA.ROUTINES   
       WHERE SPECIFIC_NAME = 'WorkOrdersForBlade')  
       DROP PROCEDURE dbo.WorkOrdersForBlade;  
    GO  
    CREATE PROCEDURE dbo.WorkOrdersForBlade  
    AS  
    SELECT Name, WorkOrderID   
    FROM Production.WorkOrder AS WO  
    JOIN Production.Product AS Prod  
    ON WO.ProductID = Prod.ProductID  
    WHERE Name = 'Blade';  
    GO  
    ```  
  
8.  <span data-ttu-id="aaa81-115">Drücken Sie F5, um das Skript auszuführen. Damit wird die Prozedur **WorkOrdersForBlade** erstellt.</span><span class="sxs-lookup"><span data-stu-id="aaa81-115">Press F5 to execute this script, creating the **WorkOrdersForBlade** procedure.</span></span>  
  
9. <span data-ttu-id="aaa81-116">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf Ihren Server und anschließend auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="aaa81-116">In Object Explorer, right-click your server, and then click **New Query**.</span></span> <span data-ttu-id="aaa81-117">Ein neues Abfrage-Editorfenster wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="aaa81-117">A new Query Editor window opens.</span></span>  
  
10. <span data-ttu-id="aaa81-118">Geben Sie im Abfrage-Editor **EXECUTE dbo.WorkOrdersForBlade**ein, und drücken Sie anschließend F5, um die Abfrage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="aaa81-118">In Query Editor, type **EXECUTE dbo.WorkOrdersForBlade**, and then press F5 to execute the query.</span></span> <span data-ttu-id="aaa81-119">Überprüfen Sie, ob im Bereich **Ergebnisse** eine Liste mit Bestellungen für Klingen zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="aaa81-119">Confirm that the **Results** pane returns a list of work orders for blades.</span></span>  
  
11. <span data-ttu-id="aaa81-120">Bearbeiten Sie das Vorlagen Skript (das Skript in Schritt 7), und ersetzen Sie das Blatt "Produktname" durch den Parameter <strong> *<* product_name</strong>, " `nvarchar(50)` <strong>Name *>* </strong>" an vier Stellen.</span><span class="sxs-lookup"><span data-stu-id="aaa81-120">Edit the template script (the script in step 7), replacing the product name Blade with the parameter <strong>*<* product_name</strong>, `nvarchar(50)`, <strong>name*>*</strong>, in four places.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="aaa81-121">Für Parameter sind drei Elemente erforderlich: der Name des zu ersetzenden Parameters, der Datentyp des Parameters und ein Standardwert für den Parameter.</span><span class="sxs-lookup"><span data-stu-id="aaa81-121">Parameters require three elements: the name of the parameter that you want to replace, the data type of the parameter, and a default value for the parameter.</span></span>  
  
12. <span data-ttu-id="aaa81-122">Das Skript sollte nun wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="aaa81-122">Now the script should look like:</span></span>  
  
    ```  
    USE AdventureWorks20012;  
    GO  
    IF EXISTS (  
    SELECT *   
       FROM INFORMATION_SCHEMA.ROUTINES   
       WHERE SPECIFIC_NAME = 'WorkOrdersFor<product_name, nvarchar(50), name>')  
       DROP PROCEDURE dbo.WorkOrdersFor<product_name, nvarchar(50), name>;  
    GO  
    CREATE PROCEDURE dbo.WorkOrdersFor<product_name, nvarchar(50), name>  
    AS  
    SELECT Name, WorkOrderID   
    FROM Production.WorkOrder AS WO  
    JOIN Production.Product AS Prod  
    ON WO.ProductID = Prod.ProductID  
    WHERE Name = '<product_name, nvarchar(50), name>';  
    GO  
    ```  
  
13. <span data-ttu-id="aaa81-123">Klicken Sie im Menü **Datei** auf **WorkOrdersProc.sql speichern** , um Ihre Vorlage zu speichern.</span><span class="sxs-lookup"><span data-stu-id="aaa81-123">On the **File** menu, click **Save WorkOrdersProc.sql** to save your template.</span></span>  
  
#### <a name="to-test-the-custom-template"></a><span data-ttu-id="aaa81-124">So testen Sie die benutzerdefinierte Vorlage</span><span class="sxs-lookup"><span data-stu-id="aaa81-124">To test the custom template</span></span>  
  
1.  <span data-ttu-id="aaa81-125">Erweitern Sie im Vorlagen-Explorer **Gespei6cherte Prozeduren**, erweitern Sie **Benutzerdefiniert**, und doppelklicken Sie anschließend auf **WorkOrderProc**.</span><span class="sxs-lookup"><span data-stu-id="aaa81-125">In Template Explorer, expand **Stored Procedure**, expand **Custom**, and then double-click **WorkOrderProc**.</span></span>  
  
2.  <span data-ttu-id="aaa81-126">Vervollständigen Sie im Dialogfeld **Verbindung mit Datenbank-Engine herstellen** die Verbindungseinstellungen, und klicken Sie anschließend auf **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="aaa81-126">In the **Connect to Database Engine** dialog box, complete the connection information and then click **Connect**.</span></span> <span data-ttu-id="aaa81-127">Ein neues Fenster des Abfrage-Editors wird geöffnet, in dem der Inhalt der Vorlage **WorkOrderProc** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="aaa81-127">A new Query Editor window opens, containing the contents of the **WorkOrderProc** template.</span></span>  
  
3.  <span data-ttu-id="aaa81-128">Klicken Sie im Menü **Abfrage** auf **Werte für Vorlagenparameter angeben**.</span><span class="sxs-lookup"><span data-stu-id="aaa81-128">On the **Query** menu, click **Specify Values for Template Parameters**.</span></span>  
  
4.  <span data-ttu-id="aaa81-129">Geben Sie im Dialogfeld **Vorlagen Parameter ersetzen** für den `product_name` Wert den Wert " **frewheel** " (Überschreiben des Standard Inhalts) ein, und klicken Sie dann auf **OK** , um das Dialogfeld **Vorlagen Parameter ersetzen** zu schließen und das Skript im Abfrage-Editor zu ändern.</span><span class="sxs-lookup"><span data-stu-id="aaa81-129">In the **Replace Template Parameters** dialog box, for the `product_name` value, type **FreeWheel** (overwriting the default contents), and then click **OK** to close the **Replace Template Parameters** dialog box and modify the script in the Query Editor.</span></span>  
  
5.  <span data-ttu-id="aaa81-130">Drücken Sie F5, um das Skript auszuführen. Damit wird die Prozedur erstellt.</span><span class="sxs-lookup"><span data-stu-id="aaa81-130">Press F5 to execute the query, creating the procedure.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="aaa81-131">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="aaa81-131">Next Task in Lesson</span></span>  
 [<span data-ttu-id="aaa81-132">Speichern von Skripts als Projekte oder Lösungen</span><span class="sxs-lookup"><span data-stu-id="aaa81-132">Save Scripts as Projects or Solutions</span></span>](lesson-3-3-save-scripts-as-projects-or-solutions.md)  
  
  
