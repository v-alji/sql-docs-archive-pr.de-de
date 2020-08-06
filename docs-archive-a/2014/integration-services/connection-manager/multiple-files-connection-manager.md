---
title: Verbindungs-Manager für mehrere Dateien | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- folders [Integration Services], connections
- files [Integration Services], connections
- Multiple Files connection manager
- connection managers [Integration Services], Multiple Files
- connections [Integration Services], files
- multiple file connections
ms.assetid: 10bdc56e-c5cd-4ddb-b2f7-375fe57fe8b2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f9ebd45aa4f0794d98be6a79125bf1874913d491
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621136"
---
# <a name="multiple-files-connection-manager"></a><span data-ttu-id="8e294-102">Verbindungs-Manager für mehrere Dateien</span><span class="sxs-lookup"><span data-stu-id="8e294-102">Multiple Files Connection Manager</span></span>
  <span data-ttu-id="8e294-103">Mit einem Verbindungs-Manager für mehrere Dateien kann ein Paket auf vorhandene Dateien und Ordner verweisen oder Dateien und Ordner zur Laufzeit erstellen.</span><span class="sxs-lookup"><span data-stu-id="8e294-103">A Multiple Files connection manager enables a package to reference existing files and folders, or to create files and folders at run time.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8e294-104">Die integrierten Tasks und Datenflusskomponenten in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] verwenden keinen Verbindungs-Manager für mehrere Dateien.</span><span class="sxs-lookup"><span data-stu-id="8e294-104">The built-in tasks and data flow components in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] do not use the Multiple Files connection manager.</span></span> <span data-ttu-id="8e294-105">Sie können den Verbindungs-Manager jedoch im Skripttask oder in der Skriptkomponente verwenden.</span><span class="sxs-lookup"><span data-stu-id="8e294-105">However, you can use this connection manager in the Script task or Script component.</span></span> <span data-ttu-id="8e294-106">Informationen zum Verwenden von Verbindungs-Managern in der Skripttask finden Sie unter [Herstellen einer Verbindung zu Datenquellen im Skripttask ](../extending-packages-scripting/task/connecting-to-data-sources-in-the-script-task.md).</span><span class="sxs-lookup"><span data-stu-id="8e294-106">For information about how to use connection managers in the Script task, see [Connecting to Data Sources in the Script Task](../extending-packages-scripting/task/connecting-to-data-sources-in-the-script-task.md).</span></span> <span data-ttu-id="8e294-107">Weitere Informationen zur Verwendung von Verbindungs-Managern in der Skript Komponente finden Sie unter [Herstellen einer Verbindung mit Datenquellen in der Skript Komponente] (.). /extending-packages-scripting/data-flow-script-component/connecting-to-data-sources-in-the-script-component.md.</span><span class="sxs-lookup"><span data-stu-id="8e294-107">For information about how to use connection managers in the Script component, see [Connecting to Data Sources in the Script Component](../extending-packages-scripting/data-flow-script-component/connecting-to-data-sources-in-the-script-component.md.</span></span>  
  
## <a name="usage-types-of-the-multiple-files-connection-manager"></a><span data-ttu-id="8e294-108">Verwendungstypen des Verbindungs-Managers für mehrere Dateien</span><span class="sxs-lookup"><span data-stu-id="8e294-108">Usage Types of the Multiple Files Connection Manager</span></span>  
 <span data-ttu-id="8e294-109">Mit der `FileUsageType`-Eigenschaft des Verbindungs-Managers für mehrere Dateien wird angegeben, wie die Verbindung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8e294-109">The `FileUsageType` property of the Multiple Files connection manager specifies how the connection is used.</span></span> <span data-ttu-id="8e294-110">Der Verbindungs-Manager für mehrere Dateien kann Dateien bzw. Ordner erstellen und vorhandene Dateien bzw. Ordner verwenden.</span><span class="sxs-lookup"><span data-stu-id="8e294-110">The Multiple Files connection manager can create files, create folders, use existing files, and use existing folders.</span></span>  
  
 <span data-ttu-id="8e294-111">In der folgenden Tabelle sind die Werte von `FileUsageType` aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="8e294-111">The following table lists the values of `FileUsageType`.</span></span>  
  
|<span data-ttu-id="8e294-112">value</span><span class="sxs-lookup"><span data-stu-id="8e294-112">Value</span></span>|<span data-ttu-id="8e294-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8e294-113">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8e294-114">**0**</span><span class="sxs-lookup"><span data-stu-id="8e294-114">**0**</span></span>|<span data-ttu-id="8e294-115">Der Verbindungs-Manager für mehrere Dateien verwendet eine vorhandene Datei.</span><span class="sxs-lookup"><span data-stu-id="8e294-115">Multiple Files connection manager uses an existing file.</span></span>|  
|<span data-ttu-id="8e294-116">**1**</span><span class="sxs-lookup"><span data-stu-id="8e294-116">**1**</span></span>|<span data-ttu-id="8e294-117">Der Verbindungs-Manager für mehrere Dateien erstellt eine Datei.</span><span class="sxs-lookup"><span data-stu-id="8e294-117">Multiple Files connection manager creates a file.</span></span>|  
|<span data-ttu-id="8e294-118">**2**</span><span class="sxs-lookup"><span data-stu-id="8e294-118">**2**</span></span>|<span data-ttu-id="8e294-119">Der Verbindungs-Manager für mehrere Dateien verwendet einen vorhandenen Ordner.</span><span class="sxs-lookup"><span data-stu-id="8e294-119">Multiple Files connection manager uses an existing folder.</span></span>|  
|<span data-ttu-id="8e294-120">**3**</span><span class="sxs-lookup"><span data-stu-id="8e294-120">**3**</span></span>|<span data-ttu-id="8e294-121">Der Verbindungs-Manager für mehrere Dateien erstellt einen Ordner.</span><span class="sxs-lookup"><span data-stu-id="8e294-121">Multiple Files connection manager creates a folder.</span></span>|  
  
