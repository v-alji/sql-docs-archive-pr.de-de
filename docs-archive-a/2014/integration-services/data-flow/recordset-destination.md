---
title: Recordsetziel | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.recordsetdest.f1
helpviewer_keywords:
- Recordset destination
- ADO recordsets [Integration Services]
- destinations [Integration Services], Recordset
- in-memory ADO recordsets [Integration Services]
ms.assetid: be973cf1-c4ff-49f8-987e-314c08ef98e4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c1acc29c904e9020721e8ac62dff09a8ec29a392
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615456"
---
# <a name="recordset-destination"></a><span data-ttu-id="a8f7f-102">Recordsetziel</span><span class="sxs-lookup"><span data-stu-id="a8f7f-102">Recordset Destination</span></span>
  <span data-ttu-id="a8f7f-103">Das Recordsetziel erstellt ein ADO-Recordset im Arbeitsspeicher und füllt es auf.</span><span class="sxs-lookup"><span data-stu-id="a8f7f-103">The Recordset destination creates and populates an in-memory ADO recordset.</span></span> <span data-ttu-id="a8f7f-104">Die Form des Recordsets wird durch die Eingabe im Recordsetziel zur Entwurfszeit definiert.</span><span class="sxs-lookup"><span data-stu-id="a8f7f-104">The shape of the recordset is defined by the input to the Recordset destination at design time.</span></span>  
  
## <a name="configuration-of-the-recordset-destination"></a><span data-ttu-id="a8f7f-105">Konfiguration des Recordsetziels</span><span class="sxs-lookup"><span data-stu-id="a8f7f-105">Configuration of the Recordset Destination</span></span>  
 <span data-ttu-id="a8f7f-106">Zum Konfigurieren des Recordsetziels geben Sie die Variable an, die das ADO-Recordset speichert.</span><span class="sxs-lookup"><span data-stu-id="a8f7f-106">You configure the Recordset destination by specifying the variable that stores the ADO recordset.</span></span>  
  
 <span data-ttu-id="a8f7f-107">Zur Laufzeit wird ein ADO-Recordset in die Variable des Typs „Object“ geschrieben, die in der „VariableName“-Eigenschaft des „Recordset“-Ziels angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="a8f7f-107">At run time, an ADO recordset is written to the variable of type, Object, that is specified in the VariableName property of the Recordset destination.</span></span> <span data-ttu-id="a8f7f-108">Die Variable stellt dann das Recordset außerhalb des Datenflusses zur Verfügung, wo es von Skripts und sonstigen Paketelementen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="a8f7f-108">The variable then makes the Recordset available outside the data flow, where it can be used by scripts and other package elements.</span></span>  
  
 <span data-ttu-id="a8f7f-109">Diese Quelle hat nur eine Eingabe.</span><span class="sxs-lookup"><span data-stu-id="a8f7f-109">This source has one input.</span></span> <span data-ttu-id="a8f7f-110">Eine Fehlerausgabe wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a8f7f-110">It does not support an error output.</span></span>  
  
 <span data-ttu-id="a8f7f-111">Sie können Eigenschaften mit dem [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="a8f7f-111">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="a8f7f-112">Das Dialogfeld **Erweiterter Editor** enthält die Eigenschaften, die programmgesteuert festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="a8f7f-112">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="a8f7f-113">Klicken Sie auf eines der folgenden Themen, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im Dialogfeld **Erweiterter Editor** oder programmgesteuert festlegen können:</span><span class="sxs-lookup"><span data-stu-id="a8f7f-113">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="a8f7f-114">Common Properties</span><span class="sxs-lookup"><span data-stu-id="a8f7f-114">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="a8f7f-115">Benutzerdefinierte Eigenschaften des Recordsetziels</span><span class="sxs-lookup"><span data-stu-id="a8f7f-115">Recordset Destination Custom Properties</span></span>](recordset-destination-custom-properties.md)  
  
 <span data-ttu-id="a8f7f-116">Informationen zum Festlegen der Eigenschaften finden Sie unter [Festlegen der Eigenschaften einer Datenflusskomponente](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="a8f7f-116">For more information about how to set the properties, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="a8f7f-117">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="a8f7f-117">Related Tasks</span></span>  
 [<span data-ttu-id="a8f7f-118">Verwenden eines Recordsetziels</span><span class="sxs-lookup"><span data-stu-id="a8f7f-118">Use a Recordset Destination</span></span>](recordset-destination.md)  
  
  
