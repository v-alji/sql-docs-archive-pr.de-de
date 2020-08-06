---
title: Starten des Hilfsprogramms "sqlcmd"
ms.custom: seo-lt-2019
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 00d57437-7a29-4da1-b639-ee990db055fb
author: rothja
ms.author: jroth
ms.openlocfilehash: d71e6f140238599b3f22850ee9b63a0ee25d900b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609779"
---
# <a name="start-the-sqlcmd-utility"></a><span data-ttu-id="cd0cb-102">Starten des Hilfsprogramms "sqlcmd"</span><span class="sxs-lookup"><span data-stu-id="cd0cb-102">Start the sqlcmd Utility</span></span>
  <span data-ttu-id="cd0cb-103">Damit Sie mit der Verwendung von `sqlcmd` beginnen können, müssen Sie zunächst das Hilfsprogramm starten und eine Verbindung mit einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] herstellen.</span><span class="sxs-lookup"><span data-stu-id="cd0cb-103">To begin using `sqlcmd`, you must first launch the utility and connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="cd0cb-104">Sie können die Verbindung mit einer Standardinstanz oder mit einer benannten Instanz herstellen.</span><span class="sxs-lookup"><span data-stu-id="cd0cb-104">You can connect to either a default or named instance.</span></span> <span data-ttu-id="cd0cb-105">Der erste Schritt besteht darin, das Hilfsprogramm `sqlcmd` zu starten.</span><span class="sxs-lookup"><span data-stu-id="cd0cb-105">The first step is to start the `sqlcmd` utility.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cd0cb-106">Die Windows-Authentifizierung ist der Standardauthentifizierungsmodus für `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="cd0cb-106">Windows Authentication is the default authentication mode for `sqlcmd`.</span></span> <span data-ttu-id="cd0cb-107">Wenn Sie die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Authentifizierung verwenden möchten, müssen Sie einen Benutzernamen und ein Kennwort angeben. Verwenden Sie hierzu die Optionen **-U** und **-P** .</span><span class="sxs-lookup"><span data-stu-id="cd0cb-107">To use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, you must specify a user name and password by using the **-U** and **-P** options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cd0cb-108">Standardmäßig wird [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] als die benannte Instanz **sqlexpress**installiert.</span><span class="sxs-lookup"><span data-stu-id="cd0cb-108">By default, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] installs as the named instance **sqlexpress**.</span></span>  
  
 <span data-ttu-id="cd0cb-109">Wenn Sie bisher noch keine Verbindung mit dieser Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] hergestellt haben, müssen Sie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] möglicherweise so konfigurieren, dass Verbindungen akzeptiert werden.</span><span class="sxs-lookup"><span data-stu-id="cd0cb-109">If you have not connected to this instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] before, you may have to configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to accept connections.</span></span>  
  
### <a name="to-start-the-sqlcmd-utility-and-connect-to-a-default-instance-of-sql-server"></a><span data-ttu-id="cd0cb-110">So starten Sie das Hilfsprogramm "sqlcmd" und stellen Sie eine Verbindung mit einer Standardinstanz von SQL Server her</span><span class="sxs-lookup"><span data-stu-id="cd0cb-110">To start the sqlcmd utility and connect to a default instance of SQL Server</span></span>  
  
1.  <span data-ttu-id="cd0cb-111">Klicken Sie im **Startmenü** auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="cd0cb-111">On the **Start** menu click **Run**.</span></span> <span data-ttu-id="cd0cb-112">Geben Sie im Feld **Öffnen** den Befehl **cmd**ein, und klicken Sie auf **OK** , um ein Eingabeaufforderungsfenster zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="cd0cb-112">In the **Open** box type **cmd**, and then click **OK** to open a Command Prompt window.</span></span>  
  
