---
title: "basic_ios, classe | Microsoft Docs"
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
  - "std.basic_ios"
  - "ios/std::basic_ios"
  - "basic_ios"
  - "std::basic_ios"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_ios (classe)"
ms.assetid: 4fdcd8e1-62d2-4611-8a70-1e4f58434007
caps.latest.revision: 24
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# basic_ios, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe de modèle décrit les fonctions membres et de stockage communes aux flux d'entrée \(de classe de modèle [basic\_istream](../standard-library/basic-istream-class.md)\) et de sortie \(de classe de modèle [basic\_ostream](../standard-library/basic-ostream-class.md)\) qui dépendent des paramètres du modèle.  \(La classe [ios\_base](../standard-library/ios-base-class.md) décrit ce qui est commun et non dépendant des paramètres de modèle.\) Un objet de la classe **basic\_ios\<class Elem, class Traits\>** permet de contrôler un flux avec des éléments de type **Elem**, dont les traits de caractère sont déterminés par la classe **Traits**.  
  
## Syntaxe  
  
```  
  
     template <class   
     Elem  
     , class   
     Traits  
     >  
class basic_ios : public ios_base  
```  
  
#### Paramètres  
 `Elem`  
 Type.  
  
 `Traits`  
 Variable de type `char_traits`.  
  
## Notes  
 Un objet de la classe **basic\_ios\<class Elem, class Traits\>** stocke :  
  
-   Un pointeur de lien vers un objet de type [basic\_istream](../standard-library/basic-istream-class.md)**\<Elem, Traits\>**.  
  
-   Un pointeur de mémoire tampon de flux vers un objet de type [basic\_streambuf](../standard-library/basic-streambuf-class.md)**\<Elem, Traits \>**.  
  
-   Des [informations sur la mise en forme](../standard-library/ios-base-class.md).  
  
-   Des [informations sur l'état du flux](../standard-library/ios-base-class.md) dans un objet de base de type [ios\_base](../standard-library/ios-base-class.md).  
  
-   Un caractère de remplissage dans un objet de type `char_type`.  
  
### Constructeurs  
  
|||  
|-|-|  
|[basic\_ios](../Topic/basic_ios::basic_ios.md)|Construit la classe `basic_ios`.|  
  
### Typedefs  
  
|||  
|-|-|  
|[char\_type](../Topic/basic_ios::char_type.md)|Synonyme pour le paramètre du modèle `Elem`.|  
|[int\_type](../Topic/basic_ios::int_type.md)|Synonyme de `Traits::int_type`.|  
|[off\_type](../Topic/basic_ios::off_type.md)|Synonyme de `Traits::off_type`.|  
|[pos\_type](../Topic/basic_ios::pos_type.md)|Synonyme de `Traits::pos_type`.|  
|[traits\_type](../Topic/basic_ios::traits_type.md)|Synonyme pour le paramètre du modèle `Traits`.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[bad](../Topic/basic_ios::bad.md)|Indique une perte d'intégrité de la mémoire tampon du flux.|  
|[clear](../Topic/basic_ios::clear.md)|Efface tous les indicateurs d'erreur.|  
|[copyfmt](../Topic/basic_ios::copyfmt.md)|Copie les indicateurs d'un flux vers un autre.|  
|[eof](../Topic/basic_ios::eof.md)|Indique si la fin d'un flux a été atteinte.|  
|[exceptions](../Topic/basic_ios::exceptions.md)|Indique les exceptions qui seront levées par le flux.|  
|[fail](../Topic/basic_ios::fail.md)|Indique l'échec de l'extraction d'un champ valide dans un flux.|  
|[fill](../Topic/basic_ios::fill.md)|Spécifie ou retourne le caractère qui est utilisé quand le texte n'est pas aussi large que le flux.|  
|[good](../Topic/basic_ios::good.md)|Indique que le flux est en bon état.|  
|[imbue](../Topic/basic_ios::imbue.md)|Change les paramètres régionaux.|  
|[init](../Topic/basic_ios::init.md)|Appelé par les constructeurs `basic_ios`.|  
|[move](../Topic/basic_ios::move.md)|Déplace toutes les valeurs, sauf le pointeur vers la mémoire tampon du flux, du paramètre vers l'objet actuel.|  
|[narrow](../Topic/basic_ios::narrow.md)|Trouve le caractère équivalent à un type `char_type` donné.|  
|[rdbuf](../Topic/basic_ios::rdbuf.md)|Dirige le flux vers la mémoire tampon spécifiée.|  
|[rdstate](../Topic/basic_ios::rdstate.md)|Lit l'état des bits pour les indicateurs.|  
|[set\_rdbuf](../Topic/basic_ios::set_rdbuf.md)|Affecte une mémoire tampon de flux comme mémoire tampon de lecture pour cet objet de flux.|  
|[setstate](../Topic/basic_ios::setstate.md)|Définit des indicateurs supplémentaires.|  
|[swap](../Topic/basic_ios::swap.md)|Échange les valeurs de cet objet `basic_ios` avec celles d'un autre objet `basic_ios`.  Les pointeurs vers les mémoires tampons de flux ne sont pas échangés.|  
|[tie](../Topic/basic_ios::tie.md)|Garantit qu'un flux est traité avant un autre flux.|  
|[widen](../Topic/basic_ios::widen.md)|Trouve le type `char_type` équivalent à un caractère donné.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[opérateur explicite bool](../Topic/basic_ios::operator%20bool.md)|Permet l'utilisation d'un objet `basic_ios` comme `bool`.  La conversion de type automatique est désactivée pour éviter des effets secondaires involontaires courants.|  
|[opérateur void \*](../Topic/basic_ios::operator%20void%20*.md)|Indique si le flux est toujours en bon état.|  
|[opérateur \!](../Topic/basic_ios::operator!.md)|Indique si le flux n'est pas en mauvais état.|  
  
## Configuration requise  
 **En\-tête :** \<ios\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream, programmation](../standard-library/iostream-programming.md)   
 [iostreams, conventions](../standard-library/iostreams-conventions.md)