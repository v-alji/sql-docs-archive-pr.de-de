---
title: Installieren von Analysis Services im tabellarischen Modus | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: cd6ac80d-b735-4e3e-a024-489f1409ad33
author: minewiskan
ms.author: owend
ms.openlocfilehash: a677fd7770f646067cafb8fedf6d3705ccf2de3c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697285"
---
# <a name="install-analysis-services-in-tabular-mode"></a><span data-ttu-id="338d4-102">Installieren von Analysis Services im Tabellenmodus</span><span class="sxs-lookup"><span data-stu-id="338d4-102">Install Analysis Services in Tabular Mode</span></span>
  <span data-ttu-id="338d4-103">Wenn Sie Analysis Services installieren, um die neuen Tabellenmodellierungsfunktionen zu verwenden, müssen Sie Analysis Services in einem Servermodus installieren, der diesen Modelltyp unterstützt.</span><span class="sxs-lookup"><span data-stu-id="338d4-103">If you are installing Analysis Services to use the new tabular modeling features, you must install Analysis Services in a server mode that supports that type of model.</span></span> <span data-ttu-id="338d4-104">Der Servermodus ist "Tabellarisch" und wird während der Installation konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="338d4-104">The server mode is Tabular, and it is configured during installation.</span></span>  
  
 <span data-ttu-id="338d4-105">Nach der Installation des Servers in diesem Modus können Sie ihn zum Hosten von Projektmappen nutzen, die Sie im Designer für tabellarische Modelle erstellen.</span><span class="sxs-lookup"><span data-stu-id="338d4-105">After you install the server in this mode, you can use it host solutions that you build in tabular model designer.</span></span> <span data-ttu-id="338d4-106">Ein Server im tabellarischen Modus ist erforderlich, um den Zugriff auf Daten im tabellarischen Modell über das Netzwerk zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="338d4-106">A tabular mode server is required if you want tabular model data access over the network.</span></span>  
  
 <span data-ttu-id="338d4-107">Sie können den Modus "Tabellarisch" im Installations-Assistenten oder in einem Befehlszeilensetup angeben.</span><span class="sxs-lookup"><span data-stu-id="338d4-107">You can specify Tabular mode in the Installation Wizard or in a command line setup.</span></span> <span data-ttu-id="338d4-108">Diese Vorgehensweisen werden in den nächsten Abschnitten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="338d4-108">The following sections describe each approach.</span></span>  
  
## <a name="installation-wizard"></a><span data-ttu-id="338d4-109">Installations-Assistent</span><span class="sxs-lookup"><span data-stu-id="338d4-109">Installation Wizard</span></span>  
 <span data-ttu-id="338d4-110">Die folgende Liste enthält die Seiten im SQL Server-Installations-Assistenten, die zum Installieren von Analysis Services im tabellarischen Modus verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="338d4-110">The following list shows you which pages in the SQL Server Installation wizard are used to install Analysis Services in Tabular mode:</span></span>  
  
1.  <span data-ttu-id="338d4-111">Wählen Sie in der Funktionsstruktur des Setups **Analysis Services** aus.</span><span class="sxs-lookup"><span data-stu-id="338d4-111">Select **Analysis Services** from the Feature Tree in Setup.</span></span>  
  
     <span data-ttu-id="338d4-112">![Funktionsstruktur des Setups mit Analysis Services](../../../sql-server/install/media/ssas-setupas.gif "Funktionsstruktur des Setups mit Analysis Services")</span><span class="sxs-lookup"><span data-stu-id="338d4-112">![Setup feature tree showing Analsyis Services](../../../sql-server/install/media/ssas-setupas.gif "Setup feature tree showing Analsyis Services")</span></span>  
  
