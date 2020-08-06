---
title: Erstellen eines Visual Basic SMO-Projekts in Visual Studio .net | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic [SMO]
ms.assetid: d7a3892c-0f1c-4c4d-8480-b58dce3720bc
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 844d27ab6aadbc972c6282c79adb13e15d55c322
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726226"
---
# <a name="create-a-visual-basic-smo-project-in-visual-studio-net"></a><span data-ttu-id="9951d-102">Erstellen eines Visual Basic-SMO-Projekts in Visual Studio .NET</span><span class="sxs-lookup"><span data-stu-id="9951d-102">Create a Visual Basic SMO Project in Visual Studio .NET</span></span>
  <span data-ttu-id="9951d-103">In diesem Abschnitt wird beschrieben, wie eine einfache SMO-Konsolenanwendung erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="9951d-103">This section describes how to build a simple SMO console application.</span></span>  
  
 <span data-ttu-id="9951d-104">In diesem Beispiel werden Namespaces importiert. Hierdurch kann das Programm auf SMO-Typen verweisen.</span><span class="sxs-lookup"><span data-stu-id="9951d-104">This example imports namespaces, which enables the program to reference SMO types.</span></span> <span data-ttu-id="9951d-105">Der Import des `Agent`-Namespaces ist optional.</span><span class="sxs-lookup"><span data-stu-id="9951d-105">The import of the `Agent` namespace is optional.</span></span> <span data-ttu-id="9951d-106">Verwenden Sie es, wenn Sie ein Programm schreiben, das den- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent verwendet.</span><span class="sxs-lookup"><span data-stu-id="9951d-106">Use it when you are writing a program that uses [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="9951d-107">Der `Common`-Namespace ist erforderlich, um eine sichere Verbindung mit der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] herzustellen.</span><span class="sxs-lookup"><span data-stu-id="9951d-107">The `Common` namespace is required to establish a secure connection to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="9951d-108">Der `SqlClient`-Namespace wird verwendet, um SQL-Ausnahmefehler zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="9951d-108">The `SqlClient` namespace is used to process SQL exception errors.</span></span>  
  
### <a name="creating-a-visual-basic-smo-project-in-visual-studionet"></a><span data-ttu-id="9951d-109">Erstellen eines Visual Basic-SMO-Projekts in Visual Studio.NET</span><span class="sxs-lookup"><span data-stu-id="9951d-109">Creating a Visual Basic SMO project in Visual Studio.NET</span></span>  
  
