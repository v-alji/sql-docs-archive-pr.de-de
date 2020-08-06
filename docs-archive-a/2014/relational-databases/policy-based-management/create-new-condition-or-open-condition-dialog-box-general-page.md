---
title: Dialogfeld 'Neue Bedingung erstellen' oder 'Bedingung öffnen', Seite 'Allgemein' | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.dmf.condition.f1
ms.assetid: 106954bf-e4ba-412b-9c1a-907d06153dcd
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 72e4a77df553ac8e97609e82bd51c8fd93b64b23
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622602"
---
# <a name="create-new-condition-or-open-condition-dialog-box-general-page"></a><span data-ttu-id="59392-102">Dialogfeld 'Neue Bedingung erstellen' oder 'Bedingung öffnen', Seite 'Allgemein'</span><span class="sxs-lookup"><span data-stu-id="59392-102">Create New Condition or Open Condition Dialog Box, General Page</span></span>
  <span data-ttu-id="59392-103">Mithilfe dieses Dialogfelds können Sie eine richtlinienbasierte Verwaltungsbedingung erstellen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="59392-103">Use this dialog box to create or change a Policy-Based Management condition.</span></span> <span data-ttu-id="59392-104">Eine Bedingung ist ein boolescher Ausdruck, der einen Satz zulässiger Zustände eines durch die richtlinienbasierte Verwaltung verwalteten Ziels für Facets angibt.</span><span class="sxs-lookup"><span data-stu-id="59392-104">A condition is a Boolean expression that specifies a set of allowed states of a Policy-Based Management managed target with regard to facets.</span></span> <span data-ttu-id="59392-105">Die Eigenschaften, die im Feld **Ausdruck/Feld** ausgewählt werden können, hängen vom verwendeten Facet ab.</span><span class="sxs-lookup"><span data-stu-id="59392-105">The properties that can be selected in the **Expression/Field** box depend upon the facet that is used.</span></span> <span data-ttu-id="59392-106">Weitere Informationen darüber, wie Bedingungen mit Facets und Richtlinien zusammenhängen finden Sie unter [Verwalten von Servern mit der richtlinienbasierten Verwaltung](administer-servers-by-using-policy-based-management.md).</span><span class="sxs-lookup"><span data-stu-id="59392-106">For more information about how conditions relate to facets and policies, see [Administer Servers by Using Policy-Based Management](administer-servers-by-using-policy-based-management.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="59392-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="59392-107">Options</span></span>  
 <span data-ttu-id="59392-108">**Name**</span><span class="sxs-lookup"><span data-stu-id="59392-108">**Name**</span></span>  
 <span data-ttu-id="59392-109">Geben Sie für eine Bedingung den Namen der neuen Bedingung ein.</span><span class="sxs-lookup"><span data-stu-id="59392-109">For a new condition, type the new condition name.</span></span> <span data-ttu-id="59392-110">Für eine vorhandene Bedingung wird der Name angezeigt.</span><span class="sxs-lookup"><span data-stu-id="59392-110">For an existing condition, the name is displayed.</span></span>  
  
 <span data-ttu-id="59392-111">**Facet**</span><span class="sxs-lookup"><span data-stu-id="59392-111">**Facet**</span></span>  
 <span data-ttu-id="59392-112">Das von dieser Bedingung verwendete Facet.</span><span class="sxs-lookup"><span data-stu-id="59392-112">The facet used by this condition.</span></span>  
  
 <span data-ttu-id="59392-113">**And/Or**</span><span class="sxs-lookup"><span data-stu-id="59392-113">**AndOr**</span></span>  
 <span data-ttu-id="59392-114">Wenn Sie mehrere Ausdrücke hinzufügen, wird hiermit angegeben, ob die Ausdrücke mit **Und** oder **Oder**verbunden werden sollen.</span><span class="sxs-lookup"><span data-stu-id="59392-114">When you add multiple expressions, indicates whether the expressions should be joined by using **And** or **Or**.</span></span> <span data-ttu-id="59392-115">Bleibt leer, wenn nur ein Ausdruck vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="59392-115">Remains blank when there is only one expression.</span></span>  
  
 <span data-ttu-id="59392-116">**Feld**</span><span class="sxs-lookup"><span data-stu-id="59392-116">**Field**</span></span>  
 <span data-ttu-id="59392-117">Jedes Facet macht eine oder mehrere Eigenschaften verfügbar, die festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="59392-117">Each facet exposes one or more properties that can be set.</span></span> <span data-ttu-id="59392-118">Wählen Sie im Feld Feld eine Eigenschaft aus der Liste der verfügbaren Eigenschaften aus, um einen Ausdruck für diese Bedingung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="59392-118">In the field box, select a property from the list of available properties to create an expression for this condition.</span></span>  
  
 <span data-ttu-id="59392-119">**Operator**</span><span class="sxs-lookup"><span data-stu-id="59392-119">**Operator**</span></span>  
 <span data-ttu-id="59392-120">Wählen Sie einen Vergleichsoperator für diesen Ausdruck aus.</span><span class="sxs-lookup"><span data-stu-id="59392-120">Select a comparison operator for this expression.</span></span> <span data-ttu-id="59392-121">Folgende Operatoren sind verfügbar: =, !=, >, >=, <, <=, [NOT]LIKE, [NOT]IN.</span><span class="sxs-lookup"><span data-stu-id="59392-121">Operators are as follows: =, !=, >, >=, <, <=, [NOT]LIKE, [NOT]IN.</span></span> <span data-ttu-id="59392-122">Für einige Eigenschaften sind nicht alle Operatoren verfügbar.</span><span class="sxs-lookup"><span data-stu-id="59392-122">Not all operators are available for some properties.</span></span>  
  
 <span data-ttu-id="59392-123">**Wert**</span><span class="sxs-lookup"><span data-stu-id="59392-123">**Value**</span></span>  
 <span data-ttu-id="59392-124">Die Werteinstellung für diesen Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="59392-124">The value setting for this expression.</span></span> <span data-ttu-id="59392-125">Die zulässigen Werte hängen vom Facet ab.</span><span class="sxs-lookup"><span data-stu-id="59392-125">The allowed values depend on the facet.</span></span> <span data-ttu-id="59392-126">Werte können WAHR/FALSCH, eine Zeichenfolge oder ein numerischer Wert sein.</span><span class="sxs-lookup"><span data-stu-id="59392-126">Values can be TRUE/FALSE, string, or numeric.</span></span> <span data-ttu-id="59392-127">Zeichenfolgenwerte müssen in einfache Anführungszeichen eingeschlossen werden, z. B.: **'AdventureWorks'**.</span><span class="sxs-lookup"><span data-stu-id="59392-127">String values must be enclosed in single quotation marks, for example: **'AdventureWorks'**.</span></span> <span data-ttu-id="59392-128">Für einige Eigenschaften sind nicht alle Operatoren verfügbar.</span><span class="sxs-lookup"><span data-stu-id="59392-128">Not all operators are available for some properties.</span></span>  
  
## <a name="group-clauses"></a><span data-ttu-id="59392-129">Klauseln gruppieren</span><span class="sxs-lookup"><span data-stu-id="59392-129">Group Clauses</span></span>  
 <span data-ttu-id="59392-130">Klauseln können gruppiert werden, sodass sie vom Rest der Abfrage getrennt als einzelne Einheit ausgeführt werden. Dies ist mit Klammern um einen Ausdruck in einer mathematischen Gleichung oder einer Logikaussage vergleichbar.</span><span class="sxs-lookup"><span data-stu-id="59392-130">Clauses can be grouped to operate as a single unit separate from the rest of the query, just like putting parentheses around an expression in a mathematical equation or logic statement.</span></span> <span data-ttu-id="59392-131">Das Gruppieren von Klauseln ist beim Erstellen von komplexen Abfragen hilfreich.</span><span class="sxs-lookup"><span data-stu-id="59392-131">Grouping clauses is useful when you are building complex queries.</span></span>  
  
 <span data-ttu-id="59392-132">**So gruppieren Sie Klauseln**</span><span class="sxs-lookup"><span data-stu-id="59392-132">**To group clauses**</span></span>  
  
-   <span data-ttu-id="59392-133">Drücken Sie UMSCHALT oder STRG, und klicken Sie dann auf zwei oder mehr Klauseln, um einen Bereich auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="59392-133">Press the SHIFT or CTRL keys, and then click two or more clauses to select a range.</span></span> <span data-ttu-id="59392-134">Klicken Sie mit der rechten Maustaste auf den ausgewählten Bereich, und klicken Sie anschließend auf **Klauseln gruppieren**.</span><span class="sxs-lookup"><span data-stu-id="59392-134">Right-click the selected area, and then click **Group Clauses**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59392-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="59392-135">See Also</span></span>  
 [<span data-ttu-id="59392-136">Verwalten von Servern mit der richtlinienbasierten Verwaltung</span><span class="sxs-lookup"><span data-stu-id="59392-136">Administer Servers by Using Policy-Based Management</span></span>](administer-servers-by-using-policy-based-management.md)  
  
  
