---
title: 'Aufgabe 5: Exportieren der Bereinigungs Ergebnisse in eine Excel-Datei | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: eaeafd65-d0d4-4a7d-a3ad-110ef644e90b
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 0dbdc1bef348e03e211e4933132985ea2c089b97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620695"
---
# <a name="task-5-exporting-cleansing-results-to-an-excel-file"></a><span data-ttu-id="d5a6d-102">Aufgabe 5: Exportieren der Bereinigungsergebnisse in eine Excel-Datei</span><span class="sxs-lookup"><span data-stu-id="d5a6d-102">Task 5: Exporting Cleansing Results to an Excel File</span></span>
  <span data-ttu-id="d5a6d-103">In dieser Aufgabe exportieren Sie Ergebnisse aus der Bereinigungsaktivität in eine Excel-Datei.</span><span class="sxs-lookup"><span data-stu-id="d5a6d-103">In this task, you export results from the cleansing activity to an Excel file.</span></span> <span data-ttu-id="d5a6d-104">Weitere Informationen finden Sie im Thema [Exportieren von Stufen](https://msdn.microsoft.com/library/hh213061.aspx#Export) .</span><span class="sxs-lookup"><span data-stu-id="d5a6d-104">See [Export Stage](https://msdn.microsoft.com/library/hh213061.aspx#Export) topic for more details.</span></span>  
  
1.  <span data-ttu-id="d5a6d-105">Wählen Sie im rechten Bereich für den **Zieltyp**die Option **Excel** aus.</span><span class="sxs-lookup"><span data-stu-id="d5a6d-105">In the right pane, select **Excel** for the **Destination Type**.</span></span>  
  
2.  <span data-ttu-id="d5a6d-106">Klicken Sie auf **Durchsuchen**, geben Sie den Namen der Ausgabedatei als \*\*bereinigten Lieferanten #b0 \*\*an, und klicken Sie dann auf **Öffnen**</span><span class="sxs-lookup"><span data-stu-id="d5a6d-106">Click **Browse**, specify the output file name as **Cleansed Supplier List.xls**, and then click **Open**.</span></span>  
  
3.  <span data-ttu-id="d5a6d-107">Wählen Sie **Daten nur** für das **Ausgabe** Format aus, um nur die bereinigten Daten zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="d5a6d-107">Select **Data Only** for the **Output** format to export just the cleansed data.</span></span> <span data-ttu-id="d5a6d-108">Mit der zweiten Option ( **Daten-und**Bereinigungs Informationen) können Sie Bereinigungs Aktivitäts Details zusammen mit den bereinigten Daten exportieren.</span><span class="sxs-lookup"><span data-stu-id="d5a6d-108">The second option, **Data and Cleansing Info**, lets you export cleansing activity details along with the cleansed data.</span></span> <span data-ttu-id="d5a6d-109">Mit der Option **Format standardisieren** können Sie alle Ausgabeformate, die Sie für eine Domäne definieren, auf die Werte dieser Domäne anwenden.</span><span class="sxs-lookup"><span data-stu-id="d5a6d-109">The **Standardize Format** option lets you apply any output formats you define on a domain to the values of that domain.</span></span> <span data-ttu-id="d5a6d-110">Sie haben kein Ausgabeformat für die Domänen im Lernprogramm definiert.</span><span class="sxs-lookup"><span data-stu-id="d5a6d-110">You have not defined an output format on any domain in the tutorial.</span></span>  
  
     <span data-ttu-id="d5a6d-111">![Bereinigungsergebnisse exportieren (Seite)](../../2014/tutorials/media/et-exportingcleansingresultstoanexcelfile.jpg "Bereinigungsergebnisse exportieren (Seite)")</span><span class="sxs-lookup"><span data-stu-id="d5a6d-111">![Export Cleansing Results Page](../../2014/tutorials/media/et-exportingcleansingresultstoanexcelfile.jpg "Export Cleansing Results Page")</span></span>  
  
4.  <span data-ttu-id="d5a6d-112">Klicken Sie auf **exportieren** , um die Daten zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="d5a6d-112">Click **Export** to export the data.</span></span> <span data-ttu-id="d5a6d-113">Klicken Sie noch nicht auf **Fertig** stellen.</span><span class="sxs-lookup"><span data-stu-id="d5a6d-113">Do not click **Finish** yet.</span></span>  
  
5.  <span data-ttu-id="d5a6d-114">Klicken Sie im Dialogfeld **exportieren** auf **Schließen** .</span><span class="sxs-lookup"><span data-stu-id="d5a6d-114">Click **Close** on the **Exporting** dialog box.</span></span>  
  
6.  <span data-ttu-id="d5a6d-115">Klicken Sie auf **Fertig** stellen, um die Aktivität abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="d5a6d-115">Click **Finish** to finish the activity.</span></span> <span data-ttu-id="d5a6d-116">Wenn Sie vergessen haben, die Ergebnisse zu exportieren, bevor Sie auf **Fertig**stellen klicken, klicken Sie auf der Hauptseite des **DQS-Clients**auf **Data Quality-Projekt öffnen** , wählen Sie **Lieferantenliste** bereinigen aus der Liste der Projekte aus, und klicken Sie unten auf dem Bildschirm auf **weiter** , um die **Export** Phase des Bereinigungs Prozesses erneut</span><span class="sxs-lookup"><span data-stu-id="d5a6d-116">If you forgot to export results before clicking **Finish**, click **Open Data Quality Project** in the main page of **DQS Client**, select **Cleanse Supplier List** from the list of projects, and click **Next** at the bottom of the screen to get to the **Export** stage of cleansing process again.</span></span> <span data-ttu-id="d5a6d-117">Sie können auch zur Registerkarte **Ergebnisse verwalten und anzeigen** wechseln, indem Sie auf die Schaltfläche **zurück** klicken.</span><span class="sxs-lookup"><span data-stu-id="d5a6d-117">You can also switch to **Manage and View Results** tab by clicking **Back** button.</span></span>  
  
7.  <span data-ttu-id="d5a6d-118">Öffnen Sie den **bereinigten Lieferanten List.xls** , und führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="d5a6d-118">Open the **Cleansed Supplier List.xls** and do the following:</span></span>  
  
    1.  <span data-ttu-id="d5a6d-119">Stellen Sie sicher, dass keine e-Mail-Adressen vorhanden sind, die mit Adventure-work.com (ohne Zeichen ') enden, indem Sie im Arbeitsblatt nach Adventure-work.com suchen.</span><span class="sxs-lookup"><span data-stu-id="d5a6d-119">Ensure that there are no email addresses that end with adventure-work.com (without character 's') by searching for adventure-work.com in the worksheet.</span></span>  
  
    2.  <span data-ttu-id="d5a6d-120">Sehen Sie, dass in der Spalte **Country** kein Wert für **USA** vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="d5a6d-120">See that there is no **USA** value in the **Country** column.</span></span>  
  
    3.  <span data-ttu-id="d5a6d-121">Suchen Sie nach **Los Angeles** , und sehen Sie, dass der **Status** auf **ca**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="d5a6d-121">Search for **Los Angeles** and see that the **State** is set to **CA**.</span></span>  
  
    4.  <span data-ttu-id="d5a6d-122">Vergewissern Sie sich, dass keine Begriffe **Co.**, **Corp.** und **Inc.** vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="d5a6d-122">Confirm that there are no terms **Co.**, **Corp.**, and **Inc.**.</span></span>  
  
    5.  <span data-ttu-id="d5a6d-123">Löschen Sie die Spalte **Adressvalidierung** aus der Tabelle, und speichern Sie die Excel-Datei.</span><span class="sxs-lookup"><span data-stu-id="d5a6d-123">Delete the **Address Validation** column from the spreadsheet and save the excel file.</span></span> <span data-ttu-id="d5a6d-124">Diese zusätzliche Spalte entspricht der Verbunddomäne "Address Validation".</span><span class="sxs-lookup"><span data-stu-id="d5a6d-124">This additional column corresponds to the Address Validation composite domain.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="d5a6d-125">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="d5a6d-125">Next Step</span></span>  
 [<span data-ttu-id="d5a6d-126">Aufgabe 6: Importieren von Werten aus dem Cleanse Supplier List-Projekt</span><span class="sxs-lookup"><span data-stu-id="d5a6d-126">Task 6: Importing Values from the Cleanse Supplier List Project</span></span>](../../2014/tutorials/task-6-importing-values-from-the-cleanse-supplier-list-project.md)  
  
  
