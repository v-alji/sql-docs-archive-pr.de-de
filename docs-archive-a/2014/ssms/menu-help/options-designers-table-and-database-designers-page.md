---
title: Optionen (Designer-Seite für Tabellen und Datenbankdesigner) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Designers.Table_Designer
ms.assetid: b43f4b97-17b9-4004-a824-f77b9e145741
author: stevestein
ms.author: sstein
ms.openlocfilehash: d8a1218b4ea1ae9c6f9cf734bb33a2a4bebcb167
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620102"
---
# <a name="options-designers-table-and-database-designers-page"></a><span data-ttu-id="a68b6-102">Optionen (Designer-Tabellen-und Datenbank-Designer-Seite)</span><span class="sxs-lookup"><span data-stu-id="a68b6-102">Options (Designers-Table and Database Designers Page)</span></span>
  <span data-ttu-id="a68b6-103">Auf dieser Seite können Sie das Standardverhalten des Designers bestimmen.</span><span class="sxs-lookup"><span data-stu-id="a68b6-103">Use this page to determine the default behavior of the designer.</span></span> <span data-ttu-id="a68b6-104">Um auf die Einstellungen zuzugreifen, klicken Sie im Menü **Extras** auf **Optionen**, erweitern Sie den Ordner **Designer** , und klicken Sie dann auf **Tabellen-Designer**.</span><span class="sxs-lookup"><span data-stu-id="a68b6-104">To access the settings, on the **Tools** menu, click **Options**, expand the **Designers** folder, and click **Table Designer**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="a68b6-105">Liste der Benutzeroberflächenelemente</span><span class="sxs-lookup"><span data-stu-id="a68b6-105">UI element list</span></span>  
 <span data-ttu-id="a68b6-106">**Timeoutwert für Verbindungszeichenfolge für Tabellen-Designer-Updates überschreiben**</span><span class="sxs-lookup"><span data-stu-id="a68b6-106">**Override connection string time-out value for table designer updates**</span></span>  
 <span data-ttu-id="a68b6-107">Lässt zu, dass für die Aktionen des Tabellen-Designers ein neuer Timeoutwert festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="a68b6-107">Permits a new time-out value to be set for the actions of the table designer.</span></span> <span data-ttu-id="a68b6-108">Das kann hilfreich sein, wenn der Tabellen-Designer Auswirkungen auf eine große Tabelle hat und für die Änderung der Tabelle zusätzliche Zeit benötigt.</span><span class="sxs-lookup"><span data-stu-id="a68b6-108">This can be useful when the table designer affects a large table and requires extra time to complete the table modification.</span></span>  
  
 <span data-ttu-id="a68b6-109">**Transaktionstimeout nach**</span><span class="sxs-lookup"><span data-stu-id="a68b6-109">**Transaction time-out after**</span></span>  
 <span data-ttu-id="a68b6-110">Legt einen Timeoutwert für den Tabellen-Designer fest.</span><span class="sxs-lookup"><span data-stu-id="a68b6-110">Sets a time-out value for the table designer.</span></span>  
  
 <span data-ttu-id="a68b6-111">**Automatisches Erstellen von Änderungsskripts**</span><span class="sxs-lookup"><span data-stu-id="a68b6-111">**Auto generate change scripts**</span></span>  
 <span data-ttu-id="a68b6-112">Erstellt automatisch ein Skript für die Implementierung der im Tabellen-Designer definierten Änderungen.</span><span class="sxs-lookup"><span data-stu-id="a68b6-112">Automatically creates a script to implement the changes defined in the table designer.</span></span>  
  
 <span data-ttu-id="a68b6-113">**Warnung bei Nullprimärschlüsseln**</span><span class="sxs-lookup"><span data-stu-id="a68b6-113">**Warn on null primary keys**</span></span>  
 <span data-ttu-id="a68b6-114">Stellt ein Warndialogfeld bereit, wenn ein für einen Primärschlüssel ausgewähltes Feld Nullwerte enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="a68b6-114">Provides a warning dialog box when a field that is selected for a primary key can contain null values.</span></span>  
  
 <span data-ttu-id="a68b6-115">**Warnung bei Unterschiederkennung**</span><span class="sxs-lookup"><span data-stu-id="a68b6-115">**Warn about difference detection**</span></span>  
 <span data-ttu-id="a68b6-116">Wenn Sie dieses Kontrollkästchen aktivieren, werden beim Speichern der Änderungen in einem Nachrichtenfeld alle Überschneidungen zwischen Ihren Änderungen und den von einem anderen Benutzer vorgenommenen Änderungen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="a68b6-116">If you check this box, when you save the changes, a message box will list any conflicts between your changes and changes that were made by another user.</span></span>  
  
 <span data-ttu-id="a68b6-117">**Warnung bei betroffenen Tabellen**</span><span class="sxs-lookup"><span data-stu-id="a68b6-117">**Warn about tables affected**</span></span>  
 <span data-ttu-id="a68b6-118">Stellt ein Warndialogfeld bereit, in dem die von der Aktion betroffenen Tabellen aufgeführt sind und zur Bestätigung aufgefordert wird.</span><span class="sxs-lookup"><span data-stu-id="a68b6-118">Provides a warning dialog box that lists the tables to be affected by the action and prompts for confirmation.</span></span>  
  
 <span data-ttu-id="a68b6-119">**Speichern von Änderungen verhindern, die die Neuerstellung der Tabelle erfordern**</span><span class="sxs-lookup"><span data-stu-id="a68b6-119">**Prevent saving changes that require table re-creation**</span></span>  
 <span data-ttu-id="a68b6-120">Verhindert, dass ein Benutzer Änderungen vornimmt, die eine Neuerstellung der Tabelle erfordern.</span><span class="sxs-lookup"><span data-stu-id="a68b6-120">Prevents a user from making changes that require re-creating the table.</span></span> <span data-ttu-id="a68b6-121">Die folgenden Aktionen können die erneute Erstellung einer Tabelle erfordern:</span><span class="sxs-lookup"><span data-stu-id="a68b6-121">The following actions might require a table to be re-created:</span></span>  
  
