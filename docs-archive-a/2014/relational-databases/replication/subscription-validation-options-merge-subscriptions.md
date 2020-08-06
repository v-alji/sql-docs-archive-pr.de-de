---
title: Optionen für die Abonnementüberprüfung (Mergeabonnements) | Microsoft Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.validate.mergeoptions.f1
helpviewer_keywords:
- Subscription Validation Options dialog box
ms.assetid: 4958c4ab-2025-42ce-b836-6fb4e9e6f24d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 458da0387dbaa1b366348c374748c42946893feb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725438"
---
# <a name="subscription-validation-options-merge-subscriptions"></a><span data-ttu-id="7b5aa-102">Optionen für die Abonnementüberprüfung (Mergeabonnements)</span><span class="sxs-lookup"><span data-stu-id="7b5aa-102">Subscription Validation Options (Merge Subscriptions)</span></span>
  <span data-ttu-id="7b5aa-103">Mithilfe des Dialogfelds **Optionen für die Abonnementüberprüfung** können Sie angeben, ob zur Überprüfung nur die Zeilenanzahl oder die Zeilenanzahl und eine binäre Prüfsumme verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7b5aa-103">Use the **Subscription Validation Options** dialog box to specify whether validation should use a row count only or a row count and a binary checksum.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7b5aa-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="7b5aa-104">Options</span></span>  
 <span data-ttu-id="7b5aa-105">**Nur Zeilenanzahl überprüfen**</span><span class="sxs-lookup"><span data-stu-id="7b5aa-105">**Verify the row counts only**</span></span>  
 <span data-ttu-id="7b5aa-106">Wählen Sie diese Option aus, um zu überprüfen, ob die Anzahl der Zeilen in der Tabelle auf dem Abonnenten mit der Anzahl der Zeilen in der Tabelle auf dem Verleger übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="7b5aa-106">Select to validate whether the table at the Subscriber has the same number of rows as the table at the Publisher.</span></span> <span data-ttu-id="7b5aa-107">Mit dieser Methode wird nicht überprüft, ob die Inhalte der Zeilen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="7b5aa-107">This method does not validate that the content of the rows matches.</span></span> <span data-ttu-id="7b5aa-108">Die Überprüfung der Zeilenanzahl bietet einen Überprüfungsansatz, der kaum Ressourcen beansprucht und Sie Probleme bei den Daten erkennen lässt.</span><span class="sxs-lookup"><span data-stu-id="7b5aa-108">Row count validation provides a lightweight approach to validation that can make you aware of issues with your data.</span></span>  
  
 <span data-ttu-id="7b5aa-109">**Die Zeilenanzahl überprüfen und Prüfsummen vergleichen, um die Zeilendaten zu überprüfen**</span><span class="sxs-lookup"><span data-stu-id="7b5aa-109">**Verify the row counts and compare checksums to verify the row data**</span></span>  
 <span data-ttu-id="7b5aa-110">Zusätzlich zum Einbinden einer Reihe von Zeilen auf Verleger- und Abonnentenebene wird eine Prüfsumme aller Daten mit dem binären Prüfsummenalgorithmus berechnet.</span><span class="sxs-lookup"><span data-stu-id="7b5aa-110">In addition to taking a count of rows at the Publisher and Subscriber, a checksum of all the data is calculated using the binary checksum algorithm.</span></span> <span data-ttu-id="7b5aa-111">Ist die Zeilenanzahl fehlerhaft, wird die Berechnung der Prüfsumme nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7b5aa-111">If the row count fails, the checksum is not performed.</span></span> <span data-ttu-id="7b5aa-112">Diese Option ist für ungültig [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssEW](../../includes/ssew-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7b5aa-112">This option is not valid for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b5aa-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7b5aa-113">See Also</span></span>  
 <span data-ttu-id="7b5aa-114">[Überprüfen von Daten auf dem Abonnenten](validate-data-at-the-subscriber.md) </span><span class="sxs-lookup"><span data-stu-id="7b5aa-114">[Validate Data at the Subscriber](validate-data-at-the-subscriber.md) </span></span>  
 [<span data-ttu-id="7b5aa-115">Überprüfen von replizierten Daten</span><span class="sxs-lookup"><span data-stu-id="7b5aa-115">Validate Replicated Data</span></span>](validate-data-at-the-subscriber.md)  
  
  
