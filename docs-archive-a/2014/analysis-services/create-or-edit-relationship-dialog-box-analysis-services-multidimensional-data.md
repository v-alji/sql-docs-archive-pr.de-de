---
title: Beziehung erstellen oder bearbeiten (Dialog Feld) (Analysis Services-Mehrdimensionale Daten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dsvdesigner.createrelationship.f1
helpviewer_keywords:
- Create Relationship dialog box
ms.assetid: da3c7074-623e-4ddf-a707-d3276a47cf1c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4edae3f78ac6b764d91e1be97787fe59d49421db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616277"
---
# <a name="create-or-edit-relationship-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="53d0e-102">Beziehung erstellen oder bearbeiten (Dialogfeld) (Analysis Services – Mehrdimensionale Daten)</span><span class="sxs-lookup"><span data-stu-id="53d0e-102">Create or Edit Relationship Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="53d0e-103">Mithilfe des Dialogfelds **Beziehung erstellen/bearbeiten** in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] können Sie eine Beziehung in der Datenquellensicht definieren oder ändern.</span><span class="sxs-lookup"><span data-stu-id="53d0e-103">Use the **Create/Edit Relationship** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to define or modify a relationship in a data source view.</span></span> <span data-ttu-id="53d0e-104">Zum Anzeigen des Dialogfelds **Beziehung erstellen/bearbeiten** führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="53d0e-104">You can display the **Create/Edit Relationship** dialog box by:</span></span>  
  
-   <span data-ttu-id="53d0e-105">Klicken Sie im Bereich **Symbolleiste** von **Datenquellensicht-Designer** auf **Neue Beziehung**.</span><span class="sxs-lookup"><span data-stu-id="53d0e-105">Clicking **New Relationship** in the **Toolbar** pane of **Data Source View Designer**.</span></span>  
  
-   <span data-ttu-id="53d0e-106">Klicken Sie im Bereich **Tabellen** oder **Diagramm** von **Datenquellensicht-Designer** mit der rechten Maustaste in eine Tabelle, und wählen Sie **Neue Beziehung**aus.</span><span class="sxs-lookup"><span data-stu-id="53d0e-106">Right-clicking a table in either the **Tables** or **Diagram** pane of **Data Source View Designer** and selecting **New Relationship**.</span></span>  
  
-   <span data-ttu-id="53d0e-107">Klicken Sie im Bereich **Diagramm** von **Datenquellensicht-Designer** mit der rechten Maustaste auf eine Beziehung, und wählen Sie **Beziehung bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="53d0e-107">Right-clicking a relationship in the **Diagram** pane of **Data Source View Designer** and selecting **Edit Relationship**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="53d0e-108">Sie können im **Datenquellen Sicht-Designer** Beziehungen erstellen, die in der zugrunde liegenden Datenquelle nicht vorhanden sind, und vom **Datenquellen Sicht-Designer** erstellte Beziehungen aus vorhandenen Fremdschlüssel Beziehungen in der zugrunde liegenden Datenquelle entfernen.</span><span class="sxs-lookup"><span data-stu-id="53d0e-108">You can create relationships in **Data Source View Designer** that do not exist in the underlying data source, and remove relationships created by **Data Source View Designer** from existing foreign key relationships in the underlying data source.</span></span>  
  
## <a name="options"></a><span data-ttu-id="53d0e-109">Tastatur</span><span class="sxs-lookup"><span data-stu-id="53d0e-109">Options</span></span>  
 <span data-ttu-id="53d0e-110">**Quelltabelle (Fremdschlüsseltabelle)**</span><span class="sxs-lookup"><span data-stu-id="53d0e-110">**Source (foreign key) table**</span></span>  
 <span data-ttu-id="53d0e-111">Wählen Sie die Tabelle oder die benannte Abfrage aus, die den Verweis auf eine oder mehrere Spalten in der Zieltabelle enthält.</span><span class="sxs-lookup"><span data-stu-id="53d0e-111">Select the table or named query that contains the reference to one or more columns in the destination table.</span></span>  
  
 <span data-ttu-id="53d0e-112">**Zieltabelle (Primärschlüsseltabelle)**</span><span class="sxs-lookup"><span data-stu-id="53d0e-112">**Destination (primary key) table**</span></span>  
 <span data-ttu-id="53d0e-113">Wählen Sie die Tabelle aus, die eine oder mehrere Spalten enthält, auf die die Quelltabelle verweist.</span><span class="sxs-lookup"><span data-stu-id="53d0e-113">Select the table that contains one or more columns referenced by the source table.</span></span> <span data-ttu-id="53d0e-114">Wählen Sie für Selbstverknüpfungen dieselbe Tabelle aus, wie in **Quelltabelle (Fremdschlüsseltabelle)**.</span><span class="sxs-lookup"><span data-stu-id="53d0e-114">For self-joins, select the same table selected in **Source (foreign key) table**.</span></span>  
  
 <span data-ttu-id="53d0e-115">**Quellspalten**</span><span class="sxs-lookup"><span data-stu-id="53d0e-115">**Source columns**</span></span>  
 <span data-ttu-id="53d0e-116">Wählen Sie die Spalten aus, die auf Spalten in der Zieltabelle verweisen.</span><span class="sxs-lookup"><span data-stu-id="53d0e-116">Select the columns that reference columns in the destination table.</span></span>  
  
 <span data-ttu-id="53d0e-117">**Zielspalten**</span><span class="sxs-lookup"><span data-stu-id="53d0e-117">**Destination columns**</span></span>  
 <span data-ttu-id="53d0e-118">Wählen Sie die Spalten aus, auf die durch Spalten in der Quelltabelle verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="53d0e-118">Select the columns that are referenced by columns in the source table.</span></span>  
  
 <span data-ttu-id="53d0e-119">**Umgekehr**</span><span class="sxs-lookup"><span data-stu-id="53d0e-119">**Reverse**</span></span>  
 <span data-ttu-id="53d0e-120">Klicken Sie auf diese Option, um die Richtung der Beziehung umzukehren.</span><span class="sxs-lookup"><span data-stu-id="53d0e-120">Click to reverse the direction of the relationship.</span></span>  
  
 <span data-ttu-id="53d0e-121">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="53d0e-121">**Description**</span></span>  
 <span data-ttu-id="53d0e-122">Geben Sie eine optionale Beschreibung für die Beziehung ein.</span><span class="sxs-lookup"><span data-stu-id="53d0e-122">Type an optional description for the relationship.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53d0e-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="53d0e-123">See Also</span></span>  
 <span data-ttu-id="53d0e-124">[Analysis Services Designer und Dialog Felder &#40;Mehrdimensionale Daten&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="53d0e-124">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="53d0e-125">Datenquellensicht-Designer &#40;Analysis Services – Mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="53d0e-125">Data Source View Designer &#40;Analysis Services - Multidimensional Data&#41;</span></span>](data-source-view-designer-analysis-services-multidimensional-data.md)  
  
  
