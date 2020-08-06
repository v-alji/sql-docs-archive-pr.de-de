---
title: Angeben von Instanzen im SQL Server PowerShell-Anbieter | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: 9373de68-fd43-45f2-b9a6-149c96610aeb
author: stevestein
ms.author: sstein
ms.openlocfilehash: cc04bacc1ff36b0b5ce526a377fcdb750ad134a4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617142"
---
# <a name="specify-instances-in-the-sql-server-powershell-provider"></a><span data-ttu-id="e0f46-102">Angeben von Instanzen im SQL Server PowerShell-Anbieter</span><span class="sxs-lookup"><span data-stu-id="e0f46-102">Specify Instances in the SQL Server PowerShell Provider</span></span>
  <span data-ttu-id="e0f46-103">Die für den SQL Server PowerShell-Anbieter angegebenen Pfade müssen die Instanz von [!INCLUDE[ssDE](../includes/ssde-md.md)] und den Computer, auf dem sie ausgeführt wird, angeben.</span><span class="sxs-lookup"><span data-stu-id="e0f46-103">The paths specified for the SQL Server PowerShell provider must identify the instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)] and the computer it is running on.</span></span> <span data-ttu-id="e0f46-104">Die Syntax zum Angeben des Computers und der Instanz muss sowohl den Regeln für die SQL Server-Bezeichner als auch für die Windows PowerShell-Pfade entsprechen.</span><span class="sxs-lookup"><span data-stu-id="e0f46-104">The syntax for specifying the computer and the instance must comply with both the rules for SQL Server identifiers and Windows PowerShell paths.</span></span>  
  
1.  <span data-ttu-id="e0f46-105">**Vorbereitungen:**  [Einschränkungen](#LimitationsRestrictions)</span><span class="sxs-lookup"><span data-stu-id="e0f46-105">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions)</span></span>  
  
2.  <span data-ttu-id="e0f46-106">**Angeben einer Instanz:**  [Beispiele](#Examples)</span><span class="sxs-lookup"><span data-stu-id="e0f46-106">**To specify an instance:**  [Examples](#Examples)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="e0f46-107">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="e0f46-107">Before You Begin</span></span>  
 <span data-ttu-id="e0f46-108">Der erste Knoten, der auf SQLSERVER:\SQL in einem SQL Server-Anbieterpfad folgt, ist der Name des Computers, auf dem die Instanz von [!INCLUDE[ssDE](../includes/ssde-md.md)]ausgeführt wird, z. B.:</span><span class="sxs-lookup"><span data-stu-id="e0f46-108">The first node following the SQLSERVER:\SQL in a SQL Server provider path is the name of the computer that is running the instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)]; for example:</span></span>  
  
```  
SQLSERVER:\SQL\MyComputer  
```  
  
 <span data-ttu-id="e0f46-109">Wenn Sie Windows PowerShell auf demselben Computer ausführen wie die Instanz von [!INCLUDE[ssDE](../includes/ssde-md.md)], können Sie anstelle des Computernamens entweder "localhost" oder "(local)" verwenden.</span><span class="sxs-lookup"><span data-stu-id="e0f46-109">If you are running Windows PowerShell on the same computer as the instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)], you can use either localhost or (local) instead of the name of the computer.</span></span> <span data-ttu-id="e0f46-110">Skripts, die "localhost" oder "(local)" verwenden, können auf jedem Computer ausgeführt werden, ohne entsprechend dem jeweiligen Computernamen geändert werden zu müssen.</span><span class="sxs-lookup"><span data-stu-id="e0f46-110">Scripts that use localhost or (local) can be run on any computer without having to be changed to reflect the different computer names.</span></span>  
  
 <span data-ttu-id="e0f46-111">Sie können mehrere Instanzen des ausführbaren Programms [!INCLUDE[ssDE](../includes/ssde-md.md)] auf demselben Computer ausführen.</span><span class="sxs-lookup"><span data-stu-id="e0f46-111">You can run multiple instances of the [!INCLUDE[ssDE](../includes/ssde-md.md)] executable program on the same computer.</span></span> <span data-ttu-id="e0f46-112">Der Knoten, der dem Computernamen in einem SQL Server-Anbieterpfad folgt, gibt die Instanz an, z. B.:</span><span class="sxs-lookup"><span data-stu-id="e0f46-112">The node following the computer name in a SQL Server provider path identifies the instance; for example:</span></span>  
  
