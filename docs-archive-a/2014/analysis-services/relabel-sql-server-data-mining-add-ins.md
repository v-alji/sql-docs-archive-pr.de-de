---
title: Relabel (SQL Server Data Mining-Add-Ins) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data preparation
- relabel
- data cleaning
ms.assetid: af041b39-fdd1-4cb5-a5ef-2f3ddab84614
author: minewiskan
ms.author: owend
ms.openlocfilehash: a625676f60e2da32e19b85a94002b51eeb9ac816
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618290"
---
# <a name="relabel-sql-server-data-mining-add-ins"></a><span data-ttu-id="6cd99-102">Neu bezeichnen (SQL Server Data Mining-Add-Ins)</span><span class="sxs-lookup"><span data-stu-id="6cd99-102">Relabel (SQL Server Data Mining Add-ins)</span></span>
  <span data-ttu-id="6cd99-103">![Office 13-Symbol für das Tool "Neu bezeichnen"](media/dm13-relabel.gif "Office 13-Symbol für das Tool "Neu bezeichnen"")</span><span class="sxs-lookup"><span data-stu-id="6cd99-103">![Office 13 icon for Relabel tool](media/dm13-relabel.gif "Office 13 icon for Relabel tool")</span></span>

 <span data-ttu-id="6cd99-104">Im Data Mining-Client für Excel können Sie neue Bezeichnungen für Ihre Daten erstellen, um die Ergebnisse der Analyse übersichtlicher zu gestalten.</span><span class="sxs-lookup"><span data-stu-id="6cd99-104">The Data Mining Client for Excel helps you create new labels for data to make it easier to understand the results of analysis.</span></span>

 <span data-ttu-id="6cd99-105">Gründe für das Neubezeichnen umfassen:</span><span class="sxs-lookup"><span data-stu-id="6cd99-105">Reasons for relabeling include:</span></span>

-   <span data-ttu-id="6cd99-106">Die Daten enthalten codierte Ergebnisse, wie 1 für Männlich und 2 für Weiblich.</span><span class="sxs-lookup"><span data-stu-id="6cd99-106">The data includes results that were coded, such as 1 for Male and 2 for Female.</span></span>

-   <span data-ttu-id="6cd99-107">Sie gruppieren numerische Werte und möchten den Bereichen einen aussagekräftigen Namen geben.</span><span class="sxs-lookup"><span data-stu-id="6cd99-107">You are bucketing numeric values and want to give the ranges a descriptive name.</span></span>

-   <span data-ttu-id="6cd99-108">Sie möchten lange Namen vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="6cd99-108">You want to simplify long names.</span></span>

## <a name="using-the-relabel-wizard"></a><span data-ttu-id="6cd99-109">Verwenden des Assistenten zum Neubezeichnen</span><span class="sxs-lookup"><span data-stu-id="6cd99-109">Using the Relabel Wizard</span></span>

1.  <span data-ttu-id="6cd99-110">Klicken Sie im Menüband **Data Mining** auf **Bereinigen** , und wählen Sie dann **erneut Bezeichnung**aus.</span><span class="sxs-lookup"><span data-stu-id="6cd99-110">In the **Data Mining** ribbon, click **Clean** and then select **Re-Label**.</span></span>

2.  <span data-ttu-id="6cd99-111">Wählen Sie die Tabelle oder den Datenbereich mit den zu bereinigenden Daten aus.</span><span class="sxs-lookup"><span data-stu-id="6cd99-111">Select the table or data range that has the data you want to fix.</span></span>

