---
title: Transformations-Editor für Union all | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.unionalltransformation.f1
helpviewer_keywords:
- Union All Transformation Editor
ms.assetid: 32fbc1c1-da83-4684-9479-31fc3e2df98c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a7e84c106767aa897b2e419b51ca5b5c538501cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609943"
---
# <a name="union-all-transformation-editor"></a><span data-ttu-id="369c1-102">Transformations-Editor für UNION ALL</span><span class="sxs-lookup"><span data-stu-id="369c1-102">Union All Transformation Editor</span></span>
  <span data-ttu-id="369c1-103">Mithilfe des Dialogfelds **Transformations-Editor für UNION ALL** können Sie mehrere Eingaberowsets zu einem einzigen Ausgaberowset zusammenführen.</span><span class="sxs-lookup"><span data-stu-id="369c1-103">Use the **Union All Transformation Editor** dialog box to merge several input rowsets into a single output rowset.</span></span> <span data-ttu-id="369c1-104">Durch das Einschließen der Transformation für UNION ALL in einen Datenfluss können Sie Daten aus mehreren Datenflüssen zusammenführen, komplexe Datasets durch Verschachteln der Transformationen für UNION ALL erstellen und Zeilen erneut zusammenführen, nachdem Sie Fehler in den Daten korrigiert haben.</span><span class="sxs-lookup"><span data-stu-id="369c1-104">By including the Union All transformation in a data flow, you can merge data from multiple data flows, create complex datasets by nesting Union All transformations, and re-merge rows after you correct errors in the data.</span></span>  
  
 <span data-ttu-id="369c1-105">Weitere Informationen zur Transformation für UNION ALL finden Sie unter [Union All Transformation](data-flow/transformations/union-all-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="369c1-105">To learn more about the Union All transformation, see [Union All Transformation](data-flow/transformations/union-all-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="369c1-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="369c1-106">Options</span></span>  
 <span data-ttu-id="369c1-107">**Name der Ausgabespalte**</span><span class="sxs-lookup"><span data-stu-id="369c1-107">**Output Column Name**</span></span>  
 <span data-ttu-id="369c1-108">Geben Sie einen Alias für jede Spalte ein.</span><span class="sxs-lookup"><span data-stu-id="369c1-108">Type an alias for each column.</span></span> <span data-ttu-id="369c1-109">Standardmäßig wird der Name der Eingabespalte von der ersten (Referenz-)Eingabe verwendet. Sie können jedoch auch einen beschreibenden Namen angeben, sofern dieser eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="369c1-109">The default is the name of the input column from the first (reference) input; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="369c1-110">**Eingabe 1 für UNION ALL**</span><span class="sxs-lookup"><span data-stu-id="369c1-110">**Union All Input 1**</span></span>  
 <span data-ttu-id="369c1-111">Wählen Sie eine Eingabespalte aus der Liste der verfügbaren Eingabespalten in der ersten (Referenz-)Eingabe aus.</span><span class="sxs-lookup"><span data-stu-id="369c1-111">Select from the list of available input columns in the first (reference) input.</span></span> <span data-ttu-id="369c1-112">Die Metadaten der zugeordneten Spalten müssen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="369c1-112">The metadata of mapped columns must match.</span></span>  
  
 <span data-ttu-id="369c1-113">**Eingabe n für UNION ALL**</span><span class="sxs-lookup"><span data-stu-id="369c1-113">**Union All Input n**</span></span>  
 <span data-ttu-id="369c1-114">Wählen Sie eine Eingabespalte aus der Liste der verfügbaren Eingabespalten in den folgenden Eingaben aus.</span><span class="sxs-lookup"><span data-stu-id="369c1-114">Select from the list of available input columns in the second and additional inputs.</span></span> <span data-ttu-id="369c1-115">Die Metadaten der zugeordneten Spalten müssen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="369c1-115">The metadata of mapped columns must match.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="369c1-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="369c1-116">See Also</span></span>  
 <span data-ttu-id="369c1-117">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="369c1-117">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="369c1-118">[Zusammenführen von Daten mithilfe der Transformation für Union all](data-flow/transformations/merge-data-by-using-the-union-all-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="369c1-118">[Merge Data by Using the Union All Transformation](data-flow/transformations/merge-data-by-using-the-union-all-transformation.md) </span></span>  
 <span data-ttu-id="369c1-119">[Transformation für Zusammenführen](data-flow/transformations/merge-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="369c1-119">[Merge Transformation](data-flow/transformations/merge-transformation.md) </span></span>  
 [<span data-ttu-id="369c1-120">Transformation für Zusammenführungsjoin</span><span class="sxs-lookup"><span data-stu-id="369c1-120">Merge Join Transformation</span></span>](data-flow/transformations/merge-join-transformation.md)  
  
  
