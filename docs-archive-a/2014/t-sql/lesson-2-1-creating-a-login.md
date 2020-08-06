---
title: Erstellen einer Anmeldung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- creating a login
ms.assetid: a2512310-bdb6-41dc-858a-e866b2b58afc
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 400a57693fbea10270a51f5735a19b9639112ce9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722133"
---
# <a name="creating-a-login"></a><span data-ttu-id="bbb8b-102">Erstellen einer Anmeldung</span><span class="sxs-lookup"><span data-stu-id="bbb8b-102">Creating a Login</span></span>
  <span data-ttu-id="bbb8b-103">Benutzer benötigen eine Anmeldung, damit sie auf [!INCLUDE[ssDE](../includes/ssde-md.md)]zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="bbb8b-103">To access the [!INCLUDE[ssDE](../includes/ssde-md.md)], users require a login.</span></span> <span data-ttu-id="bbb8b-104">Die Anmeldung kann die Identität des Benutzers als Windows-Konto oder als Mitglied einer Windows-Gruppe darstellen, oder es kann sich dabei um eine [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Anmeldung handeln, die nur in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="bbb8b-104">The login can represent the user's identity as a Windows account or as a member of a Windows group, or the login can be a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login that exists only in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="bbb8b-105">Verwenden Sie nach Möglichkeit die Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="bbb8b-105">Whenever possible you should use Windows Authentication.</span></span>  
  
 <span data-ttu-id="bbb8b-106">Standardmäßig haben Administratoren auf Ihrem Computer vollständigen Zugriff auf [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bbb8b-106">By default, administrators on your computer have full access to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="bbb8b-107">In dieser Lektion benötigen wir einen Benutzer mit geringeren Privilegien. Aus diesem Grund erstellen Sie ein neues lokales Windows-Authentifizierungskonto auf Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="bbb8b-107">For this lesson, we want to have a less privileged user; therefore, you will create a new local Windows Authentication account on your computer.</span></span> <span data-ttu-id="bbb8b-108">Dazu müssen Sie über Administratorrechte auf dem Computer verfügen.</span><span class="sxs-lookup"><span data-stu-id="bbb8b-108">To do this, you must be an administrator on your computer.</span></span> <span data-ttu-id="bbb8b-109">Anschließend erteilen Sie diesem neuen Benutzer Zugriff auf [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bbb8b-109">Then you will grant that new user access to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
### <a name="to-create-a-new-windows-account"></a><span data-ttu-id="bbb8b-110">So erstellen Sie ein neues Windows-Konto</span><span class="sxs-lookup"><span data-stu-id="bbb8b-110">To create a new Windows account</span></span>  
  
1.  <span data-ttu-id="bbb8b-111">Klicken Sie im **Startmenü**auf **Ausführen**, geben Sie im Feld **Öffnen** ein `%SystemRoot%\system32\compmgmt.msc /s` , und klicken Sie dann auf **OK** , um das Programm Computer Verwaltung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="bbb8b-111">Click **Start**, click **Run**, in the **Open** box, type `%SystemRoot%\system32\compmgmt.msc /s`, and then click **OK** to open the Computer Management program.</span></span>  
  
2.  <span data-ttu-id="bbb8b-112">Erweitern Sie unter **Systemprogramme**den Eintrag **Lokale Benutzer und Gruppen**, klicken Sie mit der rechten Maustaste auf **Benutzer**und anschließend auf **Neuer Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="bbb8b-112">Under **System Tools**, expand **Local Users and Groups**, right-click **Users**, and then click **New User**.</span></span>  
  
3.  <span data-ttu-id="bbb8b-113">Geben Sie in das Feld **Benutzername\*\*\*\*Mary**ein.</span><span class="sxs-lookup"><span data-stu-id="bbb8b-113">In the **User name** box type **Mary**.</span></span>  
  
4.  <span data-ttu-id="bbb8b-114">Geben Sie in das Feld **Kennwort** und **Kennwort bestätigen** ein sicheres Kennwort ein. Klicken Sie anschließend auf **Erstellen** , um einen neuen lokalen Windows-Benutzer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bbb8b-114">In the **Password** and **Confirm password** box, type a strong password, and then click **Create** to create a new local Windows user.</span></span>  
  
### <a name="to-create-a-login"></a><span data-ttu-id="bbb8b-115">So erstellen Sie eine Anmeldung</span><span class="sxs-lookup"><span data-stu-id="bbb8b-115">To create a login</span></span>  
  
1.  <span data-ttu-id="bbb8b-116">Geben Sie in einem Abfrage-Editor-Fenster von [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]folgenden Code ein, und führen Sie ihn aus. Ersetzen Sie dabei `computer_name` durch den Namen Ihres Computers.</span><span class="sxs-lookup"><span data-stu-id="bbb8b-116">In a Query Editor window of [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], type and execute the following code replacing `computer_name` with the name of your computer.</span></span> <span data-ttu-id="bbb8b-117">`FROM WINDOWS` gibt an, dass Windows den Benutzer authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="bbb8b-117">`FROM WINDOWS` indicates that Windows will authenticate the user.</span></span> <span data-ttu-id="bbb8b-118">Mit dem optionalen `DEFAULT_DATABASE` -Argument wird `Mary` mit der `TestData` -Datenbank verbunden, sofern nicht ihre Verbindungszeichenfolge eine andere Datenbank angibt.</span><span class="sxs-lookup"><span data-stu-id="bbb8b-118">The optional `DEFAULT_DATABASE` argument connects `Mary` to the `TestData` database, unless her connection string indicates another database.</span></span> <span data-ttu-id="bbb8b-119">Diese Anweisung führt das Semikolon als optionale Beendigung für eine [!INCLUDE[tsql](../includes/tsql-md.md)] -Anweisung ein.</span><span class="sxs-lookup"><span data-stu-id="bbb8b-119">This statement introduces the semicolon as an optional termination for a [!INCLUDE[tsql](../includes/tsql-md.md)] statement.</span></span>  
  
    ```  
    CREATE LOGIN [computer_name\Mary]  
        FROM WINDOWS  
        WITH DEFAULT_DATABASE = [TestData];  
    GO  
    ```  
  
     <span data-ttu-id="bbb8b-120">Dadurch wird ein Benutzer mit Namen `Mary`, der von Ihrem Computer authentifiziert wird, zum Zugriff auf diese Instanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]berechtigt.</span><span class="sxs-lookup"><span data-stu-id="bbb8b-120">This authorizes a user name `Mary`, authenticated by your computer, to access this instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="bbb8b-121">Ist auf dem Computer mehr als eine Instanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] vorhanden, müssen Sie die Anmeldung auf jeder Instanz erstellen, auf die `Mary` Zugriff benötigt.</span><span class="sxs-lookup"><span data-stu-id="bbb8b-121">If there is more than one instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] on the computer, you must create the login on each instance that `Mary` must access.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bbb8b-122">Weil `Mary` kein Domänenkonto ist, kann dieser Benutzername nur auf diesem Computer authentifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="bbb8b-122">Because `Mary` is not a domain account, this user name can only be authenticated on this computer.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="bbb8b-123">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="bbb8b-123">Next Task in Lesson</span></span>  
 [<span data-ttu-id="bbb8b-124">Gewähren von Zugriff auf eine Datenbank</span><span class="sxs-lookup"><span data-stu-id="bbb8b-124">Granting Access to a Database</span></span>](lesson-2-2-granting-access-to-a-database.md)  
  
## <a name="see-also"></a><span data-ttu-id="bbb8b-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bbb8b-125">See Also</span></span>  
 <span data-ttu-id="bbb8b-126">[CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bbb8b-126">[CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql) </span></span>  
 [<span data-ttu-id="bbb8b-127">Auswählen eines Authentifizierungsmodus</span><span class="sxs-lookup"><span data-stu-id="bbb8b-127">Choose an Authentication Mode</span></span>](../relational-databases/security/choose-an-authentication-mode.md)  
  
  
