---
title: Erstellen eines Visual c# SMO-Projekts in Visual Studio .net | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- Visual C# [SMO]
ms.assetid: 1e7abb16-23a0-4a18-91ad-253261e6bf84
author: stevestein
ms.author: sstein
ms.openlocfilehash: b78820fafd37675332e6703cabbb87e78bde5864
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619764"
---
# <a name="create-a-visual-c-smo-project-in-visual-studio-net"></a><span data-ttu-id="4b34c-102">Erstellen eines Visual C# SMO-Projekts in Visual Studio.NET</span><span class="sxs-lookup"><span data-stu-id="4b34c-102">Create a Visual C# SMO Project in Visual Studio .NET</span></span>
  <span data-ttu-id="4b34c-103">In diesem Abschnitt wird beschrieben, wie eine einfache SMO-Konsolenanwendung erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="4b34c-103">This section describes how to build a simple SMO console application.</span></span>  
  
 <span data-ttu-id="4b34c-104">In diesem Beispiel werden Namespaces importiert. Hierdurch kann das Programm auf SMO-Typen verweisen.</span><span class="sxs-lookup"><span data-stu-id="4b34c-104">This example imports namespaces, which enables the program to reference SMO types.</span></span> <span data-ttu-id="4b34c-105">Der Import des `Agent`-Namespaces ist optional.</span><span class="sxs-lookup"><span data-stu-id="4b34c-105">The import of the `Agent` namespace is optional.</span></span> <span data-ttu-id="4b34c-106">Verwenden Sie es, wenn Sie ein Programm schreiben, das den- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent verwendet.</span><span class="sxs-lookup"><span data-stu-id="4b34c-106">Use it when you are writing a program that uses [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="4b34c-107">Der `Common`-Namespace ist erforderlich, um eine sichere Verbindung mit der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] herzustellen.</span><span class="sxs-lookup"><span data-stu-id="4b34c-107">The `Common` namespace is required to establish a secure connection to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4b34c-108">Der `SqlClient`-Namespace wird verwendet, um SQL-Ausnahmefehler zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="4b34c-108">The `SqlClient` namespace is used to process SQL exception errors.</span></span>  
  
### <a name="creating-a-visual-c-smo-project-in-visual-studionet"></a><span data-ttu-id="4b34c-109">Erstellen eines Visual c# SMO-Projekts in Visual Studio.net</span><span class="sxs-lookup"><span data-stu-id="4b34c-109">Creating a Visual C# SMO project in Visual Studio.NET</span></span>  
  
