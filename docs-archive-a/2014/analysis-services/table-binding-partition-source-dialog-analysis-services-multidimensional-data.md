---
title: Tabellen Bindungs Details (Dialog Feld ' Partitions Quelle ') (Analysis Services-Mehrdimensionale Daten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.partitions.partitiontableselection.f1
ms.assetid: 67d05389-81ae-4a6b-947b-986d37ec72b1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 10845e18a2b7c74a8ed3aeec42f710b9706dc94a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616718"
---
# <a name="table-binding-detail-partition-source-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="5ad6c-102">Tabellenbindungsdetail (Dialogfeld 'Partitionsquelle') (Analysis Services – Mehrdimensionale Daten)</span><span class="sxs-lookup"><span data-stu-id="5ad6c-102">Table Binding Detail (Partition Source Dialog Box) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="5ad6c-103">Mithilfe der Option **Tabellenbindung** im Dialogfeld **Partitionsquelle** können Sie die Faktentabelle angeben, die die Daten für die Partition bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="5ad6c-103">Use the **Table Binding** option in the **Partition Source** dialog box to specify the fact table that provides the data for the partition.</span></span> <span data-ttu-id="5ad6c-104">Sie können diesen Bereich anzeigen, indem Sie im Dialogfeld **Partitionsquelle** unter **Bindungstyp** die Option **Tabellenbindung** auswählen.</span><span class="sxs-lookup"><span data-stu-id="5ad6c-104">You can display this pane by selecting **Table Binding** from the **Binding type** option in the **Partition Source** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5ad6c-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="5ad6c-105">Options</span></span>  
 <span data-ttu-id="5ad6c-106">**Measuregruppe**</span><span class="sxs-lookup"><span data-stu-id="5ad6c-106">**Measure group**</span></span>  
 <span data-ttu-id="5ad6c-107">Zeigt die Measuregruppe für diese Partition an.</span><span class="sxs-lookup"><span data-stu-id="5ad6c-107">Displays the measure group for this partition.</span></span>  
  
 <span data-ttu-id="5ad6c-108">**Suchen in**</span><span class="sxs-lookup"><span data-stu-id="5ad6c-108">**Look in**</span></span>  
 <span data-ttu-id="5ad6c-109">Wählen Sie die Datenquelle oder Datenquellensicht mit den Quelltabellen für die Partition aus.</span><span class="sxs-lookup"><span data-stu-id="5ad6c-109">Select the data source or data source view that contains the source tables for this partition.</span></span> <span data-ttu-id="5ad6c-110">Die durch die ausgewählte Measuregruppe verwendete Datenquellensicht wird standardmäßig ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="5ad6c-110">The data source view used by the selected measure group is selected by default.</span></span>  
  
 <span data-ttu-id="5ad6c-111">**Tabellenfilter**</span><span class="sxs-lookup"><span data-stu-id="5ad6c-111">**Filter tables**</span></span>  
 <span data-ttu-id="5ad6c-112">Geben Sie die Zeichenfolge ein, die verwendet werden soll, um die unter **Verfügbare Tabellen**angezeigten Tabellen auf der Grundlage des Tabellennamens einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="5ad6c-112">Type the string used to restrict, by table name, the tables displayed in **Available tables**.</span></span>  
  
 <span data-ttu-id="5ad6c-113">**Suchen nach Tabellen**</span><span class="sxs-lookup"><span data-stu-id="5ad6c-113">**Find tables**</span></span>  
 <span data-ttu-id="5ad6c-114">Wählen Sie diese Option aus, um die Liste der Tabellen unter **Verfügbare Tabellen**zu aktualisieren und die Liste weiter einzuschränken, falls in **Tabellenfilter**eine Zeichenfolge eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="5ad6c-114">Select to refresh the list of tables in **Available tables**, further restricting the list if a string was specified in **Filter tables**.</span></span>  
  
 <span data-ttu-id="5ad6c-115">**Verfügbare Tabellen**</span><span class="sxs-lookup"><span data-stu-id="5ad6c-115">**Available tables**</span></span>  
 <span data-ttu-id="5ad6c-116">Klicken Sie auf die Option, um die Tabelle auszuwählen, die als Quelltabelle für die Partition verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5ad6c-116">Click to select the table to use as a source table for the partition.</span></span>  
  
 <span data-ttu-id="5ad6c-117">Wenn in **Tabellenfilter**kein Filter angegeben wird, werden alle Tabellen aufgelistet, die in der unter **Suchen in** angegebenen Datenquelle oder Datenquellensicht enthalten sind, und deren Struktur der Faktentabelle gleicht, die von der unter **Measuregruppe** angegebenen Measuregruppe verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5ad6c-117">If no filter is specified in **Filter tables**, all tables in the data source or data source view specified in **Look in** that are similar in structure to the fact table used by the measure group specified in **Measure group** are listed.</span></span>  
  
 <span data-ttu-id="5ad6c-118">Wenn in **Tabellenfilter**ein Filter angegeben wird, wird die Liste weiter eingeschränkt, indem der Filter mit den Tabellennamen verglichen wird, die die oben genannten Kriterien erfüllen.</span><span class="sxs-lookup"><span data-stu-id="5ad6c-118">If a filter is specified in **Filter tables**, the list is further restricted by comparing the filter against the table names that meet the above criteria.</span></span> <span data-ttu-id="5ad6c-119">Nur die Tabellen, die die in **Tabellenfilter** angegebene Zeichenfolge enthalten, werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5ad6c-119">Only those tables that contain the string specified in **Filter tables** are displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ad6c-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5ad6c-120">See Also</span></span>  
 [<span data-ttu-id="5ad6c-121">Dialog Feld ' Partitions Quelle ' &#40;Analysis Services Mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="5ad6c-121">Partition Source Dialog Box &#40;Analysis Services - Multidimensional Data&#41;</span></span>](partition-source-dialog-box-analysis-services-multidimensional-data.md)  
  
  
