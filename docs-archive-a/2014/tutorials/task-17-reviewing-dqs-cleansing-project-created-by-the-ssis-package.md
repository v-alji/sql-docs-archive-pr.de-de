---
title: 'Aufgabe 17: Überprüfen des vom SSIS-Paket erstellten DQS-Bereinigungs Projekts | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: fc6cc258-72f5-4593-8edb-9f5bc66de9db
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 0876a0b727e810f8834fcf5445958bf9884a87f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694849"
---
# <a name="task-17-reviewing-dqs-cleansing-project-created-by-the-ssis-package"></a><span data-ttu-id="f9e89-102">Aufgabe 17: Überprüfung des vom SSIS-Paket erstellten DQS-Bereinigungsprojekts</span><span class="sxs-lookup"><span data-stu-id="f9e89-102">Task 17: Reviewing DQS Cleansing Project Created by the SSIS package</span></span>
  <span data-ttu-id="f9e89-103">In dieser Aufgabe öffnen Sie das DQS-Projekt, das durch das SSIS-Paket in DQS-Client erstellt wurde, prüfen die Ergebnisse des Bereinigungsprozesses, führen optional eine interaktive Bereinigung aus und exportieren die Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="f9e89-103">In this task, you open the DQS project created by the SSIS package in DQS Client, review the results from the cleansing process, and optionally perform interactive cleansing and export the results.</span></span>  
  
1.  <span data-ttu-id="f9e89-104">Starten Sie **Data Quality-Client**.</span><span class="sxs-lookup"><span data-stu-id="f9e89-104">Launch **Data Quality Client**.</span></span>  
  
2.  <span data-ttu-id="f9e89-105">Klicken Sie im Bereich **Verwaltung** auf **Aktivitäts Überwachung** .</span><span class="sxs-lookup"><span data-stu-id="f9e89-105">Click **Activity Monitoring** in the **Administration** pane.</span></span>  
  
3.  <span data-ttu-id="f9e89-106">Sortieren Sie die Liste basierend auf der **Startzeit der Aktivität** , um den letzten Datensatz anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f9e89-106">Sort the list based on **Activity Start Time** to see the latest record.</span></span>  
  
4.  <span data-ttu-id="f9e89-107">Beachten Sie, dass der Name des Projekts im folgenden Format angezeigt wird: **cleanabandcurr. bereinigen Lieferant Data. GUID**.</span><span class="sxs-lookup"><span data-stu-id="f9e89-107">Notice that you see a name of the project in the following format: **CleanseAndCurate.Cleanse Supplier Data.GUID**.</span></span>  
  
     <span data-ttu-id="f9e89-108">![Von SSIS-Paket erstelltes DQS-Bereinigungsprojekt](../../2014/tutorials/media/et-reviewingdqscpcreatedbythessispackage.jpg "Von SSIS-Paket erstelltes DQS-Bereinigungsprojekt")</span><span class="sxs-lookup"><span data-stu-id="f9e89-108">![DQS Cleansing Project Created by SSIS Package](../../2014/tutorials/media/et-reviewingdqscpcreatedbythessispackage.jpg "DQS Cleansing Project Created by SSIS Package")</span></span>  
  
5.  <span data-ttu-id="f9e89-109">Beachten Sie, dass der Wert im Feld **ist aktiv** **ist.**</span><span class="sxs-lookup"><span data-stu-id="f9e89-109">Notice that the value in the **Is Active** field is **Active**.</span></span>  
  
6.  <span data-ttu-id="f9e89-110">Klicken Sie im unteren Bereich auf die Registerkarte **Profiler** , um die Profiler-Statistik für die vom SSIS-Paket ausgeführte Bereinigungs Aktivität anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f9e89-110">Click **Profiler** tab in the bottom pane to see profiler statistics for the Cleansing activity that the SSIS package performed.</span></span>  
  
7.  <span data-ttu-id="f9e89-111">Klicken Sie auf **Schließen** , um den **Verwaltungs** Bildschirm zu schließen.</span><span class="sxs-lookup"><span data-stu-id="f9e89-111">Click **Close** to close the **Administration** screen.</span></span>  
  
