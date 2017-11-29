---
title: "Porady: wysyłanie danych przy użyciu klasy WebRequest"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WebRequest class, sending data to a host
- Sending data to a host, using WebRequest class
ms.assetid: 66686878-38ac-4aa6-bf42-ffb568ffc459
caps.latest.revision: "12"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 2102fce150f512a49093eb2b214258ac35e276e5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-send-data-using-the-webrequest-class"></a><span data-ttu-id="dfe52-102">Porady: wysyłanie danych przy użyciu klasy WebRequest</span><span class="sxs-lookup"><span data-stu-id="dfe52-102">How to: Send Data Using the WebRequest Class</span></span>
<span data-ttu-id="dfe52-103">W poniższej procedurze opisano kroki używane do wysyłania danych do serwera.</span><span class="sxs-lookup"><span data-stu-id="dfe52-103">The following procedure describes the steps used to send data to a server.</span></span> <span data-ttu-id="dfe52-104">Ta procedura jest najczęściej używany do publikowania danych do strony sieci Web.</span><span class="sxs-lookup"><span data-stu-id="dfe52-104">This procedure is commonly used to post data to a Web page.</span></span>  
  
### <a name="to-send-data-to-a-host-server"></a><span data-ttu-id="dfe52-105">Do przesyłania danych do serwera hosta</span><span class="sxs-lookup"><span data-stu-id="dfe52-105">To send data to a host server</span></span>  
  
