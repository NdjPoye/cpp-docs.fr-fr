---
title: "basic_streambuf, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "basic_streambuf"
  - "streambuf/std::basic_streambuf"
  - "std.basic_streambuf"
  - "std::basic_streambuf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_streambuf (classe)"
ms.assetid: 136af6c3-13bf-4501-9288-b93da26efac7
caps.latest.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 27
---
# basic_streambuf, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit une classe de base abstraite pour dériver une mémoire tampon de flux qui contrôle la transmission des éléments depuis et vers une représentation spécifique d'un flux.  
  
## Syntaxe  
  
```  
template<class Elem, class Tr = char_traits<Elem> >  
   class basic_streambuf;  
```  
  
#### Paramètres  
 `Elem`  
 Un [char\_type](../Topic/basic_streambuf::char_type.md).  
  
 `Tr`  
 Le [traits\_type](../Topic/basic_streambuf::traits_type.md) du caractère.  
  
## Notes  
 La classe de modèle décrit une classe de base abstraite pour dériver une mémoire tampon de flux qui contrôle la transmission des éléments depuis et vers une représentation spécifique d'un flux.  Un objet de la classe `basic_streambuf` permet de contrôler un flux avec des éléments de type `Tr`, également appelé [char\_type](../Topic/basic_streambuf::char_type.md), dont les caractéristiques sont déterminées par la classe [char\_traits](../standard-library/char-traits-struct.md), également appelée [traits\_type](../Topic/basic_streambuf::traits_type.md).  
  
 Chaque mémoire tampon de flux contrôle conceptuellement deux flux indépendants : un pour les extractions \(entrée\) et un pour les insertions \(sortie\).  Une représentation spécifique peut cependant rendre l'un ou l'autre \(ou les deux\) de ces flux inaccessible.  Elle conserve en général une relation entre les deux flux.  Par exemple, ce que vous insérez dans le flux de sortie d'un objet [basic\_stringbuf](../standard-library/basic-stringbuf-class.md)\<`Elem``Tr`\> est ce que vous extrayez ultérieurement de son flux d'entrée.  Quand vous positionnez un flux d'un objet [basic\_filebuf](../standard-library/basic-filebuf-class.md)\<`Elem``Tr`\>, vous positionnez l'autre flux en tandem.  
  
 L'interface publique de la classe de modèle `basic_streambuf` fournit les opérations qui sont communes à tous les tampons de flux, qui sont cependant spécialisés.  L'interface protégée fournit les opérations nécessaires pour qu'une représentation spécifique d'un flux effectue son travail.  Les fonctions membres virtuelles protégées vous permettent de personnaliser le comportement d'une mémoire tampon de flux dérivée pour une représentation spécifique d'un flux.  Chaque mémoire tampon de flux dérivée de cette bibliothèque décrit comment elle spécialise le comportement de ses fonctions membres virtuelles protégées.  Le comportement par défaut pour la classe de base, qui est souvent de ne rien faire, est décrit dans cette rubrique.  
  
 Les fonctions membres protégées restantes contrôlent la copie de et vers le stockage fourni pour mettre en mémoire tampon les transmissions vers et depuis des flux.  Par exemple, une mémoire tampon d'entrée est caractérisée par :  
  
-   [eback](../Topic/basic_streambuf::eback.md), un pointeur vers le début de la mémoire tampon.  
  
-   [gptr](../Topic/basic_streambuf::gptr.md), un pointeur vers l'élément suivant à lire.  
  
-   [egptr](../Topic/basic_streambuf::egptr.md), un pointeur qui pointe juste après la fin de la mémoire tampon.  
  
 De façon similaire, une mémoire tampon de sortie est caractérisée par :  
  
-   [pbase](../Topic/basic_streambuf::pbase.md), un pointeur vers le début de la mémoire tampon.  
  
-   [pptr](../Topic/basic_streambuf::pptr.md), un pointeur vers l'élément suivant à écrire.  
  
-   [epptr](../Topic/basic_streambuf::epptr.md), un pointeur qui pointe juste après la fin de la mémoire tampon.  
  
 Pour toutes les mémoires tampons, le protocole suivant est utilisé :  
  
-   Si le pointeur suivant est null, c'est qu'il n'existe pas de mémoire tampon.  Dans le cas contraire, les trois pointeurs pointent tous dans la même séquence.  Ils peuvent être comparés de façon fiable quant à l'ordre.  
  
-   Pour une mémoire tampon de sortie, si le pointeur suivant est inférieur au pointeur de fin, vous pouvez stocker un élément à la position d'écriture désignée par le pointeur suivant.  
  
