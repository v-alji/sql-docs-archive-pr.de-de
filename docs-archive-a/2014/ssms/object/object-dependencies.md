---
title: Objektabhängigkeiten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.common.objectdependencies.f1
ms.assetid: c63d1160-3f3d-45df-99be-6fe081125fb5
author: stevestein
ms.author: sstein
ms.openlocfilehash: 13d1775f1e4e6885fe56a43ce40c4ac155c5b361
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725218"
---
# <a name="object-dependencies"></a><span data-ttu-id="f9d2a-102">Objektabhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="f9d2a-102">Object Dependencies</span></span>
  <span data-ttu-id="f9d2a-103">Bestimmte Datenbankobjekte sind von anderen Datenbankobjekten abhängig.</span><span class="sxs-lookup"><span data-stu-id="f9d2a-103">Some database objects have dependencies upon other database objects.</span></span> <span data-ttu-id="f9d2a-104">Sichten und gespeicherte Prozeduren sind beispielsweise vom Vorhandensein von Tabellen abhängig, die die von der Sicht oder der Prozedur zurückgegebenen Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="f9d2a-104">For example, views and stored procedures depend upon the existence of tables that contain the data returned by the view or procedure.</span></span> <span data-ttu-id="f9d2a-105">Auf der Seite „Allgemein“ des Dialogfelds **Objektabhängigkeiten** für das aktuelle Objekt sind sowohl die Datenbankobjekte aufgeführt, die für die ordnungsgemäße Funktion des Objekts vorhanden sein müssen, als auch die Objekte, die vom ausgewählten Objekt abhängig sind.</span><span class="sxs-lookup"><span data-stu-id="f9d2a-105">The **Object Dependencies (General Page)** for the current object lists both the database objects that must be present for the object to function properly and the objects that depend upon the selected object.</span></span> <span data-ttu-id="f9d2a-106">Ein Objekt, das in seiner im Systemkatalog gespeicherten Definition auf ein anderes Objekt verweist, wird als *verweisende Entität*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="f9d2a-106">An object that references another object in its definition and that definition is stored in the system catalog is called a *referencing entity*.</span></span> <span data-ttu-id="f9d2a-107">Ein Objekt, auf das von einem anderen Objekt verwiesen wird, wird als *Entität, auf die verwiesen wird*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="f9d2a-107">An object that is referred to by another object is called a *referenced entity*.</span></span>  
  
 <span data-ttu-id="f9d2a-108">Unter **Objektabhängigkeiten** (erweiterte Seite) für die aktuellen Objekte werden die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbankobjekte und [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Objekte aufgeführt, die vom aktuellen Objekt abhängen.</span><span class="sxs-lookup"><span data-stu-id="f9d2a-108">The **Object Dependencies (Advanced Page)** for the current object lists the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database objects and [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] objects that depend on the object.</span></span> <span data-ttu-id="f9d2a-109">Die Objekte werden möglicherweise auf verschiedenen Servern gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f9d2a-109">The objects may be stored on different servers.</span></span>  
  
 <span data-ttu-id="f9d2a-110">Mithilfe dieses Dialogfelds können Sie sich einen Überblick über die Abhängigkeiten verschaffen, bevor Sie das ausgewählte Objekt ändern oder löschen.</span><span class="sxs-lookup"><span data-stu-id="f9d2a-110">Use this dialog box to understand the dependencies before changing or deleting the selected object.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="f9d2a-111">Liste der Benutzeroberflächenelemente</span><span class="sxs-lookup"><span data-stu-id="f9d2a-111">UI element list</span></span>  
 <span data-ttu-id="f9d2a-112">**Objekte, die von abhängen**  _\<selected object>_</span><span class="sxs-lookup"><span data-stu-id="f9d2a-112">**Objects that depend on**  _\<selected object>_</span></span>  
 <span data-ttu-id="f9d2a-113">Durch Klicken auf diese Schaltfläche wird eine Liste der Objekte angezeigt, deren Abhängigkeiten nachverfolgt werden und die vom ausgewählten Objekt abhängig sind.</span><span class="sxs-lookup"><span data-stu-id="f9d2a-113">Clicking this button displays a list of those objects that are dependency-tracked and that depend on the selected object.</span></span>  
  
 <span data-ttu-id="f9d2a-114">**Objekte, für die** _\<selected object>_ **abhängig**    </span><span class="sxs-lookup"><span data-stu-id="f9d2a-114">**Objects on which**  _\<selected object>_  **depends**</span></span>  
 <span data-ttu-id="f9d2a-115">Durch Klicken auf diese Schaltfläche wird eine Liste der Objekte angezeigt, deren Abhängigkeiten nachverfolgt werden und von denen das ausgewählte Objekt abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="f9d2a-115">Clicking this button displays a list of those objects that are dependency-tracked, on which the selected object depends.</span></span>  
  
 <span data-ttu-id="f9d2a-116">**Abhängigkeiten**</span><span class="sxs-lookup"><span data-stu-id="f9d2a-116">**Dependencies**</span></span>  
 <span data-ttu-id="f9d2a-117">Nach dem Klicken auf **Objekte, die von** _\<selected object>_ abhängig sind, wird eine hierarchische Ansicht der Objekte angezeigt, die von dem ausgewählten Objekt abhängig sind.</span><span class="sxs-lookup"><span data-stu-id="f9d2a-117">If **Objects that depend on** _\<selected object>_ is clicked, this displays an hierarchical view of objects that depend on the selected object.</span></span> <span data-ttu-id="f9d2a-118">Durch Klicken auf **Objekte, von denen** _\<selected object>_ **abhängt**, wird eine hierarchische Ansicht der Objekte angezeigt, von denen das ausgewählte Objekt abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="f9d2a-118">If **Objects on which** _\<selected object>_ **depends** is clicked, this displays an hierarchical view of objects on which the selected object depends.</span></span>  
  
 <span data-ttu-id="f9d2a-119">**Name**</span><span class="sxs-lookup"><span data-stu-id="f9d2a-119">**Name**</span></span>  
 <span data-ttu-id="f9d2a-120">Zeigt den Namen, des oben in der Strukturansicht **Abhängigkeiten** ausgewählten Objekts an.</span><span class="sxs-lookup"><span data-stu-id="f9d2a-120">Displays the name of the object selected in the **Dependencies** tree view above.</span></span>  
  
 <span data-ttu-id="f9d2a-121">**Typ**</span><span class="sxs-lookup"><span data-stu-id="f9d2a-121">**Type**</span></span>  
 <span data-ttu-id="f9d2a-122">Zeigt den Typ des oben in der Strukturansicht **Abhängigkeiten** ausgewählten Objekts an.</span><span class="sxs-lookup"><span data-stu-id="f9d2a-122">Displays the type of the object selected in the **Dependencies** tree view above.</span></span>  
  
 <span data-ttu-id="f9d2a-123">**Zeitpunkt der letzten Synchronisierung**</span><span class="sxs-lookup"><span data-stu-id="f9d2a-123">**Last Sync Time**</span></span>  
 > [!NOTE]  
>  <span data-ttu-id="f9d2a-124">Diese Option ist nur auf der Seite **Erweitert** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f9d2a-124">This option is available only on the **Advanced** page.</span></span>  
  
 <span data-ttu-id="f9d2a-125">Gibt das Datum und die Uhrzeit des letzten Updates der Abhängigkeitsinformationen an.</span><span class="sxs-lookup"><span data-stu-id="f9d2a-125">Specifies the time and date when the dependency information was last updated.</span></span>  
  
 <span data-ttu-id="f9d2a-126">**Abhängigkeitstyp**</span><span class="sxs-lookup"><span data-stu-id="f9d2a-126">**Dependency type**</span></span>  
 > [!NOTE]  
>  <span data-ttu-id="f9d2a-127">Diese Option ist nur auf der Seite **Allgemein** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f9d2a-127">This option is available only on the **General** page.</span></span>  
  
 <span data-ttu-id="f9d2a-128">Zeigt den Typ der Abhängigkeit zwischen zwei Objekten an.</span><span class="sxs-lookup"><span data-stu-id="f9d2a-128">Displays the type of dependency between two objects.</span></span> <span data-ttu-id="f9d2a-129">Dabei kann es sich um eine der folgenden Methoden handeln:</span><span class="sxs-lookup"><span data-stu-id="f9d2a-129">Can be one of the following:</span></span>  
  
-   <span data-ttu-id="f9d2a-130">Schemagebundene Abhängigkeit</span><span class="sxs-lookup"><span data-stu-id="f9d2a-130">Schema-bound dependency</span></span>  
  
     <span data-ttu-id="f9d2a-131">Dies ist eine Beziehung zwischen zwei Objekten, mit der verhindert wird, dass das Objekt, auf das verwiesen wird, gelöscht oder geändert wird, solange das verweisende Objekt vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="f9d2a-131">Is a relationship between two objects that prevents the referenced object from being dropped or modified as long as the referencing object exists.</span></span> <span data-ttu-id="f9d2a-132">Eine schemagebundene Abhängigkeit wird erstellt, wenn eine Sicht oder eine benutzerdefinierte Funktion mithilfe der WITH SCHEMABINDING-Klausel erstellt wird oder eine Tabelle über eine CHECK- oder DEFAULT-Einschränkung bzw. in der Definition einer berechneten Spalte auf ein anderen Objekt verweist.</span><span class="sxs-lookup"><span data-stu-id="f9d2a-132">A schema-bound dependency is created when a view or user-defined function is created by using the WITH SCHEMABINDING clause, or when a table references another object through a CHECK or DEFAULT constraint or in the definition of a computed column.</span></span>  
  
-   <span data-ttu-id="f9d2a-133">Nicht schemagebundene Abhängigkeit</span><span class="sxs-lookup"><span data-stu-id="f9d2a-133">Non-schema-bound dependency</span></span>  
  
     <span data-ttu-id="f9d2a-134">Dies ist eine Beziehung zwischen zwei Objekten, mit der nicht verhindert wird, dass das Objekt, auf das verwiesen wird, gelöscht oder geändert wird.</span><span class="sxs-lookup"><span data-stu-id="f9d2a-134">Is a relationship between two objects that does not prevent the referenced object from being dropped or modified.</span></span>  
  
-   <span data-ttu-id="f9d2a-135">Nicht verfügbare oder nicht aufgelöste Entität</span><span class="sxs-lookup"><span data-stu-id="f9d2a-135">Not available or Unresolved Entity</span></span>  
  
     <span data-ttu-id="f9d2a-136">Gibt an, dass der Abhängigkeitstyp nicht bestimmt werden kann.</span><span class="sxs-lookup"><span data-stu-id="f9d2a-136">Indicates the dependency type cannot be determined.</span></span> <span data-ttu-id="f9d2a-137">Dies geschieht nur, wenn sich das ausgewählte Objekt auf einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] befindet, bei der es sich um eine frühere Version von [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]handelt.</span><span class="sxs-lookup"><span data-stu-id="f9d2a-137">This occurs only when the selected object is on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is earlier than [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
  
