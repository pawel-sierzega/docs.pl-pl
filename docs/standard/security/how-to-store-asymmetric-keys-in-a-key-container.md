---
title: 'Porady: przechowywanie kluczy asymetrycznych w kontenerze kluczy'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cryptography [.NET Framework], asymmetric keys
- storing asymmetric keys
- keys, asymmetric
- encryption keys
- keys, storing in key containers
- asymmetric keys [.NET Framework]
- encryption [.NET Framework], asymmetric keys
- decryption keys
ms.assetid: 0dbcbd8d-0dcf-40e9-9f0c-e3f162d35ccc
caps.latest.revision: "20"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 475139230c4b58bc6dcc307bd99eeafdc3e89e53
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-store-asymmetric-keys-in-a-key-container"></a><span data-ttu-id="6c53e-102">Porady: przechowywanie kluczy asymetrycznych w kontenerze kluczy</span><span class="sxs-lookup"><span data-stu-id="6c53e-102">How to: Store Asymmetric Keys in a Key Container</span></span>
<span data-ttu-id="6c53e-103">Prywatne klucze asymetryczne nigdy nie powinny być przechowywane, dosłownego wyrażenia lub w postaci zwykłego tekstu na komputerze lokalnym.</span><span class="sxs-lookup"><span data-stu-id="6c53e-103">Asymmetric private keys should never be stored verbatim or in plain text on the local computer.</span></span> <span data-ttu-id="6c53e-104">Jeśli musisz przechować klucz prywatny, należy użyć kontenera kluczy.</span><span class="sxs-lookup"><span data-stu-id="6c53e-104">If you need to store a private key, you should use a key container.</span></span> <span data-ttu-id="6c53e-105">Aby uzyskać więcej informacji na kontenerów kluczy, zobacz [kontenery kluczy RSA na poziomie użytkownika i na poziomie maszyny opis](http://msdn.microsoft.com/library/9a179f38-8fb7-4442-964c-fb7b9f39f5b9).</span><span class="sxs-lookup"><span data-stu-id="6c53e-105">For more information on key containers, see [Understanding Machine-Level and User-Level RSA Key Containers](http://msdn.microsoft.com/library/9a179f38-8fb7-4442-964c-fb7b9f39f5b9).</span></span>  
  
### <a name="to-create-an-asymmetric-key-and-save-it-in-a-key-container"></a><span data-ttu-id="6c53e-106">Aby utworzyć klucz asymetryczny i zapisać ją w kontenerze kluczy</span><span class="sxs-lookup"><span data-stu-id="6c53e-106">To create an asymmetric key and save it in a key container</span></span>  
  
1.  <span data-ttu-id="6c53e-107">Utwórz nowe wystąpienie klasy <xref:System.Security.Cryptography.CspParameters> klasy i podaj nazwę, która ma zostać wywołana klucz kontenera, aby <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> pola.</span><span class="sxs-lookup"><span data-stu-id="6c53e-107">Create a new instance of a <xref:System.Security.Cryptography.CspParameters> class and pass the name that you want to call the key container to the <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> field.</span></span>  
  
2.  <span data-ttu-id="6c53e-108">Utwórz nowe wystąpienie klasy, która jest pochodną <xref:System.Security.Cryptography.AsymmetricAlgorithm> klasy (zazwyczaj **RSACryptoServiceProvider** lub **DSACryptoServiceProvider**), a następnie przekaż utworzonej wcześniej  **CspParameters** obiektu dla jego konstruktora.</span><span class="sxs-lookup"><span data-stu-id="6c53e-108">Create a new instance of a class that derives from the <xref:System.Security.Cryptography.AsymmetricAlgorithm> class (usually **RSACryptoServiceProvider** or **DSACryptoServiceProvider**) and pass the previously created **CspParameters** object to its constructor.</span></span>  
  
### <a name="to-delete-the-key-from-a-key-container"></a><span data-ttu-id="6c53e-109">Aby usunąć klucz z kontenera kluczy</span><span class="sxs-lookup"><span data-stu-id="6c53e-109">To delete the key from a key container</span></span>  
  
1.  <span data-ttu-id="6c53e-110">Utwórz nowe wystąpienie klasy **CspParameters** klasy i podaj nazwę, która ma zostać wywołana klucz kontenera, aby **CspParameters.KeyContainerName** pola.</span><span class="sxs-lookup"><span data-stu-id="6c53e-110">Create a new instance of a **CspParameters** class and pass the name that you want to call the key container to the **CspParameters.KeyContainerName** field.</span></span>  
  
2.  <span data-ttu-id="6c53e-111">Utwórz nowe wystąpienie klasy, która jest pochodną **AsymmetricAlgorithm** klasy (zazwyczaj **RSACryptoServiceProvider** lub **DSACryptoServiceProvider**) i przekaż wcześniej utworzony **CspParameters** obiektu dla jego konstruktora.</span><span class="sxs-lookup"><span data-stu-id="6c53e-111">Create a new instance of a class that derives from the **AsymmetricAlgorithm** class (usually **RSACryptoServiceProvider** or **DSACryptoServiceProvider**) and pass the previously created **CspParameters** object to its constructor.</span></span>  
  
3.  <span data-ttu-id="6c53e-112">Ustaw **PersistKeyInCSP** właściwości klasy, która jest pochodną **AsymmetricAlgorithm** do **false** (**False** w języku Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="6c53e-112">Set the **PersistKeyInCSP** property of the class that derives from **AsymmetricAlgorithm** to **false** (**False** in Visual Basic).</span></span>  
  
4.  <span data-ttu-id="6c53e-113">Wywołanie **wyczyść** metody klasy, która jest pochodną **AsymmetricAlgorithm**.</span><span class="sxs-lookup"><span data-stu-id="6c53e-113">Call the **Clear** method of the class that derives from **AsymmetricAlgorithm**.</span></span> <span data-ttu-id="6c53e-114">Ta metoda zwalnia wszystkie zasoby klasy i usuwa kontener kluczy.</span><span class="sxs-lookup"><span data-stu-id="6c53e-114">This method releases all resources of the class and clears the key container.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c53e-115">Przykład</span><span class="sxs-lookup"><span data-stu-id="6c53e-115">Example</span></span>  
 <span data-ttu-id="6c53e-116">W poniższym przykładzie pokazano, jak utworzyć klucza asymetrycznego, zapisz go w kontenerze kluczy pobrać klucza w późniejszym czasie i usunąć klucz z kontenera.</span><span class="sxs-lookup"><span data-stu-id="6c53e-116">The following example demonstrates how to create an asymmetric key, save it in a key container, retrieve the key at a later time, and delete the key from the container.</span></span>  
  
 <span data-ttu-id="6c53e-117">Zwróć uwagę, że kod w `GenKey_SaveInContainer` — metoda i `GetKeyFromContainer` metoda jest podobna.</span><span class="sxs-lookup"><span data-stu-id="6c53e-117">Notice that code in the `GenKey_SaveInContainer` method and the `GetKeyFromContainer` method is similar.</span></span>  <span data-ttu-id="6c53e-118">Po określeniu nazwę kontenera kluczy <xref:System.Security.Cryptography.CspParameters> obiektu i przekaż go do <xref:System.Security.Cryptography.AsymmetricAlgorithm> obiekt z <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp%2A> właściwości lub <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp%2A> właściwość jest ustawiona na wartość true, występuje poniższy.</span><span class="sxs-lookup"><span data-stu-id="6c53e-118">When you specify a key container name for a <xref:System.Security.Cryptography.CspParameters> object and pass it to an <xref:System.Security.Cryptography.AsymmetricAlgorithm> object with the <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp%2A> property or <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp%2A> property set to true, the following occurs.</span></span>  <span data-ttu-id="6c53e-119">Jeśli kontener kluczy o podanej nazwie nie istnieje, jest ono tworzone i klucz jest trwały.</span><span class="sxs-lookup"><span data-stu-id="6c53e-119">If a key container with the specified name does not exist, then one is created and the key is persisted.</span></span>  <span data-ttu-id="6c53e-120">Kontener kluczy o podanej nazwie istnieje, a następnie klawisz w kontenerze automatycznie jest ładowany do bieżącego <xref:System.Security.Cryptography.AsymmetricAlgorithm> obiektu.</span><span class="sxs-lookup"><span data-stu-id="6c53e-120">If a key container with the specified name does exist, then the key in the container is automatically loaded into the current <xref:System.Security.Cryptography.AsymmetricAlgorithm> object.</span></span>  <span data-ttu-id="6c53e-121">W związku z tym kod w `GenKey_SaveInContainer` metoda będzie się powtarzał klucza, ponieważ jest uruchamiany pierwszy podczas kod w `GetKeyFromContainer` metody ładuje klucza, ponieważ jest uruchamiany drugi.</span><span class="sxs-lookup"><span data-stu-id="6c53e-121">Therefore, the code in the `GenKey_SaveInContainer` method persists the key because it is run first, while the code in the `GetKeyFromContainer` method loads the key because it is run second.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Security.Cryptography  
 _  
  
Public Class StoreKey  
  
    Public Shared Sub Main()  
        Try  
            ' Create a key and save it in a container.  
            GenKey_SaveInContainer("MyKeyContainer")  
  
            ' Retrieve the key from the container.  
            GetKeyFromContainer("MyKeyContainer")  
  
            ' Delete the key from the container.  
            DeleteKeyFromContainer("MyKeyContainer")  
  
            ' Create a key and save it in a container.  
            GenKey_SaveInContainer("MyKeyContainer")  
  
            ' Delete the key from the container.  
            DeleteKeyFromContainer("MyKeyContainer")  
        Catch e As CryptographicException  
            Console.WriteLine(e.Message)  
        End Try  
    End Sub  
  
    Public Shared Sub GenKey_SaveInContainer(ByVal ContainerName As String)  
        ' Create the CspParameters object and set the key container   
        ' name used to store the RSA key pair.  
        Dim cp As New CspParameters()  
        cp.KeyContainerName = ContainerName  
  
        ' Create a new instance of RSACryptoServiceProvider that accesses  
        ' the key container MyKeyContainerName.  
        Dim rsa As New RSACryptoServiceProvider(cp)  
  
        ' Display the key information to the console.  
        Console.WriteLine("Key added to container:  {0}", rsa.ToXmlString(True))  
    End Sub  
  
    Public Shared Sub GetKeyFromContainer(ByVal ContainerName As String)  
        ' Create the CspParameters object and set the key container   
        '  name used to store the RSA key pair.  
        Dim cp As New CspParameters()  
        cp.KeyContainerName = ContainerName  
  
        ' Create a new instance of RSACryptoServiceProvider that accesses  
        ' the key container MyKeyContainerName.  
        Dim rsa As New RSACryptoServiceProvider(cp)  
  
        ' Display the key information to the console.  
        Console.WriteLine("Key retrieved from container : {0}", rsa.ToXmlString(True))  
    End Sub  
  
    Public Shared Sub DeleteKeyFromContainer(ByVal ContainerName As String)  
        ' Create the CspParameters object and set the key container   
        '  name used to store the RSA key pair.  
        Dim cp As New CspParameters()  
        cp.KeyContainerName = ContainerName  
  
        ' Create a new instance of RSACryptoServiceProvider that accesses  
        ' the key container.  
        Dim rsa As New RSACryptoServiceProvider(cp)  
  
        ' Delete the key entry in the container.  
        rsa.PersistKeyInCsp = False  
  
        ' Call Clear to release resources and delete the key from the container.  
        rsa.Clear()  
  
        Console.WriteLine("Key deleted.")  
    End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Security.Cryptography;  
  
public class StoreKey  
  
{  
    public static void Main()  
    {  
        try  
        {  
            // Create a key and save it in a container.  
            GenKey_SaveInContainer("MyKeyContainer");  
  
            // Retrieve the key from the container.  
            GetKeyFromContainer("MyKeyContainer");  
  
            // Delete the key from the container.  
            DeleteKeyFromContainer("MyKeyContainer");  
  
            // Create a key and save it in a container.  
            GenKey_SaveInContainer("MyKeyContainer");  
  
            // Delete the key from the container.  
            DeleteKeyFromContainer("MyKeyContainer");  
        }  
        catch(CryptographicException e)  
        {  
            Console.WriteLine(e.Message);  
        }  
  
    }  
  
    public static void GenKey_SaveInContainer(string ContainerName)  
    {  
        // Create the CspParameters object and set the key container   
        // name used to store the RSA key pair.  
        CspParameters cp = new CspParameters();  
        cp.KeyContainerName = ContainerName;  
  
        // Create a new instance of RSACryptoServiceProvider that accesses  
        // the key container MyKeyContainerName.  
        RSACryptoServiceProvider rsa = new RSACryptoServiceProvider(cp);  
  
        // Display the key information to the console.  
        Console.WriteLine("Key added to container: \n  {0}", rsa.ToXmlString(true));  
    }  
  
    public static void GetKeyFromContainer(string ContainerName)  
    {  
        // Create the CspParameters object and set the key container   
        // name used to store the RSA key pair.  
        CspParameters cp = new CspParameters();  
        cp.KeyContainerName = ContainerName;  
  
        // Create a new instance of RSACryptoServiceProvider that accesses  
        // the key container MyKeyContainerName.  
        RSACryptoServiceProvider rsa = new RSACryptoServiceProvider(cp);  
  
        // Display the key information to the console.  
        Console.WriteLine("Key retrieved from container : \n {0}", rsa.ToXmlString(true));  
    }  
  
    public static void DeleteKeyFromContainer(string ContainerName)  
    {  
        // Create the CspParameters object and set the key container   
        // name used to store the RSA key pair.  
        CspParameters cp = new CspParameters();  
        cp.KeyContainerName = ContainerName;  
  
        // Create a new instance of RSACryptoServiceProvider that accesses  
        // the key container.  
        RSACryptoServiceProvider rsa = new RSACryptoServiceProvider(cp);  
  
        // Delete the key entry in the container.  
        rsa.PersistKeyInCsp = false;  
  
        // Call Clear to release resources and delete the key from the container.  
        rsa.Clear();  
  
        Console.WriteLine("Key deleted.");  
    }  
}  
```  
  
```Output  
Key added to container:  
<RSAKeyValue> Key Information A</RSAKeyValue>  
Key retrieved from container :  
<RSAKeyValue> Key Information A</RSAKeyValue>  
Key deleted.  
Key added to container:  
<RSAKeyValue> Key Information B</RSAKeyValue>  
Key deleted.  
```  
  
## <a name="see-also"></a><span data-ttu-id="6c53e-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="6c53e-122">See Also</span></span>  
 [<span data-ttu-id="6c53e-123">Generowanie kluczy szyfrowania i odszyfrowywania</span><span class="sxs-lookup"><span data-stu-id="6c53e-123">Generating Keys for Encryption and Decryption</span></span>](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md)  
 [<span data-ttu-id="6c53e-124">Szyfrowanie danych</span><span class="sxs-lookup"><span data-stu-id="6c53e-124">Encrypting Data</span></span>](../../../docs/standard/security/encrypting-data.md)  
 [<span data-ttu-id="6c53e-125">Odszyfrowywanie danych</span><span class="sxs-lookup"><span data-stu-id="6c53e-125">Decrypting Data</span></span>](../../../docs/standard/security/decrypting-data.md)  
 [<span data-ttu-id="6c53e-126">Usługi kryptograficzne</span><span class="sxs-lookup"><span data-stu-id="6c53e-126">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)