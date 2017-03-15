---
title: "Vue d&#39;ensemble du marshaling dans C++ | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "marshaling"
  - "marshalling"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bibliothèque de prise en charge C++, marshaling"
  - "marshaling, à propos du marshaling"
  - "Visual C++, marshaling"
ms.assetid: 997dd4bc-5f98-408f-b890-f35de9ce3bb8
caps.latest.revision: 16
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Vue d&#39;ensemble du marshaling dans C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

En mode mixte, vous devez parfois marshaler vos données entre les types natifs et managés.  [!INCLUDE[vs_orcas_long](../atl/reference/includes/vs_orcas_long_md.md)] a introduit la bibliothèque de marshaling pour vous aider à marshaler et convertir des données de manière simple.  
  
 Il est possible d'utiliser la bibliothèque de marshaling avec ou sans un [marshal\_context, classe](../dotnet/marshal-context-class.md).  Certaines conversions requièrent un contexte.  D'autres conversions peuvent être implémentées en utilisant la fonction [marshal\_as](../dotnet/marshal-as.md).  Le tableau suivant répertorie les conversions actuelles prises en charge, suivant qu'elles aient besoin d'un contexte, et suivant le fichier marshaler que vous devez inclure :  
  
|Depuis le type|Jusqu'au type|Méthode de marshaling|Inclut le fichier|  
|--------------------|-------------------|---------------------------|-----------------------|  
|System::String^|const char \*|marshal\_context|marshal.h|  
|const char \*|System::String^|marshal\_as|marshal.h|  
|char\*|System::String^|marshal\_as|marshal.h|  
|System::String^|const wchar\_t\*|marshal\_context|marshal.h|  
|const wchar\_t \*|System::String^|marshal\_as|marshal.h|  
|wchar\_t\*|System::String^|marshal\_as|marshal.h|  
|System::IntPtr|HANDLE|marshal\_as|marshal\_windows.h|  
|HANDLE|System::IntPtr|marshal\_as|marshal\_windows.h|  
|System::String^|BSTR|marshal\_context|marshal\_windows.h|  
|BSTR|System::String^|marshal\_as|marshal.h|  
|System::String^|bstr\_t|marshal\_as|marshal\_windows.h|  
|bstr\_t|System::String^|marshal\_as|marshal\_windows.h|  
|System::String^|std::string|marshal\_as|marshal\_cppstd.h|  
|std::string|System::String^|marshal\_as|marshal\_cppstd.h|  
|System::String^|std::wstring|marshal\_as|marshal\_cppstd.h|  
|std::wstring|System::String^|marshal\_as|marshal\_cppstd.h|  
|System::String^|CStringT\<char\>|marshal\_as|marshal\_atl.h|  
|CStringT\<char\>|System::String^|marshal\_as|marshal\_atl.h|  
|System::String^|CStringT\<wchar\_t\>|marshal\_as|marshal\_atl.h|  
|CStringT\<wchar\_t\>|System::String^|marshal\_as|marshal\_atl.h|  
|System::String^|CComBSTR|marshal\_as|marshal\_atl.h|  
|CComBSTR|System::String^|marshal\_as|marshal\_atl.h|  
  
 Le marshaling requiert un contexte uniquement lorsque vous marshalez depuis des types de données managés et que le type de données natif auquel vous le convertissez n'a pas de destructeur pour un nettoyage automatique.  Le contexte de marshaling détruit le type de données natif alloué dans son destructeur.  Par conséquent, les conversions qui requièrent un contexte seront seulement valides jusqu'à ce que le contexte soit supprimé.  Pour enregistrer des valeurs marshalées, vous devez copier les valeurs dans vos propres variables.  
  
> [!NOTE]
>  Si vous avez incorporé des `NULL`s dans votre chaîne, le résultat du marshaling de la chaîne n'est pas garanti.  Les `NULL`s incorporés peuvent provoquer la troncature de la chaîne ou ils peuvent être conservés.  
  
 Les en\-têtes des bibliothèques de marshaling se trouvent dans le répertoire Include dans le sous\-répertoire msclr.  Cet exemple indique comment inclure le répertoire msclr dans une déclaration d'en\-tête Include :  
  
 `#include "msclr\marshal_cppstd.h"`  
  
 La bibliothèque de marshaling est extensible afin que vous puissiez ajouter vos propres types de marshaling.  Pour plus d'informations sur l'extension de la bibliothèque de marshaling, consultez [Comment : étendre la bibliothèque de marshaling](../dotnet/how-to-extend-the-marshaling-library.md).  
  
 Dans les versions antérieures, vous pouviez marshaler des données à l'aide de la [Platforme Invoke](../Topic/Consuming%20Unmanaged%20DLL%20Functions.md).  Pour plus d'informations sur `PInvoke`, consultez [Appel à des fonctions natives à partir de code managé](../dotnet/calling-native-functions-from-managed-code.md).  
  
## Voir aussi  
 [Bibliothèque de prise en charge C\+\+](../dotnet/cpp-support-library.md)   
 [Comment : étendre la bibliothèque de marshaling](../dotnet/how-to-extend-the-marshaling-library.md)