1.  <span data-ttu-id="dfe52-106">Utwórz <xref:System.Net.WebRequest> wystąpienia przez wywołanie metody <xref:System.Net.WebRequest.Create%2A> o identyfikatorze URI zasobu, który akceptuje dane, na przykład, skrypt lub strony ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="dfe52-106">Create a <xref:System.Net.WebRequest> instance by calling <xref:System.Net.WebRequest.Create%2A> with the URI of the resource that accepts data, for example, a script or ASP.NET page.</span></span>  
  
    ```csharp  
    WebRequest request = WebRequest.Create("http://www.contoso.com/");  
    ```  
  
    ```vb  
    Dim request as WebRequest = WebRequest.Create("http://www.contoso.com/")  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="dfe52-107">Platforma .NET Framework zapewnia oparte na protokole klasy pochodzące od **WebRequest** i **WebResponse** identyfikatory URI, które rozpoczynają się od "http:", "https:", "ftp:", i "pliku:".</span><span class="sxs-lookup"><span data-stu-id="dfe52-107">The .NET Framework provides protocol-specific classes derived from **WebRequest** and **WebResponse** for URIs that begin with "http:", "https:'', "ftp:", and "file:".</span></span> <span data-ttu-id="dfe52-108">Aby uzyskać dostęp do zasobów przy użyciu innych protokołów, musi implementować klasy specyficzne dla protokołu, pochodzących z **WebRequest** i **WebResponse**.</span><span class="sxs-lookup"><span data-stu-id="dfe52-108">To access resources using other protocols, you must implement protocol-specific classes that derive from **WebRequest** and **WebResponse**.</span></span> <span data-ttu-id="dfe52-109">Aby uzyskać więcej informacji, zobacz [programowania podłączany protokołów](../../../docs/framework/network-programming/programming-pluggable-protocols.md) .</span><span class="sxs-lookup"><span data-stu-id="dfe52-109">For more information, see [Programming Pluggable Protocols](../../../docs/framework/network-programming/programming-pluggable-protocols.md) .</span></span>  
  
2.  <span data-ttu-id="dfe52-110">Ustawianie wartości właściwości wymaganych w **WebRequest**.</span><span class="sxs-lookup"><span data-stu-id="dfe52-110">Set any property values that you need in the **WebRequest**.</span></span> <span data-ttu-id="dfe52-111">Na przykład, aby włączyć uwierzytelnianie, należy ustawić **poświadczenia** dla właściwości wystąpienia <xref:System.Net.NetworkCredential> klasy.</span><span class="sxs-lookup"><span data-stu-id="dfe52-111">For example, to enable authentication, set the **Credentials** property to an instance of the <xref:System.Net.NetworkCredential> class.</span></span>  
  
    ```csharp  
    request.Credentials = CredentialCache.DefaultCredentials;  
    ```  
  
    ```vb  
    request.Credentials = CredentialCache.DefaultCredentials  
    ```  
  
     <span data-ttu-id="dfe52-112">W większości przypadków **WebRequest** wystąpienie jest wystarczająca do przesyłania danych.</span><span class="sxs-lookup"><span data-stu-id="dfe52-112">In most cases, the **WebRequest** instance itself is sufficient to send data.</span></span> <span data-ttu-id="dfe52-113">Jednak jeśli należy ustawić właściwości specyficzne dla protokołu, należy rzutować **WebRequest** typowi specyficzne dla protokołu.</span><span class="sxs-lookup"><span data-stu-id="dfe52-113">However, if you need to set protocol-specific properties, you must cast the **WebRequest** to the protocol-specific type.</span></span> <span data-ttu-id="dfe52-114">Na przykład do właściwości dostępu specyficzne dla protokołu HTTP <xref:System.Net.HttpWebRequest>, rzutowanie **WebRequest** do **HttpWebRequest** odwołania.</span><span class="sxs-lookup"><span data-stu-id="dfe52-114">For example, to access the HTTP-specific properties of <xref:System.Net.HttpWebRequest>, cast the **WebRequest** to an **HttpWebRequest** reference.</span></span> <span data-ttu-id="dfe52-115">W poniższym przykładzie przedstawiono sposób ustawiania specyficzne dla protokołu HTTP <xref:System.Net.HttpWebRequest.UserAgent%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="dfe52-115">The following code example shows how to set the HTTP-specific <xref:System.Net.HttpWebRequest.UserAgent%2A> property.</span></span>  
  
    ```csharp  
    ((HttpWebRequest)request).UserAgent = ".NET Framework Example Client";  
    ```  
  
    ```vb  
    Ctype(request,HttpWebRequest).UserAgent = ".NET Framework Example Client"  
    ```  
  
3.  <span data-ttu-id="dfe52-116">Określ metodę protokołu, która pozwala na dane mają być wysyłane z żądaniem, takich jak HTTP **POST** metody.</span><span class="sxs-lookup"><span data-stu-id="dfe52-116">Specify a protocol method that permits data to be sent with a request, such as the HTTP **POST** method.</span></span>  
  
    ```csharp  
    request.Method = "POST";  
    ```  
  
    ```vb  
    request.Method = "POST"  
    ```  
  
4.  <span data-ttu-id="dfe52-117">Ustaw **ContentLength** właściwości.</span><span class="sxs-lookup"><span data-stu-id="dfe52-117">Set the **ContentLength** property.</span></span>  
  
    ```csharp  
    request.ContentLength = byteArray.Length;  
    ```  
  
    ```vb  
    request.ContentLength = byteArray.Length  
    ```  
  
5.  <span data-ttu-id="dfe52-118">Ustaw **ContentType** właściwości odpowiednią wartość.</span><span class="sxs-lookup"><span data-stu-id="dfe52-118">Set the **ContentType** property to an appropriate value.</span></span>  
  
    ```csharp  
    request.ContentType = "application/x-www-form-urlencoded";  
    ```  
  
    ```vb  
    request.ContentType = "application/x-www-form-urlencoded"  
    ```  
  
6.  <span data-ttu-id="dfe52-119">Strumień, że blokad dane żądania przez wywołanie metody GET <xref:System.Net.WebRequest.GetRequestStream%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="dfe52-119">Get the stream that holds request data by calling the <xref:System.Net.WebRequest.GetRequestStream%2A> method.</span></span>  
  
    ```csharp  
    Stream dataStream = request.GetRequestStream ();  
    ```  
  
    ```vb  
    Stream dataStream = request.GetRequestStream ()  
    ```  
  
7.  <span data-ttu-id="dfe52-120">Zapisane dane <xref:System.IO.Stream> obiektu zwróconego przez tę metodę.</span><span class="sxs-lookup"><span data-stu-id="dfe52-120">Write the data to the <xref:System.IO.Stream> object returned by this method.</span></span>  
  
    ```csharp  
    dataStream.Write (byteArray, 0, byteArray.Length);  
    ```  
  
    ```vb  
    dataStream.Write (byteArray, 0, byteArray.Length)  
    ```  
  
8.  <span data-ttu-id="dfe52-121">Zamknij strumienia żądania przez wywołanie metody **Stream.Close** metody.</span><span class="sxs-lookup"><span data-stu-id="dfe52-121">Close the request stream by calling the **Stream.Close** method.</span></span>  
  
    ```csharp  
    dataStream.Close ();  
    ```  
  
    ```vb  
    dataStream.Close ()  
    ```  
  
9. <span data-ttu-id="dfe52-122">Wyślij żądanie do serwera przez wywołanie metody <xref:System.Net.WebRequest.GetResponse%2A>.</span><span class="sxs-lookup"><span data-stu-id="dfe52-122">Send the request to the server by calling <xref:System.Net.WebRequest.GetResponse%2A>.</span></span> <span data-ttu-id="dfe52-123">Ta metoda zwraca obiekt zawierający odpowiedzi serwera.</span><span class="sxs-lookup"><span data-stu-id="dfe52-123">This method returns an object containing the server's response.</span></span> <span data-ttu-id="dfe52-124">Zwrócona <xref:System.Net.WebResponse> typ obiektu jest określany przez schemat identyfikatora URI żądania.</span><span class="sxs-lookup"><span data-stu-id="dfe52-124">The returned <xref:System.Net.WebResponse> object's type is determined by the scheme of the request's URI.</span></span>  
  
    ```csharp  
    WebResponse response = request.GetResponse();  
    ```  
  
    ```vb  
    Dim response As WebResponse = request.GetResponse()  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="dfe52-125">Po zakończeniu <xref:System.Net.WebResponse> obiektu, należy go zamknąć, wywołując <xref:System.Net.WebResponse.Close%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="dfe52-125">After you are finished with a <xref:System.Net.WebResponse> object, you must close it by calling the <xref:System.Net.WebResponse.Close%2A> method.</span></span> <span data-ttu-id="dfe52-126">Alternatywnie, jeśli z obiektu odpowiedzi stają się coraz w strumieniu odpowiedzi, można zamknąć strumienia przez wywołanie metody <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType> metody.</span><span class="sxs-lookup"><span data-stu-id="dfe52-126">Alternatively, if you have gotten the response stream from the response object, you can close the stream by calling the <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="dfe52-127">Jeśli nie zamkniesz odpowiedzi lub strumienia, aplikacja może zabraknie połączenia z serwerem i stają się nie może przetworzyć żądania dodatkowe.</span><span class="sxs-lookup"><span data-stu-id="dfe52-127">If you do not close the response or the stream, your application can run out of connections to the server and become unable to process additional requests.</span></span>  
  
