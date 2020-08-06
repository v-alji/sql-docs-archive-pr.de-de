---
title: Richtlinien und Einschränkungen von SQLXML 4,0 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXML, about SQLXML
ms.assetid: fe433d30-90a1-421e-85c6-af13294dc18d
author: rothja
ms.author: jroth
ms.openlocfilehash: e020cbf0ac32e4c878b0b74b67e7c9c679d5d178
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607615"
---
# <a name="guidelines-and-limitations-of-sqlxml-40"></a><span data-ttu-id="fc839-102">Richtlinien und Einschränkungen von SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="fc839-102">Guidelines and Limitations of SQLXML 4.0</span></span>
  <span data-ttu-id="fc839-103">Bei der Arbeit mit SQLXML 4.0 gilt Folgendes:</span><span class="sxs-lookup"><span data-stu-id="fc839-103">Remember the following when working with SQLXML 4.0:</span></span>  
  
-   <span data-ttu-id="fc839-104">Das als Abfrageergebnis zurückgegebene XML wird nicht anhand des Zuordnungsschemas, das das XML erstellt hat, überprüft.</span><span class="sxs-lookup"><span data-stu-id="fc839-104">XML returned as a query result is not validated against the mapping schema that generated the XML.</span></span>  
  
-   <span data-ttu-id="fc839-105">SQLXML 4.0 umfasst versionsunabhängige und versionsabhängige Programm-IDs.</span><span class="sxs-lookup"><span data-stu-id="fc839-105">SQLXML 4.0 includes version-independent and version-dependent PROGIDs.</span></span> <span data-ttu-id="fc839-106">Es wird empfohlen, dass alle Produktionsanwendungen versionsabhängige Programm-IDs verwenden.</span><span class="sxs-lookup"><span data-stu-id="fc839-106">It is recommended that all production applications use version-dependent PROGIDs.</span></span> <span data-ttu-id="fc839-107">Dies ist besonders wichtig, da SQLXML 4.0 nicht vollständig abwärtskompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="fc839-107">This is especially important because SQLXML 4.0 is not fully backward compatible.</span></span> <span data-ttu-id="fc839-108">Die Verwendung von versionsabhängige Programm-IDs schützt vor möglichen Produktionsfehlern beim Installieren neuerer Versionen.</span><span class="sxs-lookup"><span data-stu-id="fc839-108">Using version dependent PROGIDs protects from possible production failures when you install newer releases.</span></span> <span data-ttu-id="fc839-109">Mit jeder neuen Version kann sich das Programmverhalten aus verschiedenen Gründen, z. B. aufgrund von Fehlerbehebungen, möglichen Designänderungen usw. ändern.</span><span class="sxs-lookup"><span data-stu-id="fc839-109">From release to release, program behavior may change for a variety of reasons, such as bug fixes, possible design changes, and so on.</span></span> <span data-ttu-id="fc839-110">Die Verwendung von versionsabhängigen Programm-IDs schützt vor unerwarteten Fehlern beim Installieren neuerer Versionen.</span><span class="sxs-lookup"><span data-stu-id="fc839-110">Using version-dependent PROGIDs protects from unexpected failure when you install newer releases.</span></span> <span data-ttu-id="fc839-111">Wenn Sie eine neuere Version installieren, arbeitet die Anwendung bei versionsabhängigen Programm-IDs weiterhin fehlerfrei.</span><span class="sxs-lookup"><span data-stu-id="fc839-111">With version-dependent PROGIDs, when you install a newer release, your application will continue to work without failure.</span></span> <span data-ttu-id="fc839-112">Wenn Sie die vorherigen versionsabhängigen Programm-IDs ändern und die aktuelle versionsabhängigen Programm-IDs in einer neueren Version verwenden, müssen Sie die Anwendung erst testen, bevor Sie die Arbeit damit aufnehmen.</span><span class="sxs-lookup"><span data-stu-id="fc839-112">If you decide to change the previous version-dependent PROGIDs and use the recent version-dependent PROGIDs in a newer release, you must test your application before putting it into production.</span></span> <span data-ttu-id="fc839-113">Anwendungen mit versionsunabhängigen Programm-IDs schlagen beispielsweise möglicherweise im folgenden Szenario fehl:</span><span class="sxs-lookup"><span data-stu-id="fc839-113">For example, applications using version-independent PROGIDs may fail in the following scenario:</span></span>  
  
     <span data-ttu-id="fc839-114">Sie führen eine Anwendung aus, die SQLXML 4.0 und versionsunabhängige Programm-IDs verwendet, und Sie installieren einige andere Softwareprogramme.</span><span class="sxs-lookup"><span data-stu-id="fc839-114">You are running an application that uses SQLXML 4.0 and version-independent PROGIDs, and you decide to install some other software program.</span></span> <span data-ttu-id="fc839-115">Dabei könnte mit diesem Programm eine frühere Version von SQLXML installiert werden.</span><span class="sxs-lookup"><span data-stu-id="fc839-115">This program might install an earlier version of SQLXML.</span></span> <span data-ttu-id="fc839-116">Ihre Anwendung schlägt fehl, da die versionsunabhängigen Programm-IDs in der Anwendung nun auf die frühere Version von SQLXML verweisen, die nur bedingt über das SQLXML-Funktion verfügen, das Ihre Anwendung verwendet.</span><span class="sxs-lookup"><span data-stu-id="fc839-116">Your application may fail because the version-independent PROGIDS in your application now point to the earlier version of SQLXML, which may or may not have the SQLXML feature that your application is using.</span></span>  
  
-   <span data-ttu-id="fc839-117">Wenn Sie aus irgendeinem Grund den SQLXMLOLEDB-Anbieter nicht verwenden möchten und stattdessen den SQLOLEDB-Anbieter für SQLXML-Funktionen verwenden möchten, legen Sie die **SQLXML-Version** -Eigenschaft auf "SQLXML. 4.0" fest.</span><span class="sxs-lookup"><span data-stu-id="fc839-117">If for any reason you don't want to use the SQLXMLOLEDB provider, and instead want to use the SQLOLEDB provider for SQLXML features, set the **SQLXML Version** property to "SQLXML.4.0".</span></span>  
  
  