2.  <span data-ttu-id="338d4-113">Achten Sie darauf, dass Sie auf der Seite Analysis Services Konfiguration die Option **tabellarischer Modus**auswählen.</span><span class="sxs-lookup"><span data-stu-id="338d4-113">On the Analysis Services Configuration page, be sure to select **Tabular Mode**.</span></span>  
  
     <span data-ttu-id="338d4-114">![Setupseite mit Analysis Services-Konfigurationsoptionen](../../../sql-server/install/media/ssas-setupasconfig.gif "Setupseite mit Analysis Services-Konfigurationsoptionen")</span><span class="sxs-lookup"><span data-stu-id="338d4-114">![Setup page with Analysis Services config options](../../../sql-server/install/media/ssas-setupasconfig.gif "Setup page with Analysis Services config options")</span></span>  
  
 <span data-ttu-id="338d4-115">Der tabellarische Modus verwendet die xVelocity-Engine für Datenanalyse im Arbeitsspeicher (VertiPaq). Dies ist der Standardspeicher für tabellarische Modelle, die Sie in Analysis Services bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="338d4-115">Tabular mode uses the xVelocity in-memory analytics engine (VertiPaq), which is the default storage for tabular models that you deploy to Analysis Services.</span></span> <span data-ttu-id="338d4-116">Nachdem Sie Projektmappen mit einem tabellarischen Modell auf dem Server bereitgestellt haben, können Sie selektiv tabellarische Projektmappen konfigurieren, um DirectQuery-Festplattenspeicher als Alternative zu arbeitsspeichergebundenem Speicher zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="338d4-116">After you deploy tabular model solutions to the server, you can selectively configure tabular solutions to use DirectQuery disk storage as an alternative to memory-bound storage.</span></span>  
  
## <a name="command-line-setup"></a><span data-ttu-id="338d4-117">Befehlszeilensetup</span><span class="sxs-lookup"><span data-stu-id="338d4-117">Command Line Setup</span></span>  
 <span data-ttu-id="338d4-118">Das SQL Server-Setup enthält einen neuen Parameter (`ASSERVERMODE`), der den Servermodus angibt.</span><span class="sxs-lookup"><span data-stu-id="338d4-118">SQL Server Setup includes a new parameter (`ASSERVERMODE`) that specifies the server mode.</span></span> <span data-ttu-id="338d4-119">Das folgende Beispiel zeigt ein Befehlszeilensetup, bei dem Analysis Services im tabellarischen Servermodus installiert wird.</span><span class="sxs-lookup"><span data-stu-id="338d4-119">The following example illustrates a command line setup that installs Analysis Services in Tabular server mode.</span></span>  
  
```  
  
Setup.exe /q /IAcceptSQLServerLicenseTerms /ACTION=install /FEATURES=AS /ASSERVERMODE=TABULAR /INSTANCENAME=ASTabular /INDICATEPROGRESS/ASSVCACCOUNT=<DomainName\UserName> /ASSVCPASSWORD=<StrongPassword> /ASSYSADMINACCOUNTS=<DomainName\UserName>   
```  
  
 <span data-ttu-id="338d4-120">`INSTANCENAME` muss kürzer als 17 Zeichen sein.</span><span class="sxs-lookup"><span data-stu-id="338d4-120">`INSTANCENAME` must be less than 17 characters.</span></span>  
  
 <span data-ttu-id="338d4-121">Alle Platzhalterkontowerte müssen durch gültige Konten und Kennwörter ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="338d4-121">All placeholder account values must be replaced with valid accounts and password.</span></span>  
  
 <span data-ttu-id="338d4-122">Mit der angegebenen Beispielbefehlszeilensyntax werden keine Tools, z. B. SQL Server Management Studio oder [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], installiert.</span><span class="sxs-lookup"><span data-stu-id="338d4-122">Tools such as SQL Server Management Studio or [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] are not installed using the example command line syntax that is provided.</span></span> <span data-ttu-id="338d4-123">Weitere Informationen zum Hinzufügen von Features finden Sie unter [Installieren von SQL Server 2014 von der Eingabeaufforderung](../../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md).</span><span class="sxs-lookup"><span data-stu-id="338d4-123">For more information about adding features, see [Install SQL Server 2014 from the Command Prompt](../../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md).</span></span>  
  
 <span data-ttu-id="338d4-124">Bei `ASSERVERMODE` wird die Groß- und Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="338d4-124">`ASSERVERMODE` is case-sensitive.</span></span>  <span data-ttu-id="338d4-125">Alle Werte müssen in Großbuchstaben angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="338d4-125">All values must be expressed in upper case.</span></span> <span data-ttu-id="338d4-126">In der folgenden Tabelle werden die gültigen Werte für `ASSERVERMODE` beschrieben.</span><span class="sxs-lookup"><span data-stu-id="338d4-126">The following table describes the valid values for `ASSERVERMODE`.</span></span>  
  
