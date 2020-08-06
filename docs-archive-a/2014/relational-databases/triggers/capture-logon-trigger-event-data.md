---
title: Erfassen von Ereignisdaten für Logon-Trigger | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: e05b1ab4-c10b-402a-9591-f6ec1e3db8c0
author: rothja
ms.author: jroth
ms.openlocfilehash: b11323702d7468d07783b4d1c763dba691479d9c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621950"
---
# <a name="capture-logon-trigger-event-data"></a><span data-ttu-id="7ea03-102">Erfassen von Ereignisdaten für Logon-Trigger</span><span class="sxs-lookup"><span data-stu-id="7ea03-102">Capture Logon Trigger Event Data</span></span>
  <span data-ttu-id="7ea03-103">Wenn Sie XML-Daten zu LOGON-Ereignissen für die Verwendung in Logon-Triggern erfassen möchten, verwenden Sie die [EVENTDATA](/sql/t-sql/functions/eventdata-transact-sql) -Funktion.</span><span class="sxs-lookup"><span data-stu-id="7ea03-103">To capture XML data about LOGON events for use inside logon triggers, use the [EVENTDATA](/sql/t-sql/functions/eventdata-transact-sql) function.</span></span> <span data-ttu-id="7ea03-104">Mit dem LOGON-Ereignis wird das folgende Ereignisdatenschema zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="7ea03-104">The LOGON event returns the following event data schema:</span></span>  
  
 `<EVENT_INSTANCE>`  
  
 `<EventType>event_type</EventType>`  
  
 `<PostTime>post_time</PostTime>`  
  
 `<SPID>spid</SPID>`  
  
 `<ServerName>server_name</ServerName>`  
  
 `<LoginName>login_name</LoginName>`  
  
 `<LoginType>login_type</LoginType>`  
  
 `<SID>sid</SID>`  
  
 `<ClientHost>client_host</ClientHost>`  
  
 `<IsPooled>is_pooled</IsPooled>`  
  
 `</EVENT_INSTANCE>`  
  
 `<EventType>`  
 <span data-ttu-id="7ea03-105">Enthält `LOGON`.</span><span class="sxs-lookup"><span data-stu-id="7ea03-105">Contains `LOGON`.</span></span>  
  
 `<PostTime>`  
 <span data-ttu-id="7ea03-106">Enthält die Uhrzeit, zu der eine Anforderung zum Erstellen einer Sitzung ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="7ea03-106">Contains the time when a session is requested to be established.</span></span>  
  
 `<SID>`  
 <span data-ttu-id="7ea03-107">Enthält den base64-verschlüsselten binären Datenstrom der Sicherheits-ID (SID) für den angegebenen Anmeldenamen.</span><span class="sxs-lookup"><span data-stu-id="7ea03-107">Contains the base 64-encoded binary stream of the security identification number (SID) for the specified login name.</span></span>  
  
 `<ClientHost>`  
 <span data-ttu-id="7ea03-108">Enthält den Hostnamen des Clients, von dem aus die Verbindung hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="7ea03-108">Contains the host name of the client from where the connection is made.</span></span> <span data-ttu-id="7ea03-109">Der Wert lautet '`<local_machine>`', wenn der Name des Clients und des Servers identisch sind.</span><span class="sxs-lookup"><span data-stu-id="7ea03-109">The value is '`<local_machine>`' if the client and server name are the same.</span></span> <span data-ttu-id="7ea03-110">Andernfalls entspricht der Wert der IP-Adresse des Clients.</span><span class="sxs-lookup"><span data-stu-id="7ea03-110">Otherwise, the value is the IP address of the client.</span></span>  
  
 `<IsPooled>`  
 <span data-ttu-id="7ea03-111">Lautet `1` , wenn die Verbindung durch Verbindungspooling wiederverwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7ea03-111">Is `1` if the connection is reused by using connection pooling.</span></span> <span data-ttu-id="7ea03-112">Andernfalls lautet der Wert `0`.</span><span class="sxs-lookup"><span data-stu-id="7ea03-112">Otherwise, the value is `0`.</span></span>  
  
  
