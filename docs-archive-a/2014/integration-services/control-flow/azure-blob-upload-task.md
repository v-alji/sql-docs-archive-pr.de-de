---
title: Azure-Blob-Uploadtask | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afpblobuptask.f1
- sql11.dts.designer.afpblobuptask.f1
ms.assetid: 6ea068b0-4cd8-45b5-b89d-09b8f25040c0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0ca15c5a77a2694293981121f4e5927be8ec0e1c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697073"
---
# <a name="azure-blob-upload-task"></a><span data-ttu-id="1e75c-102">Azure-Blob-Uploadtask</span><span class="sxs-lookup"><span data-stu-id="1e75c-102">Azure Blob Upload Task</span></span>
  <span data-ttu-id="1e75c-103">Der Azure-Blob-Uploadtask ermöglicht einem SSIS-Paket das Hochladen von Dateien in einen Azure-Blobspeicher.</span><span class="sxs-lookup"><span data-stu-id="1e75c-103">The Azure Blob Upload Task enables an SSIS package to upload files to an Azure blob storage.</span></span>   
<span data-ttu-id="1e75c-104">Um einen **Azure-Blob-Uploadtask**hinzuzufügen, legen Sie ihn mittels Drag &amp; Drop auf dem SSIS-Designer ab, und doppelklicken Sie darauf, oder klicken Sie mit der rechten Maustaste, und klicken Sie anschließend auf **Bearbeiten** , um das folgende Dialogfeld **Azure-Blob-Uploadtask-Editor** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1e75c-104">To add an **Azure Blob Upload Task**, drag-drop it to the SSIS Designer, and double-click or right-click and click **Edit** to see the following **Azure Blob Upload Task Editor** dialog box.</span></span>  
  
 <span data-ttu-id="1e75c-105">Die folgende Tabelle enthält Beschreibungen für die Felder in diesem Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="1e75c-105">The following table provides descriptions for the fields in this dialog box.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1e75c-106">**Feld**</span><span class="sxs-lookup"><span data-stu-id="1e75c-106">**Field**</span></span>|<span data-ttu-id="1e75c-107">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="1e75c-107">**Description**</span></span>|  
|<span data-ttu-id="1e75c-108">AzureStorageConnection</span><span class="sxs-lookup"><span data-stu-id="1e75c-108">AzureStorageConnection</span></span>|<span data-ttu-id="1e75c-109">Geben Sie einen vorhandenen Azure Storage-Verbindungs-Manager an, oder erstellen Sie einen neuen, der sich auf ein Azure-Speicherkonto bezieht, das auf den Speicherort der Blob-Dateien verweist.</span><span class="sxs-lookup"><span data-stu-id="1e75c-109">Specify an existing Azure Storage Connection Manager or create a new one that refers to an Azure Storage Account, which points to where the blob files are hosted.</span></span>|  
|<span data-ttu-id="1e75c-110">BlobContainer</span><span class="sxs-lookup"><span data-stu-id="1e75c-110">BlobContainer</span></span>|<span data-ttu-id="1e75c-111">Gibt den Namen des Blobcontainers an, in dem die hochgeladenen Dateien als Blobs enthalten sein sollen.</span><span class="sxs-lookup"><span data-stu-id="1e75c-111">Specifies the name of the blob container that will hold the uploaded files as blobs.</span></span>|  
|<span data-ttu-id="1e75c-112">BlobDirectory</span><span class="sxs-lookup"><span data-stu-id="1e75c-112">BlobDirectory</span></span>|<span data-ttu-id="1e75c-113">Gibt das Blobverzeichnis an, in dem die hochgeladene Datei als Blockblob gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="1e75c-113">Specifies the blob directory where the uploaded file will be stored as a block blob.</span></span> <span data-ttu-id="1e75c-114">Das Blobverzeichnis ist eine virtuelle hierarchische Struktur.</span><span class="sxs-lookup"><span data-stu-id="1e75c-114">The blob directory is a virtual hierarchical structure.</span></span> <span data-ttu-id="1e75c-115">Wenn das Blob bereits vorhanden ist, wird es ersetzt.</span><span class="sxs-lookup"><span data-stu-id="1e75c-115">If the blob already exists, it will be replaced.</span></span>|  
|<span data-ttu-id="1e75c-116">LocalDirectory</span><span class="sxs-lookup"><span data-stu-id="1e75c-116">LocalDirectory</span></span>|<span data-ttu-id="1e75c-117">Geben Sie das lokale Verzeichnis mit den Dateien an, die hochgeladen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1e75c-117">Specify the local directory that contains the files to be uploaded.</span></span>|  
|<span data-ttu-id="1e75c-118">FileName</span><span class="sxs-lookup"><span data-stu-id="1e75c-118">FileName</span></span>|<span data-ttu-id="1e75c-119">Gibt einen Namensfilter an, um Dateien mit dem angegebenen Namensmuster auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="1e75c-119">Specifies a name filter to select files with the specified name pattern.</span></span> <span data-ttu-id="1e75c-120">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1e75c-120">E.g.</span></span> <span data-ttu-id="1e75c-121">„MeinArbeitsblatt\*.xls\* “ schließt „MeinArbeitsblatt001.xls“ und „MeinArbeitsblattABC.xlsx“ ein.</span><span class="sxs-lookup"><span data-stu-id="1e75c-121">MySheet\*.xls\* includes files such as MySheet001.xls and MySheetABC.xlsx.</span></span>|  
|<span data-ttu-id="1e75c-122">TimeRangeFrom/TimeRangeTo</span><span class="sxs-lookup"><span data-stu-id="1e75c-122">TimeRangeFrom/TimeRangeTo</span></span>|<span data-ttu-id="1e75c-123">Gibt einen Zeitbereichsfilter an.</span><span class="sxs-lookup"><span data-stu-id="1e75c-123">Specifies a time range filter.</span></span> <span data-ttu-id="1e75c-124">Dateien, die nach **TimeRangeFrom** und vor **TimeRangeTo** geändert wurden, sind eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="1e75c-124">Files modified after **TimeRangeFrom** and before **TimeRangeTo** will be included.</span></span>|  
  
  
