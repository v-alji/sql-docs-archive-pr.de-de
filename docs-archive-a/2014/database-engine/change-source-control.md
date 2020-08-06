---
title: Quell Code Verwaltung ändern | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- IDD_SCC_CONNECTION_DIALOG
helpviewer_keywords:
- Change Source Control dialog box
ms.assetid: e6a5d83c-5809-4c56-907a-73d0c7ccdd7a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 55831529243608e8c71972a31009e5672fb0234f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619366"
---
# <a name="change-source-control"></a><span data-ttu-id="761dd-102">Quellcodeverwaltung ändern</span><span class="sxs-lookup"><span data-stu-id="761dd-102">Change Source Control</span></span>
  <span data-ttu-id="761dd-103">Erstellt und verwaltet die Verbindungen und Bindungen, über die eine lokal gespeicherte Projektmappe bzw. ein Projekt mit einem Ordner in der Datenbank für die Quellcodeverwaltung verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="761dd-103">Creates and manages the connections and bindings that link a locally saved solution or project to a source control database folder.</span></span>  
  
## <a name="dialog-box-access"></a><span data-ttu-id="761dd-104">Zugriff auf das Dialogfeld</span><span class="sxs-lookup"><span data-stu-id="761dd-104">Dialog Box Access</span></span>  
 <span data-ttu-id="761dd-105">Wählen Sie in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] ein Element im Projektmappen-Explorer aus.</span><span class="sxs-lookup"><span data-stu-id="761dd-105">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], select an item in Solution Explorer.</span></span> <span data-ttu-id="761dd-106">Klicken Sie im Menü **Datei** auf **Quell**Code Verwaltung, und **ändern**Sie dann Quell Code Verwaltung.</span><span class="sxs-lookup"><span data-stu-id="761dd-106">On the **File** menu, click **Source Control**, and then **Change Source Control**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="761dd-107">Als Alternative können Sie auch im Projektmappen-Explorer mit der rechten Maustaste auf das entsprechende Element klicken, um das Dialogfeld aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="761dd-107">This dialog box is also available by right-clicking the item in Solution Explorer.</span></span>  
  
