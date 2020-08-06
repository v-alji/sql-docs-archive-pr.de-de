---
title: Datenbank sichern (Seite „Sicherungsoptionen“) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.backupdatabase.options.f1
- swb.backupdatabase.options.f1
ms.assetid: df0ddcdb-c94e-472b-b786-469ae8117b93
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ffd527ba4334244c7fd4c5d4a73099093cb8520b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622733"
---
# <a name="back-up-database-backup-options-page"></a><span data-ttu-id="24389-102">Datenbank sichern (Seite 'Sicherungsoptionen')</span><span class="sxs-lookup"><span data-stu-id="24389-102">Back Up Database (Backup Options Page)</span></span>
  <span data-ttu-id="24389-103">Auf der Seite  **Sicherungsoptionen** des Dialogfelds **Datenbank sichern** können Sie die Optionen zur Sicherung der Datenbank anzeigen und ändern.</span><span class="sxs-lookup"><span data-stu-id="24389-103">Use the  **Backup Options** page of the **Back Up Database** dialog box to view or modify database backup options.</span></span>  
  
 <span data-ttu-id="24389-104">**So erstellen Sie eine Sicherung mithilfe von SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="24389-104">**To create a backup by using SQL Server Management Studio**</span></span>  
  
-   [<span data-ttu-id="24389-105">Erstellen einer vollständigen Datenbanksicherung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="24389-105">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="24389-106">Erstellen einer differenziellen Datenbanksicherung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="24389-106">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](create-a-differential-database-backup-sql-server.md)  
  
