---
title: Zielserver (Registerkarte „Zielserverstatus“) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.target.status.f1
ms.assetid: 010a4cab-d878-4889-8ac8-7d91db6345d6
author: stevestein
ms.author: sstein
ms.openlocfilehash: be51648a4642d25c59e52be65e43037844ec0909
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699159"
---
# <a name="target-servers-target-server-status-tab"></a><span data-ttu-id="e9a45-102">Zielserver (Registerkarte Zielserverstatus)</span><span class="sxs-lookup"><span data-stu-id="e9a45-102">Target Servers (Target Server Status Tab)</span></span>
  <span data-ttu-id="e9a45-103">Mithilfe dieser Seite können Sie den Status der Zielserver für diesen Masterserver anzeigen.</span><span class="sxs-lookup"><span data-stu-id="e9a45-103">Use this page to view the status of the target servers for this master server.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e9a45-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="e9a45-104">Options</span></span>  
 <span data-ttu-id="e9a45-105">**Ziel Server**</span><span class="sxs-lookup"><span data-stu-id="e9a45-105">**Target Server**</span></span>  
 <span data-ttu-id="e9a45-106">Zeigt den Namen des Zielservers an.</span><span class="sxs-lookup"><span data-stu-id="e9a45-106">View the name of the target server.</span></span>  
  
 <span data-ttu-id="e9a45-107">**Ortszeit**</span><span class="sxs-lookup"><span data-stu-id="e9a45-107">**Local time**</span></span>  
 <span data-ttu-id="e9a45-108">Zeigt Datum und Uhrzeit des Zielservers in der Ortszeit des Servers an.</span><span class="sxs-lookup"><span data-stu-id="e9a45-108">View the date and time of the target server in the local time zone for that server.</span></span>  
  
 <span data-ttu-id="e9a45-109">**Zuletzt abgerufen**</span><span class="sxs-lookup"><span data-stu-id="e9a45-109">**Last polled**</span></span>  
 <span data-ttu-id="e9a45-110">Zeigt Datum und Uhrzeit (Ortszeit) des letzten Abrufs des Zielservers beim Masterserver an.</span><span class="sxs-lookup"><span data-stu-id="e9a45-110">View the local date and time that the target server last polled the master.</span></span>  
  
 <span data-ttu-id="e9a45-111">**Ungelesene Anweisungen**</span><span class="sxs-lookup"><span data-stu-id="e9a45-111">**Unread instructions**</span></span>  
 <span data-ttu-id="e9a45-112">Zeigt die Anzahl der Anweisungen an, die der Zielserver noch nicht empfangen hat.</span><span class="sxs-lookup"><span data-stu-id="e9a45-112">View the number of instructions that the target server has not yet received.</span></span>  
  
 <span data-ttu-id="e9a45-113">**Status**</span><span class="sxs-lookup"><span data-stu-id="e9a45-113">**Status**</span></span>  
 <span data-ttu-id="e9a45-114">Zeigt den Status des Zielservers an.</span><span class="sxs-lookup"><span data-stu-id="e9a45-114">View the status of the target server.</span></span>  
  
 <span data-ttu-id="e9a45-115">**Abruf erzwingen**</span><span class="sxs-lookup"><span data-stu-id="e9a45-115">**Force Poll**</span></span>  
 <span data-ttu-id="e9a45-116">Klicken Sie auf diese Schaltfläche, um das Abrufen des Masterservers durch die ausgewählten Zielserver zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="e9a45-116">Click this button to force the selected target servers to poll the master server.</span></span>  
  
 <span data-ttu-id="e9a45-117">**Austritt erzwingen**</span><span class="sxs-lookup"><span data-stu-id="e9a45-117">**Force Defection**</span></span>  
 <span data-ttu-id="e9a45-118">Klicken Sie auf diese Schaltfläche, um das Austragen der ausgewählten Zielserver beim Masterserver zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="e9a45-118">Click this button to force the selected target servers to defect from the master server.</span></span>  
  
 <span data-ttu-id="e9a45-119">**Anweisungen bereitstellen**</span><span class="sxs-lookup"><span data-stu-id="e9a45-119">**Post Instructions**</span></span>  
 <span data-ttu-id="e9a45-120">Stellt die Anweisungen den ausgewählten Zielservern bereit.</span><span class="sxs-lookup"><span data-stu-id="e9a45-120">Post instructions to the selected target servers.</span></span>  
  
 <span data-ttu-id="e9a45-121">**Automatische Aktualisierung aktivieren**</span><span class="sxs-lookup"><span data-stu-id="e9a45-121">**Enable Auto Refresh**</span></span>  
 <span data-ttu-id="e9a45-122">Wählen Sie diese Option, um die angezeigten Informationen automatisch zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="e9a45-122">Select this option to automatically refresh the information shown.</span></span>  
  
 <span data-ttu-id="e9a45-123">**Aktualisieren alle**</span><span class="sxs-lookup"><span data-stu-id="e9a45-123">**Refresh every**</span></span>  
 <span data-ttu-id="e9a45-124">Gibt an, wie oft die Informationen auf dieser Seite aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="e9a45-124">Specify how often the information on this page is refreshed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9a45-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e9a45-125">See Also</span></span>  
 [<span data-ttu-id="e9a45-126">Automatisierte Verwaltung in einem Unternehmen</span><span class="sxs-lookup"><span data-stu-id="e9a45-126">Automated Administration Across an Enterprise</span></span>](automated-administration-across-an-enterprise.md)  
  
  
