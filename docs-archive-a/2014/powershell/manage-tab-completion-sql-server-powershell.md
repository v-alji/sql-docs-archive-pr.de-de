---
title: Verwalten der Befehlszeilenergänzung (SQL Server PowerShell) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: 6296848a-890f-4ad3-8d9f-92ed6a79aa00
author: stevestein
ms.author: sstein
ms.openlocfilehash: 72bcf96245c536d6ea444bc1d7964b7579e793c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622737"
---
# <a name="manage-tab-completion-sql-server-powershell"></a><span data-ttu-id="1168c-102">Verwalten der Befehlszeilenergänzung (SQL Server PowerShell)</span><span class="sxs-lookup"><span data-stu-id="1168c-102">Manage Tab Completion (SQL Server PowerShell)</span></span>
  <span data-ttu-id="1168c-103">Die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell-Snap-Ins führen drei Variablen (`$SqlServerMaximumTabCompletion`, `$SqlServerMaximumChildItems` und `$SqlServerIncludeSystemObjects`) zum Steuern der Windows PowerShell-Befehlszeilenergänzung ein.</span><span class="sxs-lookup"><span data-stu-id="1168c-103">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell snap-ins introduce three variables (`$SqlServerMaximumTabCompletion`, `$SqlServerMaximumChildItems`, and `$SqlServerIncludeSystemObjects`) to control Windows PowerShell tab completion.</span></span> <span data-ttu-id="1168c-104">Die Befehlszeilenergänzung reduziert den Tippaufwand durch Zurückgeben von Tabellen mit Elementen, deren Namen mit der eingegebenen Zeichenfolge beginnen.</span><span class="sxs-lookup"><span data-stu-id="1168c-104">Tab completion reduces the amount of typing you must do by returning tables of items whose names start with the string you are typing.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="1168c-105">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="1168c-105">Before You Begin</span></span>  
 <span data-ttu-id="1168c-106">Wenn Sie die Windows PowerShell-Befehlszeilenergänzung verwenden und einen Teil eines Pfad- oder Cmdlet-Namens eingegeben haben, können Sie die TAB-TASTE drücken, um eine Liste der Elemente anzuzeigen, deren Namen mit dem bereits eingegebenen Teil übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="1168c-106">With Windows PowerShell tab-completion, when you have typed part of a path or cmdlet name, you can hit the Tab key to get a list of the items whose names match what you have already typed.</span></span> <span data-ttu-id="1168c-107">Sie können dann das gewünschte Element aus der Liste auswählen, ohne den Rest des Namens eingeben zu müssen.</span><span class="sxs-lookup"><span data-stu-id="1168c-107">You can then select the item you want from the list without having to type the rest of the name.</span></span>  
  
 <span data-ttu-id="1168c-108">Wenn Sie in einer Datenbank arbeiten, die zahlreiche Objekte enthält, können die Listen der Befehlszeilenergänzung sehr umfangreich werden.</span><span class="sxs-lookup"><span data-stu-id="1168c-108">If you are working in a database that has a lot of objects, the tab-completion lists can become very large.</span></span> <span data-ttu-id="1168c-109">Einige [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Objekttypen, z. B. Sichten, verfügen außerdem über zahlreiche Systemobjekte.</span><span class="sxs-lookup"><span data-stu-id="1168c-109">Some [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] object types, such as views, also have large numbers of system objects.</span></span>  
  
 <span data-ttu-id="1168c-110">Die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Snap-Ins führen drei Systemvariablen ein, mit denen Sie die von der Befehlszeilenergänzung und **Get-ChildItem**bereitgestellte Informationsmenge steuern können.</span><span class="sxs-lookup"><span data-stu-id="1168c-110">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] snap-ins introduces three system variables that you can use to control the amount of information presented by tab-completion and **Get-ChildItem**.</span></span>  
  
 <span data-ttu-id="1168c-111">**$SqlServerMaximumTabCompletion =** *n*</span><span class="sxs-lookup"><span data-stu-id="1168c-111">**$SqlServerMaximumTabCompletion =** *n*</span></span>  
 <span data-ttu-id="1168c-112">Gibt die maximale Anzahl der Objekte an, die in der Befehlszeilenergänzungsliste enthalten sein sollen.</span><span class="sxs-lookup"><span data-stu-id="1168c-112">Specifies the maximum number of objects to include in a tab-completion list.</span></span> <span data-ttu-id="1168c-113">Wenn Sie die TAB-TASTE an einem Pfadknoten betätigen, der mehr als *n* Objekte aufweist, wird die Befehlszeilenergänzungs-Liste bei *n*abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="1168c-113">If you select Tab at a path node having more than *n* objects, the tab-completion list is truncated at *n*.</span></span> <span data-ttu-id="1168c-114">*n* ist eine ganze Zahl.</span><span class="sxs-lookup"><span data-stu-id="1168c-114">*n* is an integer.</span></span> <span data-ttu-id="1168c-115">0 ist die Standardeinstellung und bedeutet, dass die Anzahl der aufgeführten Objekte nicht begrenzt ist.</span><span class="sxs-lookup"><span data-stu-id="1168c-115">0 is the default setting, and means there is no limit to the number of objects listed.</span></span>  
  
 <span data-ttu-id="1168c-116">**$SqlServerMaximumChildItems =** *n*</span><span class="sxs-lookup"><span data-stu-id="1168c-116">**$SqlServerMaximumChildItems =** *n*</span></span>  
 <span data-ttu-id="1168c-117">Gibt die maximale Anzahl der von **Get-ChildItem**angezeigten Objekte an.</span><span class="sxs-lookup"><span data-stu-id="1168c-117">Specifies the maximum number of objects displayed by **Get-ChildItem**.</span></span> <span data-ttu-id="1168c-118">Wenn Sie **Get-ChildItem** an einem Pfadknoten ausführen, der mehr als *n* Objekte aufweist, wird die Befehlszeilenergänzungs-Liste bei *n*abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="1168c-118">If **Get-ChildItem** is run at a path node having more than *n* objects, the list is truncated at *n*.</span></span> <span data-ttu-id="1168c-119">*n* ist eine ganze Zahl.</span><span class="sxs-lookup"><span data-stu-id="1168c-119">*n* is an integer.</span></span> <span data-ttu-id="1168c-120">0 ist die Standardeinstellung und bedeutet, dass die Anzahl der aufgeführten Objekte nicht begrenzt ist.</span><span class="sxs-lookup"><span data-stu-id="1168c-120">0 is the default setting, and means there is no limit to the number of objects listed.</span></span>  
  
 <span data-ttu-id="1168c-121">**$SqlServerIncludeSystemObjects =** { **$True** | **$False** }</span><span class="sxs-lookup"><span data-stu-id="1168c-121">**$SqlServerIncludeSystemObjects =** { **$True** | **$False** }</span></span>  
 <span data-ttu-id="1168c-122">Wenn **$True**, werden Systemobjekte durch Befehlszeilenergänzung und **Get-ChildItem**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1168c-122">If **$True**, system objects are displayed by tab-completion and **Get-ChildItem**.</span></span> <span data-ttu-id="1168c-123">Wenn **$False**, werden keine Systemobjekte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1168c-123">If **$False**, no system objects are displayed.</span></span> <span data-ttu-id="1168c-124">Die Standardeinstellung ist **$false**.</span><span class="sxs-lookup"><span data-stu-id="1168c-124">The default setting is **$False**.</span></span>  
  
