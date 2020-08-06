---
title: Zuordnen von Resultsets zu Variablen in einem Task "SQL ausführen" | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- result sets [Integration Services]
- mapping result sets to variables [Integration Services]
- variables [Integration Services], mapping result sets to
ms.assetid: f76738b6-dc75-4ff9-a3dd-8b083d8e410e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 124982a32aa9987d3dc573c732be4db4d41e8346
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617162"
---
# <a name="map-result-sets-to-variables-in-an-execute-sql-task"></a><span data-ttu-id="2e347-102">Zuordnen von Resultsets zu Variablen in einem Task „SQL ausführen“</span><span class="sxs-lookup"><span data-stu-id="2e347-102">Map Result Sets to Variables in an Execute SQL Task</span></span>
  <span data-ttu-id="2e347-103">In diesem Thema wird das Erstellen einer Zuordnung zwischen einem Resultset und einer Variablen in einem Task "SQL ausführen" beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2e347-103">This topic describes how to create a mapping between a result set and a variable in an Execute SQL task.</span></span> <span data-ttu-id="2e347-104">Indem Sie ein Resultset zu einer Variablen zuordnen, wird das Resultset für andere Elemente des Pakets zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="2e347-104">Mapping a result set to a variable makes the result set available to other elements in the package.</span></span> <span data-ttu-id="2e347-105">Beispielsweise kann ein Skript eines Skripttasks die Variable lesen und dann die Werte des Resultsets verwenden, oder eine XML-Quelle kann das in einer Variable gespeicherte Resultset verwenden.</span><span class="sxs-lookup"><span data-stu-id="2e347-105">For example, a script in a Script task can read the variable and then use the values from the result set or an XML source can consume the result set stored in a variable.</span></span> <span data-ttu-id="2e347-106">Wenn das Resultset durch ein übergeordnetes Paket generiert wird, kann das Resultset für ein untergeordnetes Paket, das von einem Task Paket ausführen aufgerufen wird, zur Verfügung gestellt werden. Hierzu wird das Resultset im übergeordneten Paket einer Variablen zugeordnet. Anschließend wird im untergeordneten Paket eine übergeordnete Variablenkonfiguration erstellt, um den übergeordneten Variablenwert zu speichern.</span><span class="sxs-lookup"><span data-stu-id="2e347-106">If the result set is generated by a parent package, the result set can be made available to a child package called by an Execute Package task by mapping the result set to a variable in the parent package, and then creating a parent package variable configuration in the child package to store the parent variable value.</span></span>  
  
 <span data-ttu-id="2e347-107">Beschreibungen zu verschiedenen Resultsettypen und variablen Datentypen, die Sie Resultsets zuordnen können, finden Sie unter [Resultsets im Task „SQL ausführen“](control-flow/execute-sql-task.md).</span><span class="sxs-lookup"><span data-stu-id="2e347-107">For descriptions of the different types of result sets and the variable data types that you can map to result sets, see [Result Sets in the Execute SQL Task](control-flow/execute-sql-task.md).</span></span>  
  
### <a name="to-map-a-result-set-to-a-variable"></a><span data-ttu-id="2e347-108">So ordnen Sie einer Variablen ein Resultset zu</span><span class="sxs-lookup"><span data-stu-id="2e347-108">To map a result set to a variable</span></span>  
  
1.  <span data-ttu-id="2e347-109">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Projekt mit dem gewünschten Paket.</span><span class="sxs-lookup"><span data-stu-id="2e347-109">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="2e347-110">Doppelklicken Sie im **Projektmappen-Explorer**auf das Paket, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="2e347-110">In **Solution Explorer**, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="2e347-111">Klicken Sie auf die Registerkarte **Ablaufsteuerung** .</span><span class="sxs-lookup"><span data-stu-id="2e347-111">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="2e347-112">Wenn das Paket noch keinen Task SQL ausführen enthält, fügen Sie der Ablaufsteuerung des Pakets einen solchen Task hinzu.</span><span class="sxs-lookup"><span data-stu-id="2e347-112">If the package does not already include an Execute SQL task, add one to the control flow of the package.</span></span> <span data-ttu-id="2e347-113">Weitere Informationen finden Sie unter [Hinzufügen oder Löschen eines Tasks oder Containers in einer Ablauf Steuerung](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md) .</span><span class="sxs-lookup"><span data-stu-id="2e347-113">For more information, see [Add or Delete a Task or a Container in a Control Flow](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md)</span></span>  
  <span data-ttu-id="2e347-114">.</span><span class="sxs-lookup"><span data-stu-id="2e347-114">.</span></span>  
  
5.  <span data-ttu-id="2e347-115">Doppelklicken Sie auf den Task SQL ausführen.</span><span class="sxs-lookup"><span data-stu-id="2e347-115">Double-click the Execute SQL task.</span></span>  
  
6.  <span data-ttu-id="2e347-116">Wählen Sie im Dialogfeld **Editor für den Task 'SQL ausführen'** auf der Seite **Allgemein** den Resultsettyp **Einzelne Zeile**, **Vollständiges Resultset**oder **XML** aus.</span><span class="sxs-lookup"><span data-stu-id="2e347-116">In the **Execute SQL Task Editor** dialog box, on the **General** page, select the **Single row**, **Full result set**, or **XML** result set type.</span></span>  
  
     <span data-ttu-id="2e347-117">Beschreibungen zu den verschiedenen Resultsets finden Sie unter [Resultsets im Task „SQL ausführen“](result-sets-in-the-execute-sql-task.md).</span><span class="sxs-lookup"><span data-stu-id="2e347-117">For descriptions of the different result sets, see [Result Sets in the Execute SQL Task](result-sets-in-the-execute-sql-task.md)</span></span>  
  
