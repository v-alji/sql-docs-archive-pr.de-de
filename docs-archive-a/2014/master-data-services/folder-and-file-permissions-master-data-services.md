---
title: Ordner- und Dateiberechtigungen (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- security [Master Data Services], file and folder
- folders [Master Data Services]
- files [Master Data Services]
ms.assetid: 6402d81d-7349-47b1-95ca-99b0c0f4f373
author: lrtoyou1223
ms.author: lle
robots: noindex,nofollow
ms.openlocfilehash: 6dc356e074574a4c520b1f4de2f41db0e983c4df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699933"
---
# <a name="folder-and-file-permissions-master-data-services"></a><span data-ttu-id="29d77-102">Ordner- und Dateiberechtigungen (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="29d77-102">Folder and File Permissions (Master Data Services)</span></span>
  <span data-ttu-id="29d77-103">Bei der Installation von [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]werden Ordner und Dateien im Dateisystem in dem Installationspfad installiert, der für freigegebenen Funktionen von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="29d77-103">When you install [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], folders and files are installed in the file system at the installation path you specify for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] shared features.</span></span> <span data-ttu-id="29d77-104">Wenn Sie den Standard Installationspfad für frei [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] gegebene Funktionen verwenden, lautet der Installationspfad für " [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] *Laufwerk*: \Programme\Microsoft SQL server\120\master Data Services".</span><span class="sxs-lookup"><span data-stu-id="29d77-104">If you use the default installation path for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] shared features, the installation path for [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] is *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services.</span></span> <span data-ttu-id="29d77-105">Sie können den Installationspfad für freigegebene Funktionen ändern; achten Sie dabei jedoch auf Berechtigungen, die vom übergeordneten Ordner geerbt werden, und auf explizit für [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]festgelegte Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="29d77-105">Although you can change the shared features installation path, be aware of permissions that are inherited from the parent folder and permissions that are explicitly set for [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span></span>  
  
## <a name="inherited-permissions"></a><span data-ttu-id="29d77-106">Geerbte Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="29d77-106">Inherited Permissions</span></span>  
 <span data-ttu-id="29d77-107">Der Order **Microsoft SQL Server** , der Ordner **Master Data Services** und die meisten Unterordner und Dateien erben Berechtigungen vom übergeordneten Ordner, der bei der Installation von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="29d77-107">The **Microsoft SQL Server** folder, the **Master Data Services** folder, and most subfolders and files inherit permissions from the parent folder specified in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Setup.</span></span> <span data-ttu-id="29d77-108">Bei Auswahl des Standardinstallationspfads lautet der übergeordnete Ordner, von dem Berechtigungen geerbt werden, *Laufwerk*:\Programme.</span><span class="sxs-lookup"><span data-stu-id="29d77-108">If you choose the default installation location, the parent folder that permissions are inherited from is *drive*:\Program Files.</span></span> <span data-ttu-id="29d77-109">In der folgenden Tabelle werden die Standardberechtigungen für den Ordner **Programme**beschrieben.</span><span class="sxs-lookup"><span data-stu-id="29d77-109">The following table describes the default permissions for **Program Files**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="29d77-110">Wenn Sie die Standardberechtigungen für den Ordner **Programme**ändern oder einen anderen Installationspfad auswählen, erben die [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] -Ordner und -Dateien Berechtigungen von dem jeweils übergeordneten Ordner, d.h. die Berechtigungen können sich von denen in der nachfolgenden Tabelle unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="29d77-110">If you modify default permissions for **Program Files**, or you choose a different installation location, the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] folders and files inherit permissions from their parent folder accordingly, and the permissions might differ from those described in the following table.</span></span>  
  
###### <a name="program-files-default-permissions"></a><span data-ttu-id="29d77-111">Standardberechtigungen im Ordner Programme</span><span class="sxs-lookup"><span data-stu-id="29d77-111">Program Files Default Permissions</span></span>  
  
|<span data-ttu-id="29d77-112">Gruppen- oder Kontoname</span><span class="sxs-lookup"><span data-stu-id="29d77-112">Group or account name</span></span>|<span data-ttu-id="29d77-113">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="29d77-113">Permissions</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="29d77-114">CREATOR OWNER</span><span class="sxs-lookup"><span data-stu-id="29d77-114">CREATOR OWNER</span></span>|<span data-ttu-id="29d77-115">Spezielle Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="29d77-115">Special permissions</span></span>|  
|<span data-ttu-id="29d77-116">SYSTEM</span><span class="sxs-lookup"><span data-stu-id="29d77-116">SYSTEM</span></span>|<span data-ttu-id="29d77-117">Spezielle Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="29d77-117">Special permissions</span></span>|  
|<span data-ttu-id="29d77-118">Administrators</span><span class="sxs-lookup"><span data-stu-id="29d77-118">Administrators</span></span>|<span data-ttu-id="29d77-119">Spezielle Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="29d77-119">Special permissions</span></span>|  
|<span data-ttu-id="29d77-120">Benutzer</span><span class="sxs-lookup"><span data-stu-id="29d77-120">Users</span></span>|<span data-ttu-id="29d77-121">Lesen & Ausführen, Ordnerinhalt auflisten, Lesen</span><span class="sxs-lookup"><span data-stu-id="29d77-121">Read & execute, List folder contents, Read</span></span>|  
|<span data-ttu-id="29d77-122">TrustedInstaller</span><span class="sxs-lookup"><span data-stu-id="29d77-122">TrustedInstaller</span></span>|<span data-ttu-id="29d77-123">Ordnerinhalt auflisten, Spezielle Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="29d77-123">List folder contents, Special permissions</span></span>|  
  
