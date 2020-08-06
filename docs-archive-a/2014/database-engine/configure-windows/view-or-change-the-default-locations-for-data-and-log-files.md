---
title: Anzeigen oder Ändern der Standard Speicherorte für Daten-und Protokolldateien (SQL Server Management Studio) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- log files [SQL Server], changing default location
- data files [SQL Server], changing default location
ms.assetid: 70a57fda-fcfe-490f-9cf6-5df620e32b2a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: def6be137aecbab7f2730fa4c2bf210b374a3a7a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697149"
---
# <a name="view-or-change-the-default-locations-for-data-and-log-files-sql-server-management-studio"></a><span data-ttu-id="ccce2-102">Anzeigen oder Ändern der Standardspeicherorte für Daten- und Protokolldateien (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="ccce2-102">View or Change the Default Locations for Data and Log Files (SQL Server Management Studio)</span></span>
  <span data-ttu-id="ccce2-103">In diesem Thema wird das Anzeigen und Ändern der Standardspeicherorte von neuen Daten- und Protokolldateien in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ccce2-103">This topic describes how to view and change the default locations of new data and log files in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="ccce2-104">Der Standardpfad wird aus der Registrierung abgerufen.</span><span class="sxs-lookup"><span data-stu-id="ccce2-104">The default path is obtained from the registry.</span></span> <span data-ttu-id="ccce2-105">Nachdem Sie den Speicherort geändert haben, verwenden alle neuen Datenbanken, die in der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] erstellt werden, diesen Speicherort, sofern kein anderer Speicherort angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ccce2-105">After you change the location all new databases created in the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will use that location if a different location is not specified.</span></span>  
  
 <span data-ttu-id="ccce2-106">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="ccce2-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ccce2-107">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="ccce2-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ccce2-108">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="ccce2-108">Recommendations</span></span>](#Recommendations)  
  
-   <span data-ttu-id="ccce2-109">**So zeigen Sie die Standardspeicherorte von Daten- und Protokolldateien an oder ändern diese mit:**</span><span class="sxs-lookup"><span data-stu-id="ccce2-109">**To view or change the data and log file default locations, using:**</span></span>  
  
     [<span data-ttu-id="ccce2-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ccce2-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   <span data-ttu-id="ccce2-111">**Nachverfolgung:**  [Ändern der Standardspeicherorte](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="ccce2-111">**Follow Up:**  [Changing the Default Locations](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ccce2-112">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="ccce2-112">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="ccce2-113">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="ccce2-113">Recommendations</span></span>  
 <span data-ttu-id="ccce2-114">Als bewährte Methode zum Schutz der Datendateien und Protokolldateien sollten Sie sicherstellen, dass diese durch Zugriffssteuerungslisten (ACLs) geschützt sind.</span><span class="sxs-lookup"><span data-stu-id="ccce2-114">The best practice for protecting your data files and log files is to ensure that they are protected by access control lists (ACLs).</span></span> <span data-ttu-id="ccce2-115">Die ACLs sollten für den Verzeichnisstamm eingerichtet werden, unter dem die Dateien erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="ccce2-115">The ACLs should be set on the directory root under which the files are created.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ccce2-116">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="ccce2-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ccce2-117">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="ccce2-117">Permissions</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ccce2-118">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ccce2-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-or-change-the-default-locations-for-database-files"></a><span data-ttu-id="ccce2-119">So zeigen Sie die Standardspeicherorte für Datenbankdateien an oder ändern diese</span><span class="sxs-lookup"><span data-stu-id="ccce2-119">To view or change the default locations for database files</span></span>  
  
1.  <span data-ttu-id="ccce2-120">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf einen Server, und klicken Sie anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="ccce2-120">In Object Explorer, right-click a server and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="ccce2-121">Klicken Sie im linken Bereich auf die Seite **Datenbankeinstellungen** .</span><span class="sxs-lookup"><span data-stu-id="ccce2-121">In the left panel, click the **Database settings** page.</span></span>  
  
3.  <span data-ttu-id="ccce2-122">Im Bereich **Standardspeicherorte für Datenbank**können Sie die aktuellen Standardspeicherorte für neue Datendateien und neue Protokolldateien anzeigen.</span><span class="sxs-lookup"><span data-stu-id="ccce2-122">In **Database default locations**, view the current default locations for new data files and new log files.</span></span> <span data-ttu-id="ccce2-123">Um einen Standardspeicherort zu ändern, geben Sie einen neuen Standardpfadnamen in das Feld **Daten** oder **Protokoll** ein, oder klicken Sie auf die Schaltfläche zum Durchsuchen, um einen Pfadnamen zu suchen und auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="ccce2-123">To change a default location, enter a new default pathname in the **Data** or **Log** field, or click the browse button to find and select a pathname.</span></span>  
  
##  <a name="follow-up-after-changing-the-default-locations"></a><a name="FollowUp"></a><span data-ttu-id="ccce2-124">Nachverfolgung: nach dem Ändern der Standard Speicherorte</span><span class="sxs-lookup"><span data-stu-id="ccce2-124">Follow Up: After Changing the Default Locations</span></span>  
 <span data-ttu-id="ccce2-125">Sie müssen den SQL Server-Dienst beenden und wieder starten, um die Änderung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="ccce2-125">You must stop and start the SQL Server service to complete the change.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccce2-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ccce2-126">See Also</span></span>  
 <span data-ttu-id="ccce2-127">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ccce2-127">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 [<span data-ttu-id="ccce2-128">Erstellen einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="ccce2-128">Create a Database</span></span>](../../relational-databases/databases/create-a-database.md)  
  
  
