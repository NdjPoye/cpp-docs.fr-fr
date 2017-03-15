---
title: "Avertissement du compilateur (niveaus 3 and 4) C4244 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4244"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4244"
ms.assetid: f116bb09-c479-4b4e-a647-fe629a1383f6
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# Avertissement du compilateur (niveaus 3 and 4) C4244
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'conversion' : conversion de 'type1' en 'type2', perte possible de données  
  
 Un type entier est converti en type entier plus petit.  Cet avertissement est de niveau 4 si *type1* est `int` et *type2* est plus petit que `int`.  Dans le cas contraire, il est de niveau 3 \(attribution d'une valeur de type [\_\_int64](../../cpp/int8-int16-int32-int64.md) à une variable de type `unsigned int`\).  Une perte de données peut avoir eu lieu.  
  
 Si vous obtenez l'avertissement C4244, vous devez modifier votre programme pour utiliser des types compatibles, ou ajouter une logique à votre code pour garantir que la plage des valeurs possibles sera toujours compatible avec les types que vous utilisez.  
  
 L'avertissement C4244 peut également se produire au niveau 2. Consultez [Avertissement du compilateur \(niveau 2\) C4244](../../error-messages/compiler-warnings/compiler-warning-level-2-c4244.md) pour plus d'informations.  
  
 La conversion peut rencontrer un problème dû à des conversions implicites.  
  
 L'exemple suivant génère l'avertissement C4244 :  
  
```  
// C4244_level4.cpp  
// compile with: /W4  
int aa;  
unsigned short bb;  
int main() {  
   int b = 0, c = 0;  
   short a = b + c;   // C4244  
  
   bb += c;   // C4244  
   bb = bb + c;   // C4244  
   bb += (unsigned short)aa;   // C4244  
   bb = bb + (unsigned short)aa;   // OK  
}  
```  
  
 Pour plus d'informations, consultez [Conversions arithmétiques courantes](../../c-language/usual-arithmetic-conversions.md).  
  
```  
// C4244_level3.cpp  
// compile with: /W3  
int main() {  
   __int64 i = 8;  
   unsigned int ii = i;   // C4244  
}  
```  
  
 L'avertissement C4244 peut se produire lors de la génération de code pour des cibles 64 bits et ne pas se produire lors de la génération de code pour des cibles 32 bits.  Par exemple, une différence entre des pointeurs est une quantité 32 bits sur les plateformes 32 bits mais une quantité 64 bits sur les plateformes 64 bits.  
  
 L'exemple suivant génère l'avertissement C4244 lors de la compilation pour des cibles 64 bits :  
  
```  
// C4244_level3_b.cpp  
// compile with: /W3   
int main() {  
   char* p1 = 0;  
   char* p2 = 0;  
   int x = p2 - p1;   // C4244  
}  
```