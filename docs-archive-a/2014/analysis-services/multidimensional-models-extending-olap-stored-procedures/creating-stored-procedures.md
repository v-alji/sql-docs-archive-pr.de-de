---
title: Erstellen gespeicherter Prozeduren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- registering assemblies
- database assemblies [Analysis Services]
- server assemblies [Analysis Services]
- stored procedures [Analysis Services], creating
- assemblies [Analysis Services]
ms.assetid: a12ff02f-6d0b-4488-9846-3609fc0d0554
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9a997244a2d54cca8732196107dd21927b5f9e2f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700437"
---
# <a name="creating-stored-procedures"></a><span data-ttu-id="de53e-102">Erstellen gespeicherter Prozeduren</span><span class="sxs-lookup"><span data-stu-id="de53e-102">Creating Stored Procedures</span></span>
  <span data-ttu-id="de53e-103">Alle gespeicherten Prozeduren müssen mit einer CLR-Klasse (Common Language Runtime) oder einer COM-Klasse (Component Object Model) verknüpft sein, damit sie verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="de53e-103">All stored procedures must be associated with a common language runtime (CLR) or Component Object Model (COM) class in order to be used.</span></span> <span data-ttu-id="de53e-104">Die-Klasse muss auf dem Server installiert sein (in der Regel in Form eines [!INCLUDE[msCoName](../../includes/msconame-md.md)] ActiveX-® Dynamic Link Library (dll)) und als Assembly auf dem Server oder in einer- [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Datenbank registriert.</span><span class="sxs-lookup"><span data-stu-id="de53e-104">The class must be installed on the server - usually in the form of a [!INCLUDE[msCoName](../../includes/msconame-md.md)] ActiveX® dynamic link library (DLL) - and registered as an assembly on the server or in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="de53e-105">Gespeicherte Prozeduren sind auf einem Server oder in einer Datenbank registriert.</span><span class="sxs-lookup"><span data-stu-id="de53e-105">Stored procedures are registered on a server or on a database.</span></span> <span data-ttu-id="de53e-106">Gespeicherte Serverprozeduren können aus einem beliebigen Abfragekontext aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="de53e-106">Server stored procedures can be called from any query context.</span></span> <span data-ttu-id="de53e-107">Der Zugriff auf gespeicherte Datenbankprozeduren ist nur möglich, wenn der Datenbankkontext die Datenbank ist, unter der die gespeicherte Prozedur definiert ist.</span><span class="sxs-lookup"><span data-stu-id="de53e-107">Database stored procedures can only be accessed if the database context is the database under which the stored procedure is defined.</span></span> <span data-ttu-id="de53e-108">Wenn Funktionen in einer Assembly die Funktionen in einer anderen Assembly aufrufen, müssen Sie beide Assemblys in demselben Kontext registrieren (Server oder Datenbank).</span><span class="sxs-lookup"><span data-stu-id="de53e-108">If functions in one assembly call functions in a different assembly, you must register both assemblies in the same context (server or database).</span></span> <span data-ttu-id="de53e-109">Für einen Server oder eine bereitgestellte [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Datenbank auf einem-Server können Sie verwenden, [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] um eine Assembly zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="de53e-109">For a server or a deployed [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database on a server, you can use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to register an assembly.</span></span> <span data-ttu-id="de53e-110">Für ein [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]-Projekt können Sie eine Assembly mithilfe von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]-Designer im Projekt registrieren.</span><span class="sxs-lookup"><span data-stu-id="de53e-110">For an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, you can use [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Designer to register an assembly in the project.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="de53e-111">COM-Assemblys können ein Sicherheitsrisiko darstellen.</span><span class="sxs-lookup"><span data-stu-id="de53e-111">COM assemblies might pose a security risk.</span></span> <span data-ttu-id="de53e-112">Aufgrund dieses Risikos und anderer Überlegungen wurden COM-Assemblys in [!INCLUDE[ssASversion10](../../includes/ssasversion10-md.md)]als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="de53e-112">Due to this risk and other considerations, COM assemblies were deprecated in [!INCLUDE[ssASversion10](../../includes/ssasversion10-md.md)].</span></span> <span data-ttu-id="de53e-113">COM-Assemblys werden in zukünftigen Versionen möglicherweise nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="de53e-113">COM assemblies might not be supported in future releases.</span></span>  
  
## <a name="registering-a-server-assembly"></a><span data-ttu-id="de53e-114">Registrieren einer Serverassembly</span><span class="sxs-lookup"><span data-stu-id="de53e-114">Registering a Server Assembly</span></span>  
 <span data-ttu-id="de53e-115">Im Objekt-Explorer von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] werden Serverassemblys im Ordner Assemblys unter einer Instanz von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="de53e-115">In Object Explorer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], server assemblies are listed in the Assemblies folder under an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="de53e-116">Serverassemblys können sowohl .NET-Assemblys (CLR) als auch COM-Bibliotheken enthalten.</span><span class="sxs-lookup"><span data-stu-id="de53e-116">Server assemblies can contain both .NET (CLR) assemblies and COM libraries.</span></span>  
  
### <a name="to-create-a-server-assembly"></a><span data-ttu-id="de53e-117">So erstellen Sie eine Serverassembly</span><span class="sxs-lookup"><span data-stu-id="de53e-117">To create a server assembly</span></span>  
  
1.  <span data-ttu-id="de53e-118">Erweitern [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Sie in Objekt-Explorer **die Instanz** von, klicken Sie mit der rechten Maustaste auf den Ordner Assemblys, und klicken Sie auf **neue Assembly**.</span><span class="sxs-lookup"><span data-stu-id="de53e-118">Expand the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] in Object Explorer, right-click the **Assemblies** folder, and then click **New Assembly**.</span></span> <span data-ttu-id="de53e-119">Dadurch wird das Dialogfeld **Serverassembly registrieren** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="de53e-119">This displays the **Register Server Assembly** dialog box.</span></span>  
  
2.  <span data-ttu-id="de53e-120">Geben Sie für **Typ** den Typ der Assembly an:</span><span class="sxs-lookup"><span data-stu-id="de53e-120">For **Type** specify the type of assembly:</span></span>  
  
    -   <span data-ttu-id="de53e-121">Für eine DLL mit verwaltetem Code (CLR) geben Sie .NET-Assembly an.</span><span class="sxs-lookup"><span data-stu-id="de53e-121">For a managed code (CLR) DLL, specify .NET Assembly.</span></span>  
  
    -   <span data-ttu-id="de53e-122">Geben Sie für eine com-dll (Native Code) com dll an.</span><span class="sxs-lookup"><span data-stu-id="de53e-122">For a native code (COM) DLL, specify COM DLL.</span></span>  
  
3.  <span data-ttu-id="de53e-123">Geben Sie unter **Dateiname**die dll an, die die gespeicherten Prozeduren enthält.</span><span class="sxs-lookup"><span data-stu-id="de53e-123">For **File name**, specify the DLL containing the stored procedures.</span></span>  
  
4.  <span data-ttu-id="de53e-124">Geben **Assembly name**Sie unter AssemblyName einen Namen für die Assembly an.</span><span class="sxs-lookup"><span data-stu-id="de53e-124">For **Assembly name**, specify a name for the assembly.</span></span>  
  
5.  <span data-ttu-id="de53e-125">Wenn es sich um einen Debugbuild der Bibliothek handelt, die Sie zum Debuggen gespeicherter Prozeduren verwenden möchten, aktivieren Sie das Kontrollkästchen **Debuginformationen einschließen** .</span><span class="sxs-lookup"><span data-stu-id="de53e-125">If this is a debug build of the library that you are going to use to debug stored procedures, select the **Include debug information** check box.</span></span> <span data-ttu-id="de53e-126">Weitere Informationen zum Debuggen gespeicherter Prozeduren finden Sie unter [Debuggen von gespeicherten](debugging-stored-procedures.md)</span><span class="sxs-lookup"><span data-stu-id="de53e-126">For more information about debugging stored procedures, see [Debugging Stored Procedures](debugging-stored-procedures.md).</span></span>  
  
6.  <span data-ttu-id="de53e-127">Sie können auf **OK** klicken, um die Assembly sofort zu registrieren, oder Sie können auf der Symbolleiste des Dialog Felds auf einen Befehl im Menü **Skript** klicken, um ein Skript für die Registrierungsaktion in ein Abfragefenster, eine Datei oder die Zwischenablage zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="de53e-127">You can click **OK** to register the assembly immediately, or on the dialog box toolbar, you can click a command on the **Script** menu to script the registration action to a query window, a file, or the Clipboard.</span></span>  
  
 <span data-ttu-id="de53e-128">Nachdem Sie eine Serverassembly registriert haben, können Sie Sie konfigurieren, indem Sie in Objekt-Explorer mit der rechten Maustaste auf die Assembly und dann auf **Eigenschaften**klicken.</span><span class="sxs-lookup"><span data-stu-id="de53e-128">After you register a server assembly, you can configure it by right-clicking the assembly in Object Explorer and then clicking **Properties**.</span></span>  
  
## <a name="registering-a-database-assembly-on-the-server"></a><span data-ttu-id="de53e-129">Registrieren einer Datenbankassembly auf dem Server</span><span class="sxs-lookup"><span data-stu-id="de53e-129">Registering a Database Assembly on the Server</span></span>  
 <span data-ttu-id="de53e-130">Im Objekt-Explorer von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] werden Datenbankassemblys im Ordner Assemblys unter einer [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]-Datenbank aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="de53e-130">In Object Explorer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], database assemblies are listed in the Assemblies folder under an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="de53e-131">Datenbankassemblys können sowohl .NET-Assemblys (CLR) als auch COM-Bibliotheken enthalten.</span><span class="sxs-lookup"><span data-stu-id="de53e-131">Database assemblies can contain both .NET (CLR) assemblies and COM libraries.</span></span>  
  
