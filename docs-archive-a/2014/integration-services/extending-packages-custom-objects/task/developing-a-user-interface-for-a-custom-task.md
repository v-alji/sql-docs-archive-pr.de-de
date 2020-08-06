---
title: Entwickeln einer Benutzeroberfläche für einen benutzerdefinierten Task | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom user interfaces [Integration Services]
- IDtsTaskUI interface
- DtsTaskAttribute attribute
- custom tasks [Integration Services], user interface
- custom user interface [Integration Services], custom tasks
- user interface [Integration Services]
- SSIS custom tasks, user interface
ms.assetid: 1e940cd1-c5f8-4527-b678-e89ba5dc398a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ed96bbc302cba4c207e5ce7b2e4fb4b74fed4ee2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621591"
---
# <a name="developing-a-user-interface-for-a-custom-task"></a><span data-ttu-id="ff336-102">Entwickeln einer Benutzeroberfläche für einen benutzerdefinierten Task</span><span class="sxs-lookup"><span data-stu-id="ff336-102">Developing a User Interface for a Custom Task</span></span>
  <span data-ttu-id="ff336-103">Das [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]-Objektmodell bietet Entwicklern benutzerdefinierter Tasks eine einfache Möglichkeit, eine individuelle Benutzeroberfläche für einen Task zu erstellen, der dann in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] integriert und angezeigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="ff336-103">The [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] object model provides custom task developers the ability to easily create a custom user interface for a task that can then be integrated and displayed in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="ff336-104">Die Benutzeroberfläche kann nützliche Informationen für den Benutzer im [!INCLUDE[ssIS](../../../includes/ssis-md.md)]-Designer bereitstellen und den Benutzern Hinweise geben, wie sie die Eigenschaften und Einstellungen des benutzerdefinierten Tasks ordnungsgemäß konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="ff336-104">The user interface can provide helpful information to the user in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, and guide users to correctly configure the properties and settings of the custom task.</span></span>  
  
 <span data-ttu-id="ff336-105">Bei der Entwicklung einer benutzerdefinierten Benutzeroberfläche für einen Task werden zwei wichtige Klassen verwendet.</span><span class="sxs-lookup"><span data-stu-id="ff336-105">Developing a custom user interface for a task involves using two important classes.</span></span> <span data-ttu-id="ff336-106">Diese Klassen werden in der folgenden Tabelle beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ff336-106">The following table describes those classes.</span></span>  
  