-   Pour une mémoire tampon d'entrée, si le pointeur suivant est inférieur au pointeur de fin, vous pouvez lire un élément à la position de lecture désignée par le pointeur suivant.  
  
-   Pour une mémoire tampon d'entrée, si le pointeur de début est inférieur au pointeur suivant, vous pouvez replacer un élément à la position de replacement désignée par le pointeur suivant décrémenté.  
  
 Les fonctions membres virtuelles protégées que vous écrivez pour une classe dérivée de `basic_streambuf`\<`Elem``Tr`\> doivent collaborer à la gestion de ce protocole.  
  
 Un objet de la classe `basic_streambuf`\<`Elem``Tr`\> stocke les six pointeurs décrits précédemment.  Il stocke également un objet de paramètres régionaux dans un objet de type [locale](../standard-library/locale-class.md) pour une éventuelle utilisation par une mémoire tampon de flux dérivée.  
  
### Constructeurs  
  
|||  
|-|-|  
|[basic\_streambuf](../Topic/basic_streambuf::basic_streambuf.md)|Construit un objet de type `basic_streambuf`.|  
  
### Typedefs  
  
|||  
|-|-|  
|[char\_type](../Topic/basic_streambuf::char_type.md)|Associe un nom de type au paramètre de modèle `Elem`.|  
|[int\_type](../Topic/basic_streambuf::int_type.md)|Associe un nom de type dans la portée `basic_streambuf` avec le paramètre de modèle `Elem`.|  
|[off\_type](../Topic/basic_streambuf::off_type.md)|Associe un nom de type dans la portée `basic_streambuf` avec le paramètre de modèle `Elem`.|  
|[pos\_type](../Topic/basic_streambuf::pos_type.md)|Associe un nom de type dans la portée `basic_streambuf` avec le paramètre de modèle `Elem`.|  
|[traits\_type](../Topic/basic_streambuf::traits_type.md)|Associe un nom de type au paramètre de modèle `Tr`.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[eback](../Topic/basic_streambuf::eback.md)|Une fonction protégée qui retourne un pointeur vers le début de la mémoire tampon d'entrée.|  
|[egptr](../Topic/basic_streambuf::egptr.md)|Une fonction protégée qui retourne un pointeur qui pointe juste après la fin de la mémoire tampon d'entrée.|  
|[epptr](../Topic/basic_streambuf::epptr.md)|Une fonction protégée qui retourne un pointeur qui pointe juste après la fin de la mémoire tampon de sortie.|  
|[gbump](../Topic/basic_streambuf::gbump.md)|Une fonction protégée qui ajoute `_Count` au pointeur suivant pour la mémoire tampon d'entrée.|  
|[getloc](../Topic/basic_streambuf::getloc.md)|Obtient les paramètres régionaux de l'objet `basic_streambuf`.|  
|[gptr](../Topic/basic_streambuf::gptr.md)|Une fonction protégée qui retourne un pointeur vers l'élément suivant de la mémoire tampon d'entrée.|  
|[imbue](../Topic/basic_streambuf::imbue.md)|Une fonction virtuelle protégée appelée par [pubimbue](../Topic/basic_streambuf::pubimbue.md).|  
|[in\_avail](../Topic/basic_streambuf::in_avail.md)|Retourne le nombre d'éléments qui sont prêts à être lus dans la mémoire tampon.|  
|[dépassement de capacité](../Topic/basic_streambuf::overflow.md)|Fonction virtuelle protégée qui peut être appelée quand un nouveau caractère est inséré dans une mémoire tampon saturée.|  
|[pbackfail](../Topic/basic_streambuf::pbackfail.md)|Une fonction membre virtuelle protégée qui tente de replacer un élément dans le flux d'entrée, puis d'en faire l'élément actif \(pointé par le pointeur suivant\).|  
|[pbase](../Topic/basic_streambuf::pbase.md)|Une fonction protégée qui retourne un pointeur vers le début de la mémoire tampon de sortie.|  
|[pbump](../Topic/basic_streambuf::pbump.md)|Une fonction protégée qui ajoute `count` au pointeur suivant pour la mémoire tampon de sortie.|  
|[pptr](../Topic/basic_streambuf::pptr.md)|Une fonction protégée qui retourne un pointeur vers l'élément suivant de la mémoire tampon de sortie.|  
|[pubimbue](../Topic/basic_streambuf::pubimbue.md)|Définit les paramètres régionaux de l'objet `basic_streambuf`.|  
|[pubseekoff](../Topic/basic_streambuf::pubseekoff.md)|Appelle [seekoff](../Topic/basic_streambuf::seekoff.md), une fonction virtuelle protégée, qui est remplacée dans une classe dérivée.|  
|[pubseekpos](../Topic/basic_streambuf::pubseekpos.md)|Appelle [seekpos](../Topic/basic_streambuf::seekpos.md), une fonction virtuelle protégée qui est remplacée dans une classe dérivée et réinitialise la position actuelle du pointeur.|  
|[pubsetbuf](../Topic/basic_streambuf::pubsetbuf.md)|Appelle [setbuf](../Topic/basic_streambuf::setbuf.md), une fonction virtuelle protégée qui est remplacée dans une classe dérivée.|  
|[pubsync](../Topic/basic_streambuf::pubsync.md)|Appelle [sync](../Topic/basic_streambuf::sync.md), une fonction virtuelle protégée qui est remplacée dans une classe dérivée et met à jour le flux externe associé à cette mémoire tampon.|  
|[sbumpc](../Topic/basic_streambuf::sbumpc.md)|Lit et retourne l'élément actuel, en déplaçant le pointeur du flux.|  
|[seekoff](../Topic/basic_streambuf::seekoff.md)|La fonction membre virtuelle protégée tente de modifier les positions actuelles des flux contrôlés.|  
|[seekpos](../Topic/basic_streambuf::seekpos.md)|La fonction membre virtuelle protégée tente de modifier les positions actuelles des flux contrôlés.|  
|[setbuf](../Topic/basic_streambuf::setbuf.md)|La fonction membre virtuelle protégée effectue une opération spécifique à chaque mémoire tampon de flux dérivée.|  
|[setg](../Topic/basic_streambuf::setg.md)|Une fonction protégée qui stocke `_Gbeg` dans le pointeur de début, `_Gnext` dans le pointeur suivant et `_Gend` dans le pointeur de fin pour la mémoire tampon d'entrée.|  
|[setp](../Topic/basic_streambuf::setp.md)|Une fonction protégée qui stocke `_Pbeg` dans le pointeur de début et `_Pend` dans le pointeur suivant dans le pointeur de fin pour la mémoire tampon de sortie.|  
|[sgetc](../Topic/basic_streambuf::sgetc.md)|Retourne l'élément actuel sans changer la position dans le flux.|  
|[sgetn](../Topic/basic_streambuf::sgetn.md)|Retourne le nombre d'éléments lus.|  
|[showmanyc](../Topic/basic_streambuf::showmanyc.md)|Fonction membre virtuelle protégée qui retourne le nombre de caractères qui peuvent être extraits du flux d'entrée et garantit que le programme ne sera pas soumis à un délai d'attente indéfini.|  
|[snextc](../Topic/basic_streambuf::snextc.md)|Lit l'élément actuel et retourne l'élément suivant.|  
|[sputbackc](../Topic/basic_streambuf::sputbackc.md)|Place un `char_type` dans le flux.|  
|[sputc](../Topic/basic_streambuf::sputc.md)|Place un caractère dans le flux.|  
|[sputn](../Topic/basic_streambuf::sputn.md)|Place une chaîne de caractères dans le flux.|  
|[stossc](../Topic/basic_streambuf::stossc.md)|Se déplace après l'élément actuel du flux.|  
|[sungetc](../Topic/basic_streambuf::sungetc.md)|Obtient un caractère du flux.|  
|[swap](../Topic/basic_streambuf::swap.md)|Échange les valeurs de cet objet avec les valeurs du paramètre de l'objet `basic_streambuf`.|  
|[sync](../Topic/basic_streambuf::sync.md)|Une fonction virtuelle protégée qui tente de synchroniser les flux contrôlés avec tous les flux externes associés.|  
|[uflow](../Topic/basic_streambuf::uflow.md)|Une fonction virtuelle protégée qui extrait l'élément actuel du flux d'entrée.|  
|[underflow](../Topic/basic_streambuf::underflow.md)|Une fonction virtuelle protégée qui extrait l'élément actuel du flux d'entrée.|  
|[xsgetn](../Topic/basic_streambuf::xsgetn.md)|Une fonction virtuelle protégée qui extrait des éléments du flux d'entrée.|  
|[xsputn](../Topic/basic_streambuf::xsputn.md)|Une fonction virtuelle protégée qui insère des éléments dans le flux d'entrée.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[opérateur \=](../Topic/basic_streambuf::operator=.md)|Affecte les valeurs de cet objet à partir d'un autre objet `basic_streambuf`.|  
  
## Configuration requise  
 **En\-tête :** \<streambuf\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream, programmation](../standard-library/iostream-programming.md)   
 [iostreams, conventions](../standard-library/iostreams-conventions.md)