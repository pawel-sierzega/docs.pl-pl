---
title: "Klasa XMLSerializer — przykład"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7d134453-9a35-4202-ba77-9ca3a65babc3
caps.latest.revision: "23"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: dc224de36f607bd1f15e10987c68b14a69e992b5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="xmlserializer-sample"></a><span data-ttu-id="032f2-102">Klasa XMLSerializer — przykład</span><span class="sxs-lookup"><span data-stu-id="032f2-102">XMLSerializer Sample</span></span>
<span data-ttu-id="032f2-103">W tym przykładzie pokazano, jak serializacji i deserializacji typy, które są zgodne z <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="032f2-103">This sample demonstrates how to serialize and deserialize types that are compatible with the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="032f2-104">Wartość domyślna [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] element formatujący <xref:System.Runtime.Serialization.DataContractSerializer> klasy.</span><span class="sxs-lookup"><span data-stu-id="032f2-104">The default [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] formatter is the <xref:System.Runtime.Serialization.DataContractSerializer> class.</span></span> <span data-ttu-id="032f2-105"><xref:System.Xml.Serialization.XmlSerializer> Klasa może być używana w celu serializacji i deserializacji typy kiedy <xref:System.Runtime.Serialization.DataContractSerializer> klasa nie może być używana.</span><span class="sxs-lookup"><span data-stu-id="032f2-105">The <xref:System.Xml.Serialization.XmlSerializer> class can be used to serialize and deserialize types when the <xref:System.Runtime.Serialization.DataContractSerializer> class cannot be used.</span></span> <span data-ttu-id="032f2-106">To sytuacja często ścisła kontrola nad XML jest wymagany — na przykład, jeśli element danych musi być atrybut XML i nie jest elementem XML.</span><span class="sxs-lookup"><span data-stu-id="032f2-106">This is often the case when precise control over the XML is required - for example, if a piece of data must be an XML attribute and not an XML element.</span></span> <span data-ttu-id="032f2-107">Ponadto <xref:System.Xml.Serialization.XmlSerializer> często automatycznie pobiera wybierany w przypadku tworzenia klientów z systemem innym niż[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usług.</span><span class="sxs-lookup"><span data-stu-id="032f2-107">Also, the <xref:System.Xml.Serialization.XmlSerializer> often gets automatically selected when creating clients for non-[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services.</span></span>  
  
 <span data-ttu-id="032f2-108">W tym przykładzie klient jest aplikacji konsoli (.exe), a usługa jest obsługiwana przez Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="032f2-108">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="032f2-109">Procedury i kompilacji instrukcje dotyczące instalacji dla tego przykładu znajdują się na końcu tego tematu.</span><span class="sxs-lookup"><span data-stu-id="032f2-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="032f2-110"><xref:System.ServiceModel.ServiceContractAttribute> i <xref:System.ServiceModel.XmlSerializerFormatAttribute> należy zastosować do interfejsu, jak pokazano w poniższym kodzie próbki.</span><span class="sxs-lookup"><span data-stu-id="032f2-110">The <xref:System.ServiceModel.ServiceContractAttribute> and <xref:System.ServiceModel.XmlSerializerFormatAttribute> must be applied to the interface as shown in the following sample code.</span></span>  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples"), XmlSerializerFormat]  
public interface IXmlSerializerCalculator  
{  
    [OperationContract]  
    ComplexNumber Add(ComplexNumber n1, ComplexNumber n2);  
    [OperationContract]  
    ComplexNumber Subtract(ComplexNumber n1, ComplexNumber n2);  
    [OperationContract]  
    ComplexNumber Multiply(ComplexNumber n1, ComplexNumber n2);  
    [OperationContract]  
    ComplexNumber Divide(ComplexNumber n1, ComplexNumber n2);  
}  
```  
  
 <span data-ttu-id="032f2-111">Publiczne elementy członkowskie `ComplexNumber` klasy są serializowane przez <xref:System.Xml.Serialization.XmlSerializer> jako atrybuty XML.</span><span class="sxs-lookup"><span data-stu-id="032f2-111">The public members of `ComplexNumber` class are serialized by <xref:System.Xml.Serialization.XmlSerializer> as XML attributes.</span></span> <span data-ttu-id="032f2-112"><xref:System.Runtime.Serialization.DataContractSerializer> Nie można użyć do utworzenia tego rodzaju wystąpienie XML.</span><span class="sxs-lookup"><span data-stu-id="032f2-112">The <xref:System.Runtime.Serialization.DataContractSerializer> cannot be used to create this kind of XML instance.</span></span>  
  
```  
public class ComplexNumber  
{  
    private double real;  
    private double imaginary;  
  
    [XmlAttribute]  
    public double Real  
    {  
        get { return real; }  
        set { real = value; }  
    }  
  
    [XmlAttribute]  
    public double Imaginary  
    {  
        get { return imaginary; }  
        set { imaginary = value; }  
    }  
  
