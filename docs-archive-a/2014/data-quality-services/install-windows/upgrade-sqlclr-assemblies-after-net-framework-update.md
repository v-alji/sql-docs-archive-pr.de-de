---
title: Aktualisieren der SQLCLR-Assemblys nach dem Aktualisieren von .NET Framework | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: b1a008cc-7e6b-4655-a869-bd429f986400
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 45d60db413e11828f26bd03e1c8f350645838d12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618916"
---
# <a name="upgrade-sqlclr-assemblies-after-net-framework-update"></a><span data-ttu-id="cde23-102">Aktualisieren der SQLCLR-Assemblys nach dem Aktualisieren von .NET Framework</span><span class="sxs-lookup"><span data-stu-id="cde23-102">Upgrade SQLCLR Assemblies After .NET Framework Update</span></span>
  [!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)] <span data-ttu-id="cde23-103">(DQS) ist eine Auflistung der SQL CLR-Routinen (SQL Common Language Runtime), die auf Microsoft .NET Framework 4-Assemblys verweisen.</span><span class="sxs-lookup"><span data-stu-id="cde23-103">(DQS) is a collection of SQL Common Language Runtime (SQLCR) routines that reference Microsoft .NET Framework 4 assemblies.</span></span> <span data-ttu-id="cde23-104">Wenn Sie ein .NET Framework-Update auf dem Computer installieren, das sich auf eine der .NET Framework-Assemblys, auf die verwiesen wird, auswirkt, wird infolgedessen die MVID (Modul Version ID) der Assembly im globalen Assemblycache (GAC) geändert.</span><span class="sxs-lookup"><span data-stu-id="cde23-104">When you install any .NET Framework updates on your computer that affect any such referenced .NET Framework assembly, it leads to a change in the Module Version ID (MVID) of the assembly in the Global Assembly Cache (GAC).</span></span> <span data-ttu-id="cde23-105">Dadurch wird ein Konflikt zwischen den MVIDs der Assembly im GAC, auf die verwiesen wird, und der Assembly in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]verursacht.</span><span class="sxs-lookup"><span data-stu-id="cde23-105">This causes a mismatch between the MVIDs of the referenced assembly in GAC and the assembly in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="cde23-106">Wenn es beim .NET Framework-Update erforderlich ist, den [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] -Computer neu zu starten, werden die betroffenen SQLCLR-Assemblys automatisch aktualisiert, um den MVID-Konflikt beim Neustart des [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] -Computers zu beheben.</span><span class="sxs-lookup"><span data-stu-id="cde23-106">If the .NET Framework update requires you to restart the [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] computer, the affected SQLCLR assemblies are upgraded automatically to fix the MVID mismatch issue on restarting the [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] computer.</span></span> <span data-ttu-id="cde23-107">Bei .NET Framework-Updates jedoch, bei denen kein Neustart des [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] -Computers erforderlich ist, tritt ein Fehler aufgrund des Konflikts in den MVIDs der Assemblys auf, wenn Sie versuchen, eine Verbindung mit einem [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] herzustellen, der einen [!INCLUDE[ssDQSClient](../../includes/ssdqsclient-md.md)]verwendet:</span><span class="sxs-lookup"><span data-stu-id="cde23-107">However, for .NET Framework updates that do not require you to restart your [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] computer, an error occurs due to the mismatch in the MVIDs of the assemblies when you try to connect to a [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] using a [!INCLUDE[ssDQSClient](../../includes/ssdqsclient-md.md)]:</span></span>  
  
