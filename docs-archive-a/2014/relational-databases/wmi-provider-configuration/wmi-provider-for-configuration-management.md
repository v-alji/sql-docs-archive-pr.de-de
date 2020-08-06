---
title: Konzepte des WMI-Anbieters für die Konfigurations Verwaltung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
helpviewer_keywords:
- WMI Provider for Configuration Management
- SQL Server WMI Provider
- configuration management [WMI]
- WMI Provider for Configuration Management, about WMI Provider for Configuration Management
ms.assetid: 7e41db24-b915-4eb8-a1d6-e6948ee915b7
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: be0682e7d6de5cb8c3d67a2f300bb89122213652
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615871"
---
# <a name="wmi-provider-for-configuration-management-concepts"></a><span data-ttu-id="e0743-102">Konzepte des WMI-Anbieters für die Konfigurationsverwaltung</span><span class="sxs-lookup"><span data-stu-id="e0743-102">WMI Provider for Configuration Management Concepts</span></span>
  <span data-ttu-id="e0743-103">Der WMI-Anbieter ist eine veröffentlichte Ebene, die mit dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager-Snap-in für die [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console (MMC) und die Configuration Manager verwendet wird [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e0743-103">The WMI provider is a published layer that is used with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager snap-in for [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console (MMC) and the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="e0743-104">Sie bietet eine vereinheitlichte Schnittstellenfunktion zu API-Aufrufen, mit denen die vom [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Konfigurations-Manager angeforderten Registrierungsvorgänge verwaltet werden, und ermöglicht eine verbesserte Steuerung und Bearbeitung der ausgewählten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Dienste.</span><span class="sxs-lookup"><span data-stu-id="e0743-104">It provides a unified way for interfacing with the API calls that manage the registry operations requested by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager and provides enhanced control and manipulation over the selected [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services.</span></span>  
  
 <span data-ttu-id="e0743-105">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-WMI-Anbieter besteht aus einer DLL- und einer MOF-Datei, die automatisch von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="e0743-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] WMI Provider is a DLL and a MOF file, which are compiled automatically by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup.</span></span>  
  
 <span data-ttu-id="e0743-106">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-WMI-Anbieter enthält einen Satz Objektklassen, die zur Steuerung der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Dienste mittels folgender Methoden verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="e0743-106">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] WMI Provider contains a set of object classes used to control the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services using the following methods:</span></span>  
  
-   <span data-ttu-id="e0743-107">Eine Skriptsprache wie VBScript, [!INCLUDE[jsprjscript](../../includes/jsprjscript-md.md)] oder Perl, in die Windows Query Language (WQL) eingebettet werden kann</span><span class="sxs-lookup"><span data-stu-id="e0743-107">A script language such as VBScript, [!INCLUDE[jsprjscript](../../includes/jsprjscript-md.md)], or Perl, in which Windows Query Language (WQL) can be embedded.</span></span>  
  
-   <span data-ttu-id="e0743-108">Das <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer>-Objekt in einem von SMO verwalteten Codeprogramm</span><span class="sxs-lookup"><span data-stu-id="e0743-108">The <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> object in an SMO managed code program.</span></span>  
  
-   <span data-ttu-id="e0743-109">Den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Konfigurations-Manager oder MMC mit dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] WMI-Anbieter-Snap-In</span><span class="sxs-lookup"><span data-stu-id="e0743-109">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager or MMC with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] WMI provider snap-in.</span></span>  
  
## <a name="using-a-script-language"></a><span data-ttu-id="e0743-110">Verwenden einer Skriptsprache</span><span class="sxs-lookup"><span data-stu-id="e0743-110">Using a Script Language</span></span>  
 <span data-ttu-id="e0743-111">Die Verwendung einer Skriptsprache bietet folgende Vorteile:</span><span class="sxs-lookup"><span data-stu-id="e0743-111">The advantages of using a script language include the following:</span></span>  
  
-   <span data-ttu-id="e0743-112">Eine Entwicklungsumgebung ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e0743-112">A development environment is not required.</span></span>  
  
-   <span data-ttu-id="e0743-113">Die Dateien, die die Skriptsprache unterstützen, sind überall verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e0743-113">The files that support the script language are widely available.</span></span>  
  
 <span data-ttu-id="e0743-114">Das Skript kann neben dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] WMI-Anbieter auch in Verbindung mit anderen WMI-Anbietern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e0743-114">The script can also work with other WMI Providers in addition to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] WMI Provider.</span></span> <span data-ttu-id="e0743-115">Ein Domänenadministrator kann ein Skript verwenden, um Dienste, Netzwerkeinstellungen und Aliaseinstellungen auf mehreren Computern in einem Netzwerk einzurichten.</span><span class="sxs-lookup"><span data-stu-id="e0743-115">A domain administrator can use a script to set up the services, network settings, and alias settings on multiple computers on a network.</span></span>  
  
 <span data-ttu-id="e0743-116">In diesem Abschnitt wird detaillierter darauf eingegangen, wie von Skripts auf den WMI-Anbieter für die Konfigurationsverwaltung zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="e0743-116">This section deals with accessing the WMI Provider for Configuration Management from scripts in further detail.</span></span>  
  
