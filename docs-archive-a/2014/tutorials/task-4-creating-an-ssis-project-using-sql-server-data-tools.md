---
title: 'Aufgabe 4: Erstellen eines SSIS-Projekts mit SQL Server Data Tools | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 8603ea91-2ec4-40b6-8070-4f824332f5d3
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 07976dbd2c84b1385d79ce3f4ce4f616e0f706b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717050"
---
# <a name="task-4-creating-an-ssis-project-using-sql-server-data-tools"></a><span data-ttu-id="0d82e-102">Aufgabe 4: Erstellen eines SSIS-Projekts mit SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="0d82e-102">Task 4: Creating an SSIS Project using SQL Server Data Tools</span></span>
  <span data-ttu-id="0d82e-103">In dieser Aufgabe erstellen Sie ein SSIS-Projekt mithilfe **SQL Server Data Tools** , um die Bereinigung und den Abgleich der Lieferantendaten zu automatisieren.</span><span class="sxs-lookup"><span data-stu-id="0d82e-103">In this task, you create an SSIS project by using **SQL Server Data Tools** to automate cleansing and matching supplier data.</span></span>

1.  <span data-ttu-id="0d82e-104">Starten Sie **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="0d82e-104">Launch **SQL Server Data Tools**.</span></span> <span data-ttu-id="0d82e-105">Klicken Sie auf Start, zeigen Sie auf **Alle Programme**, erweitern Sie **Microsoft SQL Server 2012**, und klicken Sie auf **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="0d82e-105">Click Start, point to **All Programs**, expand **Microsoft SQL Server 2012**, and click **SQL Server Data Tools**.</span></span>

2.  <span data-ttu-id="0d82e-106">Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="0d82e-106">On the **File** menu, point to **New**, and click **Project**.</span></span>

3.  <span data-ttu-id="0d82e-107">Erweitern Sie im Bereich **installierte Vorlagen** die Option **Business Intelligence** , und wählen Sie **Integration Services**aus.</span><span class="sxs-lookup"><span data-stu-id="0d82e-107">Expand **Business Intelligence** in the **Installed Templates** pane, and select **Integration Services**.</span></span>

     <span data-ttu-id="0d82e-108">![Visual Studio – Neues Projekt (Dialogfeld)](../../2014/tutorials/media/et-creatinganssisprojectusingsqlsdt-01.jpg "Visual Studio – Neues Projekt (Dialogfeld)")</span><span class="sxs-lookup"><span data-stu-id="0d82e-108">![Visual Studio - New Project Dialog Box](../../2014/tutorials/media/et-creatinganssisprojectusingsqlsdt-01.jpg "Visual Studio - New Project Dialog Box")</span></span>

4.  <span data-ttu-id="0d82e-109">Wählen Sie **Integration Services Projekt** in der **Liste der Projekttypen**aus.</span><span class="sxs-lookup"><span data-stu-id="0d82e-109">Select **Integration Services Project** in the **list of project types**.</span></span>

5.  <span data-ttu-id="0d82e-110">Geben Sie **clean\andcurratesuppliers** als **Name** ein, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="0d82e-110">Type **CleanseAndCurateSuppliers** for **Name** and click **OK**.</span></span>

6.  <span data-ttu-id="0d82e-111">Klicken Sie in **Projektmappen-Explorer** Fenster mit der rechten Maustaste auf **Package. DTX** , und wählen Sie **Umbenennen**aus.</span><span class="sxs-lookup"><span data-stu-id="0d82e-111">In **Solution Explorer** window, right-click **Package.dtsx** and select **Rename**.</span></span> <span data-ttu-id="0d82e-112">Wenn **Projektmappen-Explorer** Fenster nicht angezeigt wird, klicken Sie auf der Menüleiste auf **Ansicht** , und klicken Sie auf **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="0d82e-112">If you don't see **Solution Explorer** window, click **View** on the menu bar and click **Solution Explorer**.</span></span>

     <span data-ttu-id="0d82e-113">![Package.dtsx – Umbenennen (Menü)](../../2014/tutorials/media/et-creatinganssisprojectusingsqlsdt-02.jpg "Package.dtsx – Umbenennen (Menü)")</span><span class="sxs-lookup"><span data-stu-id="0d82e-113">![Package.dtsx - Rename Menu](../../2014/tutorials/media/et-creatinganssisprojectusingsqlsdt-02.jpg "Package.dtsx - Rename Menu")</span></span>

7.  <span data-ttu-id="0d82e-114">Geben Sie **cleantandcursor. dzx** ein, und drücken **Sie die Eingabe**Taste.</span><span class="sxs-lookup"><span data-stu-id="0d82e-114">Type **CleanseAndCurate.dtsx** and press **ENTER**.</span></span> <span data-ttu-id="0d82e-115">Stellen Sie sicher, dass die **Erweiterung** **. DTX**beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="0d82e-115">Make sure that the **extension** remains **.dtsx**.</span></span>

## <a name="next-step"></a><span data-ttu-id="0d82e-116">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="0d82e-116">Next Step</span></span>
 [<span data-ttu-id="0d82e-117">Aufgabe 5: Hinzufügen eines Datenflusstasks</span><span class="sxs-lookup"><span data-stu-id="0d82e-117">Task 5: Adding Data Flow Task</span></span>](task-5-adding-data-flow-task.md)


