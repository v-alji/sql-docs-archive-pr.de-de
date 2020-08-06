---
title: Formatieren von Pageradressen für Warnungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- pager addresses [SQL Server]
- SQL Server Agent, alerts
- formats [SQL Server], pager addresses
- pager notifications [SQL Server]
- addresses [SQL Server]
- alerts [SQL Server], pager addresses
ms.assetid: a9797d01-1050-442c-9038-ed4bfee1e76a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 471f9a4958f51491b312d89239a2204c907e25e5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608214"
---
# <a name="format-pager-addresses-for-alerts"></a><span data-ttu-id="4f166-102">Format Pager Addresses for Alerts</span><span class="sxs-lookup"><span data-stu-id="4f166-102">Format Pager Addresses for Alerts</span></span>
  <span data-ttu-id="4f166-103">In diesem Thema wird beschrieben, wie Pager-Adressen für- [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent-Warnungen in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von oder formatiert werden [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4f166-103">This topic describes how to format pager addresses for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="4f166-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="4f166-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4f166-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="4f166-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4f166-106">Security</span><span class="sxs-lookup"><span data-stu-id="4f166-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4f166-107">**So formatieren Sie Pageradressen mit**</span><span class="sxs-lookup"><span data-stu-id="4f166-107">**To format pager addresses, using:**</span></span>  
  
     [<span data-ttu-id="4f166-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4f166-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4f166-109">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="4f166-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4f166-110">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="4f166-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4f166-111">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="4f166-111">Permissions</span></span>  
 <span data-ttu-id="4f166-112">Standardmäßig können nur Mitglieder der festen Serverrolle **sysadmin** Information über eine Warnung anzeigen.</span><span class="sxs-lookup"><span data-stu-id="4f166-112">By default, members of the **sysadmin** fixed server role can view information about an alert.</span></span> <span data-ttu-id="4f166-113">Andere Benutzer müssen Mitglieder der festen Datenbankrolle **SQLAgentOperatorRole** in der **msdb** -Datenbank sein.</span><span class="sxs-lookup"><span data-stu-id="4f166-113">Other users must be granted the **SQLAgentOperatorRole** fixed database role in the **msdb** database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4f166-114">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4f166-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-format-pager-addresses"></a><span data-ttu-id="4f166-115">So formatieren Sie Pageradressen</span><span class="sxs-lookup"><span data-stu-id="4f166-115">To format pager addresses</span></span>  
  
1.  <span data-ttu-id="4f166-116">Klicken Sie im **Objekt-Explorer** auf das Pluszeichen, um den Server zu erweitern, der die Warnung enthält, die Sie an einen Pager senden möchten.</span><span class="sxs-lookup"><span data-stu-id="4f166-116">In **Object Explorer**, click the plus sign to expand the server that contains the alert that you want to send to a pager.</span></span>  
  
2.  <span data-ttu-id="4f166-117">Klicken Sie mit der rechten Maustaste auf **SQL Server-Agent** und wählen Sie **Eigenschaften**</span><span class="sxs-lookup"><span data-stu-id="4f166-117">Right-click **SQL Server Agent** and select **Properties**</span></span>  
  
3.  <span data-ttu-id="4f166-118">Wählen Sie unter **Seite auswählen**die Option **Warnungssystem**aus.</span><span class="sxs-lookup"><span data-stu-id="4f166-118">Under **Select a page**, select **Alert System**.</span></span>  
  
4.  <span data-ttu-id="4f166-119">Geben Sie in die Felder **An-Zeile** und **Cc-Zeile** des Felds **Adressformatierung für Pager-E-Mails:** das Präfix oder das Suffix der Pageradresse ein.</span><span class="sxs-lookup"><span data-stu-id="4f166-119">In the **To line** and **CC line** boxes of the **Address formatting for pager e-mails** field, enter the pager address prefix or suffix.</span></span> <span data-ttu-id="4f166-120">Die eigentliche Pageradresse des Operators wird beim Senden einer Benachrichtigung eingefügt.</span><span class="sxs-lookup"><span data-stu-id="4f166-120">The operator's actual pager address is inserted when a notification is sent.</span></span>  
  
5.  <span data-ttu-id="4f166-121">Geben Sie in das Feld **Betreff** das Präfix oder Suffix der Betreffzeile ein.</span><span class="sxs-lookup"><span data-stu-id="4f166-121">In the **Subject** box, enter the subject line prefix or suffix.</span></span>  
  
6.  <span data-ttu-id="4f166-122">Aktivieren Sie das Kontrollkästchen **Nachrichtenbereich der E-Mail in Benachrichtigungsseite aufnehmen** , um die vollständige E-Mail-Nachricht in die Pagernachricht einzuschließen (statt lediglich die Betreffzeile).</span><span class="sxs-lookup"><span data-stu-id="4f166-122">Select the **Include body of e-mail in notification page** check box to include the full e-mail message with the pager message (as opposed to the subject line only).</span></span>  
  
7.  <span data-ttu-id="4f166-123">Wenn Sie fertig sind, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4f166-123">When finished, click **OK**.</span></span>  
  
  
