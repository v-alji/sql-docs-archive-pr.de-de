---
title: Azure Data Lake Store-Task „Dateisystem“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 01/09/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.DTS.DESIGNER.AFPADLSTASK.F1
- SQL11.DTS.DESIGNER.AFPADLSTASK.F1
ms.assetid: 02b9edd7-6ef9-463e-abbf-e1830bcae875
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1bc37e774c5346190635e50259deb47f2f22a054
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619296"
---
# <a name="azure-data-lake-store-file-system-task"></a><span data-ttu-id="7aa47-102">Azure Data Lake Store-Task „Dateisystem“</span><span class="sxs-lookup"><span data-stu-id="7aa47-102">Azure Data Lake Store File System Task</span></span>

<span data-ttu-id="7aa47-103">Der **Task "Azure Data Lake Store Dateisystem** " ermöglicht es Benutzern, verschiedene Dateisystem Vorgänge auf [Azure Data Lake Store (ADLS)](https://azure.microsoft.com/services/data-lake-store/)auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7aa47-103">The **Azure Data Lake Store File System Task** enables users to perform various file system operations on [Azure Data Lake Store (ADLS)](https://azure.microsoft.com/services/data-lake-store/).</span></span>

<span data-ttu-id="7aa47-104">Ziehen Sie den Azure Data Lake Store-Task „Dateisystem“ von der SSIS-Toolbox in die Designercanvas, um diesen zu einem Paket hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="7aa47-104">To add an Azure Data Lake Store File System Task to a package, drag it from SSIS Toolbox to the designer canvas.</span></span> <span data-ttu-id="7aa47-105">Doppelklicken Sie auf den Task, oder klicken Sie mit der rechten Maustaste auf den Task, und wählen Sie **Bearbeiten**aus, um das Dialogfeld Task-Editor zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="7aa47-105">Then double-click the task, or right-click the task and select **Edit**, to open the task editor dialog box.</span></span>

<span data-ttu-id="7aa47-106">Mit der **Operation**-Eigenschaft wird der auszuführende Dateisystemvorgang angegeben.</span><span class="sxs-lookup"><span data-stu-id="7aa47-106">The **Operation** property specifies the file system operation to perform.</span></span> <span data-ttu-id="7aa47-107">Die folgenden Operatoren werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="7aa47-107">The following operations are supported.</span></span>

* <span data-ttu-id="7aa47-108">**CopyToADLS:** Hochladen von Dateien in ADLS.</span><span class="sxs-lookup"><span data-stu-id="7aa47-108">**CopyToADLS:** Upload files to ADLS.</span></span>
* <span data-ttu-id="7aa47-109">**CopyFromADLS:** Herunterladen von Dateien von ADLS.</span><span class="sxs-lookup"><span data-stu-id="7aa47-109">**CopyFromADLS:** Download files from ADLS.</span></span>

<span data-ttu-id="7aa47-110">Sie müssen für jeden Vorgang einen Azure Data Lake-Verbindungs-Manager angeben.</span><span class="sxs-lookup"><span data-stu-id="7aa47-110">For any operation, you have to specify an Azure Data Lake connection manager.</span></span>

<span data-ttu-id="7aa47-111">Hier sind die Beschreibungen der Eigenschaften, die für jeden Vorgang spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="7aa47-111">Here are the descriptions of the properties specific to each operation.</span></span>

## <a name="copytoadls"></a><span data-ttu-id="7aa47-112">CopyToADLS</span><span class="sxs-lookup"><span data-stu-id="7aa47-112">CopyToADLS</span></span>

* <span data-ttu-id="7aa47-113">**Localdirectory:** Gibt das Quellverzeichnis an, das hoch zuladende Dateien enthält.</span><span class="sxs-lookup"><span data-stu-id="7aa47-113">**LocalDirectory:** Specifies the source directory which contains files to upload.</span></span>
* <span data-ttu-id="7aa47-114">**FileNamePattern:** legt einen Dateinamensfilter für Quelldateien fest</span><span class="sxs-lookup"><span data-stu-id="7aa47-114">**FileNamePattern:** Specifies a file name filter for source files.</span></span> <span data-ttu-id="7aa47-115">Nur Dateien, deren Name mit dem angegebenen Muster übereinstimmt, werden hochgeladen.</span><span class="sxs-lookup"><span data-stu-id="7aa47-115">Only files whose name matches the specified pattern will be uploaded.</span></span> <span data-ttu-id="7aa47-116">Die Platzhalterzeichen `*` und `?` werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7aa47-116">Wildcards `*` and `?` are supported.</span></span>
* <span data-ttu-id="7aa47-117">**SearchRecursively:** gibt an, ob das Quellverzeichnis rekursiv nach hochzuladenden Dateien durchsucht werden soll</span><span class="sxs-lookup"><span data-stu-id="7aa47-117">**SearchRecursively:** Specifies whether to search recursively within the source directory for files to upload.</span></span>
* <span data-ttu-id="7aa47-118">**AzureDataLakeDirectory:** gibt das ADLS-Zielverzeichnis an, in das Dateien hochgeladen werden</span><span class="sxs-lookup"><span data-stu-id="7aa47-118">**AzureDataLakeDirectory:** Specifies the ADLS destination directory to upload files to.</span></span>
* <span data-ttu-id="7aa47-119">**Datei Ablauf:** Gibt ein Ablaufdatum und eine Uhrzeit für die in ADLS hochgeladenen Dateien an, oder lassen Sie diese Eigenschaft leer, um anzugeben, dass die Dateien nie ablaufen.</span><span class="sxs-lookup"><span data-stu-id="7aa47-119">**FileExpiry:** Specifies an expiration date and time for the files uploaded to ADLS, or leave this property blank to indicate that the files never expire.</span></span>

## <a name="copyfromadls"></a><span data-ttu-id="7aa47-120">CopyFromADLS</span><span class="sxs-lookup"><span data-stu-id="7aa47-120">CopyFromADLS</span></span>

* <span data-ttu-id="7aa47-121">**AzureDataLakeDirectory:** gibt das ADLS-Quellverzeichnis an, das die herunterzuladenden Dateien enthält</span><span class="sxs-lookup"><span data-stu-id="7aa47-121">**AzureDataLakeDirectory:** Specifies the ADLS source directory which contains the files to download.</span></span>
* <span data-ttu-id="7aa47-122">**SearchRecursively:** gibt an, ob das Quellverzeichnis rekursiv nach herunterzuladenden Dateien durchsucht werden soll</span><span class="sxs-lookup"><span data-stu-id="7aa47-122">**SearchRecursively:** Specifies whether to search recursively within the source directory for files to download.</span></span>
* <span data-ttu-id="7aa47-123">**LocalDirectory:** gibt das Zielverzeichnis an, in dem heruntergeladene Dateien gespeichert werden</span><span class="sxs-lookup"><span data-stu-id="7aa47-123">**LocalDirectory:** Specifies the destination directory to store downloaded files.</span></span>
