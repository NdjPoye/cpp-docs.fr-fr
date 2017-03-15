---
title: "Erreur du compilateur C3227 | Microsoft Docs"
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
  - "C3227"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3227"
ms.assetid: 7939c23a-96c8-43c2-89e9-f217d132d155
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3227
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'paramètre' : impossible d'utiliser 'MotClé' pour allouer un type générique  
  
 Pour instancier un type, un constructeur approprié est nécessaire.  Toutefois, le compilateur ne peut pas vérifier qu'un constructeur approprié est disponible.  
  
 Vous pouvez utiliser des modèles plutôt que des génériques pour résoudre cette erreur, ou utiliser l'une des différentes méthodes pour créer une instance du type.  
  
## Exemple  
 L'exemple suivant génère l'erreur C3227 :  
  
```  
// C3227.cpp  
// compile with: /clr /c  
generic<class T> interface class ICreate {  
   static T Create();  
};  
  
generic <class T>  
where T : ICreate<T>  
ref class C {  
   void f() {  
      T t = new T;   // C3227  
  
      // OK  
      T t2 = ICreate<T>::Create();  
      T t3 = safe_cast<T>( System::Activator::CreateInstance(T::typeid) );  
   }  
};  
```