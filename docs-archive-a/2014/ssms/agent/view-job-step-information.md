---
title: Anzeigen von Auftragsschrittinformationen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- displaying job step information
- jobs [SQL Server Agent], viewing
- SQL Server Agent jobs, viewing
- viewing job step information
ms.assetid: e3f06492-dc86-4e06-b186-ea58aff6d591
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5d9fc6a006884bc564b5db2bfa8b168c8ae59149
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607535"
---
# <a name="view-job-step-information"></a>View Job Step Information
  In diesem Thema wird beschrieben, wie Sie die Auftragsschrittdetails im Auftragsschritt-Eigenschaftendialogfeld anzeigen. Es enthält auch Informationen zum Anzeigen der Auftragsschrittausgabe.  
  
-   **Vorbereitungen:**  
  
     [Einschränkungen](#Restrictions)  
  
     [Security](#Security)  
  
-   **So zeigen Sie Auftragsschrittinformationen an mit**  
  
     [SQL Server Management Studio](#SSMS)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> Vorbereitungen  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> Einschränkungen  
 Wenn der Auftragsschritt so konfiguriert wurde, dass seine Ausgabe in eine Tabelle oder Datei geschrieben wird, und der Auftrag wurde mindestens einmal ausgeführt, können Sie die Ausgabe auf der Seite **Erweitert** des Dialogfelds **Auftragsschritt-Eigenschaften** anzeigen. Beim Löschen eines Auftrags oder Auftragsschritts wird das Ausgabeprotokoll automatisch gelöscht.  
  
###  <a name="security"></a><a name="Security"></a> Sicherheit  
  
####  <a name="permissions"></a><a name="Permissions"></a> Berechtigungen  
 Sie können nur die Aufträge anzeigen, die Sie besitzen, es sei denn, Sie sind ein Mitglied der festen Serverrolle **sysadmin** . Mitglieder dieser Rolle können alle Aufträge und Auftragsschrittdetails anzeigen.  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> Verwenden von SQL Server Management Studio  
  
#### <a name="to-view-job-step-information"></a>So zeigen Sie Auftragsschrittinformationen an  
  
1.  Stellen Sie in **Objekt-Explorer** eine Verbindung mit einer Instanz von her [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , und erweitern Sie dann diese Instanz.  
  
2.  Erweitern Sie **SQL Server-Agent**, erweitern Sie **Aufträge**, klicken Sie mit der rechten Maustaste auf den Auftrag, dessen Auftragsschritte Sie anzeigen möchten, und klicken Sie dann auf **Eigenschaften**.  
  
3.  Wählen Sie im Dialogfeld **Auftragseigenschaften** die Seite **Schritte** aus.  
  
4.  Klicken Sie auf den anzuzeigenden Auftragsschritt, und klicken Sie auf **Bearbeiten**.  
  
5.  Sie können auf der Seite **Allgemein** des Dialogfelds **Auftragsschritt-Eigenschaften** den Typ des Auftragsschritts anzeigen und welche Aktion er ausführt.  
  
6.  Klicken Sie auf die Seite **Erweitert** , um die Aktionen des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents anzuzeigen wenn der Auftragsschritt erfolgreich ausgeführt wird oder einen Fehler erzeugt, wie oft der Auftragsschritt wiederholt werden sollte, wohin die Auftragsschrittausgabe geschrieben wird und welcher Benutzer den Auftragsschritt ausführt.  
  
#### <a name="to-view-job-step-output"></a>So zeigen Sie die Auftragsschrittausgabe an  
  
1.  Klicken Sie im Dialogfeld **Auftragsschritt-Eigenschaften** auf die Seite **Erweitert** .  
  
2.  Abhängig von der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Version, mit der Sie verbunden sind, können Sie entweder die Auftragsschritt-Ausgabedatei oder die Auftragsschritt-Ausgabetabelle wie folgt anzeigen:  
  
    -   Wenn Sie mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] oder einer höheren Version verbunden sind, können Sie nur dann auf **Anzeigen** klicken, wenn **In Tabelle protokollieren** aktiviert ist. In diesem Fall wird die Auftragsschrittausgabe in die **sysjobstepslogs** -Tabelle der **msdb** -Datenbank geschrieben.  
  
    -   Die Schaltfläche **Anzeigen** ist deaktiviert, wenn die Auftragsschrittausgabe in eine Datei geschrieben wird. Verwenden Sie den Editor zum Anzeigen der Auftragsschritt-Ausgabedatei.  
  
  
