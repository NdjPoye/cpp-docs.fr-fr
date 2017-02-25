---
title: "hash_compare, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "hash_set/stdext::hash_compare"
  - "std.hash_compare"
  - "hash_compare"
  - "std::hash_compare"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "hash_compare (classe)"
ms.assetid: d502bb59-de57-4585-beb9-00e3a998c0af
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# hash_compare, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe de modèle décrit un objet qui peut être utilisé par les conteneurs associatifs de hachage, hash\_map, hash\_multimap, hash\_set, ou hash\_multiset, comme objet de paramètre **Traits** par défaut pour ordonner et hacher les éléments qu'ils contiennent.  
  
## Syntaxe  
  
```  
template<class Key, class Traits = less<Key> >  
   class hash_compare  
   {  
   Traits comp;  
public:  
   const size_t bucket_size = 4;  
   const size_t min_buckets = 8;  
   hash_compare( );  
   hash_compare( Traits pred );  
   size_t operator( )( const Key& _Key ) const;  
   bool operator( )(   
      const Key& _Key1,  
      const Key& _Key2  
   ) const;  
   };  
```  
  
## Notes  
 Chaque conteneur associatif de hachage stocke un objet de caractéristiques de hachage de type **Traits** \(un paramètre de modèle\).  Vous pouvez dériver une classe d'une spécialisation de hash\_compare pour remplacer de manière sélective certaines fonctions et certains objets, ou vous pouvez fournir votre propre version de cette classe si vous répondez à certaines conditions requises minimales.  En particulier, pour un objet hash\_comp de type **hash\_compare\<Key, Traits\>**, le comportement suivant est requis par les conteneurs ci\-dessus :  
  
-   Pour toutes les valeurs `_Key` de type **Key**, l'appel **hash\_comp**\(`_Key`\) sert de fonction de hachage, ce qui produit une distribution des valeurs de type **size\_t**.  La fonction fournie par hash\_compare retourne `_Key`.  
  
-   Pour toutes les valeurs `_Key1` de type **Key** précédant `_Key2` dans la séquence et ayant la même valeur de hachage \(la valeur retournée par la fonction de hachage\), **hash\_comp**\(`_Key2``_Key1`\) a la valeur false.  La fonction doit imposer un ordonnancement total sur les valeurs de type **Key**.  La fonction fournie par hash\_compare retourne *comp*\(`_Key2``_Key1`\)`,` où *comp* est un objet stocké de type **Traits** que vous pouvez spécifier lors de la construction de l'objet hash\_comp.  Pour le type de paramètre **Traits less\<Key\>**, la valeur des clés de tri ne va jamais en diminuant.  
  
-   La constante entière **bucket\_size** spécifie le nombre moyen d'éléments par « compartiment » \(entrée de table de hachage\) que le conteneur doit essayer de ne pas dépasser.  La valeur doit être supérieure à zéro.  La valeur fournie par hash\_compare est 4.  
  
-   La constante entière **min\_buckets** spécifie le nombre minimal de compartiments à conserver dans la table de hachage.  Il doit s'agir d'une puissance de deux et sa valeur doit être supérieure à zéro.  La valeur fournie par hash\_compare est 8.  
  
 Dans Visual C\+\+ .NET 2003, les membres des fichiers d'en\-tête [\<hash\_map\>](../standard-library/hash-map.md) et [\<hash\_set\>](../standard-library/hash-set.md) ne sont plus dans l'espace de noms std. Ils ont été transférés dans l'espace de noms stdext.  Pour plus d'informations, consultez [The stdext Namespace](../standard-library/stdext-namespace.md).  
  
## Exemple  
 Consultez les exemples pour [hash\_map::hash\_map](../Topic/hash_map::hash_map.md)[hash\_multimap::hash\_multimap](../Topic/hash_multimap::hash_multimap.md)[hash\_set::hash\_set](../Topic/hash_set::hash_set.md) et [hash\_multiset::hash\_multiset](../Topic/hash_multiset::hash_multiset.md) pour voir comment déclarer et utiliser hash\_compare.  
  
## Configuration requise  
 **En\-tête :** \<hash\_map\>  
  
 **Espace de noms :** stdext  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)