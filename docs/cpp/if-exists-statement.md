---
title: "__if_exists, instruction | Microsoft Docs"
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
  - "__if_exists_cpp"
  - "__if_exists"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__if_exists (mot clé) (C++)"
  - "identificateurs, tester l'existence"
  - "symboles, tester l'existence"
ms.assetid: d3eb34b6-f3a9-4063-a286-b62a28c0c7fa
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# __if_exists, instruction
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'instruction `__if_exists` vérifie si l'identificateur spécifié existe.  Si l'identificateur existe, le bloc d'instructions spécifié est exécuté.  
  
## Syntaxe  
  
```  
__if_exists ( identifier ) {   
statements  
};  
```  
  
#### Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`identifier`|Identificateur dont vous voulez tester l'existence.|  
|`statements`|Une ou plusieurs instructions à exécuter si `identifier` existe.|  
  
## Notes  
  
> [!CAUTION]
>  Pour obtenir les résultats les plus fiables, utilisez l'instruction `__if_exists` sous les contraintes suivantes.  
  
-   Appliquez l'instruction `__if_exists` uniquement aux types simples, et non aux modèles.  
  
-   Appliquez l'instruction `__if_exists` aux identificateurs à l'intérieur ou à l'extérieur d'une classe.  N'appliquez pas l'instruction `__if_exists` aux variables locales.  
  
-   Utilisez l'instruction `__if_exists` uniquement dans le corps d'une fonction.  En dehors du corps d'une fonction, l'instruction `__if_exists` peut tester uniquement les types entièrement définis.  
  
-   Lorsque vous vérifiez la présence de fonctions surchargées, vous ne pouvez pas effectuer le test sur une forme spécifique de la surcharge.  
  
 Le complément de l'instruction `__if_exists` est l'instruction [\_\_if\_not\_exists](../cpp/if-not-exists-statement.md).  
  
## Exemple  
 Notez que cet exemple utilise des modèles, ce qui n'est pas recommandé.  
  
```  
// the__if_exists_statement.cpp  
// compile with: /EHsc  
#include <iostream>  
  
template<typename T>  
class X : public T {  
public:  
   void Dump() {  
      std::cout << "In X<T>::Dump()" << std::endl;  
  
      __if_exists(T::Dump) {  
         T::Dump();  
      }  
  
      __if_not_exists(T::Dump) {  
         std::cout << "T::Dump does not exist" << std::endl;  
      }  
   }     
};  
  
class A {  
public:  
   void Dump() {  
      std::cout << "In A::Dump()" << std::endl;  
   }  
};  
  
class B {};  
  
bool g_bFlag = true;  
  
class C {  
public:  
   void f(int);  
   void f(double);  
};  
  
int main() {   
   X<A> x1;  
   X<B> x2;  
  
   x1.Dump();  
   x2.Dump();  
  
   __if_exists(::g_bFlag) {  
      std::cout << "g_bFlag = " << g_bFlag << std::endl;  
   }  
  
   __if_exists(C::f) {  
      std::cout << "C::f exists" << std::endl;  
   }  
  
   return 0;  
}  
```  
  
## Sortie  
  
```  
In X<T>::Dump()  
In A::Dump()  
In X<T>::Dump()  
T::Dump does not exist  
g_bFlag = 1  
C::f exists  
```  
  
## Voir aussi  
 [Instructions de sélection](../cpp/selection-statements-cpp.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)   
 [\_\_if\_not\_exists, instruction](../cpp/if-not-exists-statement.md)