---
title: 'Aufgabe 3: Importieren von Domänen Werten aus einer Excel-Datei | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 242e8309-1195-495b-9cd5-aa127748c185
ms.author: lle
author: lrtoyou1223
ms.openlocfilehash: 707a3925bb6d0014e2a1248f904123b076024e2c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609592"
---
# <a name="task-3-importing-domain-values-from-an-excel-file"></a><span data-ttu-id="38746-102">Aufgabe 3: Importieren von Domänenwerten aus einer Excel-Datei</span><span class="sxs-lookup"><span data-stu-id="38746-102">Task 3: Importing Domain Values from an Excel File</span></span>

  <span data-ttu-id="38746-103">In dieser Aufgabe importieren Sie Werte für die Domäne **State** aus einem Arbeitsblatt einer Excel-Datei.</span><span class="sxs-lookup"><span data-stu-id="38746-103">In this task, you import values for the **State** domain from a worksheet of an Excel file.</span></span>

1.  <span data-ttu-id="38746-104">Klicken Sie in der **Domänenliste** auf die Domäne **State**.</span><span class="sxs-lookup"><span data-stu-id="38746-104">Click **State** domain in the **Domain list**.</span></span>

2.  <span data-ttu-id="38746-105">Stellen Sie sicher, dass die Registerkarte **Domänenwerte** im rechten Bereich aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="38746-105">Ensure that the **Domain Values** tab is active in the right pane.</span></span>

3.  <span data-ttu-id="38746-106">Klicken Sie im rechten Bereich auf der Symbolleiste auf den **Nach-unten-Pfeil** neben der Schaltfläche **Werte importieren** , und klicken Sie auf **Gültige Werte aus Excel importieren**.</span><span class="sxs-lookup"><span data-stu-id="38746-106">In the right pane, from the toolbar, click **down arrow** next to the **Import Values** button, and click **Import Valid Values from Excel**.</span></span>

     <span data-ttu-id="38746-107">![Gültige Werte aus Excel importieren (Menü)](../../2014/tutorials/media/et-importingdomainvaluesfromanexcelfile-01.jpg "Gültige Werte aus Excel importieren (Menü)")</span><span class="sxs-lookup"><span data-stu-id="38746-107">![Import Valid Values from Excel Menu](../../2014/tutorials/media/et-importingdomainvaluesfromanexcelfile-01.jpg "Import Valid Values from Excel Menu")</span></span>

4.  <span data-ttu-id="38746-108">Klicken Sie auf **Durchsuchen**, wählen Sie **Suppliers.xls**aus, und klicken Sie auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="38746-108">Click **Browse**, select **Suppliers.xls**, and click **Open**.</span></span>

5.  <span data-ttu-id="38746-109">Wählen Sie **StatesToImport$** als **Arbeitsblatt**aus.</span><span class="sxs-lookup"><span data-stu-id="38746-109">Select **StatesToImport$** for the **Worksheet**.</span></span>

     <span data-ttu-id="38746-110">![Domänenwerte importieren (Dialogfeld)](../../2014/tutorials/media/et-importingdomainvaluesfromanexcelfile-02.jpg "Domänenwerte importieren (Dialogfeld)")</span><span class="sxs-lookup"><span data-stu-id="38746-110">![Import Domain Values Dialog Box](../../2014/tutorials/media/et-importingdomainvaluesfromanexcelfile-02.jpg "Import Domain Values Dialog Box")</span></span>

6.  <span data-ttu-id="38746-111">Klicken Sie auf **OK** , um das Dialogfeld **Domänenwerte importieren** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="38746-111">Click **OK** to close the **Import Domain Values** dialog box.</span></span> <span data-ttu-id="38746-112">Die Namen aller importierten Bundesstaaten sollten in der Liste angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="38746-112">You should see all the names of states you imported in the list.</span></span> <span data-ttu-id="38746-113">Die Option **Nur neue anzeigen** wird nach dem Import automatisch aktiviert.</span><span class="sxs-lookup"><span data-stu-id="38746-113">Notice that **Show Only New** option is automatically selected after importing.</span></span> <span data-ttu-id="38746-114">Wenn Sie Werte importieren und die alten Werte nicht in der Liste angezeigt werden, liegt dies daran, dass diese Option nach dem Import automatisch aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="38746-114">When you import values and you don't see the old values in the list, it is because this option is automatically enabled after importing.</span></span> <span data-ttu-id="38746-115">Um alle Werte anzuzeigen, deaktivieren Sie das Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="38746-115">To see all the values, clear the check box.</span></span> <span data-ttu-id="38746-116">Wenn Sie den gleichen Satz Werte erneut importieren, wird keiner der Werte importiert, da sie bereits in der Domäne vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="38746-116">If you import the same set of values again, none of the values are imported as they already exist in the domain.</span></span>

     <span data-ttu-id="38746-117">![Kontrollkästchen "Nur neue anzeigen" für Domänenwerte](../../2014/tutorials/media/et-importingdomainvaluesfromanexcelfile-03.jpg "Kontrollkästchen "Nur neue anzeigen" für Domänenwerte")</span><span class="sxs-lookup"><span data-stu-id="38746-117">![Show Only New Checkbox on Domain Values](../../2014/tutorials/media/et-importingdomainvaluesfromanexcelfile-03.jpg "Show Only New Checkbox on Domain Values")</span></span>

## <a name="next-step"></a><span data-ttu-id="38746-118">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="38746-118">Next Step</span></span>
 [<span data-ttu-id="38746-119">Aufgabe 4: Festlegen von Domänenregeln</span><span class="sxs-lookup"><span data-stu-id="38746-119">Task 4: Setting Domain Rules</span></span>](../../2014/tutorials/task-4-setting-domain-rules.md)


