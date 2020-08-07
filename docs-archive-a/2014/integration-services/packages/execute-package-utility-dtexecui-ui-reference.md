---
title: Referenz zur Paketausführungsprogramm (dtexecui)-Benutzeroberfläche | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.dtexecui.general.f1
- sql12.dts.dtexecui.executionoptions.f1
- sql12.dts.dtexecui.configuration.f1
- sql12.dts.dtexecui.setvalues.f1
- sql12.dts.dtexecui.commandline.f1
- sql12.dts.dtexecui.commandfiles.f1
- sql12.dts.dtexecui.verification.f1
- sql12.dts.dtexecui.datasources.f1
- sql12.dts.dtexecui.reporting.f1
- sql12.dts.dtexecui.logging.f1
helpviewer_keywords:
- DTExecUI utility
ms.assetid: 3d71df39-126b-4c8e-bd77-128bbd5b0887
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 13601983a4ab841a2b64ff8e4fc722fcf5ae496c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619198"
---
# <a name="execute-package-utility-dtexecui-ui-reference"></a><span data-ttu-id="7b3eb-102">Referenz zur Benutzeroberfläche des Paketausführungs-Hilfsprogramms (DtExecUI)</span><span class="sxs-lookup"><span data-stu-id="7b3eb-102">Execute Package Utility (DtExecUI) UI Reference</span></span>
  <span data-ttu-id="7b3eb-103">Verwenden Sie das **Paketausführungshilfsprogramm** , um [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Pakete auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-103">Use the **Execute Package Utility** to run [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span> <span data-ttu-id="7b3eb-104">Das Hilfsprogramm führt Pakete aus, die an einem von drei Speicherorten gespeichert wurden: in der [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datenbank, im [!INCLUDE[ssIS](../../includes/ssis-md.md)]-Paketspeicher und im Dateisystem.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-104">The utility runs packages that are stored in one of three locations: [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database, the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Store, and the file system.</span></span> <span data-ttu-id="7b3eb-105">Diese Benutzeroberfläche, die über [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder durch Eingabe von an einer Eingabeaufforderung geöffnet werden kann `dtexecui` , stellt eine Alternative zum Ausführen von Paketen mithilfe des Eingabe Aufforderungs Tools **dtexec** dar.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-105">This user interface, which can be opened from [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or by typing `dtexecui` at a command prompt, is an alternative to running packages by using the **DTExec** command prompt tool.</span></span>  
  
 <span data-ttu-id="7b3eb-106">Pakete werden im selben Prozess ausgeführt wie das **dtexecui.exe** -Hilfsprogramm.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-106">Packages execute in the same process as the **dtexecui.exe** utility.</span></span> <span data-ttu-id="7b3eb-107">Da es sich bei diesem Hilfsprogramm um ein 32-Bit-Tool handelt, werden Pakete, die mithilfe von **dtexecui.exe** in einer 64-Bit-Umgebung ausgeführt werden, in Windows unter Win32 (WOW) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-107">Because this utility is a 32-bit tool, packages run by using **dtexecui.exe** in a 64-bit environment run in Windows on Win32 (WOW).</span></span> <span data-ttu-id="7b3eb-108">Beim Entwickeln und Testen von Befehlen mithilfe des Paketausführungshilfsprogramms (dtexecui.exe) auf einem 64-Bit-Computer sollten Sie die Befehle mithilfe der 64-Bit-Version von **dtexec.exe** im 64-Bit-Modus testen, bevor Sie die Befehle auf einem Produktionsserver bereitstellen oder deren Ausführung planen.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-108">When developing and testing commands by using the dtexecui.exe utility on a 64-bit computer, you should test the commands in 64-bit mode by using the 64-bit version of **dtexec.exe** before deploying or scheduling the commands on a production server.</span></span>  
  
 <span data-ttu-id="7b3eb-109">Das **Paketausführungshilfsprogramm** ist eine grafische Benutzeroberfläche für das Eingabeaufforderungs-Hilfsprogramm **DTExec** .</span><span class="sxs-lookup"><span data-stu-id="7b3eb-109">The **Execute Package Utility** is a graphical user interface for the **DTExec** command prompt tool.</span></span> <span data-ttu-id="7b3eb-110">Die Benutzeroberfläche erleichtert das Konfigurieren von Optionen und stellt automatisch die Befehlszeile zusammen, die an das Eingabeaufforderungs-Hilfsprogramm **DTExec** übergeben wird, wenn Sie das Paket unter den angegebenen Optionen ausführen.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-110">The user interface makes it easy to configure options and it automatically assembles the command line that is passed to the **DTExec** command prompt tool when you run the package from the specified options.</span></span>  
  
 <span data-ttu-id="7b3eb-111">Das **Paketausführungshilfsprogramm** eignet sich auch zum Erstellen von Befehlszeilen, die Sie verwenden, wenn **DTExec** direkt ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-111">The **Execute Package Utility** can also be used to assemble command lines that you use when running **DTExec** directly.</span></span>  
  
### <a name="to-open-execute-package-utility-in-sql-server-management-studio"></a><span data-ttu-id="7b3eb-112">So öffnen Sie das Paketausführungsprogramm in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7b3eb-112">To open Execute Package Utility in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="7b3eb-113">Klicken Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]im Menü **Ansicht** auf **Objekt-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-113">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Object Explorer**.</span></span>  
  
2.  <span data-ttu-id="7b3eb-114">Klicken Sie im Objekt-Explorer auf **Verbinden**, und klicken Sie anschließend auf **Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-114">In Object Explorer, click **Connect**, and then click **Integration Services**.</span></span>  
  
3.  <span data-ttu-id="7b3eb-115">Geben Sie im Dialogfeld **Verbindung mit Server herstellen** in der Liste **Servername** den Servernamen ein, und klicken Sie anschließend auf **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-115">In the **Connect to Server** dialog box, enter the server name in the **Server name** list, and then click **Connect**.</span></span>  
  
4.  <span data-ttu-id="7b3eb-116">Erweitern Sie den Ordner **Gespeicherte Pakete**und dessen Unterordner, klicken Sie mit der rechten Maustaste auf das Paket, das Sie ausführen möchten, und klicken Sie anschließend auf **Paket ausführen**.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-116">Expand the **Stored Package**s folder and subfolders, right-click the package you want to run, and then click **Run Package**.</span></span>  
  
### <a name="to-open-the-execute-package-utility-at-the-command-prompt"></a><span data-ttu-id="7b3eb-117">So öffnen Sie das Paketausführungsprogramm an der Eingabeaufforderung</span><span class="sxs-lookup"><span data-stu-id="7b3eb-117">To open the Execute Package Utility at the Command Prompt</span></span>  
  
-   <span data-ttu-id="7b3eb-118">Öffnen Sie ein Eingabeaufforderungsfenster, und führen Sie `dtexecui` aus.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-118">In a command prompt window, run `dtexecui`.</span></span>  
  
 <span data-ttu-id="7b3eb-119">In den folgenden Abschnitten werden Seiten des Dialogfelds **Paketausführungshilfsprogramm** beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-119">The following sections describe pages of the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="general-page"></a><span data-ttu-id="7b3eb-120">Seite Allgemein</span><span class="sxs-lookup"><span data-stu-id="7b3eb-120">General Page</span></span>  
 <span data-ttu-id="7b3eb-121">Auf der Seite **Allgemein** des Dialogfelds **Paketausführungshilfsprogramm** können Sie einen Namen und einen Speicherort für das Paket angeben.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-121">Use the **General** page of the **Execute Package Utility** dialog box to specify a package name and location.</span></span>  
  
 <span data-ttu-id="7b3eb-122">Das Paketausführungshilfsprogramm (dtexecui.exe) führt Pakete immer auf dem lokalen Computer aus, auch wenn das Paket auf einem Remoteserver gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-122">The Execute Package utility (dtexecui.exe) always runs a package on the local computer, even if the package is saved on a remote server.</span></span> <span data-ttu-id="7b3eb-123">Falls das Remotepaket Konfigurationsdateien verwendet, die ebenfalls auf dem Remoteserver gespeichert sind, kann das Paketausführungshilfsprogramm die Konfigurationen u. U. nicht finden und das Paket nicht ausführen.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-123">If the remote package uses configuration files that also are saved on the remote server, then the Execute Package utility may not locate the configurations and the package fails.</span></span> <span data-ttu-id="7b3eb-124">Zum Vermeiden dieses Problems müssen für Verweise auf Konfigurationen UNC-Freigabenamen (Universal Naming Convention) verwendet werden, z.B. \\\myserver\myfile.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-124">To avoid this problem, the configurations must be referenced by using a Universal Naming Convention (UNC) share name like \\\myserver\myfile.</span></span>  
  
### <a name="static-options"></a><span data-ttu-id="7b3eb-125">Statische Optionen</span><span class="sxs-lookup"><span data-stu-id="7b3eb-125">Static Options</span></span>  
 <span data-ttu-id="7b3eb-126">**Paketquelle**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-126">**Package source**</span></span>  
 <span data-ttu-id="7b3eb-127">Geben Sie mithilfe der folgenden Optionen den Speicherort des Pakets an:</span><span class="sxs-lookup"><span data-stu-id="7b3eb-127">Specify the location of the package to run, using the following options:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7b3eb-128">value</span><span class="sxs-lookup"><span data-stu-id="7b3eb-128">Value</span></span>|<span data-ttu-id="7b3eb-129">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7b3eb-129">Description</span></span>|  
|<span data-ttu-id="7b3eb-130">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-130">**SQL Server**</span></span>|<span data-ttu-id="7b3eb-131">Wählen Sie diese Option, wenn das Paket auf [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-131">Select this option when the package resides in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7b3eb-132">Geben Sie eine Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] und einen Benutzernamen und das Kennwort für die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Authentifizierung an.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-132">Specify an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and provide a user name and password for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="7b3eb-133">Für jeden Benutzernamen und jedes Kennwort werden an der Eingabeaufforderungen die Optionen **/USER** _Benutzername_ und **/PASSWORD** _Kennwort_ hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-133">Each user name and password adds the **/USER** _username_ and **/PASSWORD** _password_ options to the command prompt.</span></span>|  
|<span data-ttu-id="7b3eb-134">**Dateisystem**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-134">**File system**</span></span>|<span data-ttu-id="7b3eb-135">Wählen Sie diese Option, wenn das Paket im Dateisystem gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-135">Select this option when the package resides in the file system.</span></span>|  
|<span data-ttu-id="7b3eb-136">**SSIS-Paketspeicher**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-136">**SSIS Package Store**</span></span>|<span data-ttu-id="7b3eb-137">Wählen Sie diese Option aus, wenn das Paket im [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Paketspeicher gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-137">Select this option when the package resides in the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Store.</span></span>|  
  
 <span data-ttu-id="7b3eb-138">Mit jeder dieser Auswahlmöglichkeiten sind die folgenden Optionen verbunden.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-138">Each of these selections has the following set of options.</span></span>  
  
 <span data-ttu-id="7b3eb-139">**Ausführen**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-139">**Execute**</span></span>  
 <span data-ttu-id="7b3eb-140">Klicken Sie hier, um das Paket auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-140">Click to run the package.</span></span>  
  
 <span data-ttu-id="7b3eb-141">**Close**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-141">**Close**</span></span>  
 <span data-ttu-id="7b3eb-142">Klicken Sie hier, um das Dialogfeld **Paketausführungshilfsprogramm** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-142">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
### <a name="dynamic-options"></a><span data-ttu-id="7b3eb-143">Dynamische Optionen</span><span class="sxs-lookup"><span data-stu-id="7b3eb-143">Dynamic Options</span></span>  
  
#### <a name="package-source--sql-server"></a><span data-ttu-id="7b3eb-144">Package Source = SQL Server</span><span class="sxs-lookup"><span data-stu-id="7b3eb-144">Package Source = SQL Server</span></span>  
 <span data-ttu-id="7b3eb-145">**Server**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-145">**Server**</span></span>  
 <span data-ttu-id="7b3eb-146">Geben Sie den Namen des Servers ein, auf dem das Paket gespeichert ist, oder wählen Sie einen Server aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-146">Type the name of the server where the package resides, or select a server from the list.</span></span>  
  
 <span data-ttu-id="7b3eb-147">**Am Server anmelden**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-147">**Log on to the server**</span></span>  
 <span data-ttu-id="7b3eb-148">Gibt an, ob das Paket zum Herstellen der Verbindung mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] die Windows-Authentifizierung oder die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Authentifizierung verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-148">Specify whether the package should use Windows Authentication or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7b3eb-149">Im Sinne einer größeren Sicherheit wird die Windows-Authentifizierung empfohlen.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-149">Windows Authentication is recommended for better security.</span></span> <span data-ttu-id="7b3eb-150">Bei der Windows-Authentifizierung müssen Sie keinen Benutzernamen und das zugehörige Kennwort angeben.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-150">With Windows Authentication you do not have to specify a user name and password.</span></span>  
  
 <span data-ttu-id="7b3eb-151">**Windows-Authentifizierung verwenden**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-151">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="7b3eb-152">Wählen Sie diese Option aus, um die Windows-Authentifizierung zu verwenden und sich mithilfe eines [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows-Benutzerkontos anzumelden.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-152">Select this option to use Windows Authentication and log on using a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows user account.</span></span>  
  
 <span data-ttu-id="7b3eb-153">**SQL Server-Authentifizierung verwenden**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-153">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="7b3eb-154">Wählen Sie diese Option aus, um die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Authentifizierung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-154">Select this option to use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="7b3eb-155">Wenn ein Benutzer eine Verbindung mit einem angegebenen Benutzernamen und einem Kennwort von einer nicht vertrauenswürdigen Verbindung herstellt, führt [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] die Authentifizierung aus, indem überprüft wird, ob ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldekonto eingerichtet wurde und ob das angegebene Kennwort mit dem zuvor aufgezeichneten übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-155">When a user connects with a specified login name and password from a non-trusted connection, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] performs the authentication by checking to see if a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login account has been set up and if the specified password matches the one previously recorded.</span></span> <span data-ttu-id="7b3eb-156">Wenn [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] das Anmeldekonto nicht finden kann, schlägt die Authentifizierung fehl und der Benutzer erhält eine Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-156">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot find the login account, authentication fails, and the user receives an error message.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7b3eb-157">Verwenden Sie nach Möglichkeit die Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-157">When possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="7b3eb-158">**Paket**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-158">**Package**</span></span>  
 <span data-ttu-id="7b3eb-159">Geben Sie den Namen des Pakets ein, oder klicken Sie auf die Schaltfläche mit den Auslassungspunkten **(...)** , um das Paket mithilfe des Dialogfelds **SSIS-Paket auswählen** zu suchen.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-159">Type the name of the package, or click the ellipsis button **(...)** to locate a package using the **Select an SSIS Package** dialog box.</span></span>  
  
#### <a name="package-source--file-system"></a><span data-ttu-id="7b3eb-160">Package Source = File System</span><span class="sxs-lookup"><span data-stu-id="7b3eb-160">Package Source = File System</span></span>  
 <span data-ttu-id="7b3eb-161">**Paket**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-161">**Package**</span></span>  
 <span data-ttu-id="7b3eb-162">Geben Sie den Namen des Pakets ein, oder klicken Sie auf die Schaltfläche mit den Auslassungspunkten **(...)** , um das Paket mithilfe des Dialogfelds „Öffnen“ zu suchen.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-162">Type the name of the package, or click the ellipsis button **(...)** to locate a package using the Open dialog box.</span></span> <span data-ttu-id="7b3eb-163">In dem Dialogfeld werden standardmäßig nur Dateien mit der Erweiterung .dtsx aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-163">By default, the dialog box lists only files that have the .dtsx extension.</span></span>  
  
#### <a name="package-source--ssis-package-store"></a><span data-ttu-id="7b3eb-164">Package Source = SSIS Package Store</span><span class="sxs-lookup"><span data-stu-id="7b3eb-164">Package Source = SSIS Package Store</span></span>  
 <span data-ttu-id="7b3eb-165">**Server**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-165">**Server**</span></span>  
 <span data-ttu-id="7b3eb-166">Geben Sie den Namen des Computers ein, auf dem das Paket gespeichert ist, oder wählen Sie einen Computer aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-166">Type the name of the computer where the package resides, or select a computer from the list.</span></span>  
  
 <span data-ttu-id="7b3eb-167">**Am Server anmelden**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-167">**Log on to the server**</span></span>  
 <span data-ttu-id="7b3eb-168">Gibt an, ob das Paket die Microsoft Windows-Authentifizierung verwenden soll, um eine Verbindung mit der Paketquelle herzustellen.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-168">Specify whether the package should use Microsoft Windows Authentication to connect to the package source.</span></span> <span data-ttu-id="7b3eb-169">Im Sinne einer größeren Sicherheit wird die Windows-Authentifizierung empfohlen.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-169">Windows Authentication is recommended for better security.</span></span> <span data-ttu-id="7b3eb-170">Bei der Windows-Authentifizierung müssen Sie keinen Benutzernamen und das zugehörige Kennwort angeben.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-170">With Windows Authentication you do not have to specify a user name and password.</span></span>  
  
 <span data-ttu-id="7b3eb-171">**Windows-Authentifizierung verwenden**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-171">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="7b3eb-172">Wählen Sie diese Option aus, um die Windows-Authentifizierung zu verwenden und sich mithilfe eines Microsoft Windows-Benutzerkontos anzumelden.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-172">Select this option to use Windows Authentication and log on using a Microsoft Windows user account.</span></span>  
  
 <span data-ttu-id="7b3eb-173">**SQL Server-Authentifizierung verwenden**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-173">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="7b3eb-174">Diese Option ist nicht verfügbar, wenn Sie ein in **SSIS-Paketspeicher**gespeichertes Paket ausführen.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-174">This option is not available when you run a package stored in the **SSIS Package Store**.</span></span>  
  
 <span data-ttu-id="7b3eb-175">**Paket**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-175">**Package**</span></span>  
 <span data-ttu-id="7b3eb-176">Geben Sie den Namen des Pakets ein, oder klicken Sie auf die Schaltfläche mit den Auslassungspunkten **(...)** , um das Paket mithilfe des Dialogfelds **SSIS-Paket auswählen** zu suchen.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-176">Type the name of the package, or click the ellipsis button **(...)** to locate a package using the **Select an SSIS Package** dialog box.</span></span>  
  
## <a name="configurations-page"></a><span data-ttu-id="7b3eb-177">Konfigurationsseite</span><span class="sxs-lookup"><span data-stu-id="7b3eb-177">Configurations Page</span></span>  
 <span data-ttu-id="7b3eb-178">Auf der Seite **Konfigurationen** des Dialogfelds **Paketausführungsprogramm** wählen Sie die Konfigurationsdateien aus, die zur Laufzeit geladen werden sollen, und geben Sie die Reihenfolge an, in der sie geladen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-178">Use the **Configurations** page of the **Execute Package Utility** dialog box to select the configuration files to load at run time, and to specify the order in which they load.</span></span>  
  
### <a name="options"></a><span data-ttu-id="7b3eb-179">Tastatur</span><span class="sxs-lookup"><span data-stu-id="7b3eb-179">Options</span></span>  
 <span data-ttu-id="7b3eb-180">**Konfigurationsdateien**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-180">**Configuration files**</span></span>  
 <span data-ttu-id="7b3eb-181">Listet die vom Paket verwendeten Konfigurationen auf.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-181">Lists the configurations that the package uses.</span></span> <span data-ttu-id="7b3eb-182">Durch jede der Konfigurationsdateien wird der Eingabeaufforderung eine Option **/CONFIGFILE filename** hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-182">Each configuration file adds a **/CONFIGFILE filename** option to the command prompt.</span></span>  
  
 <span data-ttu-id="7b3eb-183">**Pfeiltasten**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-183">**Arrow keys**</span></span>  
 <span data-ttu-id="7b3eb-184">Wählen Sie eine Konfigurationsdatei in der Liste aus, und ändern Sie die Reihenfolge für den Ladevorgang mithilfe der Pfeiltasten auf der rechten Seite.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-184">Select a configuration file in the list, and use the arrow keys at right to change the loading order.</span></span> <span data-ttu-id="7b3eb-185">Die Konfigurationen werden beginnend mit der obersten in der Listenreihenfolge geladen.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-185">Configurations load in order starting from the top of the list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7b3eb-186">Wenn eine Eigenschaft durch mehrere Konfigurationen geändert wird, wird die zuletzt geladene Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-186">If multiple configurations modify the same property, the configuration that loads last is used.</span></span>  
  
 <span data-ttu-id="7b3eb-187">**Add (Hinzufügen)**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-187">**Add**</span></span>  
 <span data-ttu-id="7b3eb-188">Klicken Sie auf diese Option, um Konfigurationen mithilfe des Dialogfelds **Öffnen** hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-188">Click to add configurations using the **Open** dialog box.</span></span> <span data-ttu-id="7b3eb-189">In dem Dialogfeld werden standardmäßig nur Dateien mit der Erweiterung .dtsconfig aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-189">By default, the dialog box lists only files that have the .dtsconfig extension.</span></span>  
  
 <span data-ttu-id="7b3eb-190">**Remove**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-190">**Remove**</span></span>  
 <span data-ttu-id="7b3eb-191">Wählen Sie in der Liste eine Konfigurationsdatei aus, und klicken Sie anschließend auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-191">Select a configuration file in the list and then click **Remove**.</span></span>  
  
 <span data-ttu-id="7b3eb-192">**Ausführen**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-192">**Execute**</span></span>  
 <span data-ttu-id="7b3eb-193">Klicken Sie hier, um das Paket auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-193">Click to run the package.</span></span>  
  
 <span data-ttu-id="7b3eb-194">**Close**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-194">**Close**</span></span>  
 <span data-ttu-id="7b3eb-195">Klicken Sie hier, um das Dialogfeld **Paketausführungshilfsprogramm** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-195">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="command-files-page"></a><span data-ttu-id="7b3eb-196">Seite "Befehlsdateien"</span><span class="sxs-lookup"><span data-stu-id="7b3eb-196">Command Files Page</span></span>  
 <span data-ttu-id="7b3eb-197">Wählen Sie auf der Seite **Befehlsdateien** des Dialogfelds **Paketausführungsprogramm** die Befehlsdateien aus, die zur Laufzeit geladen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-197">Use the **Command Files** page of the **Execute Package Utility** dialog box to select the command files to load at run time.</span></span>  
  
### <a name="options"></a><span data-ttu-id="7b3eb-198">Tastatur</span><span class="sxs-lookup"><span data-stu-id="7b3eb-198">Options</span></span>  
 <span data-ttu-id="7b3eb-199">**Befehlsdateien**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-199">**Command files**</span></span>  
 <span data-ttu-id="7b3eb-200">Führt die vom Paket verwendeten Befehlsdateien auf.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-200">Lists the command files that the package uses.</span></span> <span data-ttu-id="7b3eb-201">Ein Paket kann mehrere Dateien verwenden, um Befehlszeilenoptionen festzulegen.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-201">A package can use multiple files to set command-line options.</span></span>  
  
 <span data-ttu-id="7b3eb-202">**Pfeiltasten**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-202">**Arrow keys**</span></span>  
 <span data-ttu-id="7b3eb-203">Wählen Sie eine Befehlsdatei in der Liste aus, und ändern Sie die Reihenfolge für den Ladevorgang mithilfe der Pfeiltasten auf der rechten Seite.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-203">Select a command file in the list, and use the arrow keys at right to change the loading order.</span></span> <span data-ttu-id="7b3eb-204">Die Befehlsdateien werden der Reihe nach beginnend mit der obersten in der Liste geladen.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-204">Command files load in order, starting from the top of the list.</span></span>  
  
 <span data-ttu-id="7b3eb-205">**Add (Hinzufügen)**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-205">**Add**</span></span>  
 <span data-ttu-id="7b3eb-206">Klicken Sie auf diese Option, um eine Befehlsdatei mithilfe des Dialogfelds **Öffnen** hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-206">Click to add a command file, using the **Open** dialog box.</span></span>  
  
 <span data-ttu-id="7b3eb-207">**Remove**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-207">**Remove**</span></span>  
 <span data-ttu-id="7b3eb-208">Wählen Sie im Textfeld eine Befehlsdatei aus, und entfernen Sie sie anschließend mithilfe der Schaltfläche **Entfernen** .</span><span class="sxs-lookup"><span data-stu-id="7b3eb-208">Select a command file in the text box, and then remove it using the **Remove** button.</span></span>  
  
 <span data-ttu-id="7b3eb-209">**Ausführen**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-209">**Execute**</span></span>  
 <span data-ttu-id="7b3eb-210">Klicken Sie hier, um das Paket auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-210">Click to run the package.</span></span>  
  
 <span data-ttu-id="7b3eb-211">**Close**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-211">**Close**</span></span>  
 <span data-ttu-id="7b3eb-212">Klicken Sie hier, um das Dialogfeld **Paketausführungshilfsprogramm** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-212">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="connection-managers-page"></a><span data-ttu-id="7b3eb-213">Seite "Verbindungs-Manager"</span><span class="sxs-lookup"><span data-stu-id="7b3eb-213">Connection Managers Page</span></span>  
 <span data-ttu-id="7b3eb-214">Auf der Seite **Verbindungs-Manager** des Dialogfelds **Paketausführungshilfsprogramm** können Sie die Verbindungszeichenfolgen der vom Paket verwendeten Verbindungs-Manager bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-214">Use the **Connection Managers** page of the **Execute Package Utility** dialog box to edit the connection strings of the connection managers that the package uses.</span></span>  
  
### <a name="options"></a><span data-ttu-id="7b3eb-215">Tastatur</span><span class="sxs-lookup"><span data-stu-id="7b3eb-215">Options</span></span>  
 <span data-ttu-id="7b3eb-216">**Verbindungs-Manager**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-216">**Connection Manager**</span></span>  
 <span data-ttu-id="7b3eb-217">Aktivieren Sie dieses Kontrollkästchen, um die **Verbindungszeichenfolge** -Spalte bearbeiten zu können.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-217">Select its check box to make the **Connection String** column editable.</span></span>  
  
 <span data-ttu-id="7b3eb-218">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-218">**Description**</span></span>  
 <span data-ttu-id="7b3eb-219">Zeigt eine Beschreibung für jeden Verbindungs-Manager an.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-219">View a description for each connection manager.</span></span> <span data-ttu-id="7b3eb-220">Die Beschreibungen können nicht bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-220">Descriptions cannot be edited.</span></span>  
  
 <span data-ttu-id="7b3eb-221">**Verbindungszeichenfolge**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-221">**Connection String**</span></span>  
 <span data-ttu-id="7b3eb-222">Bearbeiten Sie die Verbindungszeichenfolge für einen Verbindungs-Manager.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-222">Edit the connection string for a connection manager.</span></span> <span data-ttu-id="7b3eb-223">Dieses Feld kann nur bearbeitet werden, wenn das Kontrollkästchen **Verbindungs-Manager** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-223">This field is editable only when the **Connection Manager** check box is selected.</span></span>  
  
 <span data-ttu-id="7b3eb-224">**Ausführen**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-224">**Execute**</span></span>  
 <span data-ttu-id="7b3eb-225">Klicken Sie hier, um das Paket auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-225">Click to run the package.</span></span>  
  
 <span data-ttu-id="7b3eb-226">**Close**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-226">**Close**</span></span>  
 <span data-ttu-id="7b3eb-227">Klicken Sie hier, um das Dialogfeld **Paketausführungshilfsprogramm** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-227">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="execution-options-page"></a><span data-ttu-id="7b3eb-228">Seite "Ausführungsoptionen"</span><span class="sxs-lookup"><span data-stu-id="7b3eb-228">Execution Options Page</span></span>  
 <span data-ttu-id="7b3eb-229">Auf der Seite **Ausführungsoptionen** des Dialogfelds **Paketausführungshilfsprogramm** können Sie Laufzeitoptionen für das Paket angeben.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-229">Use the **Execution Options** page of the **Execute Package Utility** dialog box to specify run-time options for the package.</span></span>  
  
### <a name="options"></a><span data-ttu-id="7b3eb-230">Tastatur</span><span class="sxs-lookup"><span data-stu-id="7b3eb-230">Options</span></span>  
 <span data-ttu-id="7b3eb-231">**Paket bei Überprüfungswarnungen fehlschlagen lassen**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-231">**Fail package on validation warnings**</span></span>  
 <span data-ttu-id="7b3eb-232">Gibt an, ob ein Paket fehlschlägt, wenn eine Überprüfungswarnung auftritt.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-232">Indicate whether the package fails if a validation warning occurs.</span></span>  
  
 <span data-ttu-id="7b3eb-233">**Paket ohne Ausführung überprüfen**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-233">**Validate package without executing**</span></span>  
 <span data-ttu-id="7b3eb-234">Gibt an, ob das Paket nur überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-234">Indicate whether the package is validated only.</span></span>  
  
 <span data-ttu-id="7b3eb-235">**Maximale Anzahl von gleichzeitig ausführbaren Dateien**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-235">**Maximum concurrent executables**</span></span>  
 <span data-ttu-id="7b3eb-236">Gibt an, ob Sie die maximale Anzahl der ausführbaren Dateien angeben möchten, die gleichzeitig im Paket ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-236">Indicate whether you want to specify the maximum number of executables that can run in the package at the same time.</span></span> <span data-ttu-id="7b3eb-237">Nachdem Sie dieses Kontrollkästchen aktiviert haben, verwenden Sie das Drehfeld, um die maximale Anzahl von ausführbaren Dateien anzugeben.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-237">After you select this check box, use the spin box to specify the maximum number of executables.</span></span>  
  
 <span data-ttu-id="7b3eb-238">**Paketprüfpunkte aktivieren**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-238">**Enable package checkpoints**</span></span>  
 <span data-ttu-id="7b3eb-239">Gibt an, ob Paketprüfpunkte aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-239">Indicate whether to enable package checkpoints.</span></span>  
  
 <span data-ttu-id="7b3eb-240">**Prüfpunktdatei**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-240">**Checkpoint file**</span></span>  
 <span data-ttu-id="7b3eb-241">Führt die vom Paket verwendete Prüfpunktdatei auf, wenn die Paketprüfpunkte aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-241">List the checkpoint file the package uses, if you enable package checkpoints.</span></span>  
  
 <span data-ttu-id="7b3eb-242">**Durchsuchen**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-242">**Browse**</span></span>  
 <span data-ttu-id="7b3eb-243">Klicken Sie auf die Schaltfläche zum Durchsuchen **(…)** , um die Prüfpunktdatei mithilfe des Dialogfelds **Öffnen** zu suchen, wenn Paketprüfpunkte aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-243">Click the browse button **(...)** to locate the checkpoint file using the **Open** dialog box, if you enable package checkpoints.</span></span> <span data-ttu-id="7b3eb-244">Wenn bereits eine Prüfpunktdatei angegeben ist, wird diese durch die ausgewählte Datei ersetzt.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-244">If a checkpoint file is already specified, it is replaced by the selected file.</span></span>  
  
 <span data-ttu-id="7b3eb-245">**Neustartoptionen überschreiben**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-245">**Override restart options**</span></span>  
 <span data-ttu-id="7b3eb-246">Gibt an, ob die Neustartoptionen überschrieben werden, wenn Sie die Paketprüfpunkte aktivieren.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-246">Indicate whether to override restart options, if you enable package checkpoints.</span></span>  
  
 <span data-ttu-id="7b3eb-247">**Neustartoption**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-247">**Restart option**</span></span>  
 <span data-ttu-id="7b3eb-248">Wählen Sie aus, wie die Prüfpunkte verwendet werden sollen, wenn die Neustartoptionen überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-248">Select how to use checkpoints, if you override restart options.</span></span>  
  
 <span data-ttu-id="7b3eb-249">**Ausführen**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-249">**Execute**</span></span>  
 <span data-ttu-id="7b3eb-250">Klicken Sie hier, um das Paket auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-250">Click to run the package.</span></span>  
  
 <span data-ttu-id="7b3eb-251">**Close**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-251">**Close**</span></span>  
 <span data-ttu-id="7b3eb-252">Klicken Sie hier, um das Dialogfeld **Paketausführungshilfsprogramm** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-252">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="reporting-page"></a><span data-ttu-id="7b3eb-253">Berichtsseite</span><span class="sxs-lookup"><span data-stu-id="7b3eb-253">Reporting Page</span></span>  
 <span data-ttu-id="7b3eb-254">Auf der Seite **Berichterstellung** des Dialogfelds **Paketausführungsprogramm** können Sie angeben, welche Ereignisse und Informationen zu dem Paket beim Ausführen des Pakets an der Konsole protokolliert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-254">Use the **Reporting** page of the **Execute Package Utility** dialog box to specify the events and information about the package to log to the console when the package runs.</span></span>  
  
### <a name="options"></a><span data-ttu-id="7b3eb-255">Tastatur</span><span class="sxs-lookup"><span data-stu-id="7b3eb-255">Options</span></span>  
 <span data-ttu-id="7b3eb-256">**Konsolenereignisse**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-256">**Console events**</span></span>  
 <span data-ttu-id="7b3eb-257">Geben Sie die Ereignisse und Meldungstypen an, die gemeldet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-257">Indicate the events and types of messages to report.</span></span>  
  
 <span data-ttu-id="7b3eb-258">**None**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-258">**None**</span></span>  
 <span data-ttu-id="7b3eb-259">Wählen Sie diese Option aus, um keinerlei Informationen zu melden.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-259">Select for no reporting.</span></span>  
  
 <span data-ttu-id="7b3eb-260">**Fehler**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-260">**Errors**</span></span>  
 <span data-ttu-id="7b3eb-261">Wählen Sie diese Option aus, um Fehlermeldungen zu melden.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-261">Select to report error messages.</span></span>  
  
 <span data-ttu-id="7b3eb-262">**Warnungen**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-262">**Warnings**</span></span>  
 <span data-ttu-id="7b3eb-263">Wählen Sie diese Option aus, um Warnungen zu melden.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-263">Select to report warning messages.</span></span>  
  
 <span data-ttu-id="7b3eb-264">**Benutzerdefinierte Ereignisse**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-264">**Custom Events**</span></span>  
 <span data-ttu-id="7b3eb-265">Wählen Sie diese Option aus, um Meldungen zu benutzerdefinierten Ereignissen zu melden.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-265">Select to report custom event messages.</span></span>  
  
 <span data-ttu-id="7b3eb-266">**Pipelineereignisse**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-266">**Pipeline Events**</span></span>  
 <span data-ttu-id="7b3eb-267">Wählen Sie diese Option aus, um Meldungen zu Datenflussereignissen zu melden.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-267">Select to report data flow events messages.</span></span>  
  
 <span data-ttu-id="7b3eb-268">**Informationen**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-268">**Information**</span></span>  
 <span data-ttu-id="7b3eb-269">Wählen Sie diese Option aus, um Informationsmeldungen zu melden.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-269">Select to report information messages.</span></span>  
  
 <span data-ttu-id="7b3eb-270">**Ausführlich**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-270">**Verbose**</span></span>  
 <span data-ttu-id="7b3eb-271">Wählen Sie diese Option aus, um die ausführliche Berichterstellung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-271">Select to use verbose reporting.</span></span>  
  
 <span data-ttu-id="7b3eb-272">**Konsolenprotokollierung**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-272">**Console logging**</span></span>  
 <span data-ttu-id="7b3eb-273">Geben Sie die Informationen ein, die in das Protokoll geschrieben werden sollen, wenn das ausgewählte Ereignis eintritt.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-273">Specify the information that you want written to the log when the selected event occurs.</span></span>  
  
 <span data-ttu-id="7b3eb-274">**Name**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-274">**Name**</span></span>  
 <span data-ttu-id="7b3eb-275">Wählen Sie diese Option aus, wenn der Name der Person gemeldet werden soll, die das Paket erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-275">Select to report the name of the person who created the package.</span></span>  
  
 <span data-ttu-id="7b3eb-276">**Computer**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-276">**Computer**</span></span>  
 <span data-ttu-id="7b3eb-277">Wählen Sie diese Option aus, um den Namen des Computers zu melden, auf dem das Paket ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-277">Select to report the name of the computer the package is running on.</span></span>  
  
 <span data-ttu-id="7b3eb-278">**Operator**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-278">**Operator**</span></span>  
 <span data-ttu-id="7b3eb-279">Wählen Sie diese Option aus, wenn der Name der Person gemeldet werden soll, die das Paket gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-279">Select to report the name of the person who started the package.</span></span>  
  
 <span data-ttu-id="7b3eb-280">**Quellname**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-280">**Source name**</span></span>  
 <span data-ttu-id="7b3eb-281">Wählen Sie diese Option aus, um den Paketnamen zu melden.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-281">Select to report the package name.</span></span>  
  
 <span data-ttu-id="7b3eb-282">**Quell-GUID**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-282">**Source GUID**</span></span>  
 <span data-ttu-id="7b3eb-283">Wählen Sie diese Option aus, um die GUID des Pakets zu melden.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-283">Select to report the package GUID.</span></span>  
  
 <span data-ttu-id="7b3eb-284">**Ausführungs-GUID**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-284">**Execution GUID**</span></span>  
 <span data-ttu-id="7b3eb-285">Wählen Sie diese Option aus, um die GUID der Paketausführungsinstanz zu melden.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-285">Select to report the GUID of the package execution instance.</span></span>  
  
 <span data-ttu-id="7b3eb-286">**Meldung**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-286">**Message**</span></span>  
 <span data-ttu-id="7b3eb-287">Wählen Sie diese Option aus, um Meldungen zu melden.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-287">Select to report messages.</span></span>  
  
 <span data-ttu-id="7b3eb-288">**Startzeit und Beendigungszeit**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-288">**Start time and end time**</span></span>  
 <span data-ttu-id="7b3eb-289">Wählen Sie diese Option aus, um zu melden, wann das Paket gestartet und beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-289">Select to report when the package began and finished.</span></span>  
  
 <span data-ttu-id="7b3eb-290">**Ausführen**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-290">**Execute**</span></span>  
 <span data-ttu-id="7b3eb-291">Klicken Sie hier, um das Paket auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-291">Click to run the package.</span></span>  
  
 <span data-ttu-id="7b3eb-292">**Close**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-292">**Close**</span></span>  
 <span data-ttu-id="7b3eb-293">Klicken Sie hier, um das Dialogfeld **Paketausführungshilfsprogramm** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-293">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="logging-page"></a><span data-ttu-id="7b3eb-294">Protokollierungsseite</span><span class="sxs-lookup"><span data-stu-id="7b3eb-294">Logging Page</span></span>  
 <span data-ttu-id="7b3eb-295">Auf der Seite **Protokollierung** des Dialogfelds **Paketausführungsprogramm** können Sie festlegen, welche Protokollanbieter dem Paket zur Laufzeit zur Verfügung stehen sollen.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-295">Use the **Logging** page of the **Execute Package Utility** dialog box to make log providers available to the package at run time.</span></span> <span data-ttu-id="7b3eb-296">Stellen Sie den Typ des Paketprotokollanbieters und die Verbindungszeichenfolge für die Verbindung mit dem Protokoll bereit.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-296">Provide the package log provider type and the connection string for connecting to the log.</span></span> <span data-ttu-id="7b3eb-297">Für jeden Protokollanbietereintrag wird der Eingabeaufforderung eine Instanz der Option **/LOGGER**_classid_ hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-297">Each log provider entry adds a **/LOGGER**_classid_ option to the command prompt.</span></span>  
  
### <a name="options"></a><span data-ttu-id="7b3eb-298">Tastatur</span><span class="sxs-lookup"><span data-stu-id="7b3eb-298">Options</span></span>  
 <span data-ttu-id="7b3eb-299">**Protokollanbieter**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-299">**Log Provider**</span></span>  
 <span data-ttu-id="7b3eb-300">Wählen Sie einen Protokollanbieter aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-300">Select a log provider from the list.</span></span>  
  
 <span data-ttu-id="7b3eb-301">**Konfigurationszeichenfolge**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-301">**Configuration String**</span></span>  
 <span data-ttu-id="7b3eb-302">Wählen Sie den Namen des Verbindungs-Managers aus dem Paket aus, das auf den Speicherort des Protokolls zeigt, oder geben Sie die Verbindungszeichenfolge für die Verbindung mit dem Protokollanbieter ein.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-302">Select the name of the connection manager from the package that points to the log location, or type the connection string for connecting to the log provider.</span></span>  
  
 <span data-ttu-id="7b3eb-303">**Remove**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-303">**Remove**</span></span>  
 <span data-ttu-id="7b3eb-304">Wählen Sie einen Protokollanbieter aus, und klicken Sie auf ihn, um ihn zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-304">Select a log provider and click to remove it.</span></span>  
  
 <span data-ttu-id="7b3eb-305">**Ausführen**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-305">**Execute**</span></span>  
 <span data-ttu-id="7b3eb-306">Klicken Sie hier, um das Paket auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-306">Click to run the package.</span></span>  
  
 <span data-ttu-id="7b3eb-307">**Close**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-307">**Close**</span></span>  
 <span data-ttu-id="7b3eb-308">Klicken Sie hier, um das Dialogfeld **Paketausführungshilfsprogramm** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-308">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="set-values-page"></a><span data-ttu-id="7b3eb-309">Seite "Werte festlegen"</span><span class="sxs-lookup"><span data-stu-id="7b3eb-309">Set Values Page</span></span>  
 <span data-ttu-id="7b3eb-310">Auf der Seite **Werte festlegen** des Dialogfelds **Paketausführungsprogramm** können Sie die Eigenschaftenwerte von Paketen, ausführbaren Dateien, Verbindungen, Variablen und Protokollanbietern festlegen, indem Sie die Pfade der Eigenschaften und die Eigenschaftenwerte eingeben.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-310">Use the **Set Values** page of the **Execute Package Utility** dialog box to set the property values of packages, executables, connections, variables, and log providers by typing the paths of properties and the property values.</span></span> <span data-ttu-id="7b3eb-311">Für jeden Pfadeintrag wird der Eingabeaufforderung eine Instanz der Option **/SET**_propertypath;value_ hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-311">Each path entry adds a **/SET**_propertypath;value_ option to the command prompt.</span></span>  
  
### <a name="options"></a><span data-ttu-id="7b3eb-312">Tastatur</span><span class="sxs-lookup"><span data-stu-id="7b3eb-312">Options</span></span>  
 <span data-ttu-id="7b3eb-313">**Eigenschaftspfad**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-313">**Property Path**</span></span>  
 <span data-ttu-id="7b3eb-314">Geben Sie den Pfad der Eigenschaft ein.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-314">Type the path of the property.</span></span> <span data-ttu-id="7b3eb-315">In der Pfadsyntax wird der umgekehrte Schrägstrich (\\) verwendet, um zu kennzeichnen, dass es sich beim nächsten Element um einen Container handelt, durch einen Punkt (.) wird gekennzeichnet, dass das folgende Element eine Eigenschaft ist, und Klammern kennzeichnen ein Sammelelement.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-315">The path syntax uses a backslash (\\) to indicate that the following item is a container, the period (.) to indicate the following item is a property, and brackets to indicate a collection member.</span></span> <span data-ttu-id="7b3eb-316">Das Element kann anhand seines Index oder Namens identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-316">The member can be identified by its index or its name.</span></span> <span data-ttu-id="7b3eb-317">Der Eigenschaftspfad einer Paketvariablen lautet beispielsweise \Package.Variables[MyVariable].Value.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-317">For example, the property path of a package variable is \Package.Variables[MyVariable].Value.</span></span>  
  
 <span data-ttu-id="7b3eb-318">**Wert**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-318">**Value**</span></span>  
 <span data-ttu-id="7b3eb-319">Geben Sie den Wert der Eigenschaft ein.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-319">Type the value of the property.</span></span>  
  
 <span data-ttu-id="7b3eb-320">**Remove**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-320">**Remove**</span></span>  
 <span data-ttu-id="7b3eb-321">Wählen Sie einen Eigenschaftspfad aus, und klicken Sie darauf, um ihn zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-321">Select a property path and click to remove it.</span></span>  
  
 <span data-ttu-id="7b3eb-322">**Ausführen**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-322">**Execute**</span></span>  
 <span data-ttu-id="7b3eb-323">Klicken Sie hier, um das Paket auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-323">Click to run the package.</span></span>  
  
 <span data-ttu-id="7b3eb-324">**Close**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-324">**Close**</span></span>  
 <span data-ttu-id="7b3eb-325">Klicken Sie hier, um das Dialogfeld **Paketausführungshilfsprogramm** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-325">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="verification-page"></a><span data-ttu-id="7b3eb-326">Überprüfungsseite</span><span class="sxs-lookup"><span data-stu-id="7b3eb-326">Verification Page</span></span>  
 <span data-ttu-id="7b3eb-327">Auf der Seite **Überprüfung** des Dialogfelds **Paket ausführen** können Sie Kriterien zum Überprüfen des Pakets festlegen.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-327">Use the **Verification** page of the **Execute Package** dialog box to set criteria for verifying the package.</span></span>  
  
### <a name="options"></a><span data-ttu-id="7b3eb-328">Tastatur</span><span class="sxs-lookup"><span data-stu-id="7b3eb-328">Options</span></span>  
 <span data-ttu-id="7b3eb-329">**Nur signierte Pakete ausführen**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-329">**Execute only signed packages**</span></span>  
 <span data-ttu-id="7b3eb-330">Wählen Sie diese Option aus, um nur signierte Pakete auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-330">Select to execute only packages that have been signed.</span></span>  
  
 <span data-ttu-id="7b3eb-331">**Paketbuild überprüfen**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-331">**Verify package build**</span></span>  
 <span data-ttu-id="7b3eb-332">Wählen Sie diese Option aus, um das Paketbuild zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-332">Select to verify the package build.</span></span>  
  
 <span data-ttu-id="7b3eb-333">Entwickeln</span><span class="sxs-lookup"><span data-stu-id="7b3eb-333">Build</span></span>  
 <span data-ttu-id="7b3eb-334">Geben Sie die dem Build zugeordnete fortlaufende Buildnummer an.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-334">Specify the sequential Build number associated with the build.</span></span>  
  
 <span data-ttu-id="7b3eb-335">**Paket-ID überprüfen**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-335">**Verify package ID**</span></span>  
 <span data-ttu-id="7b3eb-336">Wählen Sie diese Option aus, um die Paket-ID zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-336">Select to verify the package ID.</span></span>  
  
 <span data-ttu-id="7b3eb-337">Paket-ID</span><span class="sxs-lookup"><span data-stu-id="7b3eb-337">Package ID</span></span>  
 <span data-ttu-id="7b3eb-338">Geben Sie die Paket-ID an.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-338">Specify the package identification number.</span></span>  
  
 <span data-ttu-id="7b3eb-339">**Versions-ID überprüfen**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-339">**Verify version ID**</span></span>  
 <span data-ttu-id="7b3eb-340">Wählen Sie diese Option aus, um die Versions-ID zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-340">Select to verify the version ID.</span></span>  
  
 <span data-ttu-id="7b3eb-341">Versions-ID</span><span class="sxs-lookup"><span data-stu-id="7b3eb-341">Version ID</span></span>  
 <span data-ttu-id="7b3eb-342">Geben Sie die Versions-ID an.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-342">Specify the version identification number.</span></span>  
  
 <span data-ttu-id="7b3eb-343">**Ausführen**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-343">**Execute**</span></span>  
 <span data-ttu-id="7b3eb-344">Klicken Sie hier, um das Paket auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-344">Click to run the package.</span></span>  
  
 <span data-ttu-id="7b3eb-345">**Close**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-345">**Close**</span></span>  
 <span data-ttu-id="7b3eb-346">Klicken Sie hier, um das Dialogfeld **Paketausführungshilfsprogramm** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-346">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="command-line-page"></a><span data-ttu-id="7b3eb-347">Befehlszeilenseite</span><span class="sxs-lookup"><span data-stu-id="7b3eb-347">Command Line Page</span></span>  
 <span data-ttu-id="7b3eb-348">Auf der Seite **Befehlszeile** des Dialogfelds **Paketausführungsprogramm** können Sie die Befehlszeile bearbeiten, die von Optionen generiert wurde, die in den verschiedenen Dialogfeldern erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-348">Use the **Command Line** node of the **Execute Package Utility** dialog box to edit the command line that has been generated by the options created by the various dialogs.</span></span>  
  
### <a name="options"></a><span data-ttu-id="7b3eb-349">Tastatur</span><span class="sxs-lookup"><span data-stu-id="7b3eb-349">Options</span></span>  
 <span data-ttu-id="7b3eb-350">**Die ursprünglichen Optionen wiederherstellen**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-350">**Restore the original options**</span></span>  
 <span data-ttu-id="7b3eb-351">Klicken Sie hier, um den ursprünglichen Status der Befehlszeile wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-351">Click to restore the command line to its original state.</span></span> <span data-ttu-id="7b3eb-352">Verwenden Sie diese Option, wenn Sie mithilfe der Option **Befehlszeile manuell bearbeiten** Änderungen vorgenommen haben und nun die ursprünglichen Optionen der Befehlszeile wiederherstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-352">Use this option if you have made modifications using the **Edit the command line manually** option and want to restore the original command-line options.</span></span>  
  
 <span data-ttu-id="7b3eb-353">**Befehlszeile manuell bearbeiten**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-353">**Edit the command line manually**</span></span>  
 <span data-ttu-id="7b3eb-354">Klicken Sie hier, um die Befehlszeile im Textfeld **Befehlszeile** zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-354">Click to edit the command line in the **Command line** text box.</span></span>  
  
 <span data-ttu-id="7b3eb-355">**Befehlszeile**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-355">**Command line**</span></span>  
 <span data-ttu-id="7b3eb-356">Zeigt die aktuelle Befehlszeile an.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-356">Displays the current command line.</span></span> <span data-ttu-id="7b3eb-357">Die Befehlszeile kann nur bearbeitet werden, wenn Sie die Option zum manuellen Bearbeiten der Befehlszeile aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-357">Editable if you selected the option to edit the command line manually.</span></span>  
  
 <span data-ttu-id="7b3eb-358">**Ausführen**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-358">**Execute**</span></span>  
 <span data-ttu-id="7b3eb-359">Klicken Sie hier, um das Paket auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-359">Click to run the package.</span></span>  
  
 <span data-ttu-id="7b3eb-360">**Close**</span><span class="sxs-lookup"><span data-stu-id="7b3eb-360">**Close**</span></span>  
 <span data-ttu-id="7b3eb-361">Klicken Sie hier, um das Dialogfeld **Paketausführungshilfsprogramm** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="7b3eb-361">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b3eb-362">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7b3eb-362">See Also</span></span>  
 [<span data-ttu-id="7b3eb-363">dtexec (Hilfsprogramm)</span><span class="sxs-lookup"><span data-stu-id="7b3eb-363">dtexec Utility</span></span>](dtexec-utility.md)  
  
  
