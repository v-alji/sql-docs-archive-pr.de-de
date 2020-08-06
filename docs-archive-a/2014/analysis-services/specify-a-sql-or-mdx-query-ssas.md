---
title: SQL-oder MDX-Abfrage angeben (SSAS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.specsqlmdxquery.f1
ms.assetid: e4128221-3b46-48be-b0f1-d82477ce6782
author: minewiskan
ms.author: owend
ms.openlocfilehash: bce5e92aaed7a62311e989d6963e4fa5764028ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721797"
---
# <a name="specify-a-sql-or-mdx-query-ssas"></a><span data-ttu-id="49a1e-102">SQL-Abfrage oder MDX-Abfrage angeben (SSAS)</span><span class="sxs-lookup"><span data-stu-id="49a1e-102">Specify a SQL or MDX Query (SSAS)</span></span>
  <span data-ttu-id="49a1e-103">Auf dieser Seite des **Tabellenimport-Assistenten** können Sie Daten mit einer SQL- oder MDX-Abfrage importieren.</span><span class="sxs-lookup"><span data-stu-id="49a1e-103">This page of the **Table Import Wizard** enables you to import data by using a SQL or MDX query.</span></span> <span data-ttu-id="49a1e-104">Um im [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]auf den Assistenten zuzugreifen, klicken Sie im Menü **Modell** auf **Aus Datenquelle importieren**.</span><span class="sxs-lookup"><span data-stu-id="49a1e-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="49a1e-105">Mit der Abfrage können die importierten Daten bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="49a1e-105">The query can manipulate the data that is imported.</span></span> <span data-ttu-id="49a1e-106">Sie können z. B. Daten aus unterschiedlichen Tabellen verknüpfen oder nur Zeilen auswählen, die bestimmte Kriterien erfüllen.</span><span class="sxs-lookup"><span data-stu-id="49a1e-106">For example, you could join data from different tables or select only rows that meet certain criteria.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="49a1e-107">Liste der Benutzeroberflächenelemente</span><span class="sxs-lookup"><span data-stu-id="49a1e-107">UI element list</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="49a1e-108">Begriff</span><span class="sxs-lookup"><span data-stu-id="49a1e-108">Term</span></span>|<span data-ttu-id="49a1e-109">Definition</span><span class="sxs-lookup"><span data-stu-id="49a1e-109">Definition</span></span>|  
|<span data-ttu-id="49a1e-110">**Anzeigename der Abfrage**</span><span class="sxs-lookup"><span data-stu-id="49a1e-110">**Friendly Query Name**</span></span>|<span data-ttu-id="49a1e-111">Geben Sie einen eindeutigen Namen für die Abfrage ein.</span><span class="sxs-lookup"><span data-stu-id="49a1e-111">Type a unique name for the query.</span></span> <span data-ttu-id="49a1e-112">Dies ist ein Pflichtfeld.</span><span class="sxs-lookup"><span data-stu-id="49a1e-112">This is a required field.</span></span>|  
|<span data-ttu-id="49a1e-113">**SQL-Anweisung**</span><span class="sxs-lookup"><span data-stu-id="49a1e-113">**SQL Statement**</span></span>|<span data-ttu-id="49a1e-114">Geben oder fügen Sie eine SQL-Anweisung ein.</span><span class="sxs-lookup"><span data-stu-id="49a1e-114">Type or paste a SQL statement.</span></span>|  
|<span data-ttu-id="49a1e-115">**Überprüfen**</span><span class="sxs-lookup"><span data-stu-id="49a1e-115">**Validate**</span></span>|<span data-ttu-id="49a1e-116">Prüfen Sie, ob die SQL-Anweisung gültig ist.</span><span class="sxs-lookup"><span data-stu-id="49a1e-116">Determine if the SQL statement is valid.</span></span>|  
|<span data-ttu-id="49a1e-117">**Design**</span><span class="sxs-lookup"><span data-stu-id="49a1e-117">**Design**</span></span>|<span data-ttu-id="49a1e-118">Entwerfen Sie mit dem Abfrage-Designer-Dialogfeld eine SQL-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="49a1e-118">Design a SQL statement by using the query designer dialog box.</span></span> <span data-ttu-id="49a1e-119">Weitere Informationen finden Sie unter [Relationaler Abfrage-Designer &#40;SSAS&#41;](relational-query-designer-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="49a1e-119">For more information, see [Relational Query Designer &#40;SSAS&#41;](relational-query-designer-ssas.md).</span></span>|  
  
  
