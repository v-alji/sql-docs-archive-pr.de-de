---
title: SAP BW-Verbindungs-Manager | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 06b166a1-a9df-48ea-a0e8-9b8d6979c0a1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bc3bb32c4895c6ec8fbcf31d57e8685c74de32dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610013"
---
# <a name="sap-bw-connection-manager"></a><span data-ttu-id="a6170-102">SAP BW-Verbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="a6170-102">SAP BW Connection Manager</span></span>
  <span data-ttu-id="a6170-103">Der SAP BW-Verbindungs-Manager ist die Verbindungs-Manager-Komponente von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span><span class="sxs-lookup"><span data-stu-id="a6170-103">The SAP BW connection manager is the connection manager component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span></span> <span data-ttu-id="a6170-104">Daher stellt der SAP BW-Verbindungs-Manager die Konnektivität mit einem SAP NetWeaver BW-System, Version 7, bereit, das für die Quell- und Zielkomponenten von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="a6170-104">Thus, the SAP BW connection manager provides the connectivity to an SAP Netweaver BW version 7 system that the source and destination components of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW need.</span></span> <span data-ttu-id="a6170-105">(SAP BW-Quelle und -Ziel, die Teil des [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW-Pakets sind, sind die einzigen [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Komponenten, die den SAP BW-Verbindungs-Manager verwenden.)</span><span class="sxs-lookup"><span data-stu-id="a6170-105">(The SAP BW source and destination that are part of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW package are the only [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] components that use the SAP BW connection manager.)</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a6170-106">Die Dokumentation für Microsoft Connector 1.1 for SAP BW setzt Kenntnisse der SAP NetWeaver BW-Umgebung voraus.</span><span class="sxs-lookup"><span data-stu-id="a6170-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="a6170-107">Weitere Informationen zu SAP NetWeaver BW oder Informationen zur Konfiguration von SAP NetWeaver BW-Objekten und -Prozessen finden Sie in der SAP-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="a6170-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="a6170-108">Wenn Sie einem Paket einen SAP BW-Verbindungs-Manager hinzufügen, wird die `ConnectionManagerType`-Eigenschaft des Verbindungs-Managers auf `SAPBI` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a6170-108">When you add an SAP BW connection manager to a package, the `ConnectionManagerType` property of the connection manager is set to `SAPBI`.</span></span>  
  
## <a name="configuring-the-sap-bw-connection-manager"></a><span data-ttu-id="a6170-109">Konfigurieren des SAP BW-Verbindungs-Managers</span><span class="sxs-lookup"><span data-stu-id="a6170-109">Configuring the SAP BW Connection Manager</span></span>  
 <span data-ttu-id="a6170-110">Es gibt folgende Möglichkeiten, um den SAP BW-Verbindungs-Manager zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="a6170-110">You can configure the SAP BW connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="a6170-111">Geben Sie Client, Benutzernamen, Kennwort und Sprache für die Verbindung an.</span><span class="sxs-lookup"><span data-stu-id="a6170-111">Provide the client, user name, password, and language for the connection.</span></span>  
  
-   <span data-ttu-id="a6170-112">Wählen Sie aus, ob eine Verbindung mit einem Einzelanwendungsserver oder einer Gruppe von Servern mit Lastenausgleich hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a6170-112">Choose whether to connect to a single application server or to a group of load-balanced servers.</span></span>  
  
-   <span data-ttu-id="a6170-113">Geben Sie die Host- und Systemnummer für einen Einzelanwendungsserver oder Nachrichtenserver, Gruppe und SID für eine Gruppe von Servern mit Lastenausgleich an.</span><span class="sxs-lookup"><span data-stu-id="a6170-113">Provide the host and system number for a single application server, or provide the message server, group, and SID for a group of load-balanced servers.</span></span>  
  
-   <span data-ttu-id="a6170-114">Aktivieren Sie die benutzerdefinierte Protokollierung von RFC-Funktionsaufrufen für Komponenten von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span><span class="sxs-lookup"><span data-stu-id="a6170-114">Enable custom logging of RFC function calls for the components of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span></span> <span data-ttu-id="a6170-115">(Diese Protokollierung wird separat von der optionalen Protokollierung ausgeführt, die Sie für [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Pakete aktivieren können.) Um die Protokollierung von RFC-Funktionsaufrufen zu aktivieren, geben Sie ein Verzeichnis an, in dem Sie die Protokolldateien speichern, die vor und nach jedem RFC-Funktionsaufruf erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="a6170-115">(This logging is separate from the optional logging that you can enable on [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.) To enable logging of RFC function calls, you specify a directory in which to store the log files that are created before and after each RFC function call.</span></span> <span data-ttu-id="a6170-116">(Durch diese Protokollierungsfunktion werden viele Protokolldateien im XML-Format erstellt.</span><span class="sxs-lookup"><span data-stu-id="a6170-116">(This logging feature creates many log files in XML format.</span></span> <span data-ttu-id="a6170-117">Da diese Protokolldateien auch alle übertragenen Datenzeilen enthalten, können sie viel Speicherplatz auf dem Datenträger beanspruchen.) Wenn Sie kein Protokollverzeichnis auswählen, wird die Protokollierung nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a6170-117">As these log files also contain all the rows of data that are transferred, these log files may consume a large amount of disk space.) If you do not select a log directory, logging is not enabled.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="a6170-118">Wenn die übertragenen Daten vertrauliche Informationen enthalten, sind diese auch in den Protokolldateien enthalten.</span><span class="sxs-lookup"><span data-stu-id="a6170-118">If the data that is transferred contains sensitive information, the log files will also contain that sensitive information.</span></span>  
  
-   <span data-ttu-id="a6170-119">Testen Sie die Verbindung anhand der eingegebenen Werte.</span><span class="sxs-lookup"><span data-stu-id="a6170-119">Use the values that you have entered to test the connection.</span></span>  
  
 <span data-ttu-id="a6170-120">Wenn Sie nicht alle Werte kennen, die zur Konfiguration des Verbindungs-Managers erforderlich sind, müssen Sie ggf. Ihren SAP-Administrator um Unterstützung bitten.</span><span class="sxs-lookup"><span data-stu-id="a6170-120">If you do not know all the values that are required to configure the connection manager, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="a6170-121">Eine exemplarische Vorgehensweise, die zeigt, wie der SAP BW-Verbindungs-Manager sowie die zugehörige Quelle und das zugehörige Ziel konfiguriert und verwendet werden, finden Sie im Whitepaper [Verwenden von SQL Server 2008 Integration Services und SAP BI 7.0](https://go.microsoft.com/fwlink/?LinkID=137090).</span><span class="sxs-lookup"><span data-stu-id="a6170-121">For a walkthrough that demonstrates how to configure and use the SAP BW connection manager, source, and destination, see the white paper, [Using SQL Server 2008 Integration Services with SAP BI 7.0](https://go.microsoft.com/fwlink/?LinkID=137090).</span></span> <span data-ttu-id="a6170-122">In diesem Whitepaper wird auch erläutert, wie die erforderlichen Objekte in SAP BW konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="a6170-122">This white paper also shows how to configure the required objects in SAP BW.</span></span>  
  
### <a name="using-the-ssis-designer-to-configure-the-source"></a><span data-ttu-id="a6170-123">Konfigurieren der Quelle mit dem SSIS-Designer</span><span class="sxs-lookup"><span data-stu-id="a6170-123">Using the SSIS Designer to Configure the Source</span></span>  
 <span data-ttu-id="a6170-124">Klicken Sie auf das folgende Thema, um weitere Informationen zu den Eigenschaften des SAP BW-Verbindungs-Managers zu erhalten, die Sie im [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer festlegen können:</span><span class="sxs-lookup"><span data-stu-id="a6170-124">For more information about the properties of the SAP BW connection manager that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="a6170-125">Verbindungs-Manager-Editor für SAP BW</span><span class="sxs-lookup"><span data-stu-id="a6170-125">SAP BW Connection Manager Editor</span></span>](../sap-bw-connection-manager-editor.md)  
  
## <a name="see-also"></a><span data-ttu-id="a6170-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a6170-126">See Also</span></span>  
 [<span data-ttu-id="a6170-127">Komponenten von Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="a6170-127">Microsoft Connector 1.1 for SAP BW Components</span></span>](../microsoft-connector-for-sap-bw-components.md)  
  
  
