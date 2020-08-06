---
title: DataReader-Ziel | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.datareaderdest.f1
helpviewer_keywords:
- DataReader destination
- destinations [Integration Services], DataReader
ms.assetid: 56fcc4bf-c901-42c3-a71d-110039293431
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 40cfe5d99c33eb19d415f204173005a64bde7855
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726142"
---
# <a name="datareader-destination"></a><span data-ttu-id="07a50-102">DataReader-Ziel</span><span class="sxs-lookup"><span data-stu-id="07a50-102">DataReader Destination</span></span>
  <span data-ttu-id="07a50-103">Das DataReader-Ziel macht die Daten in einem Datenfluss mithilfe der `DataReader`-Schnittstelle von ADO.NET verfügbar.</span><span class="sxs-lookup"><span data-stu-id="07a50-103">The DataReader destination exposes the data in a data flow by using the ADO.NET `DataReader` interface.</span></span> <span data-ttu-id="07a50-104">Die Daten können dann von anderen Anwendungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="07a50-104">The data can then be consumed by other applications.</span></span> <span data-ttu-id="07a50-105">Beispielsweise können Sie die Datenquelle eines [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]-Berichts so konfigurieren, dass das Ergebnis der Ausführung eines [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Pakets verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="07a50-105">For example, you can configure the data source of a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report to use the result of running a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package.</span></span> <span data-ttu-id="07a50-106">Dazu erstellen Sie einen Datenfluss, der das DataReader-Ziel implementiert.</span><span class="sxs-lookup"><span data-stu-id="07a50-106">To do this, you create a data flow that implements the DataReader destination.</span></span>  
  
 <span data-ttu-id="07a50-107">Informationen zum programmgesteuerten Zugriff auf Werte im DataReader-Ziel und zum programmgesteuerten Lesen dieser Werte finden Sie unter [Laden der Ausgabe eines lokalen Pakets](../run-manage-packages-programmatically/loading-the-output-of-a-local-package.md).</span><span class="sxs-lookup"><span data-stu-id="07a50-107">For information about accessing and reading values in the DataReader destination programmatically, see [Loading the Output of a Local Package](../run-manage-packages-programmatically/loading-the-output-of-a-local-package.md).</span></span>  
  
## <a name="configuration-of-the-datareader-destination"></a><span data-ttu-id="07a50-108">Konfiguration des DataReader-Ziel</span><span class="sxs-lookup"><span data-stu-id="07a50-108">Configuration of the DataReader Destination</span></span>  
 <span data-ttu-id="07a50-109">Sie können einen Timeoutwert für das DataReader-Ziel angeben und konfigurieren, ob das Ziel einen Fehler erzeugen soll, wenn ein Timeout auftritt.</span><span class="sxs-lookup"><span data-stu-id="07a50-109">You can specify a time-out value for the DataReader destination and indicate whether the destination should fail if a time-out occurs.</span></span> <span data-ttu-id="07a50-110">Ein Timeout tritt auf, wenn die Anwendung nicht innerhalb der angegebenen Zeit Daten anfordert.</span><span class="sxs-lookup"><span data-stu-id="07a50-110">A time-out occurs if the application does not ask for data within the specified time.</span></span>  
  
 <span data-ttu-id="07a50-111">Das DataReader-Ziel hat eine Eingabe.</span><span class="sxs-lookup"><span data-stu-id="07a50-111">The DataReader destination has one input.</span></span> <span data-ttu-id="07a50-112">Eine Fehlerausgabe wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="07a50-112">It does not support an error output.</span></span>  
  
 <span data-ttu-id="07a50-113">Sie können Eigenschaften mit dem [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="07a50-113">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="07a50-114">Klicken Sie auf eines der folgenden Themen, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im Dialogfeld **Erweiterter Editor** oder programmgesteuert festlegen können:</span><span class="sxs-lookup"><span data-stu-id="07a50-114">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="07a50-115">Common Properties</span><span class="sxs-lookup"><span data-stu-id="07a50-115">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="07a50-116">Benutzerdefinierte Eigenschaften des DataReader-Ziels</span><span class="sxs-lookup"><span data-stu-id="07a50-116">DataReader Destination Custom Properties</span></span>](datareader-destination-custom-properties.md)  
  
 <span data-ttu-id="07a50-117">Weitere Informationen zum Festlegen der Eigenschaften finden Sie unter [Festlegen der Eigenschaften einer Datenflusskomponente](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="07a50-117">For more information about how to set properties, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
  