```  
A new version of .NET was installed on this machine. In order to continue to work with DQS please run dqsinstaller.exe -upgradedlls.  
```  
  
 <span data-ttu-id="cde23-108">Um dieses Problem zu beheben, müssen die betroffenen SQLCLR-Assemblys in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="cde23-108">To fix this issue, the affected SQLCLR assemblies in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] must be upgraded.</span></span> <span data-ttu-id="cde23-109">Sie können zu diesem Zweck die Datei DQSInstaller.exe mit dem **upgradedlls** -Befehlszeilenparameter ausführen, um das Neuerstellen der DQS-Datenbanken zu überspringen und nur die betroffenen Assemblys zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="cde23-109">You can do so by running the DQSInstaller.exe file with the **upgradedlls** command line parameter to skip recreating the DQS databases, and just upgrade the affected assemblies.</span></span> <span data-ttu-id="cde23-110">Dadurch wird sichergestellt, dass die Knowledge Bases, Datenqualitätsprojekte und alle anderen Daten in DQS beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="cde23-110">This ensures that your knowledge bases, data quality projects, and any other data in DQS are preserved.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="cde23-111">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="cde23-111">Prerequisites</span></span>  
  
-   <span data-ttu-id="cde23-112">Sie müssen als Mitglied der Administratorgruppe auf dem [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] -Computer angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="cde23-112">You must be logged on as a member of the Administrators group on the [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] computer.</span></span>  
  
-   <span data-ttu-id="cde23-113">Ihr Windows-Benutzerkonto muss Mitglied der festen Serverrolle sysadmin auf der SQL Server-Instanz sein, auf der der [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] installiert ist.</span><span class="sxs-lookup"><span data-stu-id="cde23-113">Your Windows user account must be a member of the sysadmin fixed server role in the SQL Server instance where [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] is installed.</span></span>  
  
### <a name="to-upgrade-sqlclr-assemblies"></a><span data-ttu-id="cde23-114">So aktualisieren Sie SQLCLR-Assemblys</span><span class="sxs-lookup"><span data-stu-id="cde23-114">To upgrade SQLCLR Assemblies</span></span>  
  
1.  <span data-ttu-id="cde23-115">Öffnen Sie die Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="cde23-115">Start Command Prompt.</span></span>  
  
2.  <span data-ttu-id="cde23-116">Wechseln Sie an der Eingabeaufforderung zu dem Verzeichnis, in dem DQSInstaller.exe enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="cde23-116">At the command prompt, change your directory to the location where DQSInstaller.exe is available.</span></span> <span data-ttu-id="cde23-117">Wenn Sie z. B. die Standardinstanz von SQL Server installiert haben, steht die Datei DQSInstaller.exe in der Regel unter C:\Programme\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="cde23-117">If you installed the default instance of SQL Server, the DQSInstaller.exe file will be available at C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn:</span></span>  
  
    ```  
    cd C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn  
    ```  
  
3.  <span data-ttu-id="cde23-118">Geben Sie an der Eingabeaufforderung den folgenden Befehl ein, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="cde23-118">At the command prompt, type the following command, and press ENTER:</span></span>  
  
    ```  
    dqsinstaller.exe -upgradedlls  
    ```  
  
4.  <span data-ttu-id="cde23-119">Die restlichen Schritte entsprechen den Schritten 2–6 im Abschnitt [Ausführen von "DQSInstaller.exe" über den Startbildschirm, das Startmenü oder Windows-Explorer](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md#WindowsExplorer) des Artikels [Ausführen von DQSInstaller.exe zum Abschließen der Installation von Data Quality Server](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span><span class="sxs-lookup"><span data-stu-id="cde23-119">Rest of the steps are same as steps 2-6 in the [Run DQSInstaller.exe from Start Screen, Start Menu or Windows Explorer](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md#WindowsExplorer) section in [Run DQSInstaller.exe to Complete Data Quality Server Installation](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cde23-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cde23-120">See Also</span></span>  
 <span data-ttu-id="cde23-121">[Installieren von Data Quality Services](install-data-quality-services.md) </span><span class="sxs-lookup"><span data-stu-id="cde23-121">[Install Data Quality Services](install-data-quality-services.md) </span></span>  
 [<span data-ttu-id="cde23-122">Aktualisieren des DQS-Datenbankschemas nach der Installation eines SQL Server-Updates</span><span class="sxs-lookup"><span data-stu-id="cde23-122">Upgrade DQS Databases Schema After Installing SQL Server Update</span></span>](upgrade-dqs-databases-schema-after-installing-sql-server-update.md)  
  
  
