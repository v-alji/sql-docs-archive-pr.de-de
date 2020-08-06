---
title: Erteilen von Berechtigungen für Prozess Datenbanken | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 69ba952e-09ae-49a9-9297-00e32e8e89a8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6ada30e3fb509bd1ffd210485ce0e34b7bf86fb7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608044"
---
# <a name="granting-process-database-permissions"></a><span data-ttu-id="8041d-102">Erteilen von Berechtigungen zum Verarbeiten von Datenbanken</span><span class="sxs-lookup"><span data-stu-id="8041d-102">Granting Process Database Permissions</span></span>
  <span data-ttu-id="8041d-103">Nach dem Installieren einer Instanz von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]verfügen alle Mitglieder der [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Serveradministratorrolle in dieser Instanz über serverweite Berechtigungen, beliebige Tasks innerhalb der Instanz von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]auszuführen.</span><span class="sxs-lookup"><span data-stu-id="8041d-103">After you install an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], all members of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server administrator role in that instance have server-wide permissions to perform any task within the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="8041d-104">Standardmäßig besitzen keine anderen Benutzer die Berechtigung, Objekte in der Instanz von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]zu verwalten oder anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8041d-104">By default, no other users have any permission to administer or view any objects in the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>

 <span data-ttu-id="8041d-105">Ein Mitglied der Serveradministratorrolle kann Benutzern serverweiten Administratorzugriff gewähren, indem er sie als Mitglieder der Rolle hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="8041d-105">A member of the server administrator role can grant users administrative access on a server-wide basis by making them members of the role.</span></span> <span data-ttu-id="8041d-106">Ein Mitglied der Serveradministratorrolle kann Benutzern auch den Zugriff auf eingeschränktem Niveau erteilen, indem ihnen eingeschränkte oder vollständige Administrator- oder Zugriffsberechtigungen auf Datenbankebene erteilt werden.</span><span class="sxs-lookup"><span data-stu-id="8041d-106">A member of the server administrator role can also grant users access on a more limited basis by granting them limited or complete administrative or access permissions at the database level.</span></span> <span data-ttu-id="8041d-107">Eingeschränkte Administratorberechtigungen schließen Berechtigungen zum Verarbeiten oder Lesen von Definitionen auf Datenbank-, Cube- oder Dimensionsebene ein.</span><span class="sxs-lookup"><span data-stu-id="8041d-107">Limited administrative permissions include process or read definition permissions at the database, cube, or dimension level.</span></span>

 <span data-ttu-id="8041d-108">Im Rahmen der Tasks in diesem Thema definieren Sie die Process Database Objects-Sicherheitsrolle, die Mitgliedern der Rolle die Berechtigung erteilt, alle Datenbankobjekte zu verarbeiten, sie jedoch nicht berechtigt, Daten innerhalb der Datenbank anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8041d-108">In the tasks in this topic, you will define a Process Database Objects security role that grants members of the role permission to process all database objects, but no permission to view data within the database.</span></span>

## <a name="defining-a-process-database-objects-security-role"></a><span data-ttu-id="8041d-109">Definieren der Process Database Objects-Sicherheitsrolle</span><span class="sxs-lookup"><span data-stu-id="8041d-109">Defining a Process Database Objects Security Role</span></span>

1.  <span data-ttu-id="8041d-110">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf **Rollen** und anschließend auf **Neue Rolle** , um den Rollen-Designer zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="8041d-110">In Solution Explorer, right-click **Roles** and then click **New Role** to open the Role Designer.</span></span>

2.  <span data-ttu-id="8041d-111">Aktivieren Sie das Kontrollkästchen **Datenbank verarbeiten** .</span><span class="sxs-lookup"><span data-stu-id="8041d-111">Click the **Process database** check box.</span></span>

3.  <span data-ttu-id="8041d-112">Ändern Sie im Eigenschaftenfenster die **Name** -Eigenschaft für diese neue Rolle in `Process Database Objects Role` .</span><span class="sxs-lookup"><span data-stu-id="8041d-112">In the Properties window, change the **Name** property for this new role to `Process Database Objects Role`.</span></span>

     <span data-ttu-id="8041d-113">![Rollen-Designer](../../2014/tutorials/media/l10-security-1.png "Rollen-Designer")</span><span class="sxs-lookup"><span data-stu-id="8041d-113">![Role Designer](../../2014/tutorials/media/l10-security-1.png "Role Designer")</span></span>

4.  <span data-ttu-id="8041d-114">Wechseln Sie zur Registerkarte **Mitgliedschaft** des Rollen-Designers, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="8041d-114">Switch to the **Membership** tab of Role Designer and click **Add**.</span></span>

