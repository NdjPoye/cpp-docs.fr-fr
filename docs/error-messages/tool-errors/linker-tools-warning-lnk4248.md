---
title: "Avertissement des outils &#201;diteur de liens LNK4248 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4248"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4248"
ms.assetid: e40523ff-e3cb-4ba6-ab79-23f0f339f6cf
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement des outils &#201;diteur de liens LNK4248
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

jeton typeref non résolu \(jeton\) pour 'type' ; l'image risque de ne pas s'exécuter  
  
 Un type ne possède pas de définition dans les métadonnées MSIL.  
  
 L'erreur LNK4248 peut se produire lorsqu'il n'existe qu'une déclaration anticipée pour un type dans un module MSIL \(compilé avec **\/clr**\), où le type est référencé dans ce dernier et où le module MSIL est lié à un module natif possédant une définition pour le type.  
  
 Dans cette situation, l'éditeur de liens fournit la définition de type native dans les métadonnées MSIL, et cela peut entraîner le comportement correct.  
  
 Toutefois, si une déclaration de type anticipée est un type CLR, la définition de type native de l'éditeur de liens risque de ne pas être correcte  
  
 Pour plus d'informations, consultez [\/clr \(Compilation pour le Common Language Runtime\)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
### Pour corriger cette erreur  
  
1.  Fournissez la définition de type dans le module MSIL.  
  
## Exemple  
 L'exemple suivant génère l'erreur LNK4248.  Définissez la structure A pour y remédier.  
  
```  
// LNK4248.cpp  
// compile with: /clr /W1  
// LNK4248 expected  
struct A;  
void Test(A*){}  
  
int main() {  
   Test(0);  
}  
```  
  
## Exemple  
 L'exemple suivant comprend une définition anticipée d'un type.  
  
```  
// LNK4248_2.cpp  
// compile with: /clr /c  
class A;   // provide a definition for A here to resolve  
A * newA();  
int valueA(A * a);  
  
int main() {  
   A * a = newA();  
   return valueA(a);  
}  
```  
  
## Exemple  
 L'exemple suivant génère l'erreur LNK4248.  
  
```  
// LNK4248_3.cpp  
// compile with: /c  
// post-build command: link LNK4248_2.obj LNK4248_3.obj  
class A {  
public:   
   int b;  
};  
  
A* newA() {  
   return new A;  
}  
  
int valueA(A * a) {  
   return (int)a;  
}  
```