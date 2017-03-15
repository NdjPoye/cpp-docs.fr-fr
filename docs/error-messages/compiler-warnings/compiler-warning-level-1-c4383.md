---
title: "Avertissement du compilateur (niveau 1) C4383 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4383"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4383"
ms.assetid: 96c0e52d-874e-4b57-a154-0e49b6a00fae
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Avertissement du compilateur (niveau 1) C4383
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'opérateur\_déréférencement\_instance' : la signification du déréférencement d'un handle peut changer lorsqu'il existe un opérateur 'opérateur' défini par l'utilisateur ; écrivez l'opérateur comme une fonction static pour rendre l'opérande explicite  
  
 Lorsque vous ajoutez une substitution d'instance définie par l'utilisateur de l'opérateur de déréférencement dans un type managé, vous empêchez potentiellement l'opérateur de déréférencement du type detranslators retourner l'objet du handle.  Envisagez d'écrire un opérateur de déréférencement statique défini par l'utilisateur.  
  
 Pour plus d’informations, consultez [Handle sur l'opérateur Object \(^\)](../../windows/handle-to-object-operator-hat-cpp-component-extensions.md) et [Tracking Reference Operator](../../windows/tracking-reference-operator-cpp-component-extensions.md).  
  
 Par ailleurs, un opérateur d'instance n'est plus disponible pour les autres compilateurs de langage par l'intermédiaire de métadonnées référencées.  Pour plus d'informations, consultez [Opérateurs définis par l'utilisateur](../../dotnet/user-defined-operators-cpp-cli.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C4383 :  
  
```  
// C4383.cpp  
// compile with: /clr /W1  
  
ref struct S {  
   int operator*() { return 0; }   // C4383  
};  
  
ref struct T {  
   static int operator*(T%) { return 0; }  
};   
  
int main() {  
   S s;  
   S^ pS = %s;  
  
   T t;  
   T^ pT = %t;  
   T% rT = *pT;  
}  
```