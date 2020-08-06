---
title: Überlegungen zu administrativen Aufgaben bei Oracle-Verlegern | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- Oracle publishing [SQL Server replication], administrative considerations
- administering replication, Oracle publishing
ms.assetid: cfd81fb5-419b-4a1b-97c4-be7c9d4ee289
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3104b507987a4a236d39dd0ae1f8e3c29358c730
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620279"
---
# <a name="administrative-considerations-for-oracle-publishers"></a><span data-ttu-id="a5399-102">Überlegungen zu administrativen Aufgaben bei Oracle-Verlegern</span><span class="sxs-lookup"><span data-stu-id="a5399-102">Administrative Considerations for Oracle Publishers</span></span>
  <span data-ttu-id="a5399-103">Auch nach dem Konfigurieren eines Oracle-Verlegers und dem Einrichten der Replikationsmechanismen zur Änderungsnachverfolgung können Administratoren von Oracle-Datenbanksystemen noch die üblichen Oracle-Datenbankhilfsprogamme nutzen und typische Systemverwaltungsaufgaben ausführen.</span><span class="sxs-lookup"><span data-stu-id="a5399-103">After an Oracle Publisher is configured and the replication change tracking mechanisms are in place, administrators of the Oracle database system can still use standard Oracle database utilities and perform typical system administration tasks.</span></span> <span data-ttu-id="a5399-104">Dabei sollte jedoch berücksichtigt werden, wie sich die Ausführung bestimmter Verwaltungsaufgaben auf die veröffentlichten Daten auswirkt.</span><span class="sxs-lookup"><span data-stu-id="a5399-104">However, you should be aware of the effects on the published data of performing certain administrative tasks.</span></span>  
  
 <span data-ttu-id="a5399-105">Mit Ausnahme des Löschens oder Änderns einer Spalte, die für eine Replikation veröffentlicht wurde, bzw. des Löschens oder Änderns von Replikationsobjekten spielen die folgenden Überlegungen bei Momentaufnahmeveröffentlichungen keine Rolle.</span><span class="sxs-lookup"><span data-stu-id="a5399-105">With the exception of dropping or modifying a column that is published for replication, or dropping or modifying any replication objects, these considerations do not apply to snapshot publications.</span></span>  
  
## <a name="importing-and-loading-data"></a><span data-ttu-id="a5399-106">Importieren und Laden von Daten</span><span class="sxs-lookup"><span data-stu-id="a5399-106">Importing and loading data</span></span>  
 <span data-ttu-id="a5399-107">Die Änderungsnachverfolgung bei Transaktionsveröffentlichungen in Oracle erfolgt mithilfe von Triggern.</span><span class="sxs-lookup"><span data-stu-id="a5399-107">Triggers are used in change tracking for transactional publications on Oracle.</span></span> <span data-ttu-id="a5399-108">Änderungen an veröffentlichten Tabellen können nur dann auf Abonnenten repliziert werden, wenn die Replikation beim Aktualisieren, Einfügen oder Löschen Trigger auslöst.</span><span class="sxs-lookup"><span data-stu-id="a5399-108">Changes to published tables can be replicated to Subscribers only if the replication triggers fire when an update, insert, or delete occurs.</span></span> <span data-ttu-id="a5399-109">Die Oracle-Hilfsprogramme Oracle Import und SQL\*Loader verfügen beide über Optionen, die sich darauf auswirken, ob Trigger ausgelöst werden, wenn mithilfe dieser Hilfsprogramme Zeilen in replizierte Tabellen eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="a5399-109">The Oracle utilities Oracle Import and SQL\*Loader both have options that affect whether triggers will fire when rows are inserted into replicated tables with these utilities.</span></span>  
  
