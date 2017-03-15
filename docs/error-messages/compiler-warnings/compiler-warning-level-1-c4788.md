---
title: "Avertissement du compilateur (niveau&#160;1) C4788 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4788"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4788"
ms.assetid: 47d75bda-f833-4bdd-93a0-a134df0cd303
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Avertissement du compilateur (niveau&#160;1) C4788
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : l'identificateur a été tronqué à 'nombre' caractères  
  
 Le compilateur limite la longueur maximale autorisée pour un nom de fonction.  Lorsque le compilateur génère des funclets pour le code EH\/SEH ; il constitue le nom du funclet en ajoutant le nom de la fonction avec du texte \(par exemple, "\_\_catch", "\_\_unwind" ou une autre chaîne\).  
  
 Le nom de funclet résultant est peut\-être trop long. Dans ce cas, le compilateur le tronquera et générera l'erreur C4788.  
  
 Pour résoudre cet avertissement, raccourcissez le nom de la fonction d'origine.  Si la fonction est une fonction ou une méthode de modèle C\+\+, utilisez un typedef pour une partie du nom.  Par exemple :  
  
```  
C1<x, y, z<T>>::C2<a,b,c>::f  
```  
  
 peut être remplacé par :  
  
```  
typedef C1<x, y, z<T>>::C2<a,b,c> new_class ;  
new_class::f  
```  
  
 Cet avertissement se produit uniquement dans le compilateur [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)].