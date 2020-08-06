---
title: Fehlerausgabe konfigurieren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.configureerroroutput.f1
ms.assetid: 5f8da390-fab5-44f8-b268-d8fa313ce4b9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: de1a5908c6075438599f4108e9780f5591b042c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619277"
---
# <a name="configure-error-output"></a><span data-ttu-id="2de6b-102">Fehlerausgabe konfigurieren</span><span class="sxs-lookup"><span data-stu-id="2de6b-102">Configure Error Output</span></span>
  <span data-ttu-id="2de6b-103">Mithilfe des Dialogfelds **Fehlerausgabe konfigurieren** können Sie die Fehlerbehandlungsoptionen für Datenflusstransformationen konfigurieren, die eine Fehlerausgabe unterstützen.</span><span class="sxs-lookup"><span data-stu-id="2de6b-103">Use the **Configure Error Output** dialog box to configure error handling options for data flow transformations that support an error output.</span></span>  
  
 <span data-ttu-id="2de6b-104">Weitere Informationen zum Arbeiten mit Fehlerausgaben finden Sie unter [Fehlerbehandlung in Daten](data-flow/error-handling-in-data.md).</span><span class="sxs-lookup"><span data-stu-id="2de6b-104">To learn more about working with error outputs, see [Error Handling in Data](data-flow/error-handling-in-data.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="2de6b-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="2de6b-105">Options</span></span>  
 <span data-ttu-id="2de6b-106">**Eingabe oder Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="2de6b-106">**Input or Output**</span></span>  
 <span data-ttu-id="2de6b-107">Zeigen Sie den Namen der Ausgabe an.</span><span class="sxs-lookup"><span data-stu-id="2de6b-107">View the name of the output.</span></span>  
  
 <span data-ttu-id="2de6b-108">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="2de6b-108">**Column**</span></span>  
 <span data-ttu-id="2de6b-109">Zeigen Sie die Ausgabespalten an, die Sie im Dialogfeld des Transformations-Editors ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="2de6b-109">View the output columns that you selected in the transformation editor dialog box.</span></span>  
  
 <span data-ttu-id="2de6b-110">**Fehler**</span><span class="sxs-lookup"><span data-stu-id="2de6b-110">**Error**</span></span>  
 <span data-ttu-id="2de6b-111">Geben Sie gegebenenfalls an, was bei Auftreten eines Fehlers geschehen soll: den Fehler ignorieren, die Zeile umleiten oder die Komponente mit einem Fehler abbrechen.</span><span class="sxs-lookup"><span data-stu-id="2de6b-111">If applicable, specify what should happen when an error occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="2de6b-112">**Verwandte Themen:** [Fehlerbehandlung in Daten](data-flow/error-handling-in-data.md)</span><span class="sxs-lookup"><span data-stu-id="2de6b-112">**Related Topics:** [Error Handling in Data](data-flow/error-handling-in-data.md)</span></span>  
  
 <span data-ttu-id="2de6b-113">**Abschneiden**</span><span class="sxs-lookup"><span data-stu-id="2de6b-113">**Truncation**</span></span>  
 <span data-ttu-id="2de6b-114">Geben Sie gegebenenfalls an, was bei Auftreten eines Abschneidens geschehen soll: den Fehler ignorieren, die Zeile umleiten oder die Komponente mit einem Fehler abbrechen.</span><span class="sxs-lookup"><span data-stu-id="2de6b-114">If applicable, specify what should happen when a truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="2de6b-115">**Verwandte Themen:** [Fehlerbehandlung in Daten](data-flow/error-handling-in-data.md)</span><span class="sxs-lookup"><span data-stu-id="2de6b-115">**Related Topics:** [Error Handling in Data](data-flow/error-handling-in-data.md)</span></span>  
  
 <span data-ttu-id="2de6b-116">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="2de6b-116">**Description**</span></span>  
 <span data-ttu-id="2de6b-117">Zeigt die Beschreibung des Vorgangs an.</span><span class="sxs-lookup"><span data-stu-id="2de6b-117">View the description of the operation.</span></span>  
  
 <span data-ttu-id="2de6b-118">**Diesen Wert für ausgewählte Zellen festlegen**</span><span class="sxs-lookup"><span data-stu-id="2de6b-118">**Set this value to selected cells**</span></span>  
 <span data-ttu-id="2de6b-119">Gibt an, was im Falle eines Fehlers oder einer Kürzung mit den ausgewählten Zellen geschehen soll: den Fehler ignorieren, die Zeile umleiten oder die Komponente mit einem Fehler abbrechen.</span><span class="sxs-lookup"><span data-stu-id="2de6b-119">Specify what should happen to all the selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="2de6b-120">**Anwenden**</span><span class="sxs-lookup"><span data-stu-id="2de6b-120">**Apply**</span></span>  
 <span data-ttu-id="2de6b-121">Wendet die Fehlerbehandlungsoption auf die ausgewählten Zellen an.</span><span class="sxs-lookup"><span data-stu-id="2de6b-121">Apply the error handling option to the selected cells.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2de6b-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2de6b-122">See Also</span></span>  
 [<span data-ttu-id="2de6b-123">Fehler- und Meldungsreferenz von Integration Services</span><span class="sxs-lookup"><span data-stu-id="2de6b-123">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
