---
title: "Erreur du compilateur C2146 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2146"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2146"
ms.assetid: 6bfb7de6-6723-4486-9350-c66ef88d7a64
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# Erreur du compilateur C2146
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

erreur de syntaxe : absence de 'jeton' avant l'identificateur 'identificateur'  
  
 Le compilateur attendait `token` et a trouvé `identifier` à la place.  Causes possibles :  
  
1.  Faute d'orthographe ou erreur de majuscule.  
  
2.  Spécificateur de type manquant dans la déclaration de l'identificateur.  
  
 Cette erreur peut découler d'une erreur typographique.  Cette erreur est généralement précédée de l'erreur [C2065](../../error-messages/compiler-errors-1/compiler-error-c2065.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C2146 :  
  
```  
// C2146.cpp  
class CDeclaredClass {};  
  
class CMyClass {  
   CUndeclared m_myClass;   // C2146  
   CDeclaredClass m_myClass2;   // OK  
};  
  
int main() {  
   int x;  
   int t x;   // C2146 : missing semicolon before 'x'  
}  
```  
  
## Exemple  
 Cette erreur peut également être due à la mise à conformité du compilateur pour Visual Studio .NET 2003 : mot clé `typename` manquant.  
  
 L'exemple suivant se compile sans problème dans Visual Studio .NET 2002, mais échoue dans Visual Studio .NET 2003 :  
  
```  
// C2146b.cpp  
// compile with: /c  
template <typename T>  
struct X {  
   struct Y {  
      int i;  
   };  
   Y memFunc();  
};  
  
template <typename T>  
X<T>::Y func() { }   // C2146  
  
// OK  
template <typename T>  
typename X<T>::Y func() { }  
```  
  
## Exemple  
 Cette erreur peut également être due à la mise à conformité du compilateur pour Visual Studio .NET 2003 : des spécialisations explicites ne trouvent plus de paramètres de modèle dans le modèle principal.  
  
 L'utilisation de `T` à partir du modèle principal n'est pas autorisée dans la spécialisation explicite.  Pour que le code soit valide dans les versions Visual Studio .NET 2003 et Visual Studio .NET de Visual C\+\+, remplacez toutes les instances du paramètre de modèle dans la spécialisation par le type explicitement spécialisé.  
  
 L'exemple suivant se compile sans problème dans Visual Studio .NET mais échoue dans Visual Studio .NET 2003 :  
  
```  
// C2146_c.cpp  
// compile with: /c  
template <class T>   
struct S;  
  
template <>   
struct S<int> {  
   T m_t;   // C2146  
   int m_t2;   // OK  
};  
```