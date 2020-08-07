---
title: Servereigenschaften (Seite „Sonstige Servereinstellungen“) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.serverproperties.miscserversettings.f1
ms.assetid: b170c066-30cd-42dd-8d34-aa129ea09551
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9a82a787140141c3bfa7b18776328a813be9f41f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618895"
---
# <a name="server-properties-misc-server-settings-page"></a><span data-ttu-id="1a155-102">Servereigenschaften (Seite Sonstige Servereinstellungen)</span><span class="sxs-lookup"><span data-stu-id="1a155-102">Server Properties (Misc Server Settings Page)</span></span>
  <span data-ttu-id="1a155-103">Auf dieser Seite können Sie Ihre Servereinstellungen anzeigen und ändern.</span><span class="sxs-lookup"><span data-stu-id="1a155-103">Use this page to view or modify your server settings.</span></span>  
  
## <a name="options"></a><span data-ttu-id="1a155-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="1a155-104">Options</span></span>  
 <span data-ttu-id="1a155-105">**Standardsprache für Benutzer**</span><span class="sxs-lookup"><span data-stu-id="1a155-105">**Default language for users**</span></span>  
 <span data-ttu-id="1a155-106">Gibt die Standardsprache für alle neu erstellten Benutzernamen an.</span><span class="sxs-lookup"><span data-stu-id="1a155-106">Specifies the default language for all newly created logins.</span></span>  
  
 <span data-ttu-id="1a155-107">**Zulassen, dass Trigger weitere Trigger auslösen**</span><span class="sxs-lookup"><span data-stu-id="1a155-107">**Allow triggers to fire other triggers**</span></span>  
 <span data-ttu-id="1a155-108">Steuert, ob ein Trigger eine Aktion ausführen kann, die weitere Trigger auslöst.</span><span class="sxs-lookup"><span data-stu-id="1a155-108">Controls whether a trigger can perform an action that initiates another trigger.</span></span> <span data-ttu-id="1a155-109">Wenn das Kontrollkästchen deaktiviert ist, können Trigger nicht von einem anderen Trigger ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="1a155-109">When cleared, triggers cannot be fired by another trigger.</span></span> <span data-ttu-id="1a155-110">Wenn das Kontrollkästchen aktiviert ist, können Trigger über 32 Ebenen jeweils von einem anderen Trigger ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="1a155-110">When selected, triggers can be fired by other triggers to as many as 32 levels.</span></span>  
  
 <span data-ttu-id="1a155-111">**Abfragekontrolle verwenden, um Abfragen mit langer Ausführungszeit zu verhindern**</span><span class="sxs-lookup"><span data-stu-id="1a155-111">**Use query governor to prevent long-running queries**</span></span>  
 <span data-ttu-id="1a155-112">Gibt eine zeitliche Obergrenze für die Ausführung einer Abfrage an.</span><span class="sxs-lookup"><span data-stu-id="1a155-112">Specifies an upper limit on the time within which a query can run.</span></span> <span data-ttu-id="1a155-113">Die Abfragekosten beziehen sich auf eine geschätzte Zeit in Sekunden, die für das Ausführen einer Abfrage bei einer bestimmten Hardwarekonfiguration benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="1a155-113">Query cost refers to the estimated elapsed time, in seconds, required to execute a query on a specific hardware configuration.</span></span> <span data-ttu-id="1a155-114">Die Abfragekontrolle ist standardmäßig deaktiviert, und alle Abfragen können ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1a155-114">By default, the query governor is turned off and all queries are allowed to run.</span></span> <span data-ttu-id="1a155-115">Wenn diese Option ausgewählt ist, müssen Sie in das Textfeld unten ein Zeitlimit eingeben.</span><span class="sxs-lookup"><span data-stu-id="1a155-115">If this option is selected, you must enter a time limit in the text box below.</span></span> <span data-ttu-id="1a155-116">Wenn Sie einen nicht negativen Wert ungleich null angeben, lässt die Abfragekontrolle die Ausführung von Abfragen, deren geschätzte Kosten über diesem Wert liegen, nicht zu.</span><span class="sxs-lookup"><span data-stu-id="1a155-116">If you specify a nonzero, nonnegative value, the query governor disallows execution of any query that has an estimated cost exceeding that value.</span></span>  
  
 <span data-ttu-id="1a155-117">**Zweistellige Jahresangaben als Jahre in diesem Bereich interpretieren**</span><span class="sxs-lookup"><span data-stu-id="1a155-117">**Interpret a two-digit year as falling between**</span></span>  
 <span data-ttu-id="1a155-118">Gibt den 100-Jahre-Datumsbereich zum Interpretieren von zweistelligen Jahreszahlenwerten an.</span><span class="sxs-lookup"><span data-stu-id="1a155-118">Specifies the 100-year date range for interpreting two-digit year values.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="1a155-119">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] interpretiert zweistellige Datumswerte so, dass auf das mit diesen Ziffern endende Jahr verwiesen wird, das in den angegebenen Bereich fällt.</span><span class="sxs-lookup"><span data-stu-id="1a155-119">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will interpret two-digit date values to refer to the year ending in those digits that falls within the specified range.</span></span>  
  
 <span data-ttu-id="1a155-120">Legen Sie im rechten Feld das Endjahr fest.</span><span class="sxs-lookup"><span data-stu-id="1a155-120">Set the right box with the ending year.</span></span> <span data-ttu-id="1a155-121">Nach dem Speichern des Endjahres wird von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] das linke Feld automatisch mit dem Startjahr aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="1a155-121">When the ending year is saved, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will automatically populate the left box with the beginning year.</span></span>  
  
 <span data-ttu-id="1a155-122">**Konfigurierte Werte**</span><span class="sxs-lookup"><span data-stu-id="1a155-122">**Configured Values**</span></span>  
 <span data-ttu-id="1a155-123">Zeigt für die Optionen in diesem Bereich konfigurierte Werte an.</span><span class="sxs-lookup"><span data-stu-id="1a155-123">Displays the configured values for the options on this pane.</span></span> <span data-ttu-id="1a155-124">Wenn Sie diese Werte ändern, klicken Sie anschließend auf **Ausgeführte Werte** , um zu sehen, ob die Änderungen wirksam sind.</span><span class="sxs-lookup"><span data-stu-id="1a155-124">If you change these values, click **Running Values** to see whether the changes have taken effect.</span></span> <span data-ttu-id="1a155-125">Wenn die Änderungen nicht wirksam geworden sind, muss die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] zunächst neu gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="1a155-125">If the changes have not taken effect, the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be restated first.</span></span>  
  
 <span data-ttu-id="1a155-126">**Ausgeführte Werte**</span><span class="sxs-lookup"><span data-stu-id="1a155-126">**Running Values**</span></span>  
 <span data-ttu-id="1a155-127">Zeigt die gegenwärtig ausgeführten Werte für die Optionen in diesem Bereich an.</span><span class="sxs-lookup"><span data-stu-id="1a155-127">View the currently running values for the options on this pane.</span></span> <span data-ttu-id="1a155-128">Diese Werte sind schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="1a155-128">These values are read-only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a155-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1a155-129">See Also</span></span>  
 [<span data-ttu-id="1a155-130">Serverkonfigurationsoptionen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1a155-130">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)  
  
  
