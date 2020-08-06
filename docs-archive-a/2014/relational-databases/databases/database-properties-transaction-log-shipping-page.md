---
title: Datenbankeigenschaften (Seite Protokollversand) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.databaseproperties.logshipping.f1
ms.assetid: 72c4e539-fe11-4d57-b977-65b418d5916f
author: stevestein
ms.author: sstein
ms.openlocfilehash: dd36b3bc56bcd48c53871c9bc1e334d72c80ac78
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725906"
---
# <a name="database-properties-transaction-log-shipping-page"></a><span data-ttu-id="c291a-102">Datenbankeigenschaften (Seite Protokollversand)</span><span class="sxs-lookup"><span data-stu-id="c291a-102">Database Properties (Transaction Log Shipping Page)</span></span>
  <span data-ttu-id="c291a-103">Mithilfe dieser Seite können Sie die Eigenschaften des Protokollversands einer Datenbank konfigurieren und ändern.</span><span class="sxs-lookup"><span data-stu-id="c291a-103">Use this page to configure and modify the properties of log shipping for a database.</span></span>  
  
 <span data-ttu-id="c291a-104">Eine Erläuterung zu den Konzepten des Protokollversands finden Sie unter [Informationen zum Protokollversand &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c291a-104">For an explanation of log shipping concepts, see [About Log Shipping &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="c291a-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="c291a-105">Options</span></span>  
 <span data-ttu-id="c291a-106">**Diese Datenbank als primäre Datenbank in einer Protokollversandkonfiguration aktivieren**</span><span class="sxs-lookup"><span data-stu-id="c291a-106">**Enable this as a primary database in a log shipping configuration**</span></span>  
 <span data-ttu-id="c291a-107">Aktiviert diese Datenbank als primäre Datenbank im Protokollversand.</span><span class="sxs-lookup"><span data-stu-id="c291a-107">Enables this database as a log shipping primary database.</span></span> <span data-ttu-id="c291a-108">Aktivieren Sie dieses Kontrollkästchen, und konfigurieren Sie anschließend die übrigen Optionen auf dieser Seite.</span><span class="sxs-lookup"><span data-stu-id="c291a-108">Select it and then configure the remaining options on this page.</span></span> <span data-ttu-id="c291a-109">Wenn Sie dieses Kontrollkästchen deaktivieren, wird die Protokollversandkonfiguration für diese Datenbank aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="c291a-109">If you clear this check box, the log shipping configuration will be dropped for this database.</span></span>  
  
 <span data-ttu-id="c291a-110">**Sicherungseinstellungen**</span><span class="sxs-lookup"><span data-stu-id="c291a-110">**Backup Settings**</span></span>  
 <span data-ttu-id="c291a-111">Klicken Sie auf **Sicherungseinstellungen** , um die Parameter für Sicherungszeitplan, Speicherort, Warnung und Archivierung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c291a-111">Click **Backup Settings** to configure backup schedule, location, alert, and archiving parameters.</span></span>  
  
 <span data-ttu-id="c291a-112">**Sicherungszeitplan**</span><span class="sxs-lookup"><span data-stu-id="c291a-112">**Backup schedule**</span></span>  
 <span data-ttu-id="c291a-113">Zeigt den zurzeit ausgewählten Sicherungszeitplan der primären Datenbank an.</span><span class="sxs-lookup"><span data-stu-id="c291a-113">Shows the currently selected backup schedule for the primary database.</span></span> <span data-ttu-id="c291a-114">Zum Ändern dieser Einstellungen klicken Sie auf **Sicherungseinstellungen** .</span><span class="sxs-lookup"><span data-stu-id="c291a-114">Click **Backup Settings** to modify these settings.</span></span>  
  
 <span data-ttu-id="c291a-115">**Letzte erstellte Sicherung**</span><span class="sxs-lookup"><span data-stu-id="c291a-115">**Last backup created**</span></span>  
 <span data-ttu-id="c291a-116">Zeigt Uhrzeit und Datum der letzten Transaktionsprotokollsicherung an, die für die primäre Datenbank vorgenommen wurde.</span><span class="sxs-lookup"><span data-stu-id="c291a-116">Indicates the time and date of the last transaction log backup of the primary database.</span></span>  
  
 <span data-ttu-id="c291a-117">**Sekundäre Serverinstanzen und Datenbanken**</span><span class="sxs-lookup"><span data-stu-id="c291a-117">**Secondary server instances and databases**</span></span>  
 <span data-ttu-id="c291a-118">Führt die für die primäre Datenbank zurzeit konfigurierten sekundären Serverinstanzen und Datenbanken auf.</span><span class="sxs-lookup"><span data-stu-id="c291a-118">Lists the currently configured secondary servers and databases for this primary database.</span></span> <span data-ttu-id="c291a-119">Markieren Sie eine Datenbank, und klicken Sie dann auf **...** , um Änderungen an den für diese sekundäre Datenbank verfügbaren Parametern vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="c291a-119">Highlight a database, and then click **...** to modify the parameters associated with that secondary database.</span></span>  
  
 <span data-ttu-id="c291a-120">**Add (Hinzufügen)**</span><span class="sxs-lookup"><span data-stu-id="c291a-120">**Add**</span></span>  
 <span data-ttu-id="c291a-121">Klicken Sie auf **Hinzufügen** , um der Protokollversandkonfiguration der primären Datenbank eine sekundäre Datenbank hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="c291a-121">Click **Add** to add a secondary database to the log shipping configuration for this primary database.</span></span>  
  
 <span data-ttu-id="c291a-122">**Remove**</span><span class="sxs-lookup"><span data-stu-id="c291a-122">**Remove**</span></span>  
 <span data-ttu-id="c291a-123">Entfernt eine ausgewählte Datenbank aus dieser Protokollversandkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="c291a-123">Removes a selected database from this log shipping configuration.</span></span> <span data-ttu-id="c291a-124">Wählen Sie zuerst die Datenbank aus, und klicken Sie dann auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="c291a-124">Select the database first and then click **Remove**.</span></span>  
  
 <span data-ttu-id="c291a-125">**Überwachungsserverinstanz verwenden**</span><span class="sxs-lookup"><span data-stu-id="c291a-125">**Use a monitor server instance**</span></span>  
 <span data-ttu-id="c291a-126">Richtet eine Überwachungsserverinstanz für die Protokollversandkonfiguration ein.</span><span class="sxs-lookup"><span data-stu-id="c291a-126">Sets up a monitor server instance for this log shipping configuration.</span></span> <span data-ttu-id="c291a-127">Aktivieren Sie das Kontrollkästchen **Überwachungsserverinstanz verwenden** , und klicken Sie dann auf **Einstellungen** , um die Überwachungsserverinstanz anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c291a-127">Select the **Use a monitor server instance** check box and then click **Settings** to specify the monitor server instance.</span></span>  
  
 <span data-ttu-id="c291a-128">**Überwachungsserverinstanz**</span><span class="sxs-lookup"><span data-stu-id="c291a-128">**Monitor server instance**</span></span>  
 <span data-ttu-id="c291a-129">Zeigt die für die Protokollversandkonfiguration zurzeit konfigurierte Überwachungsserverinstanz an.</span><span class="sxs-lookup"><span data-stu-id="c291a-129">Indicates the currently configured monitor server instance for this log shipping configuration.</span></span>  
  
 <span data-ttu-id="c291a-130">**Einstellungen**</span><span class="sxs-lookup"><span data-stu-id="c291a-130">**Settings**</span></span>  
 <span data-ttu-id="c291a-131">Konfiguriert die Überwachungsserverinstanz für eine Protokollversandkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="c291a-131">Configures the monitor server instance for a log shipping configuration.</span></span> <span data-ttu-id="c291a-132">Klicken Sie auf **Einstellungen** , um die Überwachungsserverinstanz zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c291a-132">Click **Settings** to configure this monitor server instance.</span></span>  
  
 <span data-ttu-id="c291a-133">**Skript für Konfiguration erstellen**</span><span class="sxs-lookup"><span data-stu-id="c291a-133">**Script Configuration**</span></span>  
 <span data-ttu-id="c291a-134">Generiert ein Skript, das den Protokollversand mit den ausgewählten Parametern konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="c291a-134">Generates a script for configuring log shipping with the parameters you have selected.</span></span> <span data-ttu-id="c291a-135">Klicken Sie auf **Skript für Konfiguration erstellen**, und wählen Sie dann ein Ausgabeziel für das Skript aus.</span><span class="sxs-lookup"><span data-stu-id="c291a-135">Click **Script Configuration**, and then choose an output destination for the script.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c291a-136">Bevor Sie ein Skript für die Einstellungen einer sekundären Datenbank erstellen, müssen Sie das Dialogfeld **Einstellungen für die sekundäre Datenbank** aufrufen.</span><span class="sxs-lookup"><span data-stu-id="c291a-136">Before scripting settings for a secondary database, you must invoke the **Secondary Database Settings** dialog box.</span></span> <span data-ttu-id="c291a-137">Durch das Aufrufen dieses Dialogfelds wird eine Verbindung mit dem sekundären Server hergestellt, und die aktuellen Eigenschaften der sekundären Datenbank, die zum Generieren des Skripts erforderlich sind, werden abgerufen.</span><span class="sxs-lookup"><span data-stu-id="c291a-137">Invoking this dialog box connects you to the secondary server and retrieves the current settings of the secondary database that are needed to generate the script.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c291a-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c291a-138">See Also</span></span>  
 <span data-ttu-id="c291a-139">[Gespeicherte Prozeduren für den Protokollversand &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/log-shipping-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c291a-139">[Log Shipping Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/log-shipping-stored-procedures-transact-sql) </span></span>  
 [<span data-ttu-id="c291a-140">Protokollversandtabellen &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c291a-140">Log Shipping Tables &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-tables/log-shipping-tables-transact-sql)  
  
  
