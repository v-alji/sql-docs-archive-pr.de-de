---
title: Projekteigenschaften (Dialogfeld) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.ssms.isprojectprop.general.f1
- sql12.ssis.ssms.isprojectprop.permissions.f1
ms.assetid: d5cf52f5-1fe2-438a-98a3-fe117360acf8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 259ad48f2b1f33356243635bbaa5426a5199eccf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700142"
---
# <a name="project-properties-dialog-box"></a><span data-ttu-id="b5e70-102">Projekteigenschaften (Dialogfeld)</span><span class="sxs-lookup"><span data-stu-id="b5e70-102">Project Properties Dialog Box</span></span>
  <span data-ttu-id="b5e70-103">Ein [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Projekt entspricht einer Bereitstellungseinheit.</span><span class="sxs-lookup"><span data-stu-id="b5e70-103">An [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project is a unit of deployment.</span></span> <span data-ttu-id="b5e70-104">Jedes Projekt kann Pakete, Parameter und Umgebungsverweise enthalten.</span><span class="sxs-lookup"><span data-stu-id="b5e70-104">Each project can contain packages, parameters, and environment references.</span></span> <span data-ttu-id="b5e70-105">Ein Projekt ist ein sicherungsfähiges Objekt, mit dem Berechtigungen für Datenbankprinzipale definiert werden können.</span><span class="sxs-lookup"><span data-stu-id="b5e70-105">A project is a securable object and can define permissions for database principals.</span></span> <span data-ttu-id="b5e70-106">Wenn ein Projekt erneut bereitgestellt wird, kann die frühere Version des Projekts im [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Katalog gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="b5e70-106">When a project is re-deployed, the previous version of the project can be stored in the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] catalog.</span></span>  
  
 <span data-ttu-id="b5e70-107">Mit Projekt- und Paketparametern können Sie Eigenschaften in Paketen zur Zeit der Ausführung Werte zuweisen.</span><span class="sxs-lookup"><span data-stu-id="b5e70-107">Project parameters and package parameters can be used to assign values to properties within packages at the time of execution.</span></span> <span data-ttu-id="b5e70-108">Einige Parameter erfordern Werte, bevor das Paket ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="b5e70-108">Some parameters require values before the package can be executed.</span></span> <span data-ttu-id="b5e70-109">Parameterwerte, die auf Umgebungsvariablen verweisen, erfordern einen entsprechenden Umgebungsverweis im Projekt, damit die Ausführung erfolgen kann.</span><span class="sxs-lookup"><span data-stu-id="b5e70-109">Parameter values that reference environment variables require that the project has the corresponding environment reference prior to execution.</span></span>  
  
 <span data-ttu-id="b5e70-110">**Was möchten Sie tun?**</span><span class="sxs-lookup"><span data-stu-id="b5e70-110">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="b5e70-111">Öffnen des Dialogfelds "Projekteigenschaften"</span><span class="sxs-lookup"><span data-stu-id="b5e70-111">Open the Project Properties dialog box</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="b5e70-112">Festlegen der Optionen auf der Seite "Allgemein"</span><span class="sxs-lookup"><span data-stu-id="b5e70-112">Set the options on the General page</span></span>](#general)  
  
-   [<span data-ttu-id="b5e70-113">Festlegen der Optionen auf der Seite "Berechtigungen"</span><span class="sxs-lookup"><span data-stu-id="b5e70-113">Set the options on the Permissions page</span></span>](#permissions)  
  
##  <a name="open-the-project-properties-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="b5e70-114">Öffnen des Dialogfelds "Projekteigenschaften"</span><span class="sxs-lookup"><span data-stu-id="b5e70-114">Open the Project Properties dialog box</span></span>  
  
1.  <span data-ttu-id="b5e70-115">Stellen Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]eine Verbindung zum [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Server her.</span><span class="sxs-lookup"><span data-stu-id="b5e70-115">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="b5e70-116">Sie stellen eine Verbindung mit der [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]-Instanz her, die die SSISDB-Datenbank hostet.</span><span class="sxs-lookup"><span data-stu-id="b5e70-116">You're connecting to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the SSISDB database.</span></span>  
  
2.  <span data-ttu-id="b5e70-117">Erweitern Sie im Objekt-Explorer die Struktur, um den Knoten **Integration Services-Kataloge** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b5e70-117">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="b5e70-118">Erweitern Sie den **SSISDB** -Knoten.</span><span class="sxs-lookup"><span data-stu-id="b5e70-118">Expand the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="b5e70-119">Erweitern Sie den Ordner mit dem Projekt, für das Sie die Eigenschaften festlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="b5e70-119">Expand the folder that contains the project that you want to set properties for.</span></span>  
  
5.  <span data-ttu-id="b5e70-120">Klicken Sie mit der rechten Maustaste auf das Projekt, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="b5e70-120">Right-click the project, and then click **Properties**.</span></span>  
  
##  <a name="set-the-options-on-the-general-page"></a><a name="general"></a> <span data-ttu-id="b5e70-121">Festlegen der Optionen auf der Seite "Allgemein"</span><span class="sxs-lookup"><span data-stu-id="b5e70-121">Set the options on the General page</span></span>  
 <span data-ttu-id="b5e70-122">Verwenden Sie die Seite "Allgemein", um Projekteigenschaften anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b5e70-122">Use the General page to view project properties.</span></span>  
  
 <span data-ttu-id="b5e70-123">**Name**</span><span class="sxs-lookup"><span data-stu-id="b5e70-123">**Name**</span></span>  
 <span data-ttu-id="b5e70-124">Listet den Projektnamen auf.</span><span class="sxs-lookup"><span data-stu-id="b5e70-124">Lists the project name.</span></span>  
  
 <span data-ttu-id="b5e70-125">**Bezeichner**</span><span class="sxs-lookup"><span data-stu-id="b5e70-125">**Identifier**</span></span>  
 <span data-ttu-id="b5e70-126">Listet die Projekt-ID auf.</span><span class="sxs-lookup"><span data-stu-id="b5e70-126">Lists the project ID.</span></span>  
  
 <span data-ttu-id="b5e70-127">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="b5e70-127">**Description**</span></span>  
 <span data-ttu-id="b5e70-128">Zeigt die optionale Beschreibung des Projekts an.</span><span class="sxs-lookup"><span data-stu-id="b5e70-128">Displays the optional description of the project.</span></span>  
  
 <span data-ttu-id="b5e70-129">**Projektversion**</span><span class="sxs-lookup"><span data-stu-id="b5e70-129">**Project Version**</span></span>  
 <span data-ttu-id="b5e70-130">Listet die Projektversion auf.</span><span class="sxs-lookup"><span data-stu-id="b5e70-130">Lists the project version.</span></span>  
  
 <span data-ttu-id="b5e70-131">**Bereitstellungsdatum**</span><span class="sxs-lookup"><span data-stu-id="b5e70-131">**Deployment Date**</span></span>  
 <span data-ttu-id="b5e70-132">Listet das Datum und die Uhrzeit der Bereitstellung oder erneuten Bereitstellung des Projekts auf.</span><span class="sxs-lookup"><span data-stu-id="b5e70-132">Lists the date and time the project was deployed or redeployed.</span></span>  
  
##  <a name="set-the-options-on-the-permissions-page"></a><a name="permissions"></a> <span data-ttu-id="b5e70-133">Festlegen der Optionen auf der Seite "Berechtigungen"</span><span class="sxs-lookup"><span data-stu-id="b5e70-133">Set the options on the Permissions page</span></span>  
 <span data-ttu-id="b5e70-134">Auf der Seite **Berechtigungen** können die expliziten Berechtigungen für das Projekt angezeigt oder festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="b5e70-134">Use the **Permissions** page to view and set explicit permissions for the project.</span></span>  
  
 <span data-ttu-id="b5e70-135">Durchsuchen</span><span class="sxs-lookup"><span data-stu-id="b5e70-135">Browse</span></span>  
 <span data-ttu-id="b5e70-136">Klicken Sie auf **Durchsuchen** , um mithilfe des Dialogfelds **Alle Prinzipale durchsuchen** die Benutzer und Rollen auszuwählen, deren Berechtigungen Sie festlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="b5e70-136">Click **Browse** to select users and roles that you want to set permissions for, by using the **Browse All Principals** dialog box.</span></span>  
  
 <span data-ttu-id="b5e70-137">**Name**</span><span class="sxs-lookup"><span data-stu-id="b5e70-137">**Name**</span></span>  
 <span data-ttu-id="b5e70-138">Listet den Namen des Benutzers oder der Rolle auf.</span><span class="sxs-lookup"><span data-stu-id="b5e70-138">Lists the name of the user or role.</span></span>  
  
 <span data-ttu-id="b5e70-139">**Typ**</span><span class="sxs-lookup"><span data-stu-id="b5e70-139">**Type**</span></span>  
 <span data-ttu-id="b5e70-140">Listet den Benutzer- oder Rollentyp auf.</span><span class="sxs-lookup"><span data-stu-id="b5e70-140">Lists the type of user or role.</span></span>  
  
 <span data-ttu-id="b5e70-141">**Berechtigung**</span><span class="sxs-lookup"><span data-stu-id="b5e70-141">**Permission**</span></span>  
 <span data-ttu-id="b5e70-142">Listet die Berechtigungen auf.</span><span class="sxs-lookup"><span data-stu-id="b5e70-142">Lists the permissions.</span></span>  
  
 <span data-ttu-id="b5e70-143">**Grantor**</span><span class="sxs-lookup"><span data-stu-id="b5e70-143">**Grantor**</span></span>  
 <span data-ttu-id="b5e70-144">Listet den Benutzer oder die Rolle auf, die die Berechtigung gewährt.</span><span class="sxs-lookup"><span data-stu-id="b5e70-144">Lists the user or role that grants the permission.</span></span>  
  
 <span data-ttu-id="b5e70-145">**Erteilen**</span><span class="sxs-lookup"><span data-stu-id="b5e70-145">**Grant**</span></span>  
 <span data-ttu-id="b5e70-146">Wenn **Erteilen** ausgewählt wird, wird die Berechtigung für den ausgewählten Benutzer oder die Rolle gewährt.</span><span class="sxs-lookup"><span data-stu-id="b5e70-146">When **Grant** is selected, the permission is granted for the selected user or role.</span></span>  
  
 <span data-ttu-id="b5e70-147">**Deny**</span><span class="sxs-lookup"><span data-stu-id="b5e70-147">**Deny**</span></span>  
 <span data-ttu-id="b5e70-148">Wenn **Verweigern** ausgewählt wird, wird die Berechtigung für den ausgewählten Benutzer oder die Rolle verweigert.</span><span class="sxs-lookup"><span data-stu-id="b5e70-148">When **Deny** is selected, the permission is denied for the selected user or role.</span></span>  
  
  
