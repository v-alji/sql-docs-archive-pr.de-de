---
title: OData-Verbindungs-Manager | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 3caa4372-aff3-4c0f-9ecd-97870948b8d0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 46eedaa008b284661fd1d364d2e2bc87c373a9f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619266"
---
# <a name="odata-connection-manager"></a><span data-ttu-id="599ea-102">OData-Verbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="599ea-102">OData Connection Manager</span></span>
  <span data-ttu-id="599ea-103">Mithilfe eines OData-Verbindungs-Managers kann ein Paket eine Verbindung mit einer OData-Quelle herstellen.</span><span class="sxs-lookup"><span data-stu-id="599ea-103">An OData connection manager enables a package to connect to an OData source.</span></span> <span data-ttu-id="599ea-104">Eine OData-Quellkomponente stellt über einen OData-Verbindungs-Manager eine Verbindung mit einer OData-Quelle her und verwendet die Daten des Diensts.</span><span class="sxs-lookup"><span data-stu-id="599ea-104">An OData Source component connects to an OData source using an OData connection manager and consumes data from the service.</span></span> <span data-ttu-id="599ea-105">Ausführliche Informationen einschließlich Installationsanweisungen für diese Komponenten finden Sie im Abschnitt [odata-Quelle](../data-flow/odata-source.md).</span><span class="sxs-lookup"><span data-stu-id="599ea-105">See [OData Source](../data-flow/odata-source.md)section for detailed information including the installation instructions for these components.</span></span>  
  
## <a name="adding-connection-manager-to-an-ssis-package"></a><span data-ttu-id="599ea-106">Hinzufügen des Verbindungs-Managers zu einem SSIS-Paket</span><span class="sxs-lookup"><span data-stu-id="599ea-106">Adding Connection Manager to an SSIS Package</span></span>  
 <span data-ttu-id="599ea-107">Sie können einem SSIS-Paket einen neuen OData-Verbindungs-Manager auf drei Arten hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="599ea-107">You can add a new OData Connection Manager to an SSIS package in three ways:</span></span>  
  
-   <span data-ttu-id="599ea-108">Klicken Sie im **Quellen-Editor für OData** auf die Schaltfläche **Neu...** .</span><span class="sxs-lookup"><span data-stu-id="599ea-108">Click the **New...** button in the **OData Source Editor**</span></span>  
  
-   <span data-ttu-id="599ea-109">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf **Verbindungs-Manager** , und klicken Sie auf **neuer Verbindungs-Manager**.</span><span class="sxs-lookup"><span data-stu-id="599ea-109">Right-click **Connection Managers** folder in the **Solution Explorer** and click **New Connection Manager**.</span></span> <span data-ttu-id="599ea-110">Wählen Sie unter **Typ des Verbindungs-Managers** die Option **ODATA**aus.</span><span class="sxs-lookup"><span data-stu-id="599ea-110">Select **ODATA** for **Connection manager type**.</span></span>  
  
-   <span data-ttu-id="599ea-111">Klicken Sie mit der rechten Maustaste auf den Bereich **Verbindungs-Manager** unten im Paket-Designer, und wählen Sie **neue Verbindung...** aus. Wählen Sie **odata** als **Typ des Verbindungs-Managers**aus.</span><span class="sxs-lookup"><span data-stu-id="599ea-111">Right-click in the **Connection Managers** pane at the bottom of the package designer, and select **New Connection...**. Select **ODATA** for **Connection manager type**.</span></span>  
  
## <a name="connection-manager-authentication"></a><span data-ttu-id="599ea-112">Verbindungs-Manager-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="599ea-112">Connection Manager Authentication</span></span>  
 <span data-ttu-id="599ea-113">Der OData-Verbindungs-Manager unterstützt zwei Authentifizierungsmodi.</span><span class="sxs-lookup"><span data-stu-id="599ea-113">The OData Connection Manager supports two modes of authentication.</span></span>  
  
-   <span data-ttu-id="599ea-114">Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="599ea-114">Windows Authentication</span></span>  
  
-   <span data-ttu-id="599ea-115">Standardauthentifizierung (Benutzername und Kennwort)</span><span class="sxs-lookup"><span data-stu-id="599ea-115">Basic Authentication (username/password)</span></span>  
  
 <span data-ttu-id="599ea-116">Für den anonymen Zugriff wählen Sie die Option Windows-Authentifizierung aus.</span><span class="sxs-lookup"><span data-stu-id="599ea-116">For anonymous access, select the Windows Authentication option</span></span>  
  
