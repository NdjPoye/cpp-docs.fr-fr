---
title: "deprecated (C++) | Microsoft Docs"
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
  - "deprecated"
  - "deprecated_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec (mot clé) (C++), deprecated"
  - "deprecated __declspec (mot clé)"
ms.assetid: beef1129-9434-4cb3-8392-f1eb29e04805
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# deprecated (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

\(Spécifique de Microsoft\) À l'exception des cas répertoriés ci\-dessous, la déclaration **deprecated** fournit les mêmes fonctionnalités que le pragma [deprecated](../preprocessor/deprecated-c-cpp.md) :  
  
-   La déclaration **deprecated** vous permet de spécifier des formes particulières de surcharges de fonction comme étant déconseillés, alors que la forme pragma s'applique à toutes les formes surchargées d'un nom de fonction.  
  
-   La déclaration **deprecated** vous permet de spécifier un message qui s'affiche au moment de la compilation.  Le texte du message peut être issu d'une macro.  
  
-   Les macros ne peuvent être marquées comme déconseillées que via le pragma **deprecated**.  
  
 Si le compilateur détecte l'utilisation d'un identificateur déconseillé, un avertissement [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) est généré.  
  
## Exemple  
 L'exemple suivant montre comment marquer des fonctions comme déconseillés, et comment spécifier un message à afficher au moment de la compilation, lorsque la fonction déconseillée est utilisée.  
  
```  
// deprecated.cpp  
// compile with: /W3  
#define MY_TEXT "function is deprecated"  
void func1(void) {}  
__declspec(deprecated) void func1(int) {}  
__declspec(deprecated("** this is a deprecated function **")) void func2(int) {}  
__declspec(deprecated(MY_TEXT)) void func3(int) {}  
  
int main() {  
   func1();  
   func1(1);   // C4996  
   func2(1);   // C4996  
   func3(1);   // C4996  
}  
```  
  
## Exemple  
 L'exemple suivant montre comment marquer des classes comme déconseillés, et comment spécifier un message à afficher au moment de la compilation, lorsque la classe déconseillée est utilisée.  
  
```  
// deprecate_class.cpp  
// compile with: /W3  
struct __declspec(deprecated) X {  
   void f(){}  
};  
  
struct __declspec(deprecated("** X2 is deprecated **")) X2 {  
   void f(){}  
};  
  
int main() {  
   X x;   // C4996  
   X2 x2;   // C4996  
}  
```  
  
## Voir aussi  
 [\_\_declspec](../cpp/declspec.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)