10. <span data-ttu-id="dfe52-128">Można uzyskać dostęp do właściwości **WebResponse** lub Zastosuj rzutowanie **WebResponse** do wystąpienia Protokołem do odczytu właściwości specyficzne dla protokołu.</span><span class="sxs-lookup"><span data-stu-id="dfe52-128">You can access the properties of the **WebResponse** or cast the **WebResponse** to a protocol-specific instance to read protocol-specific properties.</span></span> <span data-ttu-id="dfe52-129">Na przykład do właściwości dostępu specyficzne dla protokołu HTTP <xref:System.Net.HttpWebResponse>, rzutowanie **WebResponse** do **HttpWebResponse** odwołania.</span><span class="sxs-lookup"><span data-stu-id="dfe52-129">For example, to access the HTTP-specific properties of <xref:System.Net.HttpWebResponse>, cast the **WebResponse** to an **HttpWebResponse** reference.</span></span>  
  
    ```csharp  
    Console.WriteLine (((HttpWebResponse)response).StatusDescription);  
    ```  
  
    ```vb  
    Console.WriteLine(CType(response, HttpWebResponse).StatusDescription)  
    ```  
  
11. <span data-ttu-id="dfe52-130">Aby uzyskać strumienia zawierające dane odpowiedzi wysyłane przez serwer, należy wywołać <xref:System.Net.WebResponse.GetResponseStream%2A> metody **WebResponse**.</span><span class="sxs-lookup"><span data-stu-id="dfe52-130">To get the stream containing response data sent by the server, call the <xref:System.Net.WebResponse.GetResponseStream%2A> method of the **WebResponse**.</span></span>  
  
    ```csharp  
    Stream data = response.GetResponseStream;  
    ```  
  
    ```vb  
    Dim data As Stream = response.GetResponseStream  
    ```  
  
12. <span data-ttu-id="dfe52-131">Po odczytaniu danych z odpowiedzi, należy albo zamknąć przy użyciu strumienia odpowiedzi **Stream.Close** metody lub zamknij odpowiedzi, za pomocą **WebResponse.Close** metody.</span><span class="sxs-lookup"><span data-stu-id="dfe52-131">After reading the data from the response, you must either close the response stream using the **Stream.Close** method or close the response using the **WebResponse.Close** method.</span></span> <span data-ttu-id="dfe52-132">Nie jest konieczne do wywołania **Zamknij** metody w strumieniu odpowiedzi i **WebResponse**, ale spowoduje to nie jest szkodliwe.</span><span class="sxs-lookup"><span data-stu-id="dfe52-132">It is not necessary to call the **Close** method on both the response stream and the **WebResponse**, but doing so is not harmful.</span></span>  
  
    ```csharp  
    response.Close();  
    ```  
  
    ```vb  
    response.Close()  
    ```  
  
## <a name="example"></a><span data-ttu-id="dfe52-133">Przykład</span><span class="sxs-lookup"><span data-stu-id="dfe52-133">Example</span></span>  
  
