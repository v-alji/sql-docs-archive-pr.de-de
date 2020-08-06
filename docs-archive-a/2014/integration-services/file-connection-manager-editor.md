---
title: Dateiverbindungs-Manager-Editor | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fileconnectionmanager.f1
helpviewer_keywords:
- File Connection Manager Editor
ms.assetid: 051c48e5-3d86-49af-b554-ff62e3de3622
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2f3261b836d4800787fc078b05b15e469d3c200d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621058"
---
# <a name="file-connection-manager-editor"></a><span data-ttu-id="2a9ad-102">Dateiverbindungs-Manager-Editor</span><span class="sxs-lookup"><span data-stu-id="2a9ad-102">File Connection Manager Editor</span></span>
  <span data-ttu-id="2a9ad-103">Im Dialogfeld **Dateiverbindungs-Manager-Editor** werden die Eigenschaften angegeben, die zum Herstellen einer Verbindung zu einer Datei oder einem Ordner verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2a9ad-103">Use the **File Connection Manager Editor** dialog box to specify the properties used to connect to a file or a folder.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2a9ad-104">Sie können die ConnectionString-Eigenschaft für den Dateiverbindungs-Manager festlegen, indem Sie einen Ausdruck im Eigenschaftenfenster von [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]angeben.</span><span class="sxs-lookup"><span data-stu-id="2a9ad-104">You can set the ConnectionString property for the File connection manager by specifying an expression in the Properties window of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="2a9ad-105">Fügen Sie jedoch im **Dateiverbindungs-Manager-Editor**für **Datei/Ordner**einen Pfad für eine Datei oder einen Ordner hinzu, um Überprüfungsfehler zu vermeiden, wenn Sie die Datei oder den Ordner mit einem Ausdruck angeben.</span><span class="sxs-lookup"><span data-stu-id="2a9ad-105">However, to avoid a validation error when you use an expression to specify the file or folder, in the **File Connection Manager Editor**, for **File/Folder**, add a file or folder path.</span></span>  
  
 <span data-ttu-id="2a9ad-106">Weitere Informationen zum Dateiverbindungs-Manager finden Sie unter [File Connection Manager](connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="2a9ad-106">To learn more about the File connection manager, see [File Connection Manager](connection-manager/file-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="2a9ad-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="2a9ad-107">Options</span></span>  
 <span data-ttu-id="2a9ad-108">**Verwendungstyp**</span><span class="sxs-lookup"><span data-stu-id="2a9ad-108">**Usage Type**</span></span>  
 <span data-ttu-id="2a9ad-109">Geben Sie an, ob die Verbindung vom **Dateiverbindungs-Manager** zu einer vorhandenen Datei oder einem vorhandenen Ordner hergestellt werden soll, oder ob dafür eine neue Datei oder ein neuer Ordner erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="2a9ad-109">Specify whether the **File Connection Manager** connects to an existing file or folder or creates a new file or folder.</span></span>  
  
|<span data-ttu-id="2a9ad-110">Wert</span><span class="sxs-lookup"><span data-stu-id="2a9ad-110">Value</span></span>|<span data-ttu-id="2a9ad-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2a9ad-111">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2a9ad-112">Datei erstellen</span><span class="sxs-lookup"><span data-stu-id="2a9ad-112">Create file</span></span>|<span data-ttu-id="2a9ad-113">Erstellen Sie zur Laufzeit eine neue Datei.</span><span class="sxs-lookup"><span data-stu-id="2a9ad-113">Create a new file at run time.</span></span>|  
|<span data-ttu-id="2a9ad-114">Vorhandene Datei</span><span class="sxs-lookup"><span data-stu-id="2a9ad-114">Existing file</span></span>|<span data-ttu-id="2a9ad-115">Verwenden Sie eine vorhandene Datei.</span><span class="sxs-lookup"><span data-stu-id="2a9ad-115">Use an existing file.</span></span>|  
|<span data-ttu-id="2a9ad-116">Ordner erstellen</span><span class="sxs-lookup"><span data-stu-id="2a9ad-116">Create folder</span></span>|<span data-ttu-id="2a9ad-117">Erstellen Sie zur Laufzeit einen neuen Ordner.</span><span class="sxs-lookup"><span data-stu-id="2a9ad-117">Create a new folder at run time.</span></span>|  
|<span data-ttu-id="2a9ad-118">Vorhandener Ordner</span><span class="sxs-lookup"><span data-stu-id="2a9ad-118">Existing folder</span></span>|<span data-ttu-id="2a9ad-119">Verwenden Sie einen vorhandenen Ordner.</span><span class="sxs-lookup"><span data-stu-id="2a9ad-119">Use an existing folder.</span></span>|  
  
 <span data-ttu-id="2a9ad-120">**Datei/Ordner**</span><span class="sxs-lookup"><span data-stu-id="2a9ad-120">**File / Folder**</span></span>  
 <span data-ttu-id="2a9ad-121">Bei **Datei**geben Sie die zu verwendende Datei an.</span><span class="sxs-lookup"><span data-stu-id="2a9ad-121">If **File**, specify the file to use.</span></span>  
  
 <span data-ttu-id="2a9ad-122">Bei **Ordner**geben Sie den zu verwendenden Ordner an.</span><span class="sxs-lookup"><span data-stu-id="2a9ad-122">If **Folder**, specify the folder to use.</span></span>  
  
 <span data-ttu-id="2a9ad-123">**Durchsuchen**</span><span class="sxs-lookup"><span data-stu-id="2a9ad-123">**Browse**</span></span>  
 <span data-ttu-id="2a9ad-124">Wählen Sie die Datei oder den Ordner mithilfe des Dialogfelds **Datei auswählen** oder des Dialogfelds **Ordner suchen** aus.</span><span class="sxs-lookup"><span data-stu-id="2a9ad-124">Select the file or folder by using the **Select File** or **Browse for Folder** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a9ad-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2a9ad-125">See Also</span></span>  
 [<span data-ttu-id="2a9ad-126">Fehler- und Meldungsreferenz von Integration Services</span><span class="sxs-lookup"><span data-stu-id="2a9ad-126">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
