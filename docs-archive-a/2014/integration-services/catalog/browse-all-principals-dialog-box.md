---
title: Alle Prinzipale durchsuchen (Dialogfeld) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.ssms.browseprincipals.f1
ms.assetid: f11d2c5e-ee05-45f3-8dc2-0feb99b2f76f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c204411a4daace27745e46269cbcfa0ed33f323f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609387"
---
# <a name="browse-all-principals-dialog-box"></a><span data-ttu-id="811d2-102">Alle Prinzipale durchsuchen (Dialogfeld)</span><span class="sxs-lookup"><span data-stu-id="811d2-102">Browse All Principals Dialog Box</span></span>
  <span data-ttu-id="811d2-103">Wählen Sie über das Dialogfeld **Alle Prinzipale durchsuchen** einen Datenbankprinzipal aus und ändern Sie die Berechtigungen des Prinzipals für das ausgewählte Projekt oder alle in einem ausgewählten Ordner enthaltenen Projekte.</span><span class="sxs-lookup"><span data-stu-id="811d2-103">Use the **Browse All Principals** dialog box to select a database principal to change the principal's permissions on the selected project or on all projects contained in a selected folder.</span></span>  
  
 <span data-ttu-id="811d2-104">**Was möchten Sie tun?**</span><span class="sxs-lookup"><span data-stu-id="811d2-104">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="811d2-105">Öffnen des Dialogfelds "Alle Prinzipale durchsuchen"</span><span class="sxs-lookup"><span data-stu-id="811d2-105">Open the Browse All Principals dialog box</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="811d2-106">Konfigurieren der Optionen</span><span class="sxs-lookup"><span data-stu-id="811d2-106">Configure the Options</span></span>](#options)  
  
##  <a name="open-the-browse-all-principals-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="811d2-107">Öffnen des Dialogfelds "Alle Prinzipale durchsuchen"</span><span class="sxs-lookup"><span data-stu-id="811d2-107">Open the Browse All Principals dialog box</span></span>  
  
1.  <span data-ttu-id="811d2-108">Stellen Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]eine Verbindung zum [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Server her.</span><span class="sxs-lookup"><span data-stu-id="811d2-108">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="811d2-109">Sie stellen eine Verbindung mit der [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]-Instanz her, die den SSISDB-Katalog hostet.</span><span class="sxs-lookup"><span data-stu-id="811d2-109">You're connecting to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the SSISDB catalog.</span></span>  
  
2.  <span data-ttu-id="811d2-110">Erweitern Sie im Objekt-Explorer die Struktur, um den Knoten **Integration Services-Kataloge** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="811d2-110">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="811d2-111">Erweitern Sie den **SSISDB** -Knoten.</span><span class="sxs-lookup"><span data-stu-id="811d2-111">Expand the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="811d2-112">Klicken Sie zum Ändern der Berechtigungen des Prinzipals für alle in einem ausgewählten Ordner enthaltenen Projekte mit der rechten Maustaste auf den Ordner, und klicken Sie anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="811d2-112">To change the principal's permissions on all projects contained in a selected folder, right-click the folder and then click **Properties**.</span></span>  
  
     <span data-ttu-id="811d2-113">Wenn Sie die Berechtigungen des Prinzipals für ein ausgewähltes Projekt ändern möchten, erweitern Sie den Ordner, der das Projekt enthält, klicken Sie mit der rechten Maustaste auf das Projekt, und klicken Sie anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="811d2-113">To change the principal's permissions on a selected project, expand the folder that contains the project, right-click the project, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="811d2-114">Wählen Sie die Seite **Berechtigungen** aus, und klicken Sie dann auf **Durchsuchen**.</span><span class="sxs-lookup"><span data-stu-id="811d2-114">Select the **Permissions** page, and then click **Browse**.</span></span>  
  
##  <a name="configure-the-options"></a><a name="options"></a> <span data-ttu-id="811d2-115">Konfigurieren der Optionen</span><span class="sxs-lookup"><span data-stu-id="811d2-115">Configure the Options</span></span>  
 <span data-ttu-id="811d2-116">Auf dieser Seite werden die Prinzipale aus der Katalogsicht sys.database_principals der SSISDB-Datenbank angezeigt.</span><span class="sxs-lookup"><span data-stu-id="811d2-116">This page displays the principals from the catalog view, sys.database_principals, of the SSISDB database.</span></span>  
  
 <span data-ttu-id="811d2-117">Durch Auswählen von Prinzipalen werden diese der Liste **Anmeldenamen oder Rollen** auf der Seite **Berechtigungen** des übergeordneten Dialogfelds hinzugefügt, sobald Sie auf **OK** geklickt und das Dialogfeld **Alle Prinzipale durchsuchen** geschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="811d2-117">Selecting principals adds them to the **Logins or roles** list on the **Permissions** page of the parent dialog box when you click **OK** and close the **Browse All Principals** dialog box.</span></span> <span data-ttu-id="811d2-118">Nachdem Sie die Prinzipale der Liste **Anmeldenamen oder Rollen** hinzugefügt haben, können Sie die entsprechenden Berechtigungen für das ausgewählte Projekt ändern.</span><span class="sxs-lookup"><span data-stu-id="811d2-118">After adding principals to the **Logins or roles** list, you can change their permissions on the selected project.</span></span>  
  
 <span data-ttu-id="811d2-119">**Spaltenauswahl**</span><span class="sxs-lookup"><span data-stu-id="811d2-119">**Selection column**</span></span>  
 <span data-ttu-id="811d2-120">Mit dieser Option können Sie den Prinzipal der Liste **Anmeldenamen oder Rollen** auf der Seite **Berechtigungen** im übergeordneten Dialogfeld hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="811d2-120">Select to add the principal to the **Logins or roles** list on the **Permissions** page of the parent dialog box.</span></span>  
  
 <span data-ttu-id="811d2-121">**Symbolspalte**</span><span class="sxs-lookup"><span data-stu-id="811d2-121">**Icon column**</span></span>  
 <span data-ttu-id="811d2-122">Ein Symbol, das dem **Typ** des Prinzipals entspricht.</span><span class="sxs-lookup"><span data-stu-id="811d2-122">An icon that corresponds to the **Type** of the principal.</span></span>  
  
 <span data-ttu-id="811d2-123">**Name**</span><span class="sxs-lookup"><span data-stu-id="811d2-123">**Name**</span></span>  
 <span data-ttu-id="811d2-124">Der Name des Prinzipals.</span><span class="sxs-lookup"><span data-stu-id="811d2-124">The name of the principal.</span></span>  
  
 <span data-ttu-id="811d2-125">**Typ**</span><span class="sxs-lookup"><span data-stu-id="811d2-125">**Type**</span></span>  
 <span data-ttu-id="811d2-126">Der Typ des Prinzipals.</span><span class="sxs-lookup"><span data-stu-id="811d2-126">The type of the principal.</span></span> <span data-ttu-id="811d2-127">Häufig verwendeten Typen sind folgende:</span><span class="sxs-lookup"><span data-stu-id="811d2-127">The common types are:</span></span>  
  
-   <span data-ttu-id="811d2-128">SQL-Benutzer</span><span class="sxs-lookup"><span data-stu-id="811d2-128">SQL User</span></span>  
  
-   <span data-ttu-id="811d2-129">Windows-Benutzer</span><span class="sxs-lookup"><span data-stu-id="811d2-129">Windows User</span></span>  
  
-   <span data-ttu-id="811d2-130">Datenbankrolle</span><span class="sxs-lookup"><span data-stu-id="811d2-130">Database Role</span></span>  
  
  
