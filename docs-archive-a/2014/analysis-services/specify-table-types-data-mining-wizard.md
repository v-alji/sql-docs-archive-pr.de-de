---
title: Tabellentypen angeben (Data Mining-Assistent) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.dmwizard.specifytabletypes.f1
ms.assetid: 8209a707-faef-4ffc-8991-6c13bb350753
author: minewiskan
ms.author: owend
ms.openlocfilehash: 88c09f26958c37ed0a99efb54a5eb5c08505d16b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620545"
---
# <a name="specify-table-types-data-mining-wizard"></a><span data-ttu-id="c4bfc-102">Tabellentypen angeben (Data Mining-Assistent)</span><span class="sxs-lookup"><span data-stu-id="c4bfc-102">Specify Table Types (Data Mining Wizard)</span></span>
  <span data-ttu-id="c4bfc-103">Verwenden Sie die Seite **Tabellentypen angeben** , um die zum Definieren der Miningstruktur zu verwendenden Tabellen zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="c4bfc-103">Use the **Specify Table Types** page to identify the tables to use to define the mining structure.</span></span> <span data-ttu-id="c4bfc-104">Wenn eine Tabelle nicht ausgewählt ist, wird sie auch nicht zum Definieren der Miningstruktur verwendet.</span><span class="sxs-lookup"><span data-stu-id="c4bfc-104">If a table is not selected, it will not be used to define the mining structure.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c4bfc-105">Zu einem späteren Zeitpunkt können Sie Tabellen über die Registerkarte **Miningstruktur** im **Data Mining-Designer** hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c4bfc-105">You can add tables later from the **Mining Structure** tab in **Data Mining Designer**.</span></span>  
  
 <span data-ttu-id="c4bfc-106">**Weitere Informationen:** [Geschachtelte Tabellen &#40;Analysis Services – Data Mining&#41;](data-mining/nested-tables-analysis-services-data-mining.md), [Data Mining-Assistent &#40;Analysis Services – Data Mining&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Erstellen einer relationalen Miningstruktur](data-mining/create-a-relational-mining-structure.md)</span><span class="sxs-lookup"><span data-stu-id="c4bfc-106">**For More Information:** [Nested Tables &#40;Analysis Services - Data Mining&#41;](data-mining/nested-tables-analysis-services-data-mining.md), [Data Mining Wizard &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Create a Relational Mining Structure](data-mining/create-a-relational-mining-structure.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="c4bfc-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="c4bfc-107">Options</span></span>  
 <span data-ttu-id="c4bfc-108">**Tabellen**</span><span class="sxs-lookup"><span data-stu-id="c4bfc-108">**Tables**</span></span>  
 <span data-ttu-id="c4bfc-109">Zeigt die Tabellen in der Datenquellensicht an, die Sie auf der Seite **Datenquellensicht auswählen** des Assistenten ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="c4bfc-109">Displays the tables in the data source view that you selected on the **Select Data Source View** page of the wizard.</span></span>  
  
 <span data-ttu-id="c4bfc-110">**Sollten**</span><span class="sxs-lookup"><span data-stu-id="c4bfc-110">**Case**</span></span>  
 <span data-ttu-id="c4bfc-111">Wählen Sie eine Tabelle aus, die als Falltabelle verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c4bfc-111">Select one table to use as the case table.</span></span>  
  
 <span data-ttu-id="c4bfc-112">**Geschachtelte**</span><span class="sxs-lookup"><span data-stu-id="c4bfc-112">**Nested**</span></span>  
 <span data-ttu-id="c4bfc-113">Wählen Sie die Tabellen aus, die als geschachtelte Tabellen verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c4bfc-113">Select the tables to use as nested tables.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c4bfc-114">Diese Tabellen müssen eine m:1-Beziehung mit der Falltabelle aufweisen, nicht eine 1:n-Beziehung.</span><span class="sxs-lookup"><span data-stu-id="c4bfc-114">These tables must have a many-to-one relationship with the case table, not a one-to-many relationship.</span></span> <span data-ttu-id="c4bfc-115">Sie müssen diese Beziehung in der Datenquellensicht angeben, bevor Sie eine geschachtelte Tabelle auswählen können.</span><span class="sxs-lookup"><span data-stu-id="c4bfc-115">You must specify this relationship in the data source view before you can select the table as nested.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4bfc-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c4bfc-116">See Also</span></span>  
 <span data-ttu-id="c4bfc-117">[Data Mining-Assistent (F1-Hilfe &#40;Analysis Services-Data Mining-&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="c4bfc-117">[Data Mining Wizard F1 Help &#40;Analysis Services - Data Mining&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="c4bfc-118">[Wählen Sie die Datenquellen Sicht &#40;Data Mining-Assistenten aus&#41;](select-data-source-view-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="c4bfc-118">[Select Data Source View &#40;Data Mining Wizard&#41;](select-data-source-view-data-mining-wizard.md) </span></span>  
 [<span data-ttu-id="c4bfc-119">Geben Sie den Data Mining-Assistenten für Trainingsdaten &#40;an&#41;</span><span class="sxs-lookup"><span data-stu-id="c4bfc-119">Specify the Training Data &#40;Data Mining Wizard&#41;</span></span>](specify-the-training-data-data-mining-wizard.md)  
  
  
