---
title: 'Aufgabe 15: entwickeln und Ausführen des SSIS-Projekts | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 13adf4e0-216a-4992-b13d-b7b1e1629e77
ms.author: lle
author: lrtoyou1223
ms.openlocfilehash: 2a008cd848c95b48e6e22798b6ef903942b4d656
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719024"
---
# <a name="task-15-building-and-running-the-ssis-project"></a><span data-ttu-id="dd505-102">Aufgabe 15: Erstellen und Ausführen des SSIS-Projekts</span><span class="sxs-lookup"><span data-stu-id="dd505-102">Task 15: Building and Running the SSIS Project</span></span>

  <span data-ttu-id="dd505-103">In dieser Aufgabe erstellen Sie das SSIS-Projekt und führen es aus.</span><span class="sxs-lookup"><span data-stu-id="dd505-103">In this task, you build and run the SSIS project.</span></span> <span data-ttu-id="dd505-104">Wenn die 64-Bit-Version von Excel 2010 auf dem Computer installiert ist, sollten Sie den Wert von **Run64BitRuntime** auf **false** festlegen, damit die Excel-Quelle funktioniert.</span><span class="sxs-lookup"><span data-stu-id="dd505-104">If you have the 64-bit version of Excel 2010 installed on your computer, you should set the value of **Run64BitRuntime** to **False** for the Excel source to work.</span></span>  
  
1.  <span data-ttu-id="dd505-105">Klicken Sie im Fenster **Projektmappen-Explorer** im Menü auf **Projekt** , und klicken Sie dann auf **Eigenschaften von clean\andcurratesuppliers**.</span><span class="sxs-lookup"><span data-stu-id="dd505-105">In the **Solution Explorer** window, click **Project** on the menu, and click **CleanseAndCurateSuppliers Properties**.</span></span>  
  
2.  <span data-ttu-id="dd505-106">Erweitern Sie im Dialogfeld **Eigenschaften** auf der linken Seite die Option **Konfigurations Eigenschaften** , und klicken Sie auf **Debuggen**.</span><span class="sxs-lookup"><span data-stu-id="dd505-106">In the **Properties** dialog box, expand **Configuration Properties** on left, and click **Debugging**.</span></span>  
  
3.  <span data-ttu-id="dd505-107">Legen Sie **Run64BitRuntime** auf **false**fest.</span><span class="sxs-lookup"><span data-stu-id="dd505-107">Set **Run64BitRuntime** to **False**.</span></span>  
  
     <span data-ttu-id="dd505-108">![CleanseAndCurateSuppliers (Projekteigenschaften)](../../2014/tutorials/media/et-buildingandrunningthessisproject-01.jpg "CleanseAndCurateSuppliers (Projekteigenschaften)")</span><span class="sxs-lookup"><span data-stu-id="dd505-108">![CleanseAndCurateSuppliers Project Properties](../../2014/tutorials/media/et-buildingandrunningthessisproject-01.jpg "CleanseAndCurateSuppliers Project Properties")</span></span>  
  
4.  <span data-ttu-id="dd505-109">Klicken Sie auf **OK**, um das Dialogfeld **Eigenschaften** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="dd505-109">Click **OK** to close the **Properties** dialog box.</span></span>  
  
5.  <span data-ttu-id="dd505-110">Klicken Sie in der Menüleiste auf **Erstellen** , und klicken Sie auf **Build cleanmenandcurratesuppliers**.</span><span class="sxs-lookup"><span data-stu-id="dd505-110">Click **Build** on menu bar and click **Build CleanseAndCurateSuppliers**.</span></span> <span data-ttu-id="dd505-111">Stellen Sie sicher, dass keine Erstellungsfehler vorliegen.</span><span class="sxs-lookup"><span data-stu-id="dd505-111">Make sure that there are no build errors.</span></span>  
  
6.  <span data-ttu-id="dd505-112">Klicken Sie in der Menüleiste auf **Debuggen** und dann auf **Debugging starten**</span><span class="sxs-lookup"><span data-stu-id="dd505-112">Click **Debug** on the menu bar and click **Start Debugging**.</span></span>  
  
7.  <span data-ttu-id="dd505-113">Überprüfen Sie die Meldungen im Fenster Status, und überprüfen Sie, **ob das Paket** erfolgreich ausgeführt und beendet wurde</span><span class="sxs-lookup"><span data-stu-id="dd505-113">Review messages in the **Progress** window and verify that package executed and ended successfully.</span></span>  
  
     <span data-ttu-id="dd505-114">![Ergebnisse aus dem Statusfenster](../../2014/tutorials/media/et-buildingandrunningthessisproject-02.jpg "Ergebnisse aus dem Statusfenster")</span><span class="sxs-lookup"><span data-stu-id="dd505-114">![Results from Progress Window](../../2014/tutorials/media/et-buildingandrunningthessisproject-02.jpg "Results from Progress Window")</span></span>  
  
     <span data-ttu-id="dd505-115">![Endstatus aus dem Statusfenster](../../2014/tutorials/media/et-buildingandrunningthessisproject-03.jpg "Endstatus aus dem Statusfenster")</span><span class="sxs-lookup"><span data-stu-id="dd505-115">![Final Status from Progress Window](../../2014/tutorials/media/et-buildingandrunningthessisproject-03.jpg "Final Status from Progress Window")</span></span>  
  
8.  <span data-ttu-id="dd505-116">Klicken Sie in der Menüleiste auf **Debuggen** , und klicken Sie dann auf **Debuggen Debuggen**</span><span class="sxs-lookup"><span data-stu-id="dd505-116">Click **Debug** on menu bar and click **Stop Debugging** to stop the debugging session.</span></span> <span data-ttu-id="dd505-117">Wenn das Paket fehlschlägt, aktivieren Sie Daten-Viewer, und beobachten Sie den Datenfluss zwischen Komponenten.</span><span class="sxs-lookup"><span data-stu-id="dd505-117">If the package fails, you should enable data viewers and see how the data flows between components.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="dd505-118">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="dd505-118">Next Step</span></span>  
 [<span data-ttu-id="dd505-119">Aufgabe 16: Überprüfung mit dem Master Data Manager</span><span class="sxs-lookup"><span data-stu-id="dd505-119">Task 16: Verifying with Master Data Manager</span></span>](../../2014/tutorials/task-16-verifying-with-master-data-manager.md)  
  
  