## <a name="using-the-smo-managedcomputer-object"></a><span data-ttu-id="e0743-117">Verwenden des SMO-Objekts 'ManagedComputer'</span><span class="sxs-lookup"><span data-stu-id="e0743-117">Using the SMO ManagedComputer Object</span></span>  
 <span data-ttu-id="e0743-118">Das <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer>-Objekt ist ein verwaltetes SMO-Objekt, das Zugriff auf den WMI-Anbieter für die Konfigurationsverwaltung bietet.</span><span class="sxs-lookup"><span data-stu-id="e0743-118">The <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> object is a managed SMO object that provides access to the WMI Provider for Configuration Management.</span></span> <span data-ttu-id="e0743-119">In Verbindung mit einem SMO-Programm kann das <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer>-Objekt zur Anzeige und Änderung von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Diensten, Netzwerkeinstellungen und Aliaseinstellungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e0743-119">By using an SMO program, the <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> object can be used to view and modify [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services, network settings, and alias settings.</span></span> <span data-ttu-id="e0743-120">Weitere Informationen finden Sie unter [Verwalten von Diensten und Netzwerkeinstellungen mit dem WMI-Anbieter](../server-management-objects-smo/tasks/managing-services-and-network-settings-by-using-wmi-provider.md).</span><span class="sxs-lookup"><span data-stu-id="e0743-120">For more information, see [Managing Services and Network Settings by Using WMI Provider](../server-management-objects-smo/tasks/managing-services-and-network-settings-by-using-wmi-provider.md).</span></span>  
  
## <a name="using-the-microsoft-management-console-or-sql-server-configuration-manager"></a><span data-ttu-id="e0743-121">Verwenden von Microsoft Management Console oder des SQL Server-Konfigurations-Managers</span><span class="sxs-lookup"><span data-stu-id="e0743-121">Using the Microsoft Management Console or SQL Server Configuration Manager</span></span>  
 <span data-ttu-id="e0743-122">Microsoft Management Console (MMC) bietet statt einer Skriptsprache oder eines verwalteten Codeprogramms eine Schnittstelle für die Verwaltung von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Diensten.</span><span class="sxs-lookup"><span data-stu-id="e0743-122">Microsoft Management Console (MMC) provides an interface to manage [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services, as opposed to a scripting language or managed code program.</span></span> <span data-ttu-id="e0743-123">Das MMC-Snap-In für die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Verwaltung kann dazu verwendet werden, Dienste anzuhalten und zu starten und Dienstkonten zu ändern.</span><span class="sxs-lookup"><span data-stu-id="e0743-123">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management MMC snap-in can be used to stop and start services, and to change service accounts.</span></span>  
  
 <span data-ttu-id="e0743-124">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Konfigurations-Manager kann ebenfalls zur Verwaltung von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Diensten, Client- und Serverprotokollen sowie Serveraliasen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e0743-124">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager can also be used to manage [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services, client and server protocols, and server aliases</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0743-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e0743-125">See Also</span></span>  
 <span data-ttu-id="e0743-126">[Grundlegendes zum WMI-Anbieter für die Konfigurations Verwaltung](understanding-the-wmi-provider-for-configuration-management.md) </span><span class="sxs-lookup"><span data-stu-id="e0743-126">[Understanding the WMI Provider for Configuration Management](understanding-the-wmi-provider-for-configuration-management.md) </span></span>  
 <span data-ttu-id="e0743-127">[Arbeiten mit dem WMI-Anbieter für die Konfigurations Verwaltung](working-with-the-wmi-provider-for-configuration-management.md) </span><span class="sxs-lookup"><span data-stu-id="e0743-127">[Working with the WMI Provider for Configuration Management](working-with-the-wmi-provider-for-configuration-management.md) </span></span>  
 [<span data-ttu-id="e0743-128">Verwenden von WQL und Skriptsprachen mit dem WMI-Anbieter für die Konfigurationsverwaltung</span><span class="sxs-lookup"><span data-stu-id="e0743-128">Using WQL and Scripting Languages with the WMI Provider for Configuration Management</span></span>](using-wql-and-scripting-languages-with-the-wmi-provider.md)  
  
  
