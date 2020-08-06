---
title: Transformation für Multicast | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.multicasttrans.f1
helpviewer_keywords:
- multiple outputs
- Multicast transformation
- datasets [Integration Services], multiple outputs
- multiple transformations
ms.assetid: 32194784-1684-40cd-9f91-1aba4d8360d3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7b5c0a38c966c89f426a213f302b45c390b77cfe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727106"
---
# <a name="multicast-transformation"></a><span data-ttu-id="4ce59-102">Transformation für Multicast</span><span class="sxs-lookup"><span data-stu-id="4ce59-102">Multicast Transformation</span></span>
  <span data-ttu-id="4ce59-103">Die Multicasttransformation verteilt ihre Eingabe an mindestens eine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="4ce59-103">The Multicast transformation distributes its input to one or more outputs.</span></span> <span data-ttu-id="4ce59-104">Diese Transformation ist mit der Transformation für bedingtes Teilen vergleichbar.</span><span class="sxs-lookup"><span data-stu-id="4ce59-104">This transformation is similar to the Conditional Split transformation.</span></span> <span data-ttu-id="4ce59-105">Beide Transformationen leiten eine Ausgabe an mehrere Ausgaben weiter.</span><span class="sxs-lookup"><span data-stu-id="4ce59-105">Both transformations direct an input to multiple outputs.</span></span> <span data-ttu-id="4ce59-106">Der Unterschied zwischen den beiden Transformationen besteht darin, dass die Multicasttransformation jede Zeile an jede Ausgabe weiterleitet, während die Transformation für bedingtes Teilen eine Zeile an eine einzelne Ausgabe weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="4ce59-106">The difference between the two is that the Multicast transformation directs every row to every output, and the Conditional Split directs a row to a single output.</span></span> <span data-ttu-id="4ce59-107">Weitere Informationen finden Sie unter [Conditional Split Transformation](conditional-split-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="4ce59-107">For more information, see [Conditional Split Transformation](conditional-split-transformation.md).</span></span>  
  
 <span data-ttu-id="4ce59-108">Zum Konfigurieren der Multicasttransformation fügen Sie Ausgaben hinzu.</span><span class="sxs-lookup"><span data-stu-id="4ce59-108">You configure the Multicast transformation by adding outputs.</span></span>  
  
 <span data-ttu-id="4ce59-109">Mithilfe der Multicasttransformation kann ein Paket logische Kopien von Daten erstellen.</span><span class="sxs-lookup"><span data-stu-id="4ce59-109">Using the Multicast transformation, a package can create logical copies of data.</span></span> <span data-ttu-id="4ce59-110">Dies ist hilfreich, wenn das Paket mehrere Transformationen auf dieselben Daten anwenden muss.</span><span class="sxs-lookup"><span data-stu-id="4ce59-110">This capability is useful when the package needs to apply multiple sets of transformations to the same data.</span></span> <span data-ttu-id="4ce59-111">Angenommen, eine Kopie der Daten wird aggregiert und nur die Zusammenfassungsinformationen werden in das Ziel geladen, während die andere Kopie der Daten mit Nachschlagewerten und abgeleiteten Spalten erweitert wird, bevor sie in das Ziel geladen wird.</span><span class="sxs-lookup"><span data-stu-id="4ce59-111">For example, one copy of the data is aggregated and only the summary information is loaded into its destination, while another copy of the data is extended with lookup values and derived columns before it is loaded into its destination.</span></span>  
  
 <span data-ttu-id="4ce59-112">Diese Transformation weist eine Eingabe und mehrere Ausgaben auf.</span><span class="sxs-lookup"><span data-stu-id="4ce59-112">This transformation has one input and multiple outputs.</span></span> <span data-ttu-id="4ce59-113">Eine Fehlerausgabe wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4ce59-113">It does not support an error output.</span></span>  
  
## <a name="configuration-of-the-multicast-transformation"></a><span data-ttu-id="4ce59-114">Konfiguration der Multicasttransformation</span><span class="sxs-lookup"><span data-stu-id="4ce59-114">Configuration of the Multicast Transformation</span></span>  
 <span data-ttu-id="4ce59-115">Sie können Eigenschaften mit dem [!INCLUDE[ssIS](../../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="4ce59-115">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="4ce59-116">Weitere Informationen zu den Eigenschaften, die Sie im Dialogfeld **Transformations-Editor für Multicast** festlegen können, finden Sie unter [Multicast Transformation Editor](../../multicast-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="4ce59-116">For information about the properties that you can set in the **Multicast Transformation Editor** dialog box, see [Multicast Transformation Editor](../../multicast-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="4ce59-117">Weitere Informationen zu den Eigenschaften, die Sie programmgesteuert festlegen können, finden Sie unter [Common Properties](../../common-properties.md).</span><span class="sxs-lookup"><span data-stu-id="4ce59-117">For information about the properties that you can set programmatically, see [Common Properties](../../common-properties.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="4ce59-118">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="4ce59-118">Related Tasks</span></span>  
 <span data-ttu-id="4ce59-119">Informationen zum Festlegen der Eigenschaften dieser Komponente finden Sie unter [Festlegen der Eigenschaften einer Datenflusskomponente](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="4ce59-119">For information about how to set properties of this component, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ce59-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4ce59-120">See Also</span></span>  
 <span data-ttu-id="4ce59-121">[Datenfluss](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="4ce59-121">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="4ce59-122">SQL Server Integration Services-Transformationen</span><span class="sxs-lookup"><span data-stu-id="4ce59-122">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
