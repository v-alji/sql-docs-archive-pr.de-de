---
title: Konfigurieren (Dialogfeld) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.SSIS.SSMS.ISPROJECTPROP.PARAMETERS.F1
- SQL12.SSIS.SSMS.ISPROJECTPROP.REFERENCES.F1
- sql12.dts.designer.configure.f1
ms.assetid: 10183c8d-b1be-420f-972a-96ea97d4f4d8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 857baf3421f2744144e10b0df0b770538f533192
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619289"
---
# <a name="configure-dialog-box"></a><span data-ttu-id="ed935-102">Konfigurieren (Dialogfeld)</span><span class="sxs-lookup"><span data-stu-id="ed935-102">Configure Dialog Box</span></span>
  <span data-ttu-id="ed935-103">Verwenden Sie das Dialogfeld **Konfigurieren** , um Parameter, Verbindungs-Manager und Umgebungsverweise für Pakete und Projekte zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ed935-103">Use the **Configure** dialog box to configure parameters, connection managers, and references to environments, for packages and projects.</span></span>  
  
 <span data-ttu-id="ed935-104">**Was möchten Sie tun?**</span><span class="sxs-lookup"><span data-stu-id="ed935-104">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="ed935-105">Öffnen des Dialogfelds 'Konfigurieren'</span><span class="sxs-lookup"><span data-stu-id="ed935-105">Open the Configure Dialog Box</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="ed935-106">Festlegen der Optionen auf der Seite 'Parameter'</span><span class="sxs-lookup"><span data-stu-id="ed935-106">Set the options on the Parameters page</span></span>](#parameter)  
  
-   [<span data-ttu-id="ed935-107">Festlegen der Optionen auf der Seite 'Verweise'</span><span class="sxs-lookup"><span data-stu-id="ed935-107">Set the options on the References page</span></span>](#references)  
  
##  <a name="open-the-configure-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="ed935-108">Öffnen des Dialogfelds 'Konfigurieren'</span><span class="sxs-lookup"><span data-stu-id="ed935-108">Open the Configure Dialog Box</span></span>  
  
1.  <span data-ttu-id="ed935-109">Stellen Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]eine Verbindung zum [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Server her.</span><span class="sxs-lookup"><span data-stu-id="ed935-109">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="ed935-110">Sie stellen eine Verbindung mit der [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]-Instanz her, die die SSISDB-Datenbank hostet.</span><span class="sxs-lookup"><span data-stu-id="ed935-110">You're connecting to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the SSISDB database.</span></span>  
  
2.  <span data-ttu-id="ed935-111">Erweitern Sie im Objekt-Explorer die Struktur, um den Knoten **Integration Services-Kataloge** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ed935-111">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="ed935-112">Erweitern Sie den **SSISDB** -Knoten.</span><span class="sxs-lookup"><span data-stu-id="ed935-112">Expand the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="ed935-113">Erweitern Sie den Ordner mit dem Paket oder Projekt, das Sie konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="ed935-113">Expand the folder that contains the package or project that you want to configure.</span></span>  
  
5.  <span data-ttu-id="ed935-114">Klicken Sie mit der rechten Maustaste auf das Paket oder Projekt, und klicken Sie anschließend auf **Konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="ed935-114">Right-click the package or project, and then click **Configure**.</span></span>  
  
##  <a name="set-the-options-on-the-parameters-page"></a><a name="parameter"></a> <span data-ttu-id="ed935-115">Festlegen der Optionen auf der Seite 'Parameter'</span><span class="sxs-lookup"><span data-stu-id="ed935-115">Set the options on the Parameters page</span></span>  
 <span data-ttu-id="ed935-116">Verwenden Sie die Seite **Parameter** , um Parameternamen und Werte anzuzeigen und die Werte zu ändern.</span><span class="sxs-lookup"><span data-stu-id="ed935-116">Use the **Parameters** page to view parameter names and values, and to modify the values.</span></span>  
  
 <span data-ttu-id="ed935-117">Wählen Sie den Bereich der Parameter aus, der in den Registerkarten **Parameter** und **Verbindungs-Manager** in der Dropdownliste **Bereich** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ed935-117">Select the scope of the parameters displayed in the **Parameters** and **Connection Managers** tabs, in the **Scope** drop-down list.</span></span>  
  
 <span data-ttu-id="ed935-118">Im Folgenden finden Sie eine Liste der Optionen auf der Registerkarte **Parameter** .</span><span class="sxs-lookup"><span data-stu-id="ed935-118">The following is a list of the options in the **Parameters** tab.</span></span>  
  
 <span data-ttu-id="ed935-119">**Container**</span><span class="sxs-lookup"><span data-stu-id="ed935-119">**Container**</span></span>  
 <span data-ttu-id="ed935-120">Listet das Objekt auf, das den Parameter enthält.</span><span class="sxs-lookup"><span data-stu-id="ed935-120">Lists the object that contains the parameter.</span></span>  
  
 <span data-ttu-id="ed935-121">**Name**</span><span class="sxs-lookup"><span data-stu-id="ed935-121">**Name**</span></span>  
 <span data-ttu-id="ed935-122">Listet den Namen des Parameters auf.</span><span class="sxs-lookup"><span data-stu-id="ed935-122">Lists the parameter name.</span></span>  
  
 <span data-ttu-id="ed935-123">**Wert**</span><span class="sxs-lookup"><span data-stu-id="ed935-123">**Value**</span></span>  
 <span data-ttu-id="ed935-124">Listet den Parameterwert auf.</span><span class="sxs-lookup"><span data-stu-id="ed935-124">Lists the parameter value.</span></span> <span data-ttu-id="ed935-125">Klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um den Wert im Dialogfeld **Parameterwert festlegen** zu ändern.</span><span class="sxs-lookup"><span data-stu-id="ed935-125">Click the ellipsis button to change the value in the **Set Parameter Value** dialog box.</span></span>  
  
 <span data-ttu-id="ed935-126">Im Folgenden finden Sie eine Liste der Optionen auf der Registerkarte **Verbindungs-Manager** . Sie verwenden diese Registerkarte, um Werte für Eigenschaften des Verbindungs-Managers zu ändern.</span><span class="sxs-lookup"><span data-stu-id="ed935-126">The following is a list of the options in the **Connection Managers** tab. You use this tab to change values for connection manager properties.</span></span> <span data-ttu-id="ed935-127">Parameter für die Eigenschaften werden automatisch auf dem SSIS-Server generiert.</span><span class="sxs-lookup"><span data-stu-id="ed935-127">Parameters are automatically generated on the SSIS server for the properties.</span></span>  
  
 <span data-ttu-id="ed935-128">**Container**</span><span class="sxs-lookup"><span data-stu-id="ed935-128">**Container**</span></span>  
 <span data-ttu-id="ed935-129">Listet das Objekt auf, das den Verbindungs-Manager enthält.</span><span class="sxs-lookup"><span data-stu-id="ed935-129">Lists the object that contains the connection manager.</span></span>  
  
 <span data-ttu-id="ed935-130">**Name**</span><span class="sxs-lookup"><span data-stu-id="ed935-130">**Name**</span></span>  
 <span data-ttu-id="ed935-131">Listet den Namen des Verbindungs-Managers auf.</span><span class="sxs-lookup"><span data-stu-id="ed935-131">Lists the connection manager name.</span></span>  
  
 <span data-ttu-id="ed935-132">**Eigenschaftenname**</span><span class="sxs-lookup"><span data-stu-id="ed935-132">**Property name**</span></span>  
 <span data-ttu-id="ed935-133">Listet den Namen der Verbindungs-Manager-Eigenschaft auf.</span><span class="sxs-lookup"><span data-stu-id="ed935-133">Lists the name of the connection manager property.</span></span>  
  
 <span data-ttu-id="ed935-134">**Wert**</span><span class="sxs-lookup"><span data-stu-id="ed935-134">**Value**</span></span>  
 <span data-ttu-id="ed935-135">Listet den Wert auf, der der Verbindungs-Manager-Eigenschaft zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="ed935-135">Lists the value assigned to the connection manager property.</span></span> <span data-ttu-id="ed935-136">Klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um den Wert im Dialogfeld **Parameterwert festlegen** zu ändern.</span><span class="sxs-lookup"><span data-stu-id="ed935-136">Click the ellipsis button to change the value in the **Set Parameter Value** dialog box.</span></span> <span data-ttu-id="ed935-137">Sie können einen Literalwert eingeben, eine Umgebungsvariable mit dem zu verwendenden Wert zuordnen oder den Standardwert aus dem Paket verwenden.</span><span class="sxs-lookup"><span data-stu-id="ed935-137">You can enter a literal value, map an environment variable that contains the value you want to use, or use the default value from the package.</span></span>  
  
##  <a name="set-the-options-on-the-references-page"></a><a name="references"></a> <span data-ttu-id="ed935-138">Festlegen der Optionen auf der Seite 'Verweise'</span><span class="sxs-lookup"><span data-stu-id="ed935-138">Set the options on the References page</span></span>  
 <span data-ttu-id="ed935-139">Verwenden Sie die Seite **Verweise** , um Umgebungsverweise hinzuzufügen und zu entfernen und um auf Umgebungseigenschaften zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="ed935-139">Use the **References** page to add and remove references to environments, and to access environment properties.</span></span>  
  
 <span data-ttu-id="ed935-140">In einer Umgebung werden Laufzeitwerte für Pakete festgelegt, die in den auf dem [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Server bereitgestellten Projekten enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="ed935-140">An environment specifies runtime values for packages contained in the projects you've deployed to [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
 <span data-ttu-id="ed935-141">**Umgebung**</span><span class="sxs-lookup"><span data-stu-id="ed935-141">**Environment**</span></span>  
 <span data-ttu-id="ed935-142">Listet die Umgebung auf.</span><span class="sxs-lookup"><span data-stu-id="ed935-142">Lists the environment.</span></span>  
  
 <span data-ttu-id="ed935-143">**Umgebungsordner**</span><span class="sxs-lookup"><span data-stu-id="ed935-143">**Environment Folder**</span></span>  
 <span data-ttu-id="ed935-144">Listet den Ordner auf, der die Umgebung enthält.</span><span class="sxs-lookup"><span data-stu-id="ed935-144">Lists the folder that contains the environment.</span></span>  
  
 <span data-ttu-id="ed935-145">**Öffnen**</span><span class="sxs-lookup"><span data-stu-id="ed935-145">**Open**</span></span>  
 <span data-ttu-id="ed935-146">Klicken Sie hierauf, um das Dialogfeld **Umgebungseigenschaften** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="ed935-146">Click to open the **Environment Properties** dialog box.</span></span>  
  
 <span data-ttu-id="ed935-147">**Add (Hinzufügen)**</span><span class="sxs-lookup"><span data-stu-id="ed935-147">**Add**</span></span>  
 <span data-ttu-id="ed935-148">Klicken Sie auf diese Schaltfläche, um einen Verweis auf eine Umgebung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="ed935-148">Click to add a reference to an environment.</span></span> <span data-ttu-id="ed935-149">Klicken Sie im Dialogfeld **Umgebungen durchsuchen** auf eine Umgebung, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ed935-149">In the **Browse Environments** dialog box click an environment and then click **OK**.</span></span>  
  
 <span data-ttu-id="ed935-150">Sie können jede in einem Projektordner unter dem **SSISDB** -Knoten enthaltene Umgebung auswählen.</span><span class="sxs-lookup"><span data-stu-id="ed935-150">You can select an environment contained in any project folder under the **SSISDB** node.</span></span>  
  
 <span data-ttu-id="ed935-151">**Remove**</span><span class="sxs-lookup"><span data-stu-id="ed935-151">**Remove**</span></span>  
 <span data-ttu-id="ed935-152">Klicken Sie auf eine im Bereich **Verweise** aufgeführte Umgebung und anschließend auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="ed935-152">Click an environment listed in the **References** area, and then click **Remove**.</span></span>  
  
  
