---
title: Datenbankeigenschaften (Seite Änderungsnachverfolgung) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.databaseproperties.changetracking.f1
ms.assetid: 9b929640-bc62-449b-9b06-b5a77b8cf372
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4107f81ef4cdf19df60d4a70d8e79007f2c9270c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718241"
---
# <a name="database-properties-changetracking-page"></a><span data-ttu-id="c6e72-102">Datenbankeigenschaften (Seite Änderungsnachverfolgung)</span><span class="sxs-lookup"><span data-stu-id="c6e72-102">Database Properties (ChangeTracking Page)</span></span>
  <span data-ttu-id="c6e72-103">Mithilfe dieser Seite können Sie die Einstellungen der Änderungsnachverfolgung für die ausgewählte Datenbank anzeigen und ändern.</span><span class="sxs-lookup"><span data-stu-id="c6e72-103">Use this page to view or modify change tracking settings for the selected database.</span></span> <span data-ttu-id="c6e72-104">Informationen zu den auf dieser Seite verfügbaren Optionen finden Sie unter [Aktivieren und Deaktivieren der Änderungsnachverfolgung &#40;SQL Server&#41;](../track-changes/enable-and-disable-change-tracking-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c6e72-104">For more information about the options available on this page, see [Enable and Disable Change Tracking &#40;SQL Server&#41;](../track-changes/enable-and-disable-change-tracking-sql-server.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="c6e72-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="c6e72-105">Options</span></span>  
 <span data-ttu-id="c6e72-106">**Änderungsnachverfolgung**</span><span class="sxs-lookup"><span data-stu-id="c6e72-106">**Change Tracking**</span></span>  
 <span data-ttu-id="c6e72-107">Mithilfe dieser Option können Sie die Änderungsnachverfolgung für die Datenbank aktivieren und deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="c6e72-107">Use to enable or disable change tracking for the database.</span></span>  
  
 <span data-ttu-id="c6e72-108">Um die Änderungsnachverfolgung aktivieren zu können, müssen Sie über die Berechtigung zur Änderung der Datenbank verfügen.</span><span class="sxs-lookup"><span data-stu-id="c6e72-108">To enable change tracking, you must have permission to modify the database.</span></span>  
  
 <span data-ttu-id="c6e72-109">Durch Festlegen des Werts auf **True** wird eine Datenbankoption festgelegt, die eine Aktivierung der Änderungsnachverfolgung für einzelne Tabellen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="c6e72-109">Setting the value to **True** sets a database option that allows change tracking to be enabled on individual tables.</span></span>  
  
 <span data-ttu-id="c6e72-110">Sie können die Änderungsnachverfolgung mithilfe von [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql)konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c6e72-110">You can also configure change tracking by using [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
 <span data-ttu-id="c6e72-111">**Aufbewahrungszeitraum**</span><span class="sxs-lookup"><span data-stu-id="c6e72-111">**Retention Period**</span></span>  
 <span data-ttu-id="c6e72-112">Gibt die Mindestdauer für die Beibehaltung von Änderungsnachverfolgungsinformationen in der Datenbank an.</span><span class="sxs-lookup"><span data-stu-id="c6e72-112">Specifies the minimum period for keeping change track information in the database.</span></span> <span data-ttu-id="c6e72-113">Die Daten werden nur dann entfernt, wenn der Wert für **Automatisches Cleanup**auf **True**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="c6e72-113">Data is removed only if the **Auto Clean-Up**value is **True**.</span></span>  
  
 <span data-ttu-id="c6e72-114">Der Standardwert ist 2.</span><span class="sxs-lookup"><span data-stu-id="c6e72-114">The default value is 2.</span></span>  
  
 <span data-ttu-id="c6e72-115">**Einheiten für die Beibehaltungsdauer**</span><span class="sxs-lookup"><span data-stu-id="c6e72-115">**Retention Period Units**</span></span>  
 <span data-ttu-id="c6e72-116">Gibt die Einheiten für den Beibehaltungsdauerwert an.</span><span class="sxs-lookup"><span data-stu-id="c6e72-116">Specifies the units for the Retention Period value.</span></span> <span data-ttu-id="c6e72-117">Sie können **Tage**, **Stunden**oder **Minuten**auswählen.</span><span class="sxs-lookup"><span data-stu-id="c6e72-117">You can select **Days**, **Hours**, or **Minutes**.</span></span> <span data-ttu-id="c6e72-118">Der Standardwert ist **Tage**.</span><span class="sxs-lookup"><span data-stu-id="c6e72-118">The default value is **Days**.</span></span>  
  
 <span data-ttu-id="c6e72-119">Die Mindestbeibehaltungsdauer ist 1 Minute.</span><span class="sxs-lookup"><span data-stu-id="c6e72-119">The minimum retention period is 1 minute.</span></span> <span data-ttu-id="c6e72-120">Es gibt keine maximale Beibehaltungsdauer.</span><span class="sxs-lookup"><span data-stu-id="c6e72-120">There is no maximum retention period.</span></span>  
  
 <span data-ttu-id="c6e72-121">**Automatisches Cleanup**</span><span class="sxs-lookup"><span data-stu-id="c6e72-121">**Auto Clean-Up**</span></span>  
 <span data-ttu-id="c6e72-122">Gibt an, ob Änderungsnachverfolgungsinformationen nach der angegebenen Beibehaltungsdauer automatisch entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="c6e72-122">Indicates whether change tracking information is automatically removed after the specified retention period.</span></span>  
  
 <span data-ttu-id="c6e72-123">Durch Aktivieren von **Automatisches Cleanup** wird eine vorhandene benutzerdefinierte Beibehaltungsdauer auf die Standardbeibehaltungsdauer von 2 Tagen zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="c6e72-123">Enabling **Auto Clean-Up** resets any previous custom retention period to the default retention period of 2 days.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6e72-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c6e72-124">See Also</span></span>  
 <span data-ttu-id="c6e72-125">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c6e72-125">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 [<span data-ttu-id="c6e72-126">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c6e72-126">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-sql-server-transact-sql)  
  
  
