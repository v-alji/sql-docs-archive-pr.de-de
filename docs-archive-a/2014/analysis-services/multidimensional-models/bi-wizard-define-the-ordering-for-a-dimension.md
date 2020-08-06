---
title: Definieren der Reihenfolge für eine Dimension | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- OrderBy property
- dimensions [Analysis Services], ordering
- Business Intelligence enhancements [Analysis Services], ordering
- dimensions [Analysis Services], Business Intelligence enhancements
- ordering dimensions [Analysis Services]
- OrderByAttributeID property
ms.assetid: c42fbd58-244d-4e0a-b715-6f919cbc3ad9
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8cd5ea148e374c18c530ba0a15c80dbb23983020
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615663"
---
# <a name="define-the-ordering-for-a-dimension"></a><span data-ttu-id="d1159-102">Definieren der Reihenfolge für eine Dimension</span><span class="sxs-lookup"><span data-stu-id="d1159-102">Define the Ordering for a Dimension</span></span>
  <span data-ttu-id="d1159-103">Fügen Sie einem Cube oder einer Dimension die Erweiterung für die Attributreihenfolge hinzu, um anzugeben, wie die Elemente eines Attributs sortiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d1159-103">Add the attribute ordering enhancement to a cube or dimension to specify how the members of an attribute are ordered.</span></span> <span data-ttu-id="d1159-104">Elemente können nach dem Namen oder dem Schlüssel des Attributs oder dem Namen bzw. dem Schlüssel eines anderen Attributs (auf Basis einer Attributbeziehung) sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="d1159-104">Members can be ordered by the name or the key of the attribute, or by the name or the key of another attribute (based on an attribute relationship).</span></span> <span data-ttu-id="d1159-105">Standardmäßig sind Elemente nach dem Namen sortiert.</span><span class="sxs-lookup"><span data-stu-id="d1159-105">By default, members are ordered by the name.</span></span> <span data-ttu-id="d1159-106">Diese Erweiterung ändert die Eigenschaftseinstellungen `OrderBy` und `OrderByAttributeID` für Attribute in einer Dimension.</span><span class="sxs-lookup"><span data-stu-id="d1159-106">This enhancement changes the `OrderBy` and `OrderByAttributeID` property settings for attributes in a dimension.</span></span>  
  
 <span data-ttu-id="d1159-107">Verwenden Sie zum Hinzufügen der Attributreihenfolge den Business Intelligence-Assistenten, und wählen Sie auf der Seite **Erweiterung auswählen** die Option **Attributreihenfolge angeben** aus.</span><span class="sxs-lookup"><span data-stu-id="d1159-107">To add attribute ordering, you use the Business Intelligence Wizard, and select the **Specify attribute ordering** option on the **Choose Enhancement** page.</span></span> <span data-ttu-id="d1159-108">Der Assistent führt Sie durch die Schritte zum Auswählen einer Dimension, auf die die Attributreihenfolge angewendet werden soll, und zum Angeben der Reihenfolge der Attribute für die ausgewählte Dimension.</span><span class="sxs-lookup"><span data-stu-id="d1159-108">This wizard then guides you through the steps of selecting a dimension to which you want to apply attribute ordering and specifying how to order the attributes for the selected dimension.</span></span>  
  
## <a name="selecting-a-dimension"></a><span data-ttu-id="d1159-109">Auswählen einer Dimension</span><span class="sxs-lookup"><span data-stu-id="d1159-109">Selecting a Dimension</span></span>  
 <span data-ttu-id="d1159-110">Auf der ersten Seite des Assistenten, der Seite **Attributreihenfolge angeben** , geben Sie die Dimension an, auf die die Attributreihenfolge angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d1159-110">On the first **Specify Attribute Ordering** page of the wizard, you specify the dimension to which you want to apply attribute ordering.</span></span> <span data-ttu-id="d1159-111">Durch Anwenden der Attributreihenfolge auf die ausgewählte Dimension werden Änderungen an der Dimension vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="d1159-111">The attribute ordering enhancement added to this selected dimension will result in changes to the dimension.</span></span> <span data-ttu-id="d1159-112">Diese Änderungen werden an alle Cubes vererbt, die die ausgewählte Dimension enthalten.</span><span class="sxs-lookup"><span data-stu-id="d1159-112">These changes will be inherited by all cubes that include the selected dimension.</span></span>  
  
## <a name="specifying-ordering"></a><span data-ttu-id="d1159-113">Angeben der Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="d1159-113">Specifying Ordering</span></span>  
 <span data-ttu-id="d1159-114">Auf der zweiten Seite des Assistenten, **Attributreihenfolge angeben** ,  geben Sie an, wie die Attribute in der Dimension sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="d1159-114">On the second **Specify Attribute Ordering** page of the wizard, you specify how all the attributes in the dimension will be ordered.</span></span>  
  
 <span data-ttu-id="d1159-115">In der **Reihenfolgenattribut** -Spalte können Sie das Attribut für die Reihenfolge ändern.</span><span class="sxs-lookup"><span data-stu-id="d1159-115">In the **Ordering Attribute** column, you can change the attribute used to do the ordering.</span></span> <span data-ttu-id="d1159-116">Wenn das Attribut, das Sie zum Sortieren von Elementen verwenden möchten, nicht in der Liste aufgeführt ist, Scrollen Sie in der Liste nach unten, und wählen Sie dann aus, **\<New attribute...>** um das Dialogfeld **Spalte auswählen** zu öffnen, in dem Sie eine Spalte in einer Dimensions Tabelle auswählen können.</span><span class="sxs-lookup"><span data-stu-id="d1159-116">If the attribute that you want to use to order members is not in the list, scroll down the list, and then select **\<New attribute...>** to open the **Select a Column** dialog box, where you can select a column in a dimension table.</span></span> <span data-ttu-id="d1159-117">Durch Auswählen einer Spalte mithilfe des Dialogfelds **Spalte auswählen** wird ein zusätzliches Attribut erstellt, mit dem die Elemente eines Attributs sortiert werden können.</span><span class="sxs-lookup"><span data-stu-id="d1159-117">Selecting a column by using the **Select a Column** dialog box creates an additional attribute with which to order members of an attribute.</span></span>  
  
 <span data-ttu-id="d1159-118">In der **Kriterien** -Spalte können Sie dann auswählen, ob die Elemente des Attributs entweder nach **Schlüssel** oder nach **Name**sortiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d1159-118">In the **Criteria** column, you can then select whether to order the members of the attribute by either **Key** or **Name**.</span></span>  
  
  