2.  <span data-ttu-id="cd0cb-113">Geben Sie an der Eingabeaufforderung `sqlcmd` ein:</span><span class="sxs-lookup"><span data-stu-id="cd0cb-113">At the command prompt, type `sqlcmd`.</span></span>  
  
3.  <span data-ttu-id="cd0cb-114">Drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="cd0cb-114">Press ENTER.</span></span>  
  
     <span data-ttu-id="cd0cb-115">Sie verfügen jetzt über eine vertrauenswürdige Verbindung mit der Standardinstanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , die auf dem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cd0cb-115">You now have a trusted connection to the default instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is running on your computer.</span></span>  
  
     <span data-ttu-id="cd0cb-116">**1>** die `sqlcmd` Eingabeaufforderung, die die Zeilennummer angibt.</span><span class="sxs-lookup"><span data-stu-id="cd0cb-116">**1>** is the `sqlcmd` prompt that specifies the line number.</span></span> <span data-ttu-id="cd0cb-117">Bei jedem Drücken der EINGABETASTE wird die Nummer um eins erhöht.</span><span class="sxs-lookup"><span data-stu-id="cd0cb-117">Each time you press ENTER, the number increases by one.</span></span>  
  
4.  <span data-ttu-id="cd0cb-118">Um die Sitzung zu beenden `sqlcmd` , geben Sie `EXIT` an der `sqlcmd` Eingabeaufforderung ein.</span><span class="sxs-lookup"><span data-stu-id="cd0cb-118">To end the `sqlcmd` session, type `EXIT` at the `sqlcmd` prompt.</span></span>  
  
### <a name="to-start-the-sqlcmd-utility-and-connect-to-a-named-instance-of-sql-server"></a><span data-ttu-id="cd0cb-119">So starten Sie das Hilfsprogramm "sqlcmd" und stellen eine Verbindung mit einer benannten Instanz von SQL Server her</span><span class="sxs-lookup"><span data-stu-id="cd0cb-119">To start the sqlcmd utility and connect to a named instance of SQL Server</span></span>  
  
1.  <span data-ttu-id="cd0cb-120">Öffnen Sie ein Eingabe Aufforderungs Fenster, und geben Sie `sqlcmd -S` *myServer\instanceName*ein.</span><span class="sxs-lookup"><span data-stu-id="cd0cb-120">Open a Command Prompt window, and type `sqlcmd -S`*myServer\instanceName*.</span></span> <span data-ttu-id="cd0cb-121">Ersetzen Sie *myServer\Instanzname* durch den Namen des Computers und der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz, mit der Sie eine Verbindung herstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="cd0cb-121">Replace *myServer\instanceName* with the name of the computer and the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that you want to connect to.</span></span>  
  
2.  <span data-ttu-id="cd0cb-122">Drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="cd0cb-122">Press ENTER.</span></span>  
  
     <span data-ttu-id="cd0cb-123">Die `sqlcmd` Eingabeaufforderung (1>) gibt an, dass Sie mit der angegebenen Instanz von verbunden sind [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cd0cb-123">The `sqlcmd` prompt (1>) indicates that you are connected to the specified instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cd0cb-124">Eingegebene [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen werden in einem Puffer gespeichert.</span><span class="sxs-lookup"><span data-stu-id="cd0cb-124">Entered [!INCLUDE[tsql](../../includes/tsql-md.md)] statements are stored in a buffer.</span></span> <span data-ttu-id="cd0cb-125">Sie werden als Batch ausgeführt, wenn der Befehl "GO" erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="cd0cb-125">They are executed as a batch when the GO command is encountered.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd0cb-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cd0cb-126">See Also</span></span>  
 [<span data-ttu-id="cd0cb-127">Ausführen von Transact-SQL-Skriptdateien mithilfe von „sqlcmd“</span><span class="sxs-lookup"><span data-stu-id="cd0cb-127">Run Transact-SQL Script Files Using sqlcmd</span></span>](sqlcmd-run-transact-sql-script-files.md)  
  
  