## <a name="set-the-sql-server-tab-completion-variables"></a><span data-ttu-id="1168c-125">Festlegen der Variablen für die SQL Server-Befehlszeilenergänzung</span><span class="sxs-lookup"><span data-stu-id="1168c-125">Set the SQL Server Tab Completion Variables</span></span>  
 <span data-ttu-id="1168c-126">Legen Sie für die vom Standardwert zu ändernden Variablen einen neuen Wert fest.</span><span class="sxs-lookup"><span data-stu-id="1168c-126">For any of the variables you want to change from the default value, set the variable to the new value.</span></span>  
  
### <a name="example-powershell"></a><span data-ttu-id="1168c-127">Beispiel (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="1168c-127">Example (PowerShell)</span></span>  
 <span data-ttu-id="1168c-128">Im folgenden Beispiel werden alle drei Variablen festgelegt und ihre Einstellungen aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="1168c-128">The following example sets all three variables and lists their settings:</span></span>  
  
```powershell
$SqlServerMaximumTabCompletion = 20  
$SqlServerMaximumChildItems = 10  
$SqlServerIncludeSystemObjects = $False  
dir variable:sqlserver*  
```  
  
## <a name="see-also"></a><span data-ttu-id="1168c-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1168c-129">See Also</span></span>  
 [<span data-ttu-id="1168c-130">SQL Server-PowerShell</span><span class="sxs-lookup"><span data-stu-id="1168c-130">SQL Server PowerShell</span></span>](sql-server-powershell.md)  
