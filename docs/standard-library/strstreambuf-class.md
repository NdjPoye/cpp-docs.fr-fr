---
title: "strstreambuf, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.strstreambuf"
  - "strstreambuf"
  - "std::strstreambuf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "strstreambuf (classe)"
ms.assetid: b040b8ea-0669-4eba-8908-6a9cc159c54b
caps.latest.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 25
---
# strstreambuf, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit une mémoire tampon de flux qui contrôle la transmission d'éléments vers et à partir d'une séquence d'éléments stockée dans un objet de tableau `char`.  
  
## Syntaxe  
  
```  
  
class strstreambuf : public streambuf  
  
```  
  
## Notes  
 Selon la façon dont l'objet est construit, il peut être alloué, étendu et libéré en fonction des modifications apportées à la séquence.  
  
 Un objet de classe `strstreambuf` stocke plusieurs bits d'information de mode en tant que mode `strstreambuf`. Ces bits indiquent si la séquence contrôlée :  
  
-   a été allouée et doit être libérée par la suite ;  
  
-   est modifiable ;  
  
-   est extensible en réallouant le stockage ;  
  
-   a été figée et doit donc être défigée avant que l'objet soit détruit, ou libérée \(si elle a été allouée\) par une agence autre que l'objet.  
  
 Vous ne pouvez pas modifier ou étendre une séquence contrôlée figée, quel que soit l'état de ces bits de mode distincts.  
  
 L'objet stocke également des pointeurs vers deux fonctions qui contrôlent l'allocation de `strstreambuf`. Si ces pointeurs sont null, l'objet définit sa propre méthode d'allocation et de libération du stockage pour la séquence contrôlée.  
  
> [!NOTE]
>  Cette classe est déconseillée. Envisagez d’utiliser [stringbuf](../Topic/stringbuf.md) ou [wstringbuf](../Topic/wstringbuf.md) à la place.  
  
### Constructeurs  
  
|||  
|-|-|  
|[strstreambuf](../Topic/strstreambuf::strstreambuf.md)|Construit un objet de type `strstreambuf`.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[freeze](../Topic/strstreambuf::freeze.md)|Fait en sorte qu'une mémoire tampon de flux soit indisponible via des opérations de mémoire tampon de flux.|  
|[dépassement de capacité](../Topic/strstreambuf::overflow.md)|Fonction virtuelle protégée qui peut être appelée quand un nouveau caractère est inséré dans une mémoire tampon saturée.|  
|[pbackfail](../Topic/strstreambuf::pbackfail.md)|Fonction membre virtuelle protégée qui tente de replacer un élément dans le flux d'entrée, puis d'en faire l'élément actif \(vers lequel pointe le pointeur suivant\).|  
|[pcount](../Topic/strstreambuf::pcount.md)|Retourne le nombre d'éléments écrits dans la séquence contrôlée.|  
|[seekoff](../Topic/strstreambuf::seekoff.md)|Fonction membre virtuelle protégée qui tente de modifier les positions actuelles des flux contrôlés.|  
|[seekpos](../Topic/strstreambuf::seekpos.md)|Fonction membre virtuelle protégée qui tente de modifier les positions actuelles des flux contrôlés.|  
|[str](../Topic/strstreambuf::str.md)|Appelle [freeze](../Topic/strstreambuf::freeze.md), puis retourne un pointeur vers le début de la séquence contrôlée.|  
|[underflow](../Topic/strstreambuf::underflow.md)|Fonction virtuelle protégée pour extraire l'élément actuel du flux d'entrée.|  
  
## Configuration requise  
 **En\-tête :** \<strstream\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [streambuf](../Topic/streambuf.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream, programmation](../standard-library/iostream-programming.md)   
 [iostreams, conventions](../standard-library/iostreams-conventions.md)