1.  <span data-ttu-id="9951d-110">Starten Sie [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] (oder [!INCLUDE[vsprvslong](../../includes/vsprvslong-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="9951d-110">Start [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] (or [!INCLUDE[vsprvslong](../../includes/vsprvslong-md.md)]).</span></span>  
  
2.  <span data-ttu-id="9951d-111">Klicken Sie im Menü **Datei** auf **Neues Projekt**.</span><span class="sxs-lookup"><span data-stu-id="9951d-111">On the **File** menu, click **NewProject.**</span></span> <span data-ttu-id="9951d-112">Das Dialogfeld **Neues Projekt** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9951d-112">The **New Project** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="9951d-113">Wählen Sie im Dialogfeld **Projekttypen** die Option **Visual Basic**aus, und wählen Sie dann **Windows**aus.</span><span class="sxs-lookup"><span data-stu-id="9951d-113">In **Project Types** dialog box, select **Visual Basic**, and then select **Windows**.</span></span> <span data-ttu-id="9951d-114">[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]Wählen Sie im Bereich installierte Vorlagen die Option **Konsolenanwendung aus.**</span><span class="sxs-lookup"><span data-stu-id="9951d-114">In the [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Installed Templates pane, select **Console Application.**</span></span>  
  
4.  <span data-ttu-id="9951d-115">Optionale Geben Sie im Feld **Name** den Namen der neuen Anwendung ein.</span><span class="sxs-lookup"><span data-stu-id="9951d-115">(Optional) In the **Name** field, type the name of the new application.</span></span>  
  
5.  <span data-ttu-id="9951d-116">Klicken Sie auf **OK** , um die [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] Vorlage Konsolenanwendung zu laden.</span><span class="sxs-lookup"><span data-stu-id="9951d-116">Click **OK** to load the [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] console application template.</span></span>  
  
6.  <span data-ttu-id="9951d-117">Wählen Sie im Menü **Projekt** die Option **Verweis hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="9951d-117">On the **Project** menu, select **Add Reference**.</span></span> <span data-ttu-id="9951d-118">Das Dialogfeld **Verweis hinzufügen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9951d-118">The **Add Reference** dialog box appears.</span></span>  
  
7.  <span data-ttu-id="9951d-119">Klicken Sie auf **Durchsuchen**, suchen Sie die SMO-Assemblys im Ordner c:\Programme\Microsoft SQL server\120\sdk\assemblys, und wählen Sie dann die folgenden Dateien aus.</span><span class="sxs-lookup"><span data-stu-id="9951d-119">Click **Browse**, locate the SMO assemblies in the C:\Program Files\Microsoft SQL Server\120\SDK\Assemblies folder, and then select the following files.</span></span> <span data-ttu-id="9951d-120">Dabei handelt es sich um die mindestens zum Erstellen einer SMO-Anwendung erforderlichen Dateien:</span><span class="sxs-lookup"><span data-stu-id="9951d-120">These are the minimum files that are required to build an SMO application:</span></span>  
  
     <span data-ttu-id="9951d-121">Microsoft.SqlServer.ConnectionInfo.dll</span><span class="sxs-lookup"><span data-stu-id="9951d-121">Microsoft.SqlServer.ConnectionInfo.dll</span></span>  
  
     <span data-ttu-id="9951d-122">Microsoft.SqlServer.SqlEnum.dll</span><span class="sxs-lookup"><span data-stu-id="9951d-122">Microsoft.SqlServer.SqlEnum.dll</span></span>  
  
     <span data-ttu-id="9951d-123">Microsoft.SqlServer.Smo.dll</span><span class="sxs-lookup"><span data-stu-id="9951d-123">Microsoft.SqlServer.Smo.dll</span></span>  
  
     <span data-ttu-id="9951d-124">Microsoft.SqlServer.Management.Sdk.Sfc</span><span class="sxs-lookup"><span data-stu-id="9951d-124">Microsoft.SqlServer.Management.Sdk.Sfc</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9951d-125">Mit gedrückter `Ctrl`-TASTE können Sie mehrere Dateien gleichzeitig auswählen.</span><span class="sxs-lookup"><span data-stu-id="9951d-125">Use the `Ctrl` key to select more than one file.</span></span>  
  
8.  <span data-ttu-id="9951d-126">Fügen Sie alle zusätzlich erforderlichen SMO-Assemblys hinzu.</span><span class="sxs-lookup"><span data-stu-id="9951d-126">Add any additional SMO assemblies that are required.</span></span> <span data-ttu-id="9951d-127">Wenn Sie speziell für [!INCLUDE[ssSB](../../includes/sssb-md.md)] programmieren, fügen Sie beispielsweise die folgenden Assemblys hinzu:</span><span class="sxs-lookup"><span data-stu-id="9951d-127">For example, if you are specifically programming [!INCLUDE[ssSB](../../includes/sssb-md.md)], add the following assemblies:</span></span>  
  
     <span data-ttu-id="9951d-128">Microsoft.SqlServer.ServiceBrokerEmum.dll</span><span class="sxs-lookup"><span data-stu-id="9951d-128">Microsoft.SqlServer.ServiceBrokerEmum.dll</span></span>  
  
9. <span data-ttu-id="9951d-129">Klicken Sie auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="9951d-129">Click **Open**.</span></span>  
  
10. <span data-ttu-id="9951d-130">Klicken Sie im Menü **Ansicht** auf **Code**.-oder-wählen Sie das Fenster Module1. vb aus, um das Code Fenster anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9951d-130">On the **View** menu, click **Code**.-Or-Select the Module1.vb window to show the code window.</span></span>  
  
11. <span data-ttu-id="9951d-131">Geben Sie im Code vor allen Deklarationen die folgenden **Imports** -Anweisungen ein, um die Typen im SMO-Namespace zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="9951d-131">In the code, before any declarations, type the following **Imports** statements to qualify the types in the SMO namespace.</span></span>  
  
    ```  
    Imports Microsoft.SqlServer.Management.Smo  
    Imports Microsoft.SqlServer.Management.Common  
    ```  
  
12. <span data-ttu-id="9951d-132">SMO verfügt über verschiedene Namespaces unter Microsoft.SqlServer.Management.Smo, z. B. Microsoft.SqlServer.Management.Smo.Agent.</span><span class="sxs-lookup"><span data-stu-id="9951d-132">SMO has various namespaces under Microsoft.SqlServer.Management.Smo, such as Microsoft.SqlServer.Management.Smo.Agent.</span></span> <span data-ttu-id="9951d-133">Fügen Sie diese Namespaces nach Bedarf hinzu.</span><span class="sxs-lookup"><span data-stu-id="9951d-133">Add these namespaces as they are required.</span></span>  
  
13. <span data-ttu-id="9951d-134">Sie können jetzt den SMO-Code hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9951d-134">You can now add your SMO code.</span></span>  
  
  
