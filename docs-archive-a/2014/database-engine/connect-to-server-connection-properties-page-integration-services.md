---
title: Verbindung mit Server herstellen (Seite ' Verbindungs Eigenschaften ') Integration Services | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.connecttodts.connectionproperties.f1
- sql12.ssiseditserverregistration.connectionproperties.f1
ms.assetid: c2513dab-8415-4e0c-9475-6d4ab97fea7c
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 05f3d370a3f3a299bb90df53538b3fa3e90e28c4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724146"
---
# <a name="connect-to-server-connection-properties-page-integration-services"></a><span data-ttu-id="30faf-102">Verbinden mit SQL Server Integration Services (Eigenschaftenseite Verbindung)</span><span class="sxs-lookup"><span data-stu-id="30faf-102">Connect to Server (Connection Properties Page) Integration Services</span></span>
  <span data-ttu-id="30faf-103">Auf dieser Registerkarte können Sie Optionen anzeigen und angeben, wenn Sie eine Verbindung mit [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] herstellen oder [!INCLUDE[ssIS](../includes/ssis-md.md)] in **Registrierte Server**registrieren.</span><span class="sxs-lookup"><span data-stu-id="30faf-103">Use this tab to view or specify options when connecting to [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] or registering [!INCLUDE[ssIS](../includes/ssis-md.md)] in **Registered Servers**.</span></span> <span data-ttu-id="30faf-104">Die Felder**Verbinden** und **Optionen** werden nur beim Herstellen einer Verbindung in diesem Dialogfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="30faf-104">**Connect** and **Options** only appear in this dialog box when connecting.</span></span> <span data-ttu-id="30faf-105">Die Felder**Testen** und **Speichern** werden nur beim Registrieren von [!INCLUDE[ssIS](../includes/ssis-md.md)]in diesem Dialogfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="30faf-105">**Test** and **Save** only appear in this dialog box when registering [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="30faf-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="30faf-106">Options</span></span>  
 <span data-ttu-id="30faf-107">**Portnummer**</span><span class="sxs-lookup"><span data-stu-id="30faf-107">**Port number**</span></span>  
 <span data-ttu-id="30faf-108">Geben Sie die Nummer des von [!INCLUDE[ssIS](../includes/ssis-md.md)]verwendeten Ports ein.</span><span class="sxs-lookup"><span data-stu-id="30faf-108">Enter the port number used by [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span>  
  
 <span data-ttu-id="30faf-109">**Verbindungs Timeout**</span><span class="sxs-lookup"><span data-stu-id="30faf-109">**Connection time-out**</span></span>  
 <span data-ttu-id="30faf-110">Geben Sie die Anzahl der Sekunden ein, die auf das Herstellen einer Verbindung gewartet werden soll, bevor ein Timeout eintritt. Der Standardwert ist 15 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="30faf-110">Enter the number of seconds to wait for a connection to be established before timing out. The default value is 15 seconds.</span></span>  
  
 <span data-ttu-id="30faf-111">**Ausführungs Timeout**</span><span class="sxs-lookup"><span data-stu-id="30faf-111">**Execution time-out**</span></span>  
 <span data-ttu-id="30faf-112">Geben Sie an, wie lange (in Sekunden) auf den Abschluss eines Tasks auf dem Server gewartet werden soll.</span><span class="sxs-lookup"><span data-stu-id="30faf-112">Enter the amount of time in seconds to wait before execution of a task is completed on the server.</span></span> <span data-ttu-id="30faf-113">Der Standardwert beträgt null Sekunden, d. h. es wird kein Timeout verwendet.</span><span class="sxs-lookup"><span data-stu-id="30faf-113">The default value is zero seconds, which indicates there is no time-out.</span></span>  
  
 <span data-ttu-id="30faf-114">**Alles zurücksetzen**</span><span class="sxs-lookup"><span data-stu-id="30faf-114">**Reset All**</span></span>  
 <span data-ttu-id="30faf-115">Ersetzt alle manuell eingegebenen Verbindungseigenschaftswerte durch die Standardwerte.</span><span class="sxs-lookup"><span data-stu-id="30faf-115">Replace all manually entered connection property values with the default values.</span></span>  
  
 <span data-ttu-id="30faf-116">**Herstellen einer Verbindung**</span><span class="sxs-lookup"><span data-stu-id="30faf-116">**Connect**</span></span>  
 <span data-ttu-id="30faf-117">Versucht, mithilfe der aufgelisteten Werte eine Verbindung herzustellen.</span><span class="sxs-lookup"><span data-stu-id="30faf-117">Attempt a connection using the listed values.</span></span>  
  
 <span data-ttu-id="30faf-118">**Optionen**</span><span class="sxs-lookup"><span data-stu-id="30faf-118">**Options**</span></span>  
 <span data-ttu-id="30faf-119">Klicken Sie hier, um die Anzeige des Dialogfelds zu ändern und die zusätzlichen Serververbindungsoptionen, z. B. Speichern des Kennworts, auszublenden.</span><span class="sxs-lookup"><span data-stu-id="30faf-119">Click to change the dialog and hide the additional server connection options, such as remembering the password.</span></span>  
  
 <span data-ttu-id="30faf-120">**Test**</span><span class="sxs-lookup"><span data-stu-id="30faf-120">**Test**</span></span>  
 <span data-ttu-id="30faf-121">Klicken Sie hier, um beim Registrieren von [!INCLUDE[ssIS](../includes/ssis-md.md)] in **Registrierte Server**die Verbindung zu testen.</span><span class="sxs-lookup"><span data-stu-id="30faf-121">When registering [!INCLUDE[ssIS](../includes/ssis-md.md)] in **Registered Servers**, click to test the connection.</span></span>  
  
 <span data-ttu-id="30faf-122">**Speichern**</span><span class="sxs-lookup"><span data-stu-id="30faf-122">**Save**</span></span>  
 <span data-ttu-id="30faf-123">Speichert die Einstellungen in **Registrierte Server**.</span><span class="sxs-lookup"><span data-stu-id="30faf-123">Saves the settings in **Registered Servers**.</span></span>  
  
  
