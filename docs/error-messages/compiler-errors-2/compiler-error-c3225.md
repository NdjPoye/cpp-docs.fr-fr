---
title: "Erreur du compilateur C3225 | Microsoft Docs"
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
  - "C3225"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3225"
ms.assetid: f5f66973-256e-4298-ac46-c87819cbde34
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3225
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

l'argument de type générique de 'arg' ne peut pas être 'type', il doit s'agir d'un type valeur ou d'un type de handle  
  
 L'argument de type générique n'était pas du type correct.  
  
 Pour plus d'informations, consultez [Generics](../../windows/generics-cpp-component-extensions.md).  
  
## Exemple  
 Vous ne pouvez pas instancier de type générique avec un type natif.  L'exemple suivant génère l'erreur C3225 :  
  
```  
// C3225.cpp  
// compile with: /clr  
class A {};  
  
ref class B {};  
  
generic <class T>  
ref class C {};  
  
int main() {  
   C<A>^ c = gcnew C<A>;   // C3225  
   C<B^>^ c2 = gcnew C<B^>;   // OK  
}  
```  
  
## Exemple  
 L'exemple suivant crée un composant à l'aide de C\#.  Remarquez que la contrainte spécifie que le type générique ne peut être instancié qu'avec un type valeur.  
  
```  
// C3225_b.cs  
// compile with: /target:library  
// a C# program  
public class MyList<T> where T: struct {}  
```  
  
## Exemple  
 Cet exemple utilise le composant créé par C\# et ne respecte pas la contrainte spécifiant que MyList ne peut être instancié qu'avec un type valeur autre que <xref:System.Nullable>.  L'exemple suivant génère l'erreur C3225 :  
  
```  
// C3225_c.cpp  
// compile with: /clr  
#using "C3225_b.dll"  
ref class A {};  
value class B {};  
int main() {  
   MyList<A> x;   // C3225  
   MyList<B> y;   // OK  
}  
```