## <a name="options"></a><span data-ttu-id="761dd-108">Tastatur</span><span class="sxs-lookup"><span data-stu-id="761dd-108">Options</span></span>  
 <span data-ttu-id="761dd-109">**Zwick**</span><span class="sxs-lookup"><span data-stu-id="761dd-109">**Bind**</span></span>  
 <span data-ttu-id="761dd-110">Ordnet ausgewählte Elemente einem angegebenen Speicherort auf dem Quellcode-Verwaltungsserver zu.</span><span class="sxs-lookup"><span data-stu-id="761dd-110">Associate selected items with a specified source control server location.</span></span> <span data-ttu-id="761dd-111">So können Sie mit dieser Schaltfläche beispielsweise den letzten bekannten Ordner und die Datenbank auf dem Quellcode-Verwaltungsserver binden.</span><span class="sxs-lookup"><span data-stu-id="761dd-111">For example, you can use this button to bind to the last known source control server folder and database.</span></span> <span data-ttu-id="761dd-112">Wenn kein zuletzt verwendeter Serverordner bzw. eine Serverdatenbank gefunden wird, werden Sie aufgefordert einen anderen bzw. eine andere anzugeben.</span><span class="sxs-lookup"><span data-stu-id="761dd-112">If a recent server folder or database cannot be found, you are prompted to specify another.</span></span>  
  
 <span data-ttu-id="761dd-113">**Durchsuchen**</span><span class="sxs-lookup"><span data-stu-id="761dd-113">**Browse**</span></span>  
 <span data-ttu-id="761dd-114">Navigiert zu einem neuen Speicherort auf dem Quellcode-Verwaltungsserver für das angegebene Element.</span><span class="sxs-lookup"><span data-stu-id="761dd-114">Navigate to a new source control server location for the specified item.</span></span>  
  
 <span data-ttu-id="761dd-115">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="761dd-115">**Columns**</span></span>  
 <span data-ttu-id="761dd-116">Identifizieren Sie die anzuzeigenden Spalten und die Reihenfolge, in der Sie angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="761dd-116">Identify columns to display and the order in which they are displayed.</span></span>  
  
 <span data-ttu-id="761dd-117">**Herstellen einer Verbindung**</span><span class="sxs-lookup"><span data-stu-id="761dd-117">**Connect**</span></span>  
 <span data-ttu-id="761dd-118">Erstellt eine Verbindung zwischen ausgewählten Elementen und dem Quellcode-Verwaltungsserver.</span><span class="sxs-lookup"><span data-stu-id="761dd-118">Create a connection between selected items and the source control server.</span></span>  
  
 <span data-ttu-id="761dd-119">**Verbunden**</span><span class="sxs-lookup"><span data-stu-id="761dd-119">**Connected**</span></span>  
 <span data-ttu-id="761dd-120">Zeigt den Verbindungsstatus einer ausgewählten Projektmappe bzw. eines Projekts an.</span><span class="sxs-lookup"><span data-stu-id="761dd-120">Displays the connection status of a selected solution or project.</span></span>  
  
 <span data-ttu-id="761dd-121">**Disconnect** (Trennen)</span><span class="sxs-lookup"><span data-stu-id="761dd-121">**Disconnect**</span></span>  
 <span data-ttu-id="761dd-122">Trennt die Verbindung der lokalen Kopie einer Projektmappe bzw. eines Projekts auf Ihrem Computer zu ihrer Masterkopie in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="761dd-122">Disconnect the local copy of a solution or project on your computer from its master copy in the database.</span></span> <span data-ttu-id="761dd-123">Verwenden Sie diesen Befehl, bevor Sie Ihren Computer vom Quellcode-Verwaltungsserver trennen (z. B., wenn Sie auf Ihrem Laptop offline arbeiten).</span><span class="sxs-lookup"><span data-stu-id="761dd-123">Use this command before disconnecting your computer from the source control server, for example, when working offline on your laptop.</span></span>  
  
 <span data-ttu-id="761dd-124">**OK**</span><span class="sxs-lookup"><span data-stu-id="761dd-124">**OK**</span></span>  
 <span data-ttu-id="761dd-125">Nimmt die im Dialogfeld vorgenommenen Änderungen an.</span><span class="sxs-lookup"><span data-stu-id="761dd-125">Accept changes made in the dialog box.</span></span>  
  
 <span data-ttu-id="761dd-126">**Anbieter**</span><span class="sxs-lookup"><span data-stu-id="761dd-126">**Provider**</span></span>  
 <span data-ttu-id="761dd-127">Zeigt den Namen Ihres Quellcodeverwaltungs-Plug-Ins an.</span><span class="sxs-lookup"><span data-stu-id="761dd-127">Displays the name of your source control plug-in.</span></span>  
  
 <span data-ttu-id="761dd-128">**Aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="761dd-128">**Refresh**</span></span>  
 <span data-ttu-id="761dd-129">Aktualisiert die in diesem Dialogfeld aufgelisteten Verbindungsinformationen für alle Projekte.</span><span class="sxs-lookup"><span data-stu-id="761dd-129">Refreshes the connection information for all projects listed in this dialog box.</span></span>  
  
 <span data-ttu-id="761dd-130">**Serverbindung**</span><span class="sxs-lookup"><span data-stu-id="761dd-130">**Server Binding**</span></span>  
 <span data-ttu-id="761dd-131">Gibt die Bindung des Elements an einen Quellcode-Verwaltungsserver an.</span><span class="sxs-lookup"><span data-stu-id="761dd-131">Indicates the item's binding to a source control server.</span></span>  
  
 <span data-ttu-id="761dd-132">**Servername**</span><span class="sxs-lookup"><span data-stu-id="761dd-132">**Server Name**</span></span>  
 <span data-ttu-id="761dd-133">Zeigt den Namen des Quellcode-Verwaltungsservers an, an den die betreffende Projektmappe bzw. das Projekt gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="761dd-133">Displays the name of the source control server to which the corresponding solution or project is bound.</span></span>  
  
 <span data-ttu-id="761dd-134">**Projektmappe/Projekt**</span><span class="sxs-lookup"><span data-stu-id="761dd-134">**Solution/Project**</span></span>  
 <span data-ttu-id="761dd-135">Zeigt die Namen der einzelnen Projektmappen und Projekte in der aktuellen Auswahl an.</span><span class="sxs-lookup"><span data-stu-id="761dd-135">Displays the name of each solution and project in the current selection.</span></span>  
  
 <span data-ttu-id="761dd-136">**Sort**</span><span class="sxs-lookup"><span data-stu-id="761dd-136">**Sort**</span></span>  
 <span data-ttu-id="761dd-137">Sortiert die Reihenfolge der angezeigten Spalten.</span><span class="sxs-lookup"><span data-stu-id="761dd-137">Sort the order of displayed columns.</span></span>  
  
 <span data-ttu-id="761dd-138">**Status**</span><span class="sxs-lookup"><span data-stu-id="761dd-138">**Status**</span></span>  
 <span data-ttu-id="761dd-139">Identifiziert den Bindungs- und Verbindungsstatus eines Elements.</span><span class="sxs-lookup"><span data-stu-id="761dd-139">Identifies the binding and connection status of an item.</span></span> <span data-ttu-id="761dd-140">Folgende Optionen sind möglich:</span><span class="sxs-lookup"><span data-stu-id="761dd-140">Possible options are:</span></span>  
  
