---
title: "fpos, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.fpos"
  - "std::fpos"
  - "iosfwd/std::fpos"
  - "fpos"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fpos (classe)"
  - "fpos (classe), à propos de la classe fpos"
ms.assetid: ffd0827c-fa34-47f4-b10e-5cb707fcde47
caps.latest.revision: 20
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fpos, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe de modèle décrit un objet qui peut stocker toutes les informations nécessaires à la restauration d'un indicateur de position de fichier arbitraire dans n'importe quel flux.  Un objet de classe fpos\<**St**\> stocke au moins deux objets membres :  
  
-   un offset d'octet, de type [streamoff](../Topic/streamoff.md) ;  
  
-   un état de conversion, utilisable par un objet de classe basic\_filebuf, de type **St**, généralement `mbstate_t`.  
  
 Il peut également stocker une position de fichier arbitraire, utilisable par un objet de classe [basic\_filebuf](../standard-library/basic-filebuf-class.md), de type `fpos_t`.  Cependant, pour un environnement avec une taille de fichier limitée, `streamoff` et `fpos_t` peuvent parfois être utilisés de manière interchangeable.  Pour un environnement où aucun flux de données n'a un encodage de dépendance d'état, `mbstate_t` peut être inutilisé.  Ainsi, le nombre d'objets membres stockés peut varier.  
  
## Syntaxe  
  
```  
  
     template <class   
     Statetype  
     >  
class fpos  
```  
  
#### Paramètres  
 *Statetype*  
 Informations d'état.  
  
### Constructeurs  
  
|||  
|-|-|  
|[fpos](../Topic/fpos::fpos.md)|Créer un objet qui contient des informations sur une position \(offset\) dans un flux.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[seekpos](../Topic/fpos::seekpos.md)|Utilisée uniquement en interne par la bibliothèque C\+\+ standard.  N'appelez pas cette méthode à partir de votre code.|  
|[state](../Topic/fpos::state.md)|Définit ou retourne l'état de la conversion.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[operator\!\=](../Topic/fpos::operator!=.md)|Teste l'inégalité d'indicateurs de position de fichier.|  
|[operator\+](../Topic/fpos::operator+.md)|incrémente un indicateur de position de fichier.|  
|[operator\+\=](../Topic/fpos::operator+=.md)|incrémente un indicateur de position de fichier.|  
|[operator\-](../Topic/fpos::operator-.md)|Décrémente un indicateur de position de fichier.|  
|[operator\-\=](../Topic/fpos::operator-=.md)|Décrémente un indicateur de position de fichier.|  
|[operator\=\=](../Topic/fpos::operator==.md)|Teste l'égalité d'indicateurs de position de fichier.|  
|[operator streamoff](../Topic/fpos::operator%20streamoff.md)|Convertit un objet de type `fpos` en objet de type `streamoff`.|  
  
## Configuration requise  
 **En\-tête :** \<ios\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream, programmation](../standard-library/iostream-programming.md)   
 [iostreams, conventions](../standard-library/iostreams-conventions.md)