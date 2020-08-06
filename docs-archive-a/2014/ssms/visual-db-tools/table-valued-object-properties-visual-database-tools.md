---
title: Tabellenwertobjekt-Eigenschaften (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.designers.properties.TVO
ms.assetid: eaf06cbf-8242-4483-894f-80ae02a4840e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6f1c1e6414d0059dfd1d43bbbb40eabdfc9470b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720686"
---
# <a name="table-valued-object-properties-visual-database-tools"></a><span data-ttu-id="20add-102">Tabellenwertobjekt-Eigenschaften (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="20add-102">Table-Valued Object Properties (Visual Database Tools)</span></span>
  <span data-ttu-id="20add-103">Diese Eigenschaften werden im Eigenschaftenfenster angezeigt, wenn Sie im **Abfrage- und Sicht-Designer**ein Tabellenwertobjekt auswählen.</span><span class="sxs-lookup"><span data-stu-id="20add-103">These properties appear in the Properties window when you select a table-valued object in **Query and View Designer**.</span></span> <span data-ttu-id="20add-104">Das Tabellenwertobjekt kann eine Sicht, ein Synonym, eine abgeleitete Tabelle oder eine Tabellenwertfunktion sein.</span><span class="sxs-lookup"><span data-stu-id="20add-104">The table-valued object could be a view, synonym, derived table, or table-valued function.</span></span> <span data-ttu-id="20add-105">Soweit nicht anders angegeben, sind die Eigenschaften im Fenster **Eigenschaften** schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="20add-105">Unless otherwise noted, these properties are read-only in the **Properties** window.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="20add-106">Die in diesem Thema behandelten Eigenschaften sind nicht alphabetisch, sondern nach Kategorie angeordnet.</span><span class="sxs-lookup"><span data-stu-id="20add-106">The properties in this topic are ordered by category rather than alphabet.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="20add-107">Die angezeigten Dialogfelder und Menübefehle können von den in der Hilfe beschriebenen abweichen. Dies hängt von Ihren aktiven Einstellungen oder Ihrer Edition ab.</span><span class="sxs-lookup"><span data-stu-id="20add-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="20add-108">Um Ihre Einstellungen zu ändern, wählen Sie **Einstellungen importieren und exportieren** im Menü **Extras** aus.</span><span class="sxs-lookup"><span data-stu-id="20add-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span>  
  
 <span data-ttu-id="20add-109">**Kategorie Identität**</span><span class="sxs-lookup"><span data-stu-id="20add-109">**Identity Category**</span></span>  
 <span data-ttu-id="20add-110">Wird erweitert, um die Eigenschaften **Name** und **TVO-Typ** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="20add-110">Expands to show the **Name** and **TVO Type** properties.</span></span>  
  
 <span data-ttu-id="20add-111">**Name**</span><span class="sxs-lookup"><span data-stu-id="20add-111">**Name**</span></span>  
 <span data-ttu-id="20add-112">Zeigt den Namen des ausgewählten Tabellenwertobjekts an.</span><span class="sxs-lookup"><span data-stu-id="20add-112">Shows the name of the selected table-valued object.</span></span>  
  
 <span data-ttu-id="20add-113">**TVO-Typ**</span><span class="sxs-lookup"><span data-stu-id="20add-113">**TVO Type**</span></span>  
 <span data-ttu-id="20add-114">Zeigt den Typ des Tabellenwertobjekts an.</span><span class="sxs-lookup"><span data-stu-id="20add-114">Shows which type of table-valued object.</span></span> <span data-ttu-id="20add-115">Dabei kann es sich um eine Basistabelle, eine Sicht, eine Tabellenwertfunktion oder eine abgeleitete Tabelle handeln.</span><span class="sxs-lookup"><span data-stu-id="20add-115">It can be either a base table, view, table-valued function, or a derived table.</span></span>  
  
 <span data-ttu-id="20add-116">**Abfrage-Designer – Kategorie**</span><span class="sxs-lookup"><span data-stu-id="20add-116">**Query DesignerCategory**</span></span>  
 <span data-ttu-id="20add-117">Wird erweitert, um die Eigenschaften von **Alias**, **Spaltenliste**, **Vollständiger Name**und **Parameterliste**anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="20add-117">Expands to show properties for **Alias**, **Column List**, **Full Name**, and **Parameter List**.</span></span>  
  
 <span data-ttu-id="20add-118">**Alias**</span><span class="sxs-lookup"><span data-stu-id="20add-118">**Alias**</span></span>  
 <span data-ttu-id="20add-119">Zeigt den Alias des ausgewählten Tabellenwertobjekts an.</span><span class="sxs-lookup"><span data-stu-id="20add-119">Shows the alias for the selected table-valued object.</span></span> <span data-ttu-id="20add-120">Um einen Alias hinzuzufügen oder zu ändern, geben Sie ihn in das Feld ein.</span><span class="sxs-lookup"><span data-stu-id="20add-120">To add or change an alias, type it into the field.</span></span>  
  
 <span data-ttu-id="20add-121">**Spaltenliste**</span><span class="sxs-lookup"><span data-stu-id="20add-121">**Column List**</span></span>  
 <span data-ttu-id="20add-122">Zeigt die Spalten des ausgewählten Tabellenwertobjekts an.</span><span class="sxs-lookup"><span data-stu-id="20add-122">Shows the columns included in the selected table-valued object.</span></span> <span data-ttu-id="20add-123">Klicken Sie auf die Spaltenliste und dann rechts neben der Eigenschaft auf die Schaltfläche mit den Auslassungspunkten (...), um die Spalten in einem eigenen Fenster anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="20add-123">To see them in a separate window, click Column List and then click the ellipses (...) to the right of the property.</span></span>  
  
 <span data-ttu-id="20add-124">**Vollständiger Name**</span><span class="sxs-lookup"><span data-stu-id="20add-124">**Full Name**</span></span>  
 <span data-ttu-id="20add-125">Zeigt den Namen des ausgewählten Tabellenwertobjekts mitsamt Zusatzinformationen an, z. B. Schema oder Datenquelle des Objekts.</span><span class="sxs-lookup"><span data-stu-id="20add-125">Shows the name of the selected table-valued object, including additional information such as the schema or data source of the object.</span></span>  
  
 <span data-ttu-id="20add-126">**Parameterliste**</span><span class="sxs-lookup"><span data-stu-id="20add-126">**Parameter List**</span></span>  
 <span data-ttu-id="20add-127">Zeigt die für die ausgewählte Tabellenwertfunktion definierten Parameter an.</span><span class="sxs-lookup"><span data-stu-id="20add-127">Shows the parameters defined for selected table-valued function.</span></span> <span data-ttu-id="20add-128">Klicken Sie auf die Parameterliste und dann rechts neben der Eigenschaft auf die Schaltfläche mit den Auslassungspunkten (...), um Werte für die Parameter zu definieren.</span><span class="sxs-lookup"><span data-stu-id="20add-128">To define a value for the parameters, click Parameter List and then click the ellipses (...) to the right of the property.</span></span> <span data-ttu-id="20add-129">Geben Sie im Dialogfeld Funktionsparameter die entsprechenden Werte ein.</span><span class="sxs-lookup"><span data-stu-id="20add-129">In the Function Parameters dialog box, type in values.</span></span> <span data-ttu-id="20add-130">Diese Eigenschaft ist nur verfügbar, wenn eine Tabellenwertfunktion ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="20add-130">This property is only available when a table-valued function is selected.</span></span>  
  
  