8.  <span data-ttu-id="f9e89-112">Klicken Sie auf der Hauptseite von **DQS-Client**im Bereich **Data Quality-Projekte** auf **Data Quality-Projekt öffnen** .</span><span class="sxs-lookup"><span data-stu-id="f9e89-112">In the main page of **DQS Client**, click **Open Data Quality Project** in the **Data Quality Projects** pane.</span></span>  
  
9. <span data-ttu-id="f9e89-113">Wählen Sie in der Liste der Projekte das Projekt aus, das von der SSIS-DQS-Bereinigungskomponente erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="f9e89-113">In the list of projects, select the project created by SSIS DQS Cleansing component.</span></span> <span data-ttu-id="f9e89-114">Der Name des Projekts sollte folgendes Format aufweisen: **cleanabandcurr. bereinigen Sie Supplier Data. GUID (in roter Farbe)**.</span><span class="sxs-lookup"><span data-stu-id="f9e89-114">The name of the project should be in format:  **CleanseAndCurate.Cleanse Supplier Data.GUID (in red color)**.</span></span> <span data-ttu-id="f9e89-115">Möglicherweise müssen Sie die Liste basierend auf der Spalte mit **dem Erstellungsdatum** sortieren und nach dem neuesten Datensatz suchen.</span><span class="sxs-lookup"><span data-stu-id="f9e89-115">You may need to sort the list based on **Date Created** column and look for the latest record.</span></span>  
  
10. <span data-ttu-id="f9e89-116">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f9e89-116">Click **Next**.</span></span>  
  
11. <span data-ttu-id="f9e89-117">Die Seite **Ergebnisse verwalten und anzeigen** sollte Ihnen aus der interaktiven Bereinigung vertraut sein, die Sie zuvor in diesem Lernprogramm durchgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="f9e89-117">The **Manage and View Results** page should be familiar to you from the interactive cleansing you did earlier in this tutorial.</span></span>  
  
12. <span data-ttu-id="f9e89-118">Überprüfen Sie die Bereinigungsergebnisse.</span><span class="sxs-lookup"><span data-stu-id="f9e89-118">Review the cleansing results.</span></span> <span data-ttu-id="f9e89-119">Sie können auf der nächsten Seite auch interaktive Bereinigungen ausführen und Ergebnisse in eine Excel-Datei oder eine Datenbank exportieren.</span><span class="sxs-lookup"><span data-stu-id="f9e89-119">You can also perform interactive cleansing and export results to an Excel file or to a database in the next page.</span></span>  
  
13. <span data-ttu-id="f9e89-120">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f9e89-120">Click **Next**.</span></span> <span data-ttu-id="f9e89-121">Auf dieser Seite **exportieren** können Sie Ergebnisse in eine Excel-Datei, eine CSV-Datei oder eine SQL-Datenbank exportieren.</span><span class="sxs-lookup"><span data-stu-id="f9e89-121">In this **Export** page, you can export results to an excel file, CSV file, or to a SQL database.</span></span>  
  
14. <span data-ttu-id="f9e89-122">Klicken Sie auf **Fertig** stellen, um die Aktivität abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="f9e89-122">Click **Finish** to finish the activity.</span></span>  
  
15. <span data-ttu-id="f9e89-123">Klicken Sie im Bereich **Verwaltung** auf der **DQS-Client**-Hauptseite auf **Aktivitäts Überwachung** .</span><span class="sxs-lookup"><span data-stu-id="f9e89-123">In the main page of **DQS Client**, click **Activity Monitoring** in the **Administration** pane.</span></span>  
  
16. <span data-ttu-id="f9e89-124">Beachten Sie, dass der Wert des Felds **IsActive** für das Projekt jetzt **beendet** ist.</span><span class="sxs-lookup"><span data-stu-id="f9e89-124">Notice that the value of **IsActive** field for the project is **Ended** now.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="f9e89-125">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="f9e89-125">Next Step</span></span>  
 [<span data-ttu-id="f9e89-126">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="f9e89-126">Conclusion</span></span>](../../2014/tutorials/conclusion.md)  
  
  