5.  <span data-ttu-id="8041d-115">Geben Sie die Konten der Windows-Domänenbenutzer oder -Gruppen ein, die Mitglieder dieser Rolle sind.</span><span class="sxs-lookup"><span data-stu-id="8041d-115">Enter the accounts of the Windows domain users or groups who will be members of this role.</span></span> <span data-ttu-id="8041d-116">Klicken Sie auf **Namen überprüfen** , um die Kontoinformationen zu überprüfen, und anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="8041d-116">Click **Check Names** to verify the account information, and then click **OK**.</span></span>

6.  <span data-ttu-id="8041d-117">Wechseln Sie zur Registerkarte **Cubes** des Rollen-Designers.</span><span class="sxs-lookup"><span data-stu-id="8041d-117">Switch to the **Cubes** tab of Role Designer.</span></span>

     <span data-ttu-id="8041d-118">Mitglieder dieser Rolle sind berechtigt, diese Datenbank zu verarbeiten, können jedoch nicht auf die Daten im [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial-Cube zugreifen und besitzen keinen lokalen Cube/Drillthrough-Zugriff, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="8041d-118">Notice that members of this role have permissions to process this database, but have no permission to access the data in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube and have no local cube/drillthrough access, as shown in the following image.</span></span>

     <span data-ttu-id="8041d-119">![Cubes (Registerkarte) des Rollen-Designers](../../2014/tutorials/media/l10-security-2.png "Cubes (Registerkarte) des Rollen-Designers")</span><span class="sxs-lookup"><span data-stu-id="8041d-119">![Cubes tab of Role Designer](../../2014/tutorials/media/l10-security-2.png "Cubes tab of Role Designer")</span></span>

7.  <span data-ttu-id="8041d-120">Wechseln Sie zur Registerkarte **Dimensionen** des Rollen-Designers.</span><span class="sxs-lookup"><span data-stu-id="8041d-120">Switch to the **Dimensions** tab of Role Designer.</span></span>

     <span data-ttu-id="8041d-121">Mitglieder dieser Rolle sind berechtigt, alle Dimensionsobjekte in dieser Datenbank zu verarbeiten und verfügen standardmäßig über Leseberechtigungen für jedes Dimensionsobjekt in der [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="8041d-121">Notice that members of this role have permissions to process all dimension objects in this database, and, by default, have read permissions to access each dimension object in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial database.</span></span>

8.  <span data-ttu-id="8041d-122">Klicken Sie im Menü **Erstellen** auf **Analysis Services Tutorial bereitstellen**.</span><span class="sxs-lookup"><span data-stu-id="8041d-122">On the **Build** menu, click **Deploy Analysis Services Tutorial**.</span></span>

     <span data-ttu-id="8041d-123">Sie haben nun die Process Database Objects-Sicherheitsrolle erfolgreich definiert und bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="8041d-123">You have now successfully defined and deployed the Process Database Objects security role.</span></span> <span data-ttu-id="8041d-124">Nach dem Bereitstellen eines Cubes in der Produktionsumgebung können die Administratoren des bereitgestellten Cubes nach Bedarf der Rolle Benutzer hinzufügen, um Verarbeitungsaufgaben an bestimmte Benutzer zu delegieren.</span><span class="sxs-lookup"><span data-stu-id="8041d-124">After a cube is deployed to the production environment, the administrators of the deployed cube can add users to this role as required to delegate processing responsibilities to specific users.</span></span>

> [!NOTE]
>  <span data-ttu-id="8041d-125">Durch Herunterladen und Installieren der Beispiele ist für Lektion 10 ein abgeschlossenes Projekt verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8041d-125">A completed project for Lesson 10 is available by downloading and installing the samples.</span></span> <span data-ttu-id="8041d-126">Weitere Informationen finden Sie unter [Installieren von Beispiel Daten und-Projekten für das Analysis Services Tutorial zur mehrdimensionalen Modellierung](install-sample-data-and-projects.md).</span><span class="sxs-lookup"><span data-stu-id="8041d-126">For more information, see [Install Sample Data and Projects for the Analysis Services Multidimensional Modeling Tutorial](install-sample-data-and-projects.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8041d-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8041d-127">See Also</span></span>
 [<span data-ttu-id="8041d-128">Rollen und Berechtigungen &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8041d-128">Roles and Permissions &#40;Analysis Services&#41;</span></span>](multidimensional-models/roles-and-permissions-analysis-services.md)


