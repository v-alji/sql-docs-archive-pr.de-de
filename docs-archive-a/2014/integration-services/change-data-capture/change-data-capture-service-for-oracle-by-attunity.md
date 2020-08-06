---
title: Change Data Capture Service für Oracle von Attunity | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 22ec8a5c-9550-4d38-8a4a-485ec3e53ea8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 68e68e9edd91bd1d0c718b32e29c3b29f74778c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618861"
---
# <a name="change-data-capture-service-for-oracle-by-attunity"></a><span data-ttu-id="6f28d-102">Change Data Capture Service für Oracle von Attunity</span><span class="sxs-lookup"><span data-stu-id="6f28d-102">Change Data Capture Service for Oracle by Attunity</span></span>
  <span data-ttu-id="6f28d-103">Der CDC Service for Oracle ist ein Windows-Dienst, der Oracle-Transaktionsprotokolle scannt und Änderungen an relevanten Oracle-Tabellen in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Änderungstabellen aufzeichnet.</span><span class="sxs-lookup"><span data-stu-id="6f28d-103">The CDC Service for Oracle is a Windows service that scans Oracle transaction logs and captures changes to Oracle tables of interest into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] change tables.</span></span> <span data-ttu-id="6f28d-104">Die SQL-Änderungstabellen, in denen die aus Oracle aufgezeichneten Änderungen gespeichert werden, entsprechen vom Typ her den Änderungstabellen, die in der systemeigenen Change Data Capture-Funktion von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6f28d-104">The SQL change tables where the changes captured from Oracle are stored are the same type of change tables used in the native [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Change Data Capture feature.</span></span> <span data-ttu-id="6f28d-105">Dies macht das Verarbeiten dieser Änderungen so einfach wie das Verarbeiten von an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbanken vorgenommenen Änderungen.</span><span class="sxs-lookup"><span data-stu-id="6f28d-105">This makes consuming these changes as easy as consuming changes made to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases.</span></span>  
  
