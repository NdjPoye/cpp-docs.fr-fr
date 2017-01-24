---
title: "Utilisation de l&#39;interop&#233;rabilit&#233; C++ (PInvoke implicite) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".NET (C++), portage C++ natif vers"
  - "types blittables (C++)"
  - "interopérabilité C++ COM"
  - "interopérabilité C++"
  - "C++, interopérabilité"
  - "interfaces COM (C++)"
  - "marshaling de données (C++), fonctionnalités d'interopérabilité C++"
  - "exemples (C++), interopérabilité"
  - "appel de code non managé implicite"
  - "Interop (C++), fonctionnalités"
  - "interopérabilité (C++)"
  - "interopérabilité (C++), PInvoke implicite"
  - "marshaling (C++), fonctionnalités d'interopérabilité C++"
  - "appel de code non managé (C++), exemples"
  - "appel de code non managé (C++), implicites"
  - "porter (C++), C++ natif vers .NET"
  - "types (C++), blittables"
ms.assetid: 5f710bf1-88ae-4c4e-8326-b3f0b7c4c68a
caps.latest.revision: 27
caps.handback.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Utilisation de l&#39;interop&#233;rabilit&#233; C++ (PInvoke implicite)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Contrairement à d'autres langages .NET, Visual C\+\+ offre une prise en charge de l'interopérabilité qui autorise la présence de code managé et non managé dans la même application et également dans le même fichier \(avec les pragmas [managé, non managé](../preprocessor/managed-unmanaged.md)\).  Cela permet aux développeurs Visual C\+\+ d'intégrer des fonctionnalités .NET dans des applications Visual C\+\+ existantes sans perturber le reste de l'application.  
  
 Vous pouvez également appeler des fonctions non managées à partir d'un module \(compiland\) managé à l'aide de [dllexport, dllimport](../cpp/dllexport-dllimport.md).  
  
 Un PInvoke implicite peut être utile si vous n'avez pas besoin de spécifier de quelle manière les paramètres de fonction doivent être marshalés, ou l'un des autres détails pouvant être spécifiés lors d'un appel explicite à DllImportAttribute.  
  
 Visual C\+\+ offre aux fonctions managées et non managées deux moyens d'interagir :  
  
-   [Utilisation d'un PInvoke explicite en C\+\+ \(attribut DllImport\)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)  
  
 Un PInvoke explicite est pris en charge par le .NET Framework et est disponible dans la plupart des langages .NET.  Cependant, comme son nom l'indique, C\+\+ Interop est spécifique à Visual C\+\+.  
  
## C\+\+ Interop  
 C\+\+ Interop est recommandé par rapport au PInvoke explicite, car il assure une meilleure sécurité de type, est généralement moins fastidieux à implémenter, est plus indulgent en cas de modification de l'API non managée et autorise des améliorations des performances qui n'étaient pas possibles avec un PInvoke explicite.  Toutefois, C\+\+ Interop ne peut pas être utilisé si le code source non managé n'est pas disponible ou en cas de compilation avec **\/clr:safe** \(consultez [Code pur et vérifiable](../dotnet/pure-and-verifiable-code-cpp-cli.md) pour plus d'informations\).  
  
## C\+\+ COM Interop  
 Les fonctionnalités d'interopérabilité prises en charge par Visual C\+\+ procurent un avantage particulier par rapport aux autres langages .NET en termes d'interaction avec des composants COM.  Plutôt que d'être limité aux restrictions du .NET Framework [Tlbimp.exe \(Type Library Importer\)](../Topic/Tlbimp.exe%20\(Type%20Library%20Importer\).md), telles que la prise en charge limitée des types de données et l'exposition obligatoire de chaque membre de chaque interface COM, C\+\+ Interop autorise l'accès à volonté aux composants COM et n'exige pas d'assemblys d'interopérabilité distincts.  Pour plus d'informations, consultez [Using COM from .NET](http://msdn.microsoft.com/fr-fr/03976661-6278-4227-a6c1-3b3315502c15).  
  
## Types blittables  
 Pour les API non managées qui utilisent des types intrinsèques simples \(consultez [Blittable and Non\-Blittable Types](../Topic/Blittable%20and%20Non-Blittable%20Types.md)\), aucun codage spécial n'est requis, car ces types de données possèdent la même représentation en mémoire, mais les types de données plus complexes requièrent le marshaling explicite de données.  Pour obtenir un exemple, consultez [Comment : appeler des DLL natives à partir du code managé à l'aide de PInvoke](../dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke.md).  
  
## Exemple  
  
