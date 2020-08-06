---
title: Anpassen des Verhaltens der Wörtertrennung mit einem Benutzerwörterbuch | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
ms.assetid: a8e278d1-aeaa-48f1-a0c6-5de232c983e4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9fb02a47da20134925d9b2486ea0c08091af4aa6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700988"
---
# <a name="customize-the-behavior-of-word-breakers-with-a-custom-dictionary"></a><span data-ttu-id="09cf5-102">Anpassen des Verhaltens der Wörtertrennung mit einem Benutzerwörterbuch</span><span class="sxs-lookup"><span data-stu-id="09cf5-102">Customize the Behavior of Word Breakers with a Custom Dictionary</span></span>
  <span data-ttu-id="09cf5-103">Sie können das Verhalten der Wörtertrennung für eine bestimmte Sprache anpassen, indem Sie eine sprachspezifische Benutzerwörterbuchdatei erstellen.</span><span class="sxs-lookup"><span data-stu-id="09cf5-103">You can customize the behavior of the word breaker for a particular language by creating a language-specific custom dictionary file.</span></span> <span data-ttu-id="09cf5-104">Sie können z. B. verhindern, dass die Wörtertrennung bestimmte Begriffe oder Muster trennt.</span><span class="sxs-lookup"><span data-stu-id="09cf5-104">For example, you can prevent the word breaker from breaking certain terms or patterns.</span></span>  
  
 <span data-ttu-id="09cf5-105">Weitere Informationen finden Sie im folgenden SharePoint-Artikel:</span><span class="sxs-lookup"><span data-stu-id="09cf5-105">For more information, see the following SharePoint article:</span></span>  
  
 [<span data-ttu-id="09cf5-106">Erstellen eines Benutzerwörterbuchs (SharePoint Server 2010)</span><span class="sxs-lookup"><span data-stu-id="09cf5-106">Create a custom dictionary (SharePoint Server 2010)</span></span>](https://go.microsoft.com/fwlink/?LinkId=215011)  
  
 <span data-ttu-id="09cf5-107">Speichern Sie Benutzerwörterbuchdateien für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]in dem folgenden Ordner:</span><span class="sxs-lookup"><span data-stu-id="09cf5-107">For [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], place custom dictionary files in the following folder:</span></span>  
  
 `C:\Program Files\Microsoft SQL Server\<instance name>\MSSQL\Binn`  
  
 <span data-ttu-id="09cf5-108">Starten Sie nach dem Erstellen oder Ändern von Benutzerwörterbuchdateien das Startprogramm für den SQL-Volltextfilterdaemon mit dem folgenden Befehl neu:</span><span class="sxs-lookup"><span data-stu-id="09cf5-108">After creating or changing custom dictionary files, restart the SQL Full-text Daemon Launcher with the following command:</span></span>  
  
 `exec sp_fulltext_service 'restart_all_fdhosts'`  
  
  