## <a name="explicit-permissions"></a><span data-ttu-id="29d77-124">Explizite Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="29d77-124">Explicit Permissions</span></span>  
 <span data-ttu-id="29d77-125">Der Ordner **MDSTempDir** und die Datei Web.config von [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] (im Ordner **WebApplication** ) erben keine Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="29d77-125">The **MDSTempDir** folder and the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] Web.config file (in the **WebApplication** folder) do not inherit permissions.</span></span> <span data-ttu-id="29d77-126">Sie verfügen über Berechtigungen, die bei der Installation von [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]explizit festgelegt werden und vom ausgewählten Installationspfad unabhängig sind.</span><span class="sxs-lookup"><span data-stu-id="29d77-126">They have permissions that are set explicitly when you install [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], regardless of the installation path you choose.</span></span> <span data-ttu-id="29d77-127">Ändern Sie diese Berechtigungen nicht.</span><span class="sxs-lookup"><span data-stu-id="29d77-127">Do not modify these permissions.</span></span>  
  
###### <a name="mdstempdir-permissions"></a><span data-ttu-id="29d77-128">Berechtigungen im Ordner "MDSTempDir"</span><span class="sxs-lookup"><span data-stu-id="29d77-128">MDSTempDir Permissions</span></span>  
  
|<span data-ttu-id="29d77-129">Gruppen- oder Kontoname</span><span class="sxs-lookup"><span data-stu-id="29d77-129">Group or account name</span></span>|<span data-ttu-id="29d77-130">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="29d77-130">Permissions</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="29d77-131">SYSTEM</span><span class="sxs-lookup"><span data-stu-id="29d77-131">SYSTEM</span></span>|<span data-ttu-id="29d77-132">Ändern, Lesen & Ausführen, Ordnerinhalt auflisten, Lesen, Schreiben</span><span class="sxs-lookup"><span data-stu-id="29d77-132">Modify, Read & execute, List folder contents, Read, Write</span></span>|  
|<span data-ttu-id="29d77-133">Administrators</span><span class="sxs-lookup"><span data-stu-id="29d77-133">Administrators</span></span>|<span data-ttu-id="29d77-134">Ändern, Lesen & Ausführen, Ordnerinhalt auflisten, Lesen, Schreiben</span><span class="sxs-lookup"><span data-stu-id="29d77-134">Modify, Read & execute, List folder contents, Read, Write</span></span>|  
|<span data-ttu-id="29d77-135">MDS_ServiceAccounts</span><span class="sxs-lookup"><span data-stu-id="29d77-135">MDS_ServiceAccounts</span></span>|<span data-ttu-id="29d77-136">Ändern, Lesen & Ausführen, Ordnerinhalt auflisten, Lesen, Schreiben</span><span class="sxs-lookup"><span data-stu-id="29d77-136">Modify, Read & execute, List folder contents, Read, Write</span></span>|  
  
###### <a name="webconfig-permissions"></a><span data-ttu-id="29d77-137">Berechtigungen in der Datei "Web.config"</span><span class="sxs-lookup"><span data-stu-id="29d77-137">Web.config Permissions</span></span>  
  
|<span data-ttu-id="29d77-138">Gruppen- oder Kontoname</span><span class="sxs-lookup"><span data-stu-id="29d77-138">Group or account name</span></span>|<span data-ttu-id="29d77-139">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="29d77-139">Permissions</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="29d77-140">SYSTEM</span><span class="sxs-lookup"><span data-stu-id="29d77-140">SYSTEM</span></span>|<span data-ttu-id="29d77-141">Vollzugriff, Ändern, Lesen & Ausführen, Lesen, Schreiben</span><span class="sxs-lookup"><span data-stu-id="29d77-141">Full control, Modify, Read & execute, Read, Write</span></span>|  
|<span data-ttu-id="29d77-142">Administrators</span><span class="sxs-lookup"><span data-stu-id="29d77-142">Administrators</span></span>|<span data-ttu-id="29d77-143">Vollzugriff, Ändern, Lesen & Ausführen, Lesen, Schreiben</span><span class="sxs-lookup"><span data-stu-id="29d77-143">Full control, Modify, Read & execute, Read, Write</span></span>|  
|<span data-ttu-id="29d77-144">MDS_ServiceAccounts</span><span class="sxs-lookup"><span data-stu-id="29d77-144">MDS_ServiceAccounts</span></span>|<span data-ttu-id="29d77-145">Lesen & Ausführen, Lesen</span><span class="sxs-lookup"><span data-stu-id="29d77-145">Read & execute, Read</span></span>|  
  
 <span data-ttu-id="29d77-146">Weitere Informationen zu den Inhalten der Web.config-Datei von [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] finden Sie unter [Webkonfigurationsreferenz &#40;Master Data Services&#41;](web-configuration-reference-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="29d77-146">For more information about the contents of the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] Web.config file, see [Web Configuration Reference &#40;Master Data Services&#41;](web-configuration-reference-master-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29d77-147">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="29d77-147">See Also</span></span>  
 [<span data-ttu-id="29d77-148">Installieren von Master Data Services</span><span class="sxs-lookup"><span data-stu-id="29d77-148">Install Master Data Services</span></span>](install-windows/install-master-data-services.md)  
  
  