## <a name="configuration-of-the-multiple-files-connection-manager"></a><span data-ttu-id="8e294-122">Konfiguration des Verbindungs-Managers für mehrere Dateien</span><span class="sxs-lookup"><span data-stu-id="8e294-122">Configuration of the Multiple Files Connection Manager</span></span>  
 <span data-ttu-id="8e294-123">Wenn Sie einem Paket einen Verbindungs-Manager für mehrere Dateien hinzufügen, erstellt [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] einen Verbindungs-Manager, der zur Laufzeit in eine Verbindung für mehrere Dateien aufgelöst wird, die Eigenschaften der Verbindung für mehrere Dateien festlegt und der `Connections`-Auflistung des Pakets die Verbindung für mehrere Dateien hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="8e294-123">When you add a Multiple Files connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to a Multiple Files connection at run time, sets the Multiple Files connection properties, and adds the Multiple Files connection to the `Connections` collection of the package.</span></span>  
  
 <span data-ttu-id="8e294-124">Die `ConnectionManagerType`-Eigenschaft des Verbindungs-Managers ist auf `MULTIFILE` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8e294-124">The `ConnectionManagerType` property of the connection manager is set to `MULTIFILE`.</span></span>  
  
 <span data-ttu-id="8e294-125">Es gibt folgende Möglichkeiten, um einen Verbindungs-Manager für mehrere Dateien zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="8e294-125">You can configure a Multiple Files connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="8e294-126">Geben Sie den Verwendungstyp von Dateien und Ordnern an.</span><span class="sxs-lookup"><span data-stu-id="8e294-126">Specify the usage type of files and folders.</span></span>  
  
-   <span data-ttu-id="8e294-127">Geben Sie Dateien und Ordner an.</span><span class="sxs-lookup"><span data-stu-id="8e294-127">Specify files and folders.</span></span>  
  
-   <span data-ttu-id="8e294-128">Falls Sie mehrere Dateien oder Ordner verwenden, geben Sie die Reihenfolge an, in der auf die Dateien und Ordner zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="8e294-128">If using multiple files or folders, specify the order in which the files and folders are accessed.</span></span>  
  
 <span data-ttu-id="8e294-129">Wenn der Verbindungs-Manager für mehrere Dateien auf mehrere Dateien und Ordner verweist, werden die Pfade der Dateien und Ordner durch einen senkrechten Strich (|) getrennt.</span><span class="sxs-lookup"><span data-stu-id="8e294-129">If the Multiple Files connection manager references multiple files and folders, the paths of the files and folders are separated by the pipe (|) character.</span></span> <span data-ttu-id="8e294-130">Die `ConnectionString`-Eigenschaft des Verbindungs-Managers hat folgendes Format:</span><span class="sxs-lookup"><span data-stu-id="8e294-130">The `ConnectionString` property of the connection manager has the following format:</span></span>  
  
 \<*path*>|\<*path*>  
  
 <span data-ttu-id="8e294-131">Mehrere Dateien oder Ordner können Sie auch mithilfe von Platzhalterzeichen angeben.</span><span class="sxs-lookup"><span data-stu-id="8e294-131">You can also specify multiple files or folders using wildcard characters.</span></span> <span data-ttu-id="8e294-132">Um beispielsweise auf alle Textdateien auf dem Laufwerk C zu verweisen, kann der Wert der `ConnectionString` Eigenschaft auf c: \\ \*. txt festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="8e294-132">For example, to reference all the text files on the C drive, the value of the `ConnectionString` property can be set to C:\\*.txt.</span></span>  
  
 <span data-ttu-id="8e294-133">Sie können Eigenschaften mit dem [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="8e294-133">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="8e294-134">Weitere Informationen zu den Eigenschaften, die Sie im [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer festlegen können, finden Sie unter [Referenz zur Benutzeroberfläche des Dialogfelds Dateiverbindungs-Manager hinzufügen](add-file-connection-manager-dialog-box-ui-reference.md).</span><span class="sxs-lookup"><span data-stu-id="8e294-134">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [Add File Connection Manager Dialog Box UI Reference](add-file-connection-manager-dialog-box-ui-reference.md).</span></span>  
  
 <span data-ttu-id="8e294-135">Weitere Informationen zum programmgesteuerten Konfigurieren eines Verbindungs-Managers finden Sie unter <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> und [Programmgesteuertes Hinzufügen von Verbindungen](../building-packages-programmatically/adding-connections-programmatically.md)festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8e294-135">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
  
