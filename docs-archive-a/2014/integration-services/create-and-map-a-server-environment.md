---
title: Erstellen und Zuordnen einer Server Umgebung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.ssms.isenvprop.variables.f1
- sql12.ssis.ssms.iscreateenv.f1
- sql12.ssis.ssms.isenvprop.permissions.f1
- sql12.ssis.ssms.isenvprop.general.f1
ms.assetid: b1cbb697-713f-48e4-b234-b23724d87451
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9331b5078effb562931f45c48bd8ff975c1d1998
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616611"
---
# <a name="create-and-map-a-server-environment"></a><span data-ttu-id="8485a-102">Erstellen und Zuordnen einer Serverumgebung</span><span class="sxs-lookup"><span data-stu-id="8485a-102">Create and Map a Server Environment</span></span>
  <span data-ttu-id="8485a-103">Sie erstellen eine Serverumgebung, um Laufzeitwerte für Pakete festzulegen, die in einem auf dem [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Server bereitgestellten Projekt enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="8485a-103">You create a server environment to specify runtime values for packages contained in a project you've deployed to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="8485a-104">Anschließend können Sie die Umgebungsvariablen Parametern für ein bestimmtes Paket, für Einstiegspunktpakete oder für alle Pakete in einem angegebenen Projekt zuordnen.</span><span class="sxs-lookup"><span data-stu-id="8485a-104">You can then map the environment variables to parameters, for a specific package, for entry-point packages, or for all the packages in a given project.</span></span> <span data-ttu-id="8485a-105">Ein Einstiegspunktpaket ist in der Regel ein übergeordnetes Paket, von dem ein untergeordnetes Paket ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8485a-105">An entry-point package is typically a parent package that executes a child package.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8485a-106">Ein Paket kann jeweils nur mit den Werten ausgeführt werden, die in einer einzelnen Serverumgebung enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="8485a-106">For a given execution, a package can execute only with the values contained in a single server environment.</span></span>  
  
 <span data-ttu-id="8485a-107">Sie können Sichten nach einer Liste von Serverumgebungen, Umgebungsverweisen und Umgebungsvariablen abfragen.</span><span class="sxs-lookup"><span data-stu-id="8485a-107">You can query views for a list of server environments, environment references, and environment variables.</span></span> <span data-ttu-id="8485a-108">Sie können auch gespeicherte Prozeduren aufrufen, um Umgebungen, Umgebungsverweise und Umgebungsvariablen hinzuzufügen, zu löschen und zu ändern.</span><span class="sxs-lookup"><span data-stu-id="8485a-108">You can also call stored to add, delete, and modify environments, environment references, and environment variables.</span></span> <span data-ttu-id="8485a-109">Weitere Informationen finden Sie im Abschnitt **Serverumgebungen, Servervariablen und Serverumgebungsverweise** im [SSIS Catalog](catalog/ssis-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="8485a-109">For more information, see the **Server Environments, Server Variables and Server Environment References** section in [SSIS Catalog](catalog/ssis-catalog.md).</span></span>  
  
### <a name="to-create-and-use-a-server-environment"></a><span data-ttu-id="8485a-110">So erstellen und verwenden Sie eine Serverumgebung</span><span class="sxs-lookup"><span data-stu-id="8485a-110">To create and use a server environment</span></span>  
  
1.  <span data-ttu-id="8485a-111">[!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)]Erweitern [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Sie in Objekt-Explorer den Knoten Kataloge> **ssisdb** , und suchen Sie den Ordner **Umgebungen** des Projekts, für das Sie eine Umgebung erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="8485a-111">In [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], expand the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Catalogs> **SSISDB** node in Object Explorer, and locate the **Environments** folder of the project for which you want to create an environment.</span></span>  
  
2.  <span data-ttu-id="8485a-112">Klicken Sie mit der rechten Maustaste auf den Ordner **Umgebungen** , und klicken Sie dann auf **Umgebung erstellen**.</span><span class="sxs-lookup"><span data-stu-id="8485a-112">Right-click the **Environments** folder, and then click **Create Environment**.</span></span>  
  
3.  <span data-ttu-id="8485a-113">Geben Sie einen Namen für die Umgebung und optional eine Beschreibung ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="8485a-113">Type a name for the environment and optionally a description, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="8485a-114">Klicken Sie mit der rechten Maustaste auf die neue Umgebung, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="8485a-114">Right-click the new environment and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="8485a-115">Gehen Sie auf der Seite **Variablen** wie folgt vor, um eine Variable hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="8485a-115">On the **Variables** page, do the following to add a variable.</span></span>  
  
    1.  <span data-ttu-id="8485a-116">Wählen Sie den **Typ** für die Variable aus.</span><span class="sxs-lookup"><span data-stu-id="8485a-116">Select the **Type** for the variable.</span></span> <span data-ttu-id="8485a-117">Der Name der Variablen **muss nicht** mit dem Namen des Projektparameters übereinstimmen, den Sie der Variablen zuordnen.</span><span class="sxs-lookup"><span data-stu-id="8485a-117">The name of the variable **does not** need to match the name of the project parameter that you map to the variable.</span></span>  
  
    2.  <span data-ttu-id="8485a-118">Geben Sie eine optionale **Beschreibung** für die Variable ein.</span><span class="sxs-lookup"><span data-stu-id="8485a-118">Enter an optional **Description** for the variable.</span></span>  
  
    3.  <span data-ttu-id="8485a-119">Geben Sie den **Wert** für die Umgebungsvariable ein.</span><span class="sxs-lookup"><span data-stu-id="8485a-119">Enter the **Value** for the environment variable.</span></span>  
  
         <span data-ttu-id="8485a-120">Informationen zu den Benennungsregeln für Umgebungsvariablen finden Sie im Abschnitt **Umgebungsvariable** im [SSIS Catalog](catalog/ssis-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="8485a-120">For information about the rules for environment variable names, see the **Environment Variable** section in [SSIS Catalog](catalog/ssis-catalog.md).</span></span>  
  
    4.  <span data-ttu-id="8485a-121">Geben Sie an, ob die Variable einen vertraulichen Wert enthält, indem Sie das Kontrollkästchen **Vertraulich** aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="8485a-121">Indicate whether the variable contains sensitive value, by selecting or clearing the **Sensitive** checkbox.</span></span>  
  
         <span data-ttu-id="8485a-122">Bei Auswahl von **Vertraulich**wird der Variablenwert nicht im Feld **Wert** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8485a-122">If you select **Sensitive**, the variable value does not display in the **Value** field.</span></span>  
  
         <span data-ttu-id="8485a-123">Vertrauliche Werte werden im SSISDB-Katalog verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="8485a-123">Sensitive values are encrypted in the SSISDB catalog.</span></span> <span data-ttu-id="8485a-124">Weitere Informationen zur Verschlüsselung finden Sie unter [SSIS Catalog](catalog/ssis-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="8485a-124">For more information about the encryption, see [SSIS Catalog](catalog/ssis-catalog.md).</span></span>  
  
6.  <span data-ttu-id="8485a-125">Gehen Sie auf der Seite **Berechtigungen** wie folgt vor, um ausgewählten Benutzern und Rollen Berechtigungen zu erteilen oder zu verweigern.</span><span class="sxs-lookup"><span data-stu-id="8485a-125">On the **Permissions** page, grant or deny permissions for selected users and roles by doing the following.</span></span>  
  
    1.  <span data-ttu-id="8485a-126">Klicken Sie auf **Durchsuchen**, und wählen Sie dann im Dialogfeld **Alle Prinzipale durchsuchen** mindestens einen Benutzer und eine Rolle aus.</span><span class="sxs-lookup"><span data-stu-id="8485a-126">Click **Browse**, and then select one or more users and roles in the **Browse All Principals** dialog box.</span></span>  
  
    2.  <span data-ttu-id="8485a-127">Wählen Sie im Bereich **Anmeldenamen oder Rollen** den Benutzer oder die Rolle aus, dem bzw. der Sie Berechtigungen erteilen oder verweigern möchten.</span><span class="sxs-lookup"><span data-stu-id="8485a-127">In the **Logins or roles** area, select the user or role that you want to grant or deny permissions for.</span></span>  
  
    3.  <span data-ttu-id="8485a-128">Klicken Sie im Bereich **Explizit** neben den einzelnen Berechtigungen auf **Erteilen** oder **Verweigern** .</span><span class="sxs-lookup"><span data-stu-id="8485a-128">In the **Explicit** area, click **Grant** or **Deny** next to each permission.</span></span>  
  
7.  <span data-ttu-id="8485a-129">Um ein Skript für die Umgebung zu erstellen, klicken Sie auf **Skript**.</span><span class="sxs-lookup"><span data-stu-id="8485a-129">To script the environment, click **Script**.</span></span> <span data-ttu-id="8485a-130">Das Skript wird standardmäßig in einem neuen Abfrage-Editor-Fenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8485a-130">By default, the script displays in a new Query Editor window.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="8485a-131">Sie müssen auf **Skript** klicken, nachdem Sie Änderungen an den Umgebungseigenschaften vorgenommen, z. B. eine Variable hinzugefügt, haben und bevor Sie im Dialogfeld **Umgebungseigenschaften** auf **OK** klicken.</span><span class="sxs-lookup"><span data-stu-id="8485a-131">You need to click **Script** after you've made one or changes to the environment properties, such as adding a variable, and before you click **OK** in the **Environment Properties** dialog box.</span></span> <span data-ttu-id="8485a-132">Andernfalls wird kein Skript generiert.</span><span class="sxs-lookup"><span data-stu-id="8485a-132">Otherwise, a script is not generated.</span></span>  
  
8.  <span data-ttu-id="8485a-133">Klicken Sie auf **OK** , um die Änderungen an den Umgebungseigenschaften zu speichern.</span><span class="sxs-lookup"><span data-stu-id="8485a-133">Click **OK** to save your changes to the environment properties.</span></span>  
  
9. <span data-ttu-id="8485a-134">Erweitern Sie unter dem Knoten **SSISDB** im Objekt-Explorer den Ordner **Projekte** , klicken Sie mit der rechten Maustaste auf das Projekt, und klicken Sie dann auf **Konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="8485a-134">Under the **SSISDB** node in Object Explorer, expand the **Projects** folder, right-click the project, and then click **Configure**.</span></span>  
  
10. <span data-ttu-id="8485a-135">Klicken Sie auf der Seite **Verweise** auf **Hinzufügen** , um eine Umgebung hinzuzufügen, und klicken Sie dann auf **OK** , um den Verweis in der Umgebung zu speichern.</span><span class="sxs-lookup"><span data-stu-id="8485a-135">On the **References** page, click **Add** to add an environment, and then click **OK** to save the reference to the environment.</span></span>  
  
11. <span data-ttu-id="8485a-136">Klicken Sie mit der rechten Maustaste erneut auf das Projekt, und klicken Sie dann auf **Konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="8485a-136">Right-click the project again, and then click **Configure**.</span></span>  
  
12. <span data-ttu-id="8485a-137">Um die Umgebungsvariable einem Parameter zuzuordnen, den Sie dem Paket zur Entwurfszeit hinzugefügt haben, oder einem Parameter, der beim Konvertieren des [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekts in das Projektbereitstellungsmodell generiert wurde, gehen Sie wie folgt vor.</span><span class="sxs-lookup"><span data-stu-id="8485a-137">To map the environment variable to a parameter that you added to the package at design-time or to a parameter that was generated when you converted the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project to the project deployment model, do the following.,</span></span>  
  
    1.  <span data-ttu-id="8485a-138">Klicken Sie auf der Seite **Parameter** auf der Registerkarte **Parameter** neben dem Feld **Wert** auf die Schaltfläche zum Durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="8485a-138">In the **Parameters** tab on the **Parameters** page, click the browse button next to the **Value** field.</span></span>  
  
    2.  <span data-ttu-id="8485a-139">Klicken Sie auf **Umgebungsvariable verwenden**, und wählen Sie dann die Umgebungsvariable aus, die Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="8485a-139">Click **Use environment variable**, and then select the environment variable you created.</span></span>  
  
13. <span data-ttu-id="8485a-140">Um die Umgebungsvariable einer Eigenschaft des Verbindungs-Managers zuzuordnen, gehen Sie wie folgt vor.</span><span class="sxs-lookup"><span data-stu-id="8485a-140">To map the environment variable to a connection manager property, do the following.</span></span> <span data-ttu-id="8485a-141">Parameter für die Eigenschaften des Verbindungs-Managers werden automatisch auf dem SSIS-Server generiert.</span><span class="sxs-lookup"><span data-stu-id="8485a-141">Parameters are automatically generated on the SSIS server for the connection manager properties.</span></span>  
  
    1.  <span data-ttu-id="8485a-142">Klicken Sie auf der Seite **Parameter** auf der Registerkarte **Verbindungs-Manager** neben dem Feld **Wert** auf die Schaltfläche zum Durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="8485a-142">In the **Connection Managers** tab on the **Parameters** page, click the browse button next to the **Value** field.</span></span>  
  
    2.  <span data-ttu-id="8485a-143">Klicken Sie auf **Umgebungsvariable verwenden**, und wählen Sie dann die Umgebungsvariable aus, die Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="8485a-143">Click **Use environment variable**, and then select the environment variable you created.</span></span>  
  
14. <span data-ttu-id="8485a-144">Klicken Sie zum Speichern der Änderungen zweimal auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="8485a-144">Click **OK** twice to save your changes.</span></span>  
  
  
