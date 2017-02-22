---
title: "directory_entry, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "filesystem/std::tr2::sys::directory_entry"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::operator const std::experimental::filesystem::v1::path &"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::directory_entry"
  - "std::experimental::filesystem::v1::directory_entry::directory_entry"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::operator="
  - "std::experimental::filesystem::v1::directory_entry::operator="
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::assign"
  - "std::experimental::filesystem::v1::directory_entry::assign"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::replace_filename"
  - "std::experimental::filesystem::v1::directory_entry::replace_filename"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::path"
  - "std::experimental::filesystem::v1::directory_entry::path"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::status"
  - "std::experimental::filesystem::v1::directory_entry::status"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::symlink_status"
  - "std::experimental::filesystem::v1::directory_entry::symlink_status"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::operator<"
  - "std::experimental::filesystem::v1::directory_entry::operator<"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::operator=="
  - "std::experimental::filesystem::v1::directory_entry::operator=="
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::operator!="
  - "std::experimental::filesystem::v1::directory_entry::operator!="
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::operator<="
  - "std::experimental::filesystem::v1::directory_entry::operator<="
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::operator>"
  - "std::experimental::filesystem::v1::directory_entry::operator>"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::operator>="
  - "std::experimental::filesystem::v1::directory_entry::operator>="
dev_langs: 
  - "C++"
ms.assetid: 1827c67b-4137-4548-adb0-f955f7acaf08
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# directory_entry, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit un objet qui est retourné par `*X`, où *X* est un [directory\_iterator](../standard-library/directory-iterator-class.md) ou un [recursive\_directory\_iterator](../standard-library/recursive-directory-iterator-class.md).  
  
## Syntaxe  
  
```  
class directory_entry;  
```  
  
## Notes  
 La classe stocke un objet de type [classe Path](../standard-library/path-class-cpp-standard-template-library.md).`path` peut être un [path](../standard-library/path-class-cpp-standard-template-library.md) ou un type dérivé de `path`. Il stocke également deux valeurs [file\_type](../Topic/file_type%20Enumeration.md) : une qui représente ce qui est connu de l'état du nom du fichier stocké et une autre qui représente ce qui est connu de l'état du lien symbolique du nom de fichier.  
  
 Pour plus d’informations et d’exemples de code, consultez [Navigation dans le système de fichiers \(C\+\+\)](../standard-library/file-system-navigation.md).  
  
## assign  
  
```  
void assign(const PFX path& pval,  
    file_status stat_arg = file_status(),  
    file_status symstat_arg = file_status());  
```  
  
 La fonction membre assigne pval à mypath, stat à mystat et symstat à mysymstat.  
  
## directory\_entry  
  
```  
directory_entry() = default;  
directory_entry(const directory_entry&) = default;  
directory_entry(directory_entry&&) noexcept = default;  
explicit directory_entry(const PFX path& pval,  
    file_status stat_arg = file_status(),  
    file_status symstat_arg = file_status());  
```  
  
 Les constructeurs par défaut se comportent comme prévu. Le quatrième constructeur initialise mypath avec pval, mystat avec stat\_arg, et mysymstat avec symstat\_arg.  
  
## \!\=, opérateur  
  
```  
bool operator!=(const directory_entry& right) const noexcept;  
  
```  
  
 La fonction membre retourne \!\(\*this \=\= right\).  
  
## opérateur \=  
  
```  
directory_entry& operator=(const directory_entry&) = default;  
directory_entry& operator=(directory_entry&&) noexcept = default;  
  
```  
  
 Les opérateurs d’assignation de membre par défaut se comportent comme prévu.  
  
## operator\=\=  
  
```  
bool operator==(const directory_entry& right) const noexcept;  
```  
  
 La fonction membre retourne mypath \=\= right.mypath.  
  
## \< \(opérateur\)  
  
```  
  
bool operator<(const directory_entry& right) const noexcept;  
  
```  
  
 La fonction membre retourne mypath \< right.mypath.  
  
## \<\= \(opérateur\)  
  
```  
bool operator<=(const directory_entry& right) const noexcept;  
```  
  
 La fonction membre retourne \!\(right \< \*this\).  
  
## \> \(opérateur\)  
  
```  
bool operator>(const directory_entry& right) const noexcept;  
```  
  
 La fonction membre retourne right \< \*this.  
  
## \>\= \(opérateur\)  
  
```  
bool operator>=(const directory_entry& right) const noexcept;  
  
```  
  
 La fonction membre retourne \!\(\*this \< right\).  
  
## const path\_type&, opérateur  
  
```  
operator const path&() const; // retained  
```  
  
 L’opérateur membre retourne mypath.  
  
## chemin  
  
```  
const PFX path& path() const noexcept;  
```  
  
 La fonction membre retourne mypath.  
  
## replace\_filename  
  
```  
void replace_filename(const PFX path& pval,  
    file_status stat_arg = file_status(),  
    file_status symstat_arg = file_status());  
```  
  
 La fonction membre remplace mypath par mypath.parent\_path\(\) \/ pval, mystat par stat\_arg, et mysymstat par symstat\_arg  
  
## statut  
  
```  
file_status status() const;  
file_status status(  
    error_code& ec) const noexcept;  
Otherwise, mystat = status(mypval).  
  
```  
  
 Les deux fonctions membres retournent mystat éventuellement modifié au préalable comme suit :  
  
1.  Si status\_known\(mystat\), ne rien faire.  
  
2.  Sinon, si \!status\_known\(mysymstat\) && \!is\_symlink\(mysymstat\), mystat \= mysymstat.  
  
## symlink\_status  
  
```  
file_status symlink_status() const;  
file_status symlink_status(  
    error_code& ec) const noexcept;  
```  
  
 Les deux fonctions membres retournent mysymstat éventuellement modifié au préalable comme suit : si status\_known\(mysymstat\), ne rien faire. Sinon, mysymstat \= symlink\_status\(mypval\).  
  
## Configuration requise  
 **En\-tête :** filesystem  
  
 **Espace de noms :** std::tr2::sys  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [\<filesystem\>](../standard-library/filesystem.md)