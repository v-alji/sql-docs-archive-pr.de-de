---
title: Datenprofil-Viewer F1-Hilfe | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.dataprofileviewer.f1
helpviewer_keywords:
- Data Profile Viewer [Integration Services]
- Data Profiling task [Integration Services], viewer
ms.assetid: 3469c60a-8f4f-46ba-999a-cb9070197fea
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7003e1299938bd53a6d16a5597d4566ba5c46579
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609977"
---
# <a name="data-profile-viewer-f1-help"></a><span data-ttu-id="e2b53-102">Datenprofil-Viewer (F1-Hilfe)</span><span class="sxs-lookup"><span data-stu-id="e2b53-102">Data Profile Viewer F1 Help</span></span>
  <span data-ttu-id="e2b53-103">Verwenden Sie den Datenprofil-Viewer, um die Ausgabe des Datenprofilerstellungs-Tasks anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e2b53-103">Use the Data Profile Viewer to view the output of the Data Profiling task.</span></span>  
  
 <span data-ttu-id="e2b53-104">Weitere Informationen zum Verwenden des Datenprofil-Viewers finden Sie unter [Datenprofil-Viewer](control-flow/data-profile-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="e2b53-104">For more information about how to use the Data Profile Viewer, see [Data Profile Viewer](control-flow/data-profile-viewer.md).</span></span> <span data-ttu-id="e2b53-105">Weitere Informationen zum Verwenden des Datenprofilerstellungs-Tasks, der die Profilausgabe erstellt, die Sie im Datenprofil-Viewer analysieren, finden Sie unter [Einrichten von Datenprofilerstellungs-Tasks](control-flow/data-profiling-task.md).</span><span class="sxs-lookup"><span data-stu-id="e2b53-105">For more information about how to use the Data Profiling task, which creates the profile output that you analyze in the Data Profile Viewer, see [Setup of the Data Profiling Task](control-flow/data-profiling-task.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="e2b53-106">Statische Optionen</span><span class="sxs-lookup"><span data-stu-id="e2b53-106">Static Options</span></span>  
 <span data-ttu-id="e2b53-107">**Öffnen**</span><span class="sxs-lookup"><span data-stu-id="e2b53-107">**Open**</span></span>  
 <span data-ttu-id="e2b53-108">Klicken Sie, um nach der gespeicherten Datei zu suchen, die die Ausgabe des Datenprofilerstellungs-Tasks enthält.</span><span class="sxs-lookup"><span data-stu-id="e2b53-108">Click to browse for the saved file that contains the output of the Data Profiling task.</span></span>  
  
 <span data-ttu-id="e2b53-109">Bereich**Profile**</span><span class="sxs-lookup"><span data-stu-id="e2b53-109">**Profiles** pane</span></span>  
 <span data-ttu-id="e2b53-110">Erweitern Sie die Struktur im Bereich **Profile** , um die Profile anzuzeigen, die in der Ausgabe enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="e2b53-110">Expand the tree in the **Profiles** pane to see the profiles that are included in the output.</span></span> <span data-ttu-id="e2b53-111">Wählen Sie ein Profil aus, um die Ergebnisse für dieses Profil anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e2b53-111">Select a profile to view the results for that profile.</span></span>  
  
 <span data-ttu-id="e2b53-112">Bereich**Meldung**</span><span class="sxs-lookup"><span data-stu-id="e2b53-112">**Message** pane</span></span>  
 <span data-ttu-id="e2b53-113">Zeigt Statusmeldungen an.</span><span class="sxs-lookup"><span data-stu-id="e2b53-113">Displays status messages.</span></span>  
  
 <span data-ttu-id="e2b53-114">Bereich**Drilldown**</span><span class="sxs-lookup"><span data-stu-id="e2b53-114">**Drilldown** pane</span></span>  
 <span data-ttu-id="e2b53-115">Zeigt die Datensätze an, die mit einem Wert in der Ausgabe übereinstimmen, wenn die vom Datenprofilerstellungs-Task verwendete Datenquelle verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="e2b53-115">Displays the rows of data that match a value in the output, if the data source that is used by the Data Profiling task is available.</span></span>  
  
 <span data-ttu-id="e2b53-116">Beispiel: Wenn Sie die Ausgabe eines Verteilungsprofils für Spaltenwert für eine Spalte US-Bundesstaat anzeigen, enthält der Bereich **Detaillierte Wertverteilung** möglicherweise eine Zeile für "WA".</span><span class="sxs-lookup"><span data-stu-id="e2b53-116">For example, if you are viewing the output of a Column Value Distribution profile for a US State column, the **Detailed Value Distribution** pane might contain a row for "WA".</span></span> <span data-ttu-id="e2b53-117">Doppelklicken Sie auf die Zeile im Bereich **Detaillierte Wertverteilung** , um die Datenreihen anzuzeigen, bei denen der Wert der Bundesstaatspalte im Drilldownbereich „WA“ lautet.</span><span class="sxs-lookup"><span data-stu-id="e2b53-117">Double-click the row in the **Detailed Value Distribution** pane to see the rows of data where the value of the state column is "WA" in the drilldown pane.</span></span>  
  
## <a name="dynamic-options"></a><span data-ttu-id="e2b53-118">Dynamische Optionen</span><span class="sxs-lookup"><span data-stu-id="e2b53-118">Dynamic Options</span></span>  
  
### <a name="profile-type--column-length-distribution-profile"></a><span data-ttu-id="e2b53-119">Profiltyp = Verteilungsprofil für Spaltenlänge</span><span class="sxs-lookup"><span data-stu-id="e2b53-119">Profile Type = Column Length Distribution Profile</span></span>  
  
#### <a name="column-length-distribution-profile---column-pane"></a><span data-ttu-id="e2b53-120">Verteilungsprofil für Spaltenlänge – \<column>-Bereich</span><span class="sxs-lookup"><span data-stu-id="e2b53-120">Column Length Distribution Profile - \<column> pane</span></span>  
 <span data-ttu-id="e2b53-121">**Mindestlänge**</span><span class="sxs-lookup"><span data-stu-id="e2b53-121">**Minimum Length**</span></span>  
 <span data-ttu-id="e2b53-122">Zeigt die Mindestlänge der Werte in dieser Spalte an.</span><span class="sxs-lookup"><span data-stu-id="e2b53-122">Displays the minimum length of values in this column.</span></span>  
  
 <span data-ttu-id="e2b53-123">**Maximale Länge**</span><span class="sxs-lookup"><span data-stu-id="e2b53-123">**Maximum Length**</span></span>  
 <span data-ttu-id="e2b53-124">Zeigt die maximale Länge der Werte in dieser Spalte an.</span><span class="sxs-lookup"><span data-stu-id="e2b53-124">Displays the maximum length of values in this column.</span></span>  
  
 <span data-ttu-id="e2b53-125">**Führende Leerstellen ignorieren**</span><span class="sxs-lookup"><span data-stu-id="e2b53-125">**Ignore Leading Spaces**</span></span>  
 <span data-ttu-id="e2b53-126">Zeigt an, ob dieses Profil mit einem `IgnoreLeadingSpaces`-Wert von True oder False berechnet wurde.</span><span class="sxs-lookup"><span data-stu-id="e2b53-126">Displays whether this profile was computed with an `IgnoreLeadingSpaces` value of True or False.</span></span> <span data-ttu-id="e2b53-127">Diese Eigenschaft wurde auf der Seite **Profilanforderungen** vom Editor für den Datenprofilerstellungs-Task festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e2b53-127">This property was set on the **Profile Requests** page of the Data Profiling Task Editor.</span></span>  
  
 <span data-ttu-id="e2b53-128">**Nachfolgende Leerzeichen ignorieren**</span><span class="sxs-lookup"><span data-stu-id="e2b53-128">**Ignore Trailing Spaces**</span></span>  
 <span data-ttu-id="e2b53-129">Zeigt an, ob dieses Profil mit einem `IgnoreTrailingSpaces`-Wert von True oder False berechnet wurde.</span><span class="sxs-lookup"><span data-stu-id="e2b53-129">Displays whether this profile was computed with an `IgnoreTrailingSpaces` value of True or False.</span></span> <span data-ttu-id="e2b53-130">Diese Eigenschaft wurde auf der Seite **Profilanforderungen** vom Editor für den Datenprofilerstellungs-Task festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e2b53-130">This property was set on the **Profile Requests** page of the Data Profiling Task Editor.</span></span>  
  
 <span data-ttu-id="e2b53-131">**Zeilenanzahl**</span><span class="sxs-lookup"><span data-stu-id="e2b53-131">**Row Count**</span></span>  
 <span data-ttu-id="e2b53-132">Zeigt die Anzahl der Zeilen in der Tabelle oder Sicht an.</span><span class="sxs-lookup"><span data-stu-id="e2b53-132">Displays the number of rows in the table or view.</span></span>  
  
#### <a name="detailed-length-distribution-pane"></a><span data-ttu-id="e2b53-133">Bereich 'Detaillierte Längenverteilung'</span><span class="sxs-lookup"><span data-stu-id="e2b53-133">Detailed Length Distribution pane</span></span>  
 <span data-ttu-id="e2b53-134">**Länge**</span><span class="sxs-lookup"><span data-stu-id="e2b53-134">**Length**</span></span>  
 <span data-ttu-id="e2b53-135">Zeigt die in der Spalte, für die ein Profil erstellt wurde, gefundenen Spaltenlängen an.</span><span class="sxs-lookup"><span data-stu-id="e2b53-135">Displays the column lengths found in the profiled column.</span></span>  
  
 <span data-ttu-id="e2b53-136">**Count**</span><span class="sxs-lookup"><span data-stu-id="e2b53-136">**Count**</span></span>  
 <span data-ttu-id="e2b53-137">Zeigt die Anzahl von Zeilen an, in denen der Wert der Spalte, für die ein Profil erstellt wurde, die in der Spalte **Länge** angezeigte Länge hat.</span><span class="sxs-lookup"><span data-stu-id="e2b53-137">Displays the number of rows in which the value of the profiled column has the length shown in the **Length** column.</span></span>  
  
 <span data-ttu-id="e2b53-138">**Percentage**</span><span class="sxs-lookup"><span data-stu-id="e2b53-138">**Percentage**</span></span>  
 <span data-ttu-id="e2b53-139">Zeigt den Prozentsatz der Zeilen an, in denen der Wert der Spalte, für die ein Profil erstellt wurde, die in der Spalte **Länge** angezeigte Länge hat.</span><span class="sxs-lookup"><span data-stu-id="e2b53-139">Displays the percentage of rows in which the value of the profiled column has the length shown in the **Length** column.</span></span>  
  
### <a name="profile-type--column-null-ratio-profile"></a><span data-ttu-id="e2b53-140">Profiltyp = Profil für Spalten-NULL-Verhältnis</span><span class="sxs-lookup"><span data-stu-id="e2b53-140">Profile Type = Column Null Ratio Profile</span></span>  
  
#### <a name="column-null-ratio-profile---column-pane"></a><span data-ttu-id="e2b53-141">Profil für Spalten-NULL-Verhältnis – \<column>-Bereich</span><span class="sxs-lookup"><span data-stu-id="e2b53-141">Column Null Ratio Profile - \<column> pane</span></span>  
 <span data-ttu-id="e2b53-142">**NULL-Anzahl**</span><span class="sxs-lookup"><span data-stu-id="e2b53-142">**Null Count**</span></span>  
 <span data-ttu-id="e2b53-143">Zeigt die Anzahl der Zeilen an, in denen die Spalte, für die ein Profil erstellt wurde, einen NULL-Wert aufweist.</span><span class="sxs-lookup"><span data-stu-id="e2b53-143">Displays the number of rows in which the profiled column has a null value.</span></span>  
  
 <span data-ttu-id="e2b53-144">**NULL-Prozentsatz**</span><span class="sxs-lookup"><span data-stu-id="e2b53-144">**Null Percentage**</span></span>  
 <span data-ttu-id="e2b53-145">Zeigt den Prozentsatz der Zeilen an, in denen die Spalte, für die ein Profil erstellt wurde, einen NULL-Wert aufweist.</span><span class="sxs-lookup"><span data-stu-id="e2b53-145">Displays the percentage of rows in which the profiled column has a null value.</span></span>  
  
 <span data-ttu-id="e2b53-146">**Zeilenanzahl**</span><span class="sxs-lookup"><span data-stu-id="e2b53-146">**Row Count**</span></span>  
 <span data-ttu-id="e2b53-147">Zeigt die Anzahl der Zeilen in der Tabelle oder Sicht an.</span><span class="sxs-lookup"><span data-stu-id="e2b53-147">Displays the number of rows in the table or view.</span></span>  
  
### <a name="profile-type--column-pattern-profile"></a><span data-ttu-id="e2b53-148">Profiltyp = Spaltenmusterprofil</span><span class="sxs-lookup"><span data-stu-id="e2b53-148">Profile Type = Column Pattern Profile</span></span>  
  
#### <a name="column-pattern-profile---column-pane"></a><span data-ttu-id="e2b53-149">Spaltenmusterprofil – \<column>-Bereich</span><span class="sxs-lookup"><span data-stu-id="e2b53-149">Column Pattern Profile - \<column> pane</span></span>  
 <span data-ttu-id="e2b53-150">**Zeilenanzahl**</span><span class="sxs-lookup"><span data-stu-id="e2b53-150">**Row Count**</span></span>  
 <span data-ttu-id="e2b53-151">Zeigt die Anzahl der Zeilen in der Tabelle oder Sicht an.</span><span class="sxs-lookup"><span data-stu-id="e2b53-151">Displays the number of rows in the table or view.</span></span>  
  
#### <a name="pattern-distribution-pane"></a><span data-ttu-id="e2b53-152">Bereich 'Musterverteilung'</span><span class="sxs-lookup"><span data-stu-id="e2b53-152">Pattern Distribution pane</span></span>  
 <span data-ttu-id="e2b53-153">**Muster**</span><span class="sxs-lookup"><span data-stu-id="e2b53-153">**Pattern**</span></span>  
 <span data-ttu-id="e2b53-154">Zeigt das für die Spalte, für die ein Profil erstellt wurde, berechnete Muster an.</span><span class="sxs-lookup"><span data-stu-id="e2b53-154">Displays the patterns computed for the profiled column.</span></span>  
  
 <span data-ttu-id="e2b53-155">**Percentage**</span><span class="sxs-lookup"><span data-stu-id="e2b53-155">**Percentage**</span></span>  
 <span data-ttu-id="e2b53-156">Zeigt den Prozentsatz der Zeilen an, deren Werte mit dem in der Spalte **Muster** angezeigten Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="e2b53-156">Displays the percentage of rows whose values match the pattern displayed in the **Pattern** column.</span></span>  
  
### <a name="profile-type--column-statistics-profile"></a><span data-ttu-id="e2b53-157">Profiltyp = Spaltenstatistikprofil</span><span class="sxs-lookup"><span data-stu-id="e2b53-157">Profile Type = Column Statistics Profile</span></span>  
  
#### <a name="column-statistics-profile---column-pane"></a><span data-ttu-id="e2b53-158">Spaltenstatistikprofil – \<column>-Bereich</span><span class="sxs-lookup"><span data-stu-id="e2b53-158">Column Statistics Profile - \<column> pane</span></span>  
 <span data-ttu-id="e2b53-159">**Mindestanforderungen**</span><span class="sxs-lookup"><span data-stu-id="e2b53-159">**Minimum**</span></span>  
 <span data-ttu-id="e2b53-160">Zeigt den in der Spalte, für die ein Profil erstellt wurde, gefundenen Mindestwert an.</span><span class="sxs-lookup"><span data-stu-id="e2b53-160">Displays the minimum value found in the profiled column.</span></span>  
  
 <span data-ttu-id="e2b53-161">**Maximum**</span><span class="sxs-lookup"><span data-stu-id="e2b53-161">**Maximum**</span></span>  
 <span data-ttu-id="e2b53-162">Zeigt den in der Spalte, für die ein Profil erstellt wurde, gefundenen Höchstwert an.</span><span class="sxs-lookup"><span data-stu-id="e2b53-162">Displays the maximum value found in the profiled column.</span></span>  
  
 <span data-ttu-id="e2b53-163">**Mean**</span><span class="sxs-lookup"><span data-stu-id="e2b53-163">**Mean**</span></span>  
 <span data-ttu-id="e2b53-164">Zeigt den Durchschnitt der in der Spalte, für die ein Profil erstellt wurde, gefundenen Werte an.</span><span class="sxs-lookup"><span data-stu-id="e2b53-164">Displays the mean of the values found in the profiled column.</span></span>  
  
 <span data-ttu-id="e2b53-165">**Standardabweichung**</span><span class="sxs-lookup"><span data-stu-id="e2b53-165">**Standard Deviation**</span></span>  
 <span data-ttu-id="e2b53-166">Zeigt die Standardabweichung der in der Spalte, für die ein Profil erstellt wurde, gefundenen Werte an.</span><span class="sxs-lookup"><span data-stu-id="e2b53-166">Displays the standard deviation of the values found in the profiled column.</span></span>  
  
### <a name="profile-type--column-value-distribution-profile"></a><span data-ttu-id="e2b53-167">Profiltyp = Verteilungsprofil für Spaltenwert</span><span class="sxs-lookup"><span data-stu-id="e2b53-167">Profile Type = Column Value Distribution Profile</span></span>  
  
#### <a name="column-value-distribution-profile---column-pane"></a><span data-ttu-id="e2b53-168">Verteilungsprofil für Spaltenwerte – \<column>-Bereich</span><span class="sxs-lookup"><span data-stu-id="e2b53-168">Column Value Distribution Profile - \<column> pane</span></span>  
 <span data-ttu-id="e2b53-169">**Anzahl unterschiedlicher Werte**</span><span class="sxs-lookup"><span data-stu-id="e2b53-169">**Number of Distinct Values**</span></span>  
 <span data-ttu-id="e2b53-170">Zeigt die Anzahl unterschiedlicher Werte an, die in der Spalte, für die ein Profil erstellt wurde, gefunden wurden.</span><span class="sxs-lookup"><span data-stu-id="e2b53-170">Displays the count of distinct values found in the profiled column.</span></span>  
  
 <span data-ttu-id="e2b53-171">**Zeilenanzahl**</span><span class="sxs-lookup"><span data-stu-id="e2b53-171">**Row Count**</span></span>  
 <span data-ttu-id="e2b53-172">Zeigt die Anzahl der Zeilen in der Tabelle oder Sicht an.</span><span class="sxs-lookup"><span data-stu-id="e2b53-172">Displays the number of rows in the table or view.</span></span>  
  
#### <a name="detailed-value-distribution-pane"></a><span data-ttu-id="e2b53-173">Bereich 'Detaillierte Wertverteilung'</span><span class="sxs-lookup"><span data-stu-id="e2b53-173">Detailed Value Distribution pane</span></span>  
 <span data-ttu-id="e2b53-174">**Wert**</span><span class="sxs-lookup"><span data-stu-id="e2b53-174">**Value**</span></span>  
 <span data-ttu-id="e2b53-175">Zeigt die in der Spalte, für die ein Profil erstellt wurde, gefundenen unterschiedlichen Werte an.</span><span class="sxs-lookup"><span data-stu-id="e2b53-175">Displays the distinct values found in the profiled column.</span></span>  
  
 <span data-ttu-id="e2b53-176">**Count**</span><span class="sxs-lookup"><span data-stu-id="e2b53-176">**Count**</span></span>  
 <span data-ttu-id="e2b53-177">Zeigt die Anzahl von Zeilen an, in denen die Spalte, für die ein Profil erstellt wurde, den in der Spalte **Wert** angezeigten Wert aufweist.</span><span class="sxs-lookup"><span data-stu-id="e2b53-177">Displays the number of rows in which the profiled column has the value shown in the **Value** column.</span></span>  
  
 <span data-ttu-id="e2b53-178">**Percentage**</span><span class="sxs-lookup"><span data-stu-id="e2b53-178">**Percentage**</span></span>  
 <span data-ttu-id="e2b53-179">Zeigt den Prozentsatz der Zeilen an, in denen die Spalte, für die ein Profil erstellt wurde, den in der Spalte **Wert** angezeigten Wert aufweist.</span><span class="sxs-lookup"><span data-stu-id="e2b53-179">Displays the percentage of rows in which the profiled column has the value shown in the **Value** column.</span></span>  
  
### <a name="profile-type--candidate-key-profile"></a><span data-ttu-id="e2b53-180">Profiltyp = Kandidatenschlüsselprofil</span><span class="sxs-lookup"><span data-stu-id="e2b53-180">Profile Type = Candidate Key Profile</span></span>  
  
#### <a name="candidate-key-profile---table-pane"></a><span data-ttu-id="e2b53-181">Kandidatenschlüsselprofil – \<table>-Bereich</span><span class="sxs-lookup"><span data-stu-id="e2b53-181">Candidate Key Profile - \<table> pane</span></span>  
 <span data-ttu-id="e2b53-182">**Schlüsselspalten**</span><span class="sxs-lookup"><span data-stu-id="e2b53-182">**Key Columns**</span></span>  
 <span data-ttu-id="e2b53-183">Zeigt die Spalten an, die als Kandidatenschlüssel für die Profilerstellung ausgewählt wurden.</span><span class="sxs-lookup"><span data-stu-id="e2b53-183">Displays the columns that were selected for profiling as a candidate key.</span></span>  
  
 <span data-ttu-id="e2b53-184">**Schlüsselstärke**</span><span class="sxs-lookup"><span data-stu-id="e2b53-184">**Key Strength**</span></span>  
 <span data-ttu-id="e2b53-185">Zeigt die Stärke (als Prozentsatz) der Kandidatenschlüsselspalte oder Kombination von Spalten an.</span><span class="sxs-lookup"><span data-stu-id="e2b53-185">Displays the strength (as a percentage) of the candidate key column or combination of columns.</span></span> <span data-ttu-id="e2b53-186">Eine Schlüsselstärke von weniger als 100 % gibt an, dass doppelte Werte vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="e2b53-186">A key strength of less than 100% indicates that duplicate values exist.</span></span>  
  
#### <a name="key-violations-pane"></a><span data-ttu-id="e2b53-187">Bereich 'Schlüsselverletzungen'</span><span class="sxs-lookup"><span data-stu-id="e2b53-187">Key Violations pane</span></span>  
 <span data-ttu-id="e2b53-188">**\<column1>, \<column2> usw.**</span><span class="sxs-lookup"><span data-stu-id="e2b53-188">**\<column1>, \<column2>, etc.**</span></span>  
 <span data-ttu-id="e2b53-189">Zeigt die doppelten Werte an, die in der Spalte, für die ein Profil erstellt wurde, gefunden wurden.</span><span class="sxs-lookup"><span data-stu-id="e2b53-189">Displays the duplicate values that were found in the profiled column.</span></span>  
  
 <span data-ttu-id="e2b53-190">**Count**</span><span class="sxs-lookup"><span data-stu-id="e2b53-190">**Count**</span></span>  
 <span data-ttu-id="e2b53-191">Zeigt die Anzahl der Zeilen an, in denen die angegebene Spalte den in der ersten Spalte angezeigten Wert aufweist.</span><span class="sxs-lookup"><span data-stu-id="e2b53-191">Displays the number of rows in which the specified column has the value shown in the first column.</span></span>  
  
### <a name="profile-type--functional-dependency-profile"></a><span data-ttu-id="e2b53-192">Profiltyp = Funktionales Abhängigkeitsprofil</span><span class="sxs-lookup"><span data-stu-id="e2b53-192">Profile Type = Functional Dependency Profile</span></span>  
  
#### <a name="functional-dependency-profile-pane"></a><span data-ttu-id="e2b53-193">Bereich 'Funktionales Abhängigkeitsprofil'</span><span class="sxs-lookup"><span data-stu-id="e2b53-193">Functional Dependency Profile pane</span></span>  
 <span data-ttu-id="e2b53-194">**Bestimmende Spalten**</span><span class="sxs-lookup"><span data-stu-id="e2b53-194">**Determinant Columns**</span></span>  
 <span data-ttu-id="e2b53-195">Zeigt die als determinante Spalte ausgewählte(n) Spalte(n) an.</span><span class="sxs-lookup"><span data-stu-id="e2b53-195">Displays the column or columns selected as the determinant column.</span></span> <span data-ttu-id="e2b53-196">In dem Beispiel, in dem dieselbe US-Postleitzahl immer denselben Bundesstaat angeben sollte, ist die Postleitzahl die determinante Spalte.</span><span class="sxs-lookup"><span data-stu-id="e2b53-196">In the example where the same United States Zip Code should always have the same state, the Zip Code is the determinant column.</span></span>  
  
 <span data-ttu-id="e2b53-197">**Abhängige Spalten**</span><span class="sxs-lookup"><span data-stu-id="e2b53-197">**Dependent Columns**</span></span>  
 <span data-ttu-id="e2b53-198">Zeigt die als abhängige Spalte ausgewählte(n) Spalte(n) an.</span><span class="sxs-lookup"><span data-stu-id="e2b53-198">Displays the column or columns selected as the dependent column.</span></span> <span data-ttu-id="e2b53-199">In dem Beispiel, in dem dieselbe US-Postleitzahl immer denselben Bundesstaat angeben sollte, ist der Bundesstaat die abhängige Spalte.</span><span class="sxs-lookup"><span data-stu-id="e2b53-199">In the example where the same United States Zip Code should always have the same state, the state is the dependent column.</span></span>  
  
 <span data-ttu-id="e2b53-200">**Funktionale Abhängigkeitsstärke**</span><span class="sxs-lookup"><span data-stu-id="e2b53-200">**Functional Dependency Strength**</span></span>  
 <span data-ttu-id="e2b53-201">Zeigt die Stärke (als Prozentsatz) der funktionalen Abhängigkeit zwischen Spalten an.</span><span class="sxs-lookup"><span data-stu-id="e2b53-201">Displays the strength (as a percentage) of the functional dependency between columns.</span></span> <span data-ttu-id="e2b53-202">Eine Schlüsselstärke von weniger als 100 % gibt an, dass es Fälle gibt, in denen der determinante Wert den abhängigen Wert nicht bestimmt.</span><span class="sxs-lookup"><span data-stu-id="e2b53-202">A key strength of less than 100% indicates that there are cases where the determinant value does not determine the dependent value.</span></span> <span data-ttu-id="e2b53-203">In dem Beispiel, in dem dieselbe US-Postleitzahl immer denselben Bundesstaat angeben sollte, deutet dies wahrscheinlich darauf hin, dass einige Bundesstaatenwerte ungültig sind.</span><span class="sxs-lookup"><span data-stu-id="e2b53-203">In the example where the same United States Zip Code should always have the same state, this probably indicates some state values are not valid.</span></span>  
  
#### <a name="functional-dependency-violations-pane"></a><span data-ttu-id="e2b53-204">Bereich 'Funktionale Abhängigkeitsverletzungen'</span><span class="sxs-lookup"><span data-stu-id="e2b53-204">Functional Dependency Violations pane</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e2b53-205">Ein hoher Prozentsatz an fehlerhaften Werten in den Daten könnte zu unerwarteten Werten aus einem funktionalen Abhängigkeitsprofil führen.</span><span class="sxs-lookup"><span data-stu-id="e2b53-205">A high percentage of erroneous values in the data could lead to unexpected results from a Functional Dependency profile.</span></span> <span data-ttu-id="e2b53-206">Beispiel: 90 % der Zeilen haben den Bundesstaatenwert "WI" für den PLZ-Wert "98052".</span><span class="sxs-lookup"><span data-stu-id="e2b53-206">For example, 90% of the rows have a State value of "WI" for a Postal Code value of "98052."</span></span> <span data-ttu-id="e2b53-207">Das Profil meldet Zeilen, die den korrekten Bundesstaatenwert "WA" aufweisen, als Verletzungen.</span><span class="sxs-lookup"><span data-stu-id="e2b53-207">The profile reports rows that contain the correct state value of "WA" as violations.</span></span>  
  
 **\<determinant column name>**  
 <span data-ttu-id="e2b53-208">Zeigt den Wert der determinanten Spalte oder einer Kombination aus Spalten in dieser Instanz einer funktionalen Abhängigkeitsverletzung an.</span><span class="sxs-lookup"><span data-stu-id="e2b53-208">Displays the value of the determinant column or combination of columns in this instance of a functional dependency violation.</span></span>  
  
 **\<dependent column name>**  
 <span data-ttu-id="e2b53-209">Zeigt den Wert der abhängigen Spalte in dieser Instanz einer funktionalen Abhängigkeitsverletzung an.</span><span class="sxs-lookup"><span data-stu-id="e2b53-209">Displays the value of the dependent column in this instance of a functional dependency violation.</span></span>  
  
 <span data-ttu-id="e2b53-210">**Unterstützte Anzahl**</span><span class="sxs-lookup"><span data-stu-id="e2b53-210">**Support Count**</span></span>  
 <span data-ttu-id="e2b53-211">Zeigt die Anzahl der Zeilen an, in denen der Wert der determinanten Spalte die abhängige Spalte festlegt.</span><span class="sxs-lookup"><span data-stu-id="e2b53-211">Displays the number of rows in which the determinant column value determines the dependent column.</span></span>  
  
 <span data-ttu-id="e2b53-212">**Verletzungsanzahl**</span><span class="sxs-lookup"><span data-stu-id="e2b53-212">**Violation Count**</span></span>  
 <span data-ttu-id="e2b53-213">Zeigt die Anzahl der Zeilen an, in denen der Wert der determinanten Spalte die abhängige Spalte nicht festlegt.</span><span class="sxs-lookup"><span data-stu-id="e2b53-213">Displays the number of rows in which the determinant column value does not determine the dependent column.</span></span> <span data-ttu-id="e2b53-214">(In diesen Zeilen ist der abhängige Wert der Wert, der in der Spalte **\<dependent column name>** angezeigt wird.)</span><span class="sxs-lookup"><span data-stu-id="e2b53-214">(These are the rows where the dependent value is the value shown in the **\<dependent column name>** column.)</span></span>  
  
 <span data-ttu-id="e2b53-215">**Unterstützter Prozentsatz**</span><span class="sxs-lookup"><span data-stu-id="e2b53-215">**Support Percentage**</span></span>  
 <span data-ttu-id="e2b53-216">Zeigt den Prozentsatz der Zeilen an, in denen die determinante Spalte die abhängige Spalte festlegt.</span><span class="sxs-lookup"><span data-stu-id="e2b53-216">Displays the percentage of rows in which the determinant column determines the dependent column.</span></span>  
  
### <a name="profile-type--value-inclusion-profile"></a><span data-ttu-id="e2b53-217">Profiltyp = Wertinklusionsprofil</span><span class="sxs-lookup"><span data-stu-id="e2b53-217">Profile Type = Value Inclusion Profile</span></span>  
  
#### <a name="value-inclusion-profile-pane"></a><span data-ttu-id="e2b53-218">Bereich 'Wertinklusionsprofil'</span><span class="sxs-lookup"><span data-stu-id="e2b53-218">Value Inclusion Profile pane</span></span>  
 <span data-ttu-id="e2b53-219">**Untergeordnete Spalten**</span><span class="sxs-lookup"><span data-stu-id="e2b53-219">**Subset Side Columns**</span></span>  
 <span data-ttu-id="e2b53-220">Zeigt die Spalte oder Kombination aus Spalten an, für die ein Profil erstellt wurde, um zu ermitteln, ob sie sich in den übergeordneten Spalten befinden.</span><span class="sxs-lookup"><span data-stu-id="e2b53-220">Displays the column or combination of columns that were profiled to determine whether they are in the superset columns.</span></span>  
  
 <span data-ttu-id="e2b53-221">**Übergeordnete Spalten**</span><span class="sxs-lookup"><span data-stu-id="e2b53-221">**Superset Side Columns**</span></span>  
 <span data-ttu-id="e2b53-222">Zeigt die Spalte oder Kombination aus Spalten an, für die ein Profil erstellt wurde, um zu ermitteln, ob sie die Werte aus den untergeordneten Spalten enthalten.</span><span class="sxs-lookup"><span data-stu-id="e2b53-222">Displays the column or combination of columns that were profiled to determine whether they include the values in the subset columns.</span></span>  
  
 <span data-ttu-id="e2b53-223">**Inklusionsstärke**</span><span class="sxs-lookup"><span data-stu-id="e2b53-223">**Inclusion Strength**</span></span>  
 <span data-ttu-id="e2b53-224">Zeigt die Stärke (als Prozentsatz) der Überlappung zwischen Spalten an.</span><span class="sxs-lookup"><span data-stu-id="e2b53-224">Displays the strength (as a percentage) of the overlap between columns.</span></span> <span data-ttu-id="e2b53-225">Eine Schlüsselstärke von weniger als 100 % gibt an, dass es Fälle gibt, in denen der untergeordnete Wert nicht in den übergeordneten Werten enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="e2b53-225">A key strength of less than 100% indicates that there are cases where the subset value is not found among the superset values.</span></span>  
  
#### <a name="inclusion-violations-pane"></a><span data-ttu-id="e2b53-226">Bereich 'Inklusionsverletzungen'</span><span class="sxs-lookup"><span data-stu-id="e2b53-226">Inclusion Violations pane</span></span>  
 <span data-ttu-id="e2b53-227">**\<column1>, \<column2> usw.**</span><span class="sxs-lookup"><span data-stu-id="e2b53-227">**\<column1>, \<column2>, etc.**</span></span>  
 <span data-ttu-id="e2b53-228">Zeigt die Werte aus der bzw. den untergeordneten Spalte(n) an, die nicht in der bzw. den übergeordneten Spalte(n) gefunden wurden.</span><span class="sxs-lookup"><span data-stu-id="e2b53-228">Displays the values in the subset column or columns that were not found in the superset column or columns.</span></span>  
  
 <span data-ttu-id="e2b53-229">**Count**</span><span class="sxs-lookup"><span data-stu-id="e2b53-229">**Count**</span></span>  
 <span data-ttu-id="e2b53-230">Zeigt die Anzahl der Zeilen an, in denen die angegebene Spalte den in der ersten Spalte angezeigten Wert aufweist.</span><span class="sxs-lookup"><span data-stu-id="e2b53-230">Displays the number of rows in which the specified column has the value shown in the first column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2b53-231">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e2b53-231">See Also</span></span>  
 <span data-ttu-id="e2b53-232">[Datenprofil-Viewer](control-flow/data-profile-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="e2b53-232">[Data Profile Viewer](control-flow/data-profile-viewer.md) </span></span>  
 [<span data-ttu-id="e2b53-233">Datenprofilerstellungs-Task und -Viewer</span><span class="sxs-lookup"><span data-stu-id="e2b53-233">Data Profiling Task and Viewer</span></span>](control-flow/data-profiling-task-and-viewer.md)  
  
  
