---
title: "__uuidof, op&#233;rateur | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__LIBID_"
  - "__LIBID_cpp"
  - "__uuidof"
  - "__uuidof_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__LIBID_ (mot clé) (C++)"
  - "__uuidof (mot clé) (C++)"
ms.assetid: badfe709-809b-4b66-ad48-ee35039d25c6
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# __uuidof, op&#233;rateur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Récupère le GUID associé à l'expression.  
  
## Syntaxe  
  
```  
  
      __uuidof (  
   expression   
)  
```  
  
## Notes  
 L' *expression* peut être un nom de type, un pointeur, une référence, ou un tableau de ce type, un modèle spécifique de ces types, ou une variable de ces types.  L'argument est valide tant que le compilateur peut l'utiliser pour rechercher un GUID associé.  
  
 Un cas particulier de cette fonction intrinsèque est lorsque **0** ou **NULL** est fourni comme argument.  Dans ce cas, `__uuidof` retourne un GUID composé de zéros.  
  
 Utilisez ce mot clé pour récupérer un GUID associé :  
  
-   Un objet par l'attribut étendu [uuid](../cpp/uuid-cpp.md).  
  
-   Un bloc bibliothèque créé à l'aide de l'attribut [module](../windows/module-cpp.md).  
  
> [!NOTE]
>  Dans une version Debug, `__uuidof` initialise toujours un objet dynamiquement \(au moment de l'exécution\).  Dans une version Release, `__uuidof` peuvent \(au moment de la compilation\) initialiser statiquement un objet.  
  
## Exemple  
 Le code suivant \(compilé avec ole32.lib\) affichera l'uuid d'un bloc bibliothèque créé avec l'attribut module :  
  
```  
// expre_uuidof.cpp  
// compile with: ole32.lib  
#include "stdio.h"  
#include "windows.h"  
  
[emitidl];  
[module(name="MyLib")];  
[export]  
struct stuff {  
   int i;  
};  
  
int main() {  
   LPOLESTR lpolestr;  
   StringFromCLSID(__uuidof(MyLib), &lpolestr);  
   wprintf_s(L"%s", lpolestr);  
   CoTaskMemFree(lpolestr);  
}  
```  
  
## Commentaires  
 Dans les cas où le nom de la bibliothèque n'apparaît plus dans la portée, utilisez \_\_LIBID\_ au lieu de `__uuidof`.  Par exemple :  
  
```  
StringFromCLSID(__LIBID_, &lpolestr);  
```  
  
 **END Spécifique à Microsoft**  
  
## Voir aussi  
 [Expressions avec opérateurs unaires](../cpp/expressions-with-unary-operators.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)