---
title: Installieren von Upgrade Advisor von der Eingabeaufforderung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- installing Upgrade Advisor
- command prompt [Upgrade Advisor]
- Setup [Upgrade Advisor]
- Upgrade Advisor [SQL Server], installing
ms.assetid: a6841cc2-ca13-4b1c-9343-9e4d54312c3a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b0c5193f0b235b6d37170992d9d7ca9568b1f675
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697405"
---
# <a name="installing-upgrade-advisor-from-the-command-prompt"></a><span data-ttu-id="4a0b3-102">Installieren des Upgrade Advisors von der Eingabeaufforderung aus</span><span class="sxs-lookup"><span data-stu-id="4a0b3-102">Installing Upgrade Advisor from the Command Prompt</span></span>
  <span data-ttu-id="4a0b3-103">Sie können den Upgrade Advisor entweder mithilfe des Setup-Assistenten oder an der Eingabeaufforderung installieren.</span><span class="sxs-lookup"><span data-stu-id="4a0b3-103">You can install Upgrade Advisor either by using the Setup Wizard or from the command prompt.</span></span> <span data-ttu-id="4a0b3-104">Die Eingabeaufforderung ermöglicht unbeaufsichtigte und automatisierte Installationen.</span><span class="sxs-lookup"><span data-stu-id="4a0b3-104">By using the command prompt you can perform unattended and automated installations.</span></span>  
  
## <a name="installation-syntax"></a><span data-ttu-id="4a0b3-105">Installationssyntax</span><span class="sxs-lookup"><span data-stu-id="4a0b3-105">Installation Syntax</span></span>  
 <span data-ttu-id="4a0b3-106">Die grundlegende Syntax für die Upgrade Advisor-Installation von der Eingabeaufforderung ist folgende:</span><span class="sxs-lookup"><span data-stu-id="4a0b3-106">The basic syntax for installing Upgrade Advisor from the command prompt is as follows:</span></span>  
  
 `SQLUA.msi [options]`  
  
 <span data-ttu-id="4a0b3-107">In der folgenden Tabelle werden die gängigsten Optionen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="4a0b3-107">The following table shows the most common options.</span></span>  
  