### <a name="specifying-and-securing-credentials"></a><span data-ttu-id="599ea-117">Festlegen und Sichern von Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="599ea-117">Specifying and Securing Credentials</span></span>  
 <span data-ttu-id="599ea-118">Wenn der odata-Dienst die Standard Authentifizierung erfordert, können Sie im [odata-Verbindungs-Manager-Editor](../odata-connection-manager-editor.md)einen Benutzernamen und ein Kennwort angeben.</span><span class="sxs-lookup"><span data-stu-id="599ea-118">If your OData service requires basic authentication, you can specify a username and password in the [OData Connection Manager Editor](../odata-connection-manager-editor.md).</span></span> <span data-ttu-id="599ea-119">Die Werte, die Sie in den Editor eingeben, werden im Paket beibehalten.</span><span class="sxs-lookup"><span data-stu-id="599ea-119">The values you enter in the editor are persisted in the package.</span></span> <span data-ttu-id="599ea-120">Der Kennwortwert wird gemäß der Schutzebene des Pakets verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="599ea-120">The password value is encrypted according to the package protection level.</span></span>  
  
 <span data-ttu-id="599ea-121">Es gibt mehrere Möglichkeiten, den Benutzernamen- und Kennwortwert zu externalisieren/parametrisieren.</span><span class="sxs-lookup"><span data-stu-id="599ea-121">There are multiple ways to externalize/parameterize the username and password values.</span></span> <span data-ttu-id="599ea-122">Die beiden Hauptmethoden in [!INCLUDE[ssISversion11](../../includes/ssisversion11-md.md)] bestehen darin, Parameter zu verwenden oder die Eigenschaften des Verbindungs-Managers beim Ausführen des Pakets in SQL Server Management Studio direkt festzulegen.</span><span class="sxs-lookup"><span data-stu-id="599ea-122">The two primary ways of doing this in [!INCLUDE[ssISversion11](../../includes/ssisversion11-md.md)] are by using parameters, or by setting the connection manager properties directly when you run the package using SQL Server Management Studio.</span></span>  
  
## <a name="odata-connection-manager-properties"></a><span data-ttu-id="599ea-123">Eigenschaften des OData-Verbindungs-Managers</span><span class="sxs-lookup"><span data-stu-id="599ea-123">OData Connection Manager Properties</span></span>  
 <span data-ttu-id="599ea-124">In der folgenden Liste sind einige Eigenschaften des OData-Verbindungs-Managers beschrieben, die Sie ändern können.</span><span class="sxs-lookup"><span data-stu-id="599ea-124">The following list describes some of the OData Connection Manager properties that you may want to change.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="599ea-125">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="599ea-125">Property</span></span>|<span data-ttu-id="599ea-126">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="599ea-126">Description</span></span>|  
|<span data-ttu-id="599ea-127">url</span><span class="sxs-lookup"><span data-stu-id="599ea-127">Url</span></span>|<span data-ttu-id="599ea-128">Die URL zum Dienstdokument.</span><span class="sxs-lookup"><span data-stu-id="599ea-128">URL to the service document.</span></span>|  
|<span data-ttu-id="599ea-129">UserName</span><span class="sxs-lookup"><span data-stu-id="599ea-129">UserName</span></span>|<span data-ttu-id="599ea-130">Der Benutzername, der für die Standardauthentifizierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="599ea-130">Username to use for Basic Authentication.</span></span>|  
|<span data-ttu-id="599ea-131">Kennwort</span><span class="sxs-lookup"><span data-stu-id="599ea-131">Password</span></span>|<span data-ttu-id="599ea-132">Das Kennwort, das für die Standardauthentifizierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="599ea-132">Password to use for Basic Authentication.</span></span>|  
|<span data-ttu-id="599ea-133">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="599ea-133">ConnectionString</span></span>|<span data-ttu-id="599ea-134">Stellt weitere Eigenschaften des Verbindungs-Managers dar.</span><span class="sxs-lookup"><span data-stu-id="599ea-134">Reflects other properties of the connection manager.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="599ea-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="599ea-135">See Also</span></span>  
 [<span data-ttu-id="599ea-136">OData-Verbindungs-Manager-Editor</span><span class="sxs-lookup"><span data-stu-id="599ea-136">OData Connection Manager Editor</span></span>](../odata-connection-manager-editor.md)  
  
  
