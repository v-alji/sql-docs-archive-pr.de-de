---
title: Namens Übereinstimmung (Datenquellen Sicht-Assistent) (Analysis Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.datasourceviewwizard.namematchingcriteria.f1
ms.assetid: 7f811e02-0fe6-45c9-a7b7-29c61032d96b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 50cc46db7f582e0aea1570dadc956336ef8be074
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618343"
---
# <a name="name-matching-data-source-view-wizard-analysis-services"></a><span data-ttu-id="a9a60-102">Namensübereinstimmung (Datenquellensicht-Assistent) (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="a9a60-102">Name Matching (Data Source View Wizard) (Analysis Services)</span></span>
  <span data-ttu-id="a9a60-103">Mithilfe der Seite **Namensübereinstimmung** können Sie das Kriterium auswählen, das zum Ermitteln möglicher Beziehungen zwischen den für die Datenquellensicht ausgewählten Tabellen und den anderen Tabellen im Schema verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a9a60-103">Use the **Name Matching** page to select the criterion to use for detecting possible relationships between the tables that you select for the data source view and the other tables in the schema.</span></span> <span data-ttu-id="a9a60-104">Wenn keine physischen Fremdschlüsselbeziehungen zwischen den Tabellen vorhanden sind, hilft dieses Kriterium dabei, verwandte Tabellen zu kennzeichnen und der Datenquellensicht hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="a9a60-104">If no physical foreign key relationships exist between the tables, this criterion helps you identify and add related tables to the data source view.</span></span> <span data-ttu-id="a9a60-105">Die logischen Beziehungen, die durch die Namensübereinstimmung identifiziert sind, werden ebenfalls der Datenquellensicht hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a9a60-105">The logical relationships that are identified by name matching are also added to the data source view.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a9a60-106">Diese Seite wird nur angezeigt, wenn Sie eine Datenquelle auswählen, die mehrere Tabellen enthält, in der aber keine Fremdschlüsselbeziehungen zwischen den Tabellen bestehen.</span><span class="sxs-lookup"><span data-stu-id="a9a60-106">This page appears only if you select a data source that has multiple tables but no foreign key relationships between any one of the tables.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a9a60-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="a9a60-107">Options</span></span>  
 <span data-ttu-id="a9a60-108">**Logische Beziehungen nach übereinstimmenden Spalten erstellen**</span><span class="sxs-lookup"><span data-stu-id="a9a60-108">**Create logical relationships by matching columns**</span></span>  
 <span data-ttu-id="a9a60-109">Legt fest, dass ein Namensübereinstimmungskriterium verwendet wird, um mögliche logische Abhängigkeiten und Beziehungen zwischen den Tabellen, die für die Datenquellensicht ausgewählt wurden, und den anderen Tabellen im Schema zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="a9a60-109">Select to use a name-matching criterion to detect possible logical dependencies and relationships between the tables that you select to include in the data source view and the other tables in the schema.</span></span> <span data-ttu-id="a9a60-110">Wenn Sie dieses Kontrollkästchen deaktivieren, wird kein Kriterium für die Namensübereinstimmung verwendet, um logische Beziehungen zwischen den Tabellen in der Datenquelle zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="a9a60-110">If you clear this check box, no name-matching criterion is used to identify logical relationships between tables in the data source.</span></span>  
  
 <span data-ttu-id="a9a60-111">**Fremdschlüsselübereinstimmungen**</span><span class="sxs-lookup"><span data-stu-id="a9a60-111">**Foreign key matches**</span></span>  
 <span data-ttu-id="a9a60-112">Wählen Sie das Kriterium aus, dass für das Erstellen logischer Beziehungen zwischen Tabellen und Sichten in der Datenquelle verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a9a60-112">Select the criterion to use for creating logical relationships between tables and views in the data source.</span></span> <span data-ttu-id="a9a60-113">Nicht alphanumerische Zeichen werden in übereinstimmenden Zeichenfolgen ignoriert.</span><span class="sxs-lookup"><span data-stu-id="a9a60-113">Non-alphanumeric characters are ignored in matching strings.</span></span> <span data-ttu-id="a9a60-114">Die Zeichenfolgen "Customer ID", "Customer_ID" und "CustomerID" stimmen z. B. überein.</span><span class="sxs-lookup"><span data-stu-id="a9a60-114">For example, "Customer ID", "Customer_ID", "CustomerID" all match.</span></span> <span data-ttu-id="a9a60-115">Wählen Sie eine der Optionen in der folgenden Tabelle aus, um Beziehungen unter den angegebenen Bedingungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a9a60-115">Select one of the options in the following table to create relationships under the specified conditions.</span></span>  
  
|<span data-ttu-id="a9a60-116">Select</span><span class="sxs-lookup"><span data-stu-id="a9a60-116">Select</span></span>|<span data-ttu-id="a9a60-117">Erstellte Beziehung</span><span class="sxs-lookup"><span data-stu-id="a9a60-117">To create</span></span>|  
|------------|---------------|  
|<span data-ttu-id="a9a60-118">**Gleicher Name wie Primärschlüssel**</span><span class="sxs-lookup"><span data-stu-id="a9a60-118">**Same name as primary key**</span></span>|<span data-ttu-id="a9a60-119">Eine logische Beziehung zu jeder Tabelle mit einem Spaltennamen, der mit dem Namen der Primärschlüsselspalte in einer ausgewählten Tabelle übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="a9a60-119">A logical relationship to any table with a column name that matches the name of the primary key column in a selected table.</span></span>|  
|<span data-ttu-id="a9a60-120">**Gleicher Name wie Zieltabelle**</span><span class="sxs-lookup"><span data-stu-id="a9a60-120">**Same name as destination table name**</span></span>|<span data-ttu-id="a9a60-121">Eine logische Beziehung zu jeder Tabelle mit einem Spaltennamen, der mit dem Namen der ausgewählten Tabelle übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="a9a60-121">A logical relationship to any table with a column name that matches the name of a selected table.</span></span>|  
|<span data-ttu-id="a9a60-122">**Zieltabellenname und Primärschlüsselname**</span><span class="sxs-lookup"><span data-stu-id="a9a60-122">**Destination table name + primary key name**</span></span>|<span data-ttu-id="a9a60-123">Eine logische Beziehung zu einer beliebigen Tabelle, in der ein Spaltenname mit dem ausgewählten Tabellennamen übereinstimmt, der wiederum mit dem Namen der Primärschlüsselspalte für die ausgewählte Tabelle verkettet ist.</span><span class="sxs-lookup"><span data-stu-id="a9a60-123">A logical relationship to any table in which a column name matches the selected table name concatenated with the name of the primary key column for the selected table, in that order.</span></span> <span data-ttu-id="a9a60-124">Nicht alphanumerische Zeichen innerhalb der Verkettung werden ignoriert ("Product ID", "Product_ID" und "ProductID" stimmen z. B. überein).</span><span class="sxs-lookup"><span data-stu-id="a9a60-124">Non-alphanumeric characters within the concatenation are ignored (for example, "Product ID", "Product_ID" and "ProductID" all match).</span></span>|  
  
 <span data-ttu-id="a9a60-125">**Beschreibung und Beispiel**</span><span class="sxs-lookup"><span data-stu-id="a9a60-125">**Description and sample**</span></span>  
 <span data-ttu-id="a9a60-126">Zeigt eine Beschreibung und ein Beispiel des ausgewählten Kriteriums an.</span><span class="sxs-lookup"><span data-stu-id="a9a60-126">View a description and a sample of the selected criterion.</span></span>  
  
  
