---
title: "forward_list, classe | Microsoft Docs"
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
  - "std::forward_list"
  - "forward_list"
  - "forward_list/std::forward_list"
  - "std.forward_list"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "forward_list (classe)"
ms.assetid: 89a3b805-ab60-4858-b772-5855130c11b1
caps.latest.revision: 25
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# forward_list, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit un objet qui contrôle une séquence de longueur variable constituée d'éléments.  La séquence est stockée en tant que liste de nœuds à liaison unique, chacun contenant un membre de type `Type`.  
  
## Syntaxe  
  
```  
template<  
    class Type,   
    class Allocator = allocator<Type>   
>  
class forward_list   
```  
  
#### Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`Type`|Type de données d'élément à stocker dans le forward\_list.|  
|`Allocator`|Objet allocateur stocké qui contient des informations sur l'allocation et la désallocation de mémoire du forward\_list.  Ce paramètre est optionnel.  La valeur par défaut est allocator\<`Type`\>.|  
  
## Notes  
 Un objet `forward_list` alloue et libère du stockage pour la séquence qu'il contrôle via un objet stocké de classe `Allocator` basé sur la [allocator, classe](../standard-library/allocator-class.md) \(communément appelée `std::allocator)`\).  Pour plus d'informations, consultez [Allocateurs](../standard-library/allocators.md).  Un objet allocateur doit avoir la même interface externe qu'un objet de classe de modèle `allocator`.  
  
> [!NOTE]
>  L'objet allocateur stocké n'est pas copié quand l'objet conteneur est assigné.  
  
 Les itérateurs, pointeurs et références peuvent devenir non valides quand des éléments de leur séquence contrôlée sont effacés via `forward_list`.  Les insertions et jointures effectuées sur la séquence contrôlée via `forward_list` n'invalident pas les itérateurs.  
  
 Des ajouts à la séquence contrôlée peuvent être effectués par des appels à [forward\_list::insert\_after](../Topic/forward_list::insert_after.md), qui est la seule fonction membre qui appelle le constructeur `Type(const _Type&)`.  `forward_list` peut également appeler des constructeurs de déplacement.  Si une telle expression lève une exception, l'objet conteneur n'insère aucun nouvel élément et relève l'exception.  Ainsi, un objet de classe de modèle `forward_list` est laissé dans un état connu quand ces exceptions se produisent.  
  
### Constructeurs  
  
|||  
|-|-|  
|[forward\_list](../Topic/forward_list::forward_list.md)|Construit un objet de type `forward_list`.|  
  
### Typedefs  
  
