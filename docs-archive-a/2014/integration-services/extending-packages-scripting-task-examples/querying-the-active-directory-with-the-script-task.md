---
title: Abfragen des Active Directory mit dem Skripttask | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script task [Integration Services], Active Directory access
- SSIS Script task, Active Directory access
- Script task [Integration Services], examples
- Active Directory [Integration Services]
ms.assetid: a88fefbb-9ea2-4a86-b836-e71315bac68e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 624aa56289b9cab9174882b586a37e5d0de7ca9d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609367"
---
# <a name="querying-the-active-directory-with-the-script-task"></a><span data-ttu-id="a9190-102">Abfragen des Active Directory mit dem Skripttask</span><span class="sxs-lookup"><span data-stu-id="a9190-102">Querying the Active Directory with the Script Task</span></span>
  <span data-ttu-id="a9190-103">Anwendungen für die Verarbeitung von Unternehmensdaten, wie z. B. [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Pakete, müssen Daten häufig je nach Stellung, Berufsbezeichnung und anderen im Active Directory gespeicherten Eigenschaften der Mitarbeiter unterschiedlich verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="a9190-103">Enterprise data processing applications, such as [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages, often need to process data differently based on the rank, job title, or other characteristics of employees stored in Active Directory.</span></span> <span data-ttu-id="a9190-104">Active Directory ist ein [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows-Verzeichnisdienst, der einen zentralen Speicher für Metadaten nicht nur über Benutzer, sondern auch über andere Werte des Unternehmens, wie etwa über Computer und Drucker, bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="a9190-104">Active Directory is a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows directory service that provides a centralized store of metadata, not only about users, but also about other organizational assets such as computers and printers.</span></span> <span data-ttu-id="a9190-105">Der `System.DirectoryServices`-Namespace in Microsoft .NET Framework stellt Klassen für die Verwendung mit Active Directory bereit, sodass Sie den Datenverarbeitungsworkflow anhand der darin gespeicherten Informationen weiterleiten können.</span><span class="sxs-lookup"><span data-stu-id="a9190-105">The `System.DirectoryServices` namespace in the Microsoft .NET Framework provides classes for working with Active Directory, to help you direct data processing workflow based on the information that it stores.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a9190-106">Wenn Sie einen Task erstellen möchten, den Sie einfacher in mehreren Paketen wiederverwenden können, empfiehlt es sich, den Code in diesem Skripttaskbeispiel als Ausgangspunkt für einen benutzerdefinierten Task zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="a9190-106">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="a9190-107">Weitere Informationen finden Sie unter [Entwickeln eines benutzerdefinierten Tasks](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="a9190-107">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
## <a name="description"></a><span data-ttu-id="a9190-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a9190-108">Description</span></span>  
 <span data-ttu-id="a9190-109">Im folgenden Beispiel werden Name, Titel und Telefonnummer eines Mitarbeiters anhand des Werts der `email`-Variable, die die E-Mail-Adresse des Mitarbeiters enthält, aus dem Active Directory abgerufen.</span><span class="sxs-lookup"><span data-stu-id="a9190-109">The following example retrieves an employee's name, title, and phone number from Active Directory based on the value of the `email` variable, which contains the e-mail address of the employee.</span></span> <span data-ttu-id="a9190-110">Mithilfe von Rangfolgeneinschränkungen im Paket kann anhand der abgerufenen Informationen und der Berufsbezeichnung des Mitarbeiters beispielsweise bestimmt werden, ob eine E-Mail-Nachricht mit niedriger Priorität oder eine Seite mit hoher Priorität gesendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a9190-110">Precedence constraints in the package can use the retrieved information to determine, for example, whether to send a low-priority e-mail message or a high-priority page, based on the job title of the employee.</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="a9190-111">So konfigurieren Sie dieses Skripttaskbeispiel</span><span class="sxs-lookup"><span data-stu-id="a9190-111">To configure this Script Task example</span></span>  
  
1.  <span data-ttu-id="a9190-112">Erstellen Sie die drei Zeichenfolgenvariablen `email`, `name` und `title`.</span><span class="sxs-lookup"><span data-stu-id="a9190-112">Create the three string variables `email`, `name`, and `title`.</span></span> <span data-ttu-id="a9190-113">Geben Sie eine gültige Unternehmens-E-Mail-Adresse als Wert der `email`-Variable ein.</span><span class="sxs-lookup"><span data-stu-id="a9190-113">Enter a valid corporate email address as the value of the `email` variable.</span></span>  
  
2.  <span data-ttu-id="a9190-114">Fügen Sie der-Eigenschaft auf der Seite **Skript** im **Skript Task-Editor**die- `email` Variable hinzu `ReadOnlyVariables` .</span><span class="sxs-lookup"><span data-stu-id="a9190-114">On the **Script** page of the **Script Task Editor**, add the `email` variable to the `ReadOnlyVariables` property.</span></span>  
  
3.  <span data-ttu-id="a9190-115">Fügen Sie die Variablen `name` und `title` zur `ReadWriteVariables`-Eigenschaft hinzu.</span><span class="sxs-lookup"><span data-stu-id="a9190-115">Add the `name` and `title` variables to the `ReadWriteVariables` property.</span></span>  
  
4.  <span data-ttu-id="a9190-116">Fügen Sie im Skriptprojekt dem `System.DirectoryServices`-Namespace einen Verweis hinzu.</span><span class="sxs-lookup"><span data-stu-id="a9190-116">In the script project, add a reference to the `System.DirectoryServices` namespace.</span></span>  
  
5.  <span data-ttu-id="a9190-117">erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a9190-117">.</span></span> <span data-ttu-id="a9190-118">Verwenden Sie im Code eine `Imports`-Anweisung, um den `DirectoryServices`-Namespace zu importieren.</span><span class="sxs-lookup"><span data-stu-id="a9190-118">In your code, use an `Imports` statement to import the `DirectoryServices` namespace.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a9190-119">Damit dieses Skript ausgeführt werden kann, muss im Netzwerk des Unternehmens Active Directory verwendet werden. Zudem müssen die in diesem Beispiel verwendeten Mitarbeiterinformationen im Unternehmen gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="a9190-119">To run this script successfully, your company must be using Active Directory on its network and storing the employee information that this example uses.</span></span>  
  
### <a name="code"></a><span data-ttu-id="a9190-120">Code</span><span class="sxs-lookup"><span data-stu-id="a9190-120">Code</span></span>  
  
```vb  
Public Sub Main()  
  
    Dim directory As DirectoryServices.DirectorySearcher  
    Dim result As DirectoryServices.SearchResult  
    Dim email As String  
  
    email = Dts.Variables("email").Value.ToString  
  
    Try  
        directory = New _  
            DirectoryServices.DirectorySearcher("(mail=" & email & ")")  
        result = directory.FindOne  
        Dts.Variables("name").Value = _  
            result.Properties("displayname").ToString  
        Dts.Variables("title").Value = _  
            result.Properties("title").ToString  
        Dts.TaskResult = ScriptResults.Success  
    Catch ex As Exception  
        Dts.Events.FireError(0, _  
            "Script Task Example", _  
            ex.Message & ControlChars.CrLf & ex.StackTrace, _  
            String.Empty, 0)  
        Dts.TaskResult = ScriptResults.Failure  
    End Try  
  
End Sub  
```  
  
```csharp  
public void Main()  
{  
    //  
    DirectorySearcher directory;  
    SearchResult result;  
    string email;  
  
    email = (string)Dts.Variables["email"].Value;  
  
    try  
    {  
        directory = new DirectorySearcher("(mail=" + email + ")");  
        result = directory.FindOne();  
        Dts.Variables["name"].Value = result.Properties["displayname"].ToString();  
        Dts.Variables["title"].Value = result.Properties["title"].ToString();  
        Dts.TaskResult = (int)ScriptResults.Success;  
    }  
    catch (Exception ex)  
    {  
        Dts.Events.FireError(0, "Script Task Example", ex.Message + "\n" + ex.StackTrace, String.Empty, 0);  
        Dts.TaskResult = (int)ScriptResults.Failure;  
    }  
  
}  
```  
  
## <a name="external-resources"></a><span data-ttu-id="a9190-121">Externe Ressourcen</span><span class="sxs-lookup"><span data-stu-id="a9190-121">External Resources</span></span>  
  
-   <span data-ttu-id="a9190-122">Technischer Artikel – [Processing Active Directory Information in SSIS](https://go.microsoft.com/fwlink/?LinkId=199588) (Verarbeiten von Active Directory-Informationen in SSIS) – unter „social.technet.microsoft.com“</span><span class="sxs-lookup"><span data-stu-id="a9190-122">Technical article, [Processing Active Directory Information in SSIS](https://go.microsoft.com/fwlink/?LinkId=199588), on social.technet.microsoft.com</span></span>  
  
<span data-ttu-id="a9190-123">![Integration Services Symbol (klein)](../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="a9190-123">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="a9190-124">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="a9190-124">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="a9190-125">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="a9190-125">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="a9190-126">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a9190-126">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
