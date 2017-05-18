---
title: directory_entry, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- filesystem/std::experimental::filesystem::directory_entry
- FILESYSTEM/std::experimental::filesystem::directory_entry::operator const std::experimental::filesystem::path &
- FILESYSTEM/std::experimental::filesystem::directory_entry::directory_entry
- FILESYSTEM/std::experimental::filesystem::directory_entry::operator=
- FILESYSTEM/std::experimental::filesystem::directory_entry::assign
- FILESYSTEM/std::experimental::filesystem::directory_entry::replace_filename
- FILESYSTEM/std::experimental::filesystem::directory_entry::path
- FILESYSTEM/std::experimental::filesystem::directory_entry::status
- FILESYSTEM/std::experimental::filesystem::directory_entry::symlink_status
- FILESYSTEM/std::experimental::filesystem::directory_entry::operator<
- FILESYSTEM/std::experimental::filesystem::directory_entry::operator==
- FILESYSTEM/std::experimental::filesystem::directory_entry::operator!=
- FILESYSTEM/std::experimental::filesystem::directory_entry::operator<=
- FILESYSTEM/std::experimental::filesystem::directory_entry::operator>
- FILESYSTEM/std::experimental::filesystem::directory_entry::operator>=
dev_langs:
- C++
ms.assetid: 1827c67b-4137-4548-adb0-f955f7acaf08
caps.latest.revision: 17
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
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 0bd6b73c99eccffc7661cc4b43f97ab46890c5ee
ms.contentlocale: fr-fr
ms.lasthandoff: 04/29/2017

---
# <a name="directoryentry-class"></a>directory_entry, classe
Décrit un objet qui est retourné par `*X`, où *X* est un [directory_iterator](../standard-library/directory-iterator-class.md) ou un [recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class directory_entry;  
```  
  
## <a name="remarks"></a>Notes  
 La classe stocke un objet de type [path](../standard-library/path-class.md). Le `path` stocké peut être une instance de la [classe path](../standard-library/path-class.md) ou d’un type dérivé de `path`. Elle stocke également deux valeurs [file_type](../standard-library/filesystem-enumerations.md#file_type) ; une qui représente ce qui est connu de l’état du nom du fichier stocké et une autre qui représente ce qui est connu de l’état du lien symbolique du nom de fichier.  
  
 Pour plus d’informations et pour obtenir des exemples de code, consultez [Navigation dans le système de fichiers (C++)](../standard-library/file-system-navigation.md).  
  
## <a name="assign"></a>assign  
  
```  
void assign(const std::experimental::filesystem::path& pval,  
    file_status stat_arg = file_status(),  
    file_status symstat_arg = file_status());
```  
  
 La fonction membre assigne pval à mypath, stat à mystat et symstat à mysymstat.  
  
## <a name="directoryentry"></a>directory_entry  
  
```  
directory_entry() = default;  
directory_entry(const directory_entry&) = default;  
directory_entry(directory_entry&&) noexcept = default;  
explicit directory_entry(const std::experimental::filesystem::path& pval,  
    file_status stat_arg = file_status(),  
    file_status symstat_arg = file_status());
```  
  
 Les constructeurs par défaut se comportent comme prévu. Le quatrième constructeur initialise mypath avec pval, mystat avec stat_arg, et mysymstat avec symstat_arg.  
  
## <a name="operator"></a>!=, opérateur  
  
```  
bool operator!=(const directory_entry& right) const noexcept;  
```  
  
 La fonction membre retourne !(*this == right).  
  
## <a name="operator"></a>opérateur =  
  
```  
directory_entry& operator=(const directory_entry&) = default;  
directory_entry& operator=(directory_entry&&) noexcept = default;  
```  
  
 Les opérateurs d’assignation de membre par défaut se comportent comme prévu.  
  
## <a name="operator"></a>operator==  
  
```  
bool operator==(const directory_entry& right) const noexcept;  
```  
  
 La fonction membre retourne mypath == right.mypath.  
  
## <a name="operator"></a>< (opérateur)  
  
```  
 
bool operator<(const directory_entry& right) const noexcept;  
```  
  
 La fonction membre retourne mypath < right.mypath.  
  
## <a name="operator"></a><= (opérateur)  
  
```  
bool operator<=(const directory_entry& right) const noexcept;  
```  
  
 La fonction membre retourne !(right \< *this).  
  
## <a name="operator"></a>> (opérateur)  
  
```  
bool operator>(const directory_entry& right) const noexcept;  
```  
  
 La fonction membre retourne right \< *this.  
  
## <a name="operator"></a>>= (opérateur)  
  
```  
bool operator>=(const directory_entry& right) const noexcept;  
```  
  
 La fonction membre retourne !(*this < right).  
  
## <a name="operator-const-pathtype"></a>const path_type&, opérateur  
  
``` 
 operator const std::experimental::filesystem::path&() const; 
```  
  
 L’opérateur membre retourne mypath.  
  
## <a name="path"></a>path  
  
```  
const std::experimental::filesystem::path& path() const noexcept;  
```  
  
 La fonction membre retourne mypath.  
  
## <a name="replacefilename"></a>replace_filename  
  
```  
void replace_filename(
    const std::experimental::filesystem::path& pval,  
    file_status stat_arg = file_status(),  
    file_status symstat_arg = file_status());
```  
  
 La fonction membre remplace mypath par mypath.parent_path() / pval, mystat par stat_arg, et mysymstat par symstat_arg  
  
## <a name="status"></a>statut  
  
```  
file_status status() const; 
file_status status(error_code& ec) const noexcept;  
```  
  
 Les deux fonctions membres retournent mystat éventuellement modifié au préalable comme suit :  
  
1.  Si status_known(mystat), ne rien faire.  
  
2.  Sinon, si !status_known(mysymstat) && !is_symlink(mysymstat), mystat = mysymstat.  
  
## <a name="symlinkstatus"></a>symlink_status  
  
```  
file_status symlink_status() const; 
file_status symlink_status(error_code& ec) const noexcept;  
```  
  
 Les deux fonctions membres retournent mysymstat éventuellement modifié au préalable comme suit : si status_known(mysymstat), ne rien faire. Sinon, mysymstat = symlink_status(mypval).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<experimental/filesystem>  
  
 **Espace de noms :** std::experimental::filesystem  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les fichiers d’en-tête](../standard-library/cpp-standard-library-header-files.md)   
 [\<filesystem>](../standard-library/filesystem.md)


