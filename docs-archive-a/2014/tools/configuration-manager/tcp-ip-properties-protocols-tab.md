---
title: TCP/IP-Eigenschaften (Registerkarte Protokolle) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- TCP/IP [SQL Server], configuration options
ms.assetid: 007638fc-3a24-4460-adbe-545ded5d6f88
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1d5bc28faddae9a86a6636b56b907b57a2d8711a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608996"
---
# <a name="tcp---ip-properties-protocols-tab"></a>TCP/IP-Eigenschaften (Registerkarte Protokolle)
  Verwenden Sie das Dialogfeld **TCP/IP-Eigenschaften** zum Konfigurieren der Optionen für das TCP/IP-Protokoll. Klicken Sie im linken Bereich auf **TCP/IP** , um die einzelnen IP-Adresskonfigurationen im Detailbereich anzuzeigen.  
  
 Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] muss neu gestartet werden, damit die Änderungen in Kraft treten.  
  
## <a name="options"></a>Tastatur  
 **Aktiviert**  
 Mögliche Werte sind **Yes** und **No**.  
  
 **Keep Alive**  
 Geben Sie das Intervall (in Millisekunden) an, in dem Erhaltungspakete übertragen werden, die die Verfügbarkeit des Computers an der Remoteseite der Verbindung sicherstellen.  
  
 **Listen All**  
 Specify whether SQL Server will listen on all the IP addresses that are bound to network cards on the computer. Wenn für diese Option **Nein**festgelegt ist, müssen Sie jede IP-Adresse einzeln mithilfe des Dialogfeldes „Eigenschaften“ für jede IP-Adresse konfigurieren. Wenn für diese Option **Ja**festgelegt ist, gelten die Einstellungen des Eigenschaftenfeldes **IPAll** für alle IP-Adressen. Der Standardwert ist **Ja**.  
  
 **No Delay**  
 Von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] werden keine Änderungen an dieser Eigenschaft implementiert.  
  
## <a name="see-also"></a>Weitere Informationen  
 [Auswählen eines Netzwerkprotokolls](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md)   
 [Erstellen einer gültigen Verbindungszeichenfolge mithilfe von TCP/IP](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md)  
  
  
