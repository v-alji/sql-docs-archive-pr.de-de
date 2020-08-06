---
title: Duplizieren von Tabellen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- copying tables
- tables [SQL Server], duplicating
- duplicating tables
- table copying [SQL Server]
ms.assetid: c6b07423-d1e5-4e5e-8681-5088921f5df3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 793a38416f86a5b43a3e3bb2420127d7acf2af1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615916"
---
# <a name="duplicate-tables"></a><span data-ttu-id="cd1b0-102">Duplizieren von Tabellen</span><span class="sxs-lookup"><span data-stu-id="cd1b0-102">Duplicate Tables</span></span>
  <span data-ttu-id="cd1b0-103">Sie können mit [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] oder [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] eine vorhandene Tabelle in [!INCLUDE[tsql](../../includes/tsql-md.md)] duplizieren, indem Sie eine neue Tabelle erstellen und dann Spalteninformationen aus einer vorhandenen Tabelle kopieren.</span><span class="sxs-lookup"><span data-stu-id="cd1b0-103">You can duplicate an existing table in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)] by creating a new table and then copying column information from an existing table.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="cd1b0-104">Mit diesem Vorgang wird nur die Struktur einer Tabelle dupliziert, nicht die einzelnen Tabellenzeilen.</span><span class="sxs-lookup"><span data-stu-id="cd1b0-104">This operation duplicates only the structure of a table; it does not duplicate any table rows.</span></span>  
  
 <span data-ttu-id="cd1b0-105">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="cd1b0-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="cd1b0-106">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="cd1b0-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="cd1b0-107">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="cd1b0-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="cd1b0-108">**So duplizieren Sie eine Tabelle mit:**</span><span class="sxs-lookup"><span data-stu-id="cd1b0-108">**To duplicate a table, using:**</span></span>  
  
     [<span data-ttu-id="cd1b0-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cd1b0-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="cd1b0-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cd1b0-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="cd1b0-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="cd1b0-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="cd1b0-112">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="cd1b0-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="cd1b0-113">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="cd1b0-113">Permissions</span></span>  
 <span data-ttu-id="cd1b0-114">Erfordert die CREATE TABLE-Berechtigung in der Zieldatenbank.</span><span class="sxs-lookup"><span data-stu-id="cd1b0-114">Requires CREATE TABLE permission in the destination database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="cd1b0-115">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cd1b0-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-duplicate-a-table"></a><span data-ttu-id="cd1b0-116">So duplizieren Sie eine Tabelle</span><span class="sxs-lookup"><span data-stu-id="cd1b0-116">To duplicate a table</span></span>  
  
1.  <span data-ttu-id="cd1b0-117">Stellen Sie sicher, dass eine Verbindung mit der Datenbank vorhanden ist, in der Sie die Tabelle erstellen möchten, und dass die Datenbank im Objekt-Explorer ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="cd1b0-117">Make sure you are connected to the database in which you want to create the table and that the database is selected in Object Explorer.</span></span>  
  
2.  <span data-ttu-id="cd1b0-118">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf **Tabellen** , und klicken Sie dann auf **Neue Tabelle**.</span><span class="sxs-lookup"><span data-stu-id="cd1b0-118">In Object Explorer, right-click **Tables** and click **New Table**.</span></span>  
  
3.  <span data-ttu-id="cd1b0-119">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf die Tabelle, die Sie kopieren möchten, und klicken Sie dann auf **Entwerfen**.</span><span class="sxs-lookup"><span data-stu-id="cd1b0-119">In Object Explorer right-click the table you want to copy and click **Design**.</span></span>  
  
4.  <span data-ttu-id="cd1b0-120">Wählen Sie in der vorhandenen Tabelle die Spalten aus, und klicken Sie im Menü **Bearbeiten** auf **Kopieren**.</span><span class="sxs-lookup"><span data-stu-id="cd1b0-120">Select the columns in the existing table and, from the **Edit** menu, click **Copy**.</span></span>  
  
5.  <span data-ttu-id="cd1b0-121">Wechseln Sie zurück in die neue Tabelle, und markieren Sie die erste Zeile.</span><span class="sxs-lookup"><span data-stu-id="cd1b0-121">Switch back to the new table and select the first row.</span></span>  
  
6.  <span data-ttu-id="cd1b0-122">Klicken Sie im Menü **Bearbeiten** auf **Einfügen**.</span><span class="sxs-lookup"><span data-stu-id="cd1b0-122">From the **Edit** menu, click **Paste**.</span></span>  
  
7.  <span data-ttu-id="cd1b0-123">Klicken Sie im Menü **Datei** auf **Speichern**_table name_.</span><span class="sxs-lookup"><span data-stu-id="cd1b0-123">From the **File** menu, click **Save**_table name_.</span></span>  
  
8.  <span data-ttu-id="cd1b0-124">Geben Sie im Dialogfeld **Namen auswählen** einen Namen für die neue Tabelle ein, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="cd1b0-124">In the **Choose Name** dialog box, type a name for the new table and click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="cd1b0-125">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cd1b0-125">Using Transact-SQL</span></span>  
  
#### <a name="to-duplicate-a-table-in-query-editor"></a><span data-ttu-id="cd1b0-126">So duplizieren Sie eine Tabelle im Abfrage-Editor</span><span class="sxs-lookup"><span data-stu-id="cd1b0-126">To duplicate a table in Query Editor</span></span>  
  
1.  <span data-ttu-id="cd1b0-127">Stellen Sie sicher, dass eine Verbindung mit der Datenbank vorhanden ist, in der Sie die Tabelle erstellen möchten, und dass die Datenbank im Objekt-Explorer ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="cd1b0-127">Make sure you are connected to the database in which you want to create the table and that the database is selected in Object Explorer.</span></span>  
  
2.  <span data-ttu-id="cd1b0-128">Klicken Sie mit der rechten Maustaste auf die Tabelle, die Sie duplizieren möchten, zeigen Sie auf **Skript für Tabelle als**, zeigen Sie dann auf **CREATE in**, und wählen Sie **Neues Abfrage-Editor-Fenster**aus.</span><span class="sxs-lookup"><span data-stu-id="cd1b0-128">Right-click the table you wish to duplicate, point to **Script Table as**, then point to **CREATE to**, and then select **New Query Editor Window**.</span></span>  
  
3.  <span data-ttu-id="cd1b0-129">Ändern Sie den Namen der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="cd1b0-129">Change the name of the table.</span></span>  
  
4.  <span data-ttu-id="cd1b0-130">Entfernen Sie alle Spalten, die nicht in der neuen Tabelle benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="cd1b0-130">Remove any columns that are not needed in the new table.</span></span>  
  
5.  <span data-ttu-id="cd1b0-131">Klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="cd1b0-131">Click **Execute**.</span></span>  
  
  
