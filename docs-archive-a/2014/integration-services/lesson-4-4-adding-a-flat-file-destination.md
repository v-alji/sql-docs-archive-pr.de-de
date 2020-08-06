---
title: 'Schritt 4: Hinzufügen eines Flatfileziels | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: f4088de3-16d8-419c-96a1-a2cd005d0a5b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: eff65f4a94a412d55af8055e302195f87ae4cdb2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720242"
---
# <a name="step-4-adding-a-flat-file-destination"></a><span data-ttu-id="bfa97-102">Schritt 4: Hinzufügen eines Flatfileziels</span><span class="sxs-lookup"><span data-stu-id="bfa97-102">Step 4: Adding a Flat File Destination</span></span>
  <span data-ttu-id="bfa97-103">Die Fehlerausgabe der "Lookup Currency Key"-Transformation leitet alle Datenzeilen, für die im Suchvorgang keine Übereinstimmung gefunden wurde, zur Skripttransformation um.</span><span class="sxs-lookup"><span data-stu-id="bfa97-103">The error output of the Lookup Currency Key transformation redirects to the Script transformation any data rows that failed the lookup operation.</span></span> <span data-ttu-id="bfa97-104">Um die zu den Fehlern angezeigten Informationen zu verbessern, führt die Skripttransformation ein Skript aus, mit dem die Fehlerbeschreibung abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="bfa97-104">To enhance information about the errors that occurred, the Script transformation runs a script that gets the description of errors.</span></span>  
  
 <span data-ttu-id="bfa97-105">In dieser Aufgabe speichern Sie alle Informationen zu den fehlerhaften Zeilen für eine spätere Verarbeitung in einer Datei mit Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="bfa97-105">In this task, you will save all this information about the failed rows to a delimited file for later processing.</span></span> <span data-ttu-id="bfa97-106">Um die fehlerhaften Zeilen zu speichern, müssen Sie einen Flatfile-Verbindungs-Manager für die Textdatei, die die Fehlerdaten enthalten wird, und ein Flatfileziel hinzufügen und konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="bfa97-106">To save the failed rows, you must add and configure a Flat File connection manager for the text file that will contain the error data and a Flat File destination.</span></span> <span data-ttu-id="bfa97-107">Durch Festlegen von Eigenschaften im Verbindungs-Manager für Flatfiles, der vom Flatfileziel verwendet wird, können Sie angeben, wie das Flatfileziel die Textdatei formatiert und schreibt.</span><span class="sxs-lookup"><span data-stu-id="bfa97-107">By setting properties on the Flat File connection manager that the Flat File destination uses, you can specify how the Flat File destination formats and writes the text file.</span></span> <span data-ttu-id="bfa97-108">Weitere Informationen finden Sie unter [Verbindungs-Manager für Flatfiles](connection-manager/file-connection-manager.md) und [Flatfileziel](data-flow/flat-file-destination.md).</span><span class="sxs-lookup"><span data-stu-id="bfa97-108">For more information, see [Flat File Connection Manager](connection-manager/file-connection-manager.md) and [Flat File Destination](data-flow/flat-file-destination.md).</span></span>  
  
### <a name="to-add-and-configure-a-flat-file-destination"></a><span data-ttu-id="bfa97-109">So fügen Sie ein Flatfileziel hinzu und konfigurieren es</span><span class="sxs-lookup"><span data-stu-id="bfa97-109">To add and configure a Flat File destination</span></span>  
  
1.  <span data-ttu-id="bfa97-110">Klicken Sie auf die Registerkarte **Datenfluss** .</span><span class="sxs-lookup"><span data-stu-id="bfa97-110">Click the **Data Flow** tab.</span></span>  
  
2.  <span data-ttu-id="bfa97-111">Erweitern Sie in der **SSIS-Toolbox**die Option **Weitere**, und ziehen Sie **Flatfileziel** auf die Datenfluss-Entwurfsoberfläche.</span><span class="sxs-lookup"><span data-stu-id="bfa97-111">In the **SSIS Toolbox**, expand **Other**, and drag **Flat File Destination** onto the data flow design surface.</span></span> <span data-ttu-id="bfa97-112">Setzen Sie das **Flatfileziel** direkt unter die **Get Error Description** -Transformation.</span><span class="sxs-lookup"><span data-stu-id="bfa97-112">Put the **Flat File Destination** directly underneath the **Get Error Description** transformation.</span></span>  
  
3.  <span data-ttu-id="bfa97-113">Klicken Sie auf die **Get Error Description** -Transformation, und ziehen Sie anschließend den grünen Pfeil auf das neue **Flatfileziel**.</span><span class="sxs-lookup"><span data-stu-id="bfa97-113">Click the **Get Error Description** transformation, and then drag the green arrow onto the new **Flat File Destination**.</span></span>  
  
4.  <span data-ttu-id="bfa97-114">Klicken Sie auf der **Datenfluss** -Entwurfsoberfläche in der neu hinzugefügten **Flatfileziel** -Transformation auf **Flatfileziel** , und ändern Sie den Namen in **Failed Rows**.</span><span class="sxs-lookup"><span data-stu-id="bfa97-114">On the **Data Flow** design surface, click **Flat File Destination** in the newly added **Flat File Destination** transformation, and change the name to **Failed Rows**.</span></span>  
  
