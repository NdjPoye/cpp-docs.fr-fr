---
title: "recursive_directory_iterator, classe | Microsoft Docs"
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
  - "filesystem/std::tr2::sys::recursive_directory_iterator"
dev_langs: 
  - "C++"
ms.assetid: 79a061bd-5b64-404c-97e8-749c888c2ced
caps.latest.revision: 15
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# recursive_directory_iterator, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

décrit un itérateur d’entrée qui permet de séquencer les noms de fichiers dans un répertoire, y compris dans les sous\-répertoires, de façon récursive. Pour un itérateur X, l’expression \*X correspond à un objet de la classe directory\_entry, qui inclut dans un wrapper le nom de fichier et tout ce qui est connu sur son état.  
  
 Pour plus d’informations et d’exemples de code, consultez [Navigation dans le système de fichiers \(C\+\+\)](../standard-library/file-system-navigation.md).  
  
## Syntaxe  
  
```  
class recursive_directory_iterator;  
```  
  
## Notes  
 La classe de modèle stocke ce qui suit :  
  
1.  un objet de type stack\<pair\<directory\_iterator, path\>\>, appelé ici mystack à des fins de démonstration, et qui représente l’imbrication des répertoires à séquencer ;  
  
2.  un objet de type directory\_entry appelé ici myentry, qui représente le nom de fichier actuel dans la séquence de répertoires ;  
  
3.  un objet de type bool, appelé ici no\_push, qui enregistre si la récursivité est désactivée dans les sous\-répertoires ;  
  
4.  un objet de type directory\_options, appelé ici myoptions, qui enregistre les options établies au moment de la construction ;  
  
 Un objet construit par défaut de type recursive\_directory\_entry a un itérateur de fin de séquence à mystack.top\(\).first, et représente l’itérateur de fin de séquence. Si nous prenons l’exemple du répertoire abc avec les entrées def \(répertoire\), def\/ghi et jkl, le code suivant :  
  
```  
for (recursive_directory_iterator next(path("abc")), end; next != end; ++next)  
    visit(next->path());  
  
```  
  
 appelle visit avec les arguments `path("abc/def/ghi") and path("abc/jkl").` Vous pouvez qualifier le séquencement via une sous\-arborescence de répertoires de deux manières :  
  
1.  Un lien symbolique \(symlink\) de répertoire est analysé uniquement si vous construisez recursive\_directory\_iterator avec un argument directory\_options dont la valeur est directory\_options::follow\_directory\_symlink.  
  
2.  Si vous appelez disable\_recursion\_pending, le répertoire suivant rencontré durant l’incrémentation n’est pas analysé de manière récursive.  
  
## recursive\_directory\_iterator::depth  
  
```  
int depth() const;  
```  
  
 Retourne mystack.size\(\) \- 1. Ainsi, pval est à la profondeur zéro.  
  
## recursive\_directory\_iterator::disable\_recursion\_pending  
  
```  
void disable_recursion_pending();  
```  
  
 La fonction membre stocke la valeur true dans no\_push.  
  
## recursive\_directory\_iterator::operator\!\=  
  
```  
bool operator!=(const recursive_directory_iterator& right) const;  
  
```  
  
 L’opérateur membre retourne \!\(\*this \=\= right\).  
  
## recursive\_directory\_iterator::operator\=  
  
```  
recursive_directory_iterator& operator=(const recursive_directory_iterator&) = default;  
recursive_directory_iterator& operator=(recursive_directory_iterator&&) noexcept = default;  
  
```  
  
 Les opérateurs d’assignation de membre par défaut se comportent comme prévu.  
  
## recursive\_directory\_iterator::operator\=\=  
  
```  
bool operator==(const recursive_directory_iterator& right) const;  
```  
  
 L’opérateur membre retourne la valeur true seulement si \*this et right sont des itérateurs de fin de séquence, ou si tous les deux ne sont pas des itérateurs de fin de séquence.  
  
## recursive\_directory\_iterator::operator\*  
  
```  
const directory_entry& operator*() const;  
  
```  
  
 L’opérateur membre retourne myentry.  
  
## recursive\_directory\_iterator::operator\-\>  
  
```  
const directory_entry *operator->() const;  
```  
  
 Retourne &\*\*this.  
  
## recursive\_directory\_iterator::operator\+\+  
  
```  
recursive_directory_iterator& operator++();  
recursive_directory_iterator& operator++(int);  
  
```  
  
 La première fonction membre appelle increment\(\), puis retourne \*this. La deuxième fonction membre effectue une copie de l’objet, appelle increment\(\), puis retourne la copie.  
  
## recursive\_directory\_iterator::options  
  
```  
directory_options options() const;  
```  
  
 Retourne myoptions.  
  
## recursive\_directory\_iterator::pop  
  
```  
void pop();  
```  
  
 Si depth\(\) \=\= 0, l’objet devient un itérateur de fin de séquence. Sinon, la fonction membre met fin à l’analyse du répertoire actif \(le plus profond\), et reprend au prochain niveau de profondeur.  
  
## recursive\_directory\_iterator::recursion\_pending  
  
```  
bool recursion_pending() const;  
```  
  
 Retourne \!no\_push.  
  
## recursive\_directory\_iterator::recursive\_directory\_iterator  
  
```  
recursive_directory_iterator() noexcept;  
explicit recursive_directory_iterator(const path& pval);  
recursive_directory_iterator(const path& pval,  
    error_code& ec) noexcept;  
recursive_directory_iterator(const path& pval,  
    directory_options opts);  
recursive_directory_iterator(const path& pval,  
    directory_options opts,  
    error_code& ec) noexcept;  
recursive_directory_iterator(const recursive_directory_iterator&) = default;  
recursive_directory_iterator(recursive_directory_iterator&&) noexcept = default;  
  
```  
  
 Le premier constructeur produit un itérateur de fin de séquence. Les deuxième et troisième constructeurs stockent false dans no\_push et directory\_options::none dans myoptions, puis essaient d’ouvrir et de lire pval en tant que répertoire. En cas de réussite, ils initialisent mystack et myentry pour désigner le premier nom de fichier dans la séquence imbriquée. Sinon, ils produisent un itérateur de fin de séquence.  
  
 Les quatrième et cinquième constructeurs se comportent comme le deuxième et le troisième, à ceci près qu’ils stockent tout d’abord opts dans myoptions. Les constructeurs par défaut se comportent comme prévu.  
  
## recursive\_directory\_iterator::increment  
  
```  
recursive_directory_iterator& increment(  
    error_code& ec) noexcept;  
```  
  
 La fonction tente d’accéder au nom de fichier suivant dans la séquence imbriquée. En cas de réussite, elle stocke ce nom de fichier dans myentry. Sinon, elle génère un itérateur de fin de séquence.  
  
## Configuration requise  
 **En\-tête :** filesystem  
  
 **Espace de noms :** std::tr2::sys  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [\<filesystem\>](../standard-library/filesystem.md)   
 [Navigation dans le système de fichiers \(C\+\+\)](../standard-library/file-system-navigation.md)