### <a name="to-create-a-database-assembly-on-a-server"></a><span data-ttu-id="de53e-132">So erstellen Sie eine Datenbankassembly auf einem Server</span><span class="sxs-lookup"><span data-stu-id="de53e-132">To create a database assembly on a server</span></span>  
  
1.  <span data-ttu-id="de53e-133">Erweitern Sie die Instanz der [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Datenbank Objekt-Explorer, klicken Sie mit der **Assemblies** rechten Maustaste auf den Ordner Assemblys, und klicken Sie dann auf **neue Assembly**.</span><span class="sxs-lookup"><span data-stu-id="de53e-133">Expand the instance the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database in Object Explorer, right-click the **Assemblies** folder, and then click **New Assembly**.</span></span> <span data-ttu-id="de53e-134">Dadurch wird das Dialogfeld **Datenbankassembly registrieren** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="de53e-134">This displays the **Register Database Assembly** dialog box.</span></span>  
  
2.  <span data-ttu-id="de53e-135">Geben Sie für **Typ** den Typ der Assembly an:</span><span class="sxs-lookup"><span data-stu-id="de53e-135">For **Type** specify the type of assembly:</span></span>  
  
    -   <span data-ttu-id="de53e-136">Für eine DLL mit verwaltetem Code (CLR) geben Sie .NET-Assembly an.</span><span class="sxs-lookup"><span data-stu-id="de53e-136">For a managed code (CLR) DLL, specify .NET Assembly.</span></span>  
  
    -   <span data-ttu-id="de53e-137">Für eine DLL mit systemeigenem Code (COM) geben Sie COM-DLL an.</span><span class="sxs-lookup"><span data-stu-id="de53e-137">For a native code (COM) DLL), specify COM DLL.</span></span>  
  
