---
title: Referenz zur Benutzeroberfläche des Dialogfelds „Dateiverbindungs-Manager hinzufügen“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fileconnection.f1
helpviewer_keywords:
- Add File Connection Manager
ms.assetid: 9370bfb5-5993-4ad8-a9cd-2de53f320f34
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 044d8e2eaae9db17d7155cb354f8d009750f44d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722949"
---
# <a name="add-file-connection-manager-dialog-box-ui-reference"></a><span data-ttu-id="72eb4-102">Referenz zur Benutzeroberfläche des Dialogfelds Dateiverbindungs-Manager hinzufügen</span><span class="sxs-lookup"><span data-stu-id="72eb4-102">Add File Connection Manager Dialog Box UI Reference</span></span>
  <span data-ttu-id="72eb4-103">Mithilfe des Dialogfelds **Dateiverbindungs-Manager hinzufügen** können Sie eine Verbindung zu einer Gruppe von Dateien oder Ordnern definieren.</span><span class="sxs-lookup"><span data-stu-id="72eb4-103">Use the **Add File Connection Manager** dialog box to define a connection to a group of files or folders.</span></span>  
  
 <span data-ttu-id="72eb4-104">Weitere Informationen zum Verbindungs-Manager für mehrere Dateien finden Sie unter [Multiple Files Connection Manager](multiple-files-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="72eb4-104">To learn more about the Multiple Files connection manager, see [Multiple Files Connection Manager](multiple-files-connection-manager.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="72eb4-105">Die integrierten Tasks und Datenflusskomponenten in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] verwenden keinen Verbindungs-Manager für mehrere Dateien.</span><span class="sxs-lookup"><span data-stu-id="72eb4-105">The built-in tasks and data flow components in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] do not use the Multiple Files connection manager.</span></span> <span data-ttu-id="72eb4-106">Sie können den Verbindungs-Manager jedoch im Skripttask oder in der Skriptkomponente verwenden.</span><span class="sxs-lookup"><span data-stu-id="72eb4-106">However, you can use this connection manager in the Script task or Script component.</span></span>  
  
## <a name="options"></a><span data-ttu-id="72eb4-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="72eb4-107">Options</span></span>  
 <span data-ttu-id="72eb4-108">**Verwendungstyp**</span><span class="sxs-lookup"><span data-stu-id="72eb4-108">**Usage type**</span></span>  
 <span data-ttu-id="72eb4-109">Geben Sie den Dateityp an, der vom Verbindungs-Manager für mehrere Dateien verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="72eb4-109">Specify the type of files to use for the multiple files connection manager.</span></span>  
  
|<span data-ttu-id="72eb4-110">value</span><span class="sxs-lookup"><span data-stu-id="72eb4-110">Value</span></span>|<span data-ttu-id="72eb4-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="72eb4-111">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="72eb4-112">**Dateien erstellen**</span><span class="sxs-lookup"><span data-stu-id="72eb4-112">**Create files**</span></span>|<span data-ttu-id="72eb4-113">Der Verbindungs-Manager erstellt die Dateien.</span><span class="sxs-lookup"><span data-stu-id="72eb4-113">The connection manager will create the files.</span></span>|  
|<span data-ttu-id="72eb4-114">**Vorhandene Dateien**</span><span class="sxs-lookup"><span data-stu-id="72eb4-114">**Existing files**</span></span>|<span data-ttu-id="72eb4-115">Der Verbindungs-Manager verwendet vorhandene Dateien.</span><span class="sxs-lookup"><span data-stu-id="72eb4-115">The connection manager will use existing files.</span></span>|  
|<span data-ttu-id="72eb4-116">**Ordner erstellen**</span><span class="sxs-lookup"><span data-stu-id="72eb4-116">**Create folders**</span></span>|<span data-ttu-id="72eb4-117">Der Verbindungs-Manager erstellt die Ordner.</span><span class="sxs-lookup"><span data-stu-id="72eb4-117">The connection manager will create the folders.</span></span>|  
|<span data-ttu-id="72eb4-118">**Vorhandene Ordner**</span><span class="sxs-lookup"><span data-stu-id="72eb4-118">**Existing folders**</span></span>|<span data-ttu-id="72eb4-119">Der Verbindungs-Manager verwendet vorhandene Ordner.</span><span class="sxs-lookup"><span data-stu-id="72eb4-119">The connection manager will use existing folders.</span></span>|  
  
 <span data-ttu-id="72eb4-120">**Dateien / Ordner**</span><span class="sxs-lookup"><span data-stu-id="72eb4-120">**Files / Folders**</span></span>  
 <span data-ttu-id="72eb4-121">Zeigen Sie die hinzugefügten Dateien oder Ordner an, indem Sie die im Folgenden beschriebenen Schaltflächen verwenden.</span><span class="sxs-lookup"><span data-stu-id="72eb4-121">View the files or folders that you have added by using the buttons described as follows.</span></span>  
  
 <span data-ttu-id="72eb4-122">**Add (Hinzufügen)**</span><span class="sxs-lookup"><span data-stu-id="72eb4-122">**Add**</span></span>  
 <span data-ttu-id="72eb4-123">Fügen Sie eine Datei hinzu, indem Sie das Dialogfeld **Dateien auswählen** verwenden, oder fügen Sie mithilfe des Dialogfelds **Ordner suchen** einen Ordner hinzu.</span><span class="sxs-lookup"><span data-stu-id="72eb4-123">Add a file by using the **Select Files** dialog box, or add a folder by using the **Browse for Folder** dialog box.</span></span>  
  
 <span data-ttu-id="72eb4-124">**Bearbeiten**</span><span class="sxs-lookup"><span data-stu-id="72eb4-124">**Edit**</span></span>  
 <span data-ttu-id="72eb4-125">Wählen Sie eine Datei oder einen Ordner aus, und ersetzen Sie diese(n) dann mithilfe des Dialogfelds **Dateien auswählen** bzw. **Ordner suchen** durch eine andere Datei oder einen anderen Ordner.</span><span class="sxs-lookup"><span data-stu-id="72eb4-125">Select a file or folder, and then replace it with a different file or folder by using the **Select Files** or **Browse for Folder** dialog box.</span></span>  
  
 <span data-ttu-id="72eb4-126">**Remove**</span><span class="sxs-lookup"><span data-stu-id="72eb4-126">**Remove**</span></span>  
 <span data-ttu-id="72eb4-127">Wählen Sie eine Datei oder einen Ordner aus, und klicken Sie auf die Schaltfläche **Entfernen** , um das betreffende Objekt aus der Liste zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="72eb4-127">Select a file or folder, and then remove it from the list by using the **Remove** button.</span></span>  
  
 <span data-ttu-id="72eb4-128">**Pfeilschaltflächen**</span><span class="sxs-lookup"><span data-stu-id="72eb4-128">**Arrow buttons**</span></span>  
 <span data-ttu-id="72eb4-129">Wählen Sie eine Datei oder einen Ordner aus, und verschieben Sie das Objekt dann mit den Pfeilschaltflächen nach oben oder unten, um die Reihenfolge des Zugriffs festzulegen.</span><span class="sxs-lookup"><span data-stu-id="72eb4-129">Select a file or folder, and then use the arrow buttons to move it up or down to specify the sequence of access.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72eb4-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="72eb4-130">See Also</span></span>  
 [<span data-ttu-id="72eb4-131">Fehler- und Meldungsreferenz von Integration Services</span><span class="sxs-lookup"><span data-stu-id="72eb4-131">Integration Services Error and Message Reference</span></span>](../integration-services-error-and-message-reference.md)  
  
  
