---
title: Spalten von langsam veränderlichen Dimensionen (Assistent für langsam veränderliche Dimensionen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.loaddimwizard.scdsupport.f1
ms.assetid: 36de99d5-5368-48e0-b876-17e9c6862c6c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6283887cbddb9844e0ac769281184f588dc2a94d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695869"
---
# <a name="slowly-changing-dimension-columns-slowly-changing-dimension-wizard"></a><span data-ttu-id="d60ea-102">Spalten von langsam veränderlichen Dimensionen (Assistent für langsam veränderliche Dimensionen)</span><span class="sxs-lookup"><span data-stu-id="d60ea-102">Slowly Changing Dimension Columns (Slowly Changing Dimension Wizard)</span></span>
  <span data-ttu-id="d60ea-103">Im Dialogfeld **Spalten von langsam veränderlichen Dimensionen** können Sie für jede Spalte einer langsam veränderlichen Dimension einen Änderungstyp auswählen.</span><span class="sxs-lookup"><span data-stu-id="d60ea-103">Use the **Slowly Changing Dimensions Columns** dialog box to select a change type for each slowly changing dimension column.</span></span>  
  
 <span data-ttu-id="d60ea-104">Weitere Informationen zu diesem Assistenten finden Sie unter [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="d60ea-104">To learn more about this wizard, see [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="d60ea-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="d60ea-105">Options</span></span>  
 <span data-ttu-id="d60ea-106">**Dimensionsspalten**</span><span class="sxs-lookup"><span data-stu-id="d60ea-106">**Dimension Columns**</span></span>  
 <span data-ttu-id="d60ea-107">Wählen Sie eine Dimensionsspalte aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="d60ea-107">Select a dimension column from the list.</span></span>  
  
 <span data-ttu-id="d60ea-108">**Änderungstyp**</span><span class="sxs-lookup"><span data-stu-id="d60ea-108">**Change Type**</span></span>  
 <span data-ttu-id="d60ea-109">Wählen Sie ein **Festes Attribut**oder einen der beiden Typen von veränderlichen Attributen aus.</span><span class="sxs-lookup"><span data-stu-id="d60ea-109">Select a **Fixed Attribute**, or select one of the two types of changing attributes.</span></span> <span data-ttu-id="d60ea-110">Verwenden Sie **Festes Attribut** , wenn sich der Wert in einer Spalte nicht ändern soll; [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] behandelt Änderungen dann als Fehler.</span><span class="sxs-lookup"><span data-stu-id="d60ea-110">Use **Fixed Attribute** when the value in a column should not change; [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] then treats changes as errors.</span></span> <span data-ttu-id="d60ea-111">Verwenden Sie **Veränderliches Attribut** , wenn vorhandene Werte von geänderten Werten überschrieben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d60ea-111">Use **Changing Attribute** to overwrite existing values with changed values.</span></span> <span data-ttu-id="d60ea-112">Verwenden Sie **Verlaufsattribut** , wenn geänderte Werte in neuen Datensätzen gespeichert werden sollen, während die vorigen Datensätze gleichzeitig als veraltet gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="d60ea-112">Use **Historical Attribute** to save changed values in new records, while marking previous records as outdated.</span></span>  
  
 <span data-ttu-id="d60ea-113">**Remove**</span><span class="sxs-lookup"><span data-stu-id="d60ea-113">**Remove**</span></span>  
 <span data-ttu-id="d60ea-114">Wählen Sie eine Dimensionsspalte aus, und entfernen Sie sie aus der Liste der zugeordneten Spalten, indem Sie auf **Entfernen**klicken.</span><span class="sxs-lookup"><span data-stu-id="d60ea-114">Select a dimension column, and remove it from the list of mapped columns by clicking **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d60ea-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d60ea-115">See Also</span></span>  
 [<span data-ttu-id="d60ea-116">Konfiguration von Ausgaben mithilfe des Assistenten für langsam veränderliche Dimensionen</span><span class="sxs-lookup"><span data-stu-id="d60ea-116">Configure Outputs Using the Slowly Changing Dimension Wizard</span></span>](configure-outputs-using-the-slowly-changing-dimension-wizard.md)  
  
  
