---
title: 'Aufgabe 4: Exportieren der Ergebnisse aus der abgleichsaktivität in eine Excel-Datei | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 644454c4-3c5a-469a-90ec-e51dc7fb99fc
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: b583e44f887fc0595fb904ec977f1de28c2fecd9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720416"
---
# <a name="task-4-exporting-the-results-from-matching-activity-to-an-excel-file"></a><span data-ttu-id="d00e5-102">Aufgabe 4: Exportieren der Ergebnisse der Abgleichaktivität in eine Excel-Datei</span><span class="sxs-lookup"><span data-stu-id="d00e5-102">Task 4: Exporting the Results from Matching Activity to an Excel File</span></span>
  <span data-ttu-id="d00e5-103">In dieser Aufgabe exportieren Sie die Ergebnisse aus der Abgleichsaktivität in eine Excel-Datei.</span><span class="sxs-lookup"><span data-stu-id="d00e5-103">In this task, you export the results from the matching activity to an Excel file.</span></span>

1.  <span data-ttu-id="d00e5-104">Wählen Sie auf der Seite **exportieren** für den **Zieltyp**die Option **Excel-Datei** aus.</span><span class="sxs-lookup"><span data-stu-id="d00e5-104">In the **Export** page, select **Excel File** for the **Destination Type**.</span></span>

2.  <span data-ttu-id="d00e5-105">Wählen Sie die Option **Survivorship results** aus.</span><span class="sxs-lookup"><span data-stu-id="d00e5-105">Select **Survivorship Results** option.</span></span> <span data-ttu-id="d00e5-106">Im Survivorship-Prozess bestimmt DQS basierend auf der ausgewählten **Survivorship-Regel** einen Survivor-Datensatz für jeden Cluster.</span><span class="sxs-lookup"><span data-stu-id="d00e5-106">In the survivorship process, DQS determines a survivor record for each cluster based on the **Survivorship Rule** you selected.</span></span>

3.  <span data-ttu-id="d00e5-107">Klicken Sie auf **Durchsuchen** , und navigieren Sie zu dem Ordner, in dem Sie die Ausgabedatei speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="d00e5-107">Click **Browse** and navigate to the folder where you want to store the output file.</span></span>

4.  <span data-ttu-id="d00e5-108">Geben Sie für den Namen **bereinigt und abgeglichen Suppliers.xls** ein, und klicken Sie auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="d00e5-108">Type **Cleansed and Matched Suppliers.xls** for the name and click **Open**.</span></span>

5.  <span data-ttu-id="d00e5-109">Vergewissern Sie sich, dass **Pivot-Datensatz** für die **Survivorship-Regel**ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="d00e5-109">Confirm that **Pivot Record** is selected for the **Survivorship Rule**.</span></span> <span data-ttu-id="d00e5-110">Wenn Sie diese Option wählen, wird der Pivotdatensatz für jeden Cluster für die Ausgabe aus einem Cluster ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="d00e5-110">When you select this option, the pivot record for each cluster is picked for the output from a cluster.</span></span> <span data-ttu-id="d00e5-111">Die anderen Optionen für die Survivorship-Regel sind:</span><span class="sxs-lookup"><span data-stu-id="d00e5-111">The other options for the Survivorship Rule are:</span></span>

    1.  <span data-ttu-id="d00e5-112">**Vollständiger Datensatz:** Der Survivor-Datensatz ist der Datensatz mit der größten Anzahl ausgefüllten Felder.</span><span class="sxs-lookup"><span data-stu-id="d00e5-112">**Most complete record:** Survivor record is the one with the largest number of populated fields.</span></span>

    2.  <span data-ttu-id="d00e5-113">**Längster Datensatz:** Der Survivor-Datensatz ist der Datensatz mit der größten Anzahl von Begriffen in den Quell Feldern.</span><span class="sxs-lookup"><span data-stu-id="d00e5-113">**Longest record:** Survivor record is the one with the largest number of terms in source fields.</span></span>

    3.  <span data-ttu-id="d00e5-114">**Vollständigster und Längster Datensatz:** Der Survivor-Datensatz ist der Datensatz mit der größten Anzahl von ausgefüllten Feldern, und er verfügt über die größte Anzahl von Begriffen in jedem Feld.</span><span class="sxs-lookup"><span data-stu-id="d00e5-114">**Most complete and longest record:** Survivor record is the one with the largest number of populated fields, and has the largest number of terms in each field.</span></span>

     <span data-ttu-id="d00e5-115">![Exportieren von Ergebnissen von der Seite "Übereinstimmend"](../../2014/tutorials/media/et-exportingtheresultsfrommatoanexcelfile.jpg "Exportieren von Ergebnissen von der Seite "Übereinstimmend"")</span><span class="sxs-lookup"><span data-stu-id="d00e5-115">![Export Results from Matching Page](../../2014/tutorials/media/et-exportingtheresultsfrommatoanexcelfile.jpg "Export Results from Matching Page")</span></span>

6.  <span data-ttu-id="d00e5-116">Klicken Sie auf **exportieren** , um die Ergebnisse in eine Excel-Datei zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="d00e5-116">Click **Export** to export the results to an Excel file.</span></span>

7.  <span data-ttu-id="d00e5-117">Klicken Sie auf **Schließen** , um das Dialogfeld **übereinstimmende Exporte** zu schließen</span><span class="sxs-lookup"><span data-stu-id="d00e5-117">Click **Close** to close the **Matching Export** dialog box.</span></span>

8.  <span data-ttu-id="d00e5-118">Klicken Sie zum Abschließen der abgleichsaktivität auf **Fertig** stellen</span><span class="sxs-lookup"><span data-stu-id="d00e5-118">Click **Finish** to finish the matching activity.</span></span>

9. <span data-ttu-id="d00e5-119">Öffnen Sie die **Suppliers.xlsxDatei bereinigt, und Stimmen** Sie zu, und vergewissern Sie sich, dass keine Duplikate (SupplierID) angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d00e5-119">Open the **Cleansed and Matched Suppliers.xlsx** file and confirm that you do not see any duplicates (SupplierID).</span></span>

 <span data-ttu-id="d00e5-120">Nun verfügen Sie über Lieferantendaten, die bereinigt und abgeglichen wurden, um Duplikate zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="d00e5-120">Now, you have supplier data that has been cleansed and matched to remove duplicates.</span></span>

## <a name="next-step"></a><span data-ttu-id="d00e5-121">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="d00e5-121">Next Step</span></span>
 [<span data-ttu-id="d00e5-122">Lektion 4: Speichern von Lieferantendaten in MDS</span><span class="sxs-lookup"><span data-stu-id="d00e5-122">Lesson 4: Storing Supplier Data in MDS</span></span>](../../2014/tutorials/lesson-4-storing-supplier-data-in-mds.md)


