---
title: Spalten-Kopieren-Transformation | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.copycolumntrans.f1
helpviewer_keywords:
- columns [Integration Services], copying
- copying columns
- Copy Column transformation
ms.assetid: 1c72a313-9026-46bc-a57f-c6b3f47346f8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fd2745070a92ab71e89f3bfa9edd8673b676632b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619238"
---
# <a name="copy-column-transformation"></a><span data-ttu-id="b21e2-102">Spalten-Kopieren-Transformation</span><span class="sxs-lookup"><span data-stu-id="b21e2-102">Copy Column Transformation</span></span>
  <span data-ttu-id="b21e2-103">Die Transformation für das Kopieren von Spalten erstellt neue Spalten, indem Eingabespalten kopiert und der Transformationsausgabe die neuen Spalten hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="b21e2-103">The Copy Column transformation creates new columns by copying input columns and adding the new columns to the transformation output.</span></span> <span data-ttu-id="b21e2-104">Später können im Datenfluss verschiedene Transformationen auf die Spaltenkopien angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="b21e2-104">Later in the data flow, different transformations can be applied to the column copies.</span></span> <span data-ttu-id="b21e2-105">Beispielsweise können Sie mit der Transformation für das Kopieren von Spalten eine Kopie einer Spalte erstellen und anschließend mithilfe der Transformation zum Zuordnen der Zeichen die kopierten Daten in Großbuchstaben konvertieren. Sie könnten aber auch mithilfe der Transformation für das Aggregieren Aggregationen auf die neue Spalte anwenden.</span><span class="sxs-lookup"><span data-stu-id="b21e2-105">For example, you can use the Copy Column transformation to create a copy of a column and then convert the copied data to uppercase characters by using the Character Map transformation, or apply aggregations to the new column by using the Aggregate transformation.</span></span>  
  
## <a name="configuration-of-the-copy-column-transformation"></a><span data-ttu-id="b21e2-106">Konfiguration der Transformation für das Kopieren von Spalten</span><span class="sxs-lookup"><span data-stu-id="b21e2-106">Configuration of the Copy Column Transformation</span></span>  
 <span data-ttu-id="b21e2-107">Zum Konfigurieren der Transformation für das Kopieren von Spalten geben Sie die zu kopierenden Eingabespalten an.</span><span class="sxs-lookup"><span data-stu-id="b21e2-107">You configure the Copy Column transformation by specifying the input columns to copy.</span></span> <span data-ttu-id="b21e2-108">Sie können mehrere Kopien einer Spalte erstellen, oder Kopien mehrerer Spalten in einem Vorgang erstellen.</span><span class="sxs-lookup"><span data-stu-id="b21e2-108">You can create multiple copies of a column, or create copies of multiple columns in one operation.</span></span>  
  
 <span data-ttu-id="b21e2-109">Diese Transformation weist je eine Eingabe und eine Ausgabe auf.</span><span class="sxs-lookup"><span data-stu-id="b21e2-109">This transformation has one input and one output.</span></span> <span data-ttu-id="b21e2-110">Eine Fehlerausgabe wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b21e2-110">It does not support an error output.</span></span>  
  
 <span data-ttu-id="b21e2-111">Eigenschaften können Sie mit dem [!INCLUDE[ssIS](../../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="b21e2-111">You can set properties through the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="b21e2-112">Weitere Informationen zu den Eigenschaften, die Sie im Dialogfeld **Transformations-Editor für das Kopieren von Spalten** festlegen können, finden Sie unter [Copy Column Transformation Editor](../../copy-column-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="b21e2-112">For more information about the properties that you can set in the **Copy Column Transformation Editor** dialog box, see [Copy Column Transformation Editor](../../copy-column-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="b21e2-113">Das Dialogfeld **Erweiterter Editor** enthält die Eigenschaften, die programmgesteuert festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="b21e2-113">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="b21e2-114">Klicken Sie auf eines der folgenden Themen, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im Dialogfeld **Erweiterter Editor** oder programmgesteuert festlegen können:</span><span class="sxs-lookup"><span data-stu-id="b21e2-114">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="b21e2-115">Common Properties</span><span class="sxs-lookup"><span data-stu-id="b21e2-115">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="b21e2-116">Benutzerdefinierte Eigenschaften von Transformationen</span><span class="sxs-lookup"><span data-stu-id="b21e2-116">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
 <span data-ttu-id="b21e2-117">Weitere Informationen zum Festlegen der Eigenschaften finden Sie unter [Festlegen der Eigenschaften einer Datenflusskomponente](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="b21e2-117">For more information about how to set properties, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b21e2-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b21e2-118">See Also</span></span>  
 <span data-ttu-id="b21e2-119">[Datenfluss](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="b21e2-119">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="b21e2-120">SQL Server Integration Services-Transformationen</span><span class="sxs-lookup"><span data-stu-id="b21e2-120">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