|<span data-ttu-id="ff336-107">Klasse</span><span class="sxs-lookup"><span data-stu-id="ff336-107">Class</span></span>|<span data-ttu-id="ff336-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ff336-108">Description</span></span>|  
|-----------|-----------------|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute>|<span data-ttu-id="ff336-109">Ein Attribut, das einen verwalteten Task identifiziert und über seine Eigenschaften Informationen zur Entwurfszeit angibt, um zu kontrollieren, wie der [!INCLUDE[ssIS](../../../includes/ssis-md.md)]-Designer das Objekt anzeigt, bzw. wie er mit ihm interagiert.</span><span class="sxs-lookup"><span data-stu-id="ff336-109">An attribute that identifies a managed task, and supplies design-time information through its properties to control how [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer displays and interacts with the object.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI>|<span data-ttu-id="ff336-110">Eine vom Task verwendete Schnittstelle, um den Task seiner benutzerdefinierten Benutzeroberfläche zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="ff336-110">An interface used by the task to associate the task with its custom user interface.</span></span>|  
  
 <span data-ttu-id="ff336-111">Dieser Abschnitt beschreibt die Rolle der <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute>-Attribute und der <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI>-Schnittstelle bei der Entwicklung einer Benutzeroberfläche für einen benutzerdefinierten Task und enthält Einzelheiten zur Erstellung, Integration, Bereitstellung und dem Debuggen des Tasks innerhalb des [!INCLUDE[ssIS](../../../includes/ssis-md.md)]-Designers.</span><span class="sxs-lookup"><span data-stu-id="ff336-111">This section describes the role of the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> attribute and the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI> interface when you are developing a user interface for a custom task, and provides details about how to create, integrate, deploy, and debug the task within [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="ff336-112">Der [!INCLUDE[ssIS](../../../includes/ssis-md.md)]-Designer stellt mehrere Einstiegspunkte zur Benutzeroberfläche für den Task bereit: Der Benutzer kann im Kontextmenü **Bearbeiten** auswählen, auf den Task doppelklicken oder unten auf dem Eigenschaftenblatt auf den Link **Editor anzeigen** klicken.</span><span class="sxs-lookup"><span data-stu-id="ff336-112">The [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer provides multiple entry points to the user interface for the task: the user can select **Edit** on the shortcut menu, double-click the task, or click the **Show Editor** link at the bottom of the property sheet.</span></span> <span data-ttu-id="ff336-113">Wenn der Benutzer auf einen dieser Einstiegspunkte zugreift, dann sucht und lädt der [!INCLUDE[ssIS](../../../includes/ssis-md.md)]-Designer die Assembly, die die Benutzeroberfläche für den Task enthält.</span><span class="sxs-lookup"><span data-stu-id="ff336-113">When the user accesses one of these entry points, [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer locates and loads the assembly that contains the user interface for the task.</span></span> <span data-ttu-id="ff336-114">Die Benutzeroberfläche für den Task ist für die Erstellung des Eigenschaftendialogfelds verantwortlich, das dem Benutzer in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ff336-114">The user interface for the task is responsible for creating the properties dialog box that is displayed to the user in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="ff336-115">Ein Task und seine Benutzeroberfläche sind separate Entitäten.</span><span class="sxs-lookup"><span data-stu-id="ff336-115">A task and its user interface are separate entities.</span></span> <span data-ttu-id="ff336-116">Sie sollten in separaten Assemblys implementiert werden, um den Aufwand bei der Lokalisierung, der Bereitstellung und den Wartungsarbeiten zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="ff336-116">They should be implemented in separate assemblies to reduce localization, deployment, and maintenance work.</span></span> <span data-ttu-id="ff336-117">Mit Ausnahme der Informationen, die in den im Task codierten<xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute>-Attributwerten enthalten sind, werden von der DLL keine Informationen zur Benutzeroerfläche geladen oder aufgerufen bzw. sind solche Informationen in der Regel nicht in ihr enthalten.</span><span class="sxs-lookup"><span data-stu-id="ff336-117">The task DLL does not load, call, or generally contain any knowledge of its user interface, except for the information that is contained in the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> attribute values coded in the task.</span></span> <span data-ttu-id="ff336-118">Dies ist die einzige Möglichkeit der Zuordnung eines Task zu seiner Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="ff336-118">This is the only way that a task and its user interface are associated.</span></span>  
  
## <a name="the-dtstask-attribute"></a><span data-ttu-id="ff336-119">Das DtsTask-Attribut</span><span class="sxs-lookup"><span data-stu-id="ff336-119">The DtsTask Attribute</span></span>  
 <span data-ttu-id="ff336-120">Das <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute>-Attribut ist im Code der Taskklasse enthalten, um den Task seiner Benutzeroberfläche zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="ff336-120">The <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> attribute is included in the task class code to associate a task with its user interface.</span></span> <span data-ttu-id="ff336-121">Der [!INCLUDE[ssIS](../../../includes/ssis-md.md)]-Designer nutzt die Eigenschaften des Attributs, um zu ermitteln, wie der Task im Designer angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ff336-121">The [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer uses the properties of the attribute to determine how to display the task in the designer.</span></span> <span data-ttu-id="ff336-122">Diese Eigenschaften schließen den anzuzeigenden Namen und ggf. das Symbol ein.</span><span class="sxs-lookup"><span data-stu-id="ff336-122">These properties include the name to display and the icon, if any.</span></span>  
  
 <span data-ttu-id="ff336-123">In der folgenden Tabelle werden die Eigenschaften des <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute>-Attributs beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ff336-123">The following table describes the properties of the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> attribute.</span></span>  
  
|<span data-ttu-id="ff336-124">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="ff336-124">Property</span></span>|<span data-ttu-id="ff336-125">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ff336-125">Description</span></span>|  
|--------------|-----------------|  
|<xref:Microsoft.SqlServer.Dts.Runtime.Localization.DtsLocalizableAttribute.DisplayName%2A>|<span data-ttu-id="ff336-126">Zeigt den Tasknamen in der Toolbox der Ablaufsteuerung an.</span><span class="sxs-lookup"><span data-stu-id="ff336-126">Displays the task name in the Control Flow toolbox.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.Localization.DtsLocalizableAttribute.Description%2A>|<span data-ttu-id="ff336-127">Die Taskbeschreibung (geerbt von <xref:Microsoft.SqlServer.Dts.Runtime.Localization.DtsLocalizableAttribute>).</span><span class="sxs-lookup"><span data-stu-id="ff336-127">The task description (inherited from <xref:Microsoft.SqlServer.Dts.Runtime.Localization.DtsLocalizableAttribute>).</span></span> <span data-ttu-id="ff336-128">Diese Eigenschaft wird in QuickInfos angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ff336-128">This property is shown in ToolTips.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.IconResource%2A>|<span data-ttu-id="ff336-129">Das im [!INCLUDE[ssIS](../../../includes/ssis-md.md)]-Designer angezeigte Symbol.</span><span class="sxs-lookup"><span data-stu-id="ff336-129">The icon displayed in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.RequiredProductLevel%2A>|<span data-ttu-id="ff336-130">Sollte bei Verwendung auf einen der Werte in der <xref:Microsoft.SqlServer.Dts.Runtime.DTSProductLevel>-Enumeration festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="ff336-130">If used, set it to one of the values in the <xref:Microsoft.SqlServer.Dts.Runtime.DTSProductLevel> enumeration.</span></span> <span data-ttu-id="ff336-131">Beispiel: `RequiredProductLevel = DTSProductLevel.None`.</span><span class="sxs-lookup"><span data-stu-id="ff336-131">For example, `RequiredProductLevel = DTSProductLevel.None`.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.TaskContact%2A>|<span data-ttu-id="ff336-132">Enthält Kontaktinformationen, falls für den Task technischer Support benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="ff336-132">Holds contact information for occasions when the task requires technical support.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.TaskType%2A>|<span data-ttu-id="ff336-133">Weist dem Task einen Typ zu.</span><span class="sxs-lookup"><span data-stu-id="ff336-133">Assigns a type to the task.</span></span>|  
|<span data-ttu-id="ff336-134">Attribute.TypeId</span><span class="sxs-lookup"><span data-stu-id="ff336-134">Attribute.TypeId</span></span>|<span data-ttu-id="ff336-135">Ruft bei Implementierung in einer abgeleiteten Klasse einen eindeutigen Bezeichner für dieses Attribut ab.</span><span class="sxs-lookup"><span data-stu-id="ff336-135">When implemented in a derived class, gets a unique identifier for this Attribute.</span></span> <span data-ttu-id="ff336-136">Weitere Informationen finden Sie in der .NET Framework-Klassenbibliothek unter der `Attribute.TypeID`-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="ff336-136">For more information, see `Attribute.TypeID` property in the .NET Framework Class Library.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.UITypeName%2A>|<span data-ttu-id="ff336-137">Der Typname der Assembly, der vom [!INCLUDE[ssIS](../../../includes/ssis-md.md)]-Designer zum Laden der Assembly verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ff336-137">The type name of the assembly that is used by [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer to load the assembly.</span></span> <span data-ttu-id="ff336-138">Diese Eigenschaft wird verwendet, um die Benutzeroberflächenassembly für den Task zu suchen.</span><span class="sxs-lookup"><span data-stu-id="ff336-138">This property is used to find the user interface assembly for the task.</span></span>|  
  
 <span data-ttu-id="ff336-139">Im folgenden Codebeispiel wird das <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> gezeigt, wie es aussehen würde, wenn es oberhalb der Klassendefinition codiert wäre.</span><span class="sxs-lookup"><span data-stu-id="ff336-139">The following code example shows the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> as it would look, coded above the class definition.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
namespace Microsoft.SSIS.Samples  
{  
  [DtsTask  
  (  
   DisplayName = "MyTask",  
   IconResource = "MyTask.MyTaskIcon.ico",  
   UITypeName = "My Custom Task," +  
   "Version=1.0.0.0," +  
   "Culture = Neutral," +  
   "PublicKeyToken = 12345abc6789de01",  
   TaskType = "PackageMaintenance",  
   TaskContact = "MyTask; company name; any other information",  
   RequiredProductLevel = DTSProductLevel.None  
   )]  
  public class MyTask : Task  
  {  
    // Your code here.  
  }  
}  
```  
  
```vb  
Imports System  
Imports Microsoft.SqlServer.Dts.Runtime  
  
<DtsTask(DisplayName:="MyTask", _  
 IconResource:="MyTask.MyTaskIcon.ico", _  
 UITypeName:="My Custom Task," & _  
 "Version=1.0.0.0,Culture=Neutral," & _  
 "PublicKeyToken=12345abc6789de01", _  
 TaskType:="PackageMaintenance", _  
 TaskContact:="MyTask; company name; any other information", _  
 RequiredProductLevel:=DTSProductLevel.None)> _  
Public Class MyTask  
  Inherits Task  
  
  ' Your code here.  
  
End Class 'MyTask  
```  
  
 <span data-ttu-id="ff336-140">Der [!INCLUDE[ssIS](../../../includes/ssis-md.md)]-Designer sucht mithilfe der <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.UITypeName%2A>-Eigenschaft des Attributs, das den Namen, den Typnamen, die Version, die Kultur und das öffentliche Schlüsseltoken der Assembly enthält, um die Assembly im globalen Assemblycache (GAC) zu suchen und sie für die Verwendung durch den Designer zu laden.</span><span class="sxs-lookup"><span data-stu-id="ff336-140">The [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer uses the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.UITypeName%2A> property of the attribute that includes the assembly name, type name, version, culture, and public key token, to locate the assembly in the Global Assembly Cache (GAC) and load it for use by the designer.</span></span>  
  
 <span data-ttu-id="ff336-141">Wenn die Assembly gefunden wurde, verwendet der [!INCLUDE[ssIS](../../../includes/ssis-md.md)]-Designer die anderen Eigenschaften im Attribut, um zusätzliche Informationen zum Task im [!INCLUDE[ssIS](../../../includes/ssis-md.md)]-Designer, wie z. B. Namen, Symbol und Beschreibung des Tasks anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ff336-141">After the assembly has been located, [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer uses the other properties in the attribute to display additional information about the task in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, such as the name, icon, and description of the task.</span></span>  
  
 <span data-ttu-id="ff336-142">Die Eigenschaften <xref:Microsoft.SqlServer.Dts.Runtime.Localization.DtsLocalizableAttribute.DisplayName%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.Localization.DtsLocalizableAttribute.Description%2A> und <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.IconResource%2A> geben an, wie dem Benutzer der Task präsentiert wird.</span><span class="sxs-lookup"><span data-stu-id="ff336-142">The <xref:Microsoft.SqlServer.Dts.Runtime.Localization.DtsLocalizableAttribute.DisplayName%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.Localization.DtsLocalizableAttribute.Description%2A>, and <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.IconResource%2A> properties specify how the task is presented to the user.</span></span> <span data-ttu-id="ff336-143">Die <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.IconResource%2A>-Eigenschaft enthält die Ressourcen-ID des in der Benutzeroberflächenassembly eingebetteten Symbols.</span><span class="sxs-lookup"><span data-stu-id="ff336-143">The <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.IconResource%2A> property contains the resource ID of the icon embedded in the user interface assembly.</span></span> <span data-ttu-id="ff336-144">Der Designer lädt die Symbolressource über die ID aus der Assembly und zeigt sie neben dem Tasknamen in der Toolbox sowie auf der Designeroberfläche an, wenn der Task zum Paket hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="ff336-144">The designer loads the icon resource by ID from the assembly, and displays it next to the task name in the toolbox and on the designer surface when the task is added to a package.</span></span> <span data-ttu-id="ff336-145">Wenn ein Task keine Symbolressource bereitstellt, dann verwendet der Designer für den Task ein Standardsymbol.</span><span class="sxs-lookup"><span data-stu-id="ff336-145">If a task does not provide an icon resource, the designer uses a default icon for the task.</span></span>  
  
## <a name="the-idtstaskui-interface"></a><span data-ttu-id="ff336-146">Die IDTSTaskUI-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ff336-146">The IDTSTaskUI Interface</span></span>  
 <span data-ttu-id="ff336-147">Die <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI>-Schnittstelle definiert die Auflistung von Methoden und Eigenschaften, die vom [!INCLUDE[ssIS](../../../includes/ssis-md.md)]-Designer aufgerufen werden, um die mit dem Task verbundene Benutzeroberfläche zu initialisieren und anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ff336-147">The <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI> interface defines the collection of methods and properties called by [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer to initialize and display the user interface associated with the task.</span></span> <span data-ttu-id="ff336-148">Wenn die Benutzeroberfläche für einen Task aufgerufen wird, dann ruft der Designer die <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI.Initialize%2A>-Methode auf, die von der Task-Benutzeroberfläche implementiert wurde, als Sie diese schrieben, und stellt dann die <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>- und <xref:Microsoft.SqlServer.Dts.Runtime.Connections>-Auflistungen des Tasks und des Pakets jeweils als Parameter bereit.</span><span class="sxs-lookup"><span data-stu-id="ff336-148">When the user interface for a task is invoked, the designer calls the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI.Initialize%2A> method, implemented by the task user interface when you wrote it, and then provides the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> and <xref:Microsoft.SqlServer.Dts.Runtime.Connections> collections of the task and package, respectively, as parameters.</span></span> <span data-ttu-id="ff336-149">Diese Auflistungen werden lokal gespeichert und anschließend in der <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI.GetView%2A>-Methode verwendet.</span><span class="sxs-lookup"><span data-stu-id="ff336-149">These collections are stored locally, and used subsequently in the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI.GetView%2A> method.</span></span>  
  
 <span data-ttu-id="ff336-150">Der Designer ruft die <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI.GetView%2A>-Methode auf, um das Fenster anzufordern, das im [!INCLUDE[ssIS](../../../includes/ssis-md.md)]-Designer angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ff336-150">The designer calls the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI.GetView%2A> method to request the window that is displayed in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="ff336-151">Der Task erstellt eine Instanz des Fensters, das die Benutzeroberfläche für den Task enthält, und gibt die Benutzeroberfläche wieder zur Anzeige an den Designer zurück.</span><span class="sxs-lookup"><span data-stu-id="ff336-151">The task creates an instance of the window that contains the user interface for the task, and returns the user interface to the designer for display.</span></span> <span data-ttu-id="ff336-152">In der Regel werden die <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>- und <xref:Microsoft.SqlServer.Dts.Runtime.Connections>-Objekte dem Fenster über einen überladenen Konstruktor bereitgestellt, sodass sie zum Konfigurieren des Tasks verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="ff336-152">Typically, the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> and <xref:Microsoft.SqlServer.Dts.Runtime.Connections> objects are provided to the window through an overloaded constructor so they can be used to configure the task.</span></span>  
  
 <span data-ttu-id="ff336-153">Der [!INCLUDE[ssIS](../../../includes/ssis-md.md)]-Designer ruft die <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI.GetView%2A>-Methode der Task-Benutzeroberfläche auf, um die Benutzeroberfläche für den Task anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ff336-153">The [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer calls the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI.GetView%2A> method of the task UI to display the user interface for the task.</span></span> <span data-ttu-id="ff336-154">Die Task-Benutzeroberfläche gibt das Windows Form von dieser Methode zurück, und der [!INCLUDE[ssIS](../../../includes/ssis-md.md)]-Designer zeigt dieses Formular als modales Dialogfeld an.</span><span class="sxs-lookup"><span data-stu-id="ff336-154">The task user interface returns the Windows form from this method, and [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer shows this form as a modal dialog box.</span></span> <span data-ttu-id="ff336-155">Wenn das Formular geschlossen ist, untersucht der [!INCLUDE[ssIS](../../../includes/ssis-md.md)]-Designer den Wert der `DialogResult`-Eigenschaft des Formulars, um zu ermitteln, ob der Task geändert wurde und ob diese Änderungen gespeichert werde sollten.</span><span class="sxs-lookup"><span data-stu-id="ff336-155">When the form is closed, [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer examines the value of the `DialogResult` property of the form to determine whether the task has been modified and if these modifications should be saved.</span></span> <span data-ttu-id="ff336-156">Wenn der Wert der `DialogResult`-Eigenschaft `OK` ist, dann ruft der [!INCLUDE[ssIS](../../../includes/ssis-md.md)]-Designer die Persistenzmethoden des Tasks auf, um die Änderungen zu speichern; andernfalls werden die Änderungen verworfen.</span><span class="sxs-lookup"><span data-stu-id="ff336-156">If the value of the `DialogResult` property is `OK`, the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer calls the persistence methods of the task to save the changes; otherwise, the changes are discarded.</span></span>  
  
 <span data-ttu-id="ff336-157">Das folgende Codebeispiel implementiert die <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI>-Schnittstelle, wobei es von der Existenz einer Windows Form-Klasse mit dem Namen SampleTaskForm ausgeht.</span><span class="sxs-lookup"><span data-stu-id="ff336-157">The following code sample implements the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI> interface, and assumes the existence of a Windows form class named SampleTaskForm.</span></span>  
  
```csharp  
using System;  
using System.Windows.Forms;  
using Microsoft.SqlServer.Dts.Runtime;  
using Microsoft.SqlServer.Dts.Runtime.Design;  
  
namespace Sample  
{  
   public class HelloWorldTaskUI : IDtsTaskUI  
   {  
      TaskHost   taskHost;  
      Connections connections;  
      public void Initialize(TaskHost taskHost, IServiceProvider serviceProvider)  
      {  
         this.taskHost = taskHost;  
         IDtsConnectionService cs = serviceProvider.GetService  
         ( typeof( IDtsConnectionService ) ) as   IDtsConnectionService;   
         this.connections = cs.GetConnections();  
      }  
      public ContainerControl GetView()  
      {  
        return new HelloWorldTaskForm(this.taskHost, this.connections);  
      }  
     public void Delete(IWin32Window parentWindow)  
     {  
     }  
     public void New(IWin32Window parentWindow)  
     {  
     }  
   }  
}  
```  
  
```vb  
Imports System  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports Microsoft.SqlServer.Dts.Runtime.Design  
Imports System.Windows.Forms  
  
Public Class HelloWorldTaskUI  
  Implements IDtsTaskUI  
  
  Dim taskHost As TaskHost  
  Dim connections As Connections  
  
  Public Sub Initialize(ByVal taskHost As TaskHost, ByVal serviceProvider As IServiceProvider) _  
    Implements IDtsTaskUI.Initialize  
  
    Dim cs As IDtsConnectionService  
  
    Me.taskHost = taskHost  
    cs = DirectCast(serviceProvider.GetService(GetType(IDtsConnectionService)), IDtsConnectionService)  
    Me.connections = cs.GetConnections()  
  
  End Sub  
  
  Public Function GetView() As ContainerControl _  
    Implements IDtsTaskUI.GetView  
  
    Return New HelloWorldTaskForm(Me.taskHost, Me.connections)  
  
  End Function  
  
  Public Sub Delete(ByVal parentWindow As IWin32Window) _  
    Implements IDtsTaskUI.Delete  
  
  End Sub  
  
  Public Sub [New](ByVal parentWindow As IWin32Window) _  
    Implements IDtsTaskUI.[New]  
  
  End Sub  
  
End Class  
```  
  
<span data-ttu-id="ff336-158">![Integration Services Symbol (klein)](../../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="ff336-158">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="ff336-159">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="ff336-159">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="ff336-160">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="ff336-160">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="ff336-161">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ff336-161">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff336-162">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ff336-162">See Also</span></span>  
 <span data-ttu-id="ff336-163">[Erstellen eines benutzerdefinierten Tasks](creating-a-custom-task.md) </span><span class="sxs-lookup"><span data-stu-id="ff336-163">[Creating a Custom Task](creating-a-custom-task.md) </span></span>  
 <span data-ttu-id="ff336-164">[Codieren eines benutzerdefinierten Tasks](coding-a-custom-task.md) </span><span class="sxs-lookup"><span data-stu-id="ff336-164">[Coding a Custom Task](coding-a-custom-task.md) </span></span>  
 [<span data-ttu-id="ff336-165">Entwickeln einer Benutzeroberfläche für einen benutzerdefinierten Task</span><span class="sxs-lookup"><span data-stu-id="ff336-165">Developing a User Interface for a Custom Task</span></span>](developing-a-user-interface-for-a-custom-task.md)  
  
  
