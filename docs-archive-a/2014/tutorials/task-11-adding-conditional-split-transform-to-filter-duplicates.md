---
title: 'Aufgabe 11: Hinzufügen der Transformation für bedingtes Teilen zum Filtern von Duplikaten | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 3094bd57-5cf4-4860-bf51-fadd1b309f94
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: e8370563c4275df0d0513d5434a8b16efba728d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726366"
---
# <a name="task-11-adding-conditional-split-transform-to-filter-duplicates"></a><span data-ttu-id="d13f8-102">Aufgabe 11: Hinzufügen der Transformation „Bedingtes Teilen“ zur Filterung von Duplikaten</span><span class="sxs-lookup"><span data-stu-id="d13f8-102">Task 11: Adding Conditional Split Transform to Filter Duplicates</span></span>
  <span data-ttu-id="d13f8-103">In dieser Aufgabe fügen Sie die Transformation für bedingtes Teilen zum Datenfluss hinzu.</span><span class="sxs-lookup"><span data-stu-id="d13f8-103">In this task, you add the Conditional Split Transform to the data flow.</span></span> <span data-ttu-id="d13f8-104">Mit dieser Transformation können Sie Duplikate aus dem eingehenden Recordset filtern.</span><span class="sxs-lookup"><span data-stu-id="d13f8-104">This transform helps you filter duplicates from the incoming record set.</span></span> <span data-ttu-id="d13f8-105">Die Transformation für Fuzzygruppierung gruppiert die gefundenen übereinstimmenden Datensätze und wählt einen der Datensätze als Pivotdatensatz aus.</span><span class="sxs-lookup"><span data-stu-id="d13f8-105">The Fuzzy Group transform groups the records that it finds to be matches and picks one of the records as a pivot record.</span></span> <span data-ttu-id="d13f8-106">Alle Datensätze in einer Gruppe verfügen über denselben _key_out-Wert.</span><span class="sxs-lookup"><span data-stu-id="d13f8-106">All the records in a group have the same _key_out value.</span></span> <span data-ttu-id="d13f8-107">Für den Pivotdatensatz in der Gruppe sind der _key_in-Wert und der _key_out-Wert gleich.</span><span class="sxs-lookup"><span data-stu-id="d13f8-107">The pivot record in the group has _key_in same as the _key_out value.</span></span> <span data-ttu-id="d13f8-108">Für die anderen Datensätze in der Gruppe sind die Werte für _key_in und _key_out unterschiedlich.</span><span class="sxs-lookup"><span data-stu-id="d13f8-108">The other records in the group have different values for _key_in and _key_out.</span></span> <span data-ttu-id="d13f8-109">Wenn Sie mit condition _key_in==_key_out filtern, erhalten Sie daher nur die Pivotzeile in der Gruppe.</span><span class="sxs-lookup"><span data-stu-id="d13f8-109">Therefore, when you filter using the condition _key_in==_key_out, you only get the pivot row in the group.</span></span>  
  
1.  <span data-ttu-id="d13f8-110">Ziehen Sie die Transformation für **bedingtes Teilen** aus **Common** section in der **SSIS-Toolbox** auf die Registerkarte **Datenfluss** .</span><span class="sxs-lookup"><span data-stu-id="d13f8-110">Drag-drop **Conditional Split** Transform from **Common** section in the **SSIS Toolbox** to the **Data Flow** tab.</span></span>  
  
2.  <span data-ttu-id="d13f8-111">Klicken Sie **mit der rechten** Maustaste auf die **Transformation für bedingtes Teilen** , und klicken Sie dann auf **Umbenennen**.</span><span class="sxs-lookup"><span data-stu-id="d13f8-111">Right-click **Conditional Split Transform** in the **Data Flow** tab, and click **Rename**.</span></span> <span data-ttu-id="d13f8-112">Geben Sie **Filter Duplikate** ein, und drücken **Sie Eingabe**.</span><span class="sxs-lookup"><span data-stu-id="d13f8-112">Type **Filter Duplicates** and press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="d13f8-113">Verbinden Sie **Gruppen Lieferanten mit übereinstimmenden IDs** , um **Duplikate zu filtern**.</span><span class="sxs-lookup"><span data-stu-id="d13f8-113">Connect **Group Suppliers with Matching IDs** to **Filter Duplicates**.</span></span>  
  
4.  <span data-ttu-id="d13f8-114">Doppelklicken Sie auf **Filter Duplikate** , um das Dialogfeld **Transformations-Editor für bedingtes Teilen aufzurufen** .</span><span class="sxs-lookup"><span data-stu-id="d13f8-114">Double-click **Filter Duplicates** to launch the **Conditional Split Transform Editor** dialog box.</span></span>  
  
5.  <span data-ttu-id="d13f8-115">Erweitern Sie im linken oberen Bereich die Option **Spalten** .</span><span class="sxs-lookup"><span data-stu-id="d13f8-115">Expand **Columns** in the top-left pane.</span></span>  
  
6.  <span data-ttu-id="d13f8-116">Ziehen Sie **_key_in** in die Spalte **Bedingung** .</span><span class="sxs-lookup"><span data-stu-id="d13f8-116">Drag-drop **_key_in** to the **Condition** column.</span></span>  
  
7.  <span data-ttu-id="d13f8-117">Geben Sie = = (entspricht) neben **_key_in** ein, und ziehen Sie **_key_out**.</span><span class="sxs-lookup"><span data-stu-id="d13f8-117">Type == (equals to) next to **_key_in** and drag-drop **_key_out**.</span></span>  
  
8.  <span data-ttu-id="d13f8-118">Klicken Sie in der Spalte **Ausgabe Name** auf **Fall 1** , geben Sie **eindeutige Datensätze**ein, und drücken **Sie Eingabe**Taste.</span><span class="sxs-lookup"><span data-stu-id="d13f8-118">Click **Case 1** in the **Output Name** column, type **Unique Records**, and press **ENTER**.</span></span>  
  
     <span data-ttu-id="d13f8-119">![Transformations-Editor für bedingtes Teilen](../../2014/tutorials/media/et-addingconditionalsplittransformtofilterduplicates.jpg "Transformations-Editor für bedingtes Teilen")</span><span class="sxs-lookup"><span data-stu-id="d13f8-119">![Conditional Split Transformation Editor](../../2014/tutorials/media/et-addingconditionalsplittransformtofilterduplicates.jpg "Conditional Split Transformation Editor")</span></span>  
  
9. <span data-ttu-id="d13f8-120">Klicken Sie zum Schließen des Dialog Felds **Transformations-Editor für bedingtes Teilen** auf **OK** .</span><span class="sxs-lookup"><span data-stu-id="d13f8-120">Click **OK** to close the **Conditional Split Transformation Editor** dialog box.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="d13f8-121">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="d13f8-121">Next Step</span></span>  
 [<span data-ttu-id="d13f8-122">Aufgabe 12: Hinzufügen der Transformation „Abgeleitete Spalten“ zum Hinzufügen der für MDS erforderlichen Spalten</span><span class="sxs-lookup"><span data-stu-id="d13f8-122">Task 12: Adding Derived Column Transform to Add Columns Required by MDS</span></span>](../../2014/tutorials/task-12-adding-derived-column-transform-to-add-columns-required-by-mds.md)  
  
  
