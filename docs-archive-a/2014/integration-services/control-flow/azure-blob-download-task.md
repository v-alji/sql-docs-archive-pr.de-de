---
title: Azure-Blob-Downloadtask | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afpblobdltask.f1
- sql11.dts.designer.afpblobdltask.f1
ms.assetid: 8a63bf44-71be-456d-9a5c-be7c31aff065
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e2f61260b1fceaad3c27a0ce6ab6af28b15582bc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697074"
---
# <a name="azure-blob-download-task"></a><span data-ttu-id="04b25-102">Azure Blob-Download-Task</span><span class="sxs-lookup"><span data-stu-id="04b25-102">Azure Blob Download Task</span></span>
  <span data-ttu-id="04b25-103">Der Azure Blob-Download-Task ermöglicht einem SSIS-Paket das Herunterladen von Dateien aus einem Azure-Blob-Speicher.</span><span class="sxs-lookup"><span data-stu-id="04b25-103">The Azure Blob Download Task enables an SSIS package to download files from an Azure blob storage.</span></span>   
<span data-ttu-id="04b25-104">Um einen **Azure Blob-Download-Task**hinzuzufügen, legen Sie ihn mittels Drag &amp; Drop auf dem SSIS-Designer ab, und doppelklicken Sie darauf, oder klicken Sie mit der rechten Maustaste, und klicken Sie dann auf **Bearbeiten** , um das folgende Dialogfeld **Azure Blob-Download-Task-Editor** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="04b25-104">To add an **Azure Blob Download Task**, drag-drop it to the SSIS Designer, and double-click or right-click and click **Edit** to see the following **Azure Blob Download Task Editor** dialog box.</span></span>  
  
 <span data-ttu-id="04b25-105">Die folgende Tabelle enthält Beschreibungen für die Felder in diesem Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="04b25-105">The following table provides description for the fields in this dialog box.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="04b25-106">**Feld**</span><span class="sxs-lookup"><span data-stu-id="04b25-106">**Field**</span></span>|<span data-ttu-id="04b25-107">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="04b25-107">**Description**</span></span>|  
|<span data-ttu-id="04b25-108">AzureStorageConnection</span><span class="sxs-lookup"><span data-stu-id="04b25-108">AzureStorageConnection</span></span>|<span data-ttu-id="04b25-109">Geben Sie einen vorhandenen Azure Storage-Verbindungs-Manager an, oder erstellen Sie einen neuen, der sich auf ein Azure-Speicherkonto bezieht, das auf den Speicherort der Blob-Dateien verweist.</span><span class="sxs-lookup"><span data-stu-id="04b25-109">Specify an existing Azure Storage Connection Manager or create a new one that refers to an Azure Storage Account, which points to where the blob files are hosted.</span></span>|  
|<span data-ttu-id="04b25-110">BlobContainer</span><span class="sxs-lookup"><span data-stu-id="04b25-110">BlobContainer</span></span>|<span data-ttu-id="04b25-111">Gibt den Namen des Blob-Containers an, der die herunterzuladenden Blob-Dateien enthält.</span><span class="sxs-lookup"><span data-stu-id="04b25-111">Specifies the name of the blob container that contains the blob files to be downloaded.</span></span>|  
|<span data-ttu-id="04b25-112">BlobDirectory</span><span class="sxs-lookup"><span data-stu-id="04b25-112">BlobDirectory</span></span>|<span data-ttu-id="04b25-113">Gibt das Blob-Verzeichnis an, das die herunterzuladenden Blob-Dateien enthält.</span><span class="sxs-lookup"><span data-stu-id="04b25-113">Specifies the blob directory that contains the blob files to be downloaded.</span></span> <span data-ttu-id="04b25-114">Das Blobverzeichnis ist eine virtuelle hierarchische Struktur.</span><span class="sxs-lookup"><span data-stu-id="04b25-114">The blob directory is a virtual hierarchical structure.</span></span>|  
|<span data-ttu-id="04b25-115">LocalDirectory</span><span class="sxs-lookup"><span data-stu-id="04b25-115">LocalDirectory</span></span>|<span data-ttu-id="04b25-116">Gibt das lokale Verzeichnis an, in dem die heruntergeladenen Blob-Dateien gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="04b25-116">Specifies the local directory where the downloaded blob files will be stored.</span></span>|  
|<span data-ttu-id="04b25-117">FileName</span><span class="sxs-lookup"><span data-stu-id="04b25-117">FileName</span></span>|<span data-ttu-id="04b25-118">Gibt einen Namensfilter an, um Dateien mit dem angegebenen Namensmuster auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="04b25-118">Specifies a name filter to select files with the specified name pattern.</span></span> <span data-ttu-id="04b25-119">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="04b25-119">E.g.</span></span> <span data-ttu-id="04b25-120">„MeinArbeitsblatt\*.xls\* “ schließt „MeinArbeitsblatt001.xls“ und „MeinArbeitsblattABC.xlsx“ ein.</span><span class="sxs-lookup"><span data-stu-id="04b25-120">MySheet\*.xls\* includes files such as MySheet001.xls and MySheetABC.xlsx.</span></span>|  
|<span data-ttu-id="04b25-121">TimeRangeFrom/TimeRangeTo</span><span class="sxs-lookup"><span data-stu-id="04b25-121">TimeRangeFrom/TimeRangeTo</span></span>|<span data-ttu-id="04b25-122">Gibt einen Zeitbereichsfilter an.</span><span class="sxs-lookup"><span data-stu-id="04b25-122">Specifies a time range filter.</span></span> <span data-ttu-id="04b25-123">Dateien, die nach **TimeRangeFrom** und vor **TimeRangeTo** geändert wurden, sind eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="04b25-123">Files modified after **TimeRangeFrom** and before **TimeRangeTo** will be included.</span></span>|  
  
  
