---
title: Quell Informationen angeben (Partitions-Assistent) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.partitionwizard.specifydsvandfacttables.f1
ms.assetid: b6c13587-c690-45d9-af90-b3d652afc55b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 088a8abf7b143b68766f22af37f8ff4fa2065d65
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620547"
---
# <a name="specify-source-information-partition-wizard"></a><span data-ttu-id="587e6-102">Quellinformationen angeben (Partitions-Assistent)</span><span class="sxs-lookup"><span data-stu-id="587e6-102">Specify Source Information (Partition Wizard)</span></span>
  <span data-ttu-id="587e6-103">Auf der Seite **Quellinformationen angeben** können Sie die Measuregruppe, in der die Partition erstellt werden soll, und die Datenquellensicht und die Filtertabellen für die Partition auswählen.</span><span class="sxs-lookup"><span data-stu-id="587e6-103">Use the **Specify Source Information** page to select the measure group in which to create the partition, and also the data source view and filter tables for your partition.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="587e6-104"> Wenn Sie unter **Verfügbare Tabellen** eine Tabelle angeben, die auch von einer anderen Partition verwendet wird, müssen Sie auf der Seite **Zeilen einschränken** eine Abfrage bereitstellen, da andernfalls die Gefahr besteht, dass die Daten im Cube dupliziert werden.</span><span class="sxs-lookup"><span data-stu-id="587e6-104">If you specify a table in **Available Tables** that is used by another partition, you must provide a query in the **Restrict Rows** page or risk duplicating data in the cube.</span></span>  
  
## <a name="options"></a><span data-ttu-id="587e6-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="587e6-105">Options</span></span>  
 <span data-ttu-id="587e6-106">**Measuregruppe**</span><span class="sxs-lookup"><span data-stu-id="587e6-106">**Measure group**</span></span>  
 <span data-ttu-id="587e6-107">Wählen Sie für die Partition eine Measuregruppe aus.</span><span class="sxs-lookup"><span data-stu-id="587e6-107">Select a measure group for this partition.</span></span>  
  
 <span data-ttu-id="587e6-108">**Suchen in**</span><span class="sxs-lookup"><span data-stu-id="587e6-108">**Look in**</span></span>  
 <span data-ttu-id="587e6-109">Wählen Sie die Datenquelle oder Datenquellensicht mit den Quelltabellen für die Partition aus.</span><span class="sxs-lookup"><span data-stu-id="587e6-109">Select the data source or data source view that contains the source tables for this partition.</span></span> <span data-ttu-id="587e6-110">Die durch die Measuregruppe verwendete Datenquellensicht wird standardmäßig ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="587e6-110">The data source view used by the measure group is selected by default.</span></span>  
  
 <span data-ttu-id="587e6-111">**Tabellenfilter**</span><span class="sxs-lookup"><span data-stu-id="587e6-111">**Filter tables**</span></span>  
 <span data-ttu-id="587e6-112">Geben Sie die Zeichenfolge ein, die verwendet werden soll, um die unter **Verfügbare Tabellen**angezeigten Tabellen auf der Grundlage des Tabellennamens einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="587e6-112">Type the string used to restrict, by table name, the tables displayed in **Available tables**.</span></span>  
  
 <span data-ttu-id="587e6-113">**Suchen nach Tabellen**</span><span class="sxs-lookup"><span data-stu-id="587e6-113">**Find tables**</span></span>  
 <span data-ttu-id="587e6-114">Wählen Sie diese Option aus, um die Liste der Tabellen unter **Verfügbare Tabellen**zu aktualisieren und die Liste weiter einzuschränken, falls in **Tabellenfilter**eine Zeichenfolge eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="587e6-114">Select to refresh the list of tables in **Available tables**, further restricting the list if a string was specified in **Filter tables**.</span></span>  
  
 <span data-ttu-id="587e6-115">**Verfügbare Tabellen**</span><span class="sxs-lookup"><span data-stu-id="587e6-115">**Available tables**</span></span>  
 <span data-ttu-id="587e6-116">Wählen Sie die Tabellen aus, die als Quelltabellen für Partitionen verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="587e6-116">Select the tables to use as source tables for partitions.</span></span> <span data-ttu-id="587e6-117">Durch **Partitions-Assistent** wird für jede der in **Verfügbare Tabellen**ausgewählten Tabellen eine Partition erstellt.</span><span class="sxs-lookup"><span data-stu-id="587e6-117">The **Partition Wizard** creates one partition for each table selected in **Available tables**.</span></span>  
  
 <span data-ttu-id="587e6-118">Wenn in **Tabellenfilter**kein Filter angegeben wird, werden mit dieser Option alle Tabellen aufgelistet, die in der in **Suchen in** angegebenen Datenquelle oder Datenquellensicht enthalten sind, und deren Struktur der Faktentabelle gleicht, die von der in **Measuregruppe**angegebenen Measuregruppe verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="587e6-118">If no filter is specified in **Filter tables**, this option lists all tables in the data source or data source view that are specified in **Look in** and that are similar in structure to the fact table used by the measure group specified in **Measure group**.</span></span>  
  
 <span data-ttu-id="587e6-119">Wenn in **Tabellenfilter**ein Filter angegeben wird, wird die Liste weiter eingeschränkt, da der Filter mit den Tabellennamen verglichen wird, die die zuvor angegebenen Kriterien bereits erfüllen.</span><span class="sxs-lookup"><span data-stu-id="587e6-119">If a filter is specified in **Filter tables**, the list is further restricted by comparing the filter against the table names that meet the previous criteria.</span></span> <span data-ttu-id="587e6-120">Nur die Tabellen, die die in **Tabellenfilter** angegebene Zeichenfolge enthalten, werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="587e6-120">Only those tables that contain the string specified in **Filter tables** are displayed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="587e6-121">Wenn mehrere Tabellen ausgewählt werden, kann die Seite **Zeilen einschränken** nicht angezeigt werden, und die Zeilen können nicht für die von den ausgewählten Tabellen erstellten Partitionen eingeschränkt werden.</span><span class="sxs-lookup"><span data-stu-id="587e6-121">If more than one table is selected, the **Restrict Rows** page cannot be displayed and rows cannot be restricted for the partitions created from the selected tables.</span></span> <span data-ttu-id="587e6-122">Um die Zeilen für die einzelnen Partitionen einzuschränken, führen Sie den Partitions-Assistenten einmal für jede Tabelle aus, von der eine Partition erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="587e6-122">To restrict rows for each partition, run the Partition Wizard once for each table from which a partition is to be created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="587e6-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="587e6-123">See Also</span></span>  
 [<span data-ttu-id="587e6-124">Partitionen &#40;Analysis Services – mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="587e6-124">Partitions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md)  
  
  
