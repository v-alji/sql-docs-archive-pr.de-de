---
title: Veröffentlichen einer Datenbank (SQL Server Management Studio) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: 98b2914e-7147-40af-ba7d-87253bbe8bf9
author: stevestein
ms.author: sstein
ms.openlocfilehash: 652f2341d24c19e6c5ce34196b0e1c4dc5b09084
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617097"
---
# <a name="publish-a-database-sql-server-management-studio"></a><span data-ttu-id="c9e95-102">Veröffentlichen einer Datenbank (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="c9e95-102">Publish a Database (SQL Server Management Studio)</span></span>
  <span data-ttu-id="c9e95-103">Mit dem **Assistenten zum Generieren und Veröffentlichen von Skripts** können Sie eine ganze Datenbank oder einzelne Datenbankobjekte in einem Webhostinganbieter veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="c9e95-103">You can use the **Generate and Publish Scripts Wizard** to publish an entire database or individual database objects to a Web hosting provider.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c9e95-104">Die in diesem Thema beschriebene Funktionalität wurde früher vom Datenbankveröffentlichungs-Assistenten bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="c9e95-104">The functionality described in this topic used to be provided by the Publish Database Wizard.</span></span> <span data-ttu-id="c9e95-105">Dessen Veröffentlichungsfunktionalität wurde dem Assistenten zum Generieren und Veröffentlichen von Skripts hinzugefügt, und der Datenbankveröffentlichungs-Assistent wird in der alten Form nicht mehr bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="c9e95-105">The publishing functionality has been added to the Generate and Publish Scripts Wizard, and the Publish Database Wizard has been discontinued.</span></span>  
  