1.  <span data-ttu-id="4b34c-110">Starten Sie [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] (oder [!INCLUDE[vsprvslong](../../includes/vsprvslong-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="4b34c-110">Start [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] (or [!INCLUDE[vsprvslong](../../includes/vsprvslong-md.md)]).</span></span>  
  
2.  <span data-ttu-id="4b34c-111">Klicken Sie im Menü **Datei** auf **Neues Projekt**.</span><span class="sxs-lookup"><span data-stu-id="4b34c-111">On the **File** menu, click **NewProject.**</span></span> <span data-ttu-id="4b34c-112">Das Dialogfeld **Neues Projekt** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4b34c-112">The **New Project** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="4b34c-113">Wählen Sie im Dialogfeld **Projekttypen** die Option **Visual c#** aus, und wählen Sie dann **Windows**aus.</span><span class="sxs-lookup"><span data-stu-id="4b34c-113">In **Project Types** dialog box, select **Visual C#**, and then select **Windows**.</span></span> <span data-ttu-id="4b34c-114">[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]Wählen Sie im Bereich installierte Vorlagen die Option Windows- **Anwendung**aus.</span><span class="sxs-lookup"><span data-stu-id="4b34c-114">In the [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Installed Templates pane, select **Windows Application**.</span></span>  
  
4.  <span data-ttu-id="4b34c-115">Optionale Geben Sie im Feld **Name** den Namen der neuen Anwendung ein.</span><span class="sxs-lookup"><span data-stu-id="4b34c-115">(Optional) In the **Name** field, type the name of the new application</span></span>  
  
5.  <span data-ttu-id="4b34c-116">Wählen Sie den Visual C#-Anwendungstyp aus.</span><span class="sxs-lookup"><span data-stu-id="4b34c-116">Select the Visual C# application type.</span></span> <span data-ttu-id="4b34c-117">Wählen Sie in den folgenden Beispielen **Konsolenanwendung**aus.</span><span class="sxs-lookup"><span data-stu-id="4b34c-117">For the examples that follow, select **Console Application**.</span></span>  
  
6.  <span data-ttu-id="4b34c-118">Wählen Sie im Menü **Projekt** die Option **Verweis hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="4b34c-118">On the **Project** menu, select **Add Reference**.</span></span> <span data-ttu-id="4b34c-119">Das Dialogfeld **Verweis hinzufügen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4b34c-119">The **Add Reference** dialog box appears.</span></span>  
  
7.  <span data-ttu-id="4b34c-120">Klicken Sie auf **Durchsuchen**, suchen Sie die SMO-Assemblys im [!INCLUDE[ssSampPathSDK](../../includes/sssamppathsdk-md.md)] Ordner, und wählen Sie die folgenden Dateien aus.</span><span class="sxs-lookup"><span data-stu-id="4b34c-120">Click **Browse**, locate the SMO assemblies in the [!INCLUDE[ssSampPathSDK](../../includes/sssamppathsdk-md.md)] folder, and then select the following files.</span></span> <span data-ttu-id="4b34c-121">Dabei handelt es sich um die mindestens zum Erstellen einer SMO-Anwendung erforderlichen Dateien:</span><span class="sxs-lookup"><span data-stu-id="4b34c-121">These are the minimum files that are required to build an SMO application:</span></span>  
  
     <span data-ttu-id="4b34c-122">Microsoft.SqlServer.ConnectionInfo.dll</span><span class="sxs-lookup"><span data-stu-id="4b34c-122">Microsoft.SqlServer.ConnectionInfo.dll</span></span>  
  
     <span data-ttu-id="4b34c-123">Microsoft.SqlServer.Smo.dll</span><span class="sxs-lookup"><span data-stu-id="4b34c-123">Microsoft.SqlServer.Smo.dll</span></span>  
  
     <span data-ttu-id="4b34c-124">Microsoft.SqlServer.Management.Sdk.Sfc.dll</span><span class="sxs-lookup"><span data-stu-id="4b34c-124">Microsoft.SqlServer.Management.Sdk.Sfc.dll</span></span>  
  
     <span data-ttu-id="4b34c-125">Microsoft.SqlServer.SqlEnum.dll</span><span class="sxs-lookup"><span data-stu-id="4b34c-125">Microsoft.SqlServer.SqlEnum.dll</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4b34c-126">Mit gedrückter `Ctrl`-TASTE können Sie mehrere Dateien gleichzeitig auswählen.</span><span class="sxs-lookup"><span data-stu-id="4b34c-126">Use the `Ctrl` key to select more than one file.</span></span>  
  
8.  <span data-ttu-id="4b34c-127">Fügen Sie alle zusätzlich erforderlichen SMO-Assemblys hinzu.</span><span class="sxs-lookup"><span data-stu-id="4b34c-127">Add any additional SMO assemblies that are required.</span></span> <span data-ttu-id="4b34c-128">Wenn Sie speziell für [!INCLUDE[ssSB](../../includes/sssb-md.md)] programmieren, fügen Sie beispielsweise die folgenden Assemblys hinzu:</span><span class="sxs-lookup"><span data-stu-id="4b34c-128">For example, if you are specifically programming [!INCLUDE[ssSB](../../includes/sssb-md.md)], add the following assemblies:</span></span>  
  
     <span data-ttu-id="4b34c-129">Microsoft.SqlServer.ServiceBrokerEmum.dll</span><span class="sxs-lookup"><span data-stu-id="4b34c-129">Microsoft.SqlServer.ServiceBrokerEmum.dll</span></span>  
  
9. <span data-ttu-id="4b34c-130">Klicken Sie auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="4b34c-130">Click **Open**.</span></span>  
  
10. <span data-ttu-id="4b34c-131">Klicken Sie im Menü **Ansicht** auf **Code**.-oder wählen Sie Program1.cs [Design] Windows aus, und doppelklicken Sie auf das Windows Form, um das Code Fenster anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4b34c-131">On the **View** menu, click **Code**.-Or-Select the Program1.cs [Design] Windows and double-click the windows form to show the code window.</span></span>  
  
11. <span data-ttu-id="4b34c-132">Geben Sie im Code vor der namespace-Anweisung die folgenden `using`-Anweisungen ein, um die Typen im SMO-Namespace zu qualifizieren:</span><span class="sxs-lookup"><span data-stu-id="4b34c-132">In the code, before the namespace statement, type the following `using` statements to qualify the types in the SMO namespace:</span></span>  
  
    ```  
    using Microsoft.SqlServer.Management.Smo;  
    using Microsoft.SqlServer.Management.Common;  
    ```  
  
12. <span data-ttu-id="4b34c-133">SMO verfügt über verschiedene Namespaces unter Microsoft.SqlServer.Management.Smo, z. B. Microsoft.SqlServer.Management.Smo.Agent.</span><span class="sxs-lookup"><span data-stu-id="4b34c-133">SMO has various namespaces under Microsoft.SqlServer.Management.Smo, such as Microsoft.SqlServer.Management.Smo.Agent.</span></span> <span data-ttu-id="4b34c-134">Fügen Sie diese Namespaces nach Bedarf hinzu.</span><span class="sxs-lookup"><span data-stu-id="4b34c-134">Add these namespaces as they are required.</span></span>  
  
13. <span data-ttu-id="4b34c-135">Sie können jetzt den SMO-Code hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="4b34c-135">You can now add your SMO code.</span></span>  
  
  
