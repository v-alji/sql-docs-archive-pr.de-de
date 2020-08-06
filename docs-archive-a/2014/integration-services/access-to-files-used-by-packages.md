---
title: Zugriff auf Dateien, die von Paketen verwendet werden | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SSIS packages, security
- packages [Integration Services], security
- configuration files [Integration Services]
- checkpoint files
- Integration Services packages, security
- logs [Integration Services], security
- files [Integration Services], security
- SQL Server Integration Services packages, security
ms.assetid: 2e3ddea9-5289-4289-a70e-11c018f34977
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8db9511c91c9f229b7002f5b16cf077910a4ccf0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610030"
---
# <a name="access-to-files-used-by-packages"></a><span data-ttu-id="b4bbb-102">Zugriff auf Dateien, die von Paketen verwendet werden</span><span class="sxs-lookup"><span data-stu-id="b4bbb-102">Access to Files Used by Packages</span></span>
  <span data-ttu-id="b4bbb-103">Die Paketschutzebene bietet für Dateien, die außerhalb des Pakets gespeichert wurden, keinen Schutz.</span><span class="sxs-lookup"><span data-stu-id="b4bbb-103">The package protection level does not protect files that are stored outside the package.</span></span> <span data-ttu-id="b4bbb-104">Hierzu gehören die folgenden Dateien:</span><span class="sxs-lookup"><span data-stu-id="b4bbb-104">These files include the following:</span></span>  
  
-   <span data-ttu-id="b4bbb-105">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="b4bbb-105">Configuration files</span></span>  
  
-   <span data-ttu-id="b4bbb-106">Prüfpunktdateien</span><span class="sxs-lookup"><span data-stu-id="b4bbb-106">Checkpoint files</span></span>  
  
-   <span data-ttu-id="b4bbb-107">Protokolldateien</span><span class="sxs-lookup"><span data-stu-id="b4bbb-107">Log files</span></span>  
  
 <span data-ttu-id="b4bbb-108">Diese Dateien müssen separat geschützt werden. Dies gilt insbesondere dann, wenn sie vertrauliche Informationen beinhalten.</span><span class="sxs-lookup"><span data-stu-id="b4bbb-108">These files must be protected separately, especially if they include sensitive information.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="b4bbb-109">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="b4bbb-109">Configuration Files</span></span>  
 <span data-ttu-id="b4bbb-110">Wenn in einer Konfiguration vertrauliche Informationen enthalten sind, wie z.B. der Anmeldename und das Kennwort, sollten Sie die Konfiguration in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]speichern oder eine Zugriffssteuerungsliste (ACL, Access Control List) verwenden, um den Zugriff auf den Speicherort bzw. auf den Ordner, in dem die Dateien gespeichert sind, zu beschränken und den Zugriff nur bestimmten Konten zu gewähren.</span><span class="sxs-lookup"><span data-stu-id="b4bbb-110">If you have sensitive information in a configuration, such as login and password information, you should consider saving the configuration to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], or use an access control list (ACL) to restrict access to the location or folder where you store the files and allow access only to certain accounts.</span></span> <span data-ttu-id="b4bbb-111">In der Regel wird den Konten Zugriff gewährt, denen die Berechtigung zum Ausführen von Paketen erteilt wird, und den Konten, die Pakete verwalten und Probleme bei Paketen beheben. Hierzu gehört z. B. das Überprüfen der Inhalte der Konfiguration, des Prüfpunkts und der Protokolldateien.</span><span class="sxs-lookup"><span data-stu-id="b4bbb-111">Typically, you would grant access to the accounts that you permit to run packages, and to the accounts that manage and troubleshoot packages, which may include reviewing the contents of configuration, checkpoint, and log files.</span></span> [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="b4bbb-112">bereitgestellte Speicher ist sicherer, da er Schutz auf Server- und Datenbankebene bietet.</span><span class="sxs-lookup"><span data-stu-id="b4bbb-112">provides the more secure storage because it offers protection at the server and database levels.</span></span> <span data-ttu-id="b4bbb-113">Verwenden Sie zum Speichern der Konfigurationen in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]den [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Konfigurationstyp.</span><span class="sxs-lookup"><span data-stu-id="b4bbb-113">To save configurations to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], you use the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] configuration type.</span></span> <span data-ttu-id="b4bbb-114">Verwenden Sie zum Speichern im Dateisystem den XML-Konfigurationstyp.</span><span class="sxs-lookup"><span data-stu-id="b4bbb-114">To save to the file system, you use the XML configuration type.</span></span>  
  
 <span data-ttu-id="b4bbb-115">Weitere Informationen finden Sie unter [Paketkonfigurationen](../../2014/integration-services/package-configurations.md), [Erstellen von Paketkonfigurationen](../../2014/integration-services/create-package-configurations.md)und [Überlegungen zur Sicherheit bei SQL Server-Installationen](../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md).</span><span class="sxs-lookup"><span data-stu-id="b4bbb-115">For more information, see [Package Configurations](../../2014/integration-services/package-configurations.md), [Create Package Configurations](../../2014/integration-services/create-package-configurations.md), and [Security Considerations for a SQL Server Installation](../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md).</span></span>  
  
