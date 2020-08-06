---
title: Ziel-Editor für Rohdatendateien (Seite Verbindungs-Manager) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.rawfiledestinationconnectionmanager.f1
ms.assetid: a0ec9643-3b44-4467-b855-f45ae4794f7f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a693591921a5669eb9bc8160f0be076ab4d6869b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696953"
---
# <a name="raw-file-destination-editor-connection-manager-page"></a><span data-ttu-id="860bb-102">Ziel-Editor für Rohdatendateien (Seite Verbindungs-Manager)</span><span class="sxs-lookup"><span data-stu-id="860bb-102">Raw File Destination Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="860bb-103">Verwenden Sie den Ziel-Editor für Rohdatendateien zum Konfigurieren des Rohdatendatei-Ziels, um Rohdaten in eine Datei zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="860bb-103">Use the Raw File Destination Editor to configure the Raw File destination to write raw data to a file.</span></span>  
  
 <span data-ttu-id="860bb-104">**Was möchten Sie tun?**</span><span class="sxs-lookup"><span data-stu-id="860bb-104">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="860bb-105">Öffnen des Ziel-Editors für Rohdatendateien</span><span class="sxs-lookup"><span data-stu-id="860bb-105">Open the Raw File Destination Editor</span></span>](#open)  
  
-   [<span data-ttu-id="860bb-106">Festlegen der Optionen auf der Registerkarte "Verbindungs-Manager"</span><span class="sxs-lookup"><span data-stu-id="860bb-106">Set options on the Connection Manager tab</span></span>](#connection)  
  
-   [<span data-ttu-id="860bb-107">Festlegen von Optionen auf der Registerkarte "Spalten"</span><span class="sxs-lookup"><span data-stu-id="860bb-107">Set options on the Columns tab</span></span>](#mapping)  
  
##  <a name="open-the-raw-file-destination-editor"></a><a name="open"></a><span data-ttu-id="860bb-108">Öffnen des Ziel-Editors für Rohdatendateien</span><span class="sxs-lookup"><span data-stu-id="860bb-108">Open the Raw File Destination Editor</span></span>  
  
1.  <span data-ttu-id="860bb-109">Fügen Sie das Rohdatendatei-Ziel in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] einem [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]-Paket hinzu.</span><span class="sxs-lookup"><span data-stu-id="860bb-109">Add the Raw File destination to an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package, in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="860bb-110">Klicken Sie mit der rechten Maustaste auf die Komponente, und klicken Sie anschließend auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="860bb-110">Right-click the component and then click **Edit**.</span></span>  
  
##  <a name="set-options-on-the-connection-manager-tab"></a><a name="connection"></a><span data-ttu-id="860bb-111">Festlegen von Optionen auf der Registerkarte "Verbindungs-Manager"</span><span class="sxs-lookup"><span data-stu-id="860bb-111">Set options on the Connection Manager tab</span></span>  
 <span data-ttu-id="860bb-112">**Zugriffsmodus**</span><span class="sxs-lookup"><span data-stu-id="860bb-112">**Access mode**</span></span>  
 <span data-ttu-id="860bb-113">Wählen Sie aus, wie der Dateiname angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="860bb-113">Select how the file name is specified.</span></span> <span data-ttu-id="860bb-114">Wählen Sie **Dateiname** aus, um den Dateinamen und Pfad direkt einzugeben, oder **Dateiname aus Variable** , um eine Variable anzugeben, die den Dateinamen enthält.</span><span class="sxs-lookup"><span data-stu-id="860bb-114">Select **File name** to enter the file name and path directly, of **File name from variable** to specify a variable that contains the file name.</span></span>  
  
 <span data-ttu-id="860bb-115">**Dateiname** oder **Variablenname**</span><span class="sxs-lookup"><span data-stu-id="860bb-115">**File name** or **Variable name**</span></span>  
 <span data-ttu-id="860bb-116">Geben Sie den Namen und Pfad der Rohdatendatei ein, oder wählen Sie die Variable aus, die den Dateinamen enthält.</span><span class="sxs-lookup"><span data-stu-id="860bb-116">Enter the name and path of the raw file, or select the variable that contains the file name.</span></span>  
  
 <span data-ttu-id="860bb-117">**Schreiboption**</span><span class="sxs-lookup"><span data-stu-id="860bb-117">**Write option**</span></span>  
 <span data-ttu-id="860bb-118">Wählen Sie die Methode aus, die zum Erstellen und Schreiben in die Datei verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="860bb-118">Select the method used to create and write to the file.</span></span>  
  
 <span data-ttu-id="860bb-119">**Generieren einer anfänglichen Rohdatendatei**</span><span class="sxs-lookup"><span data-stu-id="860bb-119">**Generate initial raw file**</span></span>  
 <span data-ttu-id="860bb-120">Klicken Sie auf die Schaltfläche, um eine leere Rohdatendatei zu generieren, die nur die Spalten (Nur-Metadatendatei) enthält, ohne dass das Paket ausgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="860bb-120">Click the button to generate an empty raw file that contains only the columns (metadata-only file), without having to run the package.</span></span> <span data-ttu-id="860bb-121">Die Datei enthält die Spalten, die Sie auf der Seite **Spalten** von **Ziel-Editor für Rohdatendateien**ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="860bb-121">The file contains the columns that you selected on the **Columns** page of the **Raw File Destination Editor**.</span></span> <span data-ttu-id="860bb-122">Sie können die Rohdatendatei-Quelle auf diese Nur-Metadaten-Datei verweisen.</span><span class="sxs-lookup"><span data-stu-id="860bb-122">You can point the Raw File source to this metadata-only file.</span></span>  
  
 <span data-ttu-id="860bb-123">Wenn Sie auf **Anfängliche Rohdatendatei generieren**klicken, wird ein Meldungsfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="860bb-123">When you click **Generate initial raw file**, a message box appears.</span></span> <span data-ttu-id="860bb-124">Klicken Sie auf **OK** , um die Erstellung der Datei fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="860bb-124">Click **OK** to proceed with creating the file.</span></span> <span data-ttu-id="860bb-125">Klicken Sie auf **Abbrechen** , um eine andere Liste von Spalten auf der Seite **Spalten** auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="860bb-125">Click **Cancel** to select a different list of columns on the **Columns** page.</span></span>  
  
##  <a name="set-options-on-the-columns-tab"></a><a name="mapping"></a><span data-ttu-id="860bb-126">Festlegen von Optionen auf der Registerkarte "Spalten"</span><span class="sxs-lookup"><span data-stu-id="860bb-126">Set options on the Columns tab</span></span>  
 <span data-ttu-id="860bb-127">**Verfügbare Eingabespalten**</span><span class="sxs-lookup"><span data-stu-id="860bb-127">**Available Input Columns**</span></span>  
 <span data-ttu-id="860bb-128">Wählen Sie mindestens eine Eingabespalte aus, die in die Rohdatendatei geschrieben werden soll.</span><span class="sxs-lookup"><span data-stu-id="860bb-128">Select one or more input columns to write to the raw file.</span></span>  
  
 <span data-ttu-id="860bb-129">**Eingabespalte**</span><span class="sxs-lookup"><span data-stu-id="860bb-129">**Input Column**</span></span>  
 <span data-ttu-id="860bb-130">Dieser Tabelle wird automatisch eine Eingabespalte hinzugefügt, wenn Sie sie unter **Verfügbare Eingabespalten**auswählen. Alternativ können Sie die Eingabespalte direkt in dieser Tabelle auswählen.</span><span class="sxs-lookup"><span data-stu-id="860bb-130">An input column is automatically added to this table when you select it under **Available Input Columns**, or you can select the input column directly in this table.</span></span>  
  
 <span data-ttu-id="860bb-131">**Ausgabealias**</span><span class="sxs-lookup"><span data-stu-id="860bb-131">**Output Alias**</span></span>  
 <span data-ttu-id="860bb-132">Geben Sie einen anderen Namen an, der für die Ausgabespalte verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="860bb-132">Specify an alternate name to use for the output column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="860bb-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="860bb-133">See Also</span></span>  
 [<span data-ttu-id="860bb-134">Rohdatendatei-Ziel</span><span class="sxs-lookup"><span data-stu-id="860bb-134">Raw File Destination</span></span>](data-flow/raw-file-destination.md)  
  
  