|<span data-ttu-id="761dd-141">**Option**</span><span class="sxs-lookup"><span data-stu-id="761dd-141">**Option**</span></span>|<span data-ttu-id="761dd-142">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="761dd-142">**Description**</span></span>|  
|----------------|---------------------|  
|<span data-ttu-id="761dd-143">Gültig</span><span class="sxs-lookup"><span data-stu-id="761dd-143">Valid</span></span>|<span data-ttu-id="761dd-144">Das Element ist ordnungsgemäß an den Serverordner, zu dem es gehört, gebunden und mit ihm verbunden.</span><span class="sxs-lookup"><span data-stu-id="761dd-144">The item is correctly bound and connected to the server folder to which it belongs.</span></span>|  
|<span data-ttu-id="761dd-145">Ungültig</span><span class="sxs-lookup"><span data-stu-id="761dd-145">Invalid</span></span>|<span data-ttu-id="761dd-146">Das Element ist ordnungsgemäß an den Serverordner, zu dem es gehört, gebunden bzw. von ihm getrennt.</span><span class="sxs-lookup"><span data-stu-id="761dd-146">The item is incorrectly bound to or disconnected from the folder to which it belongs.</span></span> <span data-ttu-id="761dd-147">Verwenden Sie den Befehl **zur Quell Code Verwaltung hinzufügen** anstelle von **Bind** für dieses Element.</span><span class="sxs-lookup"><span data-stu-id="761dd-147">Use the **Add to Source Control** command instead of **Bind** for this item.</span></span>|  
|<span data-ttu-id="761dd-148">Unknown</span><span class="sxs-lookup"><span data-stu-id="761dd-148">Unknown</span></span>|<span data-ttu-id="761dd-149">Der Status des Elements, das sich unter Quellcodeverwaltung befindet, wurde noch nicht ermittelt.</span><span class="sxs-lookup"><span data-stu-id="761dd-149">The status of the item under source control has not yet been determined.</span></span>|  
|<span data-ttu-id="761dd-150">Nicht gesteuert</span><span class="sxs-lookup"><span data-stu-id="761dd-150">Not Controlled</span></span>|<span data-ttu-id="761dd-151">Das Element wurde nicht unter Quellcodeverwaltung gestellt.</span><span class="sxs-lookup"><span data-stu-id="761dd-151">The item has not been placed under source control.</span></span>|  
  
 <span data-ttu-id="761dd-152">**Aufheben der Bindung**</span><span class="sxs-lookup"><span data-stu-id="761dd-152">**Unbind**</span></span>  
 <span data-ttu-id="761dd-153">Zeigt das Dialogfeld **Quell** Code Verwaltung an, in dem Sie ausgewählte Elemente aus der Quell Code Verwaltung entfernen und die Zuordnung der Elemente zu Ihren aktuellen Ordnern dauerhaft aufheben können.</span><span class="sxs-lookup"><span data-stu-id="761dd-153">Display the **Source Control** dialog box to allow you to remove selected items from source control and permanently disassociate the items from their present folders.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="761dd-154">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="761dd-154">See Also</span></span>  
 [<span data-ttu-id="761dd-155">Quellcodeverwaltung des Projektmappen-Explorers</span><span class="sxs-lookup"><span data-stu-id="761dd-155">Solution Explorer Source Control</span></span>](../../2014/database-engine/solution-explorer-source-control.md)  
  
  
