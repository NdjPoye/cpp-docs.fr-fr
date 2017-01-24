---
title: "Erreur du compilateur C2951 | Microsoft Docs"
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
  - "C2951"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2951"
ms.assetid: c6f95aa2-c894-425b-a51c-d40d70c8daa1
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2951
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

les déclarations de type ne sont autorisées qu'au niveau de la portée globale, de la portée espace de noms ou de la portée de classe  
  
 Vous ne pouvez pas déclarer une classe générique ou de modèle en\-dehors de la portée globale ou de la portée de l'espace de noms.  Si vous effectuez vos déclarations génériques ou de modèle dans un fichier include, assurez\-vous que le fichier include se trouve au niveau de la portée globale.  
  
 L'exemple suivant génère l'erreur C2951 :  
  
```  
// C2951.cpp  
template <class T>  
class A {};  
  
int main() {  
   template <class T>   // C2951  
   class B {};  
}  
```  
  
 L'erreur C2951 peut également se produire lors de l'utilisation de génériques :  
  
```  
// C2951b.cpp  
// compile with: /clr /c  
  
// OK  
generic <class T>   
ref class GC { };  
  
int main() {  
   generic <class T> ref class GC2 {};   // C2951  
}  
```