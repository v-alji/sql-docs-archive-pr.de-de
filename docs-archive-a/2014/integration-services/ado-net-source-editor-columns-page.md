---
title: ADO.net-Quellen-Editor (Seite ' Spalten ') | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.adonetsource.columns.f1
ms.assetid: fbc205b9-2001-4737-a76b-1ba777344bd9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0d89f8c926761b9149f19269bc2519c12bcf130e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618234"
---
# <a name="ado-net-source-editor-columns-page"></a><span data-ttu-id="74bee-102">ADO.NET-Quellen-Editor (Seite 'Spalten')</span><span class="sxs-lookup"><span data-stu-id="74bee-102">ADO NET Source Editor (Columns Page)</span></span>
  <span data-ttu-id="74bee-103">Mithilfe der Seite **Spalten** des Dialogfelds **ADO.NET-Quellen-Editor** können Sie jeder externen (Quell-)Spalte eine Ausgabespalte zuordnen.</span><span class="sxs-lookup"><span data-stu-id="74bee-103">Use the **Columns** page of the **ADO NET Source Editor** dialog box to map an output column to each external (source) column.</span></span>  
  
 <span data-ttu-id="74bee-104">Weitere Informationen zur ADO NET-Quelle finden Sie unter [ADO NET Source](data-flow/ado-net-source.md).</span><span class="sxs-lookup"><span data-stu-id="74bee-104">To learn more about the ADO NET source, see [ADO NET Source](data-flow/ado-net-source.md).</span></span>  
  
 <span data-ttu-id="74bee-105">**So öffnen Sie die Seite "Spalten"**</span><span class="sxs-lookup"><span data-stu-id="74bee-105">**To open the Columns page**</span></span>  
  
1.  <span data-ttu-id="74bee-106">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Paket, das ADO.NET als Quelle hat.</span><span class="sxs-lookup"><span data-stu-id="74bee-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that has the ADO NET source.</span></span>  
  
2.  <span data-ttu-id="74bee-107">Doppelklicken Sie auf der Registerkarte **Datenfluss** auf die ADO.NET-Quelle.</span><span class="sxs-lookup"><span data-stu-id="74bee-107">On the **Data Flow** tab, double-click the ADO NET source.</span></span>  
  
3.  <span data-ttu-id="74bee-108">Klicken Sie im **ADO.NET-Quellen-Editor**auf **Spalten**.</span><span class="sxs-lookup"><span data-stu-id="74bee-108">In the **ADO NET Source Editor**, click **Columns**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="74bee-109">Tastatur</span><span class="sxs-lookup"><span data-stu-id="74bee-109">Options</span></span>  
 <span data-ttu-id="74bee-110">**Verfügbare externe Spalten**</span><span class="sxs-lookup"><span data-stu-id="74bee-110">**Available External Columns**</span></span>  
 <span data-ttu-id="74bee-111">Zeigt die Liste der in der Datenquelle verfügbaren externen Spalten an.</span><span class="sxs-lookup"><span data-stu-id="74bee-111">View the list of available external columns in the data source.</span></span> <span data-ttu-id="74bee-112">Mit der Tabelle können keine Spalten hinzugefügt oder gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="74bee-112">You cannot use this table to add or delete columns.</span></span>  
  
 <span data-ttu-id="74bee-113">**Externe Spalte**</span><span class="sxs-lookup"><span data-stu-id="74bee-113">**External Column**</span></span>  
 <span data-ttu-id="74bee-114">Zeigt die externen (Quell-)Spalten in der gleichen Reihenfolge an wie beim Konfigurieren von Komponenten, die Daten aus dieser Quelle verwenden.</span><span class="sxs-lookup"><span data-stu-id="74bee-114">View external (source) columns in the order in which you will see them when configuring components that consume data from this source.</span></span>  
  
 <span data-ttu-id="74bee-115">**Ausgabespalte**</span><span class="sxs-lookup"><span data-stu-id="74bee-115">**Output Column**</span></span>  
 <span data-ttu-id="74bee-116">Geben Sie für jede Ausgabespalte einen eindeutigen Namen an.</span><span class="sxs-lookup"><span data-stu-id="74bee-116">Provide a unique name for each output column.</span></span> <span data-ttu-id="74bee-117">Standardmäßig wird der Name der ausgewählten externen (Quell-)Spalte verwendet. Sie können jedoch auch einen beschreibenden Namen angeben, sofern dieser eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="74bee-117">The default is the name of the selected external (source) column; however, you can choose any unique, descriptive name.</span></span> <span data-ttu-id="74bee-118">Der bereitgestellte Name wird im [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="74bee-118">The name provided will be displayed within the [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74bee-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="74bee-119">See Also</span></span>  
 <span data-ttu-id="74bee-120">[ADO NET-Quellen-Editor &#40;Seite "Verbindungs-Manager"&#41;](../../2014/integration-services/ado-net-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="74bee-120">[ADO NET Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/ado-net-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="74bee-121">[ADO NET-Quellen-Editor &#40;Seite "Fehlerausgabe"&#41;](../../2014/integration-services/ado-net-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="74bee-121">[ADO NET Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/ado-net-source-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="74bee-122">ADO.NET-Verbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="74bee-122">ADO.NET Connection Manager</span></span>](connection-manager/ado-net-connection-manager.md)  
  
  
