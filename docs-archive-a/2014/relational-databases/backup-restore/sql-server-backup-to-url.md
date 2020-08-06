---
title: SQL Server-Sicherung über URLs | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: 11be89e9-ff2a-4a94-ab5d-27d8edf9167d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6918a099e00b1de9e773320b5c6c0e4089859e02
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718328"
---
# <a name="sql-server-backup-to-url"></a><span data-ttu-id="25fee-102">SQL Server-Sicherung über URLs</span><span class="sxs-lookup"><span data-stu-id="25fee-102">SQL Server Backup to URL</span></span>
  <span data-ttu-id="25fee-103">In diesem Thema werden die Konzepte, Anforderungen und Komponenten vorgestellt, die für die Verwendung des Azure-BLOB-Speicher Dienstanbieter als Sicherungs Ziel erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="25fee-103">This topic introduces the concepts, requirements and components necessary to use the Azure Blob storage service as a backup destination.</span></span> <span data-ttu-id="25fee-104">Die Sicherungs- und Wiederherstellungsfunktion sind gleich oder ähnlich wie beim Verwenden von DISK oder TAPE, mit wenigen Unterschieden.</span><span class="sxs-lookup"><span data-stu-id="25fee-104">The backup and restore functionality are same or similar to when using DISK or TAPE, with a few differences.</span></span> <span data-ttu-id="25fee-105">Die Unterschiede und alle wichtigen Ausnahmen sowie einige Codebeispiele werden in diesem Thema erörtert.</span><span class="sxs-lookup"><span data-stu-id="25fee-105">The differences are and any notable exceptions, and a few code examples are included in this topic.</span></span>  
  
## <a name="requirements-components-and-concepts"></a><span data-ttu-id="25fee-106">Anforderungen, Komponenten und Konzepte</span><span class="sxs-lookup"><span data-stu-id="25fee-106">Requirements, Components, and Concepts</span></span>  
 <span data-ttu-id="25fee-107">**In diesem Abschnitt:**</span><span class="sxs-lookup"><span data-stu-id="25fee-107">**In this section:**</span></span>  
  
