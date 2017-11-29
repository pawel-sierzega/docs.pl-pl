---
title: Bezpieczne przechowywanie kluczy tajnych aplikacji podczas tworzenia
description: "Architektura Mikrousług .NET dla aplikacji .NET konteneryzowanych | Bezpieczne przechowywanie kluczy tajnych aplikacji podczas tworzenia"
keywords: "Docker, Mikrousług, ASP.NET, kontenera"
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: f1b8b257a3e677c7e665e1d394a8adf7e651bec2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="storing-application-secrets-safely-during-development"></a><span data-ttu-id="41f0c-104">Bezpieczne przechowywanie kluczy tajnych aplikacji podczas tworzenia</span><span class="sxs-lookup"><span data-stu-id="41f0c-104">Storing application secrets safely during development</span></span>

<span data-ttu-id="41f0c-105">Aby połączyć się z chronionych zasobów i innych usług, aplikacji platformy ASP.NET Core zwykle muszą używać parametrów połączenia, hasła lub innych poświadczeń, które zawierają poufne informacje.</span><span class="sxs-lookup"><span data-stu-id="41f0c-105">To connect with protected resources and other services, ASP.NET Core applications typically need to use connection strings, passwords, or other credentials that contain sensitive information.</span></span> <span data-ttu-id="41f0c-106">Te elementy poufnych informacji są nazywane *kluczy tajnych*.</span><span class="sxs-lookup"><span data-stu-id="41f0c-106">These sensitive pieces of information are called *secrets*.</span></span> <span data-ttu-id="41f0c-107">Jest to najlepsze rozwiązanie, aby nie dołączać kluczy tajnych w kodzie źródłowym i na pewno nie do przechowywania kluczy tajnych w kontroli źródła.</span><span class="sxs-lookup"><span data-stu-id="41f0c-107">It is a best practice to not include secrets in source code and certainly not to store secrets in source control.</span></span> <span data-ttu-id="41f0c-108">Zamiast tego należy używać model konfiguracji platformy ASP.NET Core odczytu kluczy tajnych z bardziej bezpiecznych lokalizacjach.</span><span class="sxs-lookup"><span data-stu-id="41f0c-108">Instead, you should use the ASP.NET Core configuration model to read the secrets from more secure locations.</span></span>

<span data-ttu-id="41f0c-109">Rozdziel hasła podczas uzyskiwania dostępu do rozwoju i przemieszczania są używane na potrzeby uzyskiwania dostępu do zasobów w środowisku produkcyjnym, ponieważ inne osoby wymaga dostępu do tych kluczy tajnych różne zestawy zasobów.</span><span class="sxs-lookup"><span data-stu-id="41f0c-109">You should separate the secrets for accessing development and staging resources from those used for accessing production resources, because different individuals will need access to those different sets of secrets.</span></span> <span data-ttu-id="41f0c-110">Do przechowywania kluczy tajnych używanych podczas tworzenia, wspólnego podejścia są przechowywanie kluczy tajnych w zmiennych środowiskowych lub za pomocą narzędzia platformy ASP.NET Core klucz tajny menedżera.</span><span class="sxs-lookup"><span data-stu-id="41f0c-110">To store secrets used during development, common approaches are to either store secrets in environment variables or by using the ASP.NET Core Secret Manager tool.</span></span> <span data-ttu-id="41f0c-111">Dla bardziej bezpieczny magazyn w środowiskach produkcyjnych mikrousług można przechowywać kluczy tajnych w usłudze Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="41f0c-111">For more secure storage in production environments, microservices can store secrets in an Azure Key Vault.</span></span>

## <a name="storing-secrets-in-environment-variables"></a><span data-ttu-id="41f0c-112">Przechowywanie kluczy tajnych w zmiennych środowiskowych</span><span class="sxs-lookup"><span data-stu-id="41f0c-112">Storing secrets in environment variables</span></span>

