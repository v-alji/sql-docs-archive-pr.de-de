---
title: Dateiverbindungs-Manager | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- folders [Integration Services], connections
- files [Integration Services], connections
- files [Integration Services]
- connection managers [Integration Services], File
- connections [Integration Services], files
- File connection manager
ms.assetid: 019078bc-44ee-4975-9169-0f9a89e3f3be
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cebb5438003c6b14c547d14012ff1bc1175a706d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722941"
---
# <a name="file-connection-manager"></a><span data-ttu-id="2500a-102">Dateiverbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="2500a-102">File Connection Manager</span></span>
  <span data-ttu-id="2500a-103">Mit einem Dateiverbindungs-Manager kann ein Paket auf eine vorhandene Datei oder einen vorhandenen Ordner verweisen bzw. eine Datei oder einen Ordner zur Laufzeit erstellen.</span><span class="sxs-lookup"><span data-stu-id="2500a-103">A File connection manager enables a package to reference an existing file or folder, or to create a file or folder at run time.</span></span> <span data-ttu-id="2500a-104">Beispielsweise können Sie auf eine Excel-Datei verweisen.</span><span class="sxs-lookup"><span data-stu-id="2500a-104">For example, you can reference an Excel file.</span></span> <span data-ttu-id="2500a-105">Zur Ausführung bestimmter Komponenten in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] werden in Dateien enthaltene Informationen verwendet.</span><span class="sxs-lookup"><span data-stu-id="2500a-105">Certain components in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] use information in files to perform their work.</span></span> <span data-ttu-id="2500a-106">Beispielsweise kann ein Task SQL ausführen auf eine Datei verweisen, die die SQL-Anweisungen enthält, die vom Task ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2500a-106">For example, an Execute SQL task can reference a file that contains the SQL statements that the task executes.</span></span> <span data-ttu-id="2500a-107">Mit anderen Komponenten werden Vorgänge für Dateien ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2500a-107">Other components perform operations on files.</span></span> <span data-ttu-id="2500a-108">Mit dem Task Dateisystem kann beispielsweise auf eine Datei verwiesen werden, die an einen neuen Ort kopiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="2500a-108">For example, the File System task can reference a file to copy it to a new location.</span></span>  
  
## <a name="usage-types-of-the-file-connection-manager"></a><span data-ttu-id="2500a-109">Verwendungstypen des Dateiverbindungs-Managers</span><span class="sxs-lookup"><span data-stu-id="2500a-109">Usage Types of the File Connection Manager</span></span>  
 <span data-ttu-id="2500a-110">Mit der `FileUsageType`-Eigenschaft des Dateiverbindungs-Managers wird angegeben, wie die Dateiverbindung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2500a-110">The `FileUsageType` property of the File connection manager specifies how the file connection is used.</span></span> <span data-ttu-id="2500a-111">Der Dateiverbindungs-Manager kann eine Datei bzw. einen Ordner erstellen und eine vorhandene Datei bzw. einen vorhandenen Ordner verwenden.</span><span class="sxs-lookup"><span data-stu-id="2500a-111">The File connection manager can create a file, create a folder, use an existing file, or use an existing folder.</span></span>  
  
 <span data-ttu-id="2500a-112">In der folgenden Tabelle sind die Werte von `FileUsageType` aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="2500a-112">The following table lists the values of `FileUsageType`.</span></span>  
  
|<span data-ttu-id="2500a-113">value</span><span class="sxs-lookup"><span data-stu-id="2500a-113">Value</span></span>|<span data-ttu-id="2500a-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2500a-114">Description</span></span>|  
|-----------|-----------------|  
|`0`|<span data-ttu-id="2500a-115">Der Dateiverbindungs-Manager verwendet eine vorhandene Datei.</span><span class="sxs-lookup"><span data-stu-id="2500a-115">File connection manager uses an existing file.</span></span>|  
|`1`|<span data-ttu-id="2500a-116">Der Dateiverbindungs-Manager erstellt eine Datei.</span><span class="sxs-lookup"><span data-stu-id="2500a-116">File connection manager creates a file.</span></span>|  
|`2`|<span data-ttu-id="2500a-117">Der Dateiverbindungs-Manager verwendet einen vorhandenen Ordner.</span><span class="sxs-lookup"><span data-stu-id="2500a-117">File connection manager uses an existing folder.</span></span>|  
|`3`|<span data-ttu-id="2500a-118">Der Dateiverbindungs-Manager erstellt einen Ordner.</span><span class="sxs-lookup"><span data-stu-id="2500a-118">File connection manager creates a folder.</span></span>|  
  
