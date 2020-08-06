---
title: Benannte Berechnung erstellen/bearbeiten (Dialog Feld) (Analysis Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dsveditor.createnamedcalculation.f1
helpviewer_keywords:
- Named Calculation dialog box
ms.assetid: 66fb30ae-f5c5-4bfc-80ca-8c8a3a9bb30d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0b6777feb47a1ce6b601d0190e413b4baae35f1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608107"
---
# <a name="create-edit-named-calculation-dialog-box-analysis-services"></a><span data-ttu-id="f8b4a-102">Benannte Berechnung erstellen/bearbeiten (Dialog Feld) (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="f8b4a-102">Create-Edit Named Calculation Dialog Box (Analysis Services)</span></span>
  <span data-ttu-id="f8b4a-103">Mithilfe des Dialogfelds **Benannte Berechnung erstellen/bearbeiten** können Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] eine benannte Berechnung für eine Tabelle in einer Datenquellensicht definieren oder ändern.</span><span class="sxs-lookup"><span data-stu-id="f8b4a-103">Use the **Create/Edit Named Calculation** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to define or modify a named calculation for a table in a data source view.</span></span> <span data-ttu-id="f8b4a-104">Führen Sie zum Anzeigen des Dialogfelds **Benannte Berechnung erstellen/bearbeiten** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="f8b4a-104">You can display the **Create/Edit Named Calculation** dialog box by:</span></span>  
  
-   <span data-ttu-id="f8b4a-105">Klicken Sie im Bereich **Symbolleiste** von **Datenquellensicht-Designer** auf **Neue benannte Berechnung**.</span><span class="sxs-lookup"><span data-stu-id="f8b4a-105">Clicking **New Named Calculation** in the **Toolbar** pane of **Data Source View Designer**.</span></span>  
  
-   <span data-ttu-id="f8b4a-106">Klicken Sie im Bereich **Tabellen** oder **Diagramm** des **Datenquellensicht-Designers** mit der rechten Maustaste auf eine Tabelle, und wählen Sie **Neue benannte Berechnung** aus.</span><span class="sxs-lookup"><span data-stu-id="f8b4a-106">Right-clicking a table in either the **Tables** or **Diagram** pane of **Data Source View Designer** and selecting **New Named Calculation**.</span></span>  
  
-   <span data-ttu-id="f8b4a-107">Klicken Sie im Bereich **Diagramm** des **Datenquellensicht-Designers** mit der rechten Maustaste auf den Namen einer benannten Berechnung, und wählen Sie **Benannte Berechnung bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="f8b4a-107">Right-clicking the name of a named calculation in the **Diagram** pane of **Data Source View Designer** and selecting **Edit Named Calculation**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f8b4a-108">Tastatur</span><span class="sxs-lookup"><span data-stu-id="f8b4a-108">Options</span></span>  
 <span data-ttu-id="f8b4a-109">**Spaltenname**</span><span class="sxs-lookup"><span data-stu-id="f8b4a-109">**Column Name**</span></span>  
 <span data-ttu-id="f8b4a-110">Geben Sie den Namen der benannten Berechnung ein.</span><span class="sxs-lookup"><span data-stu-id="f8b4a-110">Type the name of the named calculation.</span></span>  
  
 <span data-ttu-id="f8b4a-111">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="f8b4a-111">**Description**</span></span>  
 <span data-ttu-id="f8b4a-112">Geben Sie die optionale Beschreibung der benannten Berechnung ein.</span><span class="sxs-lookup"><span data-stu-id="f8b4a-112">Type the optional description of the named calculation.</span></span>  
  
 <span data-ttu-id="f8b4a-113">**Ausdruck**</span><span class="sxs-lookup"><span data-stu-id="f8b4a-113">**Expression**</span></span>  
 <span data-ttu-id="f8b4a-114">Geben Sie einen gültigen SQL-Ausdruck ein, der einen skalaren Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="f8b4a-114">Type a valid SQL expression that returns a scalar value.</span></span> <span data-ttu-id="f8b4a-115">Der Ausdruck wird an den Anbieter gesendet und im folgenden Ausdruck überprüft:</span><span class="sxs-lookup"><span data-stu-id="f8b4a-115">The expression is sent to the provider, and validated in the following expression:</span></span>  
  
```  
SELECT <Table Name in Data Source>.* , <Expression> AS <Column Name> FROM <Table Name in Data Source>AS <Table Name in Data Source View>  
```  
  
 <span data-ttu-id="f8b4a-116">Der Ausdruck kann Verweise auf andere Tabellen in Form einer untergeordneten SELECT-Anweisung enthalten.</span><span class="sxs-lookup"><span data-stu-id="f8b4a-116">The expression can contain references to other tables, by means of a sub-select statement.</span></span> <span data-ttu-id="f8b4a-117">If the expression would require parentheses in a SELECT statement, the expression entered must be enclosed between parentheses.</span><span class="sxs-lookup"><span data-stu-id="f8b4a-117">If the expression would require parentheses in a SELECT statement, the expression entered must be enclosed between parentheses.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8b4a-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f8b4a-118">See Also</span></span>  
 <span data-ttu-id="f8b4a-119">[Analysis Services Designer und Dialog Felder &#40;Mehrdimensionale Daten&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="f8b4a-119">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="f8b4a-120">Datenquellensicht-Designer &#40;Analysis Services – Mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="f8b4a-120">Data Source View Designer &#40;Analysis Services - Multidimensional Data&#41;</span></span>](data-source-view-designer-analysis-services-multidimensional-data.md)  
  
  
