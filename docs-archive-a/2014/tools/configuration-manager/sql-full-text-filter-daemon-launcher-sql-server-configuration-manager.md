---
title: Startprogramm für SQL-Volltextfilterdaemon (SQL Server-Konfigurations-Manager) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: d0dc03db-5f76-4558-b041-1ac7b9b5bb16
author: stevestein
ms.author: sstein
ms.openlocfilehash: 45194c893db048151cdb03d33f1419ef42246d69
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608187"
---
# <a name="sql-full-text-filter-daemon-launcher-sql-server-configuration-manager"></a><span data-ttu-id="4e52e-102">Startprogramm für SQL-Volltextfilterdaemon (SQL Server-Konfigurations-Manager)</span><span class="sxs-lookup"><span data-stu-id="4e52e-102">SQL Full-text Filter Daemon Launcher (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="4e52e-103">Ab [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]wird der FDHOST (SQL-Volltextfilterdaemon)-Startprogrammdienst von der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Volltextsuche zum Starten des Filterdaemon-Hostprozesses verwendet, der für das Filtern bei der Volltextsuche und die Wörtertrennung verantwortlich ist.</span><span class="sxs-lookup"><span data-stu-id="4e52e-103">Beginning in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], the SQL Full-text Filter Daemon Launcher (FDHOST Launcher) service is used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] full-text search to start the filter daemon host process, which handles full-text search filtering and word breaking.</span></span> <span data-ttu-id="4e52e-104">Dieser Dienst muss ausgeführt werden, damit die Volltextsuche verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="4e52e-104">This service must be running to use full-text search.</span></span> <span data-ttu-id="4e52e-105">Der FDHOST-Startprogrammdienst ist ein instanzabhängiger Dienst, dem eine bestimmte Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="4e52e-105">The FDHOST Launcher service is an instance-aware service that is associated with a specific instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4e52e-106">Der FDHOST-Startprogrammdienst gibt die Dienstkontoinformationen an jeden gestarteten Filterdaemon-Hostprozess weiter.</span><span class="sxs-lookup"><span data-stu-id="4e52e-106">The FDHOST Launcher service propagates the service account information to each filter daemon host process started.</span></span> <span data-ttu-id="4e52e-107">Informationen über die Prozesse des Filterdaemonhosts finden Sie unter "Architektur der Volltextsuche" in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="4e52e-107">For information about the filter daemon host processes, see "Full-Text Search Architecture" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
  