```csharp  
using System;  
using System.IO;  
using System.Net;  
using System.Text;  
  
namespace Examples.System.Net  
{  
    public class WebRequestPostExample  
    {  
        public static void Main ()  
        {  
            // Create a request using a URL that can receive a post.   
            WebRequest request = WebRequest.Create ("http://www.contoso.com/PostAccepter.aspx ");  
            // Set the Method property of the request to POST.  
            request.Method = "POST";  
            // Create POST data and convert it to a byte array.  
            string postData = "This is a test that posts this string to a Web server.";  
            byte[] byteArray = Encoding.UTF8.GetBytes (postData);  
            // Set the ContentType property of the WebRequest.  
            request.ContentType = "application/x-www-form-urlencoded";  
            // Set the ContentLength property of the WebRequest.  
            request.ContentLength = byteArray.Length;  
            // Get the request stream.  
            Stream dataStream = request.GetRequestStream ();  
            // Write the data to the request stream.  
            dataStream.Write (byteArray, 0, byteArray.Length);  
            // Close the Stream object.  
            dataStream.Close ();  
            // Get the response.  
            WebResponse response = request.GetResponse ();  
            // Display the status.  
            Console.WriteLine (((HttpWebResponse)response).StatusDescription);  
            // Get the stream containing content returned by the server.  
            dataStream = response.GetResponseStream ();  
            // Open the stream using a StreamReader for easy access.  
            StreamReader reader = new StreamReader (dataStream);  
            // Read the content.  
            string responseFromServer = reader.ReadToEnd ();  
            // Display the content.  
            Console.WriteLine (responseFromServer);  
            // Clean up the streams.  
            reader.Close ();  
            dataStream.Close ();  
            response.Close ();  
        }  
    }  
}  
```  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Net  
Imports System.Text  
Namespace Examples.System.Net  
    Public Class WebRequestPostExample  
  
        Public Shared Sub Main()  
            ' Create a request using a URL that can receive a post.   
            Dim request As WebRequest = WebRequest.Create("http://www.contoso.com/PostAccepter.aspx ")  
            ' Set the Method property of the request to POST.  
            request.Method = "POST"  
            ' Create POST data and convert it to a byte array.  
            Dim postData As String = "This is a test that posts this string to a Web server."  
            Dim byteArray As Byte() = Encoding.UTF8.GetBytes(postData)  
            ' Set the ContentType property of the WebRequest.  
            request.ContentType = "application/x-www-form-urlencoded"  
            ' Set the ContentLength property of the WebRequest.  
            request.ContentLength = byteArray.Length  
            ' Get the request stream.  
            Dim dataStream As Stream = request.GetRequestStream()  
            ' Write the data to the request stream.  
            dataStream.Write(byteArray, 0, byteArray.Length)  
            ' Close the Stream object.  
            dataStream.Close()  
            ' Get the response.  
            Dim response As WebResponse = request.GetResponse()  
            ' Display the status.  
            Console.WriteLine(CType(response, HttpWebResponse).StatusDescription)  
            ' Get the stream containing content returned by the server.  
            dataStream = response.GetResponseStream()  
            ' Open the stream using a StreamReader for easy access.  
            Dim reader As New StreamReader(dataStream)  
            ' Read the content.  
            Dim responseFromServer As String = reader.ReadToEnd()  
            ' Display the content.  
            Console.WriteLine(responseFromServer)  
            ' Clean up the streams.  
            reader.Close()  
            dataStream.Close()  
            response.Close()  
        End Sub  
    End Class  
End Namespace  
```  
  
## <a name="see-also"></a><span data-ttu-id="dfe52-134">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="dfe52-134">See Also</span></span>  
 [<span data-ttu-id="dfe52-135">Tworzenie żądania internetowe</span><span class="sxs-lookup"><span data-stu-id="dfe52-135">Creating Internet Requests</span></span>](../../../docs/framework/network-programming/creating-internet-requests.md)  
 [<span data-ttu-id="dfe52-136">W sieci za pomocą strumieni</span><span class="sxs-lookup"><span data-stu-id="dfe52-136">Using Streams on the Network</span></span>](../../../docs/framework/network-programming/using-streams-on-the-network.md)  
 [<span data-ttu-id="dfe52-137">Dostęp do Internetu za pośrednictwem serwera Proxy</span><span class="sxs-lookup"><span data-stu-id="dfe52-137">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)  
 [<span data-ttu-id="dfe52-138">Żądanie danych</span><span class="sxs-lookup"><span data-stu-id="dfe52-138">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)  
 [<span data-ttu-id="dfe52-139">Porady: dane przy użyciu klasy WebRequest żądania</span><span class="sxs-lookup"><span data-stu-id="dfe52-139">How to: Request Data Using the WebRequest Class</span></span>](../../../docs/framework/network-programming/how-to-request-data-using-the-webrequest-class.md)