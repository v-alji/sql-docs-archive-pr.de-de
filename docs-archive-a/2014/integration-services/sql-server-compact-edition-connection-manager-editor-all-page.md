---
title: Verbindungs-Manager-Editor für SQL Server Compact Edition (Seite "alle") | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sqlmobileconnection.all.f1
helpviewer_keywords:
- SQL Server Compact Connection Manager Editor
ms.assetid: f9fbff4b-c502-44b3-8e7b-398d66e82206
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4f881d63de5435426475c3aed4b666870d706b40
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616590"
---
# <a name="sql-server-compact-edition-connection-manager-editor-all-page"></a><span data-ttu-id="5268b-102">Verbindungs-Manager-Editor für SQL Server Compact Edition (Seite Alle)</span><span class="sxs-lookup"><span data-stu-id="5268b-102">SQL Server Compact Edition Connection Manager Editor (All Page)</span></span>
  <span data-ttu-id="5268b-103">Mithilfe des Dialogfelds **Verbindungs-Manager-Editor für SQL Server Compact Edition** können Sie Eigenschaften für die Verbindung mit einer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact-Datenbank angeben.</span><span class="sxs-lookup"><span data-stu-id="5268b-103">Use the **SQL Server Compact Edition Connection Manager** dialog box to specify properties for connecting to a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact database.</span></span>  
  
 <span data-ttu-id="5268b-104">Weitere Informationen zum [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact Edition-Verbindungs-Manager finden Sie unter [Verbindungs-Manager-Editor für SQL Server Compact Edition](connection-manager/sql-server-compact-edition-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="5268b-104">To learn more about the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact Edition connection manager, see [SQL Server Compact Edition Connection Manager](connection-manager/sql-server-compact-edition-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="5268b-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="5268b-105">Options</span></span>  
 <span data-ttu-id="5268b-106">**AutoShrink Threshold**</span><span class="sxs-lookup"><span data-stu-id="5268b-106">**AutoShrink Threshold**</span></span>  
 <span data-ttu-id="5268b-107">Gibt den freien Speicherplatz in Prozent an, der in der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact-Datenbank zulässig ist, bevor der Prozess des automatischen Verkleinerns ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5268b-107">Specify the amount of free space, as a percentage, that is allowed in the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact database before the autoshrink process runs.</span></span>  
  
 <span data-ttu-id="5268b-108">**Default Lock Escalation**</span><span class="sxs-lookup"><span data-stu-id="5268b-108">**Default Lock Escalation**</span></span>  
 <span data-ttu-id="5268b-109">Gibt die Anzahl der Datenbanksperren an, die die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact-Datenbank abruft, bevor sie versucht, die Sperren auszuweiten.</span><span class="sxs-lookup"><span data-stu-id="5268b-109">Specify the number of database locks that the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact database acquires before it tries to escalate locks.</span></span>  
  
 <span data-ttu-id="5268b-110">**Default Lock Timeout**</span><span class="sxs-lookup"><span data-stu-id="5268b-110">**Default Lock Timeout**</span></span>  
 <span data-ttu-id="5268b-111">Gibt das Standardintervall in Millisekunden an, das eine Transaktion auf eine Sperre wartet.</span><span class="sxs-lookup"><span data-stu-id="5268b-111">Specify the default interval, in milliseconds, that a transaction will wait for a lock.</span></span>  
  
 <span data-ttu-id="5268b-112">**Flush Interval**</span><span class="sxs-lookup"><span data-stu-id="5268b-112">**Flush Interval**</span></span>  
 <span data-ttu-id="5268b-113">Gibt das Intervall zwischen Transaktionen an, für die ein Commit erfolgt ist, und in dem die Daten auf einen Datenträger gespeichert werden. Zeiteinheit sind Sekunden.</span><span class="sxs-lookup"><span data-stu-id="5268b-113">Specify the interval, in seconds, between committed transactions to flush data to disk.</span></span>  
  
 <span data-ttu-id="5268b-114">**Locale Identifier**</span><span class="sxs-lookup"><span data-stu-id="5268b-114">**Locale Identifier**</span></span>  
 <span data-ttu-id="5268b-115">Gibt die Gebietsschema-ID (Locale ID, LCID) der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact-Datenbank an.</span><span class="sxs-lookup"><span data-stu-id="5268b-115">Specify the Locale ID (LCID) of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact database.</span></span>  
  
 <span data-ttu-id="5268b-116">**Max Buffer Size**</span><span class="sxs-lookup"><span data-stu-id="5268b-116">**Max Buffer Size**</span></span>  
 <span data-ttu-id="5268b-117">Gibt die maximale Menge an Arbeitsspeicher in Kilobyte an, die von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact verwendet werden, bevor die Daten auf einem Datenträger gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="5268b-117">Specify the maximum amount of memory, in kilobytes, that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact uses before flushing data to disk.</span></span>  
  
 <span data-ttu-id="5268b-118">**Maximale Datenbankgröße**</span><span class="sxs-lookup"><span data-stu-id="5268b-118">**Max Database Size**</span></span>  
 <span data-ttu-id="5268b-119">Gibt die Maximalgröße der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact-Datenbank in Megabyte an.</span><span class="sxs-lookup"><span data-stu-id="5268b-119">Specify the maximum size, in megabytes, of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact database.</span></span>  
  
 <span data-ttu-id="5268b-120">**Mode**</span><span class="sxs-lookup"><span data-stu-id="5268b-120">**Mode**</span></span>  
 <span data-ttu-id="5268b-121">Gibt an, in welchem Dateimodus die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact-Datenbank zu öffnen ist.</span><span class="sxs-lookup"><span data-stu-id="5268b-121">Specify the file mode in which to open the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact database.</span></span> <span data-ttu-id="5268b-122">Der Standardwert für diese Eigenschaft lautet **Read Write**.</span><span class="sxs-lookup"><span data-stu-id="5268b-122">The default value for this property is **Read Write**.</span></span>  
  
 <span data-ttu-id="5268b-123">Die Option Mode kann vier Werte annehmen. Siehe dazu die folgende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="5268b-123">The Mode option has four values, as described in the following table.</span></span>  
  
|<span data-ttu-id="5268b-124">Wert</span><span class="sxs-lookup"><span data-stu-id="5268b-124">Value</span></span>|<span data-ttu-id="5268b-125">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5268b-125">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5268b-126">**Schreibgeschützt**</span><span class="sxs-lookup"><span data-stu-id="5268b-126">**Read Only**</span></span>|<span data-ttu-id="5268b-127">Gibt an, dass der Zugriff auf die Datenbank schreibgeschützt erfolgen kann.</span><span class="sxs-lookup"><span data-stu-id="5268b-127">Specifies read-only access to the database.</span></span>|  
|<span data-ttu-id="5268b-128">**Lese Schreibvorgang**</span><span class="sxs-lookup"><span data-stu-id="5268b-128">**Read Write**</span></span>|<span data-ttu-id="5268b-129">Gibt Lese-/Schreibberechtigungen für die Datenbank an.</span><span class="sxs-lookup"><span data-stu-id="5268b-129">Specifies read/write permission to the database.</span></span>|  
|<span data-ttu-id="5268b-130">**Exklusiv**</span><span class="sxs-lookup"><span data-stu-id="5268b-130">**Exclusive**</span></span>|<span data-ttu-id="5268b-131">Gibt exklusiven Zugriff auf die Datenbank an.</span><span class="sxs-lookup"><span data-stu-id="5268b-131">Specifies exclusive access to the database.</span></span>|  
|<span data-ttu-id="5268b-132">**Shared Read**</span><span class="sxs-lookup"><span data-stu-id="5268b-132">**Shared Read**</span></span>|<span data-ttu-id="5268b-133">Gibt an, dass andere Benutzer zu selben Zeit Daten aus der Datenbank lesen können.</span><span class="sxs-lookup"><span data-stu-id="5268b-133">Specifies that other users can read from the database at the same time.</span></span>|  
  
 <span data-ttu-id="5268b-134">**Persist Security Info**</span><span class="sxs-lookup"><span data-stu-id="5268b-134">**Persist Security Info**</span></span>  
 <span data-ttu-id="5268b-135">Gibt an, ob als Teil der Verbindungszeichenfolge Sicherheitsinformationen zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5268b-135">Specify whether security information is returned as part of the connection string.</span></span> <span data-ttu-id="5268b-136">Der Standardwert für diese Option ist **false**.</span><span class="sxs-lookup"><span data-stu-id="5268b-136">The default value for this option is **False**.</span></span>  
  
 <span data-ttu-id="5268b-137">**Temp File Directory**</span><span class="sxs-lookup"><span data-stu-id="5268b-137">**Temp File Directory**</span></span>  
 <span data-ttu-id="5268b-138">Geben Sie den Pfad der temporären [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact-Datenbankdatei an.</span><span class="sxs-lookup"><span data-stu-id="5268b-138">Specify the location of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact temporary database file.</span></span>  
  
 <span data-ttu-id="5268b-139">**Data Source**</span><span class="sxs-lookup"><span data-stu-id="5268b-139">**Data Source**</span></span>  
 <span data-ttu-id="5268b-140">Geben Sie den Namen der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact-Datenbank an.</span><span class="sxs-lookup"><span data-stu-id="5268b-140">Specify the name of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact database.</span></span>  
  
 <span data-ttu-id="5268b-141">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="5268b-141">**Password**</span></span>  
 <span data-ttu-id="5268b-142">Geben Sie das Kennwort für die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact-Datenbank ein.</span><span class="sxs-lookup"><span data-stu-id="5268b-142">Enter the password for the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5268b-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5268b-143">See Also</span></span>  
 <span data-ttu-id="5268b-144">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="5268b-144">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="5268b-145">Verbindungs-Manager-Editor für SQL Server Compact Edition &#40;Seite „Verbindung“&#41;</span><span class="sxs-lookup"><span data-stu-id="5268b-145">SQL Server Compact Edition Connection Manager Editor &#40;Connection Page&#41;</span></span>](../../2014/integration-services/sql-server-compact-edition-connection-manager-editor-connection-page.md)  
  
  
