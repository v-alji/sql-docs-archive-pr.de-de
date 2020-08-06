---
title: 'Aufgabe 8: Hinzufügen der Transformation für bedingtes Teilen zum Aufteilen der Bereinigungs Ausgabe Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: d4ebe420-a4a9-4076-89d3-41abe726fc5c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 9be7ea6f5330382ad0417df99e18bcba5b59a4e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608132"
---
# <a name="task-8-adding-conditional-split-transform-to-split-cleansing-output"></a><span data-ttu-id="ba9d6-102">Aufgabe 8: Hinzufügen der Transformation „Bedingtes Teilen“ zur Teilung der Bereinigungsausgabe</span><span class="sxs-lookup"><span data-stu-id="ba9d6-102">Task 8: Adding Conditional Split Transform to Split Cleansing Output</span></span>
  <span data-ttu-id="ba9d6-103">In dieser Aufgabe fügen Sie eine Transformation "Bedingtes Teilen" zum Datenfluss hinzu.</span><span class="sxs-lookup"><span data-stu-id="ba9d6-103">In this transform, you add a Conditional Split Transform to the data flow.</span></span> <span data-ttu-id="ba9d6-104">Die Transformation "Bedingtes Teilen" kann Zeilen je nach Dateninhalt an andere Ausgaben routen.</span><span class="sxs-lookup"><span data-stu-id="ba9d6-104">The Conditional Split transformation can route rows to different outputs based on the content of the data.</span></span> <span data-ttu-id="ba9d6-105">In diesem Tutorial verwenden Sie die Ausgabe Spalte für den **Daten Satz Status** aus der Transformation für die DQS-Bereinigung.</span><span class="sxs-lookup"><span data-stu-id="ba9d6-105">For this tutorial, you use the **Record Status** output column from the DQS Cleansing transform.</span></span> <span data-ttu-id="ba9d6-106">Sie laden in diesem Lernprogramm nur richtige oder korrigierte Datensätze zu MDS-Server hoch.</span><span class="sxs-lookup"><span data-stu-id="ba9d6-106">You will upload only correct or corrected records to MDS server in this tutorial.</span></span> <span data-ttu-id="ba9d6-107">Daher überprüfen Sie, ob der **Status des Datensatzes** **korrekt** oder **korrigiert**ist, und kombinieren die Datensätze, bevor Sie die Datensätze in MDS hochladen.</span><span class="sxs-lookup"><span data-stu-id="ba9d6-107">Therefore you check if the **Record Status** is **Correct** or **Corrected**, and combine the records before uploading the records to MDS.</span></span>  
  
1.  <span data-ttu-id="ba9d6-108">Ziehen Sie die **Transformation für bedingtes Teilen** aus **Common** section in der **SSIS-Toolbox** in die Registerkarte **Datenfluss** unter Bereinigen von **Lieferantendaten**.</span><span class="sxs-lookup"><span data-stu-id="ba9d6-108">Drag-drop **Conditional Split Transform** from **Common** section in the **SSIS Toolbox** to the **Data Flow** tab under **Cleanse Supplier Data**.</span></span>  
  
2.  <span data-ttu-id="ba9d6-109">Klicken Sie mit der rechten Maustaste auf **bedingtes Teilen**, und klicken **Sie auf**</span><span class="sxs-lookup"><span data-stu-id="ba9d6-109">Right-click **Conditional Split**, and click **Rename**.</span></span> <span data-ttu-id="ba9d6-110">Geben Sie **richtige und korrigierte Datensätze auswählen** ein, und drücken **Sie Eingabe**</span><span class="sxs-lookup"><span data-stu-id="ba9d6-110">Type **Pick Correct and Corrected Records** and press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="ba9d6-111">Verbinden Sie **Lieferantendaten** , und **Wählen Sie richtige und korrigierte Datensätze** mit dem blauen Connector aus.</span><span class="sxs-lookup"><span data-stu-id="ba9d6-111">Connect **Cleanse Supplier Data** and **Pick Correct and Corrected Records** using the blue connector.</span></span>  
  
     <span data-ttu-id="ba9d6-112">![Lieferantendaten bereinigen-> Auswahl korrigieren & korrigiert](../../2014/tutorials/media/et-addingcsttosplitcleansingoutput-01.jpg "Lieferantendaten bereinigen -> Richtige auswählen & Korrigiert")</span><span class="sxs-lookup"><span data-stu-id="ba9d6-112">![Cleanse Supplier Data -> Pick Correct & Corrected](../../2014/tutorials/media/et-addingcsttosplitcleansingoutput-01.jpg "Cleanse Supplier Data -> Pick Correct & Corrected")</span></span>  
  
