---
title: Ersetzen von Vorlagenparametern|Microsoft-Dokumente
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.templates.replaceparameters.f1
helpviewer_keywords:
- template parameters [Template Explorer]
- templates [Transact-SQL], replacing parameters
- Replace (Query) Template Parameters dialog box
- replacing template parameters
ms.assetid: 1234aa14-3464-4a3e-922a-5cfb8fb23627
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1d87b17a110efe118f7796487448e4d3bae30375
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619515"
---
# <a name="replace-template-parameters"></a><span data-ttu-id="115d6-102">Vorlagenparameter ersetzen</span><span class="sxs-lookup"><span data-stu-id="115d6-102">Replace Template Parameters</span></span>
  <span data-ttu-id="115d6-103">Vorlagen enthalten Parameter, die bei jeder Verwendung der betreffenden Vorlage durch implementierungsspezifische Werte ersetzt werden können.</span><span class="sxs-lookup"><span data-stu-id="115d6-103">Templates contain parameters that can be replaced by implementation-specific values each time the template is used.</span></span> <span data-ttu-id="115d6-104">Nach dem Öffnen einer Vorlage in einem Code-Editor können Sie die Parameter durch für die Implementierung relevante Werte ersetzen.</span><span class="sxs-lookup"><span data-stu-id="115d6-104">After opening a template in a code editor, you can replace the parameters with values relevant to your implementation.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="115d6-105">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="115d6-105">Before You Begin</span></span>  
 <span data-ttu-id="115d6-106">Das Dialogfeld **Werte für Vorlagenparameter angeben** ist ein Raster mit drei Spalten.</span><span class="sxs-lookup"><span data-stu-id="115d6-106">The **Specify Values for Template Parameters** dialog is a grid with three columns.</span></span> <span data-ttu-id="115d6-107">Die Spalten **Parameter** und **Typ** sind schreibgeschützt und können nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="115d6-107">The **Parameter** and **Type** columns are read-only and cannot be changed.</span></span> <span data-ttu-id="115d6-108">Überprüfen Sie den Inhalt der Spalte **Wert** , und ändern Sie die Standardwerte in für die Implementierung geeignete Werte.</span><span class="sxs-lookup"><span data-stu-id="115d6-108">Review the contents of the **Value** column, and change any of the defaults to values appropriate for your implementation.</span></span>  
  
 <span data-ttu-id="115d6-109">Damit Sie dieses Dialogfeld verwenden können, müssen Sie Parameter im folgenden Format in spitzen Klammern (`< >`) in das Skript einfügen: `<`*Parametername*`,` *Datentyp*`,` *Standardwert*`>`.</span><span class="sxs-lookup"><span data-stu-id="115d6-109">To use this dialog box, you must have parameters in your script enclosed in angle brackets (`< >`) in the format `<`*parameter_name*`,` *data_type*`,` *default_value*`>`.</span></span>  
  
## <a name="replace-template-parameters"></a><span data-ttu-id="115d6-110">Vorlagenparameter ersetzen</span><span class="sxs-lookup"><span data-stu-id="115d6-110">Replace Template Parameters</span></span>  
 <span data-ttu-id="115d6-111">Nach dem Öffnen der Vorlage in einem Code-Editor-Fenster:</span><span class="sxs-lookup"><span data-stu-id="115d6-111">After opening the template in a code editor window:</span></span>  
  
1.  <span data-ttu-id="115d6-112">Klicken Sie im Menü **Abfrage** auf **Werte für Vorlagenparameter angeben**.</span><span class="sxs-lookup"><span data-stu-id="115d6-112">On the **Query** menu, click **Specify Values for Template Parameters**.</span></span>  
  
2.  <span data-ttu-id="115d6-113">Im Dialogfeld **Werte für Vorlagenparameter angeben** enthält die Spalte **Werte** jeweils einen vorgeschlagenen Wert für jeden Parameter.</span><span class="sxs-lookup"><span data-stu-id="115d6-113">In the **Specify Values for Template Parameters** dialog box, the **Values** column contains a suggested value for each parameter.</span></span> <span data-ttu-id="115d6-114">Akzeptieren Sie den Wert, oder ersetzen Sie ihn durch einen neuen Wert.</span><span class="sxs-lookup"><span data-stu-id="115d6-114">Accept the value or replace it with a new value.</span></span>  
  
3.  <span data-ttu-id="115d6-115">Klicken Sie auf **OK** , um das Dialogfeld **Vorlagenparameter ersetzen** zu schließen und das Skript im Abfrage-Editor zu ändern.</span><span class="sxs-lookup"><span data-stu-id="115d6-115">Click **OK** to close the **Replace Template Parameters** dialog box and modify the script in the query editor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="115d6-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="115d6-116">See Also</span></span>  
 <span data-ttu-id="115d6-117">[Vorlagen-Explorer](template-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="115d6-117">[Template Explorer](template-explorer.md) </span></span>  
 [<span data-ttu-id="115d6-118">Öffnen einer Vorlage</span><span class="sxs-lookup"><span data-stu-id="115d6-118">Open a Template</span></span>](open-a-template.md)  
  
  
