---
title: Parameterwert festlegen (Dialogfeld) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: ce9c2201-4e9a-4495-948f-b68deeaa7955
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 637267603c66921a566ca0d2a3f49f6142cfd203
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721674"
---
# <a name="set-parameter-value-dialog-box"></a><span data-ttu-id="1e426-102">Parameterwert festlegen (Dialogfeld)</span><span class="sxs-lookup"><span data-stu-id="1e426-102">Set Parameter Value Dialog Box</span></span>
  <span data-ttu-id="1e426-103">Verwenden Sie das Dialogfeld **Parameterwert festlegen** , um Werte für Parameter und Eigenschaften des Verbindungs-Managers für Projekte und Pakete festzulegen.</span><span class="sxs-lookup"><span data-stu-id="1e426-103">Use the **Set Parameter Value** dialog box to set values for parameters and connection manager properties, for projects and packages.</span></span>  
  
 <span data-ttu-id="1e426-104">**Was möchten Sie tun?**</span><span class="sxs-lookup"><span data-stu-id="1e426-104">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="1e426-105">Öffnen des Dialogfelds 'Parameterwert festlegen'</span><span class="sxs-lookup"><span data-stu-id="1e426-105">Open the Set Parameter Value dialog box</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="1e426-106">Konfigurieren der Optionen</span><span class="sxs-lookup"><span data-stu-id="1e426-106">Configure the options</span></span>](#option)  
  
##  <a name="open-the-set-parameter-value-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="1e426-107">Öffnen des Dialogfelds 'Parameterwert festlegen'</span><span class="sxs-lookup"><span data-stu-id="1e426-107">Open the Set Parameter Value dialog box</span></span>  
  
1.  <span data-ttu-id="1e426-108">Stellen Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]eine Verbindung zum [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Server her.</span><span class="sxs-lookup"><span data-stu-id="1e426-108">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="1e426-109">Sie stellen eine Verbindung mit der [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]-Instanz her, die die SSISDB-Datenbank hostet.</span><span class="sxs-lookup"><span data-stu-id="1e426-109">You're connecting to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the SSISDB database.</span></span>  
  
2.  <span data-ttu-id="1e426-110">Erweitern Sie im Objekt-Explorer die Struktur, um den Knoten **Integration Services-Kataloge** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1e426-110">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="1e426-111">Erweitern Sie den **SSISDB** -Knoten.</span><span class="sxs-lookup"><span data-stu-id="1e426-111">Expand the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="1e426-112">Klicken Sie mit der rechten Maustaste auf ein Paket oder ein Projekt, wählen Sie **Konfigurieren**, und klicken Sie dann auf der Registerkarte **Parameter** oder auf der Registerkarte **Verbindungs-Manager** auf die Schaltfläche mit den Auslassungspunkten.</span><span class="sxs-lookup"><span data-stu-id="1e426-112">Right-click a package or project, click **Configure**, and then click the ellipsis button in the **Parameters** tab or in the **Connection Managers** tab.</span></span>  
  
##  <a name="configure-the-options"></a><a name="option"></a> <span data-ttu-id="1e426-113">Konfigurieren der Optionen</span><span class="sxs-lookup"><span data-stu-id="1e426-113">Configure the options</span></span>  
 <span data-ttu-id="1e426-114">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="1e426-114">**Parameter**</span></span>  
 <span data-ttu-id="1e426-115">Listet den Namen des Parameters auf.</span><span class="sxs-lookup"><span data-stu-id="1e426-115">Lists the parameter name.</span></span>  
  
 <span data-ttu-id="1e426-116">**Typ**</span><span class="sxs-lookup"><span data-stu-id="1e426-116">**Type**</span></span>  
 <span data-ttu-id="1e426-117">Listet den Datentyp des Parameterwerts auf.</span><span class="sxs-lookup"><span data-stu-id="1e426-117">Lists the data type of the parameter value.</span></span>  
  
 <span data-ttu-id="1e426-118">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="1e426-118">**Description**</span></span>  
 <span data-ttu-id="1e426-119">Zeigt eine optionale Beschreibung für den Parameter an.</span><span class="sxs-lookup"><span data-stu-id="1e426-119">Shows an optional description for the parameter.</span></span>  
  
 <span data-ttu-id="1e426-120">**Wert bearbeiten**</span><span class="sxs-lookup"><span data-stu-id="1e426-120">**Edit value**</span></span>  
 <span data-ttu-id="1e426-121">Verwenden Sie diese Option, um den Parameterwert zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="1e426-121">Select this option to edit the parameter value.</span></span>  
  
 <span data-ttu-id="1e426-122">**Standardwert aus Paket verwenden**</span><span class="sxs-lookup"><span data-stu-id="1e426-122">**Use default value from package**</span></span>  
 <span data-ttu-id="1e426-123">Aktivieren Sie diese Option, um den im Paket gespeicherten Standardwert für diesen Parameter zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="1e426-123">Select this option to use the default parameter value stored in the package.</span></span>  
  
 <span data-ttu-id="1e426-124">**Umgebungsvariable verwenden**</span><span class="sxs-lookup"><span data-stu-id="1e426-124">**Use environment variable**</span></span>  
 <span data-ttu-id="1e426-125">Aktivieren Sie diese Option, um einen Variablenwert zu verwenden, der in der Umgebung gespeichert wurde, auf die vom Projekt oder Paket verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="1e426-125">Select this option to use a variable value stored in the environment, which is referenced by the project or package.</span></span> <span data-ttu-id="1e426-126">Um einen Umgebungsverweis zu einem Projekt oder Paket hinzuzufügen, verwenden Sie das Dialogfeld **Konfigurieren** .</span><span class="sxs-lookup"><span data-stu-id="1e426-126">To add an environment reference to a project or package, use the **Configure** dialog box.</span></span> <span data-ttu-id="1e426-127">Weitere Informationen finden Sie unter [Configure Dialog Box](configure-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="1e426-127">For more information, see [Configure Dialog Box](configure-dialog-box.md).</span></span>  
  
  
