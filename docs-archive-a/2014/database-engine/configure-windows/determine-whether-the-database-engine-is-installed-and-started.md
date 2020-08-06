---
title: Bestimmen, ob die Datenbank-Engine installiert und gestartet wurde | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- SQL Server, determining if installed
- verifying Database Engine installation
- viewing Database Engine installation
- installed Database Engine verification [SQL Server]
ms.assetid: babb02e4-3521-4b75-b5df-e09205594375
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 0a912cf4a89f208543605cc84f480b63955214ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724174"
---
# <a name="determine-whether-the-database-engine-is-installed-and-started"></a><span data-ttu-id="af41a-102">Bestimmen, ob die Datenbank-Engine installiert und gestartet wurde</span><span class="sxs-lookup"><span data-stu-id="af41a-102">Determine Whether the Database Engine Is Installed and Started</span></span>
  <span data-ttu-id="af41a-103">Bei einer erfolgreichen Installation von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] werden Dateien auf dem Dateisystem installiert, Einträge in der Registrierung erstellt und verschiedene Tools installiert.</span><span class="sxs-lookup"><span data-stu-id="af41a-103">A successful installation of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] installs files to the file system, creates entries in the registry, and installs several tools.</span></span> <span data-ttu-id="af41a-104">In diesem Thema wird beschrieben, wie bestimmt wird, ob der [!INCLUDE[ssDE](../../includes/ssde-md.md)] installiert und in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Managers gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="af41a-104">This topic describes how to determine whether the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is installed and started in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="af41a-105">Verwenden des SQL Server-Konfigurations-Managers</span><span class="sxs-lookup"><span data-stu-id="af41a-105">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="how-to-view-and-start-the-database-engine-by-using-sql-server-configuration-manager"></a><span data-ttu-id="af41a-106">Anzeigen und Starten der Datenbank-Engine mithilfe des SQL Server-Konfigurations-Managers</span><span class="sxs-lookup"><span data-stu-id="af41a-106">How to view and start the Database Engine by using SQL Server Configuration Manager</span></span>  
  
1.  <span data-ttu-id="af41a-107">Klicken Sie auf **Start**, wählen Sie **Alle Programme**aus, zeigen Sie auf **Microsoft SQL Server**, auf **Konfigurationstools**, und klicken Sie dann auf **SQL Server-Konfigurations-Manager**.</span><span class="sxs-lookup"><span data-stu-id="af41a-107">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
     <span data-ttu-id="af41a-108">Wenn diese Einträge im Menü **Start** nicht enthalten sind, ist [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nicht korrekt installiert.</span><span class="sxs-lookup"><span data-stu-id="af41a-108">If you do not have these entries on the **Start** menu, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is not correctly installed.</span></span> <span data-ttu-id="af41a-109">Führen Sie das Setup aus, um [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]zu installieren.</span><span class="sxs-lookup"><span data-stu-id="af41a-109">Run Setup to install the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="af41a-110">Klicken Sie im linken Bereich von **SQL Server-Konfigurations-Manager**auf **SQL Server 2005-Dienste**.</span><span class="sxs-lookup"><span data-stu-id="af41a-110">In **SQL Server Configuration Manager**, on the left pane, click **SQL Server Services**.</span></span> <span data-ttu-id="af41a-111">Im rechten Bereich werden mehrere Dienste im Zusammenhang mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="af41a-111">The right pane lists several services that are related to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="af41a-112">Wenn [!INCLUDE[ssDE](../../includes/ssde-md.md)] installiert ist, wird der [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Dienst als **SQL Server (MSSQLSERVER)** aufgelistet, wenn es sich um die Standardinstanz handelt, oder als **SQL Server (** \<*instance_name*> **)** , wenn [!INCLUDE[ssDE](../../includes/ssde-md.md)] als benannte Instanz installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="af41a-112">If the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is installed, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] service is listed as **SQL Server (MSSQLSERVER)** if it is the default instance; or **SQL Server (**\<*instance_name*>**)**, if the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is installed as a named instance.</span></span> <span data-ttu-id="af41a-113">Sofern der Instanzname nicht geändert wird, wird [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] als benannte Instanz mit dem Namen **SQLEXPRESS**installiert.</span><span class="sxs-lookup"><span data-stu-id="af41a-113">Unless the instance name is changed, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] installs as a named instance with the name **SQLEXPRESS**.</span></span> <span data-ttu-id="af41a-114">Ein grünes Dreieckssymbol weist darauf hin, dass [!INCLUDE[ssDE](../../includes/ssde-md.md)] ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="af41a-114">A green triangle icon indicates that the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is running.</span></span> <span data-ttu-id="af41a-115">Ein rotes Dreieckssymbol gibt an, dass [!INCLUDE[ssDE](../../includes/ssde-md.md)] beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="af41a-115">A red square icon indicates that the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is stopped.</span></span>  
  
3.  <span data-ttu-id="af41a-116">Um das [!INCLUDE[ssDE](../../includes/ssde-md.md)]zu starten, klicken Sie im rechten Bereich mit der rechten Maustaste auf das [!INCLUDE[ssDE](../../includes/ssde-md.md)]und klicken dann auf **Start**.</span><span class="sxs-lookup"><span data-stu-id="af41a-116">To start the [!INCLUDE[ssDE](../../includes/ssde-md.md)], in the right pane, right-click the [!INCLUDE[ssDE](../../includes/ssde-md.md)], and then click **Start**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="af41a-117">Während Setup kann der Benutzer ein Verzeichnis für die Installation der Programmdateien und der Datenbankdateien auswählen.</span><span class="sxs-lookup"><span data-stu-id="af41a-117">During setup, the user can select a location in which to install the program files and the database files.</span></span> <span data-ttu-id="af41a-118">Wenn der Benutzer den Standardspeicherort übernimmt, werden die Dateien unter [!INCLUDE[ssInstallPath](../../includes/ssinstallpath-md.md)] und C:\Programme\Microsoft SQL Server\MSSQL.*x*installiert, wobei *x* eine Zahl ist.</span><span class="sxs-lookup"><span data-stu-id="af41a-118">If the user accepts the default location, the files are installed to [!INCLUDE[ssInstallPath](../../includes/ssinstallpath-md.md)] and C:\Program Files\Microsoft SQL Server\MSSQL.*x*, where *x* is a number.</span></span>  
  
  
