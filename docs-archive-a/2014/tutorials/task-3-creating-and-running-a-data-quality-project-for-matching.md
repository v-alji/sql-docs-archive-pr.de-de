---
title: 'Aufgabe 3: Erstellen und Ausführen eines Data Quality-Projekts für den Abgleich | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 6260e911-ea8b-4c69-a39d-d1bccd565a32
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 221d6d583c61ee035c20fcb63f0ed5278f2b8678
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609594"
---
# <a name="task-3-creating-and-running-a-data-quality-project-for-matching"></a><span data-ttu-id="571c7-102">Aufgabe 3: Erstellen und Ausführen eines Data Quality-Projekts für Abgleiche</span><span class="sxs-lookup"><span data-stu-id="571c7-102">Task 3: Creating and Running a Data Quality Project for Matching</span></span>
  <span data-ttu-id="571c7-103">In dieser Aufgabe erstellen Sie ein Data Quality-Projekt für die Abgleichsaktivität, und führen den Abgleichsprozess für bereinigte Lieferantendaten durch, um Duplikate in den Daten zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="571c7-103">In this task, you create a Data Quality Project for the matching activity and run the matching process on cleansed supplier data to remove any duplicates in the data.</span></span>

1.  <span data-ttu-id="571c7-104">Klicken Sie auf der Hauptseite des **DQS-Clients**auf **Neues Data Quality-Projekt**.</span><span class="sxs-lookup"><span data-stu-id="571c7-104">On the main page of **DQS Client**, click **New Data Quality Project**.</span></span>

2.  <span data-ttu-id="571c7-105">Geben Sie **Lieferanten Duplikate entfernen** aus dem **Namen des Projekts**ein.</span><span class="sxs-lookup"><span data-stu-id="571c7-105">Type **Remove Supplier Duplicates** from the **Name of the project**.</span></span>

3.  <span data-ttu-id="571c7-106">Wählen Sie **Suppliers** aus der Liste der KSB für das Feld **Wissensdatenbank verwenden** aus.</span><span class="sxs-lookup"><span data-stu-id="571c7-106">Select **Suppliers** from the list of KBs for the **Use Knowledge Base** field.</span></span> <span data-ttu-id="571c7-107">Sie haben eine Abgleichsrichtlinie in dieser Wissensdatenbank in der vorherigen Lektion erstellt.</span><span class="sxs-lookup"><span data-stu-id="571c7-107">You have created a matching policy in this knowledge base in the previous lesson.</span></span>

4.  <span data-ttu-id="571c7-108">Wählen Sie in der **Liste der Aktivitäten** aus dem unteren rechten Bereich **übereinstimmende überein** Stimmungen aus.</span><span class="sxs-lookup"><span data-stu-id="571c7-108">Select **Matching** from the **list of activities** from the bottom-right pane.</span></span>

     <span data-ttu-id="571c7-109">![Neues Data Quality-Projekt – "Abgleich" ausgewählt](../../2014/tutorials/media/et-creatingandrunningadqpformatching.jpg "Neues Data Quality-Projekt – "Abgleich" ausgewählt")</span><span class="sxs-lookup"><span data-stu-id="571c7-109">![New Data Quality Project - Matching Selected](../../2014/tutorials/media/et-creatingandrunningadqpformatching.jpg "New Data Quality Project - Matching Selected")</span></span>

5.  <span data-ttu-id="571c7-110">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="571c7-110">Click **Next**.</span></span>

6.  <span data-ttu-id="571c7-111">Wählen Sie auf der Seite **Zuordnen** für **Datenquelle** die Option **Excel-Datei**aus.</span><span class="sxs-lookup"><span data-stu-id="571c7-111">In the **Map** page, select **Excel File** for **Data Source**.</span></span>

7.  <span data-ttu-id="571c7-112">Klicken Sie auf **Durchsuchen** , und wählen Sie bereinigten Lieferanten List.xlsaus. Dies ist die Ausgabedatei der \*\*Bereinigungs \*\*Aktivität.</span><span class="sxs-lookup"><span data-stu-id="571c7-112">Click **Browse** and select **Cleansed Supplier List.xls**, which is the output file from the cleansing activity.</span></span>

8.  <span data-ttu-id="571c7-113">Ordnen Sie die Spalte **SupplierID** Source **der Lieferanten-ID** -Domäne, der Spalte **Lieferanten Name** in der Domäne **Lieferanten Name** und der Spalte **contactemailaddress** an die Domäne **Contact Email** zu.</span><span class="sxs-lookup"><span data-stu-id="571c7-113">Map **SupplierID** source column to the **Supplier ID** domain, **Supplier Name** column to **Supplier Name** domain, and **ContactEmailAddress** column to **Contact Email** domain.</span></span>

9. <span data-ttu-id="571c7-114">Klicken Sie auf **weiter** , um **zur Seite** Abgleich zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="571c7-114">Click **Next** to switch to the **Matching** page.</span></span>

10. <span data-ttu-id="571c7-115">Klicken Sie zum Starten des abgleichsprozesses auf **Start** .</span><span class="sxs-lookup"><span data-stu-id="571c7-115">Click **Start** to start the matching process.</span></span> <span data-ttu-id="571c7-116">Es sollten Ergebnisse angezeigt werden, die denen aus der vorherigen Aufgabe ähneln, da Sie dieselbe Eingabedatei zur Definition der Abgleichsrichtlinie verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="571c7-116">You should see results similar to those from the previous task because you used the same input file for defining the matching policy.</span></span>

11. <span data-ttu-id="571c7-117">Prüfen Sie alle übereinstimmenden Datensätze und ihre Treffergenauigkeit im Listenfeld.</span><span class="sxs-lookup"><span data-stu-id="571c7-117">Review all the matched records and their matching score in the list box.</span></span> <span data-ttu-id="571c7-118">Die Ergebnisse sollten denen aus der vorherigen Aufgabe entsprechen.</span><span class="sxs-lookup"><span data-stu-id="571c7-118">The results should be same as the ones you saw in the previous task.</span></span> <span data-ttu-id="571c7-119">Analysieren Sie die Ergebnisse aus dieser Abgleichsaktivität anhand der Schritte in der vorherigen Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="571c7-119">See the steps in the previous task to analyze the results from this matching activity.</span></span>

12. <span data-ttu-id="571c7-120">Klicken Sie auf **weiter** , um zur Seite **exportieren** zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="571c7-120">Click **Next** to switch to the **Export** page.</span></span>

## <a name="next-step"></a><span data-ttu-id="571c7-121">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="571c7-121">Next Step</span></span>
 [<span data-ttu-id="571c7-122">Aufgabe 4: Exportieren der Ergebnisse der Abgleichaktivität in eine Excel-Datei</span><span class="sxs-lookup"><span data-stu-id="571c7-122">Task 4: Exporting the Results from Matching Activity to an Excel File</span></span>](../../2014/tutorials/task-4-exporting-the-results-from-matching-activity-to-an-excel-file.md)


