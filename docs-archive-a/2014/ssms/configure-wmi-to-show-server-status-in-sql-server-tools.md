---
title: Konfigurieren von WMI zum Anzeigen des Serverstatus in SQL Server-Tools | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- WMI Provider for Server Events, setting permissions
- WMI permissions [SQL Server]
ms.assetid: 7e97197b-ed4d-40d1-9a52-9ab1d92401d7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 138abbe2b7b819d6afd6da62135f7cd7ce86496f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722177"
---
# <a name="configure-wmi-to-show-server-status-in-sql-server-tools"></a><span data-ttu-id="5cc90-102">Konfigurieren von WMI zum Anzeigen des Serverstatus in SQL Server-Tools</span><span class="sxs-lookup"><span data-stu-id="5cc90-102">Configure WMI to Show Server Status in SQL Server Tools</span></span>
  <span data-ttu-id="5cc90-103">In diesem Thema wird beschrieben, wie WMI konfiguriert wird, um den Serverstatus in SQL Server-Tools in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5cc90-103">This topic describes how to configure WMI to show the server status in SQL Server tools in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="5cc90-104">Bei der Verbindungsherstellung mit Servern wird von den Komponenten Registrierte Server und Objekt-Explorer von [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]sowie auch vom [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Konfigurations-Manager Windows Management Instrumentation (WMI) zum Abrufen des Status der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Dienste (MSSQLSERVER) und [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Agent-Dienste (MSSQLSERVER) verwendet.</span><span class="sxs-lookup"><span data-stu-id="5cc90-104">When connecting to servers, both the Registered Servers and Object Explorer components of [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], as well as [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Configuration Manager, use Windows Management Instrumentation (WMI) to obtain the status of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] (MSSQLSERVER) and [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent (MSSQLSERVER) services.</span></span> <span data-ttu-id="5cc90-105">Zum Anzeigen des Dienststatus muss der Benutzer über Remotezugriffsrechte für das WMI-Objekt verfügen.</span><span class="sxs-lookup"><span data-stu-id="5cc90-105">To display the status of the service, the user must have rights to remotely access the WMI object.</span></span> <span data-ttu-id="5cc90-106">Zum Konfigurieren dieser Berechtigung muss auf dem Server WMI installiert sein.</span><span class="sxs-lookup"><span data-stu-id="5cc90-106">The server must have WMI installed to configure this permission.</span></span>  
  
##  <a name="to-configure-wmi-permission"></a><a name="SSMSProcedure"></a><span data-ttu-id="5cc90-107">So konfigurieren Sie die WMI-Berechtigung</span><span class="sxs-lookup"><span data-stu-id="5cc90-107">To configure WMI permission</span></span>  
  
1.  <span data-ttu-id="5cc90-108">Klicken Sie auf dem Remoteserver im Menü **Start** auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="5cc90-108">On the **Start** menu on the remote server, click **Run**.</span></span>  
  
2.  <span data-ttu-id="5cc90-109">Geben Sie im Feld **Öffnen** ein `wmimgmt.msc` , und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5cc90-109">In the **Open** box type `wmimgmt.msc`, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="5cc90-110">Klicken Sie im Programm **Windows-Verwaltungsinfrastruktur** mit der rechten Maustaste auf **WMI-Steuerung (Lokal)** , und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="5cc90-110">In the **Windows Management Infrastructure** program, right-click **WMI Control (Local)**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="5cc90-111">Erweitern Sie im Dialogfeld **Eigenschaften von WMI-Steuerung (Lokal)** auf der Registerkarte **Sicherheit** den Eintrag **Root**, und klicken Sie dann auf **CIMV2**.</span><span class="sxs-lookup"><span data-stu-id="5cc90-111">In the **WMI Control (Local) Properties** dialog box, on the **Security** tab, expand **Root**, and then click **CIMV2**.</span></span>  
  
5.  <span data-ttu-id="5cc90-112">Klicken Sie auf **Sicherheit** , um das Dialogfeld **Sicherheit für ROOT\CIMV2** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="5cc90-112">Click **Security** to open the **Security for ROOT\CIMV2** dialog box.</span></span>  
  
6.  <span data-ttu-id="5cc90-113">Fügen Sie zum Feld **Gruppen- oder Benutzernamen** eine Gruppe oder einen Benutzer hinzu, und markieren Sie die Gruppe bzw. den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="5cc90-113">Add a group or user to the **Group or user names** box and select it.</span></span>  
  
7.  <span data-ttu-id="5cc90-114">Wählen Sie im Feld **Berechtigungen für** _\<group or user>_ die Spalte **Zulassen** für die Berechtigung **Remoteaktivierung** für Benutzer aus, durch die der Dienststatus remote erkannt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5cc90-114">In the **Permissions for**_\<group or user>_ box, select the **Allow** column, for the **Remote Enable** permission, for users whom you wish to remotely detect the service status.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cc90-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5cc90-115">See Also</span></span>  
 [<span data-ttu-id="5cc90-116">Starten, Beenden oder Anhalten des SQL Server-Agent-Diensts</span><span class="sxs-lookup"><span data-stu-id="5cc90-116">Start, Stop, or Pause the SQL Server Agent Service</span></span>](agent/start-stop-or-pause-the-sql-server-agent-service.md)  
  
  
