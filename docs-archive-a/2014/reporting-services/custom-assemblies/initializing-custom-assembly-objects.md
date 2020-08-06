---
title: Initialisieren von Objekten benutzerdefinierter Assemblys | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- initializing custom assemblies [Reporting Services]
- custom assemblies [Reporting Services], initializing
- OnInit method
ms.assetid: 26fd74dc-d02f-40f7-aeb3-50ce05e9e6b9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2aba0bd8b71b26651067a2370728dcdff521ceaa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617793"
---
# <a name="initializing-custom-assembly-objects"></a><span data-ttu-id="4e1a4-102">Initialisieren von Objekten benutzerdefinierter Assemblys</span><span class="sxs-lookup"><span data-stu-id="4e1a4-102">Initializing Custom Assembly Objects</span></span>
  <span data-ttu-id="4e1a4-103">In einigen Fällen müssen Sie die Werte der Eigenschaften und Felder in Ihren benutzerdefinierten Assemblyklassen beim Instanziieren initialisieren.</span><span class="sxs-lookup"><span data-stu-id="4e1a4-103">In some cases, you may need to initialize property and field values in your custom assembly classes when you instantiate them.</span></span> <span data-ttu-id="4e1a4-104">Wahrscheinlich müssen Sie die benutzerdefinierten Klassen mit den Werten initialisieren, die Ihnen von den globalen Objektauflistungen des Berichts zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="4e1a4-104">You will most likely need to initialize your custom classes with values available to you from the report's global object collections.</span></span> <span data-ttu-id="4e1a4-105">Hierzu überschreiben Sie die **OnInit**-Methode des **Code**-Objekts eines Berichts.</span><span class="sxs-lookup"><span data-stu-id="4e1a4-105">You do this by overriding the **OnInit** method of the **Code** object of a report.</span></span> <span data-ttu-id="4e1a4-106">Verwenden Sie das **Code**-Element der Berichtsdefinition, um auf **OnInit** zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="4e1a4-106">To access **OnInit**, use the **Code** element of the report definition.</span></span> <span data-ttu-id="4e1a4-107">Es gibt zwei Techniken, um Eigenschaften- oder Feldwerte der Klassen in einer benutzerdefinierten Assembly zu initialisieren, die Sie in Ihrem Bericht verwenden möchten: Entweder deklarieren und erstellen Sie mit **OnInit** eine neue Instanz Ihrer Klasse, oder Sie rufen mit **OnInit** eine öffentlich verfügbare Methode auf.</span><span class="sxs-lookup"><span data-stu-id="4e1a4-107">There are two techniques for initializing property or field values of the classes in a custom assembly that you plan to use in your report: You can either declare and create a new instance of your class using **OnInit**, or you can call a publicly available method using **OnInit**.</span></span>  
  
## <a name="global-object-collections-and-initialization"></a><span data-ttu-id="4e1a4-108">Globale Objektauflistungen und Initialisierung</span><span class="sxs-lookup"><span data-stu-id="4e1a4-108">Global Object Collections and Initialization</span></span>  
 <span data-ttu-id="4e1a4-109">Zum Initialisieren der benutzerdefinierten Klassenvariablen stehen Ihnen mehrere Auflistungen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="4e1a4-109">Several collections are available to you for initializing your custom class variables.</span></span> <span data-ttu-id="4e1a4-110">Sie können die **Globals**-Auflistung und **die User**-Auflistung verwenden.</span><span class="sxs-lookup"><span data-stu-id="4e1a4-110">You can use the **Globals** and **User** collections.</span></span> <span data-ttu-id="4e1a4-111">Die Auflistungen **Parameters**, **Fields** und **ReportItems** stehen Ihnen zum Zeitpunkt des Berichtslebensdauerzyklus nicht zur Verfügung, wenn die **OnInit**-Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="4e1a4-111">The **Parameters**, **Fields** and **ReportItems** collections are not available to you at the point in the report lifecycle when the **OnInit** method is invoked.</span></span> <span data-ttu-id="4e1a4-112">Sie müssen den **Report**-Objektverweis einschließen, um die freigegebenen Auflistungen **Globals** oder **User** zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="4e1a4-112">To use the shared collections, **Globals** or **User**, you need to include the **Report** object reference.</span></span> <span data-ttu-id="4e1a4-113">Wenn Sie beispielsweise Ihre benutzerdefinierte Klasse ausgehend von der aktuellen Sprache des Benutzers initialisieren möchten, der auf den Bericht zugreift, könnte Ihr **Code**-Element folgendermaßen aussehen:</span><span class="sxs-lookup"><span data-stu-id="4e1a4-113">For example, to initialize your custom class based on the current language of the user accessing the report, your **Code** element might look like the following:</span></span>  
  