    public ComplexNumber(double real, double imaginary)  
    {  
        this.Real = real;  
        this.Imaginary = imaginary;  
    }  
    public ComplexNumber()  
    {  
        this.Real = 0;  
        this.Imaginary = 0;  
    }  
  
}  
```  
  
 <span data-ttu-id="032f2-113">Implementacja usługi oblicza i zwraca wynik w odpowiednich — akceptowanie i zwracanie wartości z `ComplexNumber` typu.</span><span class="sxs-lookup"><span data-stu-id="032f2-113">The service implementation calculates and returns the appropriate result—accepting and returning values of the `ComplexNumber` type.</span></span>  
  
```  
public class XmlSerializerCalculatorService : IXmlSerializerCalculator  
{  
    public ComplexNumber Add(ComplexNumber n1, ComplexNumber n2)  
    {  
        return new ComplexNumber(n1.Real + n2.Real, n1.Imaginary +  
                                                      n2.Imaginary);  
    }  
    …  
}  
```  
  
 <span data-ttu-id="032f2-114">Implementacja klienta używa także liczby złożone.</span><span class="sxs-lookup"><span data-stu-id="032f2-114">The client implementation also uses complex numbers.</span></span> <span data-ttu-id="032f2-115">Zarówno kontraktu usługi, jak i typy danych są zdefiniowane w pliku źródłowym generatedClient.cs, który został wygenerowany przez [narzędzie narzędzia metadanych elementu ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) z metadanych usługi.</span><span class="sxs-lookup"><span data-stu-id="032f2-115">Both the service contract and the data types are defined in the generatedClient.cs source file, which was generated by the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) from service metadata.</span></span> <span data-ttu-id="032f2-116">Svcutil.exe może wykryć, gdy kontrakt nie jest możliwy do serializacji przez <xref:System.Runtime.Serialization.DataContractSerializer> i powraca do emitowania `XmlSerializable` typy w tym przypadku.</span><span class="sxs-lookup"><span data-stu-id="032f2-116">Svcutil.exe can detect when a contract is not serializable by the <xref:System.Runtime.Serialization.DataContractSerializer> and reverts to emitting `XmlSerializable` types in this case.</span></span> <span data-ttu-id="032f2-117">Aby wymusić użycie <xref:System.Xml.Serialization.XmlSerializer>, opcja polecenia /serializer:XmlSerializer (Użyj elementu XmlSerializer) można przekazać do narzędzia Svcutil.exe.</span><span class="sxs-lookup"><span data-stu-id="032f2-117">If you want to force the use of the <xref:System.Xml.Serialization.XmlSerializer>, you can pass the /serializer:XmlSerializer (use XmlSerializer) command option to the Svcutil.exe tool.</span></span>  
  
```  
// Create a client.  
XmlSerializerCalculatorClient client = new  
                         XmlSerializerCalculatorClient();  
  
// Call the Add service operation.  
ComplexNumber value1 = new ComplexNumber();  
value1.Real = 1;  
value1.Imaginary = 2;  
ComplexNumber value2 = new ComplexNumber();  
value2.Real = 3;  
value2.Imaginary = 4;  
ComplexNumber result = client.Add(value1, value2);  
Console.WriteLine("Add({0} + {1}i, {2} + {3}i) = {4} + {5}i",  
    value1.Real, value1.Imaginary, value2.Real, value2.Imaginary,   
    result.Real, result.Imaginary);  
    …  
}  
```  
  
 <span data-ttu-id="032f2-118">Po uruchomieniu próbki operację żądania i odpowiedzi są wyświetlane w oknie konsoli klienta.</span><span class="sxs-lookup"><span data-stu-id="032f2-118">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="032f2-119">Naciśnij klawisz ENTER w oknie klienta, aby zamknąć klienta.</span><span class="sxs-lookup"><span data-stu-id="032f2-119">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Add(1 + 2i, 3 + 4i) = 4 + 6i  
Subtract(1 + 2i, 3 + 4i) = -2 + -2i  
Multiply(2 + 3i, 4 + 7i) = -13 + 26i  
Divide(3 + 7i, 5 + -2i) = 0.0344827586206897 + 1.41379310344828i  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="032f2-120">Aby skonfigurować, kompilacji, a następnie uruchom próbki</span><span class="sxs-lookup"><span data-stu-id="032f2-120">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="032f2-121">Upewnij się, że wykonano procedurę [jednorazowego procedurę instalacji dla przykładów Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="032f2-121">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="032f2-122">Tworzenie wersji języka C# lub Visual Basic .NET rozwiązania, postępuj zgodnie z instrukcjami [kompilowanie przykładów programu Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="032f2-122">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="032f2-123">Aby uruchomić przykładowy w konfiguracji pojedynczej lub między komputerami, postępuj zgodnie z instrukcjami w [uruchamiania przykładów Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="032f2-123">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="032f2-124">Próbki mogą być zainstalowane na tym komputerze.</span><span class="sxs-lookup"><span data-stu-id="032f2-124">The samples may already be installed on your machine.</span></span> <span data-ttu-id="032f2-125">Przed kontynuowaniem sprawdź, czy są dostępne dla następującego katalogu (ustawienie domyślne).</span><span class="sxs-lookup"><span data-stu-id="032f2-125">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="032f2-126">Jeśli ten katalog nie istnieje, przejdź do [Windows Communication Foundation (WCF) i Windows Workflow Foundation (WF) przykłady dla programu .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) pobrać wszystkie [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] i [!INCLUDE[wf1](../../../../includes/wf1-md.md)] próbek.</span><span class="sxs-lookup"><span data-stu-id="032f2-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="032f2-127">W tym przykładzie znajduje się w następującym katalogu.</span><span class="sxs-lookup"><span data-stu-id="032f2-127">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\Interop\XmlSerializer`  
  
## <a name="see-also"></a><span data-ttu-id="032f2-128">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="032f2-128">See Also</span></span>