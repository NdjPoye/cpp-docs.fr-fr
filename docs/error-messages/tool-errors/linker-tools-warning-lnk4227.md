---
title: "Avertissement des outils &#201;diteur de liens LNK4227 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4227"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4227"
ms.assetid: 941a0414-9964-4e02-8487-f9daa42ef7f9
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Avertissement des outils &#201;diteur de liens LNK4227
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

avertissement sur l'opération de \(HRESULT\) : message\_avertissement  
  
 L'éditeur de liens a détecté des différences de métadonnées lors de la fusion :  
  
-   Un ou plusieurs assemblys référencés avec l'assembly actuellement généré.  
  
-   Un ou plusieurs fichiers de code source dans une compilation.  
  
 Par exemple, l'erreur LNK4227 peut être générée si vous possédez deux fonctions globales portant le même nom, mais si les informations sur les paramètres sont déclarées différemment \(les déclarations ne sont pas cohérentes dans tous les compilands \(modules\)\).  Utilisez ildasm.exe \/TEXT \/METADATA `object_file` sur chaque fichier .obj afin de déterminer les différences entre les types.  
  
 L'erreur LNK4227 signale également des problèmes ayant pour origine un autre outil.  Pour voir un exemple, consultez [Erreurs et avertissements de l'outil Al.exe \(Al.exe Tool Errors and Warnings\)](http://msdn.microsoft.com/fr-fr/7f125d49-0a03-47a6-9ba9-d61a679a7d4b).  
  
 Les problèmes de métadonnées doivent être corrigés pour résoudre l'avertissement.  
  
 Par exemple, LNK4227 est généré lorsqu'un assembly n'a pas été référencé de la même manière que l'assembly qui y fait référence.  
  
 L'exemple suivant génère l'erreur LNK4227 :  
  
```  
// LNK4227.cpp  
// compile with: /clr  
using namespace System::Reflection;  
  
[assembly:AssemblyDelaySignAttribute(false)];  
  
int main() {}  
```  
  
 et ensuite,  
  
```  
// LNK4227b.cpp  
// compile with: /clr LNK4227.cpp /FeLNK4227b.exe  
using namespace System::Reflection;  
using namespace System::Runtime::CompilerServices;  
  
[assembly:AssemblyDelaySignAttribute(true)];  
// Try the following line instead  
// [assembly:AssemblyDelaySignAttribute(false)];  
  
ref class MyClass  
{  
};  
```  
  
 L'exemple suivant génère l'erreur LNK4227 :  
  
```  
// LNK4227c.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System::Reflection;  
  
[assembly:AssemblyDelaySignAttribute(false)];  
  
int main() {}  
```  
  
 et ensuite,  
  
```  
// LNK4227d.cpp  
// compile with: /clr:oldSyntax LNK4227c.cpp /FeLNK4227d.exe  
#using <mscorlib.dll>  
using namespace System::Reflection;  
using namespace System::Runtime::CompilerServices;  
  
[assembly:AssemblyDelaySignAttribute(true)];  
  
__gc class MyClass  
{  
};  
```  
  
 L'erreur LNK4227 peut également être générée lorsque des numéros de version dans un format incorrect sont passés aux attributs de l'assembly.  La notation '\*' est spécifique à AssemblyVersionAttribute.  Pour remédier à cet avertissement, n'utilisez que des nombres dans les attributs de version autres que AssemblyVersionAttribute.  
  
 L'exemple suivant génère l'erreur LNK4227 :  
  
```  
// LNK4227e.cpp  
// compile with: /clr /LD /W1  
using namespace System::Reflection;  
[assembly:AssemblyVersionAttribute("2.3.*")];   // OK  
[assembly:AssemblyFileVersionAttribute("2.3.*")];   // LNK4227  
// try the following line instead  
// [assembly:AssemblyFileVersionAttribute("2.3")];  
```