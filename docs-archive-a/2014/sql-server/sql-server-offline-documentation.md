---
title: Offline Dokumentation für SQL Server 2014
description: Erfahren Sie, wie Sie die Offline Dokumentation für SQL Server 2014 installieren. Verwenden Sie SQL Server Management Studio (SSMS) zum Anzeigen der Offlineinhalte.
ms.prod: sql
ms.technology: install
ms.topic: conceptual
ms.assetid: 51f8a08c-51d0-41d8-8bc5-1cb4d42622fb
author: markingmyname
ms.author: maghan
ms.reviewer: carlrab
ms.date: 07/19/2020
ms.openlocfilehash: bfd4adc658a203f8e2d22ef77ce0381084e36363
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617372"
---
# <a name="install-sql-server-2014-offline-documentation"></a>Installieren von SQL Server 2014-Offline Dokumentation

In diesem Artikel wird beschrieben, wie Sie den Inhalt von Offline SQL Server 2014 herunterladen und anzeigen. Mithilfe von Offlineinhalten können Sie ohne bestehende Internetverbindung auf die Dokumentation zugreifen (allerdings ist für den Download anfangs eine Internetverbindung erforderlich).

Das Verfahren umfasst die Verwendung des **Hilfe** Menüs von SQL Server Management Studio (SSMS), um auf das Help Viewer-Hilfsprogramm (HlpViewer.exe) zuzugreifen.

