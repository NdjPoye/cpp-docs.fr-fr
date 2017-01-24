---
title: "Avertissement du compilateur (niveau 3) C4686 | Microsoft Docs"
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
  - "C4686"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4686"
ms.assetid: 767c83c2-9e4b-4f9e-88c8-02128ba563f4
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 3) C4686
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**'**   
 ***type défini par l'utilisateur* ' : changement de comportement possible, changement de la convention d'appel de retour UDT**  
  
 Une spécialisation de modèle de classe n'a pas été définie avant d'être utilisée dans un type de retour.  Toute entité qui instancie la classe se résoudra en C4686 ; il est également possible de déclarer une instance ou d'accéder à un membre \(C\<int\>::toute valeur\).  
  
 Cet avertissement résulte de la mise en conformité à la norme ISO C\+\+ de Visual C\+\+ .NET 2003.  
  
 Cet avertissement est désactivé par défaut.  Pour plus d'informations, consultez [Avertissements du compilateur désactivés par défaut](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
 Essayez l’opération suivante :  
  
```  
// C4686.cpp  
// compile with: /W3  
#pragma warning (default : 4686)  
template <class T>  
class C;  
  
template <class T>  
C<T> f(T);  
  
template <class T>  
class C {};  
  
int main() {  
   f(1);   // C4686  
}  
  
template <class T>  
C<T> f(T) {  
   return C<int>();  
}  
```