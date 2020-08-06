---
title: Ausführen der Data Quality-Clientanwendung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.browseforservers.f1
- sql12.dqs.connecttoserver.f1
ms.assetid: 0b2aa202-7ab2-4c9d-b0f1-802588053a1e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 45372ce22fd1b18f0ec13f7a7fd76a369b78dfd6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726290"
---
# <a name="run-the-data-quality-client-application"></a><span data-ttu-id="3d91f-102">Ausführen der Data Quality-Clientanwendung</span><span class="sxs-lookup"><span data-stu-id="3d91f-102">Run the Data Quality Client Application</span></span>
  <span data-ttu-id="3d91f-103">Sie können [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) verwenden, indem Sie [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] ausführen und sich bei einem [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] anmelden.</span><span class="sxs-lookup"><span data-stu-id="3d91f-103">You can use [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) by running [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)], and logging on to a [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3d91f-104">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="3d91f-104">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="3d91f-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="3d91f-105">Prerequisites</span></span>  
 <span data-ttu-id="3d91f-106">Sie müssen die Installation des [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] durch Ausführen der Datei DQSInstaller.exe abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="3d91f-106">You must have completed the [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] installation by running the DQSInstaller.exe file.</span></span> <span data-ttu-id="3d91f-107">Weitere Informationen finden Sie unter [Ausführen von DQSInstaller.exe zum Abschließen der Installation von Data Quality Server](install-windows/run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span><span class="sxs-lookup"><span data-stu-id="3d91f-107">For more information, see [Run DQSInstaller.exe to Complete Data Quality Server Installation](install-windows/run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3d91f-108">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="3d91f-108">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3d91f-109">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="3d91f-109">Permissions</span></span>  
 <span data-ttu-id="3d91f-110">Um sich bei [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)]anzumelden, muss der Benutzer einer der drei Rollen (dqs_administrator, dqs_kb_editor oder dqs_kb_operator) in der DQS_MAIN-Datenbank angehören.</span><span class="sxs-lookup"><span data-stu-id="3d91f-110">You must have one of the three DQS roles (dqs_adminstrator, dqs_kb_editor, or dqs_kb_operator) granted on the DQS_MAIN database to be able to log on to [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span></span>  
  
##  <a name="run-data-quality-client"></a><a name="Run"></a><span data-ttu-id="3d91f-111">Ausführen Data Quality-Client</span><span class="sxs-lookup"><span data-stu-id="3d91f-111">Run Data Quality Client</span></span>  
 <span data-ttu-id="3d91f-112">Um [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] auf dem Computer auszuführen, auf dem Sie ihn installiert haben, fahren Sie wie folgt fort:</span><span class="sxs-lookup"><span data-stu-id="3d91f-112">To run [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] on the computer where you have installed it, proceed as follows:</span></span>  
  
1.  <span data-ttu-id="3d91f-113">Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme**, klicken Sie auf **[!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]** und anschließend auf **Data Quality Services**, und klicken Sie dann auf **Data Quality Client**.</span><span class="sxs-lookup"><span data-stu-id="3d91f-113">Click **Start**, point to **All Programs**, click **[!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]**, click **Data Quality Services**, and then click **Data Quality Client**.</span></span>  
  
2.  <span data-ttu-id="3d91f-114">Führen Sie folgende Aktionen im Dialogfeld **Mit Server verbinden** aus:</span><span class="sxs-lookup"><span data-stu-id="3d91f-114">In the **Connect to Server** dialog box:</span></span>  
  
    1.  <span data-ttu-id="3d91f-115">Geben Sie den Server an, mit dem Sie die [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] -Anwendung verbinden möchten.</span><span class="sxs-lookup"><span data-stu-id="3d91f-115">Specify the server that you want to connect the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] application to.</span></span> <span data-ttu-id="3d91f-116">Wählen Sie **(LOCAL)** aus, um eine Verbindung mit [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] auf dem lokalen Computer herzustellen.</span><span class="sxs-lookup"><span data-stu-id="3d91f-116">Select **(LOCAL)** to connect to [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] on the local computer.</span></span> <span data-ttu-id="3d91f-117">Sie können auch auf den Pfeil nach unten klicken und auswählen **\<Browse network for more servers>** , um eine Verbindung mit einem anderen Server herzustellen (oder um eine Verbindung mit dem lokalen Server nach Name herzustellen).</span><span class="sxs-lookup"><span data-stu-id="3d91f-117">You can also click the down arrow and select **\<Browse network for more servers>** to connect to a different server (or to connect to the local server by name).</span></span> <span data-ttu-id="3d91f-118">Das Dialogfeld **Nach Servern suchen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3d91f-118">The **Browse for Servers** dialog box will be displayed.</span></span> <span data-ttu-id="3d91f-119">Sie können auf der Registerkarte **Lokale Server** oder auf der Registerkarte **Netzwerkserver** einen Server auswählen.</span><span class="sxs-lookup"><span data-stu-id="3d91f-119">You can select a server in the **Local Servers** tab or in the **Network Servers** tab.</span></span>  
  
    2.  <span data-ttu-id="3d91f-120">Wenn Sie die Datenübertragung zwischen [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] und [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] verschlüsseln möchten, klicken Sie auf **Optionen**, und aktivieren Sie dann das Kontrollkästchen **Verbindung verschlüsseln**.</span><span class="sxs-lookup"><span data-stu-id="3d91f-120">If you want to encrypt data transfer between [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] and [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)], click **Options**, and then select the **Encrypt Connection** check box.</span></span>  
  
3.  <span data-ttu-id="3d91f-121">Klicken Sie auf **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="3d91f-121">Click **Connect**.</span></span>  
  
 <span data-ttu-id="3d91f-122">Der [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] -Startbildschirm wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3d91f-122">The [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen appears.</span></span> <span data-ttu-id="3d91f-123">Weitere Informationen hierzu finden Sie unter [Startbildschirm des Data Quality-Clients](../../2014/data-quality-services/data-quality-client-home-screen.md).</span><span class="sxs-lookup"><span data-stu-id="3d91f-123">For more information, see [Data Quality Client Home Screen](../../2014/data-quality-services/data-quality-client-home-screen.md).</span></span>  
  
  
