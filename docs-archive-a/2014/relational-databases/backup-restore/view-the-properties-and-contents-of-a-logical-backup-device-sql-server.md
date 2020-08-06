---
title: Anzeigen der Eigenschaften und des Inhalts eines logischen Sicherungsmediums (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- displaying backup content
- viewing backup content
- database backups [SQL Server], viewing content
- backing up databases [SQL Server], viewing content
- backing up databases [SQL Server], properties
- displaying backup properties
- backup devices [SQL Server], viewing information
- viewing backup properties
- database backups [SQL Server], properties
ms.assetid: 3a309074-e816-454d-b6c3-fcfdde0cbf74
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f2bdf41e3dbda079e3627ff7a7c1c3c78103b728
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718283"
---
# <a name="view-the-properties-and-contents-of-a-logical-backup-device-sql-server"></a><span data-ttu-id="93bcc-102">Anzeigen der Eigenschaften und des Inhalts eines logischen Sicherungsmediums (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="93bcc-102">View the Properties and Contents of a Logical Backup Device (SQL Server)</span></span>
  <span data-ttu-id="93bcc-103">In diesem Thema wird beschrieben, wie Sie die Eigenschaften und Inhalte von logischen Sicherungsmedien in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="93bcc-103">This topic describes how to view the properties and contents of a logical backup device in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="93bcc-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="93bcc-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="93bcc-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="93bcc-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="93bcc-106">Security</span><span class="sxs-lookup"><span data-stu-id="93bcc-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="93bcc-107">**So zeigen Sie die Eigenschaften und den Inhalt eines logischen Sicherungsmediums an, und zwar mit**</span><span class="sxs-lookup"><span data-stu-id="93bcc-107">**To view the properties and contents of a logical backup device, using:**</span></span>  
  
     [<span data-ttu-id="93bcc-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="93bcc-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="93bcc-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="93bcc-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="93bcc-110">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="93bcc-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="93bcc-111">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="93bcc-111">Security</span></span>  
 <span data-ttu-id="93bcc-112">Weitere Informationen zur Sicherheit finden Sie unter [RESTORE LABELONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-labelonly-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="93bcc-112">For information about security, see [RESTORE LABELONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-labelonly-transact-sql).</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="93bcc-113">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="93bcc-113">Permissions</span></span>  
 <span data-ttu-id="93bcc-114">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] und höheren Versionen benötigen Sie die CREATE DATABASE-Berechtigung, um Informationen zu Sicherungssätzen oder Sicherungsmedien abzurufen.</span><span class="sxs-lookup"><span data-stu-id="93bcc-114">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later versions, obtaining information about a backup set or backup device requires CREATE DATABASE permission.</span></span> <span data-ttu-id="93bcc-115">Weitere Informationen finden Sie unter [GRANT (Datenbankberechtigungen) &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="93bcc-115">For more information, see [GRANT Database Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="93bcc-116">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="93bcc-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-properties-and-contents-of-a-logical-backup-device"></a><span data-ttu-id="93bcc-117">So zeigen Sie die Eigenschaften und den Inhalt eines logischen Sicherungsmediums an</span><span class="sxs-lookup"><span data-stu-id="93bcc-117">To view the properties and contents of a logical backup device</span></span>  
  
1.  <span data-ttu-id="93bcc-118">Klicken Sie nach dem Herstellen einer Verbindung mit der entsprechenden Instanz von [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] im Objekt-Explorer auf den Servernamen, um die Serverstruktur zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="93bcc-118">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="93bcc-119">Erweitern Sie **Serverobjekte**und anschließend **Sicherungsmedien**.</span><span class="sxs-lookup"><span data-stu-id="93bcc-119">Expand **Server Objects**, and expand **Backup Devices**.</span></span>  
  
3.  <span data-ttu-id="93bcc-120">Klicken Sie auf das Gerät, und klicken Sie mit der rechten Maustaste auf **Eigenschaften**. Hierdurch wird das Dialogfeld **Sicherungsmedium** geöffnet.</span><span class="sxs-lookup"><span data-stu-id="93bcc-120">Click the device and right-click **Properties**, which opens the **Backup Device** dialog box.</span></span>  
  
4.  <span data-ttu-id="93bcc-121">Auf der Seite **Allgemein** werden der Gerätename und das Ziel angezeigt (entweder ein Bandmedium oder ein Dateipfad).</span><span class="sxs-lookup"><span data-stu-id="93bcc-121">The **General** page displays the device name and destination, which is either a tape device or file path.</span></span>  
  
5.  <span data-ttu-id="93bcc-122">Klicken Sie im Bereich **Seite auswählen** auf **Medieninhalt**.</span><span class="sxs-lookup"><span data-stu-id="93bcc-122">In the **Select a Page** pane, click **Media Contents**.</span></span>  
  
6.  <span data-ttu-id="93bcc-123">Im rechten Vorschaufeld werden folgende Eigenschaftsbereiche angezeigt:</span><span class="sxs-lookup"><span data-stu-id="93bcc-123">The right-hand pane displays in the following properties panels:</span></span>  
  
    -   <span data-ttu-id="93bcc-124">**Medien**</span><span class="sxs-lookup"><span data-stu-id="93bcc-124">**Media**</span></span>  
  
         <span data-ttu-id="93bcc-125">Mediensequenzinformationen (die Mediensequenznummer, die Sequenznummer der Familie und ggf. der Spiegelungsbezeichner) und das Datum und die Uhrzeit der Medienerstellung.</span><span class="sxs-lookup"><span data-stu-id="93bcc-125">Media sequence information (the media sequence number, the family sequence number, and the mirror identifier, if any) and the media creation date and time.</span></span>  
  
    -   <span data-ttu-id="93bcc-126">**Mediensatz**</span><span class="sxs-lookup"><span data-stu-id="93bcc-126">**Media set**</span></span>  
  
         <span data-ttu-id="93bcc-127">Mediensatzinformationen: der Mediensatzname und ggf. die Beschreibung sowie die Anzahl der Familien im Mediensatz.</span><span class="sxs-lookup"><span data-stu-id="93bcc-127">Media set information: the media set name and description, if any, and the number of families in the media set.</span></span>  
  
7.  <span data-ttu-id="93bcc-128">Das Raster **Sicherungssätze** enthält Informationen zu den Inhalten des Mediensatzes.</span><span class="sxs-lookup"><span data-stu-id="93bcc-128">The **Backup sets** grid displays information about the contents of the media set.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="93bcc-129">Weitere Informationen finden Sie unter [Medieninhalt (Seite)](backup-device-media-contents-page.md).</span><span class="sxs-lookup"><span data-stu-id="93bcc-129">For more information, see [Media Contents Page](backup-device-media-contents-page.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="93bcc-130">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="93bcc-130">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-properties-and-contents-of-a-logical-backup-device"></a><span data-ttu-id="93bcc-131">So zeigen Sie die Eigenschaften und den Inhalt eines logischen Sicherungsmediums an</span><span class="sxs-lookup"><span data-stu-id="93bcc-131">To view the properties and contents of a logical backup device</span></span>  
  
1.  <span data-ttu-id="93bcc-132">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="93bcc-132">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="93bcc-133">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="93bcc-133">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="93bcc-134">Verwenden Sie die [RESTORE LABELONLY](/sql/t-sql/statements/restore-statements-labelonly-transact-sql) -Anweisung.</span><span class="sxs-lookup"><span data-stu-id="93bcc-134">Use the [RESTORE LABELONLY](/sql/t-sql/statements/restore-statements-labelonly-transact-sql) statement.</span></span> <span data-ttu-id="93bcc-135">In diesem Beispiel werden Informationen zum logischen Sicherungsmedium `AdvWrks2008R2Backup` zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="93bcc-135">This example returns information about the `AdvWrks2008R2Backup` logical backup device.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
RESTORE LABELONLY  
   FROM AdvWrks2008R2Backup ;  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="93bcc-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="93bcc-136">See Also</span></span>  
 <span data-ttu-id="93bcc-137">[backupfilegroup &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfilegroup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="93bcc-137">[backupfilegroup &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfilegroup-transact-sql) </span></span>  
 <span data-ttu-id="93bcc-138">[backupfile &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfile-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="93bcc-138">[backupfile &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfile-transact-sql) </span></span>  
 <span data-ttu-id="93bcc-139">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="93bcc-139">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span></span>  
 <span data-ttu-id="93bcc-140">[backupmediaset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediaset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="93bcc-140">[backupmediaset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediaset-transact-sql) </span></span>  
 <span data-ttu-id="93bcc-141">[backupmediafamily &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediafamily-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="93bcc-141">[backupmediafamily &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediafamily-transact-sql) </span></span>  
 <span data-ttu-id="93bcc-142">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="93bcc-142">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span></span>  
 [<span data-ttu-id="93bcc-143">Sicherungsmedien &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="93bcc-143">Backup Devices &#40;SQL Server&#41;</span></span>](backup-devices-sql-server.md)  
  
  