|<span data-ttu-id="338d4-127">Wert</span><span class="sxs-lookup"><span data-stu-id="338d4-127">Value</span></span>|<span data-ttu-id="338d4-128">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="338d4-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="338d4-129">MULTIDIMENSIONAL</span><span class="sxs-lookup"><span data-stu-id="338d4-129">MULTIDIMENSIONAL</span></span>|<span data-ttu-id="338d4-130">Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="338d4-130">This is the default value.</span></span> <span data-ttu-id="338d4-131">Wenn Sie `ASSERVERMODE` nicht festlegen, wird der Server im multidimensionalen Servermodus installiert.</span><span class="sxs-lookup"><span data-stu-id="338d4-131">If you do not set `ASSERVERMODE`, the server is installed in Multidimensional server mode.</span></span>|  
|<span data-ttu-id="338d4-132">POWERPIVOT</span><span class="sxs-lookup"><span data-stu-id="338d4-132">POWERPIVOT</span></span>|<span data-ttu-id="338d4-133">Dieser Wert ist optional.</span><span class="sxs-lookup"><span data-stu-id="338d4-133">This value is optional.</span></span> <span data-ttu-id="338d4-134">Wenn Sie den `ROLE`-Parameter festlegen, wird der Servermodus automatisch auf 1 festgelegt. Hierdurch wird `ASSERVERMODE` für eine PowerPivot für SharePoint-Installation optional.</span><span class="sxs-lookup"><span data-stu-id="338d4-134">In practice, if you set the `ROLE` parameter, the server mode is automatically set to 1, making `ASSERVERMODE` optional for a PowerPivot for SharePoint installation.</span></span> <span data-ttu-id="338d4-135">Weitere Informationen finden Sie unter [Installieren von Power Pivot über die Eingabeaufforderung](../../../sql-server/install/install-powerpivot-from-the-command-prompt.md).</span><span class="sxs-lookup"><span data-stu-id="338d4-135">For more information, see [Install PowerPivot from the Command Prompt](../../../sql-server/install/install-powerpivot-from-the-command-prompt.md).</span></span>|  
|<span data-ttu-id="338d4-136">TABULAR</span><span class="sxs-lookup"><span data-stu-id="338d4-136">TABULAR</span></span>|<span data-ttu-id="338d4-137">Dieser Wert ist erforderlich, wenn Sie Analysis Services mit einem Befehlszeilensetup im tabellarischen Modus installieren.</span><span class="sxs-lookup"><span data-stu-id="338d4-137">This value is required if you are installing Analysis Services in Tabular mode using command line setup.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="338d4-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="338d4-138">See Also</span></span>  
 <span data-ttu-id="338d4-139">[Bestimmen des Server Modus einer Analysis Services Instanz](../determine-the-server-mode-of-an-analysis-services-instance.md) </span><span class="sxs-lookup"><span data-stu-id="338d4-139">[Determine the Server Mode of an Analysis Services Instance](../determine-the-server-mode-of-an-analysis-services-instance.md) </span></span>  
 <span data-ttu-id="338d4-140">[Konfigurieren von in-Memory-oder directquery-Zugriff für eine tabellarische Modelldatenbank](../../tabular-models/enable-directquery-mode-in-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="338d4-140">[Configure In-Memory or DirectQuery Access for a Tabular Model Database](../../tabular-models/enable-directquery-mode-in-ssms.md) </span></span>  
 [<span data-ttu-id="338d4-141">Tabellarische Modellierung &#40;tabellarischen SSAS-&#41;</span><span class="sxs-lookup"><span data-stu-id="338d4-141">Tabular Modeling &#40;SSAS Tabular&#41;</span></span>](../../tabular-models/tabular-models-ssas.md)  
  
  
