---
title: Erstellen von Verbindungs-Managern | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/22/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.connectionmanager.f1
helpviewer_keywords:
- Integration Services packages, connections
- SSIS packages, connections
- packages [Integration Services], connections
- connection managers [Integration Services], creating
- SQL Server Integration Services packages, connections
ms.assetid: 6ca317b8-0061-4d9d-b830-ee8c21268345
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7661d165ea606af880fd00e4638ec43e9bfcc890
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616608"
---
# <a name="create-connection-managers"></a><span data-ttu-id="eaa0e-102">Erstellen von Verbindungs-Managern</span><span class="sxs-lookup"><span data-stu-id="eaa0e-102">Create Connection Managers</span></span>
  [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="eaa0e-103">enthält eine Reihe von Verbindungs-Managern für Tasks, mit denen eine Verbindung mit verschiedenen Server- und Datenquellentypen hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="eaa0e-103">includes a variety of connection managers to suit the needs of tasks that connect to different types of servers and data sources.</span></span> <span data-ttu-id="eaa0e-104">Verbindungs-Manager werden von den Datenflusskomponenten verwendet, die Daten in verschiedenen Arten von Datenspeichern extrahieren und laden, und von den Protokollanbietern, die Protokolle auf einen Server, in eine [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Tabelle oder eine Datei schreiben.</span><span class="sxs-lookup"><span data-stu-id="eaa0e-104">Connection managers are used by the data flow components that extract and load data in different types of data stores, and by the log providers that write logs to a server, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] table, or file.</span></span> <span data-ttu-id="eaa0e-105">Beispielsweise verwendet ein Paket mit einem Task Mail senden einen SMTP-Verbindungs-Manager, um eine Verbindung mit einem SMTP-Server (Simple Mail Transfer Protocol) herzustellen.</span><span class="sxs-lookup"><span data-stu-id="eaa0e-105">For example, a package with a Send Mail task uses an SMTP connection manager type to connect to a Simple Mail Transfer Protocol (SMTP) server.</span></span> <span data-ttu-id="eaa0e-106">Ein Paket mit einem Task SQL ausführen kann einen OLE DB-Verbindungs-Manager zum Herstellen einer Verbindung mit einer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Datenbank verwenden.</span><span class="sxs-lookup"><span data-stu-id="eaa0e-106">A package with an Execute SQL task can use an OLE DB connection manager to connect to a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="eaa0e-107">Weitere Informationen finden Sie unter [Integration Services-Verbindungen &#40;SSIS&#41;](connection-manager/integration-services-ssis-connections.md).</span><span class="sxs-lookup"><span data-stu-id="eaa0e-107">For more information, see [Integration Services &#40;SSIS&#41; Connections](connection-manager/integration-services-ssis-connections.md).</span></span>

 <span data-ttu-id="eaa0e-108">Um die Verbindungs-Manager beim Erstellen eines Pakets automatisch zu erstellen und zu konfigurieren, können Sie den [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Import/Export-Assistenten verwenden.</span><span class="sxs-lookup"><span data-stu-id="eaa0e-108">To automatically create and configure connection managers when you create a new package, you can use the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Import and Export Wizard.</span></span> <span data-ttu-id="eaa0e-109">Dieser Assistent hilft Ihnen auch, die Quellen und Ziele zu erstellen und zu konfigurieren, die die Verbindungs-Manager verwenden.</span><span class="sxs-lookup"><span data-stu-id="eaa0e-109">The wizard also helps you create and configure the sources and destinations that use the connection managers.</span></span> <span data-ttu-id="eaa0e-110">Weitere Informationen finden Sie unter [Create Packages in SQL Server Data Tools](create-packages-in-sql-server-data-tools.md).</span><span class="sxs-lookup"><span data-stu-id="eaa0e-110">For more information, see [Create Packages in SQL Server Data Tools](create-packages-in-sql-server-data-tools.md).</span></span>

 <span data-ttu-id="eaa0e-111">Um manuell einen neuen Verbindungs-Manager zu erstellen und ihn einem vorhandenen Paket hinzuzufügen, verwenden Sie den Bereich **Verbindungs-Manager** auf den Registerkarten **Ablaufsteuerung**, **Datenfluss**und **Ereignishandler** des [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designers.</span><span class="sxs-lookup"><span data-stu-id="eaa0e-111">To manually create a new connection manager and add it to an existing package, you use the **Connection Managers** area that appears on the **Control Flow**, **Data Flow**, and **Event Handlers** tabs of [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="eaa0e-112">Im Bereich **Verbindungs-Manager** wählen Sie in einem Dialogfeld des [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designers den Typ des Verbindungs-Managers zum Erstellen und dann zum Festlegen der Eigenschaften des Verbindungs-Managers aus.</span><span class="sxs-lookup"><span data-stu-id="eaa0e-112">From the **Connection Manager** area, you choose the type of connection manager to create, and then set the properties of the connection manager by using a dialog box that [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer provides.</span></span> <span data-ttu-id="eaa0e-113">Weitere Informationen finden Sie im Abschnitt "Verwenden des Verbindungs-Manager-Bereichs" weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="eaa0e-113">For more information, see the section, "Using the Connection Managers Area," later in this topic.</span></span>

 <span data-ttu-id="eaa0e-114">Nachdem der Verbindungs-Manager einem Paket hinzugefügt wurde, können Sie ihn in Tasks, Foreach-Schleifencontainern, Quellen, Transformationen und Zielen verwenden.</span><span class="sxs-lookup"><span data-stu-id="eaa0e-114">After the connection manager is added to a package, you can use it in tasks, Foreach Loop containers, sources, transformations, and destinations.</span></span> <span data-ttu-id="eaa0e-115">Weitere Informationen finden Sie unter [Integration Services-Tasks](control-flow/integration-services-tasks.md), [Foreach-Schleifencontainer](control-flow/foreach-loop-container.md), und [Datenfluss](data-flow/data-flow.md).</span><span class="sxs-lookup"><span data-stu-id="eaa0e-115">For more information, see [Integration Services Tasks](control-flow/integration-services-tasks.md), [Foreach Loop Container](control-flow/foreach-loop-container.md), and [Data Flow](data-flow/data-flow.md).</span></span>

## <a name="using-the-connection-managers-area"></a><span data-ttu-id="eaa0e-116">Verwenden des Verbindungs-Manager-Bereichs</span><span class="sxs-lookup"><span data-stu-id="eaa0e-116">Using the Connection Managers Area</span></span>
 <span data-ttu-id="eaa0e-117">Sie können Verbindungs-Manager erstellen, während die Registerkarte **Ablaufsteuerung**, **Datenfluss**oder **Ereignishandler** des [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designers aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="eaa0e-117">You can create connection managers while the **Control Flow**, **Data Flow**, or **Event Handlers** tab of [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer is active.</span></span>

 <span data-ttu-id="eaa0e-118">Im folgenden Diagramm wird der Bereich **Verbindungs-Manager** auf der Registerkarte **Ablaufsteuerung** des [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designers angezeigt.</span><span class="sxs-lookup"><span data-stu-id="eaa0e-118">The following diagram shows the **Connection Managers** area on the **Control Flow** tab of [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>

 <span data-ttu-id="eaa0e-119">![Screenshot des Ablaufsteuerungs-Designers mit Paket](media/samplecontrolflow.gif "Screenshot des Ablaufsteuerungs-Designers mit Paket")</span><span class="sxs-lookup"><span data-stu-id="eaa0e-119">![Screenshot of control flow designer with package](media/samplecontrolflow.gif "Screenshot of control flow designer with package")</span></span>

#### <a name="to-add-configure-or-delete-a-connection-manager-in-ssis-designer"></a><span data-ttu-id="eaa0e-120">So erstellen, konfigurieren oder löschen Sie einen Verbindungs-Manager im SSIS-Designer</span><span class="sxs-lookup"><span data-stu-id="eaa0e-120">To add, configure, or delete a connection manager in SSIS Designer</span></span>

-   [<span data-ttu-id="eaa0e-121">Hinzufügen, Löschen oder Freigeben eines Verbindungs-Managers in einem Paket</span><span class="sxs-lookup"><span data-stu-id="eaa0e-121">Add, Delete, or Share a Connection Manager in a Package</span></span>](../../2014/integration-services/add-delete-or-share-a-connection-manager-in-a-package.md)

-   [<span data-ttu-id="eaa0e-122">Festlegen der Eigenschaften eines Verbindungs-Managers</span><span class="sxs-lookup"><span data-stu-id="eaa0e-122">Set the Properties of a Connection Manager</span></span>](../../2014/integration-services/set-the-properties-of-a-connection-manager.md)

## <a name="32-bit-and-64-bit-providers-for-connection-managers"></a><span data-ttu-id="eaa0e-123">32-Bit- und 64-Bit-Anbieter für Verbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="eaa0e-123">32-Bit and 64-Bit Providers for Connection Managers</span></span>
 <span data-ttu-id="eaa0e-124">Viele der von Verbindungs-Managern verwendeten Anbieter sind in der 32-Bit- und 64-Bit-Version verfügbar.</span><span class="sxs-lookup"><span data-stu-id="eaa0e-124">Many of the providers that connection managers use are available in 32-bit and 64-bit versions.</span></span> <span data-ttu-id="eaa0e-125">Die [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Entwurfsumgebung ist eine 32-Bit-Umgebung, sodass beim Entwerfen eines Pakets nur 32-Bit-Anbieter angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="eaa0e-125">The [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] design environment is a 32-bit environment and you see only 32-bit providers while you are designing a package.</span></span> <span data-ttu-id="eaa0e-126">Daher können Sie einen Verbindungs-Manager nur dann zum Verwenden eines bestimmten 64-Bit-Anbieters konfigurieren, wenn die 32-Bit-Version desselben Anbieters ebenfalls installiert ist.</span><span class="sxs-lookup"><span data-stu-id="eaa0e-126">Therefore, you can only configure a connection manager to use a specific 64-bit provider if the 32-bit version of the same provider is also installed.</span></span>

 <span data-ttu-id="eaa0e-127">Zur Laufzeit wird stets die richtige Version verwendet, unabhängig davon, ob Sie zur Entwurfszeit die 32-Bit-Version des Anbieters angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="eaa0e-127">At run time, the correct version is used, and it does not matter that you specified the 32-bit version of the provider at design time.</span></span> <span data-ttu-id="eaa0e-128">Die 64-Bit-Version des Anbieters kann auch dann ausgeführt werden, wenn das Paket in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="eaa0e-128">The 64-bit version of the provider can be run even if the package is run in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>

 <span data-ttu-id="eaa0e-129">Beide Versionen des Anbieters verfügen über die gleiche ID.</span><span class="sxs-lookup"><span data-stu-id="eaa0e-129">Both versions of the provider have the same ID.</span></span> <span data-ttu-id="eaa0e-130">Um anzugeben, ob die [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Laufzeit eine verfügbare 64-Bit-Version des Anbieters verwenden soll, müssen Sie die Run64BitRuntime-Eigenschaft des [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Projekts festlegen.</span><span class="sxs-lookup"><span data-stu-id="eaa0e-130">To specify whether the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] runtime uses an available 64-bit version of the provider, you set the Run64BitRuntime property of the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span> <span data-ttu-id="eaa0e-131">Wenn die Run64BitRuntime-Eigenschaft auf festgelegt ist `true` , findet und verwendet die Common Language Runtime den 64-Bit-Anbieter. wenn Run64BitRuntime ist `false` , findet und verwendet die Laufzeit den 32-Bit-Anbieter.</span><span class="sxs-lookup"><span data-stu-id="eaa0e-131">If the Run64BitRuntime property is set to `true`, the runtime finds and uses the 64-bit provider; if Run64BitRuntime is `false`, the runtime finds and uses the 32-bit provider.</span></span> <span data-ttu-id="eaa0e-132">Weitere Informationen zu Eigenschaften, die Sie in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Projekten festlegen können, finden Sie unter [Integration Services- und Studio-Umgebungen &#40;SSIS&#41;](integration-services-ssis-development-and-management-tools.md).</span><span class="sxs-lookup"><span data-stu-id="eaa0e-132">For more information about properties you can set on [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] projects, see [Integration Services &#40;SSIS&#41; and Studio Environments](integration-services-ssis-development-and-management-tools.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="eaa0e-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eaa0e-133">See Also</span></span>
 <span data-ttu-id="eaa0e-134">Ablauf [Steuerungs](control-flow/control-flow.md) [Datenfluss](data-flow/data-flow.md) [Integration Services &#40;SSIS-&#41; Ereignishandler](integration-services-ssis-event-handlers.md)</span><span class="sxs-lookup"><span data-stu-id="eaa0e-134">[Control Flow](control-flow/control-flow.md) [Data Flow](data-flow/data-flow.md) [Integration Services &#40;SSIS&#41; Event Handlers](integration-services-ssis-event-handlers.md)</span></span>