3.  <span data-ttu-id="de53e-138">Geben Sie unter **Dateiname**die dll an, die die gespeicherten Prozeduren enthält.</span><span class="sxs-lookup"><span data-stu-id="de53e-138">For **File name**, specify the DLL containing the stored procedures.</span></span>  
  
4.  <span data-ttu-id="de53e-139">Geben **Assembly name**Sie unter AssemblyName einen Namen für die Assembly an.</span><span class="sxs-lookup"><span data-stu-id="de53e-139">For **Assembly name**, specify a name for the assembly.</span></span>  
  
5.  <span data-ttu-id="de53e-140">Wenn es sich um einen Debugbuild der Bibliothek handelt, die Sie zum Debuggen gespeicherter Prozeduren verwenden möchten, aktivieren Sie das Kontrollkästchen **Debuginformationen einschließen** .</span><span class="sxs-lookup"><span data-stu-id="de53e-140">If this is a debug build of the library that you are going to use to debug stored procedures, select the **Include debug information** check box.</span></span> <span data-ttu-id="de53e-141">Weitere Informationen zum Debuggen gespeicherter Prozeduren finden Sie unter [Debuggen von gespeicherten](debugging-stored-procedures.md)</span><span class="sxs-lookup"><span data-stu-id="de53e-141">For more information about debugging stored procedures, see [Debugging Stored Procedures](debugging-stored-procedures.md).</span></span>  
  
