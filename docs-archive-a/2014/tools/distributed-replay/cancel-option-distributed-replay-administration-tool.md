---
title: Option „cancel“ (Verwaltungstool Distributed Replay) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
ms.assetid: fea376de-307a-4b45-b7e2-37df88f3681a
author: stevestein
ms.author: sstein
ms.openlocfilehash: d132fbf5ce541a2bdab82e44dc55e6fc92df536d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618957"
---
# <a name="cancel-option-distributed-replay-administration-tool"></a><span data-ttu-id="15e22-102">Option Abbrechen (Verwaltungstool Distributed Replay)</span><span class="sxs-lookup"><span data-stu-id="15e22-102">Cancel Option (Distributed Replay Administration Tool)</span></span>
  <span data-ttu-id="15e22-103">Das [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay Verwaltungs Tool, `DReplay.exe` , ist ein Befehlszeilen Tool, das Sie für die Kommunikation mit dem verteilten Replay-Controller verwenden können.</span><span class="sxs-lookup"><span data-stu-id="15e22-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay administration tool, `DReplay.exe`, is a command-line tool that you can use to communicate with the distributed replay controller.</span></span> <span data-ttu-id="15e22-104">In diesem Thema werden die **cancel** -Befehlszeilenoption und die entsprechende Syntax beschrieben.</span><span class="sxs-lookup"><span data-stu-id="15e22-104">This topic describes the **cancel** command-line option and corresponding syntax.</span></span>

 <span data-ttu-id="15e22-105">Die **cancel** -Option bricht den aktuellen Vorgang ab, der auf dem Controller ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="15e22-105">The **cancel** option cancels the current operation that is running on the controller.</span></span>

 <span data-ttu-id="15e22-106">![Artikellinksymbol](../../database-engine/media/topic-link.gif "Symbol für Themenlink") Weitere Informationen zu den Syntaxkonventionen für das Verwaltungstool finden Sie unter [Transact-SQL-Syntaxkonventionen &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="15e22-106">![Topic link icon](../../database-engine/media/topic-link.gif "Topic link icon") For more information about the syntax conventions that are used with the administration tool syntax, see [Transact-SQL Syntax Conventions &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span></span>

## <a name="syntax"></a><span data-ttu-id="15e22-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="15e22-107">Syntax</span></span>

```

dreplay cancel [-mcontroller] [-q] 
```

#### <a name="parameters"></a><span data-ttu-id="15e22-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="15e22-108">Parameters</span></span>
 <span data-ttu-id="15e22-109">**-m** *Controller* der Computername des Controllers.</span><span class="sxs-lookup"><span data-stu-id="15e22-109">**-m** *controller* The computer name of the controller.</span></span> <span data-ttu-id="15e22-110">Sie können mit "`localhost`" oder "`.`" auf den lokalen Computer verweisen.</span><span class="sxs-lookup"><span data-stu-id="15e22-110">You can use "`localhost`" or "`.`" to refer to the local computer.</span></span>

 <span data-ttu-id="15e22-111">Wenn der **-m** -Parameter nicht angegeben ist, wird der lokale Computer verwendet.</span><span class="sxs-lookup"><span data-stu-id="15e22-111">If the **-m** parameter is not specified, the local computer is used.</span></span>

 <span data-ttu-id="15e22-112">**-q** Stiller Modus.</span><span class="sxs-lookup"><span data-stu-id="15e22-112">**-q** Quiet mode.</span></span> <span data-ttu-id="15e22-113">Fordert nicht zur Bestätigung auf.</span><span class="sxs-lookup"><span data-stu-id="15e22-113">Does not prompt for confirmation.</span></span>

 <span data-ttu-id="15e22-114">Der **-q** -Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="15e22-114">The **-q** parameter is optional.</span></span>

## <a name="examples"></a><span data-ttu-id="15e22-115">Beispiele</span><span class="sxs-lookup"><span data-stu-id="15e22-115">Examples</span></span>
 <span data-ttu-id="15e22-116">Im folgenden Beispiel wird eine Abbruchanforderung im stillen Modus gesendet.</span><span class="sxs-lookup"><span data-stu-id="15e22-116">In the following example, a cancel request is submitted in quiet mode.</span></span> <span data-ttu-id="15e22-117">Der Wert `localhost` gibt an, dass der Controllerdienst auf demselben Computer wie das Verwaltungstool ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="15e22-117">The value `localhost` indicates that the controller service is running on the same computer as the administration tool.</span></span>

```
dreplay cancel -m localhost -q
```

## <a name="permissions"></a><span data-ttu-id="15e22-118">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="15e22-118">Permissions</span></span>
 <span data-ttu-id="15e22-119">Sie müssen das Verwaltungstool als interaktiver Benutzer mit einem lokalen Benutzerkonto oder Domänenbenutzerkonto ausführen.</span><span class="sxs-lookup"><span data-stu-id="15e22-119">You must run the administration tool as an interactive user, as either a local user or a domain user account.</span></span> <span data-ttu-id="15e22-120">Um ein lokales Benutzerkonto zu verwenden, müssen das Verwaltungstool und der Controller auf demselben Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="15e22-120">To use a local user account, the administration tool and controller must be running on the same computer.</span></span>

 <span data-ttu-id="15e22-121">Weitere Informationen finden Sie unter [Distributed Replay Security](distributed-replay-security.md).</span><span class="sxs-lookup"><span data-stu-id="15e22-121">For more information, see [Distributed Replay Security](distributed-replay-security.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="15e22-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="15e22-122">See Also</span></span>
 [<span data-ttu-id="15e22-123">SQL Server Distributed Replay</span><span class="sxs-lookup"><span data-stu-id="15e22-123">SQL Server Distributed Replay</span></span>](sql-server-distributed-replay.md)


