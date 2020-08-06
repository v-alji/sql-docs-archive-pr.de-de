---
title: Konfigurieren von SQL Server-Agent-Mail zum Verwenden von Datenbank-E-Mails | Microsoft Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Database Mail [SQL Server], SQL Server Agent Mail
- SQL Server Agent Mail
ms.assetid: 4b8b61bd-4bd1-43cd-b6e5-c6ed2e101dce
author: stevestein
ms.author: sstein
ms.openlocfilehash: 31d116c0bc8d7e148fc2ef6d2e344400516ad923
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695706"
---
# <a name="configure-sql-server-agent-mail-to-use-database-mail"></a><span data-ttu-id="35fee-102">Konfigurieren von SQL Server-Agent-Mail zum Verwenden von Datenbank-E-Mails</span><span class="sxs-lookup"><span data-stu-id="35fee-102">Configure SQL Server Agent Mail to Use Database Mail</span></span>
  <span data-ttu-id="35fee-103">In diesem Thema wird beschrieben, wie der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent mithilfe von [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] zur Verwendung von Datenbank-E-Mails konfiguriert wird, damit Benachrichtigungen und Warnungen in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]versendet werden.</span><span class="sxs-lookup"><span data-stu-id="35fee-103">This topic describes how to configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to use Database Mail to send notification and alerts in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
-   <span data-ttu-id="35fee-104">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="35fee-104">**Before you begin:**</span></span>  
  
-   [<span data-ttu-id="35fee-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="35fee-105">Prerequisites</span></span>](#Prerequisites)  
  
-   [<span data-ttu-id="35fee-106">Security</span><span class="sxs-lookup"><span data-stu-id="35fee-106">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="35fee-107">So konfigurieren Sie mithilfe von SQL Server Management Studio den SQL Server-Agent zur Verwendung von Datenbank-E-Mail</span><span class="sxs-lookup"><span data-stu-id="35fee-107">To Configure SQL Server Agent to use Database Mail, using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   [<span data-ttu-id="35fee-108">Nach Verfolgungs Aufgaben</span><span class="sxs-lookup"><span data-stu-id="35fee-108">Follow-up Tasks</span></span>](#Follow_Up)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="35fee-109">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="35fee-109">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="35fee-110">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="35fee-110">Prerequisites</span></span>  
  
-   <span data-ttu-id="35fee-111">Aktivieren Sie Datenbank-E-Mail.</span><span class="sxs-lookup"><span data-stu-id="35fee-111">Enable Database Mail.</span></span>  
  
-   <span data-ttu-id="35fee-112">Erstellen Sie ein Datenbank-E-Mail-Konto für das zu verwendende [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Dienstkonto.</span><span class="sxs-lookup"><span data-stu-id="35fee-112">Create a Database Mail account for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account to use.</span></span>  
  
-   <span data-ttu-id="35fee-113">Erstellen Sie ein Datenbank-E-Mail-Profil für das zu verwendende Konto des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Dienstes, und fügen Sie den Benutzer zur **DatabaseMailUserRole** in der **msdb** -Datenbank hinzu.</span><span class="sxs-lookup"><span data-stu-id="35fee-113">Create a Database Mail profile for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account to use and add the user to the **DatabaseMailUserRole** in the **msdb** database.</span></span>  
  
-   <span data-ttu-id="35fee-114">Legen Sie das Profil als Standardprofil für die **msdb** -Datenbank fest.</span><span class="sxs-lookup"><span data-stu-id="35fee-114">Set the profile as the default profile for the **msdb** database.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="35fee-115">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="35fee-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="35fee-116">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="35fee-116">Permissions</span></span>  
 <span data-ttu-id="35fee-117">Der Benutzer, der die Profilkonten erstellt und gespeicherte Prozeduren ausführt, sollte Mitglied der festen Serverrolle "sysadmin" sein.</span><span class="sxs-lookup"><span data-stu-id="35fee-117">The user creating the profiles accounts and executing stored procedures should be a member of the sysadmin fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="35fee-118">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="35fee-118">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="35fee-119">**So konfigurieren Sie den SQL Server-Agent zum Verwenden von Datenbank-E-Mail**</span><span class="sxs-lookup"><span data-stu-id="35fee-119">**To configure SQL Server Agent to use Database Mail**</span></span>  
  
-   <span data-ttu-id="35fee-120">Erweitern Sie im Objekt-Explorer eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz.</span><span class="sxs-lookup"><span data-stu-id="35fee-120">In Object Explorer, expand a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
-   <span data-ttu-id="35fee-121">Klicken Sie mit der rechten Maustaste auf **SQL Server-Agent**, und klicken Sie anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="35fee-121">Right-click **SQL Server Agent**, and then click **Properties**.</span></span>  
  
-   <span data-ttu-id="35fee-122">Klicken Sie auf **Warnungssystem**.</span><span class="sxs-lookup"><span data-stu-id="35fee-122">Click **Alert System**.</span></span>  
  
-   <span data-ttu-id="35fee-123">Wählen Sie **Mailprofil aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="35fee-123">Select **Enable Mail Profile**.</span></span>  
  
-   <span data-ttu-id="35fee-124">Wählen Sie in der Liste **Mailsystem** die Option **Datenbank-E-Mail**aus.</span><span class="sxs-lookup"><span data-stu-id="35fee-124">In the **Mail system** list, select **Database Mail**.</span></span>  
  
-   <span data-ttu-id="35fee-125">Wählen Sie in der Liste **Mailprofil**ein Mailprofil für Datenbank-E-Mail aus.</span><span class="sxs-lookup"><span data-stu-id="35fee-125">In the **Mail profile list**, select a mail profile for Database Mail.</span></span>  
  
-   <span data-ttu-id="35fee-126">Starten Sie SQL Server-Agent neu.</span><span class="sxs-lookup"><span data-stu-id="35fee-126">Restart SQL Server Agent.</span></span>  
  
##  <a name="follow-up-tasks"></a><a name="Follow_Up"></a> <span data-ttu-id="35fee-127">Anschlussaufgaben</span><span class="sxs-lookup"><span data-stu-id="35fee-127">Follow-up Tasks</span></span>  
 <span data-ttu-id="35fee-128">Die folgenden Aufgaben sind zum Abschließen der Konfiguration des Agents zum Senden von Warnungen und Benachrichtigungen erforderlich:</span><span class="sxs-lookup"><span data-stu-id="35fee-128">The following tasks are necessary to complete the configuration of Agent to send alerts and notifications.</span></span>  
  
-   [<span data-ttu-id="35fee-129">Warnungen</span><span class="sxs-lookup"><span data-stu-id="35fee-129">Alerts</span></span>](../../ssms/agent/alerts.md)  
  
     <span data-ttu-id="35fee-130">Warnungen können zum Benachrichtigen eines Operators über ein bestimmtes Datenbankereignis oder eine Betriebssystembedingung konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="35fee-130">Alerts can be configured to notify an operator of a particular database event or operating system condition.</span></span>  
  
-   [<span data-ttu-id="35fee-131">Operatoren</span><span class="sxs-lookup"><span data-stu-id="35fee-131">Operators</span></span>](../../ssms/agent/operators.md)  
  
     <span data-ttu-id="35fee-132">Operatoren sind Aliase für Personen oder Gruppen, die elektronische Benachrichtigung empfangen können.</span><span class="sxs-lookup"><span data-stu-id="35fee-132">Operators are aliases for people or groups that can receive electronic notification</span></span>  
  
  
