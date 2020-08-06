---
title: Excel-Verbindungs-Manager | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- files [Integration Services], connections
- connections [Integration Services], Excel
- Excel [Integration Services]
- connection managers [Integration Services], Excel
ms.assetid: 667419f2-74fb-4b50-b963-9197d1368cda
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7561361c6d4ab7e22282b25367906aa4b75e5bc7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617239"
---
# <a name="excel-connection-manager"></a><span data-ttu-id="f7ef9-102">Excel-Verbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="f7ef9-102">Excel Connection Manager</span></span>
  <span data-ttu-id="f7ef9-103">Mit einem Excel-Verbindungs-Manager kann ein Paket eine Verbindung mit einer vorhandenen [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel-Arbeitsmappendatei herstellen.</span><span class="sxs-lookup"><span data-stu-id="f7ef9-103">An Excel connection manager enables a package to connect to an existing [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel workbook file.</span></span> <span data-ttu-id="f7ef9-104">Die Excel-Quelle und das Excel-Ziel, die [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] einschließen, verwenden den Excel-Verbindungs-Manager.</span><span class="sxs-lookup"><span data-stu-id="f7ef9-104">The Excel source and the Excel destination that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] include use the Excel connection manager.</span></span>  
  
 <span data-ttu-id="f7ef9-105">Wenn Sie einem Paket einen Excel-Verbindungs-Manager hinzufügen, erstellt [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] einen Verbindungs-Manager, der zur Laufzeit als Excel-Verbindung aufgelöst wird, die Eigenschaften des Verbindungs-Managers festlegt und der `Connections`-Auflistung im Paket den Verbindungs-Manager hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="f7ef9-105">When you add an Excel connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that is resolved as an Excel connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span>  
  
 <span data-ttu-id="f7ef9-106">Die `ConnectionManagerType`-Eigenschaft des Verbindungs-Managers ist auf `EXCEL` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="f7ef9-106">The `ConnectionManagerType` property of the connection manager is set to `EXCEL`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f7ef9-107">Es ist nicht möglich, eine Verbindung mit einer kennwortgeschützten Excel-Datei herzustellen.</span><span class="sxs-lookup"><span data-stu-id="f7ef9-107">You cannot connect to a password-protected Excel file.</span></span>  
  
## <a name="configuration-of-the-excel-connection-manager"></a><span data-ttu-id="f7ef9-108">Konfiguration des Excel-Verbindungs-Managers</span><span class="sxs-lookup"><span data-stu-id="f7ef9-108">Configuration of the Excel Connection Manager</span></span>  
 <span data-ttu-id="f7ef9-109">Es gibt folgende Möglichkeiten, um den Excel-Verbindungs-Manager zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="f7ef9-109">You can configure the Excel connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="f7ef9-110">Geben Sie den Pfad der Excel-Arbeitsmappendatei an.</span><span class="sxs-lookup"><span data-stu-id="f7ef9-110">Specify the path of the Excel workbook file.</span></span>  
  
-   <span data-ttu-id="f7ef9-111">Geben Sie die Excel-Version an, die zum Erstellen der Datei verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="f7ef9-111">Specify the version of Excel that was used to create the file.</span></span>  
  
-   <span data-ttu-id="f7ef9-112">Zeigen Sie an, ob die erste Zeile der abgerufenen Daten in den ausgewählten Arbeitsmappen oder Bereichen Spaltennamen enthält.</span><span class="sxs-lookup"><span data-stu-id="f7ef9-112">Indicate whether the first row of accessed data in the selected worksheets or ranges contains column names.</span></span>  
  
 <span data-ttu-id="f7ef9-113">Wenn der Excel-Verbindungs-Manager von einer Excel-Quelle verwendet wird, sind die Spaltennamen in den extrahierten Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="f7ef9-113">If the Excel connection manager is used by an Excel source, the column names are included with the extracted data.</span></span> <span data-ttu-id="f7ef9-114">Wird dieser von einem Excel-Ziel verwendet, sind die Spaltennamen in den geschriebenen Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="f7ef9-114">If it is used by an Excel destination, the column names are included in the written data.</span></span>  
  
 <span data-ttu-id="f7ef9-115">Der Excel-Verbindungs-Manager verwendet den [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB-Anbieter für Jet 4.0 und den zugehörigen Excel-ISAM-Treiber (Indexed Sequential Access Method, indizierte sequenzielle Zugriffsmethode), um auf Excel-Datenquellen zuzugreifen und diese zu lesen und in sie zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="f7ef9-115">The Excel connection manager uses the [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB Provider for Jet 4.0 and its supporting Excel ISAM (Indexed Sequential Access Method) driver to connect and read and write data to Excel data sources.</span></span> <span data-ttu-id="f7ef9-116">Weitere Informationen zum Verhalten dieses Anbieters und Treibers bei Verwendung mit Excel-Quellen und Excel-Zielen finden Sie unter [Excel-Quelle](../data-flow/excel-source.md) und Excel- [Ziel](../data-flow/excel-destination.md).</span><span class="sxs-lookup"><span data-stu-id="f7ef9-116">For more information about the behavior of this provider and driver when used with Excel sources and Excel destinations, see [Excel Source](../data-flow/excel-source.md) and [Excel Destination](../data-flow/excel-destination.md).</span></span>  
  
 <span data-ttu-id="f7ef9-117">Sie können Eigenschaften mit dem [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="f7ef9-117">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="f7ef9-118">Weitere Informationen zu den Eigenschaften, die Sie im [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer festlegen können, finden Sie unter [Verbindungs-Manager-Editor für Excel](../excel-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="f7ef9-118">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [Excel Connection Manager Editor](../excel-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="f7ef9-119">Weitere Informationen zum programmgesteuerten Konfigurieren eines Verbindungs-Managers finden Sie unter <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> und [Programmgesteuertes Hinzufügen von Verbindungen](../building-packages-programmatically/adding-connections-programmatically.md)festgelegt.</span><span class="sxs-lookup"><span data-stu-id="f7ef9-119">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
 <span data-ttu-id="f7ef9-120">Informationen zum Durchlaufen einer Gruppe von Excel-Dateien finden Sie unter [Schleife durch Excel-Dateien und Tabellen mit einem Foreach-Schleifencontainer](../control-flow/foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="f7ef9-120">For information about looping through a group of Excel files, see [Loop through Excel Files and Tables by Using a Foreach Loop Container](../control-flow/foreach-loop-container.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="f7ef9-121">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="f7ef9-121">Related Tasks</span></span>  
  
-   [<span data-ttu-id="f7ef9-122">Schleife durch Excel-Dateien und Tabellen mit einem Foreach-Schleifencontainer</span><span class="sxs-lookup"><span data-stu-id="f7ef9-122">Loop through Excel Files and Tables by Using a Foreach Loop Container</span></span>](../control-flow/foreach-loop-container.md)  
  
-   [<span data-ttu-id="f7ef9-123">Laden von Daten aus oder in Excel mit SQL Server Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="f7ef9-123">Import data from Excel or export data to Excel with SQL Server Integration Services (SSIS)</span></span>](../load-data-to-from-excel-with-ssis.md)
  
  