## <a name="generate-and-publish-scripts-wizard"></a><span data-ttu-id="c9e95-106">Assistenten zum Generieren und Veröffentlichen von Skripts</span><span class="sxs-lookup"><span data-stu-id="c9e95-106">Generate and Publish Scripts Wizard</span></span>  
 <span data-ttu-id="c9e95-107">Der Assistent zum Generieren und Veröffentlichen von Skripts kann verwendet werden, um eine Datenbank oder ausgewählte Datenbankobjekte in einem Webhostinganbieter zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="c9e95-107">The Generate and Publish Scripts Wizard can be used to publish a database or selected database objects to a Web hosting provider.</span></span> <span data-ttu-id="c9e95-108">Ein SQL Server-Webhostinganbieter ist eine Konnektivitätsschnittstelle zu einem Webdienst.</span><span class="sxs-lookup"><span data-stu-id="c9e95-108">A SQL Server Web hosting provider is a connectivity interface to a Web service.</span></span> <span data-ttu-id="c9e95-109">Der Webdienst wird mithilfe eines Datenbank-Veröffentlichungsdienste-Projekts vom SQL Server Hosting Toolkit aus auf der CodePlex-Website erstellt.</span><span class="sxs-lookup"><span data-stu-id="c9e95-109">The Web service is created by using the Database Publishing Services project from the SQL Server Hosting Toolkit on CodePlex.</span></span> <span data-ttu-id="c9e95-110">Mithilfe des Webdiensts können Webhoster-Kunden ihre Datenbanken problemlos im Dienst veröffentlichen. Sie verwenden dazu den Assistenten zum Generieren und Veröffentlichen von Skripts.</span><span class="sxs-lookup"><span data-stu-id="c9e95-110">The Web service makes it easy for the Web hoster customers to publish their databases to the service by using the Generate and Publish Scripts Wizard.</span></span> <span data-ttu-id="c9e95-111">Weitere Informationen zum Herunterladen des SQL Server Hosting Toolkits finden Sie unter [SQL Server Database Publishing Services](https://go.microsoft.com/fwlink/?LinkId=142025).</span><span class="sxs-lookup"><span data-stu-id="c9e95-111">For more information about downloading the SQL Server Hosting Toolkit, see [SQL Server Database Publishing Services](https://go.microsoft.com/fwlink/?LinkId=142025).</span></span>  
  
 <span data-ttu-id="c9e95-112">Der Assistent zum Generieren und Veröffentlichen von Skripts kann außerdem verwendet werden, um ein Skript zum Übertragen einer Datenbank zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c9e95-112">The Generate and Publish Scripts Wizard can also be used to create a script for transferring a database.</span></span>  
  
#### <a name="to-publish-a-database-to-a-web-service"></a><span data-ttu-id="c9e95-113">So veröffentlichen Sie eine Datenbank in einem Webdienst</span><span class="sxs-lookup"><span data-stu-id="c9e95-113">To publish a database to a Web service</span></span>  
  
1.  <span data-ttu-id="c9e95-114">Erweitern Sie im Objekt-Explorer **Datenbanken**, klicken Sie mit der rechten Maustaste auf eine Datenbank, zeigen Sie auf **Tasks**, und klicken Sie dann auf **Skripts generieren und veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="c9e95-114">In Object Explorer, expand **Databases**, right-click a database, point to **Tasks**, and then click **Generate and Publish Scripts**.</span></span> <span data-ttu-id="c9e95-115">Führen Sie die im Assistenten angegebenen Schritte aus, um ein Skript für die Veröffentlichung der Datenbankobjekte zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c9e95-115">Follow the steps in the wizard to script the database objects for publishing.</span></span>  
  
2.  <span data-ttu-id="c9e95-116">Wählen Sie auf der Seite **Objekte auswählen** die Objekte aus, die im Webhostingdienst veröffentlicht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c9e95-116">On the **Choose Objects** page, select the objects to be published to the Web hosting service.</span></span>  
  
3.  <span data-ttu-id="c9e95-117">Wählen Sie auf der Seite **Skriptoptionen festlegen** die Option **In Webdienst veröffentlichen**aus.</span><span class="sxs-lookup"><span data-stu-id="c9e95-117">On the **Set Scripting Options** page, select **Publish to Web Service**.</span></span>  
  
    1.  <span data-ttu-id="c9e95-118">Geben Sie im Feld **Anbieter** den Anbieter für den Webdienst an.</span><span class="sxs-lookup"><span data-stu-id="c9e95-118">In the **Provider** box, specify the provider for your Web service.</span></span> <span data-ttu-id="c9e95-119">Wenn Sie keinen Webhostinganbieter konfiguriert haben, wählen Sie **Anbieter verwalten** aus und verwenden das Dialogfeld **Anbieter verwalten** , um einen Anbieter für den Webdienst zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c9e95-119">If you have not configured a Web hosting provider, select **Manage Providers** and use the **Manage Providers** dialog box to configure a provider for your Web service.</span></span>  
  
    2.  <span data-ttu-id="c9e95-120">Um erweiterte Veröffentlichungsoptionen anzugeben, klicken Sie im Abschnitt **In Webdienst veröffentlichen** auf die Schaltfläche **Erweitert** .</span><span class="sxs-lookup"><span data-stu-id="c9e95-120">To specify advanced publishing options, select the **Advanced** button in the **Publish to Web Service** section.</span></span>  
  
4.  <span data-ttu-id="c9e95-121">Überprüfen Sie die Auswahl auf der Seite **Zusammenfassung** .</span><span class="sxs-lookup"><span data-stu-id="c9e95-121">On the **Summary** page, review your selections.</span></span> <span data-ttu-id="c9e95-122">Klicken Sie auf **Zurück** , um die Auswahl zu ändern.</span><span class="sxs-lookup"><span data-stu-id="c9e95-122">Click **Previous** to change your selections.</span></span> <span data-ttu-id="c9e95-123">Klicken Sie auf **Weiter** , um die ausgewählten Objekte zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="c9e95-123">Click **Next** to publish the objects you selected.</span></span>  
  
5.  <span data-ttu-id="c9e95-124">Überwachen Sie auf der Seite **Skripts speichern oder veröffentlichen** den Status der Veröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="c9e95-124">On the **Save or Publish Scripts** page, monitor the progress of the publication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9e95-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c9e95-125">See Also</span></span>  
 <span data-ttu-id="c9e95-126">[Erstellen von Skripts &#40;SQL Server Management Studio&#41;](../scripting/generate-scripts-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="c9e95-126">[Generate Scripts &#40;SQL Server Management Studio&#41;](../scripting/generate-scripts-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="c9e95-127">Kopieren von Datenbanken auf andere Server</span><span class="sxs-lookup"><span data-stu-id="c9e95-127">Copy Databases to Other Servers</span></span>](copy-databases-to-other-servers.md)  
  
  
