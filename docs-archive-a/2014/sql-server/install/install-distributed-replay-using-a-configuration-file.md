---
title: Installieren von Distributed Replay mithilfe einer Konfigurationsdatei | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 3259232c-6963-4c9c-9d10-ae42aa262eef
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 7757cce29c2e6b3ce4f1e91fc97cbf8be02ae521
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720881"
---
# <a name="install-distributed-replay-using-a-configuration-file"></a><span data-ttu-id="d7a03-102">Installieren von Distributed Replay mithilfe einer Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="d7a03-102">Install Distributed Replay Using a Configuration File</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d7a03-103">-Setup bietet die Möglichkeit, eine Konfigurationsdatei auf der Grundlage von Benutzereingaben und Systemstandards zu generieren.</span><span class="sxs-lookup"><span data-stu-id="d7a03-103">Setup provides the ability to generate a configuration file based on user input and system defaults.</span></span> <span data-ttu-id="d7a03-104">Wenn Sie angeben, dass die Verwaltungstools installiert werden sollen, können Sie mithilfe der Konfigurationsdatei die drei Distributed Replay-Komponenten bereitstellen (Verwaltungstool, Distributed Replay Controller und Distributed Replay Client).</span><span class="sxs-lookup"><span data-stu-id="d7a03-104">If you specify that you want the Management tools installed, you can use the configuration file to deploy the three Distributed Replay components (administration tool, Distributed Replay controller, and the Distributed Replay client).</span></span> <span data-ttu-id="d7a03-105">Unterstützt werden das Installieren, Reparieren und Deinstallieren der Distributed Replay-Komponenten.</span><span class="sxs-lookup"><span data-stu-id="d7a03-105">It supports Installing, repairing, and uninstalling of the Distributed Replay components.</span></span>  
  
 <span data-ttu-id="d7a03-106">Setup unterstützt die Verwendung der Konfigurationsdatei nur in der Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="d7a03-106">Setup supports the use of the configuration file only through the command-line.</span></span> <span data-ttu-id="d7a03-107">Die Verarbeitungsreihenfolge der Parameter während der Verwendung der Konfigurationsdatei wird im Folgenden erläutert:</span><span class="sxs-lookup"><span data-stu-id="d7a03-107">The processing order of the parameters while using the configuration file is outlined below:</span></span>  
  
-   <span data-ttu-id="d7a03-108">Die Konfigurationsdatei überschreibt die Standards in einem Paket</span><span class="sxs-lookup"><span data-stu-id="d7a03-108">The configuration file overwrites the defaults in a package</span></span>  
  
-   <span data-ttu-id="d7a03-109">Befehlszeilenwerte überschreiben die Werte in der Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="d7a03-109">Command-line values overwrite the values in the configuration file</span></span>  
  
 <span data-ttu-id="d7a03-110">Weitere Informationen zum Verwenden einer Konfigurationsdatei finden Sie unter Installieren von [SQL Server 2014 mithilfe einer Konfigurationsdatei](../../database-engine/install-windows/install-sql-server-using-a-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="d7a03-110">For more information about how to use a configuration file, see [Install SQL Server 2014 Using a Configuration File](../../database-engine/install-windows/install-sql-server-using-a-configuration-file.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d7a03-111">Nachdem Sie Distributed Replay installiert haben, müssen Sie auf dem Controller und den Clientcomputern Firewallregeln erstellen und jedem Clientcomputer Berechtigungen für den Zielserver gewähren.</span><span class="sxs-lookup"><span data-stu-id="d7a03-111">After you install Distributed Replay you must create firewall rules on the controller and client computers, and grant each client computer permissions on the target server.</span></span> <span data-ttu-id="d7a03-112">Weitere Informationen finden Sie unter [Ausführen der Schritte nach der Installation](../../tools/distributed-replay/complete-the-post-installation-steps.md).</span><span class="sxs-lookup"><span data-stu-id="d7a03-112">For more information, see [Complete the Post-Installation Steps](../../tools/distributed-replay/complete-the-post-installation-steps.md).</span></span>  
  
### <a name="to-generate-a-configuration-file"></a><span data-ttu-id="d7a03-113">So generieren Sie eine Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="d7a03-113">To generate a configuration file</span></span>  
  
1.  <span data-ttu-id="d7a03-114">Befolgen Sie die Anweisungen des Setup-Assistenten bis zur Seite **Installationsbereit** .</span><span class="sxs-lookup"><span data-stu-id="d7a03-114">Follow the Setup wizard through to the **Ready to Install** page.</span></span> <span data-ttu-id="d7a03-115">Der Pfad zur Konfigurationsdatei wird auf der Seite **Installationsbereit** im Abschnitt mit dem Konfigurationsdateipfad angegeben.</span><span class="sxs-lookup"><span data-stu-id="d7a03-115">The path to the configuration file is specified in the **Ready to Install** page in the configuration file path section.</span></span>  
  
2.  <span data-ttu-id="d7a03-116">Brechen Sie das Setupprogramm ab, ohne dabei die Installation abzuschließen, um die INI-Datei zu generieren.</span><span class="sxs-lookup"><span data-stu-id="d7a03-116">Cancel the setup without actually completing the installation, to generate the INI file.</span></span>  
  
### <a name="to-install-distributed-replay-using-the-configuration-file"></a><span data-ttu-id="d7a03-117">So installieren Sie Distributed Replay mithilfe der Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="d7a03-117">To Install Distributed Replay Using the Configuration File</span></span>  
  
-   <span data-ttu-id="d7a03-118">Führen Sie die Installation an der Eingabeaufforderung aus, und geben Sie die Datei ConfigurationFile.ini mit dem ConfigurationFile-Parameter an.</span><span class="sxs-lookup"><span data-stu-id="d7a03-118">Run the installation through the command prompt and supply the ConfigurationFile.ini using the ConfigurationFile parameter.</span></span>  
  
 <span data-ttu-id="d7a03-119">**Beispielsyntax**</span><span class="sxs-lookup"><span data-stu-id="d7a03-119">**Sample Syntax**</span></span>  
  
 <span data-ttu-id="d7a03-120">Im Folgenden finden Sie ein Beispiel zum Angeben der Konfigurationsdatei an der Eingabeaufforderung:</span><span class="sxs-lookup"><span data-stu-id="d7a03-120">Following is an example on how to specify the configuration file at the command prompt:</span></span>  
  
```  
Setup.exe /CTLRSVCPASSWORD="ctlrsvcpswd" /CLTSVCPASSWORD="cltsvcpswd" / ConfigurationFile=ConfigurationFile.INI\  
```  
  
> [!NOTE]  
>  <span data-ttu-id="d7a03-121">Sie müssen beide Kennwörter in der Befehlszeile angeben, da Sie diese nicht in der Konfigurationsdatei konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="d7a03-121">You must specify both passwords in the command line because you cannot configure them in the configuration file.</span></span>  
  
  