```  
SQLSERVER:\SQL\MyComputer\MyInstance  
```  
  
 <span data-ttu-id="e0f46-113">Jeder Computer kann eine Standardinstanz von [!INCLUDE[ssDE](../includes/ssde-md.md)]aufweisen.</span><span class="sxs-lookup"><span data-stu-id="e0f46-113">Each computer can have one default instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span> <span data-ttu-id="e0f46-114">Sie geben bei der Installation keinen Namen für die Standardinstanz an.</span><span class="sxs-lookup"><span data-stu-id="e0f46-114">You do not specify a name for the default instance when you install it.</span></span> <span data-ttu-id="e0f46-115">Wenn Sie in einer Verbindungszeichenfolge nur einen Computernamen angeben, werden Sie mit der Standardinstanz auf diesem Computer verbunden.</span><span class="sxs-lookup"><span data-stu-id="e0f46-115">If you specify only a computer name in a connection string, you are connected to the default instance on that computer.</span></span> <span data-ttu-id="e0f46-116">Alle anderen Instanzen auf dem Computer müssen benannte Instanzen sein.</span><span class="sxs-lookup"><span data-stu-id="e0f46-116">All other instances on the computer must be named instances.</span></span> <span data-ttu-id="e0f46-117">Sie geben den Instanznamen während des Setups ein, und die Verbindungszeichenfolgen müssen sowohl den Computernamen als auch den Instanznamen angeben.</span><span class="sxs-lookup"><span data-stu-id="e0f46-117">You specify the instance name during setup, and connection strings must specify both the computer name and the instance name.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="e0f46-118">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="e0f46-118">Limitations and Restrictions</span></span>  
 <span data-ttu-id="e0f46-119">Sie können keinen Punkt (.) verwenden, um den lokalen Computer in PowerShell-Skripts anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e0f46-119">You cannot use a period (.) to specify the local computer in PowerShell scripts.</span></span> <span data-ttu-id="e0f46-120">Der Punkt wird nicht unterstützt, da der Punkt von PowerShell als Befehl interpretiert wird.</span><span class="sxs-lookup"><span data-stu-id="e0f46-120">The period is not supported because the period is interpreted as a command by PowerShell.</span></span>  
  
 <span data-ttu-id="e0f46-121">Die Klammerzeichen in "(local)" werden von Windows PowerShell normalerweise als Befehle behandelt.</span><span class="sxs-lookup"><span data-stu-id="e0f46-121">The parenthesis characters in (local) are normally treated as commands by Windows PowerShell.</span></span> <span data-ttu-id="e0f46-122">Sie müssen sie entweder codieren, sie zur Verwendung in einem Pfad mit Escapezeichen versehen oder den Pfad in doppelte Anführungszeichen setzen.</span><span class="sxs-lookup"><span data-stu-id="e0f46-122">You must either encode them or escape them for use in a path, or enclose the path in double-quotation marks.</span></span> <span data-ttu-id="e0f46-123">Weitere Informationen finden Sie unter "Codierung und Decodierung von SQL Server-Bezeichnern".</span><span class="sxs-lookup"><span data-stu-id="e0f46-123">For more information, see Encode and Decode SQL Server Identifiers.</span></span>  
  
 <span data-ttu-id="e0f46-124">Für den [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Anbieter ist immer die Angabe eines Instanznamens erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e0f46-124">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider requires that you always specify an instance name.</span></span> <span data-ttu-id="e0f46-125">Für Standardinstanzen müssen Sie den Instanznamen DEFAULT angeben.</span><span class="sxs-lookup"><span data-stu-id="e0f46-125">For default instances, you must specify an instance name of DEFAULT.</span></span>  
  
##  <a name="examples-computer-and-instance-names"></a><a name="Examples"></a><span data-ttu-id="e0f46-126">Beispiele Computer-und Instanznamen</span><span class="sxs-lookup"><span data-stu-id="e0f46-126">Examples; Computer and Instance Names</span></span>  
 <span data-ttu-id="e0f46-127">Bei diesem Beispiel wird die Standardinstanz auf dem lokalen Computer mithilfe von "localhost" und DEFAULT angegeben:</span><span class="sxs-lookup"><span data-stu-id="e0f46-127">This example uses localhost and DEFAULT to specify the default instance on the local computer:</span></span>  
  
```powershell
Set-Location SQLSERVER:\SQL\localhost\DEFAULT
```  
  
 <span data-ttu-id="e0f46-128">Die Klammerzeichen in "(local)" werden von Windows PowerShell normalerweise als Befehle behandelt.</span><span class="sxs-lookup"><span data-stu-id="e0f46-128">The parenthesis characters in (local) are normally treated as commands by Windows PowerShell.</span></span> <span data-ttu-id="e0f46-129">Daher müssen Sie entweder:</span><span class="sxs-lookup"><span data-stu-id="e0f46-129">You must either:</span></span>  
  
-   <span data-ttu-id="e0f46-130">die Pfadzeichenfolge in Anführungszeichen setzen:</span><span class="sxs-lookup"><span data-stu-id="e0f46-130">Enclose the path string in quotes:</span></span>  
  
    ```powershell
    Set-Location "SQLSERVER:\SQL\(local)\DEFAULT"  
    ```  
  
-   <span data-ttu-id="e0f46-131">die Klammer mit dem Graviszeichen (\`) versehen:</span><span class="sxs-lookup"><span data-stu-id="e0f46-131">Escape the parenthesis using the back tick character (\`):</span></span>  
  
    ```powershell
    Set-Location SQLSERVER:\SQL\`(local`)\DEFAULT  
    ```  
  
-   <span data-ttu-id="e0f46-132">die Klammer in ihrer hexadezimalen Darstellung codieren:</span><span class="sxs-lookup"><span data-stu-id="e0f46-132">Encode the parenthesis using their hexadecimal representation:</span></span>  
  
    ```powershell
    Set-Location SQLSERVER:\SQL\%28local%29\DEFAULT  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e0f46-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e0f46-133">See Also</span></span>  
 <span data-ttu-id="e0f46-134">[SQL Server Bezeichner in PowerShell](sql-server-identifiers-in-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="e0f46-134">[SQL Server Identifiers in PowerShell](sql-server-identifiers-in-powershell.md) </span></span>  
 <span data-ttu-id="e0f46-135">[SQL Server PowerShell Anbieter](sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="e0f46-135">[SQL Server PowerShell Provider](sql-server-powershell-provider.md) </span></span>  
 [<span data-ttu-id="e0f46-136">SQL Server-PowerShell</span><span class="sxs-lookup"><span data-stu-id="e0f46-136">SQL Server PowerShell</span></span>](sql-server-powershell.md)  
