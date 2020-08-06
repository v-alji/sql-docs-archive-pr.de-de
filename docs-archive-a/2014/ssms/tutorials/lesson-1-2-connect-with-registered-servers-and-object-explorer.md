---
title: Herstellen einer Verbindung mit registrierten Servern und dem Objekt-Explorer | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: d6b3911f-68b4-4483-831b-df89d6400add
author: stevestein
ms.author: sstein
ms.openlocfilehash: b4bc75ad7f3682765dc102064a5621cd541ccd12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695182"
---
# <a name="connect-with-registered-servers-and-object-explorer"></a><span data-ttu-id="36f68-102">Herstellen einer Verbindung mit registrierten Servern und dem Objekt-Explorer</span><span class="sxs-lookup"><span data-stu-id="36f68-102">Connect with Registered Servers and Object Explorer</span></span>
  <span data-ttu-id="36f68-103">Dieses Lernprogramm veranschaulicht die Verwendung von registrierten Servern und Objekt-Explorer.</span><span class="sxs-lookup"><span data-stu-id="36f68-103">This tutorial demonstrates the use of Registered Servers and Object Explorer.</span></span>  
  
 <span data-ttu-id="36f68-104">Dieses Lernprogramm verwendet die Datenbank [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="36f68-104">This tutorial uses the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="36f68-105">Aus Sicherheitsgründen werden die Beispieldatenbanken standardmäßig nicht installiert.</span><span class="sxs-lookup"><span data-stu-id="36f68-105">To help enhance security, by default, the sample databases are not installed.</span></span> <span data-ttu-id="36f68-106">Weitere Informationen finden Sie unter [Installing SQL Server Samples and Sample Databases](http://sqlserversamples.codeplex.com).</span><span class="sxs-lookup"><span data-stu-id="36f68-106">For more information, see [Installing SQL Server Samples and Sample Databases](http://sqlserversamples.codeplex.com).</span></span>  
  
## <a name="connecting-to-servers"></a><span data-ttu-id="36f68-107">Herstellen einer Verbindung mit Servern</span><span class="sxs-lookup"><span data-stu-id="36f68-107">Connecting to Servers</span></span>  
 <span data-ttu-id="36f68-108">Auf der Symbolleiste der Komponente Registrierte Server befinden sich Schaltflächen für [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]und [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="36f68-108">The toolbar of the Registered Servers component has buttons for the [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], and [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="36f68-109">Zur Vereinfachung der Verwaltung können Sie einen oder mehrere dieser Servertypen registrieren.</span><span class="sxs-lookup"><span data-stu-id="36f68-109">You can register one or more of these server types for convenient management.</span></span> <span data-ttu-id="36f68-110">In der folgenden Übung werden Sie die [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Datenbank registrieren.</span><span class="sxs-lookup"><span data-stu-id="36f68-110">Try the following exercise to register the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
#### <a name="to-register-the-database"></a><span data-ttu-id="36f68-111">So registrieren Sie die Datenbank</span><span class="sxs-lookup"><span data-stu-id="36f68-111">To register the database</span></span>  
  
1.  <span data-ttu-id="36f68-112">Klicken Sie auf der Symbolleiste Registrierte Server auf **Datenbank-Engine**, falls erforderlich.</span><span class="sxs-lookup"><span data-stu-id="36f68-112">On the Registered Servers toolbar, click **Database Engine** if you have to.</span></span> <span data-ttu-id="36f68-113">(Dieser Knoten ist möglicherweise bereits ausgewählt.)</span><span class="sxs-lookup"><span data-stu-id="36f68-113">(It may already be selected.)</span></span>  
  
2.  <span data-ttu-id="36f68-114">Erweitern Sie **Datenbank-Engine**.</span><span class="sxs-lookup"><span data-stu-id="36f68-114">Expand **Database Engine**.</span></span>  
  
3.  <span data-ttu-id="36f68-115">Klicken Sie mit der rechten Maustaste auf **Lokale Servergruppen**und anschließend auf **Neue Serverregistrierung**.</span><span class="sxs-lookup"><span data-stu-id="36f68-115">Right-click **Local Server Groups**, and then click **New Server Registration**.</span></span>  
  
4.  <span data-ttu-id="36f68-116">Geben Sie im Dialogfeld **Neue Serverregistrierung** im Textfeld **Servername** den Namen Ihrer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]an.</span><span class="sxs-lookup"><span data-stu-id="36f68-116">In the **New Server Registration** dialog box, in the **Server name** text box, type the name of your instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
5.  <span data-ttu-id="36f68-117">Geben Sie im Feld **Name des registrierten Servers** den Namen [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]ein.</span><span class="sxs-lookup"><span data-stu-id="36f68-117">In the **Registered server name** box, type [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span>  
  
6.  <span data-ttu-id="36f68-118">Wählen Sie auf der Registerkarte **Verbindungs Eigenschaften** in der Liste Verbindung **mit Datenbank herstellen** die Option aus **\<Browse server...>** .</span><span class="sxs-lookup"><span data-stu-id="36f68-118">On the **Connection Properties** tab, in the **Connect to database** list, select **\<Browse server...>**.</span></span>  
  
7.  <span data-ttu-id="36f68-119">Klicken Sie im Dialogfeld **Nach Datenbanken suchen** auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="36f68-119">In the **Browse for Databases** dialog box, click **Yes**.</span></span>  
  
8.  <span data-ttu-id="36f68-120">Wählen Sie im Dialogfeld **Server nach Datenbank durchsuchen** den Eintrag [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="36f68-120">In the **Browse Server for Database** dialog box, select [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], and then click **OK**.</span></span>  
  
9. <span data-ttu-id="36f68-121">Um sicherzustellen, dass der Server ordnungsgemäß registriert wurde, klicken Sie auf **Testen**.</span><span class="sxs-lookup"><span data-stu-id="36f68-121">To verify that the server has been registered correctly, click **Test**.</span></span>  
  
10. <span data-ttu-id="36f68-122">Klicken Sie im Dialogfeld **Neue Serverregistrierung** auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="36f68-122">In the **New Server Registration** dialog box, click **Save**.</span></span>  
  
## <a name="connecting-with-object-explorer"></a><span data-ttu-id="36f68-123">Herstellen einer Verbindung mit dem Objekt-Explorer</span><span class="sxs-lookup"><span data-stu-id="36f68-123">Connecting with Object Explorer</span></span>  
 <span data-ttu-id="36f68-124">Wie die Komponente Registrierte Server kann der Objekt-Explorer eine Verbindung mit [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]und [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]herstellen.</span><span class="sxs-lookup"><span data-stu-id="36f68-124">Like Registered Servers, Object Explorer can connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], and [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
#### <a name="to-connect-with-object-explorer"></a><span data-ttu-id="36f68-125">So stellen Sie eine Verbindung mit dem Objekt-Explorer her</span><span class="sxs-lookup"><span data-stu-id="36f68-125">To connect with Object Explorer</span></span>  
  
1.  <span data-ttu-id="36f68-126">Klicken Sie auf der Symbolleiste vom Objekt-Explorer auf **Verbinden**, um eine Liste der möglichen Verbindungstypen anzuzeigen. Wählen Sie dann **Datenbank-Engine**aus.</span><span class="sxs-lookup"><span data-stu-id="36f68-126">On the toolbar of Object Explorer, click **Connect** for a list of possible connection types, and then select **Database Engine**.</span></span>  
  
2.  <span data-ttu-id="36f68-127">Geben Sie im Dialogfeld **Verbindung mit Server herstellen** im Textfeld **Servername** den Namen Ihrer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]an.</span><span class="sxs-lookup"><span data-stu-id="36f68-127">In the **Connect to Server** dialog box, in the **Server name** text box, type the name of your instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
3.  <span data-ttu-id="36f68-128">Klicken Sie auf **Optionen** , und sehen Sie sich die Auswahlmöglichkeiten an.</span><span class="sxs-lookup"><span data-stu-id="36f68-128">Click **Options** and explore the choices.</span></span>  
  
4.  <span data-ttu-id="36f68-129">Klicken Sie auf **Verbinden**, um eine Verbindung mit dem Server herzustellen.</span><span class="sxs-lookup"><span data-stu-id="36f68-129">To connect to the server, click **Connect**.</span></span> <span data-ttu-id="36f68-130">Wenn bereits eine Verbindung besteht, werden Sie mit dieser Aktion an den Objekt-Explorer zurückgeleitet, und der Fokus wird auf diesen Server festgelegt.</span><span class="sxs-lookup"><span data-stu-id="36f68-130">If you are already connected, this action just returns you to Object Explorer and sets the focus on that server.</span></span>  
  
     <span data-ttu-id="36f68-131">Mit dem Objekt-Explorer können Sie die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Sicherheit, den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent, die Replikation und Datenbank-E-Mail verwalten.</span><span class="sxs-lookup"><span data-stu-id="36f68-131">With Object Explorer you can administer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Security, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, Replication, and Database Mail.</span></span> <span data-ttu-id="36f68-132">Über den Objekt-Explorer können nur einige der Funktionen von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]und [!INCLUDE[ssIS](../../includes/ssis-md.md)]verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="36f68-132">Object Explorer can only manage some of the features of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], and [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span></span> <span data-ttu-id="36f68-133">Für jede dieser Komponenten gibt es zusätzliche, spezialisierte Tools.</span><span class="sxs-lookup"><span data-stu-id="36f68-133">Each of those components has additional specialized tools.</span></span>  
  
5.  <span data-ttu-id="36f68-134">Erweitern Sie im Objekt-Explorer den Ordner **Datenbanken** , und wählen Sie [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]aus.</span><span class="sxs-lookup"><span data-stu-id="36f68-134">In Object Explorer, expand the **Databases** folder and select [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span>  
  
     <span data-ttu-id="36f68-135">Beachten Sie, dass [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] die Systemdatenbanken in einem separaten Ordner präsentiert.</span><span class="sxs-lookup"><span data-stu-id="36f68-135">Notice that [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] presents the system databases in a separate folder.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="36f68-136">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="36f68-136">Next Task in Lesson</span></span>  
 [<span data-ttu-id="36f68-137">Ändern des Umgebungslayouts</span><span class="sxs-lookup"><span data-stu-id="36f68-137">Change the Environment Layout</span></span>](lesson-1-3-change-the-environment-layout.md)  
  
  