6.  <span data-ttu-id="de53e-142">Sie können auf **OK** klicken, um die Assembly sofort zu registrieren, oder Sie können auf der Symbolleiste des Dialog Felds auf einen Befehl im Menü **Skript** klicken, um ein Skript für die Registrierungsaktion in ein Abfragefenster, eine Datei oder die Zwischenablage zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="de53e-142">You can click **OK** to register the assembly immediately, or on the dialog box toolbar, you can click a command on the **Script** menu to script the registration action to a query window, a file, or the Clipboard.</span></span>  
  
 <span data-ttu-id="de53e-143">Nachdem Sie eine Datenbankassembly registriert haben, können Sie Sie konfigurieren, indem Sie in Objekt-Explorer mit der rechten Maustaste auf die Assembly und dann auf **Eigenschaften**klicken.</span><span class="sxs-lookup"><span data-stu-id="de53e-143">After you register a database assembly, you can configure it by right-clicking the assembly in Object Explorer and then clicking **Properties**.</span></span>  
  
## <a name="registering-a-database-assembly-in-a-project"></a><span data-ttu-id="de53e-144">Registrieren einer Datenbankassembly in einem Projekt</span><span class="sxs-lookup"><span data-stu-id="de53e-144">Registering a Database Assembly in a Project</span></span>  
 <span data-ttu-id="de53e-145">Im Projektmappen-Explorer von [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] werden Datenbankassemblys im Ordner Assemblys unter einem [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]-Projekt aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="de53e-145">In Solution Explorer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], database assemblies are listed in the Assemblies folder under an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> <span data-ttu-id="de53e-146">Datenbankassemblys können sowohl .NET-Assemblys (CLR) als auch COM-Bibliotheken enthalten.</span><span class="sxs-lookup"><span data-stu-id="de53e-146">Database assemblies can contain both .NET (CLR) assemblies and COM libraries.</span></span>  
  
### <a name="to-create-a-database-assembly-in-an-analysis-service-project"></a><span data-ttu-id="de53e-147">So erstellen Sie eine Datenbankassembly in einem Analysis Services-Projekt</span><span class="sxs-lookup"><span data-stu-id="de53e-147">To create a database assembly in an Analysis Service project</span></span>  
  
