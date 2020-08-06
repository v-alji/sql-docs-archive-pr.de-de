---
title: ADO NET-Ziel-Editor (Seite Fehlerausgabe) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.adonetdest.erroroutput.f1
ms.assetid: 1a56c3cf-fb6a-416d-a62c-bb19fe441ae5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b9cfd69d3adec2aa617f5e9d3add35a1a6923804
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618235"
---
# <a name="ado-net-destination-editor-error-output-page"></a><span data-ttu-id="75bf5-102">ADO.NET-Ziel-Editor (Seite 'Fehlerausgabe')</span><span class="sxs-lookup"><span data-stu-id="75bf5-102">ADO NET Destination Editor (Error Output Page)</span></span>
  <span data-ttu-id="75bf5-103">Auf der Seite **Fehlerausgabe** des Dialogfelds **ADO.NET-Ziel-Editor** geben Sie Optionen für die Fehlerbehandlung an.</span><span class="sxs-lookup"><span data-stu-id="75bf5-103">Use the **Error Output** page of the **ADO NET Destination Editor** dialog box to specify error handling options.</span></span>  
  
 <span data-ttu-id="75bf5-104">Weitere Informationen zum ADO NET-Ziel finden Sie unter [ADO NET Destination](data-flow/ado-net-destination.md).</span><span class="sxs-lookup"><span data-stu-id="75bf5-104">To learn more about the ADO NET destination, see [ADO NET Destination](data-flow/ado-net-destination.md).</span></span>  
  
 <span data-ttu-id="75bf5-105">**So öffnen Sie die Seite "Fehlerausgabe"**</span><span class="sxs-lookup"><span data-stu-id="75bf5-105">**To open the Error Output page**</span></span>  
  
1.  <span data-ttu-id="75bf5-106">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Paket, das ADO.NET als Ziel hat.</span><span class="sxs-lookup"><span data-stu-id="75bf5-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that has the ADO NET destination.</span></span>  
  
2.  <span data-ttu-id="75bf5-107">Doppelklicken Sie auf der Registerkarte **Datenfluss** auf das ADO NET-Ziel.</span><span class="sxs-lookup"><span data-stu-id="75bf5-107">On the **Data Flow** tab, double-click the ADO NET destination.</span></span>  
  
3.  <span data-ttu-id="75bf5-108">Klicken Sie im **ADO.NET-Ziel-Editor**auf **Fehlerausgabe**.</span><span class="sxs-lookup"><span data-stu-id="75bf5-108">In the **ADO NET Destination Editor**, click **Error Output**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="75bf5-109">Tastatur</span><span class="sxs-lookup"><span data-stu-id="75bf5-109">Options</span></span>  
 <span data-ttu-id="75bf5-110">**Eingabe oder Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="75bf5-110">**Input or Output**</span></span>  
 <span data-ttu-id="75bf5-111">Zeigt den Namen der Eingabe an.</span><span class="sxs-lookup"><span data-stu-id="75bf5-111">View the name of the input.</span></span>  
  
 <span data-ttu-id="75bf5-112">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="75bf5-112">**Column**</span></span>  
 <span data-ttu-id="75bf5-113">Wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="75bf5-113">Not used.</span></span>  
  
 <span data-ttu-id="75bf5-114">**Fehler**</span><span class="sxs-lookup"><span data-stu-id="75bf5-114">**Error**</span></span>  
 <span data-ttu-id="75bf5-115">Gibt an, was bei Auftreten eines Fehlers geschehen soll: den Fehler ignorieren, die Zeile umleiten oder die Komponente mit einem Fehler abbrechen.</span><span class="sxs-lookup"><span data-stu-id="75bf5-115">Specify what should happen when an error occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="75bf5-116">**Verwandte Themen:** [Fehlerbehandlung in Daten](data-flow/error-handling-in-data.md)</span><span class="sxs-lookup"><span data-stu-id="75bf5-116">**Related Topics:** [Error Handling in Data](data-flow/error-handling-in-data.md)</span></span>  
  
 <span data-ttu-id="75bf5-117">**Abschneiden**</span><span class="sxs-lookup"><span data-stu-id="75bf5-117">**Truncation**</span></span>  
 <span data-ttu-id="75bf5-118">Wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="75bf5-118">Not used.</span></span>  
  
 <span data-ttu-id="75bf5-119">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="75bf5-119">**Description**</span></span>  
 <span data-ttu-id="75bf5-120">Zeigt die Beschreibung des Vorgangs an.</span><span class="sxs-lookup"><span data-stu-id="75bf5-120">View the description of the operation.</span></span>  
  
 <span data-ttu-id="75bf5-121">**Diesen Wert für ausgewählte Zellen festlegen**</span><span class="sxs-lookup"><span data-stu-id="75bf5-121">**Set this value to selected cells**</span></span>  
 <span data-ttu-id="75bf5-122">Gibt an, was im Falle eines Fehlers oder einer Kürzung mit den ausgewählten Zellen geschehen soll: den Fehler ignorieren, die Zeile umleiten oder die Komponente mit einem Fehler abbrechen.</span><span class="sxs-lookup"><span data-stu-id="75bf5-122">Specify what should happen to all the selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="75bf5-123">**Anwenden**</span><span class="sxs-lookup"><span data-stu-id="75bf5-123">**Apply**</span></span>  
 <span data-ttu-id="75bf5-124">Wendet die Fehlerbehandlungsoption auf die ausgewählten Zellen an.</span><span class="sxs-lookup"><span data-stu-id="75bf5-124">Apply the error handling option to the selected cells.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75bf5-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="75bf5-125">See Also</span></span>  
 <span data-ttu-id="75bf5-126">[Der ADO.NET-Ziel-Editor &#40;Seite "Verbindungs-Manager"&#41;](../../2014/integration-services/ado-net-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="75bf5-126">[ADO NET Destination Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/ado-net-destination-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="75bf5-127">ADO.NET-Ziel-Editor &#40;Seite „Zuordnungen“&#41;</span><span class="sxs-lookup"><span data-stu-id="75bf5-127">ADO NET Destination Editor &#40;Mappings Page&#41;</span></span>](../../2014/integration-services/ado-net-destination-editor-mappings-page.md)  
  
  