|<span data-ttu-id="4a0b3-108">Argument</span><span class="sxs-lookup"><span data-stu-id="4a0b3-108">Argument</span></span>|<span data-ttu-id="4a0b3-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4a0b3-109">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="4a0b3-110">/q [n&#124;b&#124;r&#124;f]</span><span class="sxs-lookup"><span data-stu-id="4a0b3-110">/q[n&#124;b&#124;r&#124;f]</span></span>|<span data-ttu-id="4a0b3-111">Legt die Benutzeroberflächenebene fest:</span><span class="sxs-lookup"><span data-stu-id="4a0b3-111">Sets user interface (UI) level:</span></span><br /><br /> <span data-ttu-id="4a0b3-112">n = keine Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="4a0b3-112">n = no UI</span></span><br /><br /> <span data-ttu-id="4a0b3-113">b = grundlegende Benutzeroberfläche (nur Status, keine Eingabeaufforderungen)</span><span class="sxs-lookup"><span data-stu-id="4a0b3-113">b = basic UI (progress only, no prompts)</span></span><br /><br /> <span data-ttu-id="4a0b3-114">r = reduzierte Benutzeroberfläche (Dialogfeld am Ende der Installation)</span><span class="sxs-lookup"><span data-stu-id="4a0b3-114">r = reduced UI (dialog box at the end of installation)</span></span><br /><br /> <span data-ttu-id="4a0b3-115">f = Vollständige Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="4a0b3-115">f = full UI</span></span>|  
|<span data-ttu-id="4a0b3-116">/L</span><span class="sxs-lookup"><span data-stu-id="4a0b3-116">/L</span></span>|<span data-ttu-id="4a0b3-117">Gibt Protokolldateioptionen an.</span><span class="sxs-lookup"><span data-stu-id="4a0b3-117">Specifies log file options.</span></span> <span data-ttu-id="4a0b3-118">Um alle Nachrichten in *log_file_name*zu protokollieren, verwenden Sie **-L \* v**_log_file_name_.</span><span class="sxs-lookup"><span data-stu-id="4a0b3-118">To log all messages to *log_file_name*, use **-L\*v**_log_file_name_.</span></span> <span data-ttu-id="4a0b3-119">Verwenden Sie log_file_name, um nur Fehlermeldungen zu protokollieren `-Le` *log_file_name*.</span><span class="sxs-lookup"><span data-stu-id="4a0b3-119">To log error messages only, use `-Le`*log_file_name*.</span></span>|  
|<span data-ttu-id="4a0b3-120">ADDLOCAL = alle&#124; Remove = alle&#124;REINSTALL = ALL</span><span class="sxs-lookup"><span data-stu-id="4a0b3-120">ADDLOCAL=ALL&#124; REMOVE=ALL&#124;REINSTALL=ALL</span></span>|<span data-ttu-id="4a0b3-121">Gibt an, dass der Upgrade Advisor installiert (ADDLOCAL), entfernt (REMOVE) oder neu installiert (REINSTALL) wird.</span><span class="sxs-lookup"><span data-stu-id="4a0b3-121">Specifies to install (ADDLOCAL), remove (REMOVE), or reinstall (REINSTALL) Upgrade Advisor.</span></span>|  
|<span data-ttu-id="4a0b3-122">UAINSTALLDIR=path</span><span class="sxs-lookup"><span data-stu-id="4a0b3-122">UAINSTALLDIR=path</span></span>|<span data-ttu-id="4a0b3-123">Installiert den Upgrade Advisor am von "path" angegebenen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="4a0b3-123">Installs Upgrade Advisor to the location specified by path.</span></span>|  
  
## <a name="installation-examples"></a><span data-ttu-id="4a0b3-124">Installationsbeispiele</span><span class="sxs-lookup"><span data-stu-id="4a0b3-124">Installation Examples</span></span>  
 <span data-ttu-id="4a0b3-125">Im folgenden Beispiel wird gezeigt, wie der Upgrade Advisor mithilfe der Eingabeaufforderung installiert wird:</span><span class="sxs-lookup"><span data-stu-id="4a0b3-125">The following example shows how to install Upgrade Advisor by using the command prompt:</span></span>  
  
```  
SQLUA.msi /qn ADDLOCAL=ALL UAINSTALLDIR="C:\Upgrade Advisor"  
```  
  
 <span data-ttu-id="4a0b3-126">Sie können auch das Programm Msiexec verwenden, wenn Sie diesen Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="4a0b3-126">You can also use the Msiexec program when you run this command:</span></span>  
  
```  
Msiexec.exe /i C:\Downloads\SQLUA.msi /qn ADDLOCAL=ALL UAINSTALLDIR="C:\Upgrade Advisor"  
```  
  
 <span data-ttu-id="4a0b3-127">Dies kann hilfreich sein, wenn Sie zusätzliche Installationsoptionen verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="4a0b3-127">This can be helpful if you have to use additional installation options.</span></span>  
  
## <a name="removal-examples"></a><span data-ttu-id="4a0b3-128">Beispiele für das Entfernen von Upgrade Advisor</span><span class="sxs-lookup"><span data-stu-id="4a0b3-128">Removal Examples</span></span>  
 <span data-ttu-id="4a0b3-129">Im folgenden Beispiel wird gezeigt, wie der Upgrade Advisor mithilfe der Eingabeaufforderung entfernt wird:</span><span class="sxs-lookup"><span data-stu-id="4a0b3-129">The following example shows how to remove Upgrade Advisor by using the command prompt:</span></span>  
  
```  
SQLUA.msi /qn REMOVE=ALL  
```  
  
 <span data-ttu-id="4a0b3-130">Sie können auch das Programm Msiexec verwenden, wenn Sie diesen Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="4a0b3-130">You can also use the Msiexec program when you run this command:</span></span>  
  
```  
Msiexec.exe /i C:\Downloads\SQLUA.msi /qn REMOVE=ALL  
```  
  
## <a name="see-also"></a><span data-ttu-id="4a0b3-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4a0b3-131">See Also</span></span>  
 <span data-ttu-id="4a0b3-132">[Installieren von Upgrade Advisor](../../../2014/sql-server/install/installing-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="4a0b3-132">[Installing Upgrade Advisor](../../../2014/sql-server/install/installing-upgrade-advisor.md) </span></span>  
 [<span data-ttu-id="4a0b3-133">Voraussetzungen für den Upgrade Advisor</span><span class="sxs-lookup"><span data-stu-id="4a0b3-133">Upgrade Advisor Prerequisites</span></span>](../../../2014/sql-server/install/upgrade-advisor-prerequisites.md)  
  
  
