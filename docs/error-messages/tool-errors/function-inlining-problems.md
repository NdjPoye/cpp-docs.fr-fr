---
title: "Probl&#232;mes de fonctions inline | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Ob1 C++ (option du compilateur)"
  - "/Ob2 C++ (option du compilateur)"
  - "problèmes de fonctions inline"
  - "fonctions inline, problèmes"
  - "-Ob1 C++ (option du compilateur)"
  - "-Ob2 C++ (option du compilateur)"
ms.assetid: 65d59943-4b3c-4a43-aeb6-dccbf7686740
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Probl&#232;mes de fonctions inline
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Si vous utilisez la fonctionnalité inline, vous devez :  
  
-   Implémenter les fonctions inline dans le fichier d'en\-tête inclus.  
  
-   Activer la fonctionnalité inline dans le fichier d'en\-tête.  
  
```  
// LNK2019_function_inline.cpp  
// compile with: /c   
// post-build command: lib LNK2019_function_inline.obj  
#include <stdio.h>  
struct _load_config_used {  
   void Test();  
   void Test2() { printf("in Test2\n"); }  
};  
  
void _load_config_used::Test() { printf("in Test\n"); }  
```  
  
 Ensuite,  
  
```  
// LNK2019_function_inline_2.cpp  
// compile with: LNK2019_function_inline.lib  
struct _load_config_used {  
   void Test();  
   void Test2();  
};  
  
int main() {  
   _load_config_used x;  
   x.Test();  
   x.Test2();   // LNK2019  
}  
```  
  
 Si vous utilisez la directive du compilateur `#pragma inline_depth`, vérifiez que vous utilisez une valeur supérieure ou égale à 2.  Une valeur zéro désactive la fonctionnalité inline.  Vérifiez aussi que vous utilisez les options du compilateur **\/Ob1** ou **\/Ob2**.  
  
 Le mélange d'options de compilation en ligne et non en ligne sur des modules différents peut parfois causer des problèmes.  Si une bibliothèque C\+\+ est créée avec la fonctionnalité inline activée \([\/Ob1](../../build/reference/ob-inline-function-expansion.md) ou [\/Ob2](../../build/reference/ob-inline-function-expansion.md)\), alors que le fichier d'en\-tête correspondant décrivant les fonctions a désactivé cette fonctionnalité \(sans option\), l'erreur LNK2001 survient.  Les fonctions ne sont pas incluses en ligne dans le code à partir du fichier d'en\-tête, mais comme elles ne sont pas dans le fichier de bibliothèque, il n'y a pas d'adresse pour résoudre la référence.  
  
 De même, un projet qui utilise la fonctionnalité inline de fonction mais définit les fonctions dans un fichier .cpp au lieu du fichier d'en\-tête peut générer l'erreur LNK2019.  Le fichier d'en\-tête est inclus partout où cette inclusion est considérée comme appropriée, mais les fonctions ne sont incluses que quand le fichier .cpp passe dans le compilateur ; l'éditeur de liens voit donc les fonctions comme des externes non résolus si elles sont utilisées dans d'autres modules.  
  
```  
// LNK2019_FIP.h  
struct testclass {  
   void PublicStatMemFunc1(void);  
};  
```  
  
 et ensuite,  
  
```  
// LNK2019_FIP.cpp  
// compile with: /c  
#include "LNK2019_FIP.h"  
inline void testclass::PublicStatMemFunc1(void) {}  
```  
  
 et ensuite,  
  
```  
// LNK2019_FIP_2.cpp  
// compile with: LNK2019_FIP.cpp  
// LNK2019 expected  
#include "LNK2019_FIP.h"  
int main() {  
   testclass testclsObject;  
  
   // module cannot see the implementation of PublicStatMemFunc1  
   testclsObject.PublicStatMemFunc1();  
}  
```  
  
## Voir aussi  
 [Erreur des outils Éditeur de liens LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)