1.  <span data-ttu-id="de53e-148">Erweitern Sie die Instanz der [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Datenbank in Objekt-Explorer, klicken Sie mit **Assemblies** der rechten Maustaste auf den Ordner Assemblys, und klicken Sie dann auf **New Assembly Reference**</span><span class="sxs-lookup"><span data-stu-id="de53e-148">Expand the instance the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database in Object Explorer, right-click the **Assemblies** folder, and then click **New Assembly Reference**.</span></span> <span data-ttu-id="de53e-149">Dadurch wird das Dialogfeld **Verweis hinzufügen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="de53e-149">This displays the **Add Reference** dialog box.</span></span> <span data-ttu-id="de53e-150">Auf der Registerkarte **.net** des Dialog Felds **Verweis hinzufügen** werden vorhandene .NET-Assemblys (CLR) aufgelistet, während auf der Registerkarte **Projekte** Projekte aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="de53e-150">The **.NET** tab of the **Add Reference** dialog box lists existing .NET (CLR) assemblies, while the **Projects** tab lists projects.</span></span>  
  
2.  <span data-ttu-id="de53e-151">Sie können auf eine vorhandene Komponente oder ein vorhandenes Projekt klicken und dann auf **Hinzufügen** klicken, um Sie dem Projekt hinzuzufügen [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="de53e-151">You can click an existing component or project and then click **Add** to add it to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> <span data-ttu-id="de53e-152">Um einen Verweis auf eine COM-DLL hinzuzufügen, klicken Sie auf die Registerkarte **Durchsuchen** , um die Datei zu suchen</span><span class="sxs-lookup"><span data-stu-id="de53e-152">To add a reference to a COM DLL, click the **Browse** tab to find the file.</span></span> <span data-ttu-id="de53e-153">In der Liste **Ausgewählte Projekte und Komponenten** werden Name, Typ, Version und Speicherort für jede Komponente angezeigt, die Sie dem Projekt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="de53e-153">The **Selected projects and components** list shows the name, type, version, and location for each component that you are adding to the project.</span></span>  
  
3.  <span data-ttu-id="de53e-154">Wenn Sie die hinzu zufügenden Komponenten ausgewählt haben, klicken Sie auf **OK** , um Sie dem Projekt hinzuzufügen [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="de53e-154">When you are finished selecting components to add, click **OK** to add them to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span>  
  
## <a name="script-format-for-an-assembly"></a><span data-ttu-id="de53e-155">Skriptformat für eine Assembly</span><span class="sxs-lookup"><span data-stu-id="de53e-155">Script Format For an Assembly</span></span>  
 <span data-ttu-id="de53e-156">Das Registrieren einer .NET-Assembly ist ein relativ einfacher Vorgang.</span><span class="sxs-lookup"><span data-stu-id="de53e-156">Registering a .NET assembly is fairly simple.</span></span> <span data-ttu-id="de53e-157">Eine .NET-Assembly wird im Binärformat einer Datenbank mithilfe des folgenden Formats hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="de53e-157">A .NET assembly is added to a database in binary format using the following format:</span></span>  
  
```  
<Create>  
   <ObjectDefinition>  
      <Assembly>  
         <Files>  
            <File>  
               <Name>filename</Name>  
               <Type>filetype</Type>  
               <Data>  
                  <Block>binarydatablock</Block>  
                  <Block>binarydatablock</Block>  
                  ...  
               </Data>  
            </File>  
         </Files>  
         <PermissionSet>PermissionSet</PermissionSet>  
      </Assembly>  
   <ObjectDefinition>  
</Create>  
```  
  
## <a name="see-also"></a><span data-ttu-id="de53e-158">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="de53e-158">See Also</span></span>  
 <span data-ttu-id="de53e-159">[Verwaltung von mehrdimensionalen Modellen](../multidimensional-models/multidimensional-model-assemblies-management.md) </span><span class="sxs-lookup"><span data-stu-id="de53e-159">[Multidimensional Model Assemblies Management](../multidimensional-models/multidimensional-model-assemblies-management.md) </span></span>  
 [<span data-ttu-id="de53e-160">Definieren von gespeicherten Proze</span><span class="sxs-lookup"><span data-stu-id="de53e-160">Defining Stored Procedures</span></span>](defining-stored-procedures.md)  
  
  
