---
title: Optionen für die Abonnementüberprüfung (Transaktionsabonnements) | Microsoft Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.validate.options.f1
helpviewer_keywords:
- Subscription Validation Options dialog box
ms.assetid: fd66ad1f-df01-4240-9e89-8f41bff12c1e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 40a617dd1beff24f8f072f5d139bec7c1ca65f33
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725434"
---
# <a name="subscription-validation-options-transactional-subscriptions"></a><span data-ttu-id="5ba74-102">Optionen für die Abonnementüberprüfung (Transaktionsabonnements)</span><span class="sxs-lookup"><span data-stu-id="5ba74-102">Subscription Validation Options (Transactional Subscriptions)</span></span>
  <span data-ttu-id="5ba74-103">Verwenden Sie das Dialogfeld Optionen für die **Abonnement** Überprüfung, um anzugeben, ob die Überprüfung nur die Zeilen Anzahl oder eine Zeilen Anzahl und eine binäre Prüfsumme verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="5ba74-103">Use the **Subscription Validation Options** dialog box to specify whether validation should use a row count only, or a row count and a binary checksum.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5ba74-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="5ba74-104">Options</span></span>  
 <span data-ttu-id="5ba74-105">**Überprüfen Sie, ob der Abonnent die gleiche Anzahl von Zeilen mit replizierten Daten enthält wie der Verleger**</span><span class="sxs-lookup"><span data-stu-id="5ba74-105">**Verify that the Subscriber has the same number of rows of replicated data as the Publisher**</span></span>  
 <span data-ttu-id="5ba74-106">Wählen Sie den Typ der Zeilenanzahlüberprüfung aus, die ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5ba74-106">Select the type of row count validation to perform.</span></span> <span data-ttu-id="5ba74-107">Bei Oracle-Veröffentlichungen ist die einzig verfügbare Option **Tatsächliche Zeilenanzahl durch direktes Abfragen der Tabellen berechnen**.</span><span class="sxs-lookup"><span data-stu-id="5ba74-107">For Oracle publications, the only available option is **Compute an actual row count by querying the tables directly**.</span></span>  
  
 <span data-ttu-id="5ba74-108">**Prüfsummen vergleichen, um die Zeilendaten zu überprüfen**</span><span class="sxs-lookup"><span data-stu-id="5ba74-108">**Compare checksums to verify row data**</span></span>  
 <span data-ttu-id="5ba74-109">Zusätzlich zum Einbinden einer Reihe von Zeilen auf Verleger- und Abonnentenebene wird eine Prüfsumme aller Daten mit dem binären Prüfsummenalgorithmus berechnet.</span><span class="sxs-lookup"><span data-stu-id="5ba74-109">In addition to taking a count of rows at the Publisher and Subscriber, a checksum of all the data is calculated using the binary checksum algorithm.</span></span> <span data-ttu-id="5ba74-110">Ist die Zeilenanzahl fehlerhaft, wird die Berechnung der Prüfsumme nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5ba74-110">If the row count fails, the checksum is not performed.</span></span>  
  
 <span data-ttu-id="5ba74-111">**Verteilungs-Agent nach Abschluss der Überprüfung beenden**</span><span class="sxs-lookup"><span data-stu-id="5ba74-111">**Stop the Distribution Agent after the validation has completed**</span></span>  
 <span data-ttu-id="5ba74-112">Standardmäßig wird der Verteilungs-Agent ununterbrochen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5ba74-112">By default, the Distribution Agent runs continuously.</span></span> <span data-ttu-id="5ba74-113">Wählen Sie diese Option aus, um den Agent nach dem Ausführen der Überprüfung zu beenden.</span><span class="sxs-lookup"><span data-stu-id="5ba74-113">Select this option to stop the agent after validation is performed.</span></span> <span data-ttu-id="5ba74-114">Dadurch können Sie prüfen, ob die Überprüfung erfolgreich verlaufen ist, bevor die Replikation der Daten an den Abonnenten fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="5ba74-114">This allows you to check whether validation was successful before continuing to replicate data to the Subscriber.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ba74-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5ba74-115">See Also</span></span>  
 <span data-ttu-id="5ba74-116">[Überprüfen von Daten auf dem Abonnenten](validate-data-at-the-subscriber.md) </span><span class="sxs-lookup"><span data-stu-id="5ba74-116">[Validate Data at the Subscriber](validate-data-at-the-subscriber.md) </span></span>  
 [<span data-ttu-id="5ba74-117">Überprüfen von replizierten Daten</span><span class="sxs-lookup"><span data-stu-id="5ba74-117">Validate Replicated Data</span></span>](validate-data-at-the-subscriber.md)  
  
  
