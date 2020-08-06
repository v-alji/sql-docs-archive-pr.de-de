---
title: Aktualisieren von Berichten mithilfe von Klassen, die aus dem RDL-Schema generiert wurden (SSRS-Tutorial) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- RDL [Reporting Services], generating
- RDL [Reporting Services], tutorials
- RDL [Reporting Services], serializing
ms.assetid: 8f81d48f-7ab9-4ef8-bce0-7d16d9a47fbd
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: f3972b8e1af6d50ccc6f5188c8f671fe333ebce8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609565"
---
# <a name="updating-reports-using-classes-generated-from-the-rdl-schema-ssrs-tutorial"></a>Aktualisieren von Berichten mithilfe von Klassen, die aus dem RDL-Schema generiert wurden (SSRS-Lernprogramm)
  In diesem Tutorial wird veranschaulicht, wie Sie mit dem XML Schema Definition-Tool (Xsd.exe) Klassen generieren, mit denen Sie Berichts Definitions Dateien (RDL-und RDLC-Dateien) mit der-Klasse serialisieren und deserialisieren können [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] <xref:System.Xml.Serialization.XmlSerializer> .  
  
## <a name="what-you-will-learn"></a>Lernziele  
 Im Rahmen dieses Lernprogramms führen Sie folgende Aufgaben aus:  
  
-   Erstellen Sie eine Anwendung mithilfe der [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Projektvorlage Konsolenanwendung.  
  
-   Generieren von Klassen aus dem RDL-Schema (Report Definition Language) mit dem **XSD** -Tool.  
  
-   Sie stellen eine Verbindung mit einem Berichtsserver her und rufen eine Berichtsdefinition ab.  
  
-   Sie schreiben Code zum Aktualisieren der Berichtsdefinitionsdatei.  
  
-   Sie speichern die aktualisierte Berichtsdefinition wieder auf dem Berichtsserver.  
  
-   Sie führen die RDL-Schema-Anwendung (VB/C#) aus.  
  
> [!NOTE]  
>  Bei Berichten ohne Beschreibung verursachen die in diesem Lernprogramm bereitgestellten Codebeispiele u. U. einen Fehler. Dies liegt daran, dass für Berichte, für die keine Beschreibung angegeben wurde, keine Beschreibungseigenschaft vorhanden ist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 Für die vollständige Bearbeitung des Lernprogramms benötigen Sie Folgendes:  
  
-   [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].  
  
-   [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)].  
  
-   Ausreichende Berechtigungen für den Zugriff auf Berichte sowie zum Veröffentlichen von Berichten für den Berichtsserver-Webdienst auf dem Computer, auf dem sich der Berichtsserver befindet.  
  
-   Eine Installation der [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)]-Beispieldatenbank auf einer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]-Instanz.  
  
-   Einen auf Ihrem Berichtsserver installierten Bericht. Für dieses Lernprogramm wird der Beispielbericht Company Sales 2012 verwendet. Weitere Informationen zu Beispiel Berichten finden Sie unter [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).  
  
> [!NOTE]  
>  Die Beispiele werden nicht automatisch beim Setup installiert. Sie können sie jedoch jederzeit installieren. Weitere Informationen zu Beispielen finden Sie unter [SQL Server Product Samples](https://go.microsoft.com/fwlink/?LinkId=182887).  
  
 **Geschätzte Zeit bis zum Abschluss des Tutorials:** 30 Minuten  
  
## <a name="tasks"></a>Aufgaben  
 [Lektion 1: Erstellen des RDL-Schemaprojekts in Visual Studio](../../2014/tutorials/lesson-1-create-the-rdl-schema-visual-studio-project.md)  
  
 [Lektion 2: Generieren von Klassen aus dem RDL-Schema mithilfe des XSD-Tools](../../2014/tutorials/lesson-2-generate-classes-from-the-rdl-schema-using-the-xsd-tool.md)  
  
 [Lektion 3: Laden einer Berichtsdefinition vom Berichtsserver](../../2014/tutorials/lesson-3-load-a-report-definition-from-the-report-server.md)  
  
 [Lektion 4: Programmgesteuertes Update der Berichtsdefinition](../../2014/tutorials/lesson-4-update-the-report-definition-programmatically.md)  
  
 [Lektion 5: Veröffentlichen der Berichtsdefinition auf dem Berichtsserver](../../2014/tutorials/lesson-5-publish-the-report-definition-to-the-report-server.md)  
  
 [Lektion 6: Ausführen der RDL-Schema Anwendung &#40;VB-C&#35;&#41;](../../2014/tutorials/lesson-6-run-the-rdl-schema-application-vb-csharp.md)  
  
## <a name="see-also"></a>Weitere Informationen  
 [Berichtsdefinitionssprache (SSRS)](../reporting-services/reports/report-definition-language-ssrs.md)  
  
  
