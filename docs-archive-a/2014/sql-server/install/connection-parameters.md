---
title: Verbindungsparameter | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Upgrade Advisor [SQL Server], connections
- authentication [Upgrade Advisor]
- SQL Server Upgrade Advisor, connections
- connections [Upgrade Advisor]
- server instances [Upgrade Advisor]
- default server instances
- analyzing system [Upgrade Advisor], connections
ms.assetid: f754d038-637a-4d8e-85b0-b242e6499d26
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 27eb69dfd2c41710a47861e0992486267f692a3a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615783"
---
# <a name="connection-parameters"></a><span data-ttu-id="dd463-102">Verbindungsparameter</span><span class="sxs-lookup"><span data-stu-id="dd463-102">Connection Parameters</span></span>
  <span data-ttu-id="dd463-103">Um bestimmte Servertypen, z. B. [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], zu analysieren, müssen Sie eine bestimmte Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] auswählen.</span><span class="sxs-lookup"><span data-stu-id="dd463-103">To analyze certain server types, such as the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], you must select a specific instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="dd463-104">Die Standardinstanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] wird automatisch ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="dd463-104">The default instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is automatically selected.</span></span> <span data-ttu-id="dd463-105">Sie können diese Auswahl ändern, aber Sie können jeweils nur eine Instanz für die Analyse durch den Upgrade Advisor auswählen.</span><span class="sxs-lookup"><span data-stu-id="dd463-105">You can change this selection, but you can select only one instance at a time for analysis by Upgrade Advisor.</span></span> <span data-ttu-id="dd463-106">Wenn Sie einen Servertyp aufgenommen haben, der eine Authentifizierung erfordert, müssen Sie den Authentifizierungsmodus und die Anmeldeinformationen eingeben.</span><span class="sxs-lookup"><span data-stu-id="dd463-106">If you have included a server type that requires authentication, you must enter the authentication mode and credentials.</span></span>  
  
## <a name="options"></a><span data-ttu-id="dd463-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="dd463-107">Options</span></span>  
 <span data-ttu-id="dd463-108">**Servername**</span><span class="sxs-lookup"><span data-stu-id="dd463-108">**Server name**</span></span>  
 <span data-ttu-id="dd463-109">Ist mit dem Computernamen vorab aufgefüllt, den Sie im Bereich mit den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Komponenten eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="dd463-109">Pre-populated with the computer name that you entered in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Components pane.</span></span>  
  
 <span data-ttu-id="dd463-110">**Instanzname**</span><span class="sxs-lookup"><span data-stu-id="dd463-110">**Instance name**</span></span>  
 <span data-ttu-id="dd463-111">Wählen Sie eine Instanz aus den Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] aus, die auf dem Computer verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="dd463-111">Select from the instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are available on the computer.</span></span> <span data-ttu-id="dd463-112">Wenn eine Liste von Instanzen nicht angezeigt wird, verwenden Sie MSSQLSERVER, um die Standard Instanz zu scannen.</span><span class="sxs-lookup"><span data-stu-id="dd463-112">If you do not see a list of instances, use MSSQLSERVER to scan the default instance.</span></span> <span data-ttu-id="dd463-113">Dies ist für Remotecomputer besonders wichtig.</span><span class="sxs-lookup"><span data-stu-id="dd463-113">This is especially relevant for remote computers.</span></span> <span data-ttu-id="dd463-114">Sie können auch das Wort "default" verwenden, um die Standardinstanz zu scannen.</span><span class="sxs-lookup"><span data-stu-id="dd463-114">You can also use the word "default" to scan the default instance.</span></span>  
  
 <span data-ttu-id="dd463-115">**Authentifizierung**</span><span class="sxs-lookup"><span data-stu-id="dd463-115">**Authentication**</span></span>  
 <span data-ttu-id="dd463-116">Wählen Sie auf diesem Computer einen Eintrag aus der Liste der verfügbaren Authentifizierungsmodi aus.</span><span class="sxs-lookup"><span data-stu-id="dd463-116">Select from the list of available authentication modes on this computer.</span></span> <span data-ttu-id="dd463-117">Die Windows-Authentifizierung ist der Standardauthentifizierungsmodus.</span><span class="sxs-lookup"><span data-stu-id="dd463-117">By default, the authentication mode is Windows Authentication.</span></span>  
  
 <span data-ttu-id="dd463-118">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="dd463-118">**User name**</span></span>  
 <span data-ttu-id="dd463-119">Wenn Sie die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Authentifizierung verwenden, geben Sie einen Benutzernamen in das Feld ein.</span><span class="sxs-lookup"><span data-stu-id="dd463-119">If using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, enter a user name in the box.</span></span> <span data-ttu-id="dd463-120">Es wird empfohlen, einen Benutzernamen einzugeben, der auf dem Computer Administratorrechte hat.</span><span class="sxs-lookup"><span data-stu-id="dd463-120">We recommend that the user name have administrative credentials on the computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dd463-121">Wenn Sie die Windows-Authentifizierung auswählen, wird der Benutzername des aktuell angemeldeten Benutzers in das Textfeld **Benutzername** eingetragen.</span><span class="sxs-lookup"><span data-stu-id="dd463-121">If you select Windows Authentication, the user name of the currently logged-on user is populated in the **User name** text box.</span></span>  
  
 <span data-ttu-id="dd463-122">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="dd463-122">**Password**</span></span>  
 <span data-ttu-id="dd463-123">Geben Sie das Kennwort für den angegebenen Benutzer ein.</span><span class="sxs-lookup"><span data-stu-id="dd463-123">Enter the password for the specified user.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd463-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dd463-124">See Also</span></span>  
 <span data-ttu-id="dd463-125">[Arbeiten mit Upgrade Advisor](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="dd463-125">[Working with Upgrade Advisor](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span></span>  
 [<span data-ttu-id="dd463-126">Benutzeroberflächenreferenz des Upgrade Advisors</span><span class="sxs-lookup"><span data-stu-id="dd463-126">Upgrade Advisor User Interface Reference</span></span>](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md)  
  
  
