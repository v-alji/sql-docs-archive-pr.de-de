---
title: Paket auswählen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.selectapackage.f1
helpviewer_keywords:
- Select a Package dialog box
ms.assetid: 92b47a2b-21b5-460a-885d-6cc4bb567249
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b35276791b004a011a1c2656057046be05ed6770
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607929"
---
# <a name="select-a-package"></a><span data-ttu-id="e6a30-102">Paket auswählen</span><span class="sxs-lookup"><span data-stu-id="e6a30-102">Select a Package</span></span>
  <span data-ttu-id="e6a30-103">Mithilfe des Dialogfelds **Paket auswählen** können Sie das Paket angeben, von dem der Task Nachrichtenwarteschlange Nachrichten empfangen kann.</span><span class="sxs-lookup"><span data-stu-id="e6a30-103">Use the **Select a Package** dialog box to specify the package from which the Message Queue task can receive messages.</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="e6a30-104">Statische Optionen</span><span class="sxs-lookup"><span data-stu-id="e6a30-104">Static Options</span></span>  
 <span data-ttu-id="e6a30-105">**Location**</span><span class="sxs-lookup"><span data-stu-id="e6a30-105">**Location**</span></span>  
 <span data-ttu-id="e6a30-106">Geben Sie den Speicherort des Pakets an.</span><span class="sxs-lookup"><span data-stu-id="e6a30-106">Specify the location of the package.</span></span> <span data-ttu-id="e6a30-107">Diese Eigenschaft besitzt die in der folgenden Tabelle aufgeführten Optionen.</span><span class="sxs-lookup"><span data-stu-id="e6a30-107">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="e6a30-108">value</span><span class="sxs-lookup"><span data-stu-id="e6a30-108">Value</span></span>|<span data-ttu-id="e6a30-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e6a30-109">Description</span></span>|  
|-----------|-----------------|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<span data-ttu-id="e6a30-110">Legt den Speicherort als Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]fest.</span><span class="sxs-lookup"><span data-stu-id="e6a30-110">Set the location to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="e6a30-111">Wenn Sie diesen Wert auswählen, werden die dynamischen Optionen **Server**, **Windows-Authentifizierung verwenden**, **SQL Server-Authentifizierung verwenden**, **Benutzername**und **Kennwort**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e6a30-111">Selecting this value displays the dynamic options, **Server**, **Use Windows Authentication**, **Use SQL Server Authentication**, **User name**, and **Password**.</span></span>|  
|<span data-ttu-id="e6a30-112">DTSX-Datei</span><span class="sxs-lookup"><span data-stu-id="e6a30-112">DTSX file</span></span>|<span data-ttu-id="e6a30-113">Legt als Speicherort eine DTSX-Datei fest.</span><span class="sxs-lookup"><span data-stu-id="e6a30-113">Set the location to a DTSX file.</span></span> <span data-ttu-id="e6a30-114">Wenn Sie diesen Wert auswählen, wird die dynamische Option **Dateiname**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e6a30-114">Selecting this value displays the dynamic option, **File name**.</span></span>|  
  
## <a name="location-dynamic-options"></a><span data-ttu-id="e6a30-115">Dynamische Optionen für Location</span><span class="sxs-lookup"><span data-stu-id="e6a30-115">Location Dynamic Options</span></span>  
  
### <a name="location--sql-server"></a><span data-ttu-id="e6a30-116">Location = SQL Server</span><span class="sxs-lookup"><span data-stu-id="e6a30-116">Location = SQL Server</span></span>  
 <span data-ttu-id="e6a30-117">**Paketname**</span><span class="sxs-lookup"><span data-stu-id="e6a30-117">**Package name**</span></span>  
 <span data-ttu-id="e6a30-118">Wählen Sie ein Paket aus, das auf dem angegebenen Server gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="e6a30-118">Select a package that is stored on the specified server.</span></span>  
  
 <span data-ttu-id="e6a30-119">**Server**</span><span class="sxs-lookup"><span data-stu-id="e6a30-119">**Server**</span></span>  
 <span data-ttu-id="e6a30-120">Geben Sie einen Servernamen an, oder wählen Sie einen Server aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="e6a30-120">Provide a server name or select a server from the list.</span></span>  
  
 <span data-ttu-id="e6a30-121">**Windows-Authentifizierung verwenden**</span><span class="sxs-lookup"><span data-stu-id="e6a30-121">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="e6a30-122">Klicken Sie auf diese Option, wenn die Windows-Authentifizierung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e6a30-122">Click to use Windows Authentication.</span></span>  
  
 <span data-ttu-id="e6a30-123">**SQL Server-Authentifizierung verwenden**</span><span class="sxs-lookup"><span data-stu-id="e6a30-123">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="e6a30-124">Klicken Sie auf diese Option, wenn die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Authentifizierung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e6a30-124">Click to use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="e6a30-125">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="e6a30-125">**User name**</span></span>  
 <span data-ttu-id="e6a30-126">Wenn Sie die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Authentifizierung verwenden, geben Sie einen Benutzernamen an, der zur Anmeldung beim Server verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e6a30-126">If using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, provide a user name to use when logging on to the server.</span></span>  
  
 <span data-ttu-id="e6a30-127">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="e6a30-127">**Password**</span></span>  
 <span data-ttu-id="e6a30-128">Geben Sie ein Kennwort an, falls Sie die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="e6a30-128">If using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, provide a password.</span></span>  
  
### <a name="location--dtsx-file"></a><span data-ttu-id="e6a30-129">Speicherort = DTSX-Datei</span><span class="sxs-lookup"><span data-stu-id="e6a30-129">Location = DTSX file</span></span>  
 <span data-ttu-id="e6a30-130">**Dateiname**</span><span class="sxs-lookup"><span data-stu-id="e6a30-130">**File name**</span></span>  
 <span data-ttu-id="e6a30-131">Geben Sie den Pfad eines Pakets an, oder klicken Sie auf die Schaltfläche zum Durchsuchen **(…)** , um das Paket zu suchen.</span><span class="sxs-lookup"><span data-stu-id="e6a30-131">Provide the path of a package or click the browse button **(...)** and locate the package.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6a30-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e6a30-132">See Also</span></span>  
 [<span data-ttu-id="e6a30-133">Nachrichtenwarteschlange (Task)</span><span class="sxs-lookup"><span data-stu-id="e6a30-133">Message Queue Task</span></span>](message-queue-task.md)  
  
  