-   <span data-ttu-id="a68b6-122">Hinzufügen einer neuen Spalte zur Mitte der Tabelle</span><span class="sxs-lookup"><span data-stu-id="a68b6-122">Adding a new column to the middle of the table</span></span>  
  
-   <span data-ttu-id="a68b6-123">Löschen einer Spalte</span><span class="sxs-lookup"><span data-stu-id="a68b6-123">Dropping a column</span></span>  
  
-   <span data-ttu-id="a68b6-124">Ändern der NULL-Zulässigkeit einer Spalte</span><span class="sxs-lookup"><span data-stu-id="a68b6-124">Changing column nullability</span></span>  
  
-   <span data-ttu-id="a68b6-125">Ändern der Reihenfolge der Spalten</span><span class="sxs-lookup"><span data-stu-id="a68b6-125">Changing the order of the columns</span></span>  
  
-   <span data-ttu-id="a68b6-126">Ändern des Datentyps einer Spalte</span><span class="sxs-lookup"><span data-stu-id="a68b6-126">Changing the data type of a column</span></span>  
  
 <span data-ttu-id="a68b6-127">**Standardtabellenansicht**</span><span class="sxs-lookup"><span data-stu-id="a68b6-127">**Default table view**</span></span>  
 <span data-ttu-id="a68b6-128">Wählen Sie aus, wie Tabellen in den Designern angezeigt werden sollen:</span><span class="sxs-lookup"><span data-stu-id="a68b6-128">Select the way you want to see tables in the designers:</span></span>  
  
-   <span data-ttu-id="a68b6-129">**Standard**</span><span class="sxs-lookup"><span data-stu-id="a68b6-129">**Standard**</span></span>  
  
     <span data-ttu-id="a68b6-130">Zeigt den Tabellenkopf, alle Spaltennamen, Datentypen und die Einstellung NULL-Werte zulassen an.</span><span class="sxs-lookup"><span data-stu-id="a68b6-130">Shows the table header, all column names, data types, and the Allow Nulls setting.</span></span>  
  
-   <span data-ttu-id="a68b6-131">**Spaltennamen**</span><span class="sxs-lookup"><span data-stu-id="a68b6-131">**Column Names**</span></span>  
  
     <span data-ttu-id="a68b6-132">Zeigt die Spaltennamen an.</span><span class="sxs-lookup"><span data-stu-id="a68b6-132">Shows the column names.</span></span>  
  
-   <span data-ttu-id="a68b6-133">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="a68b6-133">**Key**</span></span>  
  
     <span data-ttu-id="a68b6-134">Zeigt den Tabellenkopf und die Primärschlüsselspalten an.</span><span class="sxs-lookup"><span data-stu-id="a68b6-134">Shows the table header and the primary key columns.</span></span>  
  
-   <span data-ttu-id="a68b6-135">**Nur Name**</span><span class="sxs-lookup"><span data-stu-id="a68b6-135">**Name Only**</span></span>  
  
     <span data-ttu-id="a68b6-136">Zeigt nur den Tabellenkopf mit seinem Namen an.</span><span class="sxs-lookup"><span data-stu-id="a68b6-136">Shows only the table header with it's name.</span></span>  
  
-   <span data-ttu-id="a68b6-137">**Benutzerdefiniert**</span><span class="sxs-lookup"><span data-stu-id="a68b6-137">**Custom**</span></span>  
  
     <span data-ttu-id="a68b6-138">Ermöglicht Ihnen die Auswahl der anzuzeigenden Spalten.</span><span class="sxs-lookup"><span data-stu-id="a68b6-138">Allows you to choose which columns to view.</span></span>  
  
 <span data-ttu-id="a68b6-139">**Tabellendialogfeld hinzufügen bei Neues Diagramm starten**</span><span class="sxs-lookup"><span data-stu-id="a68b6-139">**Launch add table dialog on new diagram**</span></span>  
 <span data-ttu-id="a68b6-140">Öffnet beim Öffnen der Designer automatisch das Dialogfeld **Tabelle hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="a68b6-140">Automatically opens the **Add Table** dialog box when the designers open.</span></span>  
  
  
