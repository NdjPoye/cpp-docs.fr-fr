---
title: "Erreur du compilateur C2955 | Microsoft Docs"
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
  - "C2955"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2955"
ms.assetid: 77709fb6-d69b-46fd-a62f-e8564563d01b
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2955
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : l'utilisation d'un modèle de classe ou d'un générique d'alias requiert une liste d'arguments modèles ou génériques  
  
 Vous ne pouvez pas utiliser un modèle de classe ni un générique de classe comme identificateur sans une liste d'arguments modèles ou génériques.  
  
 Pour plus d'informations, consultez [Modèles de classe](../../cpp/class-templates.md).  
  
 L'exemple suivant génère l'erreur C2955 et montre comment la corriger :  
  
```  
// C2955.cpp  
// compile with: /c  
template<class T>   
class X {};  
  
X x1;   // C2955  
X<int> x2;   // OK - this is how to fix it.  
```  
  
 L'erreur C2955 peut également se produire lors de la tentative d'une définition hors ligne d'une fonction déclarée dans un modèle de classe :  
  
```  
// C2955_b.cpp  
// compile with: /c  
template <class T>  
class CT {  
public:  
   void CTFunc();  
   void CTFunc2();  
};  
  
void CT::CTFunc() {}   // C2955  
  
// OK - this is how to fix it  
template <class T>  
void CT<T>::CTFunc2() {}  
  
```  
  
 L'erreur C2955 peut également se produire lors de l'utilisation de génériques :  
  
```  
// C2955_c.cpp  
// compile with: /clr  
generic <class T>   
ref struct GC {   
   T t;  
};  
  
int main() {  
   GC^ g;   // C2955  
   GC <int>^ g;  
}  
```