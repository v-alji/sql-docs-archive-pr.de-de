---
title: Angeben von "als Datums Tabelle markieren" zur Verwendung mit Zeit Intelligenz (SSAS-tabellarisch) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 30841d1f-0c3b-4575-8f4a-27a1492e248c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 81038369b8cb8636a2aa216f1c26783a96d5f7ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694721"
---
# <a name="specify-mark-as-date-table-for-use-with-time-intelligence-ssas-tabular"></a><span data-ttu-id="8e97d-102">Angeben von "Als Datumstabelle markieren" zur Verwendung mit Zeitintelligenz (SSAS – tabellarisch)</span><span class="sxs-lookup"><span data-stu-id="8e97d-102">Specify Mark as Date Table for use with Time Intelligence (SSAS Tabular)</span></span>
  <span data-ttu-id="8e97d-103">Um die Zeitintelligenzfunktionen in DAX-Formeln zu verwenden, müssen Sie eine Datumstabelle und eine eindeutige Bezeichnerspalte (datetime) des Date-Datentyps angeben.</span><span class="sxs-lookup"><span data-stu-id="8e97d-103">In order to use time intelligence functions in DAX formulas, you must specify a date table and a unique identifier (datetime) column of the Date data type.</span></span> <span data-ttu-id="8e97d-104">Sobald eine Spalte in der Datumstabelle als eindeutiger Bezeichner angegeben wird, können Sie Beziehungen zwischen Spalten in der Datumstabelle und beliebigen Faktentabellen erstellen.</span><span class="sxs-lookup"><span data-stu-id="8e97d-104">Once a column in the date table is specified as a unique identifier, you can create relationships between columns in the date table and any fact tables.</span></span>  
  
 <span data-ttu-id="8e97d-105">Bei Verwendung der Zeitintelligenzfunktionen gelten die folgenden Regeln:</span><span class="sxs-lookup"><span data-stu-id="8e97d-105">When using time intelligence functions, the following rules apply:</span></span>  
  
-   <span data-ttu-id="8e97d-106">Bei Verwendung von DAX-Zeitintelligenzfunktionen sollte niemals eine datetime-Spalte aus einer Faktentabelle angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8e97d-106">When using DAX time intelligence functions, never specify a datetime column from a fact table.</span></span> <span data-ttu-id="8e97d-107">Erstellen Sie im Modell immer eine separate Datumstabelle, die mindestens eine datetime-Spalte des Date-Datentyps mit eindeutigen Werten enthält.</span><span class="sxs-lookup"><span data-stu-id="8e97d-107">Always create a separate date table in your model with at least one datetime column of Date data type and with unique values.</span></span>  
  
-   <span data-ttu-id="8e97d-108">Stellen Sie sicher, dass die Datumstabelle über einen fortlaufenden Datumsbereich verfügt.</span><span class="sxs-lookup"><span data-stu-id="8e97d-108">Make sure your date table has a continuous date range.</span></span>  
  
-   <span data-ttu-id="8e97d-109">Die datetime-Spalte in der Datumstabelle sollte Tagesgranularität (ohne Unterteilung der Tage) aufweisen.</span><span class="sxs-lookup"><span data-stu-id="8e97d-109">The datetime column in the date table should be at day granularity (without fractions of a day).</span></span>  
  
-   <span data-ttu-id="8e97d-110">Sie müssen eine Datumstabelle und eine eindeutige Bezeichnerspalte im Dialogfeld **Als Datumstabelle markieren** angeben.</span><span class="sxs-lookup"><span data-stu-id="8e97d-110">You must specify a date table and a unique identifier column by using the **Mark the Date Table** dialog box.</span></span>  
  
-   <span data-ttu-id="8e97d-111">Erstellen Sie Beziehungen zwischen Faktentabellen und Spalten des Date-Datentyps in der Datumstabelle.</span><span class="sxs-lookup"><span data-stu-id="8e97d-111">Create relationships between fact tables and columns of Date data type in the date table.</span></span>  
  
#### <a name="to-specify-a-date-table-and-unique-identifier"></a><span data-ttu-id="8e97d-112">So geben Sie eine Datumstabelle und einen eindeutigen Bezeichner an</span><span class="sxs-lookup"><span data-stu-id="8e97d-112">To specify a date table and unique identifier</span></span>  
  
1.  <span data-ttu-id="8e97d-113">Klicken Sie im Modell-Designer auf die Datumstabelle.</span><span class="sxs-lookup"><span data-stu-id="8e97d-113">In the model designer, click the date table.</span></span>  
  
2.  <span data-ttu-id="8e97d-114">Klicken Sie im Menü **Tabelle** auf **Datum**, und klicken Sie dann auf **Als Datumstabelle markieren**</span><span class="sxs-lookup"><span data-stu-id="8e97d-114">Click the **Table** menu, then click **Date**, and then click **Mark as Date Table**</span></span>  
  
3.  <span data-ttu-id="8e97d-115">Wählen Sie im Dialogfeld **Als Datumstabelle markieren** im Listenfeld **Datum** eine Spalte aus, die als eindeutiger Bezeichner verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8e97d-115">In the **Mark as Date Table** dialog box, in the **Date** listbox, select a column to be used as a unique identifier.</span></span> <span data-ttu-id="8e97d-116">Diese Spalte muss eindeutige Werte enthalten und sollte den Date-Datentyp aufweisen.</span><span class="sxs-lookup"><span data-stu-id="8e97d-116">This column must contain unique values and should be of Date data type.</span></span> <span data-ttu-id="8e97d-117">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8e97d-117">For example:</span></span>  
  
    |<span data-ttu-id="8e97d-118">Date</span><span class="sxs-lookup"><span data-stu-id="8e97d-118">Date</span></span>|  
    |----------|  
    |<span data-ttu-id="8e97d-119">7/1/2010 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="8e97d-119">7/1/2010 12:00:00 AM</span></span>|  
    |<span data-ttu-id="8e97d-120">7/2/2010 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="8e97d-120">7/2/2010 12:00:00 AM</span></span>|  
    |<span data-ttu-id="8e97d-121">7/3/2010 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="8e97d-121">7/3/2010 12:00:00 AM</span></span>|  
    |<span data-ttu-id="8e97d-122">7/4/2010 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="8e97d-122">7/4/2010 12:00:00 AM</span></span>|  
    |<span data-ttu-id="8e97d-123">7/5/2010 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="8e97d-123">7/5/2010 12:00:00 AM</span></span>|  
  
4.  <span data-ttu-id="8e97d-124">Erstellen Sie ggf. Beziehungen zwischen Faktentabellen und der Datumstabelle.</span><span class="sxs-lookup"><span data-stu-id="8e97d-124">If necessary, create any relationships between fact tables and the date table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e97d-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8e97d-125">See Also</span></span>  
 <span data-ttu-id="8e97d-126">[Berechnungen &#40;tabellarischen SSAS-&#41;](calculations-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="8e97d-126">[Calculations &#40;SSAS Tabular&#41;](calculations-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="8e97d-127">Zeit Intelligenz Funktionen &#40;DAX-&#41;</span><span class="sxs-lookup"><span data-stu-id="8e97d-127">Time Intelligence Functions &#40;DAX&#41;</span></span>](/dax/time-intelligence-functions-dax)  
  
  