## <a name="multiple-file-or-folder-connections"></a><span data-ttu-id="2500a-119">Mehrere Datei- oder Ordnerverbindungen</span><span class="sxs-lookup"><span data-stu-id="2500a-119">Multiple File or Folder Connections</span></span>  
 <span data-ttu-id="2500a-120">Der Dateiverbindungs-Manager kann nur auf eine einzige Datei oder einen einzigen Ordner verweisen.</span><span class="sxs-lookup"><span data-stu-id="2500a-120">The File connection manager can reference only one file or folder.</span></span> <span data-ttu-id="2500a-121">Wenn Sie auf mehrere Dateien oder Ordner verweisen möchten, verwenden Sie anstelle eines Dateiverbindungs-Managers einen Verbindungs-Manager für mehrere Dateien.</span><span class="sxs-lookup"><span data-stu-id="2500a-121">To reference multiple files or folders, use a Multiple Files connection manager instead of a File connection manager.</span></span> <span data-ttu-id="2500a-122">Weitere Informationen finden Sie unter [Multiple Files Connection Manager](multiple-files-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="2500a-122">For more information, see [Multiple Files Connection Manager](multiple-files-connection-manager.md).</span></span>  
  
## <a name="configuration-of-the-file-connection-manager"></a><span data-ttu-id="2500a-123">Konfiguration des Verbindungs-Managers für Dateien</span><span class="sxs-lookup"><span data-stu-id="2500a-123">Configuration of the File Connection Manager</span></span>  
 <span data-ttu-id="2500a-124">Wenn Sie einem Paket einen Dateiverbindungs-Manager hinzufügen, erstellt [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] einen Verbindungs-Manager, der zur Laufzeit in eine Dateiverbindung aufgelöst wird, die Eigenschaften der Dateiverbindung festlegt und der `Connections`-Auflistung des Pakets die Dateiverbindung hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="2500a-124">When you add a File connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to a File connection at run time, sets the File connection properties, and adds the File connection to the `Connections` collection of the package.</span></span>  
  
 <span data-ttu-id="2500a-125">Die `ConnectionManagerType`-Eigenschaft des Verbindungs-Managers ist auf `FILE` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2500a-125">The `ConnectionManagerType` property of the connection manager is set to `FILE`.</span></span>  
  
 <span data-ttu-id="2500a-126">Es gibt folgende Möglichkeiten, um einen Dateiverbindungs-Manager zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="2500a-126">You can configure a File connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="2500a-127">Geben Sie den Verwendungstyp an.</span><span class="sxs-lookup"><span data-stu-id="2500a-127">Specify the usage type.</span></span>  
  
-   <span data-ttu-id="2500a-128">Geben Sie eine Datei oder einen Ordner an.</span><span class="sxs-lookup"><span data-stu-id="2500a-128">Specify a file or folder.</span></span>  
  
 <span data-ttu-id="2500a-129">Sie können die ConnectionString-Eigenschaft für den Dateiverbindungs-Manager festlegen, indem Sie einen Ausdruck im Eigenschaftenfenster von [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]angeben.</span><span class="sxs-lookup"><span data-stu-id="2500a-129">You can set the ConnectionString property for the File connection manager by specifying an expression in the Properties window of [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="2500a-130">Fügen Sie jedoch im **Dateiverbindungs-Manager-Editor**für **Datei/Ordner**einen Pfad für eine Datei oder einen Ordner hinzu, um Überprüfungsfehler zu vermeiden, wenn Sie die Datei oder den Ordner mit einem Ausdruck angeben.</span><span class="sxs-lookup"><span data-stu-id="2500a-130">However, to avoid a validation error when you use an expression to specify the file or folder, in the **File Connection Manager Editor**, for **File/Folder**, add a file or folder path.</span></span>  
  
 <span data-ttu-id="2500a-131">Sie können Eigenschaften mit dem [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="2500a-131">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="2500a-132">Weitere Informationen zu den Eigenschaften, die Sie im [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer festlegen können, finden Sie unter [Dateiverbindungs-Manager-Editor](../file-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="2500a-132">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [File Connection Manager Editor](../file-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="2500a-133">Weitere Informationen zum programmgesteuerten Konfigurieren eines Verbindungs-Managers finden Sie unter <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> und [Programmgesteuertes Hinzufügen von Verbindungen](../building-packages-programmatically/adding-connections-programmatically.md)festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2500a-133">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
  
