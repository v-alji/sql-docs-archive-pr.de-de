---
title: 'Schritt 3: Hinzufügen und Konfigurieren eines OLE DB-Verbindungs-Managers | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: e7b74cba-a0e5-4478-af12-3f81b9484e9e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3bc4c885ce6c39c72031dd3b528a769cd47ac8f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618142"
---
# <a name="step-3-adding-and-configuring-an-ole-db-connection-manager"></a><span data-ttu-id="2564a-102">Schritt 3: Hinzufügen und Konfigurieren eines OLE DB-Verbindungs-Managers</span><span class="sxs-lookup"><span data-stu-id="2564a-102">Step 3: Adding and Configuring an OLE DB Connection Manager</span></span>
  <span data-ttu-id="2564a-103">Nach dem Hinzufügen eines Flatfile-Verbindungs-Managers zum Herstellen einer Verbindung mit der Datenquelle besteht die nächste Aufgabe im Hinzufügen eines OLE DB-Verbindungs-Managers zum Herstellen einer Verbindung mit dem Ziel.</span><span class="sxs-lookup"><span data-stu-id="2564a-103">After you have added a Flat File connection manager to connect to the data source, the next task is to add an OLE DB connection manager to connect to the destination.</span></span> <span data-ttu-id="2564a-104">Ein OLE DB-Verbindungs-Manager ermöglicht einem Paket das Extrahieren von Daten aus einer oder das Laden von Daten in eine OLE DB-kompatible(n) Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="2564a-104">An OLE DB connection manager enables a package to extract data from or load data into any OLE DB-compliant data source.</span></span> <span data-ttu-id="2564a-105">Mithilfe des OLE DB-Verbindungs-Managers können Sie den Server, die Authentifizierungsmethode und die Standarddatenbank für die Verbindung angeben.</span><span class="sxs-lookup"><span data-stu-id="2564a-105">Using the OLE DB Connection manager, you can specify the server, the authentication method, and the default database for the connection.</span></span>  
  
 <span data-ttu-id="2564a-106">In dieser Lektion erstellen Sie einen OLE DB-Verbindungs-Manager, der die Windows-Authentifizierung zum Herstellen einer Verbindung mit der lokalen Instanz von **AdventureWorksDB2012**verwendet.</span><span class="sxs-lookup"><span data-stu-id="2564a-106">In this lesson, you will create an OLE DB connection manager that uses Windows Authentication to connect to the local instance of **AdventureWorksDB2012**.</span></span> <span data-ttu-id="2564a-107">Der von Ihnen erstellte OLE DB-Verbindungs-Manager wird auch von anderen Komponenten referenziert, die Sie später in diesem Lernprogramm erstellen werden. Dazu gehören die Transformation zum Suchen und das OLE DB-Ziel.</span><span class="sxs-lookup"><span data-stu-id="2564a-107">The OLE DB connection manager that you create will also be referenced by other components that you will create later in this tutorial, such as the Lookup transformation and the OLE DB destination.</span></span>  
  
### <a name="to-add-and-configure-an-ole-db-connection-manager-to-the-ssis-package"></a><span data-ttu-id="2564a-108">So fügen Sie dem SSIS-Paket einen OLE DB-Verbindungs-Manager hinzu und konfigurieren ihn</span><span class="sxs-lookup"><span data-stu-id="2564a-108">To add and configure an OLE DB Connection Manager to the SSIS package</span></span>  
  
1.  <span data-ttu-id="2564a-109">Klicken Sie mit der rechten Maustaste auf eine beliebige Stelle im **Verbindungs-Manager** -Bereich und anschließend auf **Neue OLE DB-Verbindung**.</span><span class="sxs-lookup"><span data-stu-id="2564a-109">Right-click anywhere in the **Connection Managers** area, and then click **New OLE DB Connection**.</span></span>  
  
2.  <span data-ttu-id="2564a-110">Klicken Sie im Dialogfeld **OLE DB-Verbindungs-Manager konfigurieren** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="2564a-110">In the **Configure OLE DB Connection Manager** dialog box, click **New**.</span></span>  
  
3.  <span data-ttu-id="2564a-111">Geben Sie für **Servername**den Namen **localhost**ein.</span><span class="sxs-lookup"><span data-stu-id="2564a-111">For **Server name**, enter **localhost**.</span></span>  
  
     <span data-ttu-id="2564a-112">Wenn Sie localhost als Servernamen angeben, stellt der Verbindungs-Manager eine Verbindung mit der Standardinstanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] auf dem lokalen Computer her.</span><span class="sxs-lookup"><span data-stu-id="2564a-112">When you specify localhost as the server name, the connection manager connects to the default instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] on the local computer.</span></span> <span data-ttu-id="2564a-113">Wenn Sie eine Remoteinstanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]verwenden möchten, ersetzen Sie localhost durch den Namen des Servers, mit dem Sie eine Verbindung herstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="2564a-113">To use a remote instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], replace localhost with the name of the server to which you want to connect.</span></span>  
  
4.  <span data-ttu-id="2564a-114">Überprüfen Sie in der Gruppe **Am Server anmelden** , ob **Windows-Authentifizierung verwenden** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="2564a-114">In the **Log on to the server** group, verify that **Use Windows Authentication** is selected.</span></span>  
  
5.  <span data-ttu-id="2564a-115">Geben Sie in der Gruppe **Verbindung mit einer Datenbank herstellen** im Feld **Datenbanknamen eingeben oder** auswählen den Text ein, oder wählen Sie ihn aus `AdventureWorksDW2012` .</span><span class="sxs-lookup"><span data-stu-id="2564a-115">In the **Connect to a database** group, in the **Select or enter a database name** box, type or select `AdventureWorksDW2012`.</span></span>  
  
6.  <span data-ttu-id="2564a-116">Klicken Sie auf **Verbindung testen** , um zu überprüfen, ob die von Ihnen angegebenen Verbindungseinstellungen gültig sind.</span><span class="sxs-lookup"><span data-stu-id="2564a-116">Click **Test Connection** to verify that the connection settings you have specified are valid.</span></span>  
  
7.  <span data-ttu-id="2564a-117">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="2564a-117">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="2564a-118">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="2564a-118">Click **OK**.</span></span>  
  
9. <span data-ttu-id="2564a-119">Überprüfen Sie im Dialogfeld **OLE DB-Verbindungs-Manager konfigurieren** im Bereich **Datenverbindungen** , ob **localhost.AdventureWorksDW2012** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="2564a-119">In the **Data Connections** pane of the **Configure OLE DB Connection Manager** dialog box, verify that **localhost.AdventureWorksDW2012** is selected.</span></span>  
  
10. <span data-ttu-id="2564a-120">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="2564a-120">Click **OK**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="2564a-121">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="2564a-121">Next Task in Lesson</span></span>  
 [<span data-ttu-id="2564a-122">Schritt 4: Hinzufügen eines Datenflusstasks zum Paket</span><span class="sxs-lookup"><span data-stu-id="2564a-122">Step 4: Adding a Data Flow Task to the Package</span></span>](lesson-1-4-adding-a-data-flow-task-to-the-package.md)  
  
## <a name="see-also"></a><span data-ttu-id="2564a-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2564a-123">See Also</span></span>  
 [<span data-ttu-id="2564a-124">OLE DB-Verbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="2564a-124">OLE DB Connection Manager</span></span>](connection-manager/ole-db-connection-manager.md)  
  
  