5.  <span data-ttu-id="bfa97-115">Klicken Sie mit der rechten Maustaste auf die Transformation **Failed Rows** , klicken Sie auf **Bearbeiten**und anschließend im **Ziel-Editor für Flatfiles**auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="bfa97-115">Right-click the **Failed Rows** transformation, click **Edit**, and then in the **Flat File Destination Editor**, click **New**.</span></span>  
  
6.  <span data-ttu-id="bfa97-116">Überprüfen Sie im Dialogfeld **Flatfileformat** , ob **Mit Trennzeichen** ausgewählt ist, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="bfa97-116">In the **Flat File Format** dialog box, verify that **Delimited** is selected, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="bfa97-117">Geben Sie im **Verbindungs-Manager-Editor für Flatfiles**im Feld Name des Verbindungs-Managers den **Namen** ein `Error Data` .</span><span class="sxs-lookup"><span data-stu-id="bfa97-117">In the **Flat File Connection Manager Editor**, in the **Connection Manager Name** box type `Error Data`.</span></span>  
  
8.  <span data-ttu-id="bfa97-118">Klicken Sie im Dialogfeld **Verbindungs-Manager-Editor für Flatfiles** auf **Durchsuchen**, und suchen Sie den Ordner, in dem die Datei gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="bfa97-118">In the **Flat File Connection Manager Editor** dialog box, click **Browse**, and locate the folder in which to store the file.</span></span>  
  
9. <span data-ttu-id="bfa97-119">Geben Sie im Dialogfeld **Öffnen** für **Dateiname den Namen**ein `ErrorOutput.txt` , und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="bfa97-119">In the **Open** dialog box, for **File name**, type `ErrorOutput.txt`, and then click **Open**.</span></span>  
  
10. <span data-ttu-id="bfa97-120">Prüfen Sie im Dialogfeld **Verbindungs-Manager-Editor für Flatfiles** , ob das Feld **Gebietsschema** den Wert Englisch (USA) und das Feld **Codepage** den Wert 1252 (ANSI -Latin I) enthält.</span><span class="sxs-lookup"><span data-stu-id="bfa97-120">In the **Flat File Connection Manager Editor** dialog box, verify that the **Locale** box contains English (United States) and **Code page** contains 1252 (ANSI -Latin I).</span></span>  
  
11. <span data-ttu-id="bfa97-121">Klicken Sie im Optionen-Bereich auf **Spalten**.</span><span class="sxs-lookup"><span data-stu-id="bfa97-121">In the options pane, click **Columns**.</span></span>  
  
     <span data-ttu-id="bfa97-122">Beachten Sie, dass zusätzlich zu den Spalten aus der Quelldatendatei drei neue Spalten vorhanden sind: ErrorCode, ErrorColumn und ErrorDescription.</span><span class="sxs-lookup"><span data-stu-id="bfa97-122">Notice that, in addition to the columns from the source data file, three new columns are present: ErrorCode, ErrorColumn, and ErrorDescription.</span></span> <span data-ttu-id="bfa97-123">Diese Spalten werden von der Fehlerausgabe der Lookup Currency Key-Transformation und vom Skript in der Get Error Description-Transformation generiert und können dazu verwendet werden, die Ursache für das Fehlschlagen der Zeile zu beheben.</span><span class="sxs-lookup"><span data-stu-id="bfa97-123">These columns are generated by the error output of the Lookup Currency Key transformation and by the script in the Get Error Description transformation, and can be used to troubleshoot the cause of the failed row.</span></span>  
  
12. <span data-ttu-id="bfa97-124">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="bfa97-124">Click **OK**.</span></span>  
  
13. <span data-ttu-id="bfa97-125">Deaktivieren Sie im **Ziel-Editor für Flatfiles**das Kontrollkästchen **Daten in der Datei überschreiben** .</span><span class="sxs-lookup"><span data-stu-id="bfa97-125">In the **Flat File Destination Editor**, clear the **Overwrite data in the file** check box.</span></span>  
  
     <span data-ttu-id="bfa97-126">Wenn Sie dieses Kontrollkästchen deaktivieren, werden die Fehler über mehrere Paketausführungen beibehalten.</span><span class="sxs-lookup"><span data-stu-id="bfa97-126">Clearing this check box persists the errors over multiple package executions.</span></span>  
  
14. <span data-ttu-id="bfa97-127">Klicken Sie im **Ziel-Editor für Flatfiles**auf **Zuordnungen** um zu überprüfen, ob alle Spalten ordnungsgemäß sind.</span><span class="sxs-lookup"><span data-stu-id="bfa97-127">In the **Flat File Destination Editor**, click **Mappings** to verify that all the columns are correct.</span></span> <span data-ttu-id="bfa97-128">Optional können Sie die Spalten im Ziel umbenennen.</span><span class="sxs-lookup"><span data-stu-id="bfa97-128">Optionally, you can rename the columns in the destination.</span></span>  
  
15. <span data-ttu-id="bfa97-129">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="bfa97-129">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="bfa97-130">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="bfa97-130">Next Steps</span></span>  
 [<span data-ttu-id="bfa97-131">Schritt 5: Testen des Tutorialpakets aus Lektion 4</span><span class="sxs-lookup"><span data-stu-id="bfa97-131">Step 5: Testing the Lesson 4 Tutorial Package</span></span>](../integration-services/lesson-4-5-testing-the-lesson-4-tutorial-package.md)  
  
  
