---
title: "&#201;crire vos propres manipulateurs sans arguments | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "manipulateurs"
ms.assetid: 2dc62d09-45b7-454d-bd9d-55f3c72c206d
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# &#201;crire vos propres manipulateurs sans arguments
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les manipulateurs d'écriture qui n'utilisent pas d'arguments ne requièrent ni de dérivation de classe ni l'utilisation de macros complexes.  Supposons que votre imprimante nécessite la paire \<échap\> pour entrer en mode gras.  Vous pouvez insérer cette paire directement dans le flux de données :  
  
```  
cout << "regular " << '\033' << '[' << "boldface" << endl;  
```  
  
 Vous pouvez définir le manipulateur de `bold`, qui insère les caractères suivants :  
  
```  
ostream& bold( ostream& os ) {  
    return os << '\033' << '[';  
}  
cout << "regular " << bold << "boldface" << endl;  
```  
  
 La fonction définie globalement `bold` accepte un argument de référence d' `ostream` et retourne la référence d' `ostream`.  Ce n'est pas une méthode ou une fonction amie car il n'a pas besoin d'accéder à un élément privé de la classe.  La fonction `bold` se connecte au flux de données car l'opérateur de `<<` du flux de données est surexploité pour accepter ce type de fonction, utilisant une déclaration qui ressemble à ceci :  
  
```  
_Myt& operator<<(ios_base& (__cdecl *_Pfn)(ios_base&))  
{     
   // call ios_base manipulator  
   (*_Pfn)(*(ios_base *)this);  
   return (*this);  
}  
```  
  
 Vous pouvez utiliser cette fonctionnalité pour étendre d'autres opérateurs surchargés.  Dans ce cas, il est fortuit que `bold` insère les caractères dans le flux de données.  La fonction est appelée lorsqu'elle est insérée dans le flux de données, mais pas nécessairement lorsque les caractères adjacents sont imprimés.  Par conséquent, imprimer peut être retardé en raison de la mise en mémoire tampon du flux de données.  
  
## Voir aussi  
 [Flux de sortie](../standard-library/output-streams.md)