## <a name="installation"></a><span data-ttu-id="6f28d-106">Installation</span><span class="sxs-lookup"><span data-stu-id="6f28d-106">Installation</span></span>  
 <span data-ttu-id="6f28d-107">Der CDC Service for Oracle kann auf jedem unterstützten Windows-Computer mit Zugriff auf die aufgezeichneten Oracle-Quelldatenbanken und die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Zielinstanz installiert werden, auf der sich die CDC-Zieldatenbank befindet.</span><span class="sxs-lookup"><span data-stu-id="6f28d-107">The CDC Service for Oracle can be installed on any supported Windows computer with access to the source Oracle database(s) being captured and the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance where the target CDC database resides.</span></span> <span data-ttu-id="6f28d-108">Der CDC Service benötigt keine lokale Installation der Oracle-Datenbank oder der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbank, nur die unterstützten Clients.</span><span class="sxs-lookup"><span data-stu-id="6f28d-108">The CDC Service does not need a local installation of the Oracle database or the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database, only their supported clients.</span></span> <span data-ttu-id="6f28d-109">Informationen dazu, wo die erforderlichen Datenbankkomponenten installiert werden müssen, finden Sie in diesem Thema unter **Erforderliche Komponenten für die Datenbank** .</span><span class="sxs-lookup"><span data-stu-id="6f28d-109">For information about where to install the required database components, see **Database Prerequisites** in this topic.</span></span>  
  
 <span data-ttu-id="6f28d-110">Bei der Installation des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC Service for Oracle wird die Benutzeroberfläche der Dienstkonfiguration und das Dienstprogramm am ausgewählten Speicherort abgelegt.</span><span class="sxs-lookup"><span data-stu-id="6f28d-110">The installation of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC Service for Oracle places the service configuration UI and the service program in the selected location.</span></span> <span data-ttu-id="6f28d-111">Der CDC Service for Oracle wird mithilfe der Oracle CDC Service Configuration Console separat konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="6f28d-111">The CDC Service for Oracle is configured separately using the Oracle CDC Service Configuration Console.</span></span> <span data-ttu-id="6f28d-112">Weitere Informationen zur Konfiguration des Oracle CDC Service finden Sie unter [Change Data Capture Service für Oracle von Attunity F1 Hilfe](change-data-capture-service-for-oracle-by-attunity-f1-help.md).</span><span class="sxs-lookup"><span data-stu-id="6f28d-112">For more information on configuring the Oracle CDC Service, see [Change Data Capture Service for Oracle by Attunity F1 Help](change-data-capture-service-for-oracle-by-attunity-f1-help.md).</span></span>  
  
 <span data-ttu-id="6f28d-113">Um CDC Service for Oracle zu installieren, führen Sie **AttunityOracleCdcService.msi** manuell vom SQL Server-Installationsmedium aus.</span><span class="sxs-lookup"><span data-stu-id="6f28d-113">To install the CDC Service for Oracle, manually run **AttunityOracleCdcService.msi** from the SQL Server installation media.</span></span> <span data-ttu-id="6f28d-114">Installationspakete für x86 und x64 befinden sich auf den SQL Server-Installationsmedien unter \*\*.\tools\attunitycdcoracle \\ \*\* .</span><span class="sxs-lookup"><span data-stu-id="6f28d-114">Installation packages for x86 and x64 are located in **.\Tools\AttunityCDCOracle\\** on the SQL Server installation media.</span></span>  
  
 <span data-ttu-id="6f28d-115">Der CDC Service for Oracle kann auf jedem unterstützten Windows-Computer installiert werden, auf dem der [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Native Client installiert ist. Er muss nicht auf dem gleichen Computer installiert sein, auf dem das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Ziel installiert ist.</span><span class="sxs-lookup"><span data-stu-id="6f28d-115">The CDC Service for Oracle can be installed on any supported Windows computer where the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Native Client is installed; it does not need to be installed on the same computer where the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed.</span></span>  
  
## <a name="supported-windows-environments"></a><span data-ttu-id="6f28d-116">Unterstützte Windows-Umgebungen</span><span class="sxs-lookup"><span data-stu-id="6f28d-116">Supported Windows Environments</span></span>  
 <span data-ttu-id="6f28d-117">Der Change Data Capture Service für Oracle von Attunity kann in den folgenden Windows-Umgebungen ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="6f28d-117">The Change Data Capture Service for Oracle by Attunity can run in the following Windows environments:</span></span>  
  
-   <span data-ttu-id="6f28d-118">Windows 8</span><span class="sxs-lookup"><span data-stu-id="6f28d-118">Windows 8</span></span>  
  
-   <span data-ttu-id="6f28d-119">Windows 7 32 Bit (x86) und 64 Bit (x64)</span><span class="sxs-lookup"><span data-stu-id="6f28d-119">Windows 7 32-bit (x86) and 64-bit (x64)</span></span>  
  
-   <span data-ttu-id="6f28d-120">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="6f28d-120">Windows Server 2012</span></span>  
  
-   <span data-ttu-id="6f28d-121">Windows Server 2008 R2 mit Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="6f28d-121">Windows Server 2008 R2 with Service Pack 1</span></span>  
  
-   <span data-ttu-id="6f28d-122">Windows Server 2008 32 Bit (x86) und 64 Bit (x64) mit Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="6f28d-122">Windows Server 2008 32-bit (x86) and 64-bit (x64) with Service Pack 2</span></span>  
  
## <a name="database-prerequisites"></a><span data-ttu-id="6f28d-123">Erforderliche Komponenten für die Datenbank</span><span class="sxs-lookup"><span data-stu-id="6f28d-123">Database Prerequisites</span></span>  
 <span data-ttu-id="6f28d-124">Um den CDC Service for Oracle verwenden zu können, müssen Sie die [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Native Client Oracle-Software installieren.</span><span class="sxs-lookup"><span data-stu-id="6f28d-124">To work with the CDC Service for Oracle you must install the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Native Client Oracle software.</span></span> <span data-ttu-id="6f28d-125">Dies ist eine erforderliche Komponente von Oracle, die vor dem Installieren des Oracle CDC Service vorhanden sein muss.</span><span class="sxs-lookup"><span data-stu-id="6f28d-125">This is a prerequisite that should be obtained from Oracle and installed before installing the Oracle CDC Service.</span></span> <span data-ttu-id="6f28d-126">Darüber hinaus müssen Sie den SQL Server-ODBC-Client über das SQL Server-Setup installieren.</span><span class="sxs-lookup"><span data-stu-id="6f28d-126">Additionally, you need to install the SQL Server ODBC Client using SQL Server Setup.</span></span>  
  
 <span data-ttu-id="6f28d-127">Der CDC Service for Oracle unterstützt die folgenden Versionen:</span><span class="sxs-lookup"><span data-stu-id="6f28d-127">The CDC Service for Oracle supports the following versions:</span></span>  
  
### <a name="source-oracle-database"></a><span data-ttu-id="6f28d-128">Oracle-Quelldatenbank</span><span class="sxs-lookup"><span data-stu-id="6f28d-128">Source Oracle Database</span></span>  
  
-   <span data-ttu-id="6f28d-129">Oracle-Datenbank 11x, alle Versionen</span><span class="sxs-lookup"><span data-stu-id="6f28d-129">Oracle Database 11x, any version</span></span>  
  
-   <span data-ttu-id="6f28d-130">Oracle-Datenbank 10x, alle Versionen</span><span class="sxs-lookup"><span data-stu-id="6f28d-130">Oracle Database 10x, any version</span></span>  
  
### <a name="target-sql-server-database"></a><span data-ttu-id="6f28d-131">SQL Server-Zieldatenbank</span><span class="sxs-lookup"><span data-stu-id="6f28d-131">Target SQL Server Database</span></span>  
 <span data-ttu-id="6f28d-132">Eine Liste der Funktionen, die von den Editionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]unterstützt werden, finden Sie unter [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="6f28d-132">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
## <a name="running-the-installation-program"></a><span data-ttu-id="6f28d-133">Ausführen des Installationsprogramms</span><span class="sxs-lookup"><span data-stu-id="6f28d-133">Running the Installation Program</span></span>  
 <span data-ttu-id="6f28d-134">Öffnen Sie zum Installieren des CDC Service for Oracle den Installations-Assistenten für die von Ihnen verwendete Windows-Plattform (32/64 Bit), und befolgen Sie die Anleitung auf dem Bildschirm.</span><span class="sxs-lookup"><span data-stu-id="6f28d-134">To install the CDC Service for Oracle, open the installation wizard for the Windows platform you are using (32/64-bit) and follow the directions on the screen.</span></span>  
  
## <a name="uninstalling-change-data-capture-service-for-oracle-by-attunity"></a><span data-ttu-id="6f28d-135">Deinstallieren des Change Data Capture Service für Oracle von Attunity</span><span class="sxs-lookup"><span data-stu-id="6f28d-135">Uninstalling Change Data Capture Service for Oracle by Attunity</span></span>  
 <span data-ttu-id="6f28d-136">Sie deinstallieren den CDC Service for Oracle über die Option Programme und Funktionen in der Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="6f28d-136">You uninstall the CDC Service for Oracle using Control Panel, Programs and Features.</span></span>  
  
 <span data-ttu-id="6f28d-137">Beim Deinstallieren des CDC Service werden die erstellten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbanken nicht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="6f28d-137">Uninstalling the CDC Service does not delete the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases created.</span></span> <span data-ttu-id="6f28d-138">Zum vollständigen Entfernen des Tools müssen Sie die MSXDBCDC-Datenbank und die jeweiligen CDC-Datenbanken entfernen, die auf der verwendeten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Zielinstanz erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="6f28d-138">For complete removal of the tool, you must remove the MSXDBCDC database and the specific CDC databases that were created in the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you worked with.</span></span>  
  
 <span data-ttu-id="6f28d-139">Wenn Sie die CDC Service-Software auf einem Computer deinstallieren und auf einem anderen Computer installieren, müssen Sie nur die folgenden Definitionen angeben:</span><span class="sxs-lookup"><span data-stu-id="6f28d-139">If you uninstall the CDC Service software from one machine and install it on another computer, you only need to provide the following definitions:</span></span>  
  
-   <span data-ttu-id="6f28d-140">Dienstkonto</span><span class="sxs-lookup"><span data-stu-id="6f28d-140">Service account</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6f28d-141">-Verbindungszeichenfolge und -Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="6f28d-141">connect string and credentials</span></span>  
  
-   <span data-ttu-id="6f28d-142">Masterkennwort</span><span class="sxs-lookup"><span data-stu-id="6f28d-142">The master password</span></span>  
  
 <span data-ttu-id="6f28d-143">Alle anderen Definitionen werden in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gespeichert und sind über die vorherige Installation auf einem anderen Computer verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6f28d-143">All the other definitions are stored in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and are available from the previous installation on another computer.</span></span>  
  
## <a name="in-this-documentation"></a><span data-ttu-id="6f28d-144">In dieser Dokumentation</span><span class="sxs-lookup"><span data-stu-id="6f28d-144">In This Documentation</span></span>  
  
-   [<span data-ttu-id="6f28d-145">Change Data Capture Service für Oracle von Attunity System Architecture</span><span class="sxs-lookup"><span data-stu-id="6f28d-145">Change Data Capture Service for Oracle by Attunity System Architecture</span></span>](change-data-capture-service-for-oracle-by-attunity-system-architecture.md)  
  
-   [<span data-ttu-id="6f28d-146">Oracle CDC Service</span><span class="sxs-lookup"><span data-stu-id="6f28d-146">The Oracle CDC Service</span></span>](the-oracle-cdc-service.md)  
  
-   [<span data-ttu-id="6f28d-147">Change Data Capture Service für Oracle von Attunity – F1-Hilfe</span><span class="sxs-lookup"><span data-stu-id="6f28d-147">Change Data Capture Service for Oracle by Attunity F1 Help</span></span>](change-data-capture-service-for-oracle-by-attunity-f1-help.md)  
  
-   [<span data-ttu-id="6f28d-148">Change Data Capture Service für Oracle von Attunity – Anleitung</span><span class="sxs-lookup"><span data-stu-id="6f28d-148">Change Data Capture Service for Oracle by Attunity How to Guide</span></span>](change-data-capture-service-for-oracle-by-attunity-how-to-guide.md)  
  
## <a name="see-also"></a><span data-ttu-id="6f28d-149">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6f28d-149">See Also</span></span>  
 [<span data-ttu-id="6f28d-150">Arbeiten mit dem Oracle CDC Service</span><span class="sxs-lookup"><span data-stu-id="6f28d-150">Working with the Oracle CDC Service</span></span>](working-with-the-oracle-cdc-service.md)  
  
  