3.  <span data-ttu-id="6cd99-112">Wählen Sie auf der Seite **neu bezeichnen** des Assistenten eine einzelne Spalte aus. Wählen Sie hierzu entweder die Spalte aus der Dropdown Liste aus, oder klicken Sie auf die Spalte im Bereich **Daten Stichproben** .</span><span class="sxs-lookup"><span data-stu-id="6cd99-112">In the **Re-label** page of the wizard, select a single column, either by choosing the column from the dropdown list, or by clicking the column in the **Data samples** pane.</span></span>

     <span data-ttu-id="6cd99-113">Im Bereich **Daten Stichproben** werden nur ungefähr 50 Daten Zeilen angezeigt. Sie werden jedoch als Stichprobe angezeigt, um sicherzustellen, dass Sie eine gute Verteilung von Werten sehen.</span><span class="sxs-lookup"><span data-stu-id="6cd99-113">The **Data samples** pane only shows about 50 rows of data, but they are sampled to ensure that you see a good spread of values.</span></span>

     <span data-ttu-id="6cd99-114">Klicken Sie auf die Spaltenüberschrift für **count** , um nach der Anzahl der einzelnen Werte zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="6cd99-114">Click the column header for **Count** to sort by the count of each value.</span></span>

     <span data-ttu-id="6cd99-115">Sie können auch nach **ursprünglichen Bezeichnungen**sortieren. Dies ist praktisch, wenn Sie alle höchsten oder niedrigsten Werte zuerst neu bezeichnen möchten.</span><span class="sxs-lookup"><span data-stu-id="6cd99-115">You can also sort by **Original Labels**, which is handy if you want to re-label all the highest or lowest values first.</span></span>

4.  <span data-ttu-id="6cd99-116">Überprüfen Sie auf der Seite Daten **neu bezeichnen** des Assistenten die Werte in der Spalte **Original Bezeichnungen** , und entscheiden Sie, wie Sie diese gruppieren oder bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="6cd99-116">In the **Re-label** data page of the wizard, review the values in the **Original Labels** column, and decide how you want to group or edit them.</span></span>

5.  <span data-ttu-id="6cd99-117">Geben Sie einen neuen Wert in die Zeile unter **neue Bezeichnungen**ein.</span><span class="sxs-lookup"><span data-stu-id="6cd99-117">Type a new value into the row under **New Labels**.</span></span> <span data-ttu-id="6cd99-118">Sie können auch einen Wert aus der Liste der vorhandenen Werte auswählen.</span><span class="sxs-lookup"><span data-stu-id="6cd99-118">You can also choose a value from the list of existing values.</span></span> <span data-ttu-id="6cd99-119">Bei der Eingabe neuer Werte werden diese sofort für die Wiederverwendung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6cd99-119">As you type new values, they become available for re-use right away.</span></span>

6.  <span data-ttu-id="6cd99-120">Wenn Sie genügend Zeilen eingegeben haben, klicken Sie auf **weiter**, und wählen Sie auf der Seite **Ziel auswählen** aus, wo Sie die neu zu speichernden Daten speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="6cd99-120">When you have entered enough rows, click **Next**, and on the **Select Destination** page, choose where you'll save the relabeled data.</span></span>

    -   <span data-ttu-id="6cd99-121">**Dem aktuellen Arbeitsblatt als neue Spalte hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="6cd99-121">**Add as a new column to the current worksheet**</span></span>

         <span data-ttu-id="6cd99-122">Klicken Sie auf diese Option, um der Tabelle eine neue Spalte mit den neuen Werten hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="6cd99-122">Click to add a new column to the table that contains the new values.</span></span>

    -   <span data-ttu-id="6cd99-123">**Blattdaten mit Änderungen in ein neues Arbeitsblatt kopieren**</span><span class="sxs-lookup"><span data-stu-id="6cd99-123">**Copy sheet data with changes to a new worksheet**</span></span>

         <span data-ttu-id="6cd99-124">Klicken Sie auf diese Option, um ein neues Arbeitsblatt mit den aktualisierten Daten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6cd99-124">Click to create a new worksheet that contains the updated data.</span></span>

    -   <span data-ttu-id="6cd99-125">**Daten direkt ändern**</span><span class="sxs-lookup"><span data-stu-id="6cd99-125">**Change data in place**</span></span>

         <span data-ttu-id="6cd99-126">Klicken Sie auf diese Option, um die ursprünglichen Daten durch die neuen Werte zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="6cd99-126">Click to replace the original data with the new values.</span></span>

## <a name="see-also"></a><span data-ttu-id="6cd99-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6cd99-127">See Also</span></span>
 [<span data-ttu-id="6cd99-128">Durchsuchen und Bereinigen von Daten</span><span class="sxs-lookup"><span data-stu-id="6cd99-128">Exploring and Cleaning Data</span></span>](exploring-and-cleaning-data.md)