```  
// vcmcppv2_impl_dllimp.cpp  
// compile with: /clr:pure user32.lib  
using namespace System::Runtime::InteropServices;  
  
// Implicit DLLImport specifying calling convention  
extern "C" int __stdcall MessageBeep(int);  
  
// explicit DLLImport needed here to use P/Invoke marshalling because  
// System::String ^ is not the type of the first parameter to printf  
[DllImport("msvcrt.dll", EntryPoint = "printf", CallingConvention = CallingConvention::Cdecl,  CharSet = CharSet::Ansi)]  
// or just  
// [DllImport("msvcrt.dll")]  
int printf(System::String ^, ...);   
  
int main() {  
   // (string literals are System::String by default)  
   printf("Begin beep\n");  
   MessageBeep(100000);  
   printf("Done\n");  
}  
```  
  
  **Démarrez le signal sonore**  
**Terminé**   
## Dans cette section  
  
-   [Comment : marshaler des chaînes ANSI à l'aide de l'interopérabilité C\+\+](../dotnet/how-to-marshal-ansi-strings-using-cpp-interop.md)  
  
-   [Comment : marshaler des chaînes Unicode à l'aide de l'interopérabilité C\+\+](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)  
  
-   [Comment : marshaler des chaînes COM à l'aide de l'interopérabilité C\+\+](../dotnet/how-to-marshal-com-strings-using-cpp-interop.md)  
  
-   [Comment : marshaler des structures à l'aide de l'interopérabilité C\+\+](../dotnet/how-to-marshal-structures-using-cpp-interop.md)  
  
-   [Comment : marshaler des tableaux à l'aide de l'interopérabilité C\+\+](../dotnet/how-to-marshal-arrays-using-cpp-interop.md)  
  
-   [Comment : marshaler des rappels et des délégués à l'aide de l'interopérabilité C\+\+](../dotnet/how-to-marshal-callbacks-and-delegates-by-using-cpp-interop.md)  
  
-   [Comment : marshaler des pointeurs incorporés à l'aide de l'interopérabilité C\+\+](../dotnet/how-to-marshal-embedded-pointers-using-cpp-interop.md)  
  
-   [Comment : accéder aux caractères d'un System::String](../dotnet/how-to-access-characters-in-a-system-string.md)  
  
-   [Comment : convertir la chaîne char \* en tableau System::Byte](../dotnet/how-to-convert-char-star-string-to-system-byte-array.md)  
  
-   [Comment : convertir System::String en wchar\_t \* ou char\*](../dotnet/how-to-convert-system-string-to-wchar-t-star-or-char-star.md)  
  
-   [Comment : convertir System::String en chaîne standard](../dotnet/how-to-convert-system-string-to-standard-string.md)  
  
-   [Comment : convertir une chaîne standard en System::String](../dotnet/how-to-convert-standard-string-to-system-string.md)  
  
-   [Comment : obtenir un pointeur vers un tableau d'octets](../dotnet/how-to-obtain-a-pointer-to-byte-array.md)  
  
-   [Comment : charger des ressources non managées dans un tableau d'octets](../dotnet/how-to-load-unmanaged-resources-into-a-byte-array.md)  
  
-   [Comment : modifier la classe de référence dans une fonction native](../dotnet/how-to-modify-reference-class-in-a-native-function.md)  
  
-   [Comment : déterminer si une image est native ou CLR](../dotnet/how-to-determine-if-an-image-is-native-or-clr.md)  
  
-   [Comment : ajouter une DLL native au Global Assembly Cache](../dotnet/how-to-add-native-dll-to-global-assembly-cache.md)  
  
-   [Comment : stocker une référence à un type valeur dans un type natif](../dotnet/how-to-hold-reference-to-value-type-in-native-type.md)  
  
-   [Comment : stocker la référence d'un objet dans une mémoire non managée](../dotnet/how-to-hold-object-reference-in-unmanaged-memory.md)  
  
-   [Comment : détecter une compilation \/clr](../dotnet/how-to-detect-clr-compilation.md)  
  
-   [Comment : procéder à une conversion entre System::Guid et \_GUID](../dotnet/how-to-convert-between-system-guid-and-guid.md)  
  
-   [Comment : spécifier un paramètre Out](../dotnet/how-to-specify-an-out-parameter.md)  
  
-   [Comment : utiliser un type natif dans une compilation \/clr](../dotnet/how-to-use-a-native-type-in-a-clr-compilation.md)  
  
-   [Comment : déclarer des handles dans les types natifs](../dotnet/how-to-declare-handles-in-native-types.md)  
  
-   [Comment : inclure une classe native dans un wrapper pour une utilisation par C\#](../dotnet/how-to-wrap-native-class-for-use-by-csharp.md)  
  
 Pour plus d'informations sur l'utilisation de délégués dans un scénario d'interopérabilité, consultez [délégué](../windows/delegate-cpp-component-extensions.md).  
  
## Voir aussi  
 [Appel à des fonctions natives à partir de code managé](../dotnet/calling-native-functions-from-managed-code.md)