### <a name="oracle-import"></a><span data-ttu-id="a5399-110">Oracle Import</span><span class="sxs-lookup"><span data-stu-id="a5399-110">Oracle Import</span></span>  
 <span data-ttu-id="a5399-111">Mit Oracle Import können Sie für die Option **ignore** 'y' oder 'n' festlegen (die Standardeinstellung ist 'n').</span><span class="sxs-lookup"><span data-stu-id="a5399-111">With Oracle Import, you can set the option **ignore** to 'y' or 'n' (the default is 'n').</span></span> <span data-ttu-id="a5399-112">Wenn für **ignore** 'n' festgelegt ist, wird die Tabelle gelöscht und beim Importieren neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="a5399-112">If **ignore** is set to 'n', the table is dropped and re-created during import.</span></span> <span data-ttu-id="a5399-113">Dabei werden die Replikationstrigger entfernt, und die Replikation wird deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="a5399-113">This removes replication triggers and disables replication.</span></span> <span data-ttu-id="a5399-114">Wenn für **ignore** 'y' festgelegt ist, wird beim Importieren versucht, die Zeilen in die vorhandene Tabelle zu laden, wodurch die Replikationstrigger ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="a5399-114">If **ignore** is set to 'y', import will attempt to load the rows into the existing table, which fires the replication triggers.</span></span> <span data-ttu-id="a5399-115">Stellen Sie daher sicher, dass beim Importieren in eine replizierte Tabelle mit dem Import-Hilfsprogramm für **ignore** 'y' festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="a5399-115">Therefore, ensure **ignore** is set to 'y' when importing into a replicated table with the Import tool.</span></span>  
  
### <a name="sqlloader"></a><span data-ttu-id="a5399-116">SQL\*Loader</span><span class="sxs-lookup"><span data-stu-id="a5399-116">SQL\*Loader</span></span>  
 <span data-ttu-id="a5399-117">Mit SQL\*-Loader können Sie die Option **direct** auf TRUE oder FALSE festlegen (der Standardwert ist FALSE).</span><span class="sxs-lookup"><span data-stu-id="a5399-117">With SQL\*Loader, you can set the option **direct** to 'true' or 'false' (the default is 'false').</span></span> <span data-ttu-id="a5399-118">Wenn für **direct** 'false' festgelegt ist, werden die Zeilen mithilfe herkömmlicher INSERT-Anweisungen eingefügt, die die Replikationstrigger auslösen.</span><span class="sxs-lookup"><span data-stu-id="a5399-118">If **direct** is set to 'false', rows are inserted using conventional INSERT statements, which fire replication triggers.</span></span> <span data-ttu-id="a5399-119">Wenn für **direct** 'true' festgelegt ist, wird die Last optimiert, und die Trigger werden nicht ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="a5399-119">If **direct** is set to 'true', the load is optimized, and triggers are not fired.</span></span> <span data-ttu-id="a5399-120">Stellen Sie daher sicher, dass beim Laden in eine replizierte Tabelle mit SQL\*Loader für **direct** 'false' festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="a5399-120">Therefore, ensure **direct** is set to 'false' when loading into a replicated table with the SQL\*Loader tool.</span></span>  
  
## <a name="making-changes-to-published-objects"></a><span data-ttu-id="a5399-121">Ändern von veröffentlichten Objekten</span><span class="sxs-lookup"><span data-stu-id="a5399-121">Making changes to published objects</span></span>  
 <span data-ttu-id="a5399-122">Die folgenden Aktionen bedürfen keiner speziellen Überlegungen:</span><span class="sxs-lookup"><span data-stu-id="a5399-122">The following actions require no special considerations:</span></span>  
  
-   <span data-ttu-id="a5399-123">Erneutes Erstellen von Indizes für veröffentlichte Tabellen</span><span class="sxs-lookup"><span data-stu-id="a5399-123">Rebuilding indexes on published tables.</span></span>  
  
-   <span data-ttu-id="a5399-124">Hinzufügen von Benutzertriggern zu veröffentlichten Tabellen</span><span class="sxs-lookup"><span data-stu-id="a5399-124">Adding user triggers to a published table.</span></span>  
  
 <span data-ttu-id="a5399-125">Bei der folgenden Aktion müssen Sie alle Aktivitäten an den veröffentlichten Tabellen einstellen:</span><span class="sxs-lookup"><span data-stu-id="a5399-125">The following action requires you to stop all activity on the published tables:</span></span>  
  