```  
<Code>  
   Dim m_myClass As MyClass  
  
   Protected Overrides Sub OnInit()  
      m_myClass = new MyClass(Report.User!Language, _  
         Report.Globals!ExecutionTime)  
   End Sub  
</Code>  
```  
  
 <span data-ttu-id="4e1a4-114">Eine Möglichkeit, die Eigenschaften- und Feldwerte einer Klasse zu initialisieren (wie bereits zuvor gezeigt), besteht darin, die neue Klasse zu deklarieren und eine neue Instanz davon zu erstellen, indem Sie einen überschriebenen Konstruktor aufrufen.</span><span class="sxs-lookup"><span data-stu-id="4e1a4-114">One way to initialize the property and field values of a class as shown previously is to declare your class and create a new instance of it by calling an overridden constructor.</span></span>  
  
 <span data-ttu-id="4e1a4-115">Eine andere Möglichkeit zur Initialisierung von Eigenschaften- und Feldwerten in den Klassen Ihrer benutzerdefinierten Assemblys besteht im Aufrufen einer öffentlich verfügbaren Methode, die Sie von der **OnInit**-Methode aus definieren.</span><span class="sxs-lookup"><span data-stu-id="4e1a4-115">Another way to initialize the property and field values of the classes in your custom assemblies is to call a publicly available method that you define from the **OnInit** method.</span></span> <span data-ttu-id="4e1a4-116">Sie müssen zuerst in der Berichtsdefinitionsdatei einen Instanznamen für die Klasse hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="4e1a4-116">You first need to add an instance name for your class in the report definition file.</span></span> <span data-ttu-id="4e1a4-117">Sobald Sie den entsprechenden Assemblyverweis und den Instanznamen hinzugefügt haben, können Sie die Initialisierungsmethode aufrufen, um die Eigenschaften- und Feldwerte für Ihre Klasse zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="4e1a4-117">Once you have added the appropriate assembly reference and instance name, you can call your initialization method to initialize property and field values for your class.</span></span> <span data-ttu-id="4e1a4-118">Ihre **OnInit**-Methode könnte folgendermaßen aussehen:</span><span class="sxs-lookup"><span data-stu-id="4e1a4-118">Your **OnInit** method might look like the following:</span></span>  
  
```  
<Code>  
   Protected Overrides Sub OnInit()  
      m_myClass.MyInitializationMethod(Report.User!Language, _  
         Report.Globals!ExecutionTime)  
   End Sub  
</Code>  
```  
  
 <span data-ttu-id="4e1a4-119">Weitere Informationen über das Hinzufügen eines Assemblyverweises und eines Instanznamens für die benutzerdefinierte Klasse finden Sie unter [Hinzufügen eines Assemblyverweises zu einem Bericht (SSRS)](../report-design/add-an-assembly-reference-to-a-report-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="4e1a4-119">For more information about adding an assembly reference and instance name for your custom class, see [Add an Assembly Reference to a Report &#40;SSRS&#41;](../report-design/add-an-assembly-reference-to-a-report-ssrs.md).</span></span>  
  
 <span data-ttu-id="4e1a4-120">Weitere Informationen zur Verwendung der globalen Objektauflistungen finden Sie unter [Integrierte Auflistungen in Ausdrücken (Berichts-Generator und SSRS)](../report-design/built-in-collections-in-expressions-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="4e1a4-120">For more information about the global object collections, see [Built-in Collections in Expressions &#40;Report Builder and SSRS&#41;](../report-design/built-in-collections-in-expressions-report-builder.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e1a4-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4e1a4-121">See Also</span></span>  
 [<span data-ttu-id="4e1a4-122">Verwenden benutzerdefinierter Assemblys mit Berichten</span><span class="sxs-lookup"><span data-stu-id="4e1a4-122">Using Custom Assemblies with Reports</span></span>](using-custom-assemblies-with-reports.md)  
  
  
