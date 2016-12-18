---
title: "path, classe (biblioth&#232;que STL C++) | Microsoft Docs"
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
  - "filesystem/std::tr2::sys::path"
dev_langs: 
  - "C++"
ms.assetid: 8a1227ca-aeb2-4e0e-84aa-86e34e4f4fe8
caps.latest.revision: 14
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# path, classe (biblioth&#232;que STL C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe **chemin** stocke un objet de type string\_type, appelé ici myname à des fins de démonstration, pouvant être utilisée comme un nom de chemin. string\_type est un synonyme de basic\_string\<value\_type\>, où value\_type est un synonyme de char sous Windows ou wchar\_t sous Posix.  
  
 Pour plus d’informations et des exemples de code, consultez [Navigation dans le système de fichiers \(C\+\+\)](../standard-library/file-system-navigation.md).  
  
## Syntaxe  
  
```  
class path;  
```  
  
## path::append  
  
```  
template<class Source>  
    path& append(const Source& source);  
template<class InIt>  
    path& append(InIt first, InIt last);  
```  
  
 Les fonctions membres ajoutent la séquence spécifiée à mypath convertie et en insérant un preferred\_separator selon les besoins.  
  
## path::assign  
  
```  
template<class Source>  
    path& assign(const Source& source);  
template<class InIt>  
    path& assign(InIt first, InIt last);  
```  
  
 Les fonctions membres remplacent mypath par la séquence spécifiée, convertie selon les besoins.  
  
## path::begin  
  
```  
iterator begin() const;  
```  
  
 Retourne un path::iterator désignant le premier élément du chemin dans le nom du chemin, s’il est présent.  
  
## path::c\_str  
  
```  
const value_type& *c_str() const noexcept;  
```  
  
 Retourne un pointeur vers le premier caractère de mypath.  
  
## path::clear  
  
```  
void clear() noexcept;  
```  
  
 La fonction membre exécute mypath.clear\(\)  
  
## path::compare  
  
```  
int compare(const path& pval) const noexcept;  
int compare(const string_type& str) const;  
int compare(const value_type *ptr) const;  
```  
  
 La première fonction retourne mypath.compare\(pval.native\(\)\). La deuxième fonction retourne mypath.compare\(str\). La troisième fonction retourne mypath.compare\(ptr\).  
  
## path::concat  
  
```  
template<class Source>  
    path& concat(const Source& source);  
template<class InIt>  
    path& concat(InIt first, InIt last);  
```  
  
 Les fonctions membres ajoutent la séquence spécifiée à mypath, convertie \(pas en insérant un séparateur\) selon les besoins.  
  
## path::const\_iterator  
  
```  
typedef iterator const_iterator;  
```  
  
 Type est un synonyme de iterator.  
  
## path::empty  
  
```  
bool empty() const noexcept;  
```  
  
 Retourne mypath.empty\(\).  
  
## path::end  
  
```  
iterator end() const;  
```  
  
 Retourne un itérateur de fin de séquence de type iterator.  
  
## path::extension  
  
```  
path extension() const;  
```  
  
 Retourne le suffixe de filename\(\) X tel que :  
  
 Si X \=\= path\("."\) &#124;&#124; X \=\= path\(".."\) ou si X ne contient pas de point, le suffixe est vide.  
  
 Dans le cas contraire, le suffixe commence par \(et inclut\) le point le plus à droite.  
  
## path::filename  
  
```  
path filename() const;  
```  
  
 Retourne le composant du répertoire racine de myname, spécifiquement `empty() ? path() : *--end()`. Le composant peut être vide.  
  
## path::generic\_string  
  
```  
template<class Elem,  
    class Traits = char_traits<Elem>,  
    class Alloc = allocator<Elem>>  
    basic_string<Elem, Traits, Alloc>  
        generic_string(const Alloc& al = Alloc()) const;  
STD string generic_string() const;  
```  
  
 Retourne `this->string<Elem, Traits, Alloc>(_Al)` avec \(sous Windows\) les barres obliques inverses converties en barres obliques.  
  
## path::generic\_u16string  
  
