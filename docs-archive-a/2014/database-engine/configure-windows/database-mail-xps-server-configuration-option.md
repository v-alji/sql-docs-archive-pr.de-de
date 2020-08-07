---
title: Database Mail XPs (Serverkonfigurationsoption) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- Database Mail XPs option
- Database Mail [SQL Server], enabling
ms.assetid: e22c4e63-1792-473b-af11-14a7931ca9ed
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 33ee15e862e0992f39373ec30275040c4fcacc0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619319"
---
# <a name="database-mail-xps-server-configuration-option"></a><span data-ttu-id="8f324-102">Database Mail XPs (Serverkonfigurationsoption)</span><span class="sxs-lookup"><span data-stu-id="8f324-102">Database Mail XPs Server Configuration Option</span></span>
  <span data-ttu-id="8f324-103">Verwenden Sie die Option **DatabaseMail XPs** , um Datenbank-E-Mail auf diesem Server zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="8f324-103">Use the **DatabaseMail XPs** option to enable Database Mail on this server.</span></span> <span data-ttu-id="8f324-104">Mögliche Werte:</span><span class="sxs-lookup"><span data-stu-id="8f324-104">The possible values are:</span></span>  
  
-   <span data-ttu-id="8f324-105">**0** gibt an, dass Datenbank-E-Mail nicht verfügbar ist (Standard).</span><span class="sxs-lookup"><span data-stu-id="8f324-105">**0** indicating Database Mail is not available (default).</span></span>  
  
-   <span data-ttu-id="8f324-106">**1** gibt an, dass Datenbank-E-Mail verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="8f324-106">**1** indicating Database Mail is available.</span></span>  
  
 <span data-ttu-id="8f324-107">Die Einstellung tritt ohne Beenden und Neustarten des Servers sofort in Kraft.</span><span class="sxs-lookup"><span data-stu-id="8f324-107">The setting takes effect immediately without a server stop and restart.</span></span>  
  
 <span data-ttu-id="8f324-108">Nachdem Sie Datenbank-E-Mail aktiviert haben, müssen Sie zum Verwenden von Datenbank-E-Mail eine Hostdatenbank für Datenbank-E-Mail konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="8f324-108">After enabling Database Mail, you must configure a Database Mail host database to use Database Mail.</span></span>  
  
 <span data-ttu-id="8f324-109">Durch das Konfigurieren von Datenbank-E-Mail mithilfe des **Assistenten zum Konfigurieren von Datenbank-E-Mail** werden die erweiterten gespeicherten Prozeduren von Datenbank-E-Mail in der **msdb** -Datenbank aktiviert.</span><span class="sxs-lookup"><span data-stu-id="8f324-109">Configuring Database Mail using the **Database Mail Configuration Wizard** enables the Database Mail extended stored procedures in the **msdb** database.</span></span> <span data-ttu-id="8f324-110">Wenn Sie den **Assistenten zum Konfigurieren von Datenbank-E-Mail**verwenden, müssen Sie das unten angeführte **sp_configure** -Beispiel nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="8f324-110">If you use the **Database Mail Configuration Wizard**, you do not have to use the **sp_configure** example below.</span></span>  
  
 <span data-ttu-id="8f324-111">Das festlegen der Option **Database Mail XPs** auf 0 verhindert das Starten von Datenbank-E-Mail.</span><span class="sxs-lookup"><span data-stu-id="8f324-111">Setting the **Database Mail XPs** option to 0 prevents Database Mail from starting.</span></span> <span data-ttu-id="8f324-112">Wird Datenbank-E-Mail mit dem Wert 0 ausgeführt, wird die Ausführung und das Senden von E-Mails bis zur in der Option **DatabaseMailExeMinimumLifeTime** konfigurierten Leerlaufzeit fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="8f324-112">If it is running when the option is set to 0, it continues to run and send mail until it is idle for the time configured in the **DatabaseMailExeMinimumLifeTime** option.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="8f324-113">Beispiele</span><span class="sxs-lookup"><span data-stu-id="8f324-113">Examples</span></span>  
 <span data-ttu-id="8f324-114">Im folgenden Beispiel werden die erweiterten gespeicherten Prozeduren von Datenbank-E-Mail aktiviert.</span><span class="sxs-lookup"><span data-stu-id="8f324-114">The following example enables the Database Mail extended stored procedures.</span></span>  
  
```  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'Database Mail XPs', 1;  
GO  
RECONFIGURE  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="8f324-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8f324-115">See Also</span></span>  
 [<span data-ttu-id="8f324-116">Datenbank-E-Mail</span><span class="sxs-lookup"><span data-stu-id="8f324-116">Database Mail</span></span>](../../relational-databases/database-mail/database-mail.md)  
  
  