7.  <span data-ttu-id="2e347-118">Klicken Sie auf **Resultset**.</span><span class="sxs-lookup"><span data-stu-id="2e347-118">Click **Result Set**.</span></span>  
  
8.  <span data-ttu-id="2e347-119">Klicken Sie auf **Hinzufügen**, um eine Resultsetzuordnung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="2e347-119">To add a result set mapping, click **Add**.</span></span>  
  
9. <span data-ttu-id="2e347-120">Wählen Sie in der Liste **Variablenname** eine Variable aus, oder erstellen Sie eine neue Variable.</span><span class="sxs-lookup"><span data-stu-id="2e347-120">From the **Variables Name** list, select a variable or create a new variable.</span></span> <span data-ttu-id="2e347-121">Weitere Informationen finden Sie unter [Hinzufügen, Löschen, Ändern des Bereichs von benutzerdefinierten Variablen in einem Paket](../../2014/integration-services/add-delete-change-scope-of-user-defined-variable-in-a-package.md).</span><span class="sxs-lookup"><span data-stu-id="2e347-121">For more information, see [Add, Delete, Change Scope of User-Defined Variable in a Package](../../2014/integration-services/add-delete-change-scope-of-user-defined-variable-in-a-package.md).</span></span>  
  
     <span data-ttu-id="2e347-122">Beschreibungen zu den variablen Datentypen, die Sie den unterschiedlichen Resultsets zuordnen können, finden Sie unter [Resultsets im Task „SQL ausführen“](result-sets-in-the-execute-sql-task.md).</span><span class="sxs-lookup"><span data-stu-id="2e347-122">For descriptions of the variable data types that you can map to the different result sets, see [Result Sets in the Execute SQL Task](result-sets-in-the-execute-sql-task.md).</span></span>  
  
     <span data-ttu-id="2e347-123">Informationen dazu, wie eine Variable einer einzelnen Spalte und mehrere Variablen mehreren Spalten zugeordnet werden, finden Sie im Abschnitt **Auffüllen einer Variablen mit einem Resultset** in [Result Sets in the Execute SQL Task](control-flow/execute-sql-task.md).</span><span class="sxs-lookup"><span data-stu-id="2e347-123">For information on how to map a variable to a single column and to map multiple variables to multiple columns, see the **Populating a Variable with a Result Set** section in [Result Sets in the Execute SQL Task](control-flow/execute-sql-task.md).</span></span>  
  
10. <span data-ttu-id="2e347-124">Ändern Sie in der Liste **Ergebnisname** optional den Namen des Resultsets.</span><span class="sxs-lookup"><span data-stu-id="2e347-124">In the **Result Name** list, optionally, modify the name of the result set.</span></span>  
  
     <span data-ttu-id="2e347-125">Im Allgemeinen können Sie den Spaltennamen als Resultsetnamen verwenden, oder Sie können die Ordnungsposition der Spalte in der Spaltenliste als Resultset verwenden.</span><span class="sxs-lookup"><span data-stu-id="2e347-125">In general, you can use the column name as the result set name, or you can use the ordinal position of the column in the column list as the result set.</span></span> <span data-ttu-id="2e347-126">Ob ein Spaltenname als Resultsetname verwendet werden kann, hängt davon ab, für welchen Anbieter der Task konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="2e347-126">The ability to use a column name as the result set name depends on the provider that the task is configured to use.</span></span> <span data-ttu-id="2e347-127">Nicht alle Anbieter machen Spaltennamen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2e347-127">Not all providers make column names available.</span></span>  
  
11. <span data-ttu-id="2e347-128">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="2e347-128">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e347-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2e347-129">See Also</span></span>  
 <span data-ttu-id="2e347-130">[SQL ausführen (Task)](control-flow/execute-sql-task.md) </span><span class="sxs-lookup"><span data-stu-id="2e347-130">[Execute SQL Task](control-flow/execute-sql-task.md) </span></span>  
 <span data-ttu-id="2e347-131">[Resultsets im Task "SQL ausführen"](result-sets-in-the-execute-sql-task.md) </span><span class="sxs-lookup"><span data-stu-id="2e347-131">[Result Sets in the Execute SQL Task](result-sets-in-the-execute-sql-task.md) </span></span>  
 <span data-ttu-id="2e347-132">[Task ' Paket ausführen '](control-flow/execute-package-task.md) </span><span class="sxs-lookup"><span data-stu-id="2e347-132">[Execute Package Task](control-flow/execute-package-task.md) </span></span>  
 <span data-ttu-id="2e347-133">[Paket Konfigurationen](../../2014/integration-services/package-configurations.md) </span><span class="sxs-lookup"><span data-stu-id="2e347-133">[Package Configurations](../../2014/integration-services/package-configurations.md) </span></span>  
 <span data-ttu-id="2e347-134">[Erstellen von Paket Konfigurationen](../../2014/integration-services/create-package-configurations.md) </span><span class="sxs-lookup"><span data-stu-id="2e347-134">[Create Package Configurations](../../2014/integration-services/create-package-configurations.md) </span></span>  
 <span data-ttu-id="2e347-135">[Verwenden der Werte von Variablen und Parametern in einem untergeordneten Paket](../../2014/integration-services/use-the-values-of-variables-and-parameters-in-a-child-package.md) </span><span class="sxs-lookup"><span data-stu-id="2e347-135">[Use the Values of Variables and Parameters in a Child Package](../../2014/integration-services/use-the-values-of-variables-and-parameters-in-a-child-package.md) </span></span>  
 [<span data-ttu-id="2e347-136">Integration Services-Variablen &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="2e347-136">Integration Services &#40;SSIS&#41; Variables</span></span>](integration-services-ssis-variables.md)  
  
  