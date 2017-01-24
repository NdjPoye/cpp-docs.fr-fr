---
title: "Ressources propres objets (RAII) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: f86b484e-5a27-4c3b-a92a-dfaa5dd6d93a
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Ressources propres objets (RAII)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vérifiez que les objets possèdent des ressources.  Ce principe est également appelée « l'aquisition de ressources est une initialisation » ou « RAII ».  
  
## Exemple  
 Passez chaque « nouvel objet » comme argument de constructeur à un autre objet qui le possède \(presque toujours unique\_ptr\).  
  
```cpp  
void f() {  
  unique_ptr<widget> p( new widget(…) );  
  my_class x( new widget() );  
  …  
} // automatic destruction and deallocation for both widget objects  
  // automatic exception safety, as if “finally { p->dispose(); x.w.dispose(); }”  
  
```  
  
 Passez immédiatement toute nouvelle ressource à un autre objet qui la possède.  
  
```cpp  
void g() {  
  other_class y( OpenFile() );  
  …  
} // automatic closing and release for file resource  
  // automatic exception safety, as if “finally { y.file.dispose(); }”  
  
```  
  
## Voir aussi  
 [Bienvenue dans C\+\+](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [Référence du langage C\+\+](../cpp/cpp-language-reference.md)   
 [Bibliothèque standard C\+\+](../standard-library/cpp-standard-library-reference.md)