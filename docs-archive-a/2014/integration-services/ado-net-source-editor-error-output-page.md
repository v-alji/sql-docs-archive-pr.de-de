---
title: ADO NET-Quellen-Editor (Seite Fehlerausgabe) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.adonetsource.erroroutput.f1
ms.assetid: 4dd9d129-a95c-4d3a-bbbf-e84a39089950
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b9ee480caa8764d70b52b25a416f200f353d30c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724066"
---
# <a name="ado-net-source-editor-error-output-page"></a><span data-ttu-id="2c0a7-102">ADO.NET-Quellen-Editor (Seite 'Fehlerausgabe')</span><span class="sxs-lookup"><span data-stu-id="2c0a7-102">ADO NET Source Editor (Error Output Page)</span></span>
  <span data-ttu-id="2c0a7-103">Mithilfe der Seite **Fehlerausgabe** des Dialogfelds **ADO.NET-Quellen-Editor** können Sie Fehlerbehandlungsoptionen auswählen und Eigenschaften für Fehlerausgabespalten festlegen.</span><span class="sxs-lookup"><span data-stu-id="2c0a7-103">Use the **Error Output** page of the **ADO NET Source Editor** dialog box to select error handling options and to set properties on error output columns.</span></span>  
  
 <span data-ttu-id="2c0a7-104">Weitere Informationen zur ADO NET-Quelle finden Sie unter [ADO NET Source](data-flow/ado-net-source.md).</span><span class="sxs-lookup"><span data-stu-id="2c0a7-104">To learn more about the ADO NET source, see [ADO NET Source](data-flow/ado-net-source.md).</span></span>  
  
 <span data-ttu-id="2c0a7-105">**So öffnen Sie die Seite "Fehlerausgabe"**</span><span class="sxs-lookup"><span data-stu-id="2c0a7-105">**To open the Error Output page**</span></span>  
  
1.  <span data-ttu-id="2c0a7-106">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Paket, das ADO.NET als Quelle hat.</span><span class="sxs-lookup"><span data-stu-id="2c0a7-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that has the ADO NET source.</span></span>  
  
2.  <span data-ttu-id="2c0a7-107">Doppelklicken Sie auf der Registerkarte **Datenfluss** auf die ADO.NET-Quelle.</span><span class="sxs-lookup"><span data-stu-id="2c0a7-107">On the **Data Flow** tab, double-click the ADO NET source.</span></span>  
  
3.  <span data-ttu-id="2c0a7-108">Klicken Sie im **ADO.NET-Quellen-Editor**auf **Fehlerausgabe**.</span><span class="sxs-lookup"><span data-stu-id="2c0a7-108">In the **ADO NET Source Editor**, click **Error Output**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="2c0a7-109">Tastatur</span><span class="sxs-lookup"><span data-stu-id="2c0a7-109">Options</span></span>  
 <span data-ttu-id="2c0a7-110">**Eingabe/Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="2c0a7-110">**Input/Output**</span></span>  
 <span data-ttu-id="2c0a7-111">Zeigt den Namen der Datenquelle an.</span><span class="sxs-lookup"><span data-stu-id="2c0a7-111">View the name of the data source.</span></span>  
  
 <span data-ttu-id="2c0a7-112">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="2c0a7-112">**Column**</span></span>  
 <span data-ttu-id="2c0a7-113">Zeigt die externen (Quell-)Spalten an, die im Dialogfeld **ADO.NET-Quellen-Editor** auf der Seite **Verbindungs-Manager** ausgewählt wurden.</span><span class="sxs-lookup"><span data-stu-id="2c0a7-113">View the external (source) columns that you selected on the **Connection Manager** page of the **ADO NET Source Editor** dialog box.</span></span>  
  
 <span data-ttu-id="2c0a7-114">**Fehler**</span><span class="sxs-lookup"><span data-stu-id="2c0a7-114">**Error**</span></span>  
 <span data-ttu-id="2c0a7-115">Gibt an, was bei Auftreten eines Fehlers geschehen soll: den Fehler ignorieren, die Zeile umleiten oder die Komponente mit einem Fehler abbrechen.</span><span class="sxs-lookup"><span data-stu-id="2c0a7-115">Specify what should happen when an error occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="2c0a7-116">**Verwandte Themen:** [Fehlerbehandlung in Daten](data-flow/error-handling-in-data.md)</span><span class="sxs-lookup"><span data-stu-id="2c0a7-116">**Related Topics:** [Error Handling in Data](data-flow/error-handling-in-data.md)</span></span>  
  
 <span data-ttu-id="2c0a7-117">**Abschneiden**</span><span class="sxs-lookup"><span data-stu-id="2c0a7-117">**Truncation**</span></span>  
 <span data-ttu-id="2c0a7-118">Gibt an, was im Falle einer Kürzung geschehen soll: den Fehler ignorieren, die Zeile umleiten oder die Komponente mit einem Fehler abbrechen.</span><span class="sxs-lookup"><span data-stu-id="2c0a7-118">Specify what should happen when a truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="2c0a7-119">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="2c0a7-119">**Description**</span></span>  
 <span data-ttu-id="2c0a7-120">Zeigt die Beschreibung des Fehlers an.</span><span class="sxs-lookup"><span data-stu-id="2c0a7-120">View the description of the error.</span></span>  
  
 <span data-ttu-id="2c0a7-121">**Diesen Wert für ausgewählte Zellen festlegen**</span><span class="sxs-lookup"><span data-stu-id="2c0a7-121">**Set this value to selected cells**</span></span>  
 <span data-ttu-id="2c0a7-122">Gibt an, was im Falle eines Fehlers oder einer Kürzung mit den ausgewählten Zellen geschehen soll: den Fehler ignorieren, die Zeile umleiten oder die Komponente mit einem Fehler abbrechen.</span><span class="sxs-lookup"><span data-stu-id="2c0a7-122">Specify what should happen to all the selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="2c0a7-123">**Anwenden**</span><span class="sxs-lookup"><span data-stu-id="2c0a7-123">**Apply**</span></span>  
 <span data-ttu-id="2c0a7-124">Wendet die Fehlerbehandlungsoption auf die ausgewählten Zellen an.</span><span class="sxs-lookup"><span data-stu-id="2c0a7-124">Apply the error handling option to the selected cells.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c0a7-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2c0a7-125">See Also</span></span>  
 <span data-ttu-id="2c0a7-126">[ADO NET-Quellen-Editor &#40;Seite "Verbindungs-Manager"&#41;](../../2014/integration-services/ado-net-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="2c0a7-126">[ADO NET Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/ado-net-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="2c0a7-127">[ADO.net-Quellen-Editor &#40;Seite "Spalten"&#41;](../../2014/integration-services/ado-net-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="2c0a7-127">[ADO NET Source Editor &#40;Columns Page&#41;](../../2014/integration-services/ado-net-source-editor-columns-page.md) </span></span>  
 [<span data-ttu-id="2c0a7-128">ADO.NET-Verbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="2c0a7-128">ADO.NET Connection Manager</span></span>](connection-manager/ado-net-connection-manager.md)  
  
  