Die Offline Dokumentation ist für Versionen von SQL Server im Bereich von 2012-2019 und möglicherweise auch für weitere spätere Versionen verfügbar. Zwar lassen sich [Inhalte für frühere Versionen online](https://docs.microsoft.com/previous-versions/sql/) anzeigen, eine Offlineoption bietet jedoch ein komfortables Zugriffsverfahren für die älteren Inhalte.

- [SQL Server 2014](#sql-server-2014-offline-content)
- [SQL Server 2012](#sql-server-2012-offline-content)

Informationen zu den SQL Server 2016 und höheren Versionen finden Sie in der Versions spezifischen Dokumentation, um zu erfahren, wie diese Versionen Ihre Offline Dokumentation verarbeiten.

## <a name="sql-server-2014-offline-content"></a>Offlineinhalte für SQL Server 2014

> [!IMPORTANT]
> SQL 2014 Transact-SQL-Inhalte sind nur offline verfügbar.

In den folgenden Schritten wird erläutert, wie Offlineinhalte für SQL Server 2014 geladen werden.

1. Laden Sie den Inhalt [Produktdokumentation für Microsoft SQL Server 2014 für firewall- und proxygeschützte Umgebungen](https://www.microsoft.com/download/details.aspx?id=42557) aus dem Downloadcenter herunter, und speichern Sie ihn in einem Ordner.

2. Entzippen Sie die Datei, um die *MSHA* -Datei anzuzeigen.

   ![Setupdatei der SQL Server 2014-Hilfedokumentation](../sql-server/media/sql-server-offline-documentation/sql-2014-help-content-setup-msha.png)

3. Wählen Sie in SSMS im Menü „Hilfe“ **Hilfeinhalt hinzufügen und entfernen** aus.

   ![Hinzufügen und Entfernen von Inhalten in Help Viewer](../sql-server/media/sql-server-offline-documentation/add-remove-content.png)

   Help Viewer öffnet die Registerkarte „Inhalt verwalten“.

4. Wählen Sie unter „Installationsquelle“ **Datenträger**, um die neuesten Hilfeinhalte zu installieren, und anschließend die Auslassungspunkte (...) aus.

   ![Quelle „Datenträger“ in Help Viewer – Inhalte verwalten](../sql-server/media/sql-server-offline-documentation/install-source-disk.png)

   > [!NOTE]
   > Der lokale Speicherpfad auf der Registerkarte „Inhalt verwalten“ zeigt an, wo sich der Inhalt auf dem lokalen Computer befindet. Wenn Sie den Speicherort ändern möchten, wählen Sie **Verschieben** aus, geben Sie einen anderen Ordnerpfad im Feld **Nach** ein, und wählen Sie anschließend **OK** aus.
   Wenn die Installation der Hilfe nach dem Ändern des lokalen Speicherpfads fehlschlägt, müssen Sie Help Viewer schließen und anschließend wieder öffnen. Stellen Sie sicher, dass der neue Speicherort im lokalen Speicherpfad angezeigt wird, und versuchen Sie dann noch mal, die Installation durchzuführen.

5. Navigieren Sie zu dem Ordner, in dem Sie die Inhalte entzippt haben. Wählen Sie die Datei **HelpContentSetup.msha** im Ordner und anschließend **Öffnen** aus.

   ![Öffnen der Datei „SQL Server 2014 Help Content Setup.msha“](../sql-server/media/sql-server-offline-documentation/sql-2014-open-msha.png)

6. Geben Sie in der Suchleiste *sql server 2014* ein. Wenn Sie die verfügbaren 2014-Inhalte sehen, wählen Sie neben jedem einzelnen Inhaltspaket (Buch), das Sie in Help Viewer installieren möchten, **Hinzufügen**, und wählen Sie dann **Aktualisieren** aus.

   ![Suche nach SQL Server 2014-Büchern in Help Viewer](../sql-server/media/sql-server-offline-documentation/sql-2014-search.png)

   ![Hinzufügen und Aktualisieren von SQL Server 2014-Büchern in Help Viewer](../sql-server/media/sql-server-offline-documentation/sql-2014-add-update.png)

    > [!NOTE]
    > Wenn der Help Viewer während des Hinzufügens von Inhalt einfriert (reagiert), ändern Sie die Zeile Cache LastRefreshed = " \<mm/dd/yyyy> 00:00:00" in der Datei "%LocalAppData%\microsoft\helpviewer2.x\ HlpViewer_SSMSx_en-US. Settings" oder "HlpViewer_VisualStudiox_en-US. Settings" in ein Datum in der Zukunft. Weitere Informationen zu diesem Problem finden Sie unter [Visual Studio Help Viewer friert beim Begrüßungsbildschirm ein](/visualstudio/welcome-to-visual-studio).

7. Sie können überprüfen, ob die SQL Server 2014-Inhalte installiert wurden, indem Sie im Inhaltsbereich links nach *sql server 2014* suchen.

   ![Automatische Aktualisierung von SQL Server 2014-Büchern](../sql-server/media/sql-server-offline-documentation/sql-2014-content.png)

## <a name="sql-server-2012-offline-content"></a>Offlineinhalte für SQL Server 2012

In den folgenden Schritten wird erläutert, wie Offlineinhalte für SQL Server 2012 geladen werden.

1. Laden Sie den Inhalt [Produktdokumentation für Microsoft SQL Server 2012 für firewall- und proxygeschützte Umgebungen](https://www.microsoft.com/download/details.aspx?id=35750) aus dem Downloadcenter herunter, und speichern Sie ihn in einem Ordner.

2. Entzippen Sie die Datei, um die *MSHA* -Datei anzuzeigen.

   ![Setupdatei für SQL Server 2012-Hilfeinhalte](../sql-server/media/sql-server-offline-documentation/sql-2012-help-content-setup-msha.png)

3. Wählen Sie in SSMS im Menü „Hilfe“ **Hilfeinhalt hinzufügen und entfernen** aus.

   ![Hinzufügen und Entfernen von Inhalten in Help Viewer](../sql-server/media/sql-server-offline-documentation/add-remove-content.png)

   Help Viewer öffnet die Registerkarte „Inhalt verwalten“.

4. Wählen Sie unter „Installationsquelle“ **Datenträger**, um die neuesten Hilfeinhalte zu installieren, und anschließend die Auslassungspunkte (...) aus.

   ![Quelle „Datenträger“ in Help Viewer – Inhalte verwalten](../sql-server/media/sql-server-offline-documentation/install-source-disk.png)

   > [!NOTE]
   > Der lokale Speicherpfad auf der Registerkarte „Inhalt verwalten“ zeigt an, wo sich der Inhalt auf dem lokalen Computer befindet. Wenn Sie den Speicherort ändern möchten, wählen Sie **Verschieben** aus, geben Sie einen anderen Ordnerpfad im Feld **Nach** ein, und wählen Sie anschließend **OK** aus.
   Wenn die Installation der Hilfe nach dem Ändern des lokalen Speicherpfads fehlschlägt, müssen Sie Help Viewer schließen und anschließend wieder öffnen. Stellen Sie sicher, dass der neue Speicherort im lokalen Speicherpfad angezeigt wird, und versuchen Sie dann noch mal, die Installation durchzuführen.

5. Navigieren Sie zu dem Ordner, in dem Sie die Inhalte entzippt haben. Wählen Sie die Datei **HelpContentSetup.msha** im Ordner und anschließend **Öffnen** aus.

   ![Öffnen der Datei „SQL Server 2012 Help Content Setup.msha“](../sql-server/media/sql-server-offline-documentation/sql-2012-open-msha.png)

6. Geben Sie in der Suchleiste *sql server 2012* ein. Wenn Sie die verfügbaren 2012-Inhalte sehen, wählen Sie neben jedem einzelnen Inhaltspaket (Buch), das Sie in Help Viewer installieren möchten, **Hinzufügen**, und wählen Sie dann **Aktualisieren** aus.

   ![Suche nach SQL Server 2012-Büchern in Help Viewer](../sql-server/media/sql-server-offline-documentation/sql-2012-search.png)

   ![Hinzufügen und Aktualisieren von SQL Server 2012-Büchern in Help Viewer](../sql-server/media/sql-server-offline-documentation/sql-2012-add-update.png)

    > [!NOTE]
    > Wenn der Help Viewer während des Hinzufügens von Inhalt einfriert (reagiert), ändern Sie die Zeile Cache LastRefreshed = " \<mm/dd/yyyy> 00:00:00" in der Datei "%LocalAppData%\microsoft\helpviewer2.x\ HlpViewer_SSMSx_en-US. Settings" oder "HlpViewer_VisualStudiox_en-US. Settings" in ein Datum in der Zukunft. Weitere Informationen zu diesem Problem finden Sie unter [Visual Studio Help Viewer friert beim Begrüßungsbildschirm ein](/visualstudio/welcome-to-visual-studio).

7. Sie können überprüfen, ob die SQL Server 2012-Inhalte geladen wurden, indem Sie im Inhaltsbereich links nach *sql server 2012* suchen.

   ![Automatisch aktualisierte SQL Server 2012-Dokumentation](../sql-server/media/sql-server-offline-documentation/sql-2012-content.png)

## <a name="view-offline-documentation"></a>Anzeigen der Offlinedokumentation

Sie können SQL Server Hilfe Inhalt mithilfe des Menüs **Hilfe** in der aktuellen Version von SQL Server Management Studio (SSMS) anzeigen.

### <a name="view-offline-help-content-in-ssms"></a>Anzeigen von Offline-Hilfeinhalten in SSMS

Um die installierte Hilfe in SSMS anzuzeigen, wählen Sie im Menü „Hilfe“ **In Help Viewer starten** aus, um den Help Viewer zu starten.

   ![In Help Viewer starten](../sql-server/media/sql-server-offline-documentation/helpviewer-view-offline.png)  

Help Viewer öffnet sich auf der Registerkarte „Inhalt verwalten“ mit dem installierten Inhaltsverzeichnis für die Hilfe im linken Bereich. Wählen Sie im Inhaltsverzeichnis Artikel aus, um diese auf der rechten Seite anzuzeigen.

> [!Important]
> Wenn der Inhaltsbereich nicht angezeigt wird, wählen Sie auf der linken Seite „Inhalt“ aus. Wählen Sie das Reißzweckensymbol aus, damit der Inhaltsbereich geöffnet bleibt.  

   ![Help Viewer mit Inhalt](../sql-server/media/sql-server-offline-documentation/view-offline-all.png)
