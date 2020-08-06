---
title: Option „status“ (Verwaltungstool Distributed Replay) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
ms.assetid: ea89386e-1598-4412-8b37-680d14b2a5b6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6ce3d07bc357c5f3788fb6f995a43399021b3553
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695041"
---
# <a name="status-option-distributed-replay-administration-tool"></a><span data-ttu-id="76aa5-102">Option Status (Verwaltungstool Distributed Replay)</span><span class="sxs-lookup"><span data-stu-id="76aa5-102">Status Option (Distributed Replay Administration Tool)</span></span>
  <span data-ttu-id="76aa5-103">Das [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay Verwaltungs Tool, `DReplay.exe` , ist ein Befehlszeilen Tool, das Sie für die Kommunikation mit dem verteilten Replay-Controller verwenden können.</span><span class="sxs-lookup"><span data-stu-id="76aa5-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay administration tool, `DReplay.exe`, is a command-line tool that you can use to communicate with the distributed replay controller.</span></span> <span data-ttu-id="76aa5-104">In diesem Thema werden die Befehlszeilenoption **status** und die entsprechende Syntax beschrieben.</span><span class="sxs-lookup"><span data-stu-id="76aa5-104">This topic describes the **status** command-line option and corresponding syntax.</span></span>

 <span data-ttu-id="76aa5-105">Mit der **status** -Option wird der Controller abgefragt und der aktuelle Status angezeigt.</span><span class="sxs-lookup"><span data-stu-id="76aa5-105">The **status** option queries the controller and displays the current status.</span></span>

 <span data-ttu-id="76aa5-106">![Artikellinksymbol](../../database-engine/media/topic-link.gif "Symbol für Themenlink") Weitere Informationen zu den Syntaxkonventionen für das Verwaltungstool finden Sie unter [Transact-SQL-Syntaxkonventionen &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="76aa5-106">![Topic link icon](../../database-engine/media/topic-link.gif "Topic link icon") For more information about the syntax conventions that are used with the administration tool syntax, see [Transact-SQL Syntax Conventions &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span></span>

## <a name="syntax"></a><span data-ttu-id="76aa5-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="76aa5-107">Syntax</span></span>

```

dreplay status [-mcontroller] [-fstatus_interval]
```

#### <a name="parameters"></a><span data-ttu-id="76aa5-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="76aa5-108">Parameters</span></span>
 <span data-ttu-id="76aa5-109">**-m** *Controller* gibt den Computernamen des Controllers an.</span><span class="sxs-lookup"><span data-stu-id="76aa5-109">**-m** *controller* Specifies the computer name of the controller.</span></span> <span data-ttu-id="76aa5-110">Sie können mit "`localhost`" oder "`.`" auf den lokalen Computer verweisen.</span><span class="sxs-lookup"><span data-stu-id="76aa5-110">You can use "`localhost`" or "`.`" to refer to the local computer.</span></span>

 <span data-ttu-id="76aa5-111">Wenn der **-m** -Parameter nicht angegeben ist, wird der lokale Computer verwendet.</span><span class="sxs-lookup"><span data-stu-id="76aa5-111">If the **-m** parameter is not specified, the local computer is used.</span></span>

 <span data-ttu-id="76aa5-112">**-f** *status_interval* gibt die Häufigkeit (in Sekunden) an, mit der der Status angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="76aa5-112">**-f** *status_interval* Specifies the frequency (in seconds) at which to display the status.</span></span>

 <span data-ttu-id="76aa5-113">Wenn der **-f** -Parameter nicht angegeben wird, ist das Standardintervall 30 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="76aa5-113">If the **-f** parameter is not specified, the default interval is 30 seconds.</span></span>

## <a name="examples"></a><span data-ttu-id="76aa5-114">Beispiele</span><span class="sxs-lookup"><span data-stu-id="76aa5-114">Examples</span></span>
 <span data-ttu-id="76aa5-115">Im folgenden Beispiel wird der aktuelle Status alle 60 Sekunden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="76aa5-115">In the following example, the current status is displayed every 60 seconds.</span></span> <span data-ttu-id="76aa5-116">Der Wert `localhost` gibt an, dass der Controllerdienst auf demselben Computer wie das Verwaltungstool ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="76aa5-116">The value `localhost` indicates that the controller service is running on the same computer as the administration tool.</span></span>

```
dreplay status -m localhost -f 60
```

## <a name="permissions"></a><span data-ttu-id="76aa5-117">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="76aa5-117">Permissions</span></span>
 <span data-ttu-id="76aa5-118">Sie müssen das Verwaltungstool als interaktiver Benutzer mit einem lokalen Benutzerkonto oder Domänenbenutzerkonto ausführen.</span><span class="sxs-lookup"><span data-stu-id="76aa5-118">You must run the administration tool as an interactive user, as either a local user or a domain user account.</span></span> <span data-ttu-id="76aa5-119">Um ein lokales Benutzerkonto zu verwenden, müssen das Verwaltungstool und der Controller auf demselben Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="76aa5-119">To use a local user account, the administration tool and controller must be running on the same computer.</span></span>

 <span data-ttu-id="76aa5-120">Weitere Informationen finden Sie unter [Distributed Replay Security](distributed-replay-security.md).</span><span class="sxs-lookup"><span data-stu-id="76aa5-120">For more information, see [Distributed Replay Security](distributed-replay-security.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="76aa5-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="76aa5-121">See Also</span></span>
 <span data-ttu-id="76aa5-122">[SQL Server Distributed Replay](sql-server-distributed-replay.md) [Transact-SQL-Debugger](../../relational-databases/scripting/transact-sql-debugger.md)</span><span class="sxs-lookup"><span data-stu-id="76aa5-122">[SQL Server Distributed Replay](sql-server-distributed-replay.md) [Transact-SQL Debugger](../../relational-databases/scripting/transact-sql-debugger.md)</span></span>


