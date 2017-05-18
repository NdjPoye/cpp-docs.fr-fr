---
title: "LNK4227 d’avertissement des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4227
dev_langs:
- C++
helpviewer_keywords:
- LNK4227
ms.assetid: 941a0414-9964-4e02-8487-f9daa42ef7f9
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: ee566318c7d19159f9a2c084d348b5010a65e2de
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-warning-lnk4227"></a>Avertissement des outils Éditeur de liens LNK4227
Avertissement d’opération de métadonnées (HRESULT) : message_avertissement  
  
L’éditeur de liens a détecté des différences de métadonnées lors de la fusion :  
  
-   Un ou plusieurs assemblys référencés avec l’assembly en cours de génération.  
  
-   Un ou plusieurs fichiers de code source une compilation.  
  
Par exemple, LNK4227 peut se produire si vous avez deux fonctions globales portant le même nom mais les informations sur les paramètres déclarés différemment (les déclarations ne sont pas cohérentes dans tous les compilands). Utilisez ildasm.exe /TEXT /METADATA `object_file` sur chaque .obj fichier et vous devez voir comment les types sont différents.  
  
LNK4227 signale également des problèmes provenant d’un autre outil. Par exemple, al.exe ; consultez la page [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b).  
  
Les problèmes de métadonnées doivent être corrigées pour résoudre l’avertissement.  
  
Par exemple, LNK4227 est généré lorsqu’un assembly référencé a été signé différemment de l’assembly qui y fait référence.  
  
L’exemple suivant génère l’erreur LNK4227 :  
  
```  
// LNK4227.cpp  
// compile with: /clr  
using namespace System::Reflection;  
  
[assembly:AssemblyDelaySignAttribute(false)];  
  
int main() {}  
```  
  
 Et puis  
  
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
  
LNK4227 peut également être générée lorsque les numéros de version dans un format incorrect sont passés aux attributs de l’assembly.  Le ' *' notation est spécifique à AssemblyVersionAttribute.  Pour résoudre cet avertissement, utilisez uniquement des nombres dans les attributs de version autres que AssemblyVersionAttribute.  
  
L’exemple suivant génère l’erreur LNK4227 :  
  
```  
// LNK4227e.cpp  
// compile with: /clr /LD /W1  
using namespace System::Reflection;  
[assembly:AssemblyVersionAttribute("2.3.*")];   // OK  
[assembly:AssemblyFileVersionAttribute("2.3.*")];   // LNK4227  
// try the following line instead  
// [assembly:AssemblyFileVersionAttribute("2.3")];  
```