-   [<span data-ttu-id="25fee-108">Security</span><span class="sxs-lookup"><span data-stu-id="25fee-108">Security</span></span>](#security)  
  
-   [<span data-ttu-id="25fee-109">Einführung in die wichtigsten Komponenten und Konzepte</span><span class="sxs-lookup"><span data-stu-id="25fee-109">Introduction to Key Components and Concepts</span></span>](#intorkeyconcepts)  
  
-   [<span data-ttu-id="25fee-110">Azure BLOB Storage-Dienst</span><span class="sxs-lookup"><span data-stu-id="25fee-110">Azure Blob Storage Service</span></span>](#Blob)  
  
-   [<span data-ttu-id="25fee-111">SQL Server Komponenten</span><span class="sxs-lookup"><span data-stu-id="25fee-111">SQL Server Components</span></span>](#sqlserver)  
  
-   [<span data-ttu-id="25fee-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="25fee-112">Limitations</span></span>](#limitations)  
  
-   [<span data-ttu-id="25fee-113">Unterstützung für Backup/Restore-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="25fee-113">Support for Backup/Restore Statements</span></span>](#Support)  
  
-   [<span data-ttu-id="25fee-114">Verwenden des Sicherungstasks in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="25fee-114">Using Backup Task in SQL Server Management Studio</span></span>](sql-server-backup-to-url.md#BackupTaskSSMS)  
  
-   [<span data-ttu-id="25fee-115">SQL Server-Sicherung über URLs mithilfe des Wartungsplanungs-Assistenten</span><span class="sxs-lookup"><span data-stu-id="25fee-115">SQL Server Backup to URL Using Maintenance Plan Wizard</span></span>](sql-server-backup-to-url.md#MaintenanceWiz)  
  
-   [<span data-ttu-id="25fee-116">Wiederherstellen aus Azure Storage mithilfe von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="25fee-116">Restoring from Azure storage Using SQL Server Management Studio</span></span>](sql-server-backup-to-url.md#RestoreSSMS)  
  
###  <a name="security"></a><a name="security"></a> <span data-ttu-id="25fee-117">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="25fee-117">Security</span></span>  
 <span data-ttu-id="25fee-118">Im folgenden finden Sie Sicherheitsüberlegungen und-Anforderungen beim Sichern oder Wiederherstellen von Azure BLOB Storage-Diensten.</span><span class="sxs-lookup"><span data-stu-id="25fee-118">The following are security considerations and requirements when backing up to or restoring from the Azure Blob storage services.</span></span>  
  
-   <span data-ttu-id="25fee-119">Beim Erstellen eines Containers für den Azure BLOB Storage-Dienst wird empfohlen, den Zugriff auf **Privat**festzulegen.</span><span class="sxs-lookup"><span data-stu-id="25fee-119">When creating a container for the Azure Blob storage service, we recommend that you set the access to **private**.</span></span> <span data-ttu-id="25fee-120">Dadurch wird der Zugriff auf Benutzer oder Konten beschränkt, die über die erforderlichen Anmeldeinformationen zur Authentifizierung beim Azure-Konto verfügen.</span><span class="sxs-lookup"><span data-stu-id="25fee-120">Setting the access to private restricts the access to users or accounts able to provide the necessary information to authenticate to the Azure account.</span></span>  
  
    > [!IMPORTANT]  
    >  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="25fee-121">erfordert, dass der Azure-Konto Name und die Zugriffsschlüssel Authentifizierung in Anmelde Informationen gespeichert werden [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="25fee-121">requires Azure account name and access key authentication to be stored in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Credential.</span></span> <span data-ttu-id="25fee-122">Diese Informationen werden verwendet, um beim Ausführen von Sicherungs-oder Wiederherstellungs Vorgängen bei dem Azure-Konto zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="25fee-122">This information is used to authenticate to the Azure account when it performs backup or restore operations.</span></span>  
  
-   <span data-ttu-id="25fee-123">Das zum Ausgeben von BACKUP- oder RESTORE-Befehlen verwendete Benutzerkonto sollte Mitglied der Datenbankrolle **db_backup operator** sein und über Berechtigungen zum **Ändern beliebiger Anmeldeinformationen** verfügen.</span><span class="sxs-lookup"><span data-stu-id="25fee-123">The user account that is used to issue BACKUP or RESTORE commands should be in the **db_backup operator** database role with **Alter any credential** permissions.</span></span>  
  
###  <a name="introduction-to-key-components-and-concepts"></a><a name="intorkeyconcepts"></a><span data-ttu-id="25fee-124">Einführung in die wichtigsten Komponenten und Konzepte</span><span class="sxs-lookup"><span data-stu-id="25fee-124">Introduction to Key Components and Concepts</span></span>  
 <span data-ttu-id="25fee-125">In den folgenden beiden Abschnitten werden der Azure BLOB Storage-Dienst und die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] für die Sicherung oder Wiederherstellung im Azure-BLOB-Speicherdienst verwendeten Komponenten vorgestellt.</span><span class="sxs-lookup"><span data-stu-id="25fee-125">The following two sections introduce the Azure Blob storage service, and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components used when backing up to or restoring from the Azure Blob storage service.</span></span> <span data-ttu-id="25fee-126">Es ist wichtig, die Komponenten und die Interaktion zwischen den Komponenten zu verstehen, um eine Sicherung oder Wiederherstellung aus dem Azure-BLOB-Speicherdienst durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="25fee-126">It is important to understand the components and the interaction between them to do a backup to or restore from the Azure Blob storage service.</span></span>  
  
 <span data-ttu-id="25fee-127">Der erste Schritt dieses Prozesses ist das Erstellen eines Azure-Kontos.</span><span class="sxs-lookup"><span data-stu-id="25fee-127">Creating an Azure account is the first step to this process.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="25fee-128">verwendet den **Azure Storage-Kontonamen** und seine **Zugriffsschlüssel** Werte, um BLOB-BLOB-Speicherdienste zu authentifizieren und zu schreiben und zu lesen.</span><span class="sxs-lookup"><span data-stu-id="25fee-128">uses the **Azure storage account name** and its **access key** values to authenticate and write and read blobs to the storage service.</span></span> <span data-ttu-id="25fee-129">Diese Authentifizierungsinformationen werden in den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldeinformationen gespeichert und bei Sicherungs- und Wiederherstellungsvorgängen verwendet.</span><span class="sxs-lookup"><span data-stu-id="25fee-129">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Credential stores this authentication information and is used during the backup or restore operations.</span></span> <span data-ttu-id="25fee-130">Eine umfassende Exemplarische Vorgehensweise zum Erstellen eines Speicher Kontos und zum Durchführen einer einfachen Wiederherstellung finden [Sie unter Tutorial using Azure Storage Service for SQL Server Backup and Restore](https://go.microsoft.com/fwlink/?LinkId=271615).</span><span class="sxs-lookup"><span data-stu-id="25fee-130">For a complete walkthrough of creating a storage account and performing a simple restore, see [Tutorial Using Azure Storage Service for SQL Server Backup and Restore](https://go.microsoft.com/fwlink/?LinkId=271615).</span></span>  
  
 <span data-ttu-id="25fee-131">![Zuordnen des Speicherkontos zu SQL-Anmeldeinformationen](../../tutorials/media/backuptocloud-storage-credential-mapping.gif "Zuordnen des Speicherkontos zu SQL-Anmeldeinformationen")</span><span class="sxs-lookup"><span data-stu-id="25fee-131">![mapping storage account to sql credentials](../../tutorials/media/backuptocloud-storage-credential-mapping.gif "mapping storage account to sql credentials")</span></span>  
  
###  <a name="azure-blob-storage-service"></a><a name="Blob"></a><span data-ttu-id="25fee-132">Azure BLOB Storage-Dienst</span><span class="sxs-lookup"><span data-stu-id="25fee-132">Azure Blob Storage Service</span></span>  
 <span data-ttu-id="25fee-133">**Speicherkonto:** Das Speicherkonto ist der Ausgangspunkt für alle Speicherdienste.</span><span class="sxs-lookup"><span data-stu-id="25fee-133">**Storage Account:** The storage account is the starting point for all storage services.</span></span> <span data-ttu-id="25fee-134">Um auf den Azure BLOB Storage-Dienst zuzugreifen, erstellen Sie zunächst ein Azure-Speicherkonto.</span><span class="sxs-lookup"><span data-stu-id="25fee-134">To access the Azure Blob Storage service, first create an Azure storage account.</span></span> <span data-ttu-id="25fee-135">Der **Speicherkonto Name** und seine **Zugriffsschlüssel** Eigenschaften sind erforderlich, um sich beim Azure BLOB Storage-Dienst und dessen Komponenten zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="25fee-135">The **storage account name** and its **access key** properties are required to authenticate to the Azure Blob Storage service and its components.</span></span>  
  
 <span data-ttu-id="25fee-136">**Container:** Ein Container stellt eine Gruppierung eines Satzes von blobspeicher bereit und kann eine unbegrenzte Anzahl von blobspeicher speichern.</span><span class="sxs-lookup"><span data-stu-id="25fee-136">**Container:** A container provides a grouping of a set of Blobs, and can store an unlimited number of Blobs.</span></span> <span data-ttu-id="25fee-137">Um eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Sicherung in den Azure-BLOB-Dienst zu schreiben, muss mindestens der Stamm Container erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="25fee-137">To write a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup to the Azure Blob service, you must have at least the root container created.</span></span>  
  
 <span data-ttu-id="25fee-138">**BLOB:** Eine Datei eines beliebigen Typs und beliebiger Größe.</span><span class="sxs-lookup"><span data-stu-id="25fee-138">**Blob:** A file of any type and size.</span></span> <span data-ttu-id="25fee-139">Es gibt zwei Typen von BLOBs, die im Azure-BLOB-Speicherdienst gespeichert werden können: Block-und seitenblobs.</span><span class="sxs-lookup"><span data-stu-id="25fee-139">There are two types of blobs that can be stored in the Azure Blob storage service: block and page blobs.</span></span> <span data-ttu-id="25fee-140">Bei der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Sicherung werden Seitenblobs als Blobtyp verwendet.</span><span class="sxs-lookup"><span data-stu-id="25fee-140">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup uses page Blobs as the Blob type.</span></span> <span data-ttu-id="25fee-141">BLOB können mithilfe des folgenden URL-Formats adressiert werden: https:// \<storage account> . BLOB.Core.Windows.net/\<container>/\<blob></span><span class="sxs-lookup"><span data-stu-id="25fee-141">Blobs are addressable using the following URL format: https://\<storage account>.blob.core.windows.net/\<container>/\<blob></span></span>  
  
 <span data-ttu-id="25fee-142">![Azure Blob Storage](../../database-engine/media/backuptocloud-blobarchitecture.gif "Azure Blob Storage")</span><span class="sxs-lookup"><span data-stu-id="25fee-142">![Azure Blob Storage](../../database-engine/media/backuptocloud-blobarchitecture.gif "Azure Blob Storage")</span></span>  
  
 <span data-ttu-id="25fee-143">Weitere Informationen zum Azure-BLOB-Speicherdienst finden [Sie unter Verwenden des Azure BLOB Storage Dienstanbieter](https://www.windowsazure.com/develop/net/how-to-guides/blob-storage/) .</span><span class="sxs-lookup"><span data-stu-id="25fee-143">For more information about the Azure Blob storage service, see [How to use the Azure Blob Storage Service](https://www.windowsazure.com/develop/net/how-to-guides/blob-storage/)</span></span>  
  
 <span data-ttu-id="25fee-144">Weitere Informationen über Seitenblobs finden Sie unter [Grundlegendes zu Block- und Seitenblobs](https://msdn.microsoft.com/library/windowsazure/ee691964.aspx)</span><span class="sxs-lookup"><span data-stu-id="25fee-144">For more information about page Blobs, see [Understanding Block and Page Blobs](https://msdn.microsoft.com/library/windowsazure/ee691964.aspx)</span></span>  
  
###  <a name="ssnoversion-components"></a><a name="sqlserver"></a> <span data-ttu-id="25fee-145">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Komponenten</span><span class="sxs-lookup"><span data-stu-id="25fee-145">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Components</span></span>  
 <span data-ttu-id="25fee-146">**URL:** Eine URL gibt einen URI (Uniform Resource Identifier) für eine eindeutige Sicherungsdatei an.</span><span class="sxs-lookup"><span data-stu-id="25fee-146">**URL:** A URL specifies a Uniform Resource Identifier (URI) to a unique backup file.</span></span> <span data-ttu-id="25fee-147">Mit der URL werden Speicherort und Name der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Sicherungsdatei angegeben.</span><span class="sxs-lookup"><span data-stu-id="25fee-147">The URL is used to provide the location and name of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup file.</span></span> <span data-ttu-id="25fee-148">In dieser Implementierung ist die einzige gültige URL eine, die auf ein seitenblob in einem Azure-Speicherkonto verweist.</span><span class="sxs-lookup"><span data-stu-id="25fee-148">In this implementation, the only valid URL is one that points to a page Blob in an Azure storage account.</span></span> <span data-ttu-id="25fee-149">Die URL muss auf ein tatsächliches BLOB, nicht nur auf einen Container verweisen.</span><span class="sxs-lookup"><span data-stu-id="25fee-149">The URL must point to an actual Blob, not just a container.</span></span> <span data-ttu-id="25fee-150">Wenn das BLOB nicht vorhanden ist, wird es erstellt.</span><span class="sxs-lookup"><span data-stu-id="25fee-150">If the Blob does not exist, it is created.</span></span> <span data-ttu-id="25fee-151">Wenn ein vorhandenes BLOB angegeben wird, tritt bei der Sicherung ein Fehler auf, es sei denn, die with Format-Option ist angegeben.</span><span class="sxs-lookup"><span data-stu-id="25fee-151">If an existing Blob is specified, BACKUP fails, unless the "WITH FORMAT" option is specified.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="25fee-152">Wenn Sie eine Sicherungsdatei kopieren und in den Azure-BLOB-Speicherdienst hochladen möchten, verwenden Sie seitenblob als Speicher Option.</span><span class="sxs-lookup"><span data-stu-id="25fee-152">If you choose to copy and upload a backup file to the Azure Blob storage service, use page blob as your storage option.</span></span> <span data-ttu-id="25fee-153">Wiederherstellungen von Blockblobs werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="25fee-153">Restores from Block Blobs are not supported.</span></span> <span data-ttu-id="25fee-154">Die Ausführung von RESTORE für ein Blockblob verursacht einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="25fee-154">RESTORE from a block blob type fails with an error.</span></span>  
  
 <span data-ttu-id="25fee-155">Hier ist ein Beispiel-URL-Wert: http [s]://ACCOUNTNAME.BLOB.Core.Windows.net/ \<CONTAINER> / \<FILENAME.bak> .</span><span class="sxs-lookup"><span data-stu-id="25fee-155">Here is a sample URL value: http[s]://ACCOUNTNAME.Blob.core.windows.net/\<CONTAINER>/\<FILENAME.bak>.</span></span> <span data-ttu-id="25fee-156">HTTPS ist zwar nicht erforderlich, aber empfehlenswert.</span><span class="sxs-lookup"><span data-stu-id="25fee-156">HTTPS is not required, but is recommended.</span></span>  
  
 <span data-ttu-id="25fee-157">**Anmeldeinformationen:** [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Anmeldeinformationen sind ein Objekt zum Speichern von Authentifizierungsinformationen, die für die Verbindung mit einer Ressource außerhalb von SQL Server erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="25fee-157">**Credential:** A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] credential is an object that is used to store authentication information required to connect to a resource outside of SQL Server.</span></span>  <span data-ttu-id="25fee-158">Hier werden [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] von Sicherungs-und Wiederherstellungs Prozessen Anmelde Informationen für die Authentifizierung beim Azure BLOB Storage-Dienst verwendet.</span><span class="sxs-lookup"><span data-stu-id="25fee-158">Here, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup and restore processes use credential to authenticate to the Azure Blob storage service.</span></span> <span data-ttu-id="25fee-159">In den Anmeldeinformationen werden der Name des Speicherkontos und der **Zugriffsschlüssel** des Speicherkontos gespeichert.</span><span class="sxs-lookup"><span data-stu-id="25fee-159">The Credential stores the name of the storage account and the storage account **access key** values.</span></span> <span data-ttu-id="25fee-160">Sobald die Anmeldeinformationen erstellt wurden, müssen sie beim Ausgeben der BACKUP-/RESTORE-Anweisungen in der WITH CREDENTIAL-Option angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="25fee-160">Once the credential is created, it must be specified in the WITH CREDENTIAL option when issuing the BACKUP/RESTORE statements.</span></span> <span data-ttu-id="25fee-161">Weitere Informationen zum Anzeigen, Kopieren oder erneuten Generieren von **access keys**für Speicherkonten finden Sie unter [Zugriffsschlüssel für Speicherkonten](https://msdn.microsoft.com/library/windowsazure/hh531566.aspx).</span><span class="sxs-lookup"><span data-stu-id="25fee-161">For more information about how to view, copy or regenerate storage account **access keys**, see [Storage Account Access Keys](https://msdn.microsoft.com/library/windowsazure/hh531566.aspx).</span></span>  
  
 <span data-ttu-id="25fee-162">Schritt-für-Schritt-Anweisungen zum Erstellen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldeinformationen finden Sie im Beispiel [Create a Credential](#credential) weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="25fee-162">For step by step instructions about how to create a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Credential, see [Create a Credential](#credential) example later in this topic.</span></span>  
  
 <span data-ttu-id="25fee-163">Weitere allgemeine Informationen über Anmeldeinformationen finden Sie unter [Anmeldeinformationen](../security/authentication-access/credentials-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="25fee-163">For general information about credentials, see [Credentials](../security/authentication-access/credentials-database-engine.md)</span></span>  
  
 <span data-ttu-id="25fee-164">Informationen zu anderen Beispielen, in denen Anmelde Informationen verwendet werden, finden Sie unter [Erstellen eines SQL Server-Agent Proxys](../../ssms/agent/create-a-sql-server-agent-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="25fee-164">For information, on other examples where credentials are used, see [Create a SQL Server Agent Proxy](../../ssms/agent/create-a-sql-server-agent-proxy.md).</span></span>  
  
###  <a name="limitations"></a><a name="limitations"></a> <span data-ttu-id="25fee-165">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="25fee-165">Limitations</span></span>  
  
-   <span data-ttu-id="25fee-166">Das Sichern auf Premium-Speicher wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="25fee-166">Backup to premium storage is not supported.</span></span>  
  
-   <span data-ttu-id="25fee-167">Die maximal unterstützte Größe für Sicherungen beträgt 1 TB.</span><span class="sxs-lookup"><span data-stu-id="25fee-167">The maximum backup size supported is 1 TB.</span></span>  
  
-   <span data-ttu-id="25fee-168">Sie können BACKUP- und RESTORE-Anweisungen mithilfe von TSQL-, SMO- oder PowerShell-Cmdlets ausgeben.</span><span class="sxs-lookup"><span data-stu-id="25fee-168">You can issue backup or restore statements by using TSQL, SMO, or PowerShell cmdlets.</span></span> <span data-ttu-id="25fee-169">Eine Sicherung oder Wiederherstellung aus dem Azure-BLOB-Speicherdienst mithilfe SQL Server Management Studio Assistenten zum Sichern oder Wiederherstellen ist zurzeit nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="25fee-169">A backup to or restoring from the Azure Blob storage service by using SQL Server Management Studio Backup or Restore wizard is not currently enabled.</span></span>  
  
-   <span data-ttu-id="25fee-170">Das Erstellen von Namen für logische Geräte wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="25fee-170">Creating a logical device name is not supported.</span></span> <span data-ttu-id="25fee-171">Folglich ist es nicht möglich, eine URL mithilfe von sp_dumpdevice oder über SQL Server Management Studio als Sicherungsmedium hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="25fee-171">So adding URL as a backup device using sp_dumpdevice or through SQL Server Management Studio is not supported.</span></span>  
  
-   <span data-ttu-id="25fee-172">Das Anfügen an vorhandene Sicherungs-BLOBs wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="25fee-172">Appending to existing backup blobs is not supported.</span></span> <span data-ttu-id="25fee-173">Sicherungen auf einem vorhandenen BLOB können nur unter Verwendung der WITH FORMAT-Option überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="25fee-173">Backups to an existing Blob can only be overwritten by using the WITH FORMAT option.</span></span>  
  
-   <span data-ttu-id="25fee-174">Sicherungen auf mehreren BLOBS in einem einzelnen Sicherungsvorgang werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="25fee-174">Backup to multiple blobs in a single backup operation is not supported.</span></span> <span data-ttu-id="25fee-175">So gibt der folgende Code z. B. einen Fehler zurück:</span><span class="sxs-lookup"><span data-stu-id="25fee-175">For example, the following returns an error:</span></span>  
  
    ```sql
    BACKUP DATABASE AdventureWorks2012
    TO URL = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012_1.bak'
       URL = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012_2.bak'
          WITH CREDENTIAL = 'mycredential'
         ,STATS = 5;  
    GO
    ```  
  
-   <span data-ttu-id="25fee-176">Das Angeben einer Blockgröße mit `BACKUP` wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="25fee-176">Specifying a block size with `BACKUP` is not supported.</span></span>  
  
-   <span data-ttu-id="25fee-177">Das Angeben von `MAXTRANSFERSIZE` wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="25fee-177">Specifying `MAXTRANSFERSIZE` is not supported.</span></span>  
  
-   <span data-ttu-id="25fee-178">Das Angeben von Optionen für Sicherungssätze, wie `RETAINDAYS` und `EXPIREDATE`, wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="25fee-178">Specifying backupset options - `RETAINDAYS` and `EXPIREDATE` are not supported.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="25fee-179">auf 259 Zeichen begrenzt.</span><span class="sxs-lookup"><span data-stu-id="25fee-179">has a maximum limit of 259 characters for a backup device name.</span></span> <span data-ttu-id="25fee-180">Da BACKUP TO URL 36 Zeichen für die erforderlichen Elemente zur Angabe der URL (https://.blob.core.windows.net//.bak ) beansprucht, verbleiben insgesamt noch 223 Zeichen für Konto-, Container- und Blobnamen.</span><span class="sxs-lookup"><span data-stu-id="25fee-180">The BACKUP TO URL consumes 36 characters for the required elements used to specify the URL - 'https://.blob.core.windows.net//.bak', leaving 223 characters for account, container, and blob names put together.</span></span>  
  
###  <a name="support-for-backuprestore-statements"></a><a name="Support"></a> <span data-ttu-id="25fee-181">Unterstützung für BACKUP-/RESTORE-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="25fee-181">Support for Backup/Restore Statements</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="25fee-182">BACKUP-/RESTORE-Anweisung</span><span class="sxs-lookup"><span data-stu-id="25fee-182">Backup/Restore Statement</span></span>|<span data-ttu-id="25fee-183">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="25fee-183">Supported</span></span>|<span data-ttu-id="25fee-184">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="25fee-184">Exceptions</span></span>|<span data-ttu-id="25fee-185">Kommentare</span><span class="sxs-lookup"><span data-stu-id="25fee-185">Comments</span></span>|  
|<span data-ttu-id="25fee-186">BACKUP</span><span class="sxs-lookup"><span data-stu-id="25fee-186">BACKUP</span></span>|<span data-ttu-id="25fee-187">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-187">&#x2713;</span></span>|<span data-ttu-id="25fee-188">BLOCKSIZE und MAXTRANSFERSIZE werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="25fee-188">BLOCKSIZE, and MAXTRANSFERSIZE are not supported.</span></span>|<span data-ttu-id="25fee-189">WITH CREDENTIAL muss angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="25fee-189">Requires WITH CREDENTIAL specified</span></span>|  
|<span data-ttu-id="25fee-190">RESTORE</span><span class="sxs-lookup"><span data-stu-id="25fee-190">RESTORE</span></span>|<span data-ttu-id="25fee-191">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-191">&#x2713;</span></span>||<span data-ttu-id="25fee-192">WITH CREDENTIAL muss angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="25fee-192">Requires WITH CREDENTIAL specified</span></span>|  
|<span data-ttu-id="25fee-193">RESTORE FILELISTONLY</span><span class="sxs-lookup"><span data-stu-id="25fee-193">RESTORE FILELISTONLY</span></span>|<span data-ttu-id="25fee-194">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-194">&#x2713;</span></span>||<span data-ttu-id="25fee-195">WITH CREDENTIAL muss angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="25fee-195">Requires WITH CREDENTIAL specified</span></span>|  
|<span data-ttu-id="25fee-196">RESTORE HEADERONLY</span><span class="sxs-lookup"><span data-stu-id="25fee-196">RESTORE HEADERONLY</span></span>|<span data-ttu-id="25fee-197">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-197">&#x2713;</span></span>||<span data-ttu-id="25fee-198">WITH CREDENTIAL muss angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="25fee-198">Requires WITH CREDENTIAL specified</span></span>|  
|<span data-ttu-id="25fee-199">RESTORE LABELONLY</span><span class="sxs-lookup"><span data-stu-id="25fee-199">RESTORE LABELONLY</span></span>|<span data-ttu-id="25fee-200">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-200">&#x2713;</span></span>||<span data-ttu-id="25fee-201">WITH CREDENTIAL muss angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="25fee-201">Requires WITH CREDENTIAL specified</span></span>|  
|<span data-ttu-id="25fee-202">RESTORE VERIFYONLY</span><span class="sxs-lookup"><span data-stu-id="25fee-202">RESTORE VERIFYONLY</span></span>|<span data-ttu-id="25fee-203">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-203">&#x2713;</span></span>||<span data-ttu-id="25fee-204">WITH CREDENTIAL muss angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="25fee-204">Requires WITH CREDENTIAL specified</span></span>|  
|<span data-ttu-id="25fee-205">RESTORE REWINDONLY</span><span class="sxs-lookup"><span data-stu-id="25fee-205">RESTORE REWINDONLY</span></span>|<span data-ttu-id="25fee-206">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-206">&#x2713;</span></span>|||  
  
 <span data-ttu-id="25fee-207">Allgemeine und Syntaxinformationen zu BACKUP-Anweisungen finden Sie unter [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="25fee-207">For syntax and general information about backup statements, see [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span></span>  
  
 <span data-ttu-id="25fee-208">Allgemeine und Syntaxinformationen zu RESTORE-Anweisungen finden Sie unter [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="25fee-208">For syntax and general information about restore statements, see [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span></span>  
  
### <a name="support-for-backup-arguments"></a><span data-ttu-id="25fee-209">Unterstützung für BACKUP-Argumente</span><span class="sxs-lookup"><span data-stu-id="25fee-209">Support for Backup Arguments</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="25fee-210">Argument</span><span class="sxs-lookup"><span data-stu-id="25fee-210">Argument</span></span>|<span data-ttu-id="25fee-211">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="25fee-211">Supported</span></span>|<span data-ttu-id="25fee-212">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="25fee-212">Exception</span></span>|<span data-ttu-id="25fee-213">Kommentare</span><span class="sxs-lookup"><span data-stu-id="25fee-213">Comments</span></span>|  
|<span data-ttu-id="25fee-214">DATABASE</span><span class="sxs-lookup"><span data-stu-id="25fee-214">DATABASE</span></span>|<span data-ttu-id="25fee-215">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-215">&#x2713;</span></span>|||  
|<span data-ttu-id="25fee-216">PROTOKOLL</span><span class="sxs-lookup"><span data-stu-id="25fee-216">LOG</span></span>|<span data-ttu-id="25fee-217">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-217">&#x2713;</span></span>|||  
||  
|<span data-ttu-id="25fee-218">TO (URL)</span><span class="sxs-lookup"><span data-stu-id="25fee-218">TO (URL)</span></span>|<span data-ttu-id="25fee-219">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-219">&#x2713;</span></span>|<span data-ttu-id="25fee-220">Bei URL wird das Angeben bzw. Erstellen eines logischen Namens im Gegensatz zu DISK und TAPE nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="25fee-220">Unlike DISK and TAPE, URL does not support specifying or creating a logical name.</span></span>|<span data-ttu-id="25fee-221">Dieses Argument wird verwendet, um den URL-Pfad der Sicherungsdatei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="25fee-221">This argument is used to specify the URL path for the backup file.</span></span>|  
|<span data-ttu-id="25fee-222">MIRROR TO</span><span class="sxs-lookup"><span data-stu-id="25fee-222">MIRROR TO</span></span>|<span data-ttu-id="25fee-223">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-223">&#x2713;</span></span>|||  
|<span data-ttu-id="25fee-224">**WITH-OPTIONEN:**</span><span class="sxs-lookup"><span data-stu-id="25fee-224">**WITH OPTIONS:**</span></span>||||  
|<span data-ttu-id="25fee-225">CREDENTIAL</span><span class="sxs-lookup"><span data-stu-id="25fee-225">CREDENTIAL</span></span>|<span data-ttu-id="25fee-226">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-226">&#x2713;</span></span>||<span data-ttu-id="25fee-227">WITH Credential wird nur unterstützt, wenn die Option Backup to URL zum Sichern im Azure BLOB Storage-Dienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="25fee-227">WITH CREDENTIAL is only supported when using BACKUP TO URL option to back up to the Azure Blob storage service.</span></span>|  
|<span data-ttu-id="25fee-228">DIFFERENTIAL</span><span class="sxs-lookup"><span data-stu-id="25fee-228">DIFFERENTIAL</span></span>|<span data-ttu-id="25fee-229">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-229">&#x2713;</span></span>|||  
|<span data-ttu-id="25fee-230">COPY_ONLY</span><span class="sxs-lookup"><span data-stu-id="25fee-230">COPY_ONLY</span></span>|<span data-ttu-id="25fee-231">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-231">&#x2713;</span></span>|||  
|<span data-ttu-id="25fee-232">COMPRESSION&#124;NO_COMPRESSION</span><span class="sxs-lookup"><span data-stu-id="25fee-232">COMPRESSION&#124;NO_COMPRESSION</span></span>|<span data-ttu-id="25fee-233">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-233">&#x2713;</span></span>|||  
|<span data-ttu-id="25fee-234">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="25fee-234">DESCRIPTION</span></span>|<span data-ttu-id="25fee-235">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-235">&#x2713;</span></span>|||  
|<span data-ttu-id="25fee-236">NAME</span><span class="sxs-lookup"><span data-stu-id="25fee-236">NAME</span></span>|<span data-ttu-id="25fee-237">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-237">&#x2713;</span></span>|||  
|<span data-ttu-id="25fee-238">EXPIREDATE &#124; RETAINDAYS</span><span class="sxs-lookup"><span data-stu-id="25fee-238">EXPIREDATE &#124; RETAINDAYS</span></span>|<span data-ttu-id="25fee-239">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-239">&#x2713;</span></span>|||  
|<span data-ttu-id="25fee-240">NOINIT &#124; INIT</span><span class="sxs-lookup"><span data-stu-id="25fee-240">NOINIT &#124; INIT</span></span>|<span data-ttu-id="25fee-241">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-241">&#x2713;</span></span>||<span data-ttu-id="25fee-242">Wenn diese Option verwendet wird, wird sie ignoriert.</span><span class="sxs-lookup"><span data-stu-id="25fee-242">This option is ignored if used.</span></span><br /><br /> <span data-ttu-id="25fee-243">Das Anfügen an BLOBs ist nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="25fee-243">Appending to blobs is not possible.</span></span> <span data-ttu-id="25fee-244">Verwenden Sie zum Überschreiben einer Sicherung das FORMAT-Argument.</span><span class="sxs-lookup"><span data-stu-id="25fee-244">To overwrite a backup use the FORMAT argument.</span></span>|  
|<span data-ttu-id="25fee-245">NOSKIP &#124; SKIP</span><span class="sxs-lookup"><span data-stu-id="25fee-245">NOSKIP &#124; SKIP</span></span>|<span data-ttu-id="25fee-246">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-246">&#x2713;</span></span>|||  
|<span data-ttu-id="25fee-247">NOFORMAT &#124; FORMAT</span><span class="sxs-lookup"><span data-stu-id="25fee-247">NOFORMAT &#124; FORMAT</span></span>|<span data-ttu-id="25fee-248">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-248">&#x2713;</span></span>||<span data-ttu-id="25fee-249">Wenn diese Option verwendet wird, wird sie ignoriert.</span><span class="sxs-lookup"><span data-stu-id="25fee-249">This option is ignored if used.</span></span><br /><br /> <span data-ttu-id="25fee-250">Eine Sicherung, die auf ein vorhandenes BLOB geschrieben wird, ist nur erfolgreich, wenn WITH FORMAT angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="25fee-250">A backup taken to an existing blob fails unless WITH FORMAT is specified.</span></span> <span data-ttu-id="25fee-251">Das vorhandene BLOB wird bei Angabe von WITH FORMAT überschrieben.</span><span class="sxs-lookup"><span data-stu-id="25fee-251">The existing blob is overwritten when WITH FORMAT is specified.</span></span>|  
|<span data-ttu-id="25fee-252">MEDIADESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="25fee-252">MEDIADESCRIPTION</span></span>|<span data-ttu-id="25fee-253">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-253">&#x2713;</span></span>|||  
|<span data-ttu-id="25fee-254">MEDIANAME</span><span class="sxs-lookup"><span data-stu-id="25fee-254">MEDIANAME</span></span>|<span data-ttu-id="25fee-255">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-255">&#x2713;</span></span>|||  
|<span data-ttu-id="25fee-256">BLOCKSIZE</span><span class="sxs-lookup"><span data-stu-id="25fee-256">BLOCKSIZE</span></span>|<span data-ttu-id="25fee-257">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-257">&#x2713;</span></span>|||  
|<span data-ttu-id="25fee-258">BUFFERCOUNT</span><span class="sxs-lookup"><span data-stu-id="25fee-258">BUFFERCOUNT</span></span>|<span data-ttu-id="25fee-259">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-259">&#x2713;</span></span>|||  
|<span data-ttu-id="25fee-260">MAXTRANSFERSIZE</span><span class="sxs-lookup"><span data-stu-id="25fee-260">MAXTRANSFERSIZE</span></span>|<span data-ttu-id="25fee-261">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-261">&#x2713;</span></span>|||  
|<span data-ttu-id="25fee-262">NO_CHECKSUM &#124; CHECKSUM</span><span class="sxs-lookup"><span data-stu-id="25fee-262">NO_CHECKSUM &#124; CHECKSUM</span></span>|<span data-ttu-id="25fee-263">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-263">&#x2713;</span></span>|||  
|<span data-ttu-id="25fee-264">STOP_ON_ERROR &#124; CONTINUE_AFTER_ERROR</span><span class="sxs-lookup"><span data-stu-id="25fee-264">STOP_ON_ERROR &#124; CONTINUE_AFTER_ERROR</span></span>|<span data-ttu-id="25fee-265">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-265">&#x2713;</span></span>|||  
|<span data-ttu-id="25fee-266">STATISTIK</span><span class="sxs-lookup"><span data-stu-id="25fee-266">STATS</span></span>|<span data-ttu-id="25fee-267">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-267">&#x2713;</span></span>|||  
|<span data-ttu-id="25fee-268">REWIND &#124; NOREWIND</span><span class="sxs-lookup"><span data-stu-id="25fee-268">REWIND &#124; NOREWIND</span></span>|<span data-ttu-id="25fee-269">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-269">&#x2713;</span></span>|||  
|<span data-ttu-id="25fee-270">UNLOAD &#124; NOUNLOAD</span><span class="sxs-lookup"><span data-stu-id="25fee-270">UNLOAD &#124; NOUNLOAD</span></span>|<span data-ttu-id="25fee-271">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-271">&#x2713;</span></span>|||  
|<span data-ttu-id="25fee-272">NORECOVERY &#124; STANDBY</span><span class="sxs-lookup"><span data-stu-id="25fee-272">NORECOVERY &#124; STANDBY</span></span>|<span data-ttu-id="25fee-273">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-273">&#x2713;</span></span>|||  
|<span data-ttu-id="25fee-274">NO_TRUNCATE</span><span class="sxs-lookup"><span data-stu-id="25fee-274">NO_TRUNCATE</span></span>|<span data-ttu-id="25fee-275">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-275">&#x2713;</span></span>|||  
  
 <span data-ttu-id="25fee-276">Weitere Informationen zu BACKUP-Argumenten finden Sie unter [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="25fee-276">For more information about backup arguments, see [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span></span>  
  
### <a name="support-for-restore-arguments"></a><span data-ttu-id="25fee-277">Unterstützung für RESTORE-Argumente</span><span class="sxs-lookup"><span data-stu-id="25fee-277">Support for Restore Arguments</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="25fee-278">Argument</span><span class="sxs-lookup"><span data-stu-id="25fee-278">Argument</span></span>|<span data-ttu-id="25fee-279">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="25fee-279">Supported</span></span>|<span data-ttu-id="25fee-280">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="25fee-280">Exceptions</span></span>|<span data-ttu-id="25fee-281">Kommentare</span><span class="sxs-lookup"><span data-stu-id="25fee-281">Comments</span></span>|  
|<span data-ttu-id="25fee-282">DATABASE</span><span class="sxs-lookup"><span data-stu-id="25fee-282">DATABASE</span></span>|<span data-ttu-id="25fee-283">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-283">&#x2713;</span></span>|||  
|<span data-ttu-id="25fee-284">PROTOKOLL</span><span class="sxs-lookup"><span data-stu-id="25fee-284">LOG</span></span>|<span data-ttu-id="25fee-285">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-285">&#x2713;</span></span>|||  
|<span data-ttu-id="25fee-286">FROM (URL)</span><span class="sxs-lookup"><span data-stu-id="25fee-286">FROM (URL)</span></span>|<span data-ttu-id="25fee-287">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-287">&#x2713;</span></span>||<span data-ttu-id="25fee-288">Das FROM URL-Argument wird verwendet, um den URL-Pfad der Sicherungsdatei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="25fee-288">The FROM URL argument is used to specify the URL path for the backup file.</span></span>|  
|<span data-ttu-id="25fee-289">**WITH Options:**</span><span class="sxs-lookup"><span data-stu-id="25fee-289">**WITH Options:**</span></span>||||  
|<span data-ttu-id="25fee-290">CREDENTIAL</span><span class="sxs-lookup"><span data-stu-id="25fee-290">CREDENTIAL</span></span>|<span data-ttu-id="25fee-291">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-291">&#x2713;</span></span>||<span data-ttu-id="25fee-292">WITH Credential wird nur unterstützt, wenn die Option Restore from URL für die Wiederherstellung aus Azure BLOB Storage-Dienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="25fee-292">WITH CREDENTIAL is only supported when using RESTORE FROM URL option to restore from Azure Blob Storage service.</span></span>|  
|<span data-ttu-id="25fee-293">PARTIAL</span><span class="sxs-lookup"><span data-stu-id="25fee-293">PARTIAL</span></span>|<span data-ttu-id="25fee-294">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-294">&#x2713;</span></span>|||  
|<span data-ttu-id="25fee-295">RECOVERY &#124; NORECOVERY &#124; STANDBY</span><span class="sxs-lookup"><span data-stu-id="25fee-295">RECOVERY &#124; NORECOVERY &#124; STANDBY</span></span>|<span data-ttu-id="25fee-296">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-296">&#x2713;</span></span>|||  
|<span data-ttu-id="25fee-297">LOADHISTORY</span><span class="sxs-lookup"><span data-stu-id="25fee-297">LOADHISTORY</span></span>|<span data-ttu-id="25fee-298">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-298">&#x2713;</span></span>|||  
|<span data-ttu-id="25fee-299">MOVE</span><span class="sxs-lookup"><span data-stu-id="25fee-299">MOVE</span></span>|<span data-ttu-id="25fee-300">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-300">&#x2713;</span></span>|||  
|<span data-ttu-id="25fee-301">REPLACE</span><span class="sxs-lookup"><span data-stu-id="25fee-301">REPLACE</span></span>|<span data-ttu-id="25fee-302">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-302">&#x2713;</span></span>|||  
|<span data-ttu-id="25fee-303">RESTART</span><span class="sxs-lookup"><span data-stu-id="25fee-303">RESTART</span></span>|<span data-ttu-id="25fee-304">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-304">&#x2713;</span></span>|||  
|<span data-ttu-id="25fee-305">RESTRICTED_USER</span><span class="sxs-lookup"><span data-stu-id="25fee-305">RESTRICTED_USER</span></span>|<span data-ttu-id="25fee-306">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-306">&#x2713;</span></span>|||  
|<span data-ttu-id="25fee-307">FILE</span><span class="sxs-lookup"><span data-stu-id="25fee-307">FILE</span></span>|<span data-ttu-id="25fee-308">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-308">&#x2713;</span></span>|||  
|<span data-ttu-id="25fee-309">PASSWORD</span><span class="sxs-lookup"><span data-stu-id="25fee-309">PASSWORD</span></span>|<span data-ttu-id="25fee-310">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-310">&#x2713;</span></span>|||  
|<span data-ttu-id="25fee-311">MEDIANAME</span><span class="sxs-lookup"><span data-stu-id="25fee-311">MEDIANAME</span></span>|<span data-ttu-id="25fee-312">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-312">&#x2713;</span></span>|||  
|<span data-ttu-id="25fee-313">MEDIAPASSWORD</span><span class="sxs-lookup"><span data-stu-id="25fee-313">MEDIAPASSWORD</span></span>|<span data-ttu-id="25fee-314">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-314">&#x2713;</span></span>|||  
|<span data-ttu-id="25fee-315">BLOCKSIZE</span><span class="sxs-lookup"><span data-stu-id="25fee-315">BLOCKSIZE</span></span>|<span data-ttu-id="25fee-316">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-316">&#x2713;</span></span>|||  
|<span data-ttu-id="25fee-317">BUFFERCOUNT</span><span class="sxs-lookup"><span data-stu-id="25fee-317">BUFFERCOUNT</span></span>|<span data-ttu-id="25fee-318">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-318">&#x2713;</span></span>|||  
|<span data-ttu-id="25fee-319">MAXTRANSFERSIZE</span><span class="sxs-lookup"><span data-stu-id="25fee-319">MAXTRANSFERSIZE</span></span>|<span data-ttu-id="25fee-320">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-320">&#x2713;</span></span>|||  
|<span data-ttu-id="25fee-321">CHECKSUM &#124; NO_CHECKSUM</span><span class="sxs-lookup"><span data-stu-id="25fee-321">CHECKSUM &#124; NO_CHECKSUM</span></span>|<span data-ttu-id="25fee-322">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-322">&#x2713;</span></span>|||  
|<span data-ttu-id="25fee-323">STOP_ON_ERROR &#124; CONTINUE_AFTER_ERROR</span><span class="sxs-lookup"><span data-stu-id="25fee-323">STOP_ON_ERROR &#124; CONTINUE_AFTER_ERROR</span></span>|<span data-ttu-id="25fee-324">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-324">&#x2713;</span></span>|||  
|<span data-ttu-id="25fee-325">FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="25fee-325">FILESTREAM</span></span>|<span data-ttu-id="25fee-326">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-326">&#x2713;</span></span>|||  
|<span data-ttu-id="25fee-327">STATISTIK</span><span class="sxs-lookup"><span data-stu-id="25fee-327">STATS</span></span>|<span data-ttu-id="25fee-328">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-328">&#x2713;</span></span>|||  
|<span data-ttu-id="25fee-329">REWIND &#124; NOREWIND</span><span class="sxs-lookup"><span data-stu-id="25fee-329">REWIND &#124; NOREWIND</span></span>|<span data-ttu-id="25fee-330">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-330">&#x2713;</span></span>|||  
|<span data-ttu-id="25fee-331">UNLOAD &#124; NOUNLOAD</span><span class="sxs-lookup"><span data-stu-id="25fee-331">UNLOAD &#124; NOUNLOAD</span></span>|<span data-ttu-id="25fee-332">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-332">&#x2713;</span></span>|||  
|<span data-ttu-id="25fee-333">KEEP_REPLICATION</span><span class="sxs-lookup"><span data-stu-id="25fee-333">KEEP_REPLICATION</span></span>|<span data-ttu-id="25fee-334">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-334">&#x2713;</span></span>|||  
|<span data-ttu-id="25fee-335">KEEP_CDC</span><span class="sxs-lookup"><span data-stu-id="25fee-335">KEEP_CDC</span></span>|<span data-ttu-id="25fee-336">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-336">&#x2713;</span></span>|||  
|<span data-ttu-id="25fee-337">ENABLE_BROKER &#124; ERROR_BROKER_CONVERSATIONS &#124; NEW_BROKER</span><span class="sxs-lookup"><span data-stu-id="25fee-337">ENABLE_BROKER &#124; ERROR_BROKER_CONVERSATIONS &#124; NEW_BROKER</span></span>|<span data-ttu-id="25fee-338">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-338">&#x2713;</span></span>|||  
|<span data-ttu-id="25fee-339">STOPAT &#124; STOPATMARK &#124; STOPBEFOREMARK</span><span class="sxs-lookup"><span data-stu-id="25fee-339">STOPAT &#124; STOPATMARK &#124; STOPBEFOREMARK</span></span>|<span data-ttu-id="25fee-340">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="25fee-340">&#x2713;</span></span>|||  
  
 <span data-ttu-id="25fee-341">Weitere Informationen zu RESTORE-Argumenten finden Sie unter [RESTORE-Argumente &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="25fee-341">For more information about Restore arguments, see [RESTORE Arguments &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql).</span></span>  
  
##  <a name="using-backup-task-in-sql-server-management-studio"></a><a name="BackupTaskSSMS"></a><span data-ttu-id="25fee-342">Verwenden des Sicherungs Tasks in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="25fee-342">Using Backup Task in SQL Server Management Studio</span></span>  
 <span data-ttu-id="25fee-343">Der Sicherungs Task in SQL Server Management Studio wurde verbessert, um URL als eine der Ziel Optionen und andere unterstützende Objekte einzuschließen, die für die Sicherung im Azure-Speicher wie die SQL-Anmelde Informationen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="25fee-343">The Backup task in SQL Server Management Studio has been enhanced to include URL as one of the destination options, and other supporting objects required to backup to Azure storage like the SQL Credential.</span></span>  
  
 <span data-ttu-id="25fee-344">In den folgenden Schritten werden die Änderungen beschrieben, die am Task Datenbank sichern vorgenommen wurden, um die Sicherung im Azure-Speicher zu ermöglichen:</span><span class="sxs-lookup"><span data-stu-id="25fee-344">The following steps describe the changes made to the Back Up Database task to allow for backing up to Azure storage.:</span></span>  
  
1.  <span data-ttu-id="25fee-345">Starten Sie SQL Server Management Studio, und stellen Sie eine Verbindung mit der SQL Server-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="25fee-345">Start SQL Server Management Studio and connect to the SQL Server instance.</span></span>  <span data-ttu-id="25fee-346">Wählen Sie eine Datenbank aus, die Sie sichern möchten, klicken Sie mit der rechten Maustaste auf **Tasks**, und wählen Sie **sichern aus.** Dadurch wird das Dialogfeld Datenbank sichern geöffnet.</span><span class="sxs-lookup"><span data-stu-id="25fee-346">Select a database you want to backup, and right click on **Tasks**, and select **Back Up..**. This opens the Back Up Database dialog box.</span></span>  
  
2.  <span data-ttu-id="25fee-347">Auf der Seite Allgemein wird die Option **URL** verwendet, um eine Sicherung im Azure-Speicher zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="25fee-347">On the general page the **URL** option is used to create a backup to Azure storage.</span></span> <span data-ttu-id="25fee-348">Wenn Sie diese Option auswählen, werden weitere Optionen auf dieser Seite aktiviert:</span><span class="sxs-lookup"><span data-stu-id="25fee-348">When you select this option, you see other options enabled on this page:</span></span>  
  
    1.  <span data-ttu-id="25fee-349">**Dateiname:** Name der Sicherungsdatei.</span><span class="sxs-lookup"><span data-stu-id="25fee-349">**File Name:** Name of the backup file.</span></span>  
  
    2.  <span data-ttu-id="25fee-350">**SQL-Anmeldeinformationen:** Sie können entweder vorhandene SQL Server-Anmeldeinformationen angeben oder neue erstellen, indem Sie neben dem Feld für die SQL-Anmeldeinformationen auf **Erstellen** klicken.</span><span class="sxs-lookup"><span data-stu-id="25fee-350">**SQL Credential:** You can either specify an existing SQL Server Credential, or can create a new one by clicking on the **Create** next to the SQL Credential box.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="25fee-351">Das Dialogfeld, das beim Klicken auf **Erstellen** geöffnet wird, erfordert ein Verwaltungszertifikat oder das Veröffentlichungsprofil für das Abonnement.</span><span class="sxs-lookup"><span data-stu-id="25fee-351">The dialog that opens when you click **Create** requires a management certificate or the publishing profile for the subscription.</span></span> <span data-ttu-id="25fee-352">SQL Server unterstützt derzeit die Version 2.0 des Veröffentlichungsprofils.</span><span class="sxs-lookup"><span data-stu-id="25fee-352">SQL Server currently supports publishing profile version 2.0.</span></span> <span data-ttu-id="25fee-353">Weitere Informationen zum Herunterladen der unterstützten Version des Veröffentlichungsprofils finden Sie unter [Herunterladen des Veröffentlichungsprofils 2.0](https://go.microsoft.com/fwlink/?LinkId=396421).</span><span class="sxs-lookup"><span data-stu-id="25fee-353">To download the supported version of the publishing profile, see [Download Publishing Profile 2.0](https://go.microsoft.com/fwlink/?LinkId=396421).</span></span>  
        >   
        >  <span data-ttu-id="25fee-354">Wenn Sie keinen Zugriff auf das Verwaltungszertifikat oder Veröffentlichungsprofil haben, können Sie SQL-Anmeldeinformationen erstellen, indem Sie den Namen des Speicherkontos und die Informationen zum Zugriffsschlüssel mithilfe von Transact-SQL oder SQL Server Management Studio angeben.</span><span class="sxs-lookup"><span data-stu-id="25fee-354">If you do not have access to the management certificate or publishing profile, you can create a SQL Credential by specifying the storage account name and access key information using Transact-SQL or SQL Server Management Studio.</span></span> <span data-ttu-id="25fee-355">Der Beispielcode im Abschnitt [Erstellen von Anmeldeinformationen](#credential) veranschaulicht das Erstellen von Anmeldeinformationen mithilfe von Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="25fee-355">See the sample code in the [Create a Credential](#credential) section to create a credential using Transact-SQL.</span></span> <span data-ttu-id="25fee-356">Alternativ können Sie auf der Datenbank-Engine-Instanz in SQL Server Management Studio mit der rechten Maustaste auf **Sicherheit**klicken und **Neu**sowie **Anmeldeinformationen**auswählen.</span><span class="sxs-lookup"><span data-stu-id="25fee-356">Alternatively, using SQL Server Management Studio, from the database engine instance, right click **Security**, select **New**, and select **Credential**.</span></span> <span data-ttu-id="25fee-357">Geben Sie im Feld **Identität** den Namen des Speicherkontos und im Feld **Kennwort** den Zugriffsschlüssel an.</span><span class="sxs-lookup"><span data-stu-id="25fee-357">Specify the storage account name for **Identity** and the access key in the **Password** field.</span></span>  
  
    3.  <span data-ttu-id="25fee-358">**Azure-Speicher Container:** Der Name des Azure-Speicher Containers, in dem die Sicherungsdateien gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="25fee-358">**Azure storage container:** The name of the Azure storage container to store the backup files.</span></span>  
  
    4.  <span data-ttu-id="25fee-359">**URL-Präfix:** Dieses wird automatisch mit den Informationen erstellt, die in den Feldern angegeben werden, die in den vorherigen Schritten beschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="25fee-359">**URL prefix:** This is built automatically using the information specified in the fields described in the previous steps.</span></span> <span data-ttu-id="25fee-360">Wenn Sie diesen Wert manuell bearbeiten, stellen Sie sicher, dass er mit den anderen Informationen übereinstimmt, die Sie zuvor bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="25fee-360">If you do edit this value manually, make sure it matches with the other information you provided previously.</span></span> <span data-ttu-id="25fee-361">Wenn Sie beispielsweise die Speicher-URL ändern, sollten Sie sicherstellen, dass die SQL-Anmeldeinformationen für die Authentifizierung beim gleichen Speicherkonto festgelegt wurden.</span><span class="sxs-lookup"><span data-stu-id="25fee-361">For example if you modify the storage URL, make sure the SQL Credential is set to authenticate to the same storage account.</span></span>  
  
 <span data-ttu-id="25fee-362">Wenn Sie eine URL als Ziel auswählen, sind bestimmte Optionen auf der Seite **Medienoptionen** deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="25fee-362">When you select URL as the destination, certain options in the **Media Options** page are disabled.</span></span>  <span data-ttu-id="25fee-363">Die folgenden Themen enthalten weitere Informationen zum Dialogfeld Datenbank sichern:</span><span class="sxs-lookup"><span data-stu-id="25fee-363">The following topics have more information on the Back Up Database dialog:</span></span>  
  
 [<span data-ttu-id="25fee-364">Datenbank sichern &#40;Seite Allgemein&#41;</span><span class="sxs-lookup"><span data-stu-id="25fee-364">Back Up Database &#40;General Page&#41;</span></span>](../../integration-services/general-page-of-integration-services-designers-options.md)  
  
 [<span data-ttu-id="25fee-365">Datenbank sichern &#40;Seite 'Medienoptionen'&#41;</span><span class="sxs-lookup"><span data-stu-id="25fee-365">Back Up Database &#40;Media Options Page&#41;</span></span>](back-up-database-media-options-page.md)  
  
 [<span data-ttu-id="25fee-366">Datenbank sichern &#40;Seite 'Sicherungsoptionen'&#41;</span><span class="sxs-lookup"><span data-stu-id="25fee-366">Back Up Database &#40;Backup Options Page&#41;</span></span>](back-up-database-backup-options-page.md)  
  
 [<span data-ttu-id="25fee-367">Erstellen von Anmeldeinformationen – Authentifizieren beim Azure-Speicher</span><span class="sxs-lookup"><span data-stu-id="25fee-367">Create Credential - Authenticate to Azure Storage</span></span>](create-credential-authenticate-to-azure-storage.md)  
  
##  <a name="sql-server-backup-to-url-using-maintenance-plan-wizard"></a><a name="MaintenanceWiz"></a><span data-ttu-id="25fee-368">SQL Server URL-Sicherung mithilfe des Wartungsplanungs-Assistenten</span><span class="sxs-lookup"><span data-stu-id="25fee-368">SQL Server Backup to URL Using Maintenance Plan Wizard</span></span>  
 <span data-ttu-id="25fee-369">Ähnlich wie beim zuvor beschriebenen Sicherungs Task wurde der Wartungsplanungs-Assistent in SQL Server Management Studio erweitert, um die **URL** als eine der Ziel Optionen und andere unterstützende Objekte einzuschließen, die für die Sicherung im Azure-Speicher wie die SQL-Anmelde Informationen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="25fee-369">Similar to the backup task described previously, the Maintenance Plan Wizard in SQL Server Management Studio has been enhanced to include **URL** as one of the destination options, and other supporting objects required to backup to Azure storage like the SQL Credential.</span></span> <span data-ttu-id="25fee-370">Weitere Informationen finden Sie unter der **Definieren von Sicherungstasks** im Abschnitt [Using Maintenance Plan Wizard](../maintenance-plans/use-the-maintenance-plan-wizard.md#SSMSProcedure).</span><span class="sxs-lookup"><span data-stu-id="25fee-370">For more information, see  the **Define Backup Tasks** section in [Using Maintenance Plan Wizard](../maintenance-plans/use-the-maintenance-plan-wizard.md#SSMSProcedure).</span></span>  
  
##  <a name="restoring-from-azure-storage-using-sql-server-management-studio"></a><a name="RestoreSSMS"></a><span data-ttu-id="25fee-371">Wiederherstellen aus Azure Storage mithilfe von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="25fee-371">Restoring from Azure storage Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="25fee-372">Wenn Sie eine Datenbank wiederherstellen, wird **URL** als Gerät für die Wiederherstellung eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="25fee-372">If you are restoring a database, **URL** is included as the device to restore from.</span></span> <span data-ttu-id="25fee-373">Die folgenden Schritte beschreiben die Änderungen am Wiederherstellungs Task, um die Wiederherstellung aus Azure Storage zuzulassen:</span><span class="sxs-lookup"><span data-stu-id="25fee-373">Following steps describe the changes in the Restore task to allow restoring from Azure storage:</span></span>  
  
1.  <span data-ttu-id="25fee-374">Wenn Sie in SQL Server Management Studio auf der Seite **Allgemein** des Wiederherstellungstasks die Option **Geräte** auswählen, wird das Dialogfeld **Sicherungsmedien auswählen** geöffnet, das **URL** als Sicherungsmediumtyp enthält.</span><span class="sxs-lookup"><span data-stu-id="25fee-374">When you select **Devices** in the **General** page of the Restore task in SQL Server Management Studio, this takes you to the **Select backup devices** dialog box which includes **URL** as a backup media type.</span></span>  
  
2.  <span data-ttu-id="25fee-375">Wenn Sie **URL** auswählen und auf **Hinzufügen**klicken, wird das Dialogfeld **Mit Azure-Speicher verbinden** geöffnet.</span><span class="sxs-lookup"><span data-stu-id="25fee-375">When you select **URL** and click **Add**, this opens the **Connect to Azure storage** dialog.</span></span> <span data-ttu-id="25fee-376">Geben Sie die SQL-Anmelde Informationen für die Authentifizierung beim Azure-Speicher an.</span><span class="sxs-lookup"><span data-stu-id="25fee-376">Specify the SQL Credential information to authenticate to Azure storage.</span></span>  
  
3.  <span data-ttu-id="25fee-377">SQL Server dann mithilfe der angegebenen SQL-Anmelde Informationen eine Verbindung mit dem Azure-Speicher her und öffnet das Dialogfeld **Sicherungsdatei in Azure suchen** .</span><span class="sxs-lookup"><span data-stu-id="25fee-377">SQL Server then connects to Azure storage using the SQL Credential information you provided and opens the **Locate Backup File in Azure** dialog.</span></span> <span data-ttu-id="25fee-378">Die Sicherungsdateien, die sich im Arbeitsspeicher befinden, werden auf dieser Seite angezeigt.</span><span class="sxs-lookup"><span data-stu-id="25fee-378">The backup files residing in the storage are displayed on this page.</span></span> <span data-ttu-id="25fee-379">Wählen Sie die Datei aus, die Sie zum Wiederherstellen verwenden möchten, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="25fee-379">Select the file you want to use to restore and click **OK**.</span></span> <span data-ttu-id="25fee-380">Dadurch gelangen Sie zurück zum Dialogfeld **Sicherungsmedien auswählen** . Wenn Sie in diesem Dialogfeld auf **OK** klicken, wird das Haupt Dialogfeld wieder **herstellen** angezeigt, in dem Sie die Wiederherstellung durchführen können.</span><span class="sxs-lookup"><span data-stu-id="25fee-380">This takes you back to the **Select Backup Devices** dialog, and Clicking **OK** on this dialog takes you back to the main **Restore** dialog where you will be able complete the restore.</span></span>  <span data-ttu-id="25fee-381">Weitere Informationen finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="25fee-381">For more information see, the following topics:</span></span>  
  
     [<span data-ttu-id="25fee-382">Datenbank wiederherstellen &#40;Seite „Allgemein“&#41;</span><span class="sxs-lookup"><span data-stu-id="25fee-382">Restore Database &#40;General Page&#41;</span></span>](restore-database-general-page.md)  
  
     [<span data-ttu-id="25fee-383">Datenbank wiederherstellen &#40;Seite Dateien&#41;</span><span class="sxs-lookup"><span data-stu-id="25fee-383">Restore Database &#40;Files Page&#41;</span></span>](restore-database-files-page.md)  
  
     [<span data-ttu-id="25fee-384">Datenbank wiederherstellen &#40;Seite Optionen&#41;</span><span class="sxs-lookup"><span data-stu-id="25fee-384">Restore Database &#40;Options Page&#41;</span></span>](restore-database-options-page.md)  
  
##  <a name="code-examples"></a><a name="Examples"></a> <span data-ttu-id="25fee-385">Codebeispiele</span><span class="sxs-lookup"><span data-stu-id="25fee-385">Code Examples</span></span>  
 <span data-ttu-id="25fee-386">Dieser Abschnitt enthält die folgenden Beispiele.</span><span class="sxs-lookup"><span data-stu-id="25fee-386">This section contains the following examples.</span></span>  
  
-   [<span data-ttu-id="25fee-387">Erstellen von Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="25fee-387">Create a Credential</span></span>](#credential)  
  
-   [<span data-ttu-id="25fee-388">Sichern einer vollständigen Datenbank</span><span class="sxs-lookup"><span data-stu-id="25fee-388">Backing up a complete database</span></span>](#complete)  
  
-   [<span data-ttu-id="25fee-389">Sichern der Datenbank und des Protokolls</span><span class="sxs-lookup"><span data-stu-id="25fee-389">Backing up the database and log</span></span>](#databaselog)  
  
-   [<span data-ttu-id="25fee-390">Erstellen einer vollständigen Dateisicherung der primären Dateigruppe</span><span class="sxs-lookup"><span data-stu-id="25fee-390">Creating a full file backup of the primary filegroup</span></span>](#filebackup)  
  
-   [<span data-ttu-id="25fee-391">Erstellen einer differenziellen Dateisicherung der primären Dateigruppen</span><span class="sxs-lookup"><span data-stu-id="25fee-391">Creating a differential file backup of the primary filegroups</span></span>](#differential)  
  
-   [<span data-ttu-id="25fee-392">Wiederherstellen einer Datenbank und Verschieben von Dateien</span><span class="sxs-lookup"><span data-stu-id="25fee-392">Restoring a database and move files</span></span>](#restoredbwithmove)  
  
-   [<span data-ttu-id="25fee-393">Wiederherstellen eines bestimmten Zeitpunkts mithilfe von STOPAT</span><span class="sxs-lookup"><span data-stu-id="25fee-393">Restoring to a point-in-time using STOPAT</span></span>](#PITR)  
  
###  <a name="create-a-credential"></a><a name="credential"></a> <span data-ttu-id="25fee-394">Erstellen von Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="25fee-394">Create a Credential</span></span>  
 <span data-ttu-id="25fee-395">Im folgenden Beispiel werden Anmelde Informationen erstellt, in denen die Azure Storage Authentifizierungsinformationen gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="25fee-395">The following example creates a credential that stores the Azure Storage authentication information.</span></span>  

   ```sql
   IF NOT EXISTS  
   (SELECT * FROM sys.credentials   
   WHERE credential_identity = 'mycredential')  
   CREATE CREDENTIAL mycredential WITH IDENTITY = 'mystorageaccount'  
   ,SECRET = '<storage access key>' ;  
   ```
  
   ```csharp
   // Connect to default sql server instance on local machine  
   Server server = new Server(".");  
   string identity = "mystorageaccount";  
   string secret = "<storage access key>";  
  
   // Create a Credential  
   string credentialName = "mycredential";  
   Credential credential = new Credential(server, credentialName);  
   credential.Create(identity, secret);  
   ```  
  
   ```powershell
   # create variables  
   $storageAccount = "mystorageaccount"  
   $storageKey = "<storage access key>"  
   $secureString = ConvertTo-SecureString $storageKey  -asplaintext -force  
   $credentialName = "mycredential"  
  
   $srvPath = "SQLSERVER:\SQL\COMPUTERNAME\INSTANCENAME"  
   # for default instance, the $srvpath variable would be "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
  
   # Create a credential  
   New-SqlCredential -Name $credentialName -Path $srvpath -Identity $storageAccount -Secret $secureString
   ```  
  
###  <a name="backing-up-a-complete-database"></a><a name="complete"></a><span data-ttu-id="25fee-396">Sichern einer kompletten Datenbank</span><span class="sxs-lookup"><span data-stu-id="25fee-396">Backing up a complete database</span></span>  
 <span data-ttu-id="25fee-397">Im folgenden Beispiel wird die AdventureWorks2012-Datenbank im Azure-BLOB-Speicherdienst gesichert.</span><span class="sxs-lookup"><span data-stu-id="25fee-397">The following example backs up the AdventureWorks2012 database to the Azure Blob storage service.</span></span>
  
   ```sql
   BACKUP DATABASE AdventureWorks2012   
   TO URL = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012.bak'   
         WITH CREDENTIAL = 'mycredential'   
         ,COMPRESSION  
         ,STATS = 5;  
   GO
   ```  
  
   ```csharp
   // Connect to default sql server instance on local machine  
   Server server = new Server(".");  
   string identity = "mystorageaccount";  
  
   string credentialName = "mycredential";  
   string dbName = "AdventureWorks2012";  
   string blobContainerName = "mycontainer";  
  
   // Generate Unique Url  
   string url = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}-{3}.bak",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup to Url  
   Backup backup = new Backup();  
   backup.CredentialName = credentialName;  
   backup.Database = dbName;  
   backup.CompressionOption = BackupCompressionOptions.On;  
   backup.Devices.AddDevice(url, DeviceType.Url);  
   backup.SqlBackup(server);  
   ```
  
   ```powershell
   # create variables  
   $backupUrlContainer = "https://mystorageaccount.blob.core.windows.net/mycontainer/"  
   $credentialName = "mycredential"  
   $srvPath = "SQLSERVER:\SQL\COMPUTERNAME\INSTANCENAME"   
   # for default instance, the $srvpath varilable would be "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
  
   # navigate to SQL Server Instance  
   CD $srvPath   
   $backupFile = $backupUrlContainer + "AdventureWorks2012" +  ".bak"  
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupFile  -SqlCredential $credentialName -CompressionOption On
   ```  
  
###  <a name="backing-up-the-database-and-log"></a><a name="databaselog"></a><span data-ttu-id="25fee-398">Sichern der Datenbank und des Protokolls</span><span class="sxs-lookup"><span data-stu-id="25fee-398">Backing up the database and log</span></span>  
 <span data-ttu-id="25fee-399">Im folgenden Beispiel wird die AdventureWorks2012-Beispieldatenbank gesichert, in der standardmäßig das einfache Wiederherstellungsmodell verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="25fee-399">The following example backups up the AdventureWorks2012 sample database, which uses the simple recovery model by default.</span></span> <span data-ttu-id="25fee-400">Zur Unterstützung von Protokollsicherungen wird die AdventureWorks2012-Datenbank geändert, sodass sie das vollständige Wiederherstellungsmodell verwendet.</span><span class="sxs-lookup"><span data-stu-id="25fee-400">To support log backups, the AdventureWorks2012 database is modified to use the full recovery model.</span></span> <span data-ttu-id="25fee-401">Im Beispiel wird dann eine vollständige Datenbanksicherung im Azure-Blob erstellt, und nach einem Zeitraum der Update Aktivität wird das Protokoll gesichert.</span><span class="sxs-lookup"><span data-stu-id="25fee-401">The example then creates a full database backup to Azure Blob, and after a period of update activity, backs up the log.</span></span> <span data-ttu-id="25fee-402">In diesem Beispiel wird für eine Sicherungsdatei ein Name mit einem Datums-/Zeitstempel erstellt.</span><span class="sxs-lookup"><span data-stu-id="25fee-402">This example creates a backup file name with a datetime stamp.</span></span>  
  
   ```sql
   -- To permit log backups, before the full database backup, modify the database   
   -- to use the full recovery model.  
   USE master;  
   GO  
   ALTER DATABASE AdventureWorks2012  
      SET RECOVERY FULL;  
   GO  
  
   -- Back up the full AdventureWorks2012 database.  
          -- First create a file name for the backup file with DateTime stamp  
  
   DECLARE @Full_Filename AS VARCHAR (300);  
   SET @Full_Filename = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012_Full_'+   
   REPLACE (REPLACE (REPLACE (CONVERT (VARCHAR (40), GETDATE (), 120), '-','_'),':', '_'),' ', '_') + '.bak';   
   --Back up Adventureworks2012 database  
  
   BACKUP DATABASE AdventureWorks2012  
   TO URL =  @Full_Filename  
   WITH CREDENTIAL = 'mycredential';  
   ,COMPRESSION  
   GO  
   -- Back up the AdventureWorks2012 log.  
   DECLARE @Log_Filename AS VARCHAR (300);  
   SET @Log_Filename = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012_Log_'+   
   REPLACE (REPLACE (REPLACE (CONVERT (VARCHAR (40), GETDATE (), 120), '-','_'),':', '_'),' ', '_') + '.trn';  
   BACKUP LOG AdventureWorks2012  
    TO URL = @Log_Filename  
    WITH CREDENTIAL = 'mycredential'  
    ,COMPRESSION;  
   GO  
   ```
  
   ```csharp
   // Connect to default sql server instance on local machine  
   Server server = new Server(".");  
   string identity = "mystorageaccount";  
  
   string credentialName = "mycredential";  
   string dbName = "AdventureWorks2012";  
   string blobContainerName = "mycontainer";  
  
   // Generate Unique Url for data backup  
   string urlDataBackup = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}_Data-{3}.bak",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup Database to Url  
   Backup backupData = new Backup();  
   backupData.CredentialName = credentialName;  
   backupData.Database = dbName;  
   backup.CompressionOption = BackupCompressionOptions.On;  
   backupData.Devices.AddDevice(urlDataBackup, DeviceType.Url);  
   backupData.SqlBackup(server);  
  
   // Generate Unique Url for data backup  
   string urlLogBackup = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}_Log-{3}.bak",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup Database Log to Url  
   Backup backupLog = new Backup();  
   backupLog.CredentialName = credentialName;  
   backupLog.Database = dbName;  
   backup.CompressionOption = BackupCompressionOptions.On;  
   backupLog.Devices.AddDevice(urlLogBackup, DeviceType.Url);  
   backupLog.Action = BackupActionType.Log;  
   backupLog.SqlBackup(server);  
   ```  

   ```powershell
   #create variables  
   $backupUrlContainer = "https://mystorageaccount.blob.core.windows.net/mycontainer/"  
   $credentialName = "mycredential"  
   $srvPath = "SQLSERVER:\SQL\COMPUTERNAME\INSTANCENAME"  
   # for default instance, the $srvpath variable would be "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
  
   # navigate to theSQL Server Instance
   CD $srvPath   
   #Create a unique file name for the full database backup  
   $backupFile = $backupUrlContainer + "AdventureWorks2012_" + (Get-Date).ToString("s").Replace("-","_").Replace(":", "_").Replace(" ","_").Replace("/", "_") +  ".bak"  
  
   #Backup Database to URL
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupFile  -SqlCredential $credentialName -CompressionOption On -BackupAction Database    
  
   #Create a unique file name for log backup  
  
   $backupFile = $backupUrlContainer + "AdventureWorks2012_" + (Get-Date).ToString("s").Replace("-","_").Replace(":", "_").Replace(" ","_").Replace("/", "_") +  ".trn"  
  
   #Backup Log to URL
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupFile  -SqlCredential $credentialName -CompressionOption On -BackupAction Log
   ```  
  
###  <a name="creating-a-full-file-backup-of-the-primary-filegroup"></a><a name="filebackup"></a><span data-ttu-id="25fee-403">Erstellen einer vollständigen Datei Sicherung der primären Datei Gruppe</span><span class="sxs-lookup"><span data-stu-id="25fee-403">Creating a full file backup of the primary filegroup</span></span>  
 <span data-ttu-id="25fee-404">Im folgenden Beispiel wird eine vollständige Dateisicherung der primären Dateigruppe erstellt.</span><span class="sxs-lookup"><span data-stu-id="25fee-404">The following example creates a full file backup of the primary filegroup.</span></span>
  
   ```sql
   --Back up the files in Primary:  
   BACKUP DATABASE AdventureWorks2012  
       FILEGROUP = 'Primary'  
       TO URL = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012files.bck'  
       WITH CREDENTIAL = 'mycredential'  
       ,COMPRESSION;  
   GO  
   ```
  
   ```csharp
   // Connect to default sql server instance on local machine  
   Server server = new Server(".");  
   string identity = "mystorageaccount";  
  
   string credentialName = "mycredential";  
   string dbName = "AdventureWorks2012";  
   string blobContainerName = "mycontainer";  
  
   // Generate Unique Url  
   string url = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}-{3}.bck",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup to Url  
   Backup backup = new Backup();  
   backup.CredentialName = credentialName;  
   backup.Database = dbName;  
   backup.Action = BackupActionType.Files;  
   backup.DatabaseFileGroups.Add("PRIMARY");  
   backup.CompressionOption = BackupCompressionOptions.On;  
   backup.Devices.AddDevice(url, DeviceType.Url);  
   backup.SqlBackup(server);
   ```
  
   ```powershell
   #create variables  
   $backupUrlContainer = "https://mystorageaccount.blob.core.windows.net/mycontainer/"  
   $credentialName = "mycredential"  
   $srvPath = "SQLSERVER:\SQL\COMPUTERNAME\INSTANCENAME"  
   # for default instance, the $srvpath variable would be "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
  
   # navigate to the SQL Server Instance  
  
   CD $srvPath   
   #Create a unique file name for the file backup  
   $backupFile = $backupUrlContainer + "AdventureWorks2012_" + (Get-Date).ToString("s").Replace("-","_").Replace(":", "_").Replace(" ","_").Replace("/", "_") +  ".bck"  
  
   #Backup Primary File Group to URL  
  
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupFile  -SqlCredential $credentialName -CompressionOption On -BackupAction Files -DatabaseFileGroup Primary
   ```  
  
###  <a name="creating-a-differential-file-backup-of-the-primary-filegroup"></a><a name="differential"></a><span data-ttu-id="25fee-405">Erstellen einer differenziellen Datei Sicherung der primären Datei Gruppe</span><span class="sxs-lookup"><span data-stu-id="25fee-405">Creating a differential file backup of the primary filegroup</span></span>  
 <span data-ttu-id="25fee-406">Im folgenden Beispiel wird eine differenzielle Dateisicherung der primären Dateigruppe erstellt.</span><span class="sxs-lookup"><span data-stu-id="25fee-406">The following example creates a differential file backup of the primary filegroup.</span></span>  
  
   ```sql
   --Back up the files in Primary:  
   BACKUP DATABASE AdventureWorks2012  
       FILEGROUP = 'Primary'  
       TO URL = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012filesdiff.bck'  
       WITH   
          CREDENTIAL = 'mycredential'  
          ,COMPRESSION  
      ,DIFFERENTIAL;  
   GO
   ```
  
   ```csharp
   // Connect to default sql server instance on local machine  
   Server server = new Server(".");  
   string identity = "mystorageaccount";  
  
   string credentialName = "mycredential";  
   string dbName = "AdventureWorks2012";  
   string blobContainerName = "mycontainer";  
  
   // Generate Unique Url  
   string url = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}-{3}.bak",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup to Url  
   Backup backup = new Backup();  
   backup.CredentialName = credentialName;  
   backup.Database = dbName;  
   backup.Action = BackupActionType.Files;  
   backup.DatabaseFileGroups.Add("PRIMARY");  
   backup.Incremental = true;  
   backup.CompressionOption = BackupCompressionOptions.On;  
   backup.Devices.AddDevice(url, DeviceType.Url);  
   backup.SqlBackup(server); 
   ```

   ```powershell
   #create variables  
   $backupUrlContainer = "https://mystorageaccount.blob.core.windows.net/mycontainer/"  
   $credentialName = "mycredential"  
   $srvPath = "SQLSERVER:\SQL\COMUTERNAME\INSTANCENAME"  
   # for default instance, the $srvpath variable would be "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
  
   # navigate to SQL Server Instance
   CD $srvPath   
  
   #create a unique file name for the full backup  
   $backupdbFile = $backupUrlContainer + "AdventureWorks2012_" + (Get-Date).ToString("s").Replace("-","_").Replace(":", "_").Replace(" ","_").Replace("/", "_") +  ".bak"  
  
   #Create a differential backup of the primary filegroup
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupFile  -SqlCredential $credentialName -CompressionOption On -BackupAction Files -DatabaseFileGroup Primary -Incremental
   ```  
  
###  <a name="restore-a-database-and-move-files"></a><a name="restoredbwithmove"></a><span data-ttu-id="25fee-407">Wiederherstellen einer Datenbank und Verschieben von Dateien</span><span class="sxs-lookup"><span data-stu-id="25fee-407">Restore a database and move files</span></span>  
 <span data-ttu-id="25fee-408">Zum Wiederherstellen einer vollständigen Datenbanksicherung und Verschieben der wiederhergestellten Datenbank in das Verzeichnis C:\Programme\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Data führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="25fee-408">To restore a full database backup and move the restored database to C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Data directory, use the following steps.</span></span>
  
   ```sql
   -- Backup the tail of the log first
   DECLARE @Log_Filename AS VARCHAR (300);  
   SET @Log_Filename = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012_Log_'+   
   REPLACE (REPLACE (REPLACE (CONVERT (VARCHAR (40), GETDATE (), 120), '-','_'),':', '_'),' ', '_') + '.trn';  
   BACKUP LOG AdventureWorks2012  
    TO URL = @Log_Filename  
    WITH CREDENTIAL = 'mycredential'  
    ,NORECOVERY;  
   GO  
  
   RESTORE DATABASE AdventureWorks2012 FROM URL = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012.bak'  
   WITH CREDENTIAL = 'mycredential'  
    ,MOVE 'AdventureWorks2012_data' to 'C:\Program Files\Microsoft SQL Server\myinstance\MSSQL\DATA\AdventureWorks2012.mdf'  
    ,MOVE 'AdventureWorks2012_log' to 'C:\Program Files\Microsoft SQL Server\myinstance\MSSQL\DATA\AdventureWorks2012.ldf'  
    ,STATS = 5
   ```
  
   ```csharp
   // Connect to default sql server instance on local machine  
   Server server = new Server(".");  
   string identity = "mystorageaccount";  
  
   string credentialName = "mycredential";  
   string dbName = "AdventureWorks2012";  
   string blobContainerName = "mycontainer";  
  
   // Generate Unique Url  
   string urlBackupData = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}-Data{3}.bak",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup to Url  
   Backup backup = new Backup();  
   backup.CredentialName = credentialName;  
   backup.Database = dbName;  
   backup.Devices.AddDevice(urlBackupData, DeviceType.Url);  
   backup.SqlBackup(server);  
  
   // Generate Unique Url for tail log backup  
   string urlTailLogBackup = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}-TailLog{3}.bak",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup Tail Log to Url  
   Backup backupTailLog = new Backup();  
   backupTailLog.CredentialName = credentialName;  
   backupTailLog.Database = dbName;  
   backupTailLog.Action = BackupActionType.Log;  
   backupTailLog.NoRecovery = true;  
   backupTailLog.Devices.AddDevice(urlTailLogBackup, DeviceType.Url);  
   backupTailLog.SqlBackup(server);  
  
   // Restore a database and move files  
   string newDataFilePath = server.MasterDBLogPath  + @"\" + dbName + DateTime.Now.ToString("s").Replace(":", "-") + ".mdf";  
   string newLogFilePath = server.MasterDBLogPath  + @"\" + dbName + DateTime.Now.ToString("s").Replace(":", "-") + ".ldf";  
  
   Restore restore = new Restore();  
   restore.CredentialName = credentialName;  
   restore.Database = dbName;  
   restore.ReplaceDatabase = true;  
   restore.Devices.AddDevice(urlBackupData, DeviceType.Url);  
   restore.RelocateFiles.Add(new RelocateFile(dbName, newDataFilePath));  
   restore.RelocateFiles.Add(new RelocateFile(dbName+ "_Log", newLogFilePath));  
   restore.SqlRestore(server);
   ```  

   ```powershell
   #create variables  
   $backupUrlContainer = "https://mystorageaccount.blob.core.windows.net/mycontainer/"  
   $credentialName = "mycredential"  
   $srvPath = "SQLSERVER:\SQL\COMPUTERNAME\INSTNACENAME"  
   # for default instance, the $srvpath variable would be "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
  
   # navigate to SQL Server Instance
   CD $srvPath   
  
   #create a unique file name for the full backup  
   $backupdbFile = $backupUrlContainer + "AdventureWorks2012_" + (Get-Date).ToString("s").Replace("-","_").Replace(":", "_").Replace(" ","_").Replace("/", "_") +  ".bak"  
  
   # Full database backup to URL  
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupdbFile  -SqlCredential $credentialName -CompressionOption On      
  
   #Create a unique file name for the tail log backup  
   $backuplogFile = $backupUrlContainer + "AdventureWorks2012_" + (Get-Date).ToString("s").Replace("-","_").Replace(":", "_").Replace(" ","_").Replace("/", "_") +  ".trn"  
  
   #Backup tail log to URL
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupFile  -SqlCredential $credentialName  -BackupAction Log -NoRecovery    
  
   # Restore Database and move files
   $newDataFilePath = New-Object Microsoft.SqlServer.Management.Smo.RelocateFile ("AdventureWorks_Data","C:\Program Files\Microsoft SQL Server\myinstance\MSSQL\DATA\AdventureWorks2012.mdf")  
   $newLogFilePath = New-Object Microsoft.SqlServer.Management.Smo.RelocateFile("AdventureWorks_Log","C:\Program Files\Microsoft SQL Server\myinstance\MSSQL\DATA\AdventureWorks2012.ldf")  
  
   Restore-SqlDatabase -Database AdventureWorks2012 -SqlCredential $credentialName -BackupFile $backupdbFile -RelocateFile @($newDataFilePath,$newLogFilePath)
   ```  
  
###  <a name="restoring-to-a-point-in-time-using-stopat"></a><a name="PITR"></a> <span data-ttu-id="25fee-409">Wiederherstellen eines bestimmten Zeitpunkts mithilfe von STOPAT</span><span class="sxs-lookup"><span data-stu-id="25fee-409">Restoring to a point-in-time using STOPAT</span></span>  
 <span data-ttu-id="25fee-410">Im folgenden Beispiel wird der Zustand einer Datenbank zu einem bestimmten Zeitpunkt wiederhergestellt und ein Wiederherstellungsvorgang veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="25fee-410">The following example restores a database to its state to a point in time, and shows a restore operation.</span></span>  
  
   ```sql
   RESTORE DATABASE AdventureWorks FROM URL = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012.bak'   
   WITH   
     CREDENTIAL = 'mycredential'  
    ,MOVE 'AdventureWorks2012_data' to 'C:\Program Files\Microsoft SQL Server\myinstance\MSSQL\DATA\AdventureWorks2012.mdf'  
    ,Move 'AdventureWorks2012_log' to 'C:\Program Files\Microsoft SQL Server\myinstance\MSSQL\DATA\AdventureWorks2012.ldf'  
    ,NORECOVERY  
    --,REPLACE  
    ,STATS = 5;  
   GO   
  
   RESTORE LOG AdventureWorks FROM URL = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012.trn'   
   WITH CREDENTIAL = 'mycredential'  
    ,RECOVERY   
    ,STOPAT = 'Oct 23, 2012 5:00 PM'   
   GO  
   ```  
  
   ```csharp
   // Connect to default sql server instance on local machine  
   Server server = new Server(".");  
   string identity = "mystorageaccount";  
  
   string credentialName = "mycredential";  
   string dbName = "AdventureWorks2012";  
   string blobContainerName = "mycontainer";  
  
   // Generate Unique Url  
   string urlBackupData = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}-Data{3}.bak",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup to Url  
   Backup backup = new Backup();  
   backup.CredentialName = credentialName;  
   backup.Database = dbName;  
   backup.Devices.AddDevice(urlBackupData, DeviceType.Url);  
   backup.SqlBackup(server);  
  
   // Generate Unique Url for Tail Log backup  
   string urlTailLogBackup = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}-TailLog{3}.bak",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup Tail Log to Url  
   Backup backupTailLog = new Backup();  
   backupTailLog.CredentialName = credentialName;  
   backupTailLog.Database = dbName;  
   backupTailLog.Action = BackupActionType.Log;  
   backupTailLog.NoRecovery = true;  
   backupTailLog.Devices.AddDevice(urlTailLogBackup, DeviceType.Url);  
   backupTailLog.SqlBackup(server);  
  
   // Restore a database and move files  
   string newDataFilePath = server.MasterDBLogPath + @"\" + dbName + DateTime.Now.ToString("s").Replace(":", "-") + ".mdf";  
   string newLogFilePath = server.MasterDBLogPath + @"\" + dbName + DateTime.Now.ToString("s").Replace(":", "-") + ".ldf";  
  
   Restore restore = new Restore();  
   restore.CredentialName = credentialName;  
   restore.Database = dbName;  
   restore.ReplaceDatabase = true;  
   restore.NoRecovery = true;  
   restore.Devices.AddDevice(urlBackupData, DeviceType.Url);  
   restore.RelocateFiles.Add(new RelocateFile(dbName, newDataFilePath));  
   restore.RelocateFiles.Add(new RelocateFile(dbName + "_Log", newLogFilePath));  
   restore.SqlRestore(server);  
      
   // Restore transaction Log with stop at   
   Restore restoreLog = new Restore();  
   restoreLog.CredentialName = credentialName;  
   restoreLog.Database = dbName;  
   restoreLog.Action = RestoreActionType.Log;  
   restoreLog.Devices.AddDevice(urlBackupData, DeviceType.Url);  
   restoreLog.ToPointInTime = DateTime.Now.ToString();   
   restoreLog.SqlRestore(server);
   ```
  
   ```powershell
   #create variables  
   $backupUrlContainer = "https://mystorageaccount.blob.core.windows.net/mycontainer/"  
   $credentialName = "mycredential"  
   $srvPath = "SQLSERVER:\SQL\COMPUTERNAME\INSTANCENAME"  
   # for default instance, the $srvpath variable would be "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
  
   # Navigate to SQL Server Instance Directory
   CD $srvPath   
  
   #create a unique file name for the full backup  
   $backupdbFile = $backupUrlContainer + "AdventureWorks2012_" + (Get-Date).ToString("s").Replace("-","_").Replace(":", "_").Replace(" ","_").Replace("/", "_") +  ".bak"  
  
   # Full database backup to URL  
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupdbFile  -SqlCredential $credentialName -CompressionOption On     
  
   #Create a unique file name for the tail log backup  
   $backuplogFile = $backupUrlContainer + "AdventureWorks2012_" + (Get-Date).ToString("s").Replace("-","_").Replace(":", "_").Replace(" ","_").Replace("/", "_") +  ".trn"  
  
   #Backup tail log to URL
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupFile  -SqlCredential $credentialName  -BackupAction Log -NoRecovery     
  
   # Restore Database and move files
   $newDataFilePath = New-Object Microsoft.SqlServer.Management.Smo.RelocateFile ("AdventureWorks_Data","C:\Program Files\Microsoft SQL Server\myinstance\MSSQL\DATA\AdventureWorks2012.mdf")  
   $newLogFilePath = New-Object Microsoft.SqlServer.Management.Smo.RelocateFile("AdventureWorks_Log","C:\Program Files\Microsoft SQL Server\myinstance\MSSQL\DATA\AdventureWorks2012.ldf")  
  
   Restore-SqlDatabase -Database AdventureWorks2012 -SqlCredential $credentialName -BackupFile $backupdbFile -RelocateFile @($newDataFilePath,$newLogFilePath) -NoRecovery    
  
   # Restore Transaction log with Stop At:  
   Restore-SqlDatabase -Database AdventureWorks2012 -SqlCredential $credentialName -BackupFile $backuplogFile  -ToPointInTime (Get-Date).ToString()
   ```  
  
## <a name="see-also"></a><span data-ttu-id="25fee-411">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="25fee-411">See Also</span></span>  
 <span data-ttu-id="25fee-412">[SQL Server-URL-Sicherung – bewährte Methoden und Problembehandlung](sql-server-backup-to-url-best-practices-and-troubleshooting.md) </span><span class="sxs-lookup"><span data-stu-id="25fee-412">[SQL Server Backup to URL Best Practices and Troubleshooting](sql-server-backup-to-url-best-practices-and-troubleshooting.md) </span></span>  
 [<span data-ttu-id="25fee-413">Sichern und Wiederherstellen von Systemdatenbanken &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="25fee-413">Back Up and Restore of System Databases &#40;SQL Server&#41;</span></span>](back-up-and-restore-of-system-databases-sql-server.md)   
