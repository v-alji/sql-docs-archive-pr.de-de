---
title: Überprüfen (Dialogfeld) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.ssms.ispackagevalidate.f1
- sql12.ssis.ssms.isprojectvalidate.f1
ms.assetid: 134e14ce-4f8d-4a20-889a-918014c841d8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 69e29d106dc9f4f100bf191911c5c34e0250be8f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609375"
---
# <a name="validate-dialog-box"></a><span data-ttu-id="74b9d-102">Dialogfeld 'Überprüfen'</span><span class="sxs-lookup"><span data-stu-id="74b9d-102">Validate Dialog Box</span></span>
  <span data-ttu-id="74b9d-103">Verwenden Sie das Dialogfeld **Überprüfen** , um nach häufigen Problemen in einem Projekt oder Paket von [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] zu suchen.</span><span class="sxs-lookup"><span data-stu-id="74b9d-103">Use the **Validate** dialog box to check for common problems in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] a project or package.</span></span>  
  
 <span data-ttu-id="74b9d-104">Wenn ein Problem vorliegt, wird eine Meldung am oberen Rand des Dialogfelds angezeigt.</span><span class="sxs-lookup"><span data-stu-id="74b9d-104">If there is a problem, a message is displayed at the top of the dialog box.</span></span> <span data-ttu-id="74b9d-105">Andernfalls wird "Bereit" oben angezeigt.</span><span class="sxs-lookup"><span data-stu-id="74b9d-105">Otherwise, the term Ready displays at the top.</span></span>  
  
 <span data-ttu-id="74b9d-106">**Was möchten Sie tun?**</span><span class="sxs-lookup"><span data-stu-id="74b9d-106">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="74b9d-107">Öffnen des Dialogfelds "Überprüfen"</span><span class="sxs-lookup"><span data-stu-id="74b9d-107">Open the Validate dialog box</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="74b9d-108">Festlegen der Optionen auf der Seite "Allgemein"</span><span class="sxs-lookup"><span data-stu-id="74b9d-108">Set the options on the General page</span></span>](#general)  
  
##  <a name="open-the-validate-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="74b9d-109">Öffnen des Dialogfelds "Überprüfen"</span><span class="sxs-lookup"><span data-stu-id="74b9d-109">Open the Validate dialog box</span></span>  
  
1.  <span data-ttu-id="74b9d-110">Stellen Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]eine Verbindung zum [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Server her.</span><span class="sxs-lookup"><span data-stu-id="74b9d-110">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="74b9d-111">Sie stellen eine Verbindung mit der [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]-Instanz her, die die SSISDB-Datenbank hostet.</span><span class="sxs-lookup"><span data-stu-id="74b9d-111">You're connecting to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the SSISDB database.</span></span>  
  
2.  <span data-ttu-id="74b9d-112">Erweitern Sie im Objekt-Explorer die Struktur, um den Knoten **Integration Services-Kataloge** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="74b9d-112">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="74b9d-113">Erweitern Sie den **SSISDB** -Knoten.</span><span class="sxs-lookup"><span data-stu-id="74b9d-113">Expand the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="74b9d-114">Erweitern Sie den Ordner mit dem Projekt oder Paket, das Sie überprüfen möchten.</span><span class="sxs-lookup"><span data-stu-id="74b9d-114">Expand the folder that contains the project or package you want to validate.</span></span>  
  
5.  <span data-ttu-id="74b9d-115">Klicken Sie mit der rechten Maustaste auf das Projekt oder Paket, und wählen Sie **Überprüfen**aus.</span><span class="sxs-lookup"><span data-stu-id="74b9d-115">Right-click the package or package, and then click **Validate**.</span></span>  
  
##  <a name="set-the-options-on-the-general-page"></a><a name="general"></a> <span data-ttu-id="74b9d-116">Festlegen der Optionen auf der Seite "Allgemein"</span><span class="sxs-lookup"><span data-stu-id="74b9d-116">Set the options on the General page</span></span>  
 <span data-ttu-id="74b9d-117">**Umgebung**</span><span class="sxs-lookup"><span data-stu-id="74b9d-117">**Environment**</span></span>  
 <span data-ttu-id="74b9d-118">Wählen Sie die Umgebung aus, die Sie verwenden möchten, um das Projekt oder Paket zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="74b9d-118">Select the environment that you want to use to validate the project or package.</span></span>  
  
 <span data-ttu-id="74b9d-119">**32-Bit-Laufzeit**</span><span class="sxs-lookup"><span data-stu-id="74b9d-119">**32-bit runtime**</span></span>  
 <span data-ttu-id="74b9d-120">Wählen Sie eine 32-Bit-Laufzeit aus, um ein Paket auszuführen.</span><span class="sxs-lookup"><span data-stu-id="74b9d-120">Select to use a 32-bit runtime to execute a package.</span></span>  
  
 <span data-ttu-id="74b9d-121">Auf der Registerkarte **Parameter** werden die Parameterwerte aufgelistet, die Sie zum Überprüfen des Projekts oder Pakets verwenden.</span><span class="sxs-lookup"><span data-stu-id="74b9d-121">The **Parameters** tab lists the parameter values that you use to validate the project or package.</span></span> <span data-ttu-id="74b9d-122">Im Folgenden finden Sie die Optionen der Registerkarte Parameter.</span><span class="sxs-lookup"><span data-stu-id="74b9d-122">The following are the options on the Parameters tab.</span></span>  
  
 <span data-ttu-id="74b9d-123">**Container**</span><span class="sxs-lookup"><span data-stu-id="74b9d-123">**Container**</span></span>  
 <span data-ttu-id="74b9d-124">Listet das Objekt auf, das den Parameter enthält.</span><span class="sxs-lookup"><span data-stu-id="74b9d-124">Lists the object that contains the parameter.</span></span>  
  
 <span data-ttu-id="74b9d-125">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="74b9d-125">**Parameter**</span></span>  
 <span data-ttu-id="74b9d-126">Listet den Namen des Parameters auf.</span><span class="sxs-lookup"><span data-stu-id="74b9d-126">Lists the name of the parameters</span></span>  
  
 <span data-ttu-id="74b9d-127">**Wert**</span><span class="sxs-lookup"><span data-stu-id="74b9d-127">**Value**</span></span>  
 <span data-ttu-id="74b9d-128">Listet den Parameterwert auf.</span><span class="sxs-lookup"><span data-stu-id="74b9d-128">Lists the parameter value.</span></span>  
  
 <span data-ttu-id="74b9d-129">Auf der Registerkarte **Verbindungs-Manager** werden die Verbindungs-Manager-Eigenschaften aufgelistet, die Sie zum Überprüfen des Projekts oder Pakets verwenden.</span><span class="sxs-lookup"><span data-stu-id="74b9d-129">The **Connection Managers** tab lists the connection manager property values that you use to validate the project or package.</span></span>  
  
 <span data-ttu-id="74b9d-130">Im Folgenden finden Sie die Optionen der Registerkarte **Verbindungs-Manager** .</span><span class="sxs-lookup"><span data-stu-id="74b9d-130">The following are the options on the **Connection Managers** tab.</span></span>  
  
 <span data-ttu-id="74b9d-131">**Container**</span><span class="sxs-lookup"><span data-stu-id="74b9d-131">**Container**</span></span>  
 <span data-ttu-id="74b9d-132">Listet das Objekt auf, das den Verbindungs-Manager enthält.</span><span class="sxs-lookup"><span data-stu-id="74b9d-132">Lists the object that contains the connection manager.</span></span>  
  
 <span data-ttu-id="74b9d-133">**Name**</span><span class="sxs-lookup"><span data-stu-id="74b9d-133">**Name**</span></span>  
 <span data-ttu-id="74b9d-134">Listet den Namen des Verbindungs-Managers auf.</span><span class="sxs-lookup"><span data-stu-id="74b9d-134">Lists the connection manager name.</span></span>  
  
 <span data-ttu-id="74b9d-135">**Eigenschaftenname**</span><span class="sxs-lookup"><span data-stu-id="74b9d-135">**Property name**</span></span>  
 <span data-ttu-id="74b9d-136">Listet den Namen der Verbindungs-Manager-Eigenschaft auf.</span><span class="sxs-lookup"><span data-stu-id="74b9d-136">Lists the name of the connection manager property.</span></span>  
  
 <span data-ttu-id="74b9d-137">**Wert**</span><span class="sxs-lookup"><span data-stu-id="74b9d-137">**Value**</span></span>  
 <span data-ttu-id="74b9d-138">Listet den Wert auf, der der Verbindungs-Manager-Eigenschaft zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="74b9d-138">Lists the value assigned to the connection manager property.</span></span>  
  
  