```  
STD u16string generic_u16string() const;  
```  
  
 Retourne u16string\(\) avec \(sous Windows\) les barres obliques inverses converties en barres obliques.  
  
## path::generic\_u32string  
  
```  
STD u32string generic_u32string() const;  
```  
  
 Retourne u32string\(\) avec \(sous Windows\) les barres obliques inverses converties en barres obliques.  
  
## path::generic\_u8string  
  
```  
STD string generic_u8string() const;  
```  
  
 Retourne u8string\(\) avec \(sous Windows\) les barres obliques inverses converties en barres obliques.  
  
## path::generic\_wstring  
  
```  
STD wstring generic_wstring() const;  
```  
  
 Retourne wstring\(\) avec \(sous Windows\) les barres obliques inverses converties en barres obliques.  
  
## path::has\_extension  
  
```  
bool has_extension() const;  
```  
  
 Retourne \!extension\(\).empty\(\).  
  
## path::has\_filename  
  
```  
bool has_filename() const;  
```  
  
 Retourne \!filename\(\).empty\(\).  
  
## path::has\_parent\_path  
  
```  
  
bool has_parent_path() const;  
  
```  
  
 Retourne \!parent\_path\(\).empty\(\).  
  
## path::has\_relative\_path  
  
```  
bool has_relative_path() const;  
  
```  
  
 Retourne \!relative\_path\(\).empty\(\).  
  
## path::has\_root\_directory  
  
```  
bool has_root_directory() const;  
  
```  
  
 Retourne \!root\_directory\(\).empty\(\).  
  
## path::has\_root\_name  
  
```  
bool has_root_name() const;  
```  
  
 Retourne \!root\_name\(\).empty\(\).  
  
## path::has\_root\_path  
  
```  
bool has_root_path() const;  
  
```  
  
 Retourne \!root\_path\(\).empty\(\).  
  
## path::has\_stem  
  
```  
bool has_stem() const;  
```  
  
 Retourne \!stem\(\).empty\(\).  
  
## path::is\_absolute  
  
```  
bool is_absolute() const;  
```  
  
 Pour Windows, la fonction retourne has\_root\_name\(\) && has\_root\_directory\(\). Pour Posix, la fonction retourne has\_root\_directory\(\).  
  
## path::is\_relative  
  
```  
bool is_relative() const;  
```  
  
 Retourne \!is\_absolute\(\).  
  
## path::iterator  
  
```  
class iterator  
    {// bidirectional iterator for path  
    typedef bidirectional_iterator_tag iterator_category;  
    typedef path_type value_type;  
    typedef ptrdiff_t difference_type;  
    typedef const value_type *pointer;  
    typedef const value_type& reference;  
    .....  
    };  
  
```  
  
 Cette classe décrit un itérateur de constante bidirectionnel qui désigne les composants de chemin de myname dans la séquence :  
  
1.  le nom de la racine, s’il est présent  
  
2.  le répertoire racine, s’il est présent  
  
3.  les éléments du répertoire restants du chemin parent, s’il est présent, se terminant par le nom de fichier, s’il est présent  
  
4.  
  
5.  
  
 Pour pval, un objet de type path :  
  
1.  path::iterator X \= pval.begin\(\) désigne le premier élément du chemin dans le chemin, s’il est présent.  
  
2.  X \=\= pval.end\(\) a la valeur true quand X pointe juste après la fin de la séquence de composants.  
  
3.  \*X retourne une chaîne qui correspond au composant actuel.  
  
4.  \+\+X désigne le composant suivant dans la séquence, s’il est présent.  
  
5.  \-\-X désigne le composant précédent dans la séquence, s’il est présent.  
  
6.  La modification de myname invalide tous les itérateurs désignant des éléments dans myname.  
  
## path::make\_preferred  
  
```  
path& make_preferred();  
  
```  
  
 La fonction membre convertit chaque séparateur en un preferred\_separator selon les besoins.  
  
## path::native  
  
```  
const string_type& native() const noexcept;  
```  
  
 Retourne myname.  
  
## path::operator\=  
  