4.  <span data-ttu-id="ba9d6-113">Doppelklicken Sie auf der Registerkarte **Datenfluss** auf **richtige und korrigierte Datensätze auswählen** .</span><span class="sxs-lookup"><span data-stu-id="ba9d6-113">Double-click **Pick Correct and Corrected Records** in the **Data Flow** tab.</span></span>  
  
5.  <span data-ttu-id="ba9d6-114">Ändern Sie den **standardmäßigen Ausgabe Namen** unten auf dem Bildschirm, um ihn zu **korrigieren**.</span><span class="sxs-lookup"><span data-stu-id="ba9d6-114">Change the **Default Output Name** at the bottom of the screen to **Correct**.</span></span>  
  
6.  <span data-ttu-id="ba9d6-115">Erweitern Sie im **linken oberen**Bereich die Option **Spalten** .</span><span class="sxs-lookup"><span data-stu-id="ba9d6-115">Expand **Columns** in the **top-left pane**.</span></span>  
  
     <span data-ttu-id="ba9d6-116">![Transformations-Editor für bedingtes Teilen](../../2014/tutorials/media/et-addingcsttosplitcleansingoutput-02.jpg "Transformations-Editor für bedingtes Teilen")</span><span class="sxs-lookup"><span data-stu-id="ba9d6-116">![Conditional Split Transformation Editor](../../2014/tutorials/media/et-addingcsttosplitcleansingoutput-02.jpg "Conditional Split Transformation Editor")</span></span>  
  
7.  <span data-ttu-id="ba9d6-117">Ziehen Sie **Daten Satz Status** in die Spalte **Bedingung** .</span><span class="sxs-lookup"><span data-stu-id="ba9d6-117">Drag-drop **Record Status** to the **Condition** column.</span></span>  
  
8.  <span data-ttu-id="ba9d6-118">Geben Sie **= = "korrigiert"** neben **[Daten Satz Status]** für die Spalte **Bedingung** ein.</span><span class="sxs-lookup"><span data-stu-id="ba9d6-118">Type **=="Corrected"** next to **[Record Status]** for the **Condition** column.</span></span>  
  
9. <span data-ttu-id="ba9d6-119">Klicken Sie in der **Spalte Ausgabe Name**auf Groß-/Kleinschreibung **1** , und ändern Sie den Namen in **korrigiert**.</span><span class="sxs-lookup"><span data-stu-id="ba9d6-119">Click **Case 1** in the **Output Name Column**, and change the name to **Corrected**.</span></span>  
  
10. <span data-ttu-id="ba9d6-120">Klicken Sie zum Schließen des Dialog Felds **Transformations-Editor für bedingtes Teilen** auf **OK** .</span><span class="sxs-lookup"><span data-stu-id="ba9d6-120">Click **OK** to close the **Conditional Split Transformation Editor** dialog box.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="ba9d6-121">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="ba9d6-121">Next Step</span></span>  
 [<span data-ttu-id="ba9d6-122">Aufgabe 9: Hinzufügen der Transformation UNION ALL zur Kombination richtiger und korrigierter Datensätze</span><span class="sxs-lookup"><span data-stu-id="ba9d6-122">Task 9: Adding Union All Transform to Combine Correct and Corrected Records</span></span>](../../2014/tutorials/task-9-adding-union-all-transform-to-combine-correct-and-corrected-records.md)  
  
  
