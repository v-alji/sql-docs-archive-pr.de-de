---
title: Arbeiten mit Bildern mithilfe des Skripttasks | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- graphics [Integration Services]
- Script task [Integration Services], images
- Drawing namespace
- images [Integration Services]
- SSIS Script task, images
- Script task [Integration Services], examples
- thumbnails [Integration Services]
- System.Drawing namespace
- JPEG format [Integration Services]
- .jpeg files
ms.assetid: 74aeb7ab-51b2-4b9f-84ee-0b46a7908ab9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 75a5b72f87a4463d7270dc9f28529a81525860cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618205"
---
# <a name="working-with-images-with-the-script-task"></a><span data-ttu-id="34e0c-102">Arbeiten mit Bildern mithilfe des Skripttasks</span><span class="sxs-lookup"><span data-stu-id="34e0c-102">Working with Images with the Script Task</span></span>
  <span data-ttu-id="34e0c-103">Datenbanken von Produkten oder Benutzern enthalten häufig neben Text und numerischen Daten auch Bilder.</span><span class="sxs-lookup"><span data-stu-id="34e0c-103">A database of products or users frequently includes images in addition to text and numeric data.</span></span> <span data-ttu-id="34e0c-104">Der `System.Drawing`-Namespace in Microsoft .NET Framework stellt Klassen zum Bearbeiten von Bildern bereit.</span><span class="sxs-lookup"><span data-stu-id="34e0c-104">The `System.Drawing` namespace in the Microsoft .NET Framework provides classes for manipulating images.</span></span>  
  
 [<span data-ttu-id="34e0c-105">Beispiel 1: Konvertieren von Bildern in das JPEG-Format</span><span class="sxs-lookup"><span data-stu-id="34e0c-105">Example 1: Convert Images to JPEG Format</span></span>](#example1)  
  
 [<span data-ttu-id="34e0c-106">Beispiel 2: Erstellen und Speichern von Miniaturbildern</span><span class="sxs-lookup"><span data-stu-id="34e0c-106">Example 2: Create and Save Thumbnail Images</span></span>](#example2)  
  
> [!NOTE]  
>  <span data-ttu-id="34e0c-107">Wenn Sie einen Task erstellen möchten, den Sie einfacher in mehreren Paketen wiederverwenden können, empfiehlt es sich, den Code in diesem Skripttaskbeispiel als Ausgangspunkt für einen benutzerdefinierten Task zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="34e0c-107">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="34e0c-108">Weitere Informationen finden Sie unter [Entwickeln eines benutzerdefinierten Tasks](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="34e0c-108">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
##  <a name="example-1-description-convert-images-to-jpeg-format"></a><a name="example1"></a> <span data-ttu-id="34e0c-109">Beschreibung zu Beispiel 1: Konvertieren von Bildern in das JPEG-Format</span><span class="sxs-lookup"><span data-stu-id="34e0c-109">Example 1 Description: Convert Images to JPEG Format</span></span>  
 <span data-ttu-id="34e0c-110">Im folgenden Beispiel wird eine Bilddatei, die durch eine Variable definiert ist, geöffnet und mithilfe eines Encoders als komprimierte JPEG-Datei gespeichert.</span><span class="sxs-lookup"><span data-stu-id="34e0c-110">The following example opens an image file specified by a variable and saves it as a compressed JPEG file by using an encoder.</span></span> <span data-ttu-id="34e0c-111">Der Code zum Abrufen der Encoderinformationen wird in einer privaten Funktion gekapselt.</span><span class="sxs-lookup"><span data-stu-id="34e0c-111">The code to retrieve encoder information is encapsulated in a private function.</span></span>  
  
#### <a name="to-configure-this-script-task-example-for-use-with-a-single-image-file"></a><span data-ttu-id="34e0c-112">So konfigurieren Sie dieses Skripttaskbeispiel zur Verwendung mit einer einzelnen Bilddatei</span><span class="sxs-lookup"><span data-stu-id="34e0c-112">To configure this Script Task example for use with a single image file</span></span>  
  
1.  <span data-ttu-id="34e0c-113">Erstellen Sie eine Zeichenfolgenvariable namens `CurrentImageFile`, und legen Sie ihren Wert auf den Pfad und Dateinamen einer bestehenden Bilddatei fest.</span><span class="sxs-lookup"><span data-stu-id="34e0c-113">Create a string variable named `CurrentImageFile` and set its value to the path and file name of an existing image file.</span></span>  
  
2.  <span data-ttu-id="34e0c-114">Fügen Sie der-Eigenschaft auf der Seite **Skript** im **Skript Task-Editor**die- `CurrentImageFile` Variable hinzu `ReadOnlyVariables` .</span><span class="sxs-lookup"><span data-stu-id="34e0c-114">On the **Script** page of the **Script Task Editor**, add the `CurrentImageFile` variable to the `ReadOnlyVariables` property.</span></span>  
  
3.  <span data-ttu-id="34e0c-115">Legen Sie im Skriptprojekt einen Verweis auf den `System.Drawing`-Namespace fest.</span><span class="sxs-lookup"><span data-stu-id="34e0c-115">In the script project, set a reference to the `System.Drawing` namespace.</span></span>  
  
4.  <span data-ttu-id="34e0c-116">Verwenden Sie im Code `Imports`-Anweisungen, um die Namespaces `System.Drawing` und `System.IO` zu importieren.</span><span class="sxs-lookup"><span data-stu-id="34e0c-116">In your code, use `Imports` statements to import the `System.Drawing` and `System.IO` namespaces.</span></span>  
  
#### <a name="to-configure-this-script-task-example-for-use-with-multiple-image-files"></a><span data-ttu-id="34e0c-117">So konfigurieren Sie dieses Skripttaskbeispiel zur Verwendung mit mehreren Bilddateien</span><span class="sxs-lookup"><span data-stu-id="34e0c-117">To configure this Script Task example for use with multiple image files</span></span>  
  
1.  <span data-ttu-id="34e0c-118">Platzieren Sie den Skripttask in einen Foreach-Schleifencontainer.</span><span class="sxs-lookup"><span data-stu-id="34e0c-118">Place the Script task within a Foreach Loop container.</span></span>  
  
2.  <span data-ttu-id="34e0c-119">Wählen Sie auf der Seite **Auflistung** im **Foreach-Schleifen-Editor** die Option **Foreach-Dateienumerator** als Enumerator aus, und geben Sie den Pfad und die Dateimaske der Quelldateien an, beispielsweise „\*.bmp“.</span><span class="sxs-lookup"><span data-stu-id="34e0c-119">On the **Collection** page of the **Foreach Loop Editor**, select the **Foreach File Enumerator** as the enumerator, and specify the path and file mask of the source files, such as "\*.bmp."</span></span>  
  
3.  <span data-ttu-id="34e0c-120">Ordnen Sie auf der Seite **Variablenzuordnungen** dem Index 0 die `CurrentImageFile`-Variable zu.</span><span class="sxs-lookup"><span data-stu-id="34e0c-120">On the **Variable Mappings** page, map the `CurrentImageFile` variable to Index 0.</span></span> <span data-ttu-id="34e0c-121">Die Variable übergibt bei jeder Iteration des Enumerators den aktuellen Dateinamen an den Skripttask.</span><span class="sxs-lookup"><span data-stu-id="34e0c-121">This variable passes the current file name to the Script task on each iteration of the enumerator.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="34e0c-122">Diese Schritte sind zusätzlich zu denen, die in der Vorgehensweise für eine einzelne Bilddatei beschrieben wurden, erforderlich.</span><span class="sxs-lookup"><span data-stu-id="34e0c-122">These steps are in addition to the steps listed in the procedure for use with a single image file.</span></span>  
  
### <a name="example-1-code"></a><span data-ttu-id="34e0c-123">Codebeispiel 1</span><span class="sxs-lookup"><span data-stu-id="34e0c-123">Example 1 Code</span></span>  
  
```vb  
Public Sub Main()  
  
    'Create and initialize variables.  
    Dim currentFile As String  
    Dim newFile As String  
    Dim bmp As Bitmap  
    Dim eps As New Imaging.EncoderParameters(1)  
    Dim ici As Imaging.ImageCodecInfo  
    Dim supportedExtensions() As String = _  
        {".BMP", ".GIF", ".JPG", ".JPEG", ".EXIF", ".PNG", _  
        ".TIFF", ".TIF", ".ICO", ".ICON"}  
  
    Try  
        'Store the variable in a string for local manipulation.  
        currentFile = Dts.Variables("CurrentImageFile").Value.ToString  
        'Check the extension of the file against a list of  
        'files that the Bitmap class supports.  
        If Array.IndexOf(supportedExtensions, _  
            Path.GetExtension(currentFile).ToUpper) > -1 Then  
  
            'Load the file.  
            bmp = New Bitmap(currentFile)  
  
            'Calculate the new name for the compressed image.  
            'Note: This will overwrite existing JPEGs.  
            newFile = Path.Combine( _  
                Path.GetDirectoryName(currentFile), _  
                String.Concat(Path.GetFileNameWithoutExtension(currentFile), _  
                ".jpg"))  
  
            'Specify the compression ratio (0=worst quality, 100=best quality).  
            eps.Param(0) = New Imaging.EncoderParameter( _  
                Imaging.Encoder.Quality, 75)  
  
            'Retrieve the ImageCodecInfo associated with the jpeg format.  
            ici = GetEncoderInfo("image/jpeg")  
  
            'Save the file, compressing it into the jpeg encoding.  
            bmp.Save(newFile, ici, eps)  
        Else  
            'The file is not supported by the Bitmap class.  
            Dts.Events.FireWarning(0, "Image Resampling Sample", _  
                "File " & currentFile & " is not a supported format.", _  
                "", 0)  
         End If  
        Dts.TaskResult = ScriptResults.Success  
    Catch ex As Exception  
        'An error occurred.  
        Dts.Events.FireError(0, "Image Resampling Sample", _  
            ex.Message & ControlChars.CrLf & ex.StackTrace, _  
            String.Empty, 0)  
        Dts.TaskResult = ScriptResults.Failure  
    End Try  
  
End Sub  
  
Private Function GetEncoderInfo(ByVal mimeType As String) As Imaging.ImageCodecInfo  
  
    'The available image codecs are returned as an array,  
    'which requires code to iterate until the specified codec is found.  
  
    Dim count As Integer  
    Dim encoders() As Imaging.ImageCodecInfo  
  
    encoders = Imaging.ImageCodecInfo.GetImageEncoders()  
  
    For count = 0 To encoders.Length  
        If encoders(count).MimeType = mimeType Then  
            Return encoders(count)  
        End If  
    Next  
  
    'This point is only reached if a codec is not found.  
    Err.Raise(513, "Image Resampling Sample", String.Format( _  
        "The {0} codec is not available. Unable to compress file.", _  
            mimeType))  
    Return Nothing  
  
End Function  
  
```  
  
##  <a name="example-2-description-create-and-save-thumbnail-images"></a><a name="example2"></a> <span data-ttu-id="34e0c-124">Beschreibung zu Beispiel 2: Erstellen und Speichern von Miniaturbildern</span><span class="sxs-lookup"><span data-stu-id="34e0c-124">Example 2 Description: Create and Save Thumbnail Images</span></span>  
 <span data-ttu-id="34e0c-125">Im folgenden Beispiel wird eine Bilddatei, die durch eine Variable definiert ist, geöffnet, ein Miniaturbild dieses Bilds mit gleichem Seitenverhältnis erstellt und das Miniaturbild mit geändertem Dateinamen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="34e0c-125">The following example opens an image file specified by a variable, creates a thumbnail of the image while maintaining a constant aspect ratio, and saves the thumbnail with a modified file name.</span></span> <span data-ttu-id="34e0c-126">Der Code, der Höhe und Breite des Miniaturbilds berechnet und dabei das Seitenverhältnis beibehält, wird in einer privaten Unterroutine gekapselt.</span><span class="sxs-lookup"><span data-stu-id="34e0c-126">The code that calculates the height and width of the thumbnail while maintaining a constant aspect ratio is encapsulated in a private subroutine.</span></span>  
  
#### <a name="to-configure-this-script-task-example-for-use-with-a-single-image-file"></a><span data-ttu-id="34e0c-127">So konfigurieren Sie dieses Skripttaskbeispiel zur Verwendung mit einer einzelnen Bilddatei</span><span class="sxs-lookup"><span data-stu-id="34e0c-127">To configure this Script Task example for use with a single image file</span></span>  
  
1.  <span data-ttu-id="34e0c-128">Erstellen Sie eine Zeichenfolgenvariable namens `CurrentImageFile`, und legen Sie ihren Wert auf den Pfad und Dateinamen einer bestehenden Bilddatei fest.</span><span class="sxs-lookup"><span data-stu-id="34e0c-128">Create a string variable named `CurrentImageFile` and set its value to the path and file name of an existing image file.</span></span>  
  
2.  <span data-ttu-id="34e0c-129">Erstellen Sie zudem die ganzzahlige Variable `MaxThumbSize`, und weisen Sie ihr einen Pixelwert, z. B. 100, zu.</span><span class="sxs-lookup"><span data-stu-id="34e0c-129">Also create the `MaxThumbSize` integer variable and assign a value in pixels, such as 100.</span></span>  
  
3.  <span data-ttu-id="34e0c-130">Fügen Sie der-Eigenschaft auf der Seite **Skript** des **Skript Task-Editors**beide Variablen hinzu `ReadOnlyVariables` .</span><span class="sxs-lookup"><span data-stu-id="34e0c-130">On the **Script** page of the **Script Task Editor**, add both variables to the `ReadOnlyVariables` property.</span></span>  
  
4.  <span data-ttu-id="34e0c-131">Legen Sie im Skriptprojekt einen Verweis auf den `System.Drawing`-Namespace fest.</span><span class="sxs-lookup"><span data-stu-id="34e0c-131">In the script project, set a reference to the `System.Drawing` namespace.</span></span>  
  
5.  <span data-ttu-id="34e0c-132">Verwenden Sie im Code `Imports`-Anweisungen, um die Namespaces `System.Drawing` und `System.IO` zu importieren.</span><span class="sxs-lookup"><span data-stu-id="34e0c-132">In your code, use `Imports` statements to import the `System.Drawing` and `System.IO` namespaces.</span></span>  
  
#### <a name="to-configure-this-script-task-example-for-use-with-multiple-image-files"></a><span data-ttu-id="34e0c-133">So konfigurieren Sie dieses Skripttaskbeispiel zur Verwendung mit mehreren Bilddateien</span><span class="sxs-lookup"><span data-stu-id="34e0c-133">To configure this Script Task example for use with multiple image files</span></span>  
  
1.  <span data-ttu-id="34e0c-134">Platzieren Sie den Skripttask in einen Foreach-Schleifencontainer.</span><span class="sxs-lookup"><span data-stu-id="34e0c-134">Place the Script task within a Foreach Loop container.</span></span>  
  
2.  <span data-ttu-id="34e0c-135">Wählen Sie auf der Seite **Auflistung** im **Foreach-Schleifen-Editor** die Option **Foreach-Dateienumerator** als **Enumerator** aus, und geben Sie den Pfad und die Dateimaske der Quelldateien an, beispielsweise „\*.jpg“.</span><span class="sxs-lookup"><span data-stu-id="34e0c-135">On the **Collection** page of the **Foreach Loop Editor**, select the **Foreach File Enumerator** as the **Enumerator**, and specify the path and file mask of the source files, such as "\*.jpg."</span></span>  
  
3.  <span data-ttu-id="34e0c-136">Ordnen Sie auf der Seite **Variablenzuordnungen** dem Index 0 die `CurrentImageFile`-Variable zu.</span><span class="sxs-lookup"><span data-stu-id="34e0c-136">On the **Variable Mappings** page, map the `CurrentImageFile` variable to Index 0.</span></span> <span data-ttu-id="34e0c-137">Die Variable übergibt bei jeder Iteration des Enumerators den aktuellen Dateinamen an den Skripttask.</span><span class="sxs-lookup"><span data-stu-id="34e0c-137">This variable passes the current file name to the Script task on each iteration of the enumerator.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="34e0c-138">Diese Schritte sind zusätzlich zu denen, die in der Vorgehensweise für eine einzelne Bilddatei beschrieben wurden, erforderlich.</span><span class="sxs-lookup"><span data-stu-id="34e0c-138">These steps are in addition to the steps listed in the procedure for use with a single image file.</span></span>  
  
### <a name="example-2-code"></a><span data-ttu-id="34e0c-139">Codebeispiel 2</span><span class="sxs-lookup"><span data-stu-id="34e0c-139">Example 2 Code</span></span>  
  
```vb  
Public Sub Main()  
  
    Dim currentImageFile As String  
    Dim currentImage As Image  
    Dim maxThumbSize As Integer  
    Dim thumbnailImage As Image  
    Dim thumbnailFile As String  
    Dim thumbnailHeight As Integer  
    Dim thumbnailWidth As Integer  
  
    currentImageFile = Dts.Variables("CurrentImageFile").Value.ToString  
    thumbnailFile = Path.Combine( _  
        Path.GetDirectoryName(currentImageFile), _  
        String.Concat(Path.GetFileNameWithoutExtension(currentImageFile), _  
        "_thumbnail.jpg"))  
  
    Try  
        currentImage = Image.FromFile(currentImageFile)  
  
        maxThumbSize = CType(Dts.Variables("MaxThumbSize").Value, Integer)  
        CalculateThumbnailSize( _  
            maxThumbSize, currentImage, thumbnailWidth, thumbnailHeight)  
  
        thumbnailImage = currentImage.GetThumbnailImage( _  
           thumbnailWidth, thumbnailHeight, Nothing, Nothing)  
        thumbnailImage.Save(thumbnailFile)  
        Dts.TaskResult = ScriptResults.Success  
    Catch ex As Exception  
        Dts.Events.FireError(0, "Script Task Example", _  
        ex.Message & ControlChars.CrLf & ex.StackTrace, _  
        String.Empty, 0)  
        Dts.TaskResult = ScriptResults.Failure  
    End Try  
  
End Sub  
  
Private Sub CalculateThumbnailSize( _  
    ByVal maxSize As Integer, ByVal sourceImage As Image, _  
    ByRef thumbWidth As Integer, ByRef thumbHeight As Integer)  
  
    If sourceImage.Width > sourceImage.Height Then  
        thumbWidth = maxSize  
        thumbHeight = CInt((maxSize / sourceImage.Width) * sourceImage.Height)  
    Else  
        thumbHeight = maxSize  
        thumbWidth = CInt((maxSize / sourceImage.Height) * sourceImage.Width)  
    End If  
  
End Sub  
```  
  
```csharp  
bool ThumbnailCallback()  
        {  
            return false;  
        }  
        public void Main()  
        {  
  
            string currentImageFile;  
            Image currentImage;  
            int maxThumbSize;  
            Image thumbnailImage;  
            string thumbnailFile;  
            int thumbnailHeight = 0;  
            int thumbnailWidth = 0;  
  
            currentImageFile = Dts.Variables["CurrentImageFile"].Value.ToString();  
            thumbnailFile = Path.Combine(Path.GetDirectoryName(currentImageFile), String.Concat(Path.GetFileNameWithoutExtension(currentImageFile), "_thumbnail.jpg"));  
  
            try  
            {  
  
                currentImage = Image.FromFile(currentImageFile);  
  
                maxThumbSize = (int)Dts.Variables["MaxThumbSize"].Value;  
                CalculateThumbnailSize(maxThumbSize, currentImage, ref thumbnailWidth, ref thumbnailHeight);  
  
                Image.GetThumbnailImageAbort myCallback = new Image.GetThumbnailImageAbort(ThumbnailCallback);  
  
                thumbnailImage = currentImage.GetThumbnailImage(thumbnailWidth, thumbnailHeight, ThumbnailCallback, IntPtr.Zero);  
                thumbnailImage.Save(thumbnailFile);  
                Dts.TaskResult = (int)ScriptResults.Success;  
            }  
            catch (Exception ex)  
            {  
                Dts.Events.FireError(0, "Script Task Example", ex.Message + "\r" + ex.StackTrace, String.Empty, 0);  
                Dts.TaskResult = (int)ScriptResults.Failure;  
            }  
  
        }  
  
        private void CalculateThumbnailSize(int maxSize, Image sourceImage, ref int thumbWidth, ref int thumbHeight)  
        {  
  
            if (sourceImage.Width > sourceImage.Height)  
            {  
                thumbWidth = maxSize;  
                thumbHeight = (int)(sourceImage.Height * maxSize / sourceImage.Width);  
            }  
            else  
            {  
                thumbHeight = maxSize;  
                thumbWidth = (int)(sourceImage.Width * maxSize / sourceImage.Height);  
  
            }  
  
        }  
  
```  
  
<span data-ttu-id="34e0c-140">![Integration Services Symbol (klein)](../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="34e0c-140">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="34e0c-141">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="34e0c-141">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="34e0c-142">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="34e0c-142">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="34e0c-143">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="34e0c-143">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