```  
path& operator=(const path& right);  
path& operator=(path&& right) noexcept;  
template<class Source>  
    path& operator=(const Source& source);  
  
```  
  
 Le premier opérateur membre copie right.myname vers myname. Le deuxième opérateur membre copie right.myname vers myname. Le troisième opérateur membre se comporte comme \*this \= path\(source\).  
  
## path::operator\+\=  
  
```  
path& operator+=(const path& right);  
path& operator+=(const string_type& str);  
path& operator+=(const value_type *ptr);  
path& operator+=(value_type elem);  
template<class Source>  
    path& operator+=(const Source& source);  
template<class Elem>  
    path& operator+=(Elem elem);  
```  
  
 Les fonctions membres se comportent comme les expressions correspondantes suivantes :  
  
1.  concat\(right\);  
  
2.  concat\(path\(str\)\);  
  
3.  concat\(ptr\);  
  
4.  concat\(string\_type\(1, elem\)\);  
  
5.  concat\(source\);  
  
6.  concat\(path\(basic\_string\<Elem\>\(1, elem\)\)\);  
  
## path::operator\/\=  
  
```  
path& operator/=(const path& right);  
template<class Source>  
    path& operator/=(const Source& source);  
  
```  
  
 Les fonctions membres se comportent comme les expressions correspondantes suivantes :  
  
1.  append\(right\);  
  
2.  append\(source\);  
  
## path::operator string\_type  
  
```  
operator string_type() const;  
```  
  
 L’opérateur membre retourne myname.  
  
## path::parent\_path  
  
```  
path parent_path() const;  
  
```  
  
 Retourne le composant du chemin parent de myname, spécifiquement le préfixe de myname après suppression de filename\(\).native\(\) et des séparateurs de répertoire immédiatement précédents. \(De même, si begin\(\) \! \= end\(\), il correspond à la combinaison de tous les éléments dans la plage \[begin\(\), \-\-end\(\)\) en appliquant successivement l’opérateur \/\=.\) Le composant peut être vide.  
  
## path::path  
  
```  
path();  
path(const path& right);  
path(path&& right) noexcept;  
template<class Source>  
    path(const Source& source);  
template<class Source>  
    path(const Source& source, const locale& loc);  
template<class InIt>  
    path(InIt first, InIt last);  
template<class InIt>  
    path(InIt first, InIt last, const locale& loc);  
  
```  
  
 Tous les constructeurs construisent tous myname de différentes façons :  
  
 Pour path\(\), c’est myname\(\).  
  
 Pour path\(const path& right\), c’est myname\(right.myname\).  
  
 Pour path\(path&& right\), c’est myname\(right.myname\).  
  
 Pour template\<class Source\> path\(const Source& source\), c’est myname\(source\).  
  
 Pour template\<class Source\> path\(const Source& source, const locale& loc\), c’est myname\(source\), en obtenant toutes les facettes codecvt nécessaires de loc.  
  
 Pour template\<class InIt\> path\(InIt first, InIt last\), c’est myname\(first, last\).  
  
 Pour template\<class InIt\> path\(InIt first, InIt last, const locale& loc\), c’est myname\(first, last\), en obtenant toutes les facettes codecvt nécessaires de loc.  
  
## path::preferred\_separator  
  
```  
#if _WIN32_C_LIB  
static constexpr value_type preferred_separator == L'\\';  
#else // assume Posix  
static constexpr value_type preferred_separator == '/';  
#endif // filesystem model now defined  
  
```  
  
 L’objet de constante donne le caractère préféré pour la séparation des composants du chemin, en fonction du système d’exploitation hôte. Notez qu’il est également possible dans la plupart des contextes sous Windows d’utiliser à la place L'\/'.  
  
## path::relative\_path  
  
```  
path relative_path() const;  
  
```  
  
 Retourne le composant du chemin relatif de myname, spécifiquement le suffixe de myname après suppression de root\_path\(\).native\(\) et des séparateurs de répertoire redondants immédiatement suivants. Le composant peut être vide.  
  
## path::remove\_filename  
  
