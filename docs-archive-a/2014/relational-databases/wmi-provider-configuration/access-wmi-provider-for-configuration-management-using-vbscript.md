---
title: Ändern der erweiterten Eigenschaften des SQL Server Dienstanbieter mithilfe von VBScript | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- VBScript [WMI]
- modifying SQL Server Service properties
- WMI Provider for Configuration Management, VBScript
ms.assetid: f3c5d981-eaa3-4d34-9b91-37e42636aa81
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 2cf722b00a31723b77624c33fef81a82ff0cb926
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622456"
---
# <a name="modify-sql-server-service-advanced-properties-using-vbscript"></a><span data-ttu-id="c42d2-102">Ändern der erweiterten Eigenschaften des SQL Server-Diensts mit VBScript</span><span class="sxs-lookup"><span data-stu-id="c42d2-102">Modify SQL Server Service Advanced Properties using VBScript</span></span>
  <span data-ttu-id="c42d2-103">In diesem Abschnitt wird beschrieben, wie Sie ein VBScript-Programm erstellen, das die Version der installierten Instanzen von auflistet [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , die auf einem Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c42d2-103">This section describes how to create a VBScript program that lists the version of installed instances of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are running on a computer.</span></span>  
  
 <span data-ttu-id="c42d2-104">Mit dem Codebeispiel werden die Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], die auf dem Computer ausgeführt werden, und deren Version aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="c42d2-104">The code example lists the instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on the computer and its version.</span></span>  
  
### <a name="listing-name-and-version-of-installed-instances-of-sql-server"></a><span data-ttu-id="c42d2-105">Auflisten der Namen und der Version von installierten Instanzen von SQL Server</span><span class="sxs-lookup"><span data-stu-id="c42d2-105">Listing name and version of installed instances of SQL Server</span></span>  
  
1.  <span data-ttu-id="c42d2-106">Öffnen Sie ein neues Dokument in einem Texteditor wie [!INCLUDE[msCoName](../../includes/msconame-md.md)] Editor.</span><span class="sxs-lookup"><span data-stu-id="c42d2-106">Open a new document in a text editor, such as [!INCLUDE[msCoName](../../includes/msconame-md.md)] Notepad.</span></span> <span data-ttu-id="c42d2-107">Kopieren Sie den Code, den Sie im Anschluss an diese Prozedur finden, und speichern Sie die Datei mit der Erweiterung .vbs.</span><span class="sxs-lookup"><span data-stu-id="c42d2-107">Copy the code that follows this procedure and save the file with a .vbs extension.</span></span> <span data-ttu-id="c42d2-108">Dieses Beispiel hat den Namen test.vbs.</span><span class="sxs-lookup"><span data-stu-id="c42d2-108">This example is called test.vbs.</span></span>  
  
2.  <span data-ttu-id="c42d2-109">Stellen Sie eine Verbindung zu einer Instanz des WMI-Anbieters für die Computerverwaltung mit der VBScript `GetObject`-Funktion her.</span><span class="sxs-lookup"><span data-stu-id="c42d2-109">Connect to an instance of the WMI Provider for Computer Management with the VBScript `GetObject` function.</span></span> <span data-ttu-id="c42d2-110">In diesem Beispiel wird eine Verbindung zu einem Remotecomputer mit dem Namen mpc hergestellt, allerdings wird der Computername zur Verbindung zum lokalen Computer ausgelassen: winmgmts:root\Microsoft\SqlServer\ComputerManagement.</span><span class="sxs-lookup"><span data-stu-id="c42d2-110">This example connects to a remote computer named mpc, but omit the computer name to connect to the local computer: winmgmts:root\Microsoft\SqlServer\ComputerManagement.</span></span> <span data-ttu-id="c42d2-111">Weitere Informationen zur `GetObject`-Funktion finden Sie in der VBScript-Referenz.</span><span class="sxs-lookup"><span data-stu-id="c42d2-111">For more information about the `GetObject` function, see the VBScript reference.</span></span>  
  
3.  <span data-ttu-id="c42d2-112">Verwenden Sie die `InstancesOf`-Methode, um eine Liste der Dienste aufzuzählen.</span><span class="sxs-lookup"><span data-stu-id="c42d2-112">Use the `InstancesOf` method to enumerate a list of the services.</span></span> <span data-ttu-id="c42d2-113">Die Dienste können auch mit einer einfachen WQL-Abfrage und einer `ExecQuery`-Methode anstelle der `InstancesOf`-Methode aufgezählt werden.</span><span class="sxs-lookup"><span data-stu-id="c42d2-113">The services can also be enumerated by using a simple WQL query and an `ExecQuery` method instead of the `InstancesOf` method.</span></span>  
  
4.  <span data-ttu-id="c42d2-114">Verwenden Sie die `ExecQuery`-Methode und eine WQL-Abfrage, um den Namen und die Version der installierten Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] abzurufen.</span><span class="sxs-lookup"><span data-stu-id="c42d2-114">Use the `ExecQuery` method and a WQL query to retrieve the name and version of the installed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
5.  <span data-ttu-id="c42d2-115">Speichern Sie die Datei .</span><span class="sxs-lookup"><span data-stu-id="c42d2-115">Save the file.</span></span>  
  
6.  <span data-ttu-id="c42d2-116">Führen Sie das Skript aus, indem Sie `cscript test.vbs` an der Eingabeaufforderung eingeben.</span><span class="sxs-lookup"><span data-stu-id="c42d2-116">Run the script by typing `cscript test.vbs` at the command prompt.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c42d2-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c42d2-117">Example</span></span>  
  
```  
set wmi = GetObject("WINMGMTS:\\.\root\Microsoft\SqlServer\ComputerManagement12")  
for each prop in wmi.ExecQuery("select * from SqlServiceAdvancedProperty where SQLServiceType = 1 AND PropertyName = 'VERSION'")  
WScript.Echo prop.ServiceName & " " & prop.PropertyName & ": " & prop.PropertyStrValue  
next  
```  
  
  
