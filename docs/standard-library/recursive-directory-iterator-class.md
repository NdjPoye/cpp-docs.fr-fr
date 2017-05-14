---
title: recursive_directory_iterator, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- filesystem/std::tr2::sys::recursive_directory_iterator
dev_langs:
- C++
ms.assetid: 79a061bd-5b64-404c-97e8-749c888c2ced
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: 0d4325fbe8d4f336f4ca1ac6afe4ba5a96a7172d
ms.contentlocale: fr-fr
ms.lasthandoff: 04/19/2017

---
# <a name="recursivedirectoryiterator-class"></a>recursive_directory_iterator, classe
décrit un itérateur d’entrée qui permet de séquencer les noms de fichiers dans un répertoire, y compris dans les sous-répertoires, de façon récursive. Pour un itérateur X, l’expression *X correspond à un objet de la classe directory_entry, qui inclut dans un wrapper le nom de fichier et tout ce qui est connu sur son état.  
  
 Pour obtenir plus d’informations et des exemples de code, consultez [Navigation dans le système de fichiers (C++)](../standard-library/file-system-navigation.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class recursive_directory_iterator;  
```  
  
## <a name="remarks"></a>Notes  
 La classe de modèle stocke ce qui suit :  
  
1.  un objet de type stack<pair\<directory_iterator, path>>, appelé ici mystack pour les besoins de la démonstration, qui représente l’imbrication des répertoires à séquencer ;  
  
2.  un objet de type directory_entry appelé ici myentry, qui représente le nom de fichier actuel dans la séquence de répertoires ;  
  
3.  un objet de type bool, appelé ici no_push, qui enregistre si la récursivité est désactivée dans les sous-répertoires ;  
  
4.  un objet de type directory_options, appelé ici myoptions, qui enregistre les options établies au moment de la construction ;  
  
 Un objet construit par défaut de type recursive_directory_entry a un itérateur de fin de séquence à mystack.top().first, et représente l’itérateur de fin de séquence. Si nous prenons l’exemple du répertoire abc avec les entrées def (répertoire), def/ghi et jkl, le code suivant :  
  
```  
for (recursive_directory_iterator next(path("abc")), end; next != end; ++next)  
    visit(next->path());
```  
  
 appelle visit avec les arguments `path("abc/def/ghi") and path("abc/jkl").`Vous pouvez qualifier le séquencement via une sous-arborescence de répertoires de deux manières :  
  
1.  Un lien symbolique (symlink) de répertoire est analysé uniquement si vous construisez recursive_directory_iterator avec un argument directory_options dont la valeur est directory_options::follow_directory_symlink.  
  
2.  Si vous appelez disable_recursion_pending, le répertoire suivant rencontré durant l’incrémentation n’est pas analysé de manière récursive.  
  
## <a name="recursivedirectoryiteratordepth"></a>recursive_directory_iterator::depth  
  
```  
int depth() const;
```  
  
 Retourne mystack.size() - 1. Ainsi, pval est à la profondeur zéro.  
  
## <a name="recursivedirectoryiteratordisablerecursionpending"></a>recursive_directory_iterator::disable_recursion_pending  
  
```  
void disable_recursion_pending();
```  
  
 La fonction membre stocke la valeur true dans no_push.  
  
## <a name="recursivedirectoryiteratoroperator"></a>recursive_directory_iterator::operator!=  
  
```  
bool operator!=(const recursive_directory_iterator& right) const;
```  
  
 L’opérateur membre retourne !(*this == right).  
  
## <a name="recursivedirectoryiteratoroperator"></a>recursive_directory_iterator::operator=  
  
```  
recursive_directory_iterator& operator=(const recursive_directory_iterator&) = default;  
recursive_directory_iterator& operator=(recursive_directory_iterator&&) noexcept = default;  
```  
  
 Les opérateurs d’assignation de membre par défaut se comportent comme prévu.  
  
## <a name="recursivedirectoryiteratoroperator"></a>recursive_directory_iterator::operator==  
  
```  
bool operator==(const recursive_directory_iterator& right) const;
```  
  
 L’opérateur membre retourne la valeur true seulement si *this et right sont des itérateurs de fin de séquence, ou si tous les deux ne sont pas des itérateurs de fin de séquence.  
  
## <a name="recursivedirectoryiteratoroperator"></a>recursive_directory_iterator::operator*  
  
```  
const directory_entry& operator*() const;
```  
  
 L’opérateur membre retourne myentry.  
  
## <a name="recursivedirectoryiteratoroperator-"></a>recursive_directory_iterator::operator->  
  
```  
const directory_entry * operator->() const;
```  
  
 Retourne &**this.  
  
## <a name="recursivedirectoryiteratoroperator"></a>recursive_directory_iterator::operator++  
  
```  
recursive_directory_iterator& operator++();

recursive_directory_iterator& operator++(int);
```  
  
 La première fonction membre appelle increment(), puis retourne *this. La deuxième fonction membre effectue une copie de l’objet, appelle increment(), puis retourne la copie.  
  
## <a name="recursivedirectoryiteratoroptions"></a>recursive_directory_iterator::options  
  
```  
directory_options options() const;
```  
  
 Retourne myoptions.  
  
## <a name="recursivedirectoryiteratorpop"></a>recursive_directory_iterator::pop  
  
```  
void pop();
```  
  
 Si depth() == 0, l’objet devient un itérateur de fin de séquence. Sinon, la fonction membre met fin à l’analyse du répertoire actif (le plus profond), et reprend au prochain niveau de profondeur.  
  
## <a name="recursivedirectoryiteratorrecursionpending"></a>recursive_directory_iterator::recursion_pending  
  
```  
bool recursion_pending() const;
```  
  
 Retourne !no_push.  
  
## <a name="recursivedirectoryiteratorrecursivedirectoryiterator"></a>recursive_directory_iterator::recursive_directory_iterator  
  
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
  
 Le premier constructeur produit un itérateur de fin de séquence. Les deuxième et troisième constructeurs stockent false dans no_push et directory_options::none dans myoptions, puis essaient d’ouvrir et de lire pval en tant que répertoire. En cas de réussite, ils initialisent mystack et myentry pour désigner le premier nom de fichier dans la séquence imbriquée. Sinon, ils produisent un itérateur de fin de séquence.  
  
 Les quatrième et cinquième constructeurs se comportent comme le deuxième et le troisième, à ceci près qu’ils stockent tout d’abord opts dans myoptions. Les constructeurs par défaut se comportent comme prévu.  
  
## <a name="recursivedirectoryiteratorincrement"></a>recursive_directory_iterator::increment  
  
```  
recursive_directory_iterator& increment(error_code& ec) noexcept;  
```  
  
 La fonction tente d’accéder au nom de fichier suivant dans la séquence imbriquée. En cas de réussite, elle stocke ce nom de fichier dans myentry. Sinon, elle génère un itérateur de fin de séquence.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<filesystem >  
  
 **Espace de noms :** std::tr2::sys  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les fichiers d’en-tête](../standard-library/cpp-standard-library-header-files.md)   
 [\<filesystem>](../standard-library/filesystem.md)   
 [Navigation dans le système de fichiers (C++)](../standard-library/file-system-navigation.md)


