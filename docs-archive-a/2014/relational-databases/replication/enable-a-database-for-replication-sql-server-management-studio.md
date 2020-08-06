---
title: Aktivieren einer Datenbank für die Replikation (SQL Server Management Studio) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- databases [SQL Server replication]
ms.assetid: 8092faa3-9cff-4f81-926c-6a0070d1ce2c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 307d52e24187e35c1c30f609facd13bfad569216
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609110"
---
# <a name="enable-a-database-for-replication-sql-server-management-studio"></a>Aktivieren einer Datenbank für die Replikation (SQL Server Management Studio)
  Eine Datenbank wird implizit für die Replikation aktiviert, wenn ein Mitglied der festen Serverrolle **sysadmin** mit dem Assistenten für neue Veröffentlichung eine Veröffentlichung erstellt. Ein Mitglied der festen Serverrolle **sysadmin** kann eine Datenbank auch explizit für die Replikation aktivieren, sodass ein Mitglied der festen Datenbankrolle **db_owner** eine oder mehrere Veröffentlichungen in der Datenbank erstellen kann. Verwenden Sie zum expliziten Aktivieren einer Datenbank die Seite **Veröffentlichungsdatenbanken** im Dialogfeld **Verlegereigenschaften - \<Publisher>** . Weitere Informationen zum Zugreifen auf dieses Dialogfeld finden Sie unter [Create a Publication](publish/create-a-publication.md).  
  
### <a name="to-enable-a-database-for-replication"></a>So aktivieren Sie eine Datenbank für die Replikation  
  
1.  Aktivieren Sie auf der Seite **Veröffentlichungsdatenbanken** im Dialogfeld **Verlegereigenschaften - \<Publisher>** das Kontrollkästchen **Transaktionsreplikation** und/oder **Mergereplikation** für jede Datenbank, die Sie replizieren möchten. Aktivieren Sie **Transaktionsreplikation** , um die Datenbank für die Momentaufnahmereplikation zu aktivieren.  
  
2.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
  