<span data-ttu-id="41f0c-113">Jest jednym ze sposobów przechowywać klucze tajne poza kodu źródłowego dla deweloperów można ustawić na podstawie ciągu kluczy tajnych jako [zmiennych środowiskowych](https://docs.microsoft.com/aspnet/core/security/app-secrets#environment-variables) na swoich komputerach programowanie.</span><span class="sxs-lookup"><span data-stu-id="41f0c-113">One way to keep secrets out of source code is for developers to set string-based secrets as [environment variables](https://docs.microsoft.com/aspnet/core/security/app-secrets#environment-variables) on their development machines.</span></span> <span data-ttu-id="41f0c-114">Użycie zmiennych środowiskowych do przechowywania kluczy tajnych nazwami hierarchicznych (te zagnieżdżona w sekcji konfiguracji), Utwórz nazwę zmiennych środowiskowych, która zawiera hierarchię Pełna nazwa klucza tajnego, rozdzielone dwukropkiem (:).</span><span class="sxs-lookup"><span data-stu-id="41f0c-114">When you use environment variables to store secrets with hierarchical names (those nested in configuration sections), create a name for the environment variables that includes the full hierarchy of the secret’s name, delimited with colons (:).</span></span>

<span data-ttu-id="41f0c-115">Na przykład ustawienie zmiennej środowiskowej rejestrowania: LogLevel:Default debugowania będzie odpowiednikiem wartości konfiguracji z następującego pliku JSON:</span><span class="sxs-lookup"><span data-stu-id="41f0c-115">For example, setting an environment variable Logging:LogLevel:Default to Debug would be equivalent to a configuration value from the following JSON file:</span></span>

```json
{
    "Logging": {
        "LogLevel": {
            "Default": "Debug"
        }
    }
}
```

<span data-ttu-id="41f0c-116">Aby uzyskać dostęp do tych wartości w zmiennych środowiskowych, aplikacja tylko musi wywołać jej ConfigurationBuilder AddEnvironmentVariables podczas konstruowania obiektu IConfigurationRoot.</span><span class="sxs-lookup"><span data-stu-id="41f0c-116">To access these values from environment variables, the application just needs to call AddEnvironmentVariables on its ConfigurationBuilder when constructing an IConfigurationRoot object.</span></span>

<span data-ttu-id="41f0c-117">Należy pamiętać, że zmienne środowiskowe zazwyczaj są przechowywane jako zwykły tekst, tak więc w przypadku naruszenia zabezpieczeń komputera lub proces o zmiennych środowiskowych, wartości zmiennych środowiskowych będzie widoczna.</span><span class="sxs-lookup"><span data-stu-id="41f0c-117">Note that environment variables are generally stored as plain text, so if the machine or process with the environment variables is compromised, the environment variable values will be visible.</span></span>

## <a name="storing-secrets-using-the-aspnet-core-secret-manager"></a><span data-ttu-id="41f0c-118">Przechowywanie kluczy tajnych za pomocą Menedżera platformy ASP.NET Core klucz tajny</span><span class="sxs-lookup"><span data-stu-id="41f0c-118">Storing secrets using the ASP.NET Core Secret Manager</span></span>

<span data-ttu-id="41f0c-119">Platformy ASP.NET Core [Manager klucz tajny](https://docs.microsoft.com/aspnet/core/security/app-secrets#secret-manager) narzędzia zawiera inną metodą przechowywanie kluczy tajnych z kodu źródłowego.</span><span class="sxs-lookup"><span data-stu-id="41f0c-119">The ASP.NET Core [Secret Manager](https://docs.microsoft.com/aspnet/core/security/app-secrets#secret-manager) tool provides another method of keeping secrets out of source code.</span></span> <span data-ttu-id="41f0c-120">Aby użyć narzędzia menedżera klucz tajny, obejmują informacje dotyczące narzędzi (DotNetCliToolReference) do pakietu Microsoft.Extensions.SecretManager.Tools w pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="41f0c-120">To use the Secret Manager tool, include a tools reference (DotNetCliToolReference) to the Microsoft.Extensions.SecretManager.Tools package in your project file.</span></span> <span data-ttu-id="41f0c-121">Po tym zależności i zostało przywrócone, polecenie kluczy tajnych użytkownika dotnet może służyć do wartości kluczy tajnych w wierszu polecenia.</span><span class="sxs-lookup"><span data-stu-id="41f0c-121">Once that dependency is present and has been restored, the dotnet user-secrets command can be used to set the value of secrets from the command line.</span></span> <span data-ttu-id="41f0c-122">Te klucze tajne będą przechowywane w pliku JSON w katalogu profilu użytkownika (Szczegóły różnią się zależnie od systemu operacyjnego), od kodu źródłowego.</span><span class="sxs-lookup"><span data-stu-id="41f0c-122">These secrets will be stored in a JSON file in the user’s profile directory (details vary by OS), away from source code.</span></span>

<span data-ttu-id="41f0c-123">Klucze tajne ustawione przez narzędzie Menedżer klucz tajny są zorganizowane według właściwości UserSecretsId projektu, która używa kluczy tajnych.</span><span class="sxs-lookup"><span data-stu-id="41f0c-123">Secrets set by the Secret Manager tool are organized by the UserSecretsId property of the project that is using the secrets.</span></span> <span data-ttu-id="41f0c-124">W związku z tym należy ustaw właściwość UserSecretsId w pliku projektu (jak pokazano w poniższy fragment).</span><span class="sxs-lookup"><span data-stu-id="41f0c-124">Therefore, you must be sure to set the UserSecretsId property in your project file (as shown in the snippet below).</span></span> <span data-ttu-id="41f0c-125">Rzeczywisty ciąg używany jako identyfikator nie jest ważne, ile jest unikatowa w projekcie.</span><span class="sxs-lookup"><span data-stu-id="41f0c-125">The actual string used as the ID is not important as long as it is unique in the project.</span></span>

```xml
<PropertyGroup>
    <UserSecretsId>UniqueIdentifyingString</UserSecretsId>
</PropertyGroup>
```

<span data-ttu-id="41f0c-126">Przy użyciu kluczy tajnych przechowywanych w aplikacji przy użyciu Menedżera klucz tajny odbywa się przez wywołanie metody AddUserSecrets&lt;T&gt; w wystąpieniu ConfigurationBuilder, aby uwzględnić klucze tajne dla aplikacji w swojej konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="41f0c-126">Using secrets stored with Secret Manager in an application is accomplished by calling AddUserSecrets&lt;T&gt; on the ConfigurationBuilder instance to include secrets for the application in its configuration.</span></span> <span data-ttu-id="41f0c-127">Parametr generyczny T powinien być typem z zestawu, które zostało zastosowane UserSecretId.</span><span class="sxs-lookup"><span data-stu-id="41f0c-127">The generic parameter T should be a type from the assembly that the UserSecretId was applied to.</span></span> <span data-ttu-id="41f0c-128">Zazwyczaj przy użyciu AddUserSecrets&lt;uruchamiania&gt; funkcjonuje prawidłowo.</span><span class="sxs-lookup"><span data-stu-id="41f0c-128">Usually using AddUserSecrets&lt;Startup&gt; is fine.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="41f0c-129">[Poprzednie] (autoryzacji net mikrousług web-applications.md) [dalej] (azure-key magazynu chroni — secrets.md)</span><span class="sxs-lookup"><span data-stu-id="41f0c-129">[Previous] (authorization-net-microservices-web-applications.md) [Next] (azure-key-vault-protects-secrets.md)</span></span>