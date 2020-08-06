---
title: Definieren von Elementgruppen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- member groups [Analysis Services]
- grouping members
- DiscretizationMethod property
ms.assetid: 006cc915-c499-4781-b9a7-01ad31bebf6a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 95f9516c7a0077e97af348afa863fe15c8d4528b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725117"
---
# <a name="define-member-groups"></a><span data-ttu-id="3c443-102">Definieren von Elementgruppen</span><span class="sxs-lookup"><span data-stu-id="3c443-102">Define Member Groups</span></span>
  <span data-ttu-id="3c443-103">Wenn ein Attribut über viele Elemente verfügt, können Sie diese Elemente in Buckets gruppieren und so die Zahl derjenigen Elemente verringern, die Benutzer sehen, wenn sie die Daten einer Hierarchie durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="3c443-103">If an attribute has a large number of members, you can choose to group those members into buckets, reducing the number of members that users see when they browse the data in a hierarchy.</span></span> <span data-ttu-id="3c443-104">Sie können auch die Zahl der Buckets festlegen, in denen die Elemente Gruppen bilden und ein Benennungsschema für die Buckets vorgeben.</span><span class="sxs-lookup"><span data-stu-id="3c443-104">You can also determine the number of buckets in which the members are groups and set a naming scheme for the buckets.</span></span> <span data-ttu-id="3c443-105">Weitere Informationen finden Sie unter [Gruppieren von Attributelementen &#40;Diskretisierung&#41;](attribute-properties-group-attribute-members.md).</span><span class="sxs-lookup"><span data-stu-id="3c443-105">For more information, see [Group Attribute Members &#40;Discretization&#41;](attribute-properties-group-attribute-members.md).</span></span>  
  
 <span data-ttu-id="3c443-106">Sie gruppieren Elemente, indem Sie die **DiscretizationMethod** -Eigenschaft festlegen, auf die Sie im Fenster **Eigenschaften** in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="3c443-106">You group members by setting the **DiscretizationMethod** property, which is accessed through the **Properties** window in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="3c443-107">Wenn Sie Elementgruppen erstellen, sind Ihre Änderungen erst dann für Benutzer verfügbar, wenn Sie die Dimension verarbeitet haben.</span><span class="sxs-lookup"><span data-stu-id="3c443-107">When you create member groups, your changes are not available to users until you process the dimension.</span></span> <span data-ttu-id="3c443-108">Weitere Informationen finden Sie unter mehr [dimensionale Modell Objekt Verarbeitung](processing-a-multidimensional-model-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="3c443-108">For more information, see [Multidimensional Model Object Processing](processing-a-multidimensional-model-analysis-services.md).</span></span>  
  
### <a name="to-create-member-groups"></a><span data-ttu-id="3c443-109">So erstellen Sie eine Elementgruppe</span><span class="sxs-lookup"><span data-stu-id="3c443-109">To create member groups</span></span>  
  
1.  <span data-ttu-id="3c443-110">Öffnen Sie die Dimension, mit der Sie arbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="3c443-110">Open the dimension that you want to work with.</span></span> <span data-ttu-id="3c443-111">Standardmäßig wird die Registerkarte **Dimensionsstruktur** geöffnet.</span><span class="sxs-lookup"><span data-stu-id="3c443-111">The **Dimension Structure** tab opens by default.</span></span>  
  
2.  <span data-ttu-id="3c443-112">Klicken Sie in **Attribute**mit der rechten Maustaste auf die Attribute, deren Elemente Sie gruppieren möchten, und klicken Sie anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="3c443-112">In **Attributes**, right-click the attribute whose members you want to group, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="3c443-113">Wählen Sie in der Dropdownliste neben **DiscretizationMethod**eine Methode aus, nach der Sie die Elemente gruppieren.</span><span class="sxs-lookup"><span data-stu-id="3c443-113">From the drop-down list next to **DiscretizationMethod**, select a method by which to group the members.</span></span> <span data-ttu-id="3c443-114">Weitere Informationen zu **DiscretizationMethod**-Einstellungen finden Sie unter [Gruppieren von Attributelementen &#40;Diskretisierung&#41;](attribute-properties-group-attribute-members.md).</span><span class="sxs-lookup"><span data-stu-id="3c443-114">For more information about **DiscretizationMethod** settings, see [Group Attribute Members &#40;Discretization&#41;](attribute-properties-group-attribute-members.md).</span></span>  
  
  
