---
title: "Erreur du compilateur C3409 | Microsoft Docs"
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
  - "C3409"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3409"
ms.assetid: e372d9fa-230c-4b28-b6d3-6ad81ccf9dbb
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3409
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

un bloc d'attribut vide est interdit  
  
 Le compilateur a interprété les crochets comme un bloc d'[attribut](../../windows/cpp-attributes-reference.md), mais il n'a trouvé aucun attribut.  
  
 Le compilateur peut générer cette erreur lorsque vous utilisez des crochets dans le cadre de la définition d'une expression lambda.  Cette erreur se produit lorsque le compilateur ne peut pas déterminer si les crochets font partie de la définition d'une expression lambda ou d'un bloc d'attributs.  Pour plus d'informations sur les expressions lambda, consultez [Expressions lambda](../../cpp/lambda-expressions-in-cpp.md).  
  
### Pour corriger cette erreur  
  
1.  Si les crochets font partie d'un bloc d'attributs :  
  
    1.  fournissez un ou plusieurs attributs dans le bloc d'attributs.  
  
    2.  supprimez le bloc d'attributs.  
  
2.  Si les crochets font partie d'une expression lambda :  
  
    1.  Assurez\-vous que l'expression lambda suit des règles de syntaxes valides.  
  
         Pour plus d'informations sur la syntaxe d'une expression lambda, consultez [Syntaxe d'expression lambda](../../cpp/lambda-expression-syntax.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C3409.  
  
```  
// C3409.cpp  
// compile with: /c  
#include <windows.h>  
[]   // C3409  
class a {};  
  
// OK  
[object, uuid("00000000-0000-0000-0000-000000000000")]  
__interface x {};  
  
[coclass, uuid("00000000-0000-0000-0000-000000000001")]  
class b : public x {};  
```  
  
## Exemple  
 L'exemple suivant génère C3409 parce qu'une expression lambda utilise la spécification `mutable`, mais ne fournit pas de liste de paramètres.  Le compilateur ne peut pas déterminer si les crochets font partie de la définition d'une expression lambda ou d'un bloc d'attributs.  
  
```  
// C3409b.cpp  
  
int main()  
{  
   [] mutable {}();  
}  
```  
  
## Voir aussi  
 [attribut](../../windows/cpp-attributes-reference.md)   
 [Expressions lambda](../../cpp/lambda-expressions-in-cpp.md)   
 [Syntaxe d'expression lambda](../../cpp/lambda-expression-syntax.md)