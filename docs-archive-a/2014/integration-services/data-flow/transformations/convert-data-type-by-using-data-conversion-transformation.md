---
title: Konvertieren von Daten in einen anderen Datentyp mithilfe der Transformation für Datenkonvertierung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- converting data types [Integration Services]
- Data Conversion transformation
- data types [Integration Services], converting
ms.assetid: 4aabbe4f-7666-4672-865a-9627bd25fbfd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 878741717c36c18e9a069c62e86be0148272239f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619240"
---
# <a name="convert-data-to-a-different-data-type-by-using-the-data-conversion-transformation"></a><span data-ttu-id="2ba97-102">Konvertieren von Daten in einen anderen Datentyp mithilfe der Transformation für Datenkonvertierung</span><span class="sxs-lookup"><span data-stu-id="2ba97-102">Convert Data to a Different Data Type by Using the Data Conversion Transformation</span></span>
  <span data-ttu-id="2ba97-103">Um eine Transformation für Datenkonvertierung hinzuzufügen und zu konfigurieren, muss das Paket bereits mindestens einen Datenflusstask und eine Quelle enthalten.</span><span class="sxs-lookup"><span data-stu-id="2ba97-103">To add and configure a Data Conversion transformation, the package must already include at least one Data Flow task and one source.</span></span>  
  
### <a name="to-convert-data-to-a-different-data-type"></a><span data-ttu-id="2ba97-104">So konvertieren Sie Daten in einen anderen Datentyp</span><span class="sxs-lookup"><span data-stu-id="2ba97-104">To convert data to a different data type</span></span>  
  
1.  <span data-ttu-id="2ba97-105">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] das [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]-Projekt mit dem gewünschten Paket.</span><span class="sxs-lookup"><span data-stu-id="2ba97-105">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="2ba97-106">Doppelklicken Sie im Projektmappen-Explorer auf das Paket, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="2ba97-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="2ba97-107">Klicken Sie auf die Registerkarte **Datenfluss** , und ziehen Sie dann aus dem Bereich **Toolbox**die Transformation für Datenkonvertierung auf die Entwurfsoberfläche.</span><span class="sxs-lookup"><span data-stu-id="2ba97-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the Data Conversion transformation to the design surface.</span></span>  
  
4.  <span data-ttu-id="2ba97-108">Verbinden Sie die Transformation für Datenkonvertierung mit dem Datenfluss, indem Sie einen Konnektor von der Quelle oder der vorherigen Transformation auf die Transformation für Datenkonvertierung ziehen.</span><span class="sxs-lookup"><span data-stu-id="2ba97-108">Connect the Data Conversion transformation to the data flow by dragging a connector from the source or the previous transformation to the Data Conversion transformation.</span></span>  
  
5.  <span data-ttu-id="2ba97-109">Doppelklicken Sie auf die Transformation für Datenkonvertierung.</span><span class="sxs-lookup"><span data-stu-id="2ba97-109">Double-click the Data Conversion transformation.</span></span>  
  
6.  <span data-ttu-id="2ba97-110">Aktivieren Sie im Dialogfeld **Transformations-Editor für Datenkonvertierung** in der Tabelle **Verfügbare Eingabespalten** das Kontrollkästchen neben den Spalten, deren Datentyp Sie konvertieren möchten.</span><span class="sxs-lookup"><span data-stu-id="2ba97-110">In the **Data ConversionTransformation Editor** dialog box, in the **Available Input Columns** table, select the check box next to the columns whose data type you want to convert.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2ba97-111">Für eine Eingabespalte können mehrere Datenkonvertierungen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="2ba97-111">You can apply multiple data conversions to an input column.</span></span>  
  
7.  <span data-ttu-id="2ba97-112">Optional können die Standardwerte in der **Ausgabealias** -Spalte geändert werden.</span><span class="sxs-lookup"><span data-stu-id="2ba97-112">Optionally, modify the default values in the **Output Alias** column.</span></span>  
  
8.  <span data-ttu-id="2ba97-113">Wählen Sie in der Liste **Datentyp** den neuen Datentyp für die Spalte aus.</span><span class="sxs-lookup"><span data-stu-id="2ba97-113">In the **Data Type** list, select the new data type for the column.</span></span> <span data-ttu-id="2ba97-114">Der Standarddatentyp ist der Datentyp der Eingabespalte.</span><span class="sxs-lookup"><span data-stu-id="2ba97-114">The default data type is the data type of the input column.</span></span>  
  
9. <span data-ttu-id="2ba97-115">Aktualisieren Sie optional in Abhängigkeit vom ausgewählten Datentyp die Werte in den Spalten **Länge**, **Genauigkeit**, **Dezimalstellen**und **Codepage** .</span><span class="sxs-lookup"><span data-stu-id="2ba97-115">Optionally, depending on the selected data type, update the values in the **Length**, the **Precision**, the **Scale**, and the **Code Page** columns.</span></span>  
  
10. <span data-ttu-id="2ba97-116">Um die Fehlerausgabe zu konfigurieren, klicken Sie auf **Fehlerausgabe konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="2ba97-116">To configure the error output, click **Configure Error Output**.</span></span> <span data-ttu-id="2ba97-117">Weitere Informationen finden Sie unter [Konfigurieren einer Fehlerausgabe in einer Datenflusskomponente](../../configure-an-error-output-in-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="2ba97-117">For more information, see [Configure an Error Output in a Data Flow Component](../../configure-an-error-output-in-a-data-flow-component.md).</span></span>  
  
11. <span data-ttu-id="2ba97-118">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="2ba97-118">Click **OK**.</span></span>  
  
12. <span data-ttu-id="2ba97-119">Klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern** , um das aktualisierte Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="2ba97-119">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ba97-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2ba97-120">See Also</span></span>  
 <span data-ttu-id="2ba97-121">[Data Conversion Transformation](data-conversion-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="2ba97-121">[Data Conversion Transformation](data-conversion-transformation.md) </span></span>  
 <span data-ttu-id="2ba97-122">[SQL Server Integration Services-Transformationen](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="2ba97-122">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 <span data-ttu-id="2ba97-123">[SQL Server Integration Services-Pfade](../integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="2ba97-123">[Integration Services Paths](../integration-services-paths.md) </span></span>  
 <span data-ttu-id="2ba97-124">[SQL Server Integration Services-Datentypen](../integration-services-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="2ba97-124">[Integration Services Data Types](../integration-services-data-types.md) </span></span>  
 [<span data-ttu-id="2ba97-125">Datenflusstask</span><span class="sxs-lookup"><span data-stu-id="2ba97-125">Data Flow Task</span></span>](../../control-flow/data-flow-task.md)  
  
  
