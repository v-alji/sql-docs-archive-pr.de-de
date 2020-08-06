---
title: Ändern gespeicherter Prozeduren, die nicht mehr unterstützte Eigenschaften der voll Text Suche verwenden Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- discontinued properties [Full-Text Search]
- stored procedures [Full-Text Search]
ms.assetid: 8d9392d9-a9ba-4378-84e4-59f516b67ddb
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 12262a588742f0e3be094e32a2a0208a85b6f28a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617471"
---
# <a name="modify-stored-procedures-that-use-discontinued-full-text-search-properties"></a>Ändern gespeicherter Prozeduren, die nicht mehr unterstützte Volltextsuche-Eigenschaften verwenden
  Um sicherzustellen, dass Ihre gespeicherten Prozeduren korrekt funktionieren, sollten Sie vorhandene Prozeduren bearbeiten und volltextbezogene Eigenschaften und Einstellungen entfernen, die entfernt wurden oder nicht mehr unterstützt werden.  
  
## <a name="component"></a>Komponente  
 Volltextsuche  
  
## <a name="description"></a>BESCHREIBUNG  
 Die folgenden Eigenschaften und Einstellungen der Volltextsuche wurden entfernt.  
  
-   **DataTimeout**  
  
-   **ConnectTimeout**  
  
-   **Clean_up**  
  
-   **LogSize**  
  
 Die folgenden Eigenschaften und Einstellungen der Volltextsuche wurden entfernt bzw. werden nicht mehr unterstützt.  
  
-   'Path' des Volltextkatalogs. Der Volltextkatalog ist ein logisches Objekt ohne einen spezifischen Dateipfad im System.  
  
-   Das Aktivieren/Deaktivieren von SP_FULLTEXT_DATABASE hat keine Wirkung mehr, da Datenbanken in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] jederzeit und standardmäßig für die Volltextsuche aktiviert sind.  
  
## <a name="corrective-action"></a>Korrekturmaßnahme  
 Ändern Sie die gespeicherten Prozeduren, um diese Eigenschaften zu entfernen.  
  
## <a name="see-also"></a>Weitere Informationen  
 [Arbeiten mit dem Upgrade Advisor](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