-   <span data-ttu-id="a5399-126">Verschieben einer veröffentlichten Tabelle</span><span class="sxs-lookup"><span data-stu-id="a5399-126">Moving a published table.</span></span>  
  
 <span data-ttu-id="a5399-127">Bei den folgenden Aktionen müssen Sie die Veröffentlichung löschen, die Operation ausführen und die Veröffentlichung dann erneut erstellen:</span><span class="sxs-lookup"><span data-stu-id="a5399-127">The following actions require you to drop the publication, perform the operation, and then recreate the publication:</span></span>  
  
-   <span data-ttu-id="a5399-128">Abschneiden von Daten in einer veröffentlichten Tabelle</span><span class="sxs-lookup"><span data-stu-id="a5399-128">Truncating a published table.</span></span>  
  
-   <span data-ttu-id="a5399-129">Umbenennen einer veröffentlichten Tabelle</span><span class="sxs-lookup"><span data-stu-id="a5399-129">Renaming a published table.</span></span>  
  
-   <span data-ttu-id="a5399-130">Hinzufügen einer Spalte zu einer veröffentlichten Tabelle</span><span class="sxs-lookup"><span data-stu-id="a5399-130">Adding a column to a published table.</span></span>  
  
-   <span data-ttu-id="a5399-131">Löschen oder Ändern einer Spalte, die für Replikationszwecke veröffentlicht wurde</span><span class="sxs-lookup"><span data-stu-id="a5399-131">Dropping or modifying a column that is published for replication.</span></span>  
  
-   <span data-ttu-id="a5399-132">Ausführen nicht protokollierter Operationen</span><span class="sxs-lookup"><span data-stu-id="a5399-132">Performing non-logged operations.</span></span>  
  
## <a name="dropping-or-modifying-replication-objects"></a><span data-ttu-id="a5399-133">Löschen oder Ändern von Replikationsobjekten</span><span class="sxs-lookup"><span data-stu-id="a5399-133">Dropping or modifying replication objects</span></span>  
 <span data-ttu-id="a5399-134">Sie müssen den Verleger löschen und neu konfigurieren, wenn Sie Nachverfolgungstabellen, Trigger, Sequenzen oder gespeicherte Prozeduren auf Verlegerebene löschen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="a5399-134">You must drop and reconfigure the Publisher if you drop or modify any Publisher level tracking tables, triggers, sequences, or stored procedures.</span></span> <span data-ttu-id="a5399-135">Eine Teilliste dieser Objekte finden Sie unter [Auf dem Oracle-Verleger erstellte Objekte](objects-created-on-the-oracle-publisher.md).</span><span class="sxs-lookup"><span data-stu-id="a5399-135">For a partial list of these objects, see [Objects Created on the Oracle Publisher](objects-created-on-the-oracle-publisher.md).</span></span>  
  
 <span data-ttu-id="a5399-136">Informationen zum Löschen und Neukonfigurieren des Verlegers finden Sie im Abschnitt zu Änderungen, die eine Neukonfiguration des Verlegers erforderlich machen, im Thema [Troubleshooting Oracle Publishers](troubleshooting-oracle-publishers.md).</span><span class="sxs-lookup"><span data-stu-id="a5399-136">For information about dropping and reconfiguring the Publisher, see the section "Changes are made that require reconfiguration of the Publisher" in the topic [Troubleshooting Oracle Publishers](troubleshooting-oracle-publishers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5399-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a5399-137">See Also</span></span>  
 <span data-ttu-id="a5399-138">[Konfigurieren eines Oracle-Verlegers](configure-an-oracle-publisher.md) </span><span class="sxs-lookup"><span data-stu-id="a5399-138">[Configure an Oracle Publisher](configure-an-oracle-publisher.md) </span></span>  
 <span data-ttu-id="a5399-139">[Überlegungen zum Entwurf und Einschränkungen für Oracle-Verleger](design-considerations-and-limitations-for-oracle-publishers.md) </span><span class="sxs-lookup"><span data-stu-id="a5399-139">[Design Considerations and Limitations for Oracle Publishers](design-considerations-and-limitations-for-oracle-publishers.md) </span></span>  
 [<span data-ttu-id="a5399-140">Veröffentlichungen mit Oracle (Übersicht)</span><span class="sxs-lookup"><span data-stu-id="a5399-140">Oracle Publishing Overview</span></span>](oracle-publishing-overview.md)  
  
  