## <a name="checkpoint-files"></a><span data-ttu-id="b4bbb-116">Prüfpunktdateien</span><span class="sxs-lookup"><span data-stu-id="b4bbb-116">Checkpoint Files</span></span>  
 <span data-ttu-id="b4bbb-117">Wenn die vom Paket verwendete Prüfpunktdatei vertrauliche Informationen enthält, sollten Sie entsprechend mithilfe einer Zugriffssteuerungsliste den Speicherort oder Ordner schützen, in dem Sie die Datei speichern.</span><span class="sxs-lookup"><span data-stu-id="b4bbb-117">Similarly, if the checkpoint file that the package uses includes sensitive information, you should use an access control list (ACL) to secure the location or folder where you store the file.</span></span> <span data-ttu-id="b4bbb-118">In Prüfpunktdateien werden aktuelle Statusinformationen zum Fortschritt des Pakets sowie die aktuellen Werte von Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b4bbb-118">Checkpoint files save current state information on the progress of the package as well as the current values of variables.</span></span> <span data-ttu-id="b4bbb-119">Beispielsweise kann das Paket eine benutzerdefinierte Variable mit einer Telefonnummer enthalten.</span><span class="sxs-lookup"><span data-stu-id="b4bbb-119">For example, the package may include a custom variable that contains a telephone number.</span></span> <span data-ttu-id="b4bbb-120">Weitere Informationen finden Sie unter [Neustarten von Paketen mit Prüfpunkten](packages/restart-packages-by-using-checkpoints.md).</span><span class="sxs-lookup"><span data-stu-id="b4bbb-120">For more information, see [Restart Packages by Using Checkpoints](packages/restart-packages-by-using-checkpoints.md).</span></span>  
  
## <a name="log-files"></a><span data-ttu-id="b4bbb-121">Protokolldateien</span><span class="sxs-lookup"><span data-stu-id="b4bbb-121">Log Files</span></span>  
 <span data-ttu-id="b4bbb-122">Protokolleinträge, die in das Dateisystem geschrieben werden, sollten ebenfalls mithilfe einer Zugriffssteuerungsliste geschützt werden.</span><span class="sxs-lookup"><span data-stu-id="b4bbb-122">Log entries that are written to the file system should also be secured using an access control list (ACL).</span></span> <span data-ttu-id="b4bbb-123">Protokolleinträge können auch in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Tabellen gespeichert und mithilfe der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Sicherheit geschützt werden.</span><span class="sxs-lookup"><span data-stu-id="b4bbb-123">Log entries can also be stored in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] tables and protected by [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] security.</span></span> <span data-ttu-id="b4bbb-124">Protokolleinträge können vertrauliche Informationen enthalten. Angenommen, das Paket enthält einen Task SQL ausführen, mit dem eine SQL-Anweisung erstellt wird, die auf eine Telefonnummer verweist. In diesem Fall enthält der Protokolleintrag der SQL-Anweisung die Telefonnummer.</span><span class="sxs-lookup"><span data-stu-id="b4bbb-124">Log entries may include sensitive information, For example, if the package contains an Execute SQL task that constructs an SQL statement that refers to a telephone number, the log entry for the SQL statement includes the telephone number.</span></span> <span data-ttu-id="b4bbb-125">Die SQL-Anweisung kann auch private Informationen zu Tabellen- und Spaltennamen in Datenbanken anzeigen.</span><span class="sxs-lookup"><span data-stu-id="b4bbb-125">The SQL statement may also reveal private information about table and column names in databases.</span></span> <span data-ttu-id="b4bbb-126">Weitere Informationen finden Sie unter [Integration Services-Protokollierung &#40;SSIS&#41;](performance/integration-services-ssis-logging.md).</span><span class="sxs-lookup"><span data-stu-id="b4bbb-126">For more information, see [Integration Services &#40;SSIS&#41; Logging](performance/integration-services-ssis-logging.md).</span></span>  
  
  
