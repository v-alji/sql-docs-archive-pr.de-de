---
title: Hinzufügen oder Löschen einer Komponente im Datenfluss | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- adding components
- components [Integration Services], data flow
ms.assetid: d99124f9-0994-4f40-a48e-fdca6a4383e7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a2f041258d2b66e7b8da540a842848ebf70f4ed5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697034"
---
# <a name="add-or-delete-a-component-in-a-data-flow"></a><span data-ttu-id="88058-102">Hinzufügen oder Löschen einer Komponente im Datenfluss</span><span class="sxs-lookup"><span data-stu-id="88058-102">Add or Delete a Component in a Data Flow</span></span>
  <span data-ttu-id="88058-103">Bei Datenflusskomponenten handelt es sich um Quellen, Ziele und Transformationen in einem Datenfluss.</span><span class="sxs-lookup"><span data-stu-id="88058-103">Data flow components are sources, destinations, and transformations in a data flow.</span></span> <span data-ttu-id="88058-104">Bevor Sie einem Datenfluss Komponenten hinzufügen können, muss die Ablaufsteuerung im Paket einen Datenflusstask einschließen.</span><span class="sxs-lookup"><span data-stu-id="88058-104">Before you can add components to a data flow, the control flow in the package must include a Data Flow task.</span></span>  
  
 <span data-ttu-id="88058-105">Im Folgenden wird beschrieben, wie eine Komponente zum Datenfluss eines Pakets hinzugefügt oder in diesem gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="88058-105">The following procedures describe how to add or delete a component in the data flow of a package.</span></span>  
  
### <a name="to-add-a-component-to-a-data-flow"></a><span data-ttu-id="88058-106">So fügen Sie einem Datenfluss eine Komponente hinzu</span><span class="sxs-lookup"><span data-stu-id="88058-106">To add a component to a data flow</span></span>  
  
1.  <span data-ttu-id="88058-107">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] das [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Projekt mit dem gewünschten Paket.</span><span class="sxs-lookup"><span data-stu-id="88058-107">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="88058-108">Doppelklicken Sie im Projektmappen-Explorer auf das Paket, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="88058-108">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="88058-109">Klicken Sie auf die Registerkarte **Ablaufsteuerung** , und doppelklicken Sie dann auf den Datenflusstask, der den Datenfluss enthält, dem Sie eine Komponente hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="88058-109">Click the **Control Flow** tab, and then double-click the Data Flow task that contains the data flow to which you want to add a component.</span></span>  
  
4.  <span data-ttu-id="88058-110">Erweitern Sie in der Toolbox **Datenflussquellen**, **Datenflusstransformationen**oder **Datenflussziele**, und ziehen Sie ein Datenflusselement auf die Entwurfsoberfläche der Registerkarte **Datenfluss** .</span><span class="sxs-lookup"><span data-stu-id="88058-110">In the Toolbox, expand **Data Flow Sources**, **Data Flow Transformations**, or **Data Flow Destinations**, and then drag a data flow item to the design surface of the **Data Flow** tab.</span></span>  
  
5.  <span data-ttu-id="88058-111">Klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern** , um das aktualisierte Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="88058-111">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-delete-a-component-from-a-data-flow"></a><span data-ttu-id="88058-112">So löschen Sie eine Komponente aus einem Datenfluss</span><span class="sxs-lookup"><span data-stu-id="88058-112">To delete a component from a data flow</span></span>  
  
1.  <span data-ttu-id="88058-113">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] das [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Projekt mit dem gewünschten Paket.</span><span class="sxs-lookup"><span data-stu-id="88058-113">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="88058-114">Doppelklicken Sie im Projektmappen-Explorer auf das Paket, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="88058-114">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="88058-115">Klicken Sie auf die Registerkarte **Ablaufsteuerung** , und doppelklicken Sie dann auf den Datenflusstask, der den Datenfluss enthält, in dem Sie eine Komponente löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="88058-115">Click the **Control Flow** tab, and then double-click the Data Flow task that contains the data flow from which you want to delete a component.</span></span>  
  
4.  <span data-ttu-id="88058-116">Klicken Sie mit der rechten Maustaste auf die Datenflusskomponente, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="88058-116">Right-click the data flow component, and then click **Delete**.</span></span>  
  
5.  <span data-ttu-id="88058-117">Bestätigen Sie den Löschvorgang.</span><span class="sxs-lookup"><span data-stu-id="88058-117">Confirm the delete operation.</span></span>  
  
6.  <span data-ttu-id="88058-118">Klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern** , um das aktualisierte Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="88058-118">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88058-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="88058-119">See Also</span></span>  
 <span data-ttu-id="88058-120">[Verbinden von Komponenten in einem Datenfluss](data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="88058-120">[Connect Components in a Data Flow](data-flow.md) </span></span>  
 <span data-ttu-id="88058-121">[Konfigurieren einer Fehlerausgabe in einer Datenfluss Komponente](../configure-an-error-output-in-a-data-flow-component.md) </span><span class="sxs-lookup"><span data-stu-id="88058-121">[Configure an Error Output in a Data Flow Component](../configure-an-error-output-in-a-data-flow-component.md) </span></span>  
 [<span data-ttu-id="88058-122">Datenfluss</span><span class="sxs-lookup"><span data-stu-id="88058-122">Data Flow</span></span>](data-flow.md)  
  
  