|||  
|-|-|  
|[allocator\_type](../Topic/forward_list::allocator_type.md)|Type qui représente la classe d'allocateur pour un forward\_list.|  
|[const\_iterator](../Topic/forward_list::const_iterator.md)|Type qui fournit un itérateur constant pour le forward\_list.|  
|[const\_pointer](../Topic/forward_list::const_pointer.md)|Type qui fournit un pointeur vers un élément `const` dans un forward\_list.|  
|[const\_reference](../Topic/forward_list::const_reference.md)|Type qui fournit une référence constante à un élément dans le forward\_list.|  
|[difference\_type](../Topic/forward_list::difference_type.md)|Type entier signé qui peut être utilisé pour représenter le nombre d'éléments d'un forward\_list au sein d'une plage, parmi les éléments vers lesquels pointent les itérateurs.|  
|[iterator](../Topic/forward_list::iterator.md)|Type qui fournit un itérateur pour le forward\_list.|  
|[pointer](../Topic/forward_list::pointer.md)|Type qui fournit un pointeur vers un élément du forward\_list.|  
|[reference](../Topic/forward_list::reference.md)|Type qui fournit une référence à un élément du forward\_list.|  
|[size\_type](../Topic/forward_list::size_type.md)|Type qui représente la distance non signée entre deux éléments.|  
|[value\_type](../Topic/forward_list::value_type.md)|Type qui représente le type d'élément stocké dans un forward\_list.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[assign](../Topic/forward_list::assign.md)|Efface les éléments d'un forward\_list et copie un nouvel ensemble d'éléments dans un forward\_list cible.|  
|[before\_begin](../Topic/forward_list::before_begin.md)|Retourne un itérateur qui traite la position avant le premier élément dans un forward\_list.|  
|[begin](../Topic/forward_list::begin.md)|Retourne un itérateur qui traite le premier élément d'un forward\_list.|  
|[cbefore\_begin](../Topic/forward_list::cbefore_begin.md)|Retourne un itérateur const qui traite la position avant le premier élément dans un forward\_list.|  
|[cbegin](../Topic/forward_list::cbegin.md)|Retourne un itérateur const qui traite le premier élément d'un forward\_list.|  
|[cend](../Topic/forward_list::cend.md)|Retourne un itérateur const qui traite l'emplacement suivant le dernier élément d'un forward\_list.|  
|[clear](../Topic/forward_list::clear.md)|Efface tous les éléments d'un forward\_list.|  
|[emplace\_after](../Topic/forward_list::emplace_after.md)|Construit par déplacement un nouvel élément après la position spécifiée.|  
|[emplace\_front](../Topic/forward_list::emplace_front.md)|Ajoute un élément construit sur place au début de la liste.|  
|[empty](../Topic/forward_list::empty.md)|Teste si un forward\_list est vide.|  
|[end](../Topic/forward_list::end.md)|Retourne un itérateur qui traite l'emplacement suivant le dernier élément d'un forward\_list.|  
|[erase\_after](../Topic/forward_list::erase_after.md)|Supprime les éléments du forward\_list après une position spécifiée.|  
|[front](../Topic/forward_list::front.md)|Retourne une référence au premier élément d'un forward\_list.|  
|[get\_allocator](../Topic/forward_list::get_allocator.md)|Retourne une copie de l'objet allocateur utilisé pour construire un forward\_list.|  
|[insert\_after](../Topic/forward_list::insert_after.md)|Ajoute des éléments au forward\_list après une position spécifiée.|  
|[max\_size](../Topic/forward_list::max_size.md)|Retourne la longueur maximale d'un forward\_list.|  
|[merge](../Topic/forward_list::merge.md)|Supprime les éléments de la liste d'arguments, les insère dans le forward\_list cible, puis classe le nouvel ensemble combiné d'éléments dans l'ordre croissant ou dans un autre ordre spécifique.|  
|[pop\_front](../Topic/forward_list::pop_front.md)|Supprime l'élément au début d'un forward\_list.|  
|[push\_front](../Topic/forward_list::push_front.md)|Ajoute un élément au début d'un forward\_list.|  
|[supprimer](../Topic/forward_list::remove.md)|Efface les éléments dans un forward\_list qui correspond à une valeur spécifiée.|  
|[remove\_if](../Topic/forward_list::remove_if.md)|Efface les éléments d'un forward\_list pour lequel un prédicat spécifié est satisfait.|  
|[resize](../Topic/forward_list::resize.md)|Spécifie une nouvelle taille pour un forward\_list.|  
|[reverse](../Topic/forward_list::reverse.md)|Inverse l'ordre dans lequel les éléments apparaissent dans un forward\_list.|  
|[sort](../Topic/forward_list::sort.md)|Réorganise les éléments dans l'ordre croissant ou dans un ordre spécifié par un prédicat.|  
|[splice\_after](../Topic/forward_list::splice_after.md)|Réassocie les liens entre les nœuds.|  
|[swap](../Topic/forward_list::swap.md)|Échange les éléments de deux forward\_list.|  
|[unique](../Topic/forward_list::unique.md)|Supprime des éléments adjacents qui réussissent un test spécifié.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[operator\=](../Topic/forward_list::operator=.md)|Remplace les éléments du forward\_list par une copie d'un autre forward\_list.|  
  
## Configuration requise  
 **En\-tête :** \<forward\_list\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<forward\_list\>](../standard-library/forward-list.md)