> [!IMPORTANT]  
>  <span data-ttu-id="24389-107">Sie können einen Datenbank-Wartungsplan definieren, um Datenbanksicherungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="24389-107">You can define a database maintenance plan to create database backups.</span></span> <span data-ttu-id="24389-108">Weitere Informationen finden Sie unter [Wartungspläne](../maintenance-plans/maintenance-plans.md) und [Verwenden des Wartungsplanungs-Assistenten](../maintenance-plans/use-the-maintenance-plan-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="24389-108">For more information, see [Maintenance Plans](../maintenance-plans/maintenance-plans.md) and [Use the Maintenance Plan Wizard](../maintenance-plans/use-the-maintenance-plan-wizard.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="24389-109">Wenn Sie eine Sicherungsaufgabe mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]angeben, können Sie das entsprechende [!INCLUDE[tsql](../../includes/tsql-md.md)][BACKUP](/sql/t-sql/statements/backup-transact-sql) -Skript generieren, indem Sie auf die Schaltfläche **Skript** klicken und anschließend ein Ziel für das Skript auswählen.</span><span class="sxs-lookup"><span data-stu-id="24389-109">When you specify a backup task by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you can generate the corresponding [!INCLUDE[tsql](../../includes/tsql-md.md)][BACKUP](/sql/t-sql/statements/backup-transact-sql) script by clicking the **Script** button and then selecting a destination for the script.</span></span>  
  
## <a name="options"></a><span data-ttu-id="24389-110">Tastatur</span><span class="sxs-lookup"><span data-stu-id="24389-110">Options</span></span>  
  
### <a name="backup-set"></a><span data-ttu-id="24389-111">Sicherungssatz</span><span class="sxs-lookup"><span data-stu-id="24389-111">Backup set</span></span>  
 <span data-ttu-id="24389-112">Mit den Optionen des Bereichs **Sicherungssatz** können Sie optionale Informationen zu dem durch den Sicherungsvorgang erstellten Sicherungssatz angeben.</span><span class="sxs-lookup"><span data-stu-id="24389-112">The options of the **Backup set** panel allow for you to specify optional information about the backup set created by the back up operation.</span></span>  
  
 <span data-ttu-id="24389-113">**Name**</span><span class="sxs-lookup"><span data-stu-id="24389-113">**Name**</span></span>  
 <span data-ttu-id="24389-114">Geben Sie den Namen des Sicherungssatzes an.</span><span class="sxs-lookup"><span data-stu-id="24389-114">Specify the backup set name.</span></span> <span data-ttu-id="24389-115">Vom System wird automatisch ein Standardname vorgeschlagen, der auf dem Datenbanknamen und dem Sicherungstyp basiert.</span><span class="sxs-lookup"><span data-stu-id="24389-115">The system automatically suggests a default name based on the database name and the backup type.</span></span>  
  
 <span data-ttu-id="24389-116">Informationen über Sicherungssätze finden Sie unter [Mediensätze, Medienfamilien und Sicherungssätze &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="24389-116">For information about backup sets, see [Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span></span>  
  
 <span data-ttu-id="24389-117">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="24389-117">**Description**</span></span>  
 <span data-ttu-id="24389-118">Geben Sie eine Beschreibung des Sicherungssatzes ein.</span><span class="sxs-lookup"><span data-stu-id="24389-118">Enter a description of the backup set.</span></span>  
  
 <span data-ttu-id="24389-119">**Sicherungssatz läuft ab**</span><span class="sxs-lookup"><span data-stu-id="24389-119">**Backup set will expire**</span></span>  
 <span data-ttu-id="24389-120">Wählen Sie eine der folgenden Optionen für den Ablauf.</span><span class="sxs-lookup"><span data-stu-id="24389-120">Choose one of the following expiration options.</span></span> <span data-ttu-id="24389-121">Diese Option ist deaktiviert, wenn **URL** als Sicherungsziel ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="24389-121">This option is disabled if **URL** is chosen as the backup destination.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="24389-122">**Nachher**</span><span class="sxs-lookup"><span data-stu-id="24389-122">**After**</span></span>|<span data-ttu-id="24389-123">Geben Sie die Anzahl von Tagen an, die verstreichen müssen, bevor dieser Sicherungssatz abläuft und überschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="24389-123">Specify the number of days that must elapse before this backup set expires and can be overwritten.</span></span> <span data-ttu-id="24389-124">Dieser Wert kann zwischen 0 und 99999 Tagen liegen. Ein Wert von 0 Tagen bedeutet, dass der Sicherungssatz nicht abläuft.</span><span class="sxs-lookup"><span data-stu-id="24389-124">This value can be from 0 to 99999 days; a value of 0 days means that the backup set will never expire.</span></span><br /><br /> <span data-ttu-id="24389-125">Der Standardwert für den Sicherungsablauf ist der Wert, der in der Option **Standardbeibehaltung für Sicherungsmedien (in Tagen)** festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="24389-125">The default value for backup expiration is the value set in the **Default backup media retention (in days)** option.</span></span> <span data-ttu-id="24389-126">Um auf diese Option zuzugreifen, klicken Sie im Objekt-Explorer mit der rechten Maustaste auf den Servernamen, und wählen Sie **Eigenschaften**aus. Klicken Sie dann im Dialogfeld **Servereigenschaften** auf die Seite **Datenbankeinstellungen** .</span><span class="sxs-lookup"><span data-stu-id="24389-126">To access this, right-click the server name in Object Explorer and select **Properties**; then click the **Database Settings** page of the **Server Properties** dialog box.</span></span>|  
|<span data-ttu-id="24389-127">**On**</span><span class="sxs-lookup"><span data-stu-id="24389-127">**On**</span></span>|<span data-ttu-id="24389-128">Geben Sie ein bestimmtes Datum an, an dem der Sicherungssatz abläuft und überschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="24389-128">Specify a specific date when the backup set expires and can be overwritten.</span></span>|  
  
### <a name="compression"></a><span data-ttu-id="24389-129">Komprimierung</span><span class="sxs-lookup"><span data-stu-id="24389-129">Compression</span></span>  
 [!INCLUDE[ssEnterpriseEd10](../../../includes/ssenterpriseed10-md.md)] <span data-ttu-id="24389-130">(oder höher) unterstützt die [Sicherungskomprimierung](backup-compression-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="24389-130">(or a later version) supports [backup compression](backup-compression-sql-server.md).</span></span>  
  
 <span data-ttu-id="24389-131">**Sicherungskomprimierung festlegen**</span><span class="sxs-lookup"><span data-stu-id="24389-131">**Set backup compression**</span></span>  
 <span data-ttu-id="24389-132">Wählen Sie in [!INCLUDE[ssEnterpriseEd10](../../../includes/ssenterpriseed10-md.md)] (oder höher) einen der folgenden Werte für die Sicherungskomprimierung aus:</span><span class="sxs-lookup"><span data-stu-id="24389-132">In [!INCLUDE[ssEnterpriseEd10](../../../includes/ssenterpriseed10-md.md)] (or a later version), select one of the following backup compression values:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="24389-133">**Standardservereinstellungen verwenden**</span><span class="sxs-lookup"><span data-stu-id="24389-133">**Use the default server setting**</span></span>|<span data-ttu-id="24389-134">Klicken Sie hier, um die Standardeinstellung auf Serverebene zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="24389-134">Click to use the server-level default.</span></span><br /><br /> <span data-ttu-id="24389-135">Diese Standardeinstellung wird durch die Serverkonfigurationsoption **Komprimierungsstandard für Sicherung** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="24389-135">This default is set by the **backup compression default** server-configuration option.</span></span> <span data-ttu-id="24389-136">Informationen zum Anzeigen der aktuellen Einstellung dieser Option finden Sie unter [Anzeigen oder Konfigurieren der Serverkonfigurationsoption „Standardeinstellung für die Sicherungskomprimierung“](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="24389-136">For information about how to view the current setting of this option, see [View or Configure the backup compression default Server Configuration Option](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md).</span></span>|  
|<span data-ttu-id="24389-137">**Sicherung komprimieren**</span><span class="sxs-lookup"><span data-stu-id="24389-137">**Compress backup**</span></span>|<span data-ttu-id="24389-138">Klicken Sie hier, um die Sicherung unabhängig von der Standardeinstellung auf Serverebene zu komprimieren.</span><span class="sxs-lookup"><span data-stu-id="24389-138">Click to compress the backup, regardless of the server-level default.</span></span><br /><br /> <span data-ttu-id="24389-139">**\*\* Wichtig \*\*** Standardmäßig steigt die CPU-Nutzung durch die Komprimierung erheblich, und die durch die Komprimierung zusätzlich genutzten CPU-Ressourcen können sich negativ auf gleichzeitige Vorgänge auswirken.</span><span class="sxs-lookup"><span data-stu-id="24389-139">**\*\* Important \*\*** By default, compression significantly increases CPU usage, and the additional CPU consumed by the compression process might adversely impact concurrent operations.</span></span> <span data-ttu-id="24389-140">Daher ist es u. U. sinnvoll, in einer Sitzung, bei der die CPU-Nutzung durch die [Ressourcenkontrolle](../resource-governor/resource-governor.md) eingeschränkt ist, komprimierte Sicherungen mit niedriger Priorität zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="24389-140">Therefore, you might want to create low-priority compressed backups in a session whose CPU usage is limited by [Resource Governor](../resource-governor/resource-governor.md).</span></span> <span data-ttu-id="24389-141">Weitere Informationen finden Sie unter [Einschränken der CPU-Nutzung durch die Sicherungskomprimierung mithilfe der Ressourcenkontrolle &#40;Transact-SQL&#41;](use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="24389-141">For more information, see [Use Resource Governor to Limit CPU Usage by Backup Compression &#40;Transact-SQL&#41;](use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md).</span></span>|  
|<span data-ttu-id="24389-142">**Sicherung nicht komprimieren**</span><span class="sxs-lookup"><span data-stu-id="24389-142">**Do not compress backup**</span></span>|<span data-ttu-id="24389-143">Klicken Sie hier, um unabhängig von der Standardeinstellung auf Serverebene eine nicht komprimierte Sicherung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="24389-143">Click to create an uncompressed backup, regardless of the server-level default.</span></span>|  
  
### <a name="encryption"></a><span data-ttu-id="24389-144">Verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="24389-144">Encryption</span></span>  
 <span data-ttu-id="24389-145">Um eine verschlüsselte Sicherung zu erstellen, aktivieren Sie das Kontrollkästchen **Sicherung verschlüsseln** .</span><span class="sxs-lookup"><span data-stu-id="24389-145">To create an encrypted backup, check the **Encrypt backup** check box.</span></span> <span data-ttu-id="24389-146">Wählen Sie einen Verschlüsselungsalgorithmus für den Verschlüsselungsschritt aus, und geben Sie ein Zertifikat oder einen asymmetrischen Schlüssel aus der Liste der vorhandenen Zertifikate und asymmetrischen Schlüssel an.</span><span class="sxs-lookup"><span data-stu-id="24389-146">Select an encryption algorithm to use for the encryption step, and provide a Certificate or Asymmetric key from a list of existing certificates or asymmetric keys.</span></span> <span data-ttu-id="24389-147">Folgende Algorithmen stehen für die Verschlüsselung zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="24389-147">The available algorithms for encryption are:</span></span>  
  
-   <span data-ttu-id="24389-148">AES 128</span><span class="sxs-lookup"><span data-stu-id="24389-148">AES 128</span></span>  
  
-   <span data-ttu-id="24389-149">AES 192</span><span class="sxs-lookup"><span data-stu-id="24389-149">AES 192</span></span>  
  
-   <span data-ttu-id="24389-150">AES 256</span><span class="sxs-lookup"><span data-stu-id="24389-150">AES 256</span></span>  
  
-   <span data-ttu-id="24389-151">Triple DES</span><span class="sxs-lookup"><span data-stu-id="24389-151">Triple DES</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="24389-152">Die Verschlüsselungsoption ist deaktiviert, wenn Sie ausgewählt haben, dass die Sicherung an einen vorhandenen Sicherungssatz angefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="24389-152">The encryption option is disabled if you selected to append to existing backup set.</span></span>  
>   
>  <span data-ttu-id="24389-153">Es ist ratsam, das Zertifikat bzw. die Schlüssel zu sichern und an einem anderen Speicherort als dem der verschlüsselten Sicherung zu speichern.</span><span class="sxs-lookup"><span data-stu-id="24389-153">It is recommended practice to back up your certificate or keys and store them in a different location than the backup you encrypted.</span></span>  
>   
>  <span data-ttu-id="24389-154">Es werden nur Schlüssel aus der erweiterbaren Schlüsselverwaltung (Extensible Key Management, EKM) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="24389-154">Only keys residing in the Extensible Key Management (EKM) are supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24389-155">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="24389-155">See Also</span></span>  
 <span data-ttu-id="24389-156">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="24389-156">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="24389-157">[Sichern eines Transaktionsprotokolls &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="24389-157">[Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span></span>  
 <span data-ttu-id="24389-158">[Sichern von Dateien und Dateigruppen &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="24389-158">[Back Up Files and Filegroups &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span></span>  
 [<span data-ttu-id="24389-159">Sichern des Transaktionsprotokolls bei beschädigter Datenbank &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="24389-159">Back Up the Transaction Log When the Database Is Damaged &#40;SQL Server&#41;</span></span>](back-up-the-transaction-log-when-the-database-is-damaged-sql-server.md)  
  
  
