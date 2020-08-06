---
title: Erteilen von Berechtigungen für Data Mining Strukturen und Modelle (Analysis Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.roledesignerdialog.miningmodels.f1
helpviewer_keywords:
- data mining [Analysis Services], security
- permissions [Analysis Services], mining models
- mining models [Analysis Services], security
- mining structures [Analysis Services], security
- permissions [Analysis Services], mining structures
- user access rights [Analysis Services], mining structures
- user access rights [Analysis Services], mining models
ms.assetid: a0008004-e2b7-47db-acad-5fe7e12b130f
author: minewiskan
ms.author: owend
ms.openlocfilehash: d0db849551bdb38615f280b123c98f0e9d3053d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718799"
---
# <a name="grant-permissions-on-data-mining-structures-and-models-analysis-services"></a><span data-ttu-id="04438-102">Erteilen von Berechtigungen für Data Mining-Strukturen und -Modellen (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="04438-102">Grant permissions on data mining structures and models (Analysis Services)</span></span>
  <span data-ttu-id="04438-103">Standardmäßig besitzt nur ein Analysis Services-Serveradministrator Berechtigungen zum Anzeigen von Data Mining-Strukturen oder Miningmodellen in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="04438-103">By default, only an Analysis Services server administrator has permissions to view data mining structures or mining models in the database.</span></span> <span data-ttu-id="04438-104">Befolgen Sie die Anweisungen unten, um Berechtigungen für Benutzer, die keine Administratoren sind, zu vergeben.</span><span class="sxs-lookup"><span data-stu-id="04438-104">Follow the instructions below to grant permissions to non-administrator users.</span></span>  
  
## <a name="set-permissions-to-access-a-mining-structure"></a><span data-ttu-id="04438-105">Festlegen von Berechtigungen für den Zugriff auf eine Miningstruktur</span><span class="sxs-lookup"><span data-stu-id="04438-105">Set permissions to access a mining structure</span></span>  
  
1.  <span data-ttu-id="04438-106">Verbinden Sie sich in SSMS mit Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="04438-106">In SSMS, connect to Analysis Services.</span></span> <span data-ttu-id="04438-107">Falls Sie Hilfe bei den Schritten brauchen, gehen Sie unter [Herstellen einer Verbindung von Clientanwendungen &#40;Analysis Services&#41;](../instances/connect-from-client-applications-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="04438-107">See [Connect from client applications &#40;Analysis Services&#41;](../instances/connect-from-client-applications-analysis-services.md) if you need help with the steps.</span></span>  
  
2.  <span data-ttu-id="04438-108">Öffnen Sie den Ordner **Datenbanken** in Objekt-Explorer, und wählen Sie eine Datenbank aus.</span><span class="sxs-lookup"><span data-stu-id="04438-108">Open the **Databases** folder, and select a database in Object Explorer.</span></span>  
  
3.  <span data-ttu-id="04438-109">Klicken Sie mit der rechten Maustaste auf **Rollen** , und wählen Sie **Neue Rolle**aus.</span><span class="sxs-lookup"><span data-stu-id="04438-109">Right-click **Roles** and choose **New Role**.</span></span>  
  
4.  <span data-ttu-id="04438-110">Geben Sie auf der Seite "Allgemein" einen Namen und optional eine Beschreibung ein.</span><span class="sxs-lookup"><span data-stu-id="04438-110">In the General page, enter a name, and optionally, a description.</span></span> <span data-ttu-id="04438-111">Diese Seite enthält auch mehrere Datenbankberechtigungen wie beispielsweise "Vollzugriff", "Datenbank verarbeiten" und "Definition lesen".</span><span class="sxs-lookup"><span data-stu-id="04438-111">The page also contains several database permissions, such as Full Control, Process Database, and Read Definition.</span></span> <span data-ttu-id="04438-112">Für den Data Mining-Zugriff ist keine dieser Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="04438-112">None of these permissions are needed for data mining access.</span></span> <span data-ttu-id="04438-113">Weitere Informationen zu Datenbankberechtigungen finden Sie unter [Erteilen von Datenbankberechtigungen &#40;Analysis Services&#41;](grant-database-permissions-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="04438-113">See [Grant database permissions &#40;Analysis Services&#41;](grant-database-permissions-analysis-services.md) for more information about database permissions.</span></span>  
  
5.  <span data-ttu-id="04438-114">Wählen Sie im Bereich **Miningstruktur** entweder **Lesen** oder **Lesen/Schreiben**  für jede Data Mining-Struktur aus.</span><span class="sxs-lookup"><span data-stu-id="04438-114">In the **Mining Structure** pane, select **Read** or **Read/Write**  for each data mining structure.</span></span>  
  
6.  <span data-ttu-id="04438-115">Geben Sie im **Mitgliedschaft** sbereich die Windows-Konten von Benutzern und Gruppen ein, die mit dieser Rolle eine Verbindung zu Analysis Services herstellen.</span><span class="sxs-lookup"><span data-stu-id="04438-115">In the **Membership** pane, enter the Windows user and group accounts that connect to Analysis Services using this role.</span></span>  
  
7.  <span data-ttu-id="04438-116">Klicken Sie auf **OK** , um die Erstellung der Rolle zu abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="04438-116">Click **OK** to finish creating the role.</span></span>  
  
## <a name="set-permissions-to-access-a-mining-model"></a><span data-ttu-id="04438-117">Festlegen von Berechtigungen für den Zugriff auf ein Miningmodell</span><span class="sxs-lookup"><span data-stu-id="04438-117">Set permissions to access a mining model</span></span>  
 <span data-ttu-id="04438-118">Für ein Data Mining-Modell kann eine Rolle entweder über **Lesen** - oder **Lesen/Schreiben** -Berechtigungen verfügen sowie über die Berechtigungen **Drillthrough** und **Definition lesen** , die das Anzeigen und Durchsuchen der zugrunde liegenden Daten ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="04438-118">For a data mining model, a role can have either **Read** or **Read/Write** permissions, as well as **Drillthrough** and **Read Definition** permissions that allow viewing and browsing the underlying data.</span></span>  
  
 <span data-ttu-id="04438-119">**Hinweis** Wenn Sie Drillthrough sowohl für die Miningstruktur als auch für das Miningmodell aktivieren, kann jeder Benutzer, der Mitglied einer Rolle mit Drillthroughberechtigungen für das Miningmodell und die Miningstruktur ist, auch Spalten in der Miningstruktur einsehen, selbst wenn diese Spalten nicht Teil des Miningmodells sind.</span><span class="sxs-lookup"><span data-stu-id="04438-119">**Note** If you enable drillthrough on both the mining structure and the mining model, any user who is a member of a role that has drillthrough permissions on the mining model and the mining structure can also view columns in the mining structure, even if those columns are not included in the mining model.</span></span> <span data-ttu-id="04438-120">Deswegen sollten Sie zum Schutz sensibler Informationen die Datenquellensicht so einrichten, dass persönliche Informationen verborgen sind, und Drillthroughzugriff auf die Miningstruktur nur zulassen, wenn es wirklich erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="04438-120">Therefore, to protect sensitive information, you should set up the data source view to mask personal information, and allow drillthrough access on the mining structure only when necessary.</span></span>  
  
 <span data-ttu-id="04438-121">Um einer Datenbankrolle Lese-/Schreibberechtigungen zu erteilen, muss der Benutzer Mitglied der [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Serverrolle oder ein Mitglied einer [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbankrolle sein, die über die Berechtigung Vollzugriff (Administrator) verfügt.</span><span class="sxs-lookup"><span data-stu-id="04438-121">To grant read or read/write permissions to a database role, a user must be a member of the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] server role or a member of an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database role that has Full Control (Administrator) permissions.</span></span>  
  
1.  <span data-ttu-id="04438-122">Stellen [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Sie in eine Verbindung mit der Instanz von her [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , erweitern Sie in Objekt-Explorer **Rollen** für die entsprechende Datenbank, und klicken Sie dann auf eine Daten Bank Rolle (oder erstellen Sie eine neue Daten Bank Rolle).</span><span class="sxs-lookup"><span data-stu-id="04438-122">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], expand **Roles** for the appropriate database in Object Explorer, and then click a database role (or create a new database role).</span></span>  
  
2.  <span data-ttu-id="04438-123">Suchen Sie im Bereich **Miningstuktur** das Miningmodell in der Liste **Miningmodelle** , und wählen Sie anschließend für dieses Miningmodell die Option **Lesen**, **Lesen/Schreiben**, **Drillthrough**oder **Durchsuchen** aus.</span><span class="sxs-lookup"><span data-stu-id="04438-123">In the **Mining Structure** pane, locate the mining model in the **Mining Models** list, and then select **Read**, **Read/Write**, **Drill Through**, or **Browse** for that mining model.</span></span>  
  
3.  <span data-ttu-id="04438-124">Geben Sie im **Mitgliedschaft** sbereich die Windows-Konten von Benutzern und Gruppen ein, die mit dieser Rolle eine Verbindung zu Analysis Services herstellen.</span><span class="sxs-lookup"><span data-stu-id="04438-124">In the **Membership** pane, enter the Windows user and group accounts that connect to Analysis Services using this role.</span></span>  
  
4.  <span data-ttu-id="04438-125">Klicken Sie auf **OK** , um die Erstellung der Rolle zu abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="04438-125">Click **OK** to finish creating the role.</span></span>  
  
 <span data-ttu-id="04438-126">Wenn Sie eine Datenquelle in einer Drillthroughabfrage verwenden möchten, die die OPENQUERY-Klausel der Data Mining-Erweiterungen (DMX) verwendet, muss die Datenbankrolle auch über Lese-/Schreibberechtigungen für das entsprechende Datenquellenobjekt verfügen.</span><span class="sxs-lookup"><span data-stu-id="04438-126">To use a data source in a drillthrough query that uses the Data Mining Extensions (DMX) OPENQUERY clause, the database role also needs read/write permission on the appropriate data source object.</span></span> <span data-ttu-id="04438-127">Weitere Informationen finden Sie unter [Erteilen von Berechtigungen für ein Datenquellenobjekt &#40;Analysis Services&#41;](grant-permissions-on-a-data-source-object-analysis-services.md) und [OPENQUERY &#40;DMX&#41;](/sql/dmx/source-data-query-openquery).</span><span class="sxs-lookup"><span data-stu-id="04438-127">For more information, see [Grant permissions on a data source object &#40;Analysis Services&#41;](grant-permissions-on-a-data-source-object-analysis-services.md) and [OPENQUERY &#40;DMX&#41;](/sql/dmx/source-data-query-openquery).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="04438-128">Standardmäßig ist die Einreichung von DMX-Abfragen über OPENROWSET deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="04438-128">By default, the submission of DMX queries by using OPENROWSET is disabled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04438-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="04438-129">See Also</span></span>  
 <span data-ttu-id="04438-130">[Erteilen von Server Administrator Berechtigungen &#40;Analysis Services&#41;](../instances/grant-server-admin-rights-to-an-analysis-services-instance.md) </span><span class="sxs-lookup"><span data-stu-id="04438-130">[Grant Server Administrator Permissions &#40;Analysis Services&#41;](../instances/grant-server-admin-rights-to-an-analysis-services-instance.md) </span></span>  
 <span data-ttu-id="04438-131">[Erteilen von Cube-oder Modell Berechtigungen &#40;Analysis Services&#41;](grant-cube-or-model-permissions-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="04438-131">[Grant cube or model permissions &#40;Analysis Services&#41;](grant-cube-or-model-permissions-analysis-services.md) </span></span>  
 <span data-ttu-id="04438-132">[Gewähren von benutzerdefiniertem Zugriff auf Dimensions Daten &#40;Analysis Services&#41;](grant-custom-access-to-dimension-data-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="04438-132">[Grant custom access to dimension data &#40;Analysis Services&#41;](grant-custom-access-to-dimension-data-analysis-services.md) </span></span>  
 [<span data-ttu-id="04438-133">Erteilen von benutzerdefiniertem Zugriff auf Zellendaten &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="04438-133">Grant custom access to cell data &#40;Analysis Services&#41;</span></span>](grant-custom-access-to-cell-data-analysis-services.md)  
  
  
