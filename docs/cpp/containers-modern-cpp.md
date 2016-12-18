---
title: "Conteneurs (Modern C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 6e10b758-e928-4827-9c3f-86cafe54bf5b
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Conteneurs (Modern C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Par défaut, utilisez [vecteur](vector%20Class.md) comme conteneur par défaut séquentielle en C++. Ceci est l’équivalent de la liste \< T> dans d’autres langues.  
  
```cpp  
vector<string> v;  
v.push_back( "Geddy Lee" );  
  
```  
  
 Utilisez [carte](../standard-library/map-class.md) (pas unordered_map) comme conteneur associatif par défaut. Utilisez [défini](../standard-library/set-class.md), [multimap](../standard-library/multimap-class.md), [multiset](../standard-library/multiset-class.md) dégénérée & plusieurs cas.  
  
```cpp  
map<string, string> phone_book;  
// ...  
phone_book["Alex Lifeson"] = "+1 (416) 555-1212";  
  
```  
  
 Optimisation des performances est nécessaire, utilisez :  
  
1.  le type de tableau lors de l’incorporation est important - par exemple, comme un membre de classe.  
  
2.  non ordonné les conteneurs associatifs (unordered_map, AL) : réduire la surcharge par élément (principale) et une recherche constante (potentiellement majeure, mineure parfois). Plus difficile à utiliser correctement et efficacement, en raison des inconvénients et les frontières nettes.  
  
3.  vecteur trié. (Voir : [Algorithmes](../cpp/algorithms-modern-cpp.md).)  
  
 N’utilisez pas les tableaux C. (Pour les anciennes API, utilisez `f( vec.data(), vec.size() );` .)  
  
 Pour un autre article sur les conteneurs, consultez [conteneurs STL](../standard-library/stl-containers.md).  
  
## <a name="container-sizes"></a>Tailles de conteneur  
 Les tableaux suivants indiquent les tailles de conteneur, en octets, pour les plates-formes x86 et x64.  (Dans ce cas, 32 bits ARM est équivalent à x86.)  Ces tables couvrent mode version finale, car le mode débogage contient vérification machines qui consomme du temps et espace.  Les colonnes distinctes sont pour [!INCLUDE[cpp_orcas_long](../cpp/includes/cpp_orcas_long_md.md)] SP1, où `_SECURE_SCL` par défaut 1 et pour [!INCLUDE[cpp_orcas_long](../cpp/includes/cpp_orcas_long_md.md)] SP1 avec `_SECURE_SCL` manuellement la valeur 0 pour une vitesse maximale.  Visual C++ dans Visual Studio 2010, [!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)], et [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)] par défaut `_SECURE_SCL` 0 (maintenant appelé `_ITERATOR_DEBUG_LEVEL`).  
  
|x86 conteneur taille (octets)|VC9 SP1|VC9 SP1<br /><br /> SCL=0|VC10|VC11|  
|-----------------------------------|-------------|------------------------|----------|----------|  
|vecteur \< int>|24|16|16|12|  
|tableau \< int, 5 >|20|20|20|20|  
|deque \< int>|32|32|24|20|  
|forward_list \< int>|N/A|N/A|8|4|  
|liste \< int>|28|12|12|8|  
|priority_queue \< int>|28|20|20|16|  
|file d’attente \< int>|32|32|24|20|  
|pile \< int>|32|32|24|20|  
|paire \< int, int >|8|8|8|8|  
|Tuple \< int, int, int >|16|16|16|12|  
|carte \< int, int >|32|12|16|8|  
|multimap \< int, int >|32|12|16|8|  
|Définissez \< int>|32|12|16|8|  
|multiset \< int>|32|12|16|8|  
|hash_map \< int, int >|72|44|44|32|  
|hash_multimap \< int, int >|72|44|44|32|  
|hash_set \< int>|72|44|44|32|  
|hash_multiset \< int>|72|44|44|32|  
|unordered_map \< int, int >|72|44|44|32|  
|unordered_multimap \< int, int >|72|44|44|32|  
|unordered_set \< int>|72|44|44|32|  
ordered_multiset \< int>|72|44|44|32|  
|string|28|28|28|24|  
|wstring|28|28|28|24|  
  
|x64 conteneur taille (octets)|VC9 SP1|VC9 SP1<br /><br /> SCL=0|VC10|VC11|  
|-----------------------------------|-------------|------------------------|----------|----------|  
|vecteur \< int>|48|32|32|24|  
|tableau \< int, 5 >|20|20|20|20|  
|deque \< int>|64|64|48|40|  
|forward_list \< int>|N/A|N/A|16|8|  
|liste \< int>|56|24|24|16|  
|priority_queue \< int>|56|40|40|32|  
|file d’attente \< int>|64|64|48|40|  
|pile \< int>|64|64|48|40|  
|paire \< int, int >|8|8|8|8|  
|Tuple \< int, int, int >|16|16|16|12|  
|carte \< int, int >|64|24|32|16|  
|multimap \< int, int >|64|24|32|16|  
|Définissez \< int>|64|24|32|16|  
|multiset \< int>|64|24|32|16|  
|hash_map \< int, int >|144|88|88|64|  
|hash_multimap \< int, int >|144|88|88|64|  
|hash_set \< int>|144|88|88|64|  
|hash_multiset \< int>|144|88|88|64|  
|unordered_map \< int, int >|144|88|88|64|  
|unordered_multimap \< int, int >|144|88|88|64|  
|unordered_set \< int>|144|88|88|64|  
ordered_multiset \< int>|144|88|88|64|  
|string|40|40|40|32|  
|wstring|40|40|40|32|  
  
## <a name="see-also"></a>Voir aussi  
 [Bienvenue dans C++](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [Référence du langage C++](../cpp/cpp-language-reference.md)   
 [Bibliothèque C++ Standard](../standard-library/cpp-standard-library-reference.md)