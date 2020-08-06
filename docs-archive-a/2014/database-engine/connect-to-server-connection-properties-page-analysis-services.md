---
title: Herstellen einer Verbindung mit SQL Server Analysis Services (Eigenschaftenseite Verbindung) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.connecttoas.connectionproperties.f1
ms.assetid: 26cf53e3-3bcb-4697-8a88-53e93bc68b56
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 04706671ea8b0a50f2bf72cd7b73db88dce34d89
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694698"
---
# <a name="connect-to-server-connection-properties-page-analysis-services"></a><span data-ttu-id="ff099-102">Verbinden mit SQL Server Analysis Services (Eigenschaftenseite Verbindung)</span><span class="sxs-lookup"><span data-stu-id="ff099-102">Connect to Server (Connection Properties Page) Analysis Services</span></span>
  <span data-ttu-id="ff099-103">Auf dieser Registerkarte können Sie Optionen anzeigen und angeben, wenn Sie eine Verbindung mit [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] herstellen oder [!INCLUDE[ssAS](../includes/ssas-md.md)] in **Registrierte Server**registrieren.</span><span class="sxs-lookup"><span data-stu-id="ff099-103">Use this tab to view or specify options when connecting to [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] or registering [!INCLUDE[ssAS](../includes/ssas-md.md)] in **Registered Servers**.</span></span> <span data-ttu-id="ff099-104">Die Felder**Verbinden** und **Optionen** werden nur beim Herstellen einer Verbindung in diesem Dialogfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ff099-104">**Connect** and **Options** only appear in this dialog box when connecting.</span></span> <span data-ttu-id="ff099-105">Die Felder**Testen** und **Speichern** werden nur beim Registrieren von [!INCLUDE[ssAS](../includes/ssas-md.md)]in diesem Dialogfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ff099-105">**Test** and **Save** only appear in this dialog box when registering [!INCLUDE[ssAS](../includes/ssas-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="ff099-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="ff099-106">Options</span></span>  
 <span data-ttu-id="ff099-107">**Herstellen einer Verbindung mit der Datenbank**</span><span class="sxs-lookup"><span data-stu-id="ff099-107">**Connect to database**</span></span>  
 <span data-ttu-id="ff099-108">Wählen Sie eine Datenbank aus der Liste aus, zu der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ff099-108">Select a database to connect to from the list.</span></span> <span data-ttu-id="ff099-109">Wenn Sie auswählen **\<default>** , wird eine Verbindung mit der Standarddatenbank für den Server hergestellt.</span><span class="sxs-lookup"><span data-stu-id="ff099-109">If you select **\<default>**, you will be connected to the default database for the server.</span></span> <span data-ttu-id="ff099-110">Wenn Sie auswählen **\<Browse server>** , können Sie den Server nach der Datenbank durchsuchen, mit der Sie eine Verbindung herstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="ff099-110">If you select **\<Browse server>**, you can browse the server for the database you would like to connect to.</span></span>  
  
 <span data-ttu-id="ff099-111">**Verbindungs Timeout**</span><span class="sxs-lookup"><span data-stu-id="ff099-111">**Connection timeout**</span></span>  
 <span data-ttu-id="ff099-112">Geben Sie die Anzahl der Sekunden ein, die auf das Herstellen einer Verbindung gewartet werden soll, bevor ein Timeout eintritt. Der Standardwert ist 15 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="ff099-112">Enter the number of seconds to wait for a connection to be established before timing out. The default value is 15 seconds.</span></span>  
  
 <span data-ttu-id="ff099-113">**Ausführungstimeout**</span><span class="sxs-lookup"><span data-stu-id="ff099-113">**Execution timeout**</span></span>  
 <span data-ttu-id="ff099-114">Geben Sie an, wie lange (in Sekunden) auf den Abschluss eines Tasks auf dem Server gewartet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ff099-114">Enter the amount of time in seconds to wait before execution of a task is completed on the server.</span></span> <span data-ttu-id="ff099-115">Der Standardwert beträgt null Sekunden, d. h. es wird kein Timeout verwendet.</span><span class="sxs-lookup"><span data-stu-id="ff099-115">The default value is zero seconds, which indicates there is no time-out.</span></span>  
  
 <span data-ttu-id="ff099-116">**Verbindung verschlüsseln**</span><span class="sxs-lookup"><span data-stu-id="ff099-116">**Encrypt connection**</span></span>  
 <span data-ttu-id="ff099-117">Erzwingt die Verschlüsselung der Verbindung.</span><span class="sxs-lookup"><span data-stu-id="ff099-117">Forces encryption of the connection.</span></span>  
  
 <span data-ttu-id="ff099-118">**Alles zurücksetzen**</span><span class="sxs-lookup"><span data-stu-id="ff099-118">**Reset All**</span></span>  
 <span data-ttu-id="ff099-119">Ersetzt alle manuell eingegebenen Verbindungseigenschaftswerte durch die Standardwerte.</span><span class="sxs-lookup"><span data-stu-id="ff099-119">Replace all manually entered connection property values with the default values.</span></span>  
  
 <span data-ttu-id="ff099-120">**Herstellen einer Verbindung**</span><span class="sxs-lookup"><span data-stu-id="ff099-120">**Connect**</span></span>  
 <span data-ttu-id="ff099-121">Versucht, mithilfe der aufgelisteten Werte eine Verbindung herzustellen.</span><span class="sxs-lookup"><span data-stu-id="ff099-121">Attempt a connection using the listed values.</span></span>  
  
 <span data-ttu-id="ff099-122">**Optionen**</span><span class="sxs-lookup"><span data-stu-id="ff099-122">**Options**</span></span>  
 <span data-ttu-id="ff099-123">Klicken Sie hier, um die Anzeige des Dialogfelds zu ändern und die zusätzlichen Serververbindungsoptionen, z. B. Speichern des Kennworts, auszublenden.</span><span class="sxs-lookup"><span data-stu-id="ff099-123">Click to change the dialog and hide the additional server connection options, such as remembering the password.</span></span>  
  
 <span data-ttu-id="ff099-124">**Test**</span><span class="sxs-lookup"><span data-stu-id="ff099-124">**Test**</span></span>  
 <span data-ttu-id="ff099-125">Klicken Sie hier, um beim Registrieren von [!INCLUDE[ssAS](../includes/ssas-md.md)] in **Registrierte Server**die Verbindung zu testen.</span><span class="sxs-lookup"><span data-stu-id="ff099-125">When registering [!INCLUDE[ssAS](../includes/ssas-md.md)] in **Registered Servers**, click to test the connection.</span></span>  
  
 <span data-ttu-id="ff099-126">**Speichern**</span><span class="sxs-lookup"><span data-stu-id="ff099-126">**Save**</span></span>  
 <span data-ttu-id="ff099-127">Speichert die Einstellungen in **Registrierte Server**.</span><span class="sxs-lookup"><span data-stu-id="ff099-127">Saves the settings in **Registered Servers**.</span></span>  
  
  