```  
path& remove_filename();  
  
```  
  
## path::replace\_extension  
  
```  
path& replace_extension(const path& newext = path());  
  
```  
  
 La fonction membre supprime d’abord le suffixe extension\(\).native\(\) de myname. Ensuite, si \!newext.empty\(\) && newext\[0\] \!\= dot \(où dot est \*path\("."\).c\_str\(\)\), dot est ajouté à myname. Ensuite, newext est ajouté à myname.  
  
## path::replace\_filename  
  
```  
  
path& replace_filename(const path& pval);  
  
```  
  
 La fonction membre exécute :  
  
```  
remove_filename();  
*this /= pval;  
return (*this);  
```  
  
## path::root\_directory  
  
```  
path root_directory() const;  
  
```  
  
 Retourne le composant du répertoire racine de myname. Le composant peut être vide.  
  
## path::root\_name  
  
```  
path root_name() const;  
  
```  
  
 Retourne le composant du nom racine de myname. Le composant peut être vide.  
  
## path::root\_path  
  
```  
  
path root_path() const;  
  
```  
  
 Retourne le composant du nom racine de myname, c’est\-à\-dire root\_name\(\) \/ root\_directory. Le composant peut être vide.  
  
## path::stem  
  
```  
  
path stem() const;  
  
```  
  
 Retourne le composant stem de myname, c’est\-à\-dire filename\(\).native\(\) avec les extension\(\).native\(\) de fin supprimés. Le composant peut être vide.  
  
## path::string  
  
```  
template<class Elem,  
    class Traits = char_traits<Elem>,  
    class Alloc = allocator<Elem>>  
    basic_string<Elem, Traits, Alloc>  
        string(const Alloc& al = Alloc()) const;  
STD string string() const;  
  
```  
  
 La première fonction membre \(de modèle\) convertit la séquence stockée dans mypath de la même façon que :  
  
1.  string\(\) for string\<char, Traits, Alloc\>\(\)  
  
2.  wstring\(\) for string\<wchar\_t, Traits, Alloc\>\(\)  
  
3.  u16string\(\) for string\<char16\_t, Traits, Alloc\>\(\)  
  
4.  u32string\(\) for string\<char32\_t, Traits, Alloc\>\(\)  
  
 La deuxième fonction membre convertit la séquence stockée dans mypath dans l’encodage privilégié par le système hôte pour une séquence de caractères et la retourne stockée dans un objet de type string.  
  
## path::string\_type  
  
```  
typedef basic_string<value_type> string_type;  
  
```  
  
 Le type est un synonyme de basic\_string\<value\_type\>.  
  
## path::swap  
  
```  
void swap(path & right) noexcept;  
  
```  
  
 Exécute swap\(mypath, right.mypath\).  
  
## path::u16string  
  
```  
STD u16string u16string() const;  
  
```  
  
 La fonction membre convertit la séquence stockée dans mypath en UTF\-16 et la retourne stockée dans un objet de type u16string.  
  
## path::u32string  
  
```  
STD u32string u32string() const;  
  
```  
  
 La fonction membre convertit la séquence stockée dans mypath en UTF\-32 et la retourne stockée dans un objet de type u32string.  
  
## path::u8string  
  
```  
STD string u8string() const;  
  
```  
  
 La fonction membre convertit la séquence stockée dans mypath en UTF\-8 et la retourne stockée dans un objet de type u8string.  
  
## path::value\_type  
  
```  
  
#if _WIN32_C_LIB  
typedef wchar_t value_type;  
#else // assume Posix  
typedef char value_type;  
#endif // filesystem model now defined  
  
```  
  
 Le type décrit les éléments du chemin privilégiés par le système d’exploitation hôte.  
  
## path::wstring  
  
```  
STD wstring wstring() const;  
```  
  
 Convertit la séquence stockée dans mypath dans l’encodage privilégié par le système hôte pour une séquence wchar\_t et la retourne stockée dans un objet de type wstring.  
  
## Configuration requise  
 **En\-tête :** filesystem  
  
 **Espace de noms :** std::tr2::sys  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)