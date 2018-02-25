---
title: "&lt;filesystem&gt;, opérateurs | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- FILESYSTEM/std::experimental::filesystem::operator==
- FILESYSTEM/std::experimental::filesystem::operator!=
- FILESYSTEM/std::experimental::filesystem::operator<
- FILESYSTEM/std::experimental::filesystem::operator<=
- FILESYSTEM/std::experimental::filesystem::operator>
- FILESYSTEM/std::experimental::filesystem::operator>=
- FILESYSTEM/std::experimental::filesystem::operator/
- FILESYSTEM/std::experimental::filesystem::operator<<
- FILESYSTEM/std::experimental::filesystem::operator>>
dev_langs:
- C++
ms.assetid: 102c4833-aa3b-41a8-8998-f5003c546bfd
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2fea2837179018e703547a6a66d712404b19a28a
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="ltfilesystemgt-operators"></a>&lt;filesystem&gt;, opérateurs
Les opérateurs exécutent une comparaison lexicale de deux chemins d'accès sous forme de chaînes. Utilisez la fonction **equivalent** pour déterminer si deux chemins d'accès (par exemple, un chemin d'accès relatif et un chemin d'accès absolu) font référence au même fichier ou répertoire sur le disque.  
  
```  
C:\root> D:\root: false  
C:\root> C:\root\sub: false  
C:\root> C:\roo: true  
```  
  
 Pour plus d’informations, consultez [Navigation dans le système de fichiers (C++)](../standard-library/file-system-navigation.md).  
  
## <a name="operator"></a>operator==  
  
```  
bool operator==(const path& left, const path& right) noexcept;  
```  
  
 La fonction retourne left.native() == right.native().  
  
## <a name="operator"></a>!=, opérateur  
  
```  
bool operator!=(const path& left, const path& right) noexcept;  
```  
  
 La fonction retourne !(left == right).  
  
## <a name="operator"></a>< (opérateur)  
  
```  
bool operator<(const path& left, const path& right) noexcept;  
```  
  
 La fonction retourne left.native() < right.native().  
  
## <a name="operator"></a><= (opérateur)  
  
```  
bool operator<=(const path& left, const path& right) noexcept;  
```  
  
 La fonction retourne !(right \< left).  
  
## <a name="operator"></a>> (opérateur)  
  
```  
bool operator>(const path& left, const path& right) noexcept;  
```  
  
 La fonction retourne right \< left.  
  
## <a name="operator"></a>>= (opérateur)  
  
```  
bool operator>=(const path& left, const path& right) noexcept;  
```  
  
 La fonction retourne !(left < right).  
  
## <a name="operator"></a>operator/  
  
```  
path operator/(const path& left, const path& right);
```  
  
 La fonction exécute :  
  
```  
basic_string<Elem, Traits> str;  
path ans = left;  
return (ans /= right);
```  
  
## <a name="operator"></a><<, opérateur  
  
```  
template <class Elem, class Traits>  
basic_ostream<Elem, Traits>& operator<<(basic_ostream<Elem, Traits>& os, const path& pval);
```  
  
 La fonction retourne os << pval.string\<Elem, Traits>().  
  
## <a name="operator"></a>>>, opérateur  
  
```  
template <class Elem, class Traits>  
basic_istream<Elem, Traits>& operator<<(basic_istream<Elem, Traits>& is, const path& pval);
```  
  
 La fonction exécute :  
  
```  
basic_string<Elem, Traits> str;  
is>> str;  
pval = str;  
return (is);
```  
  
## <a name="see-also"></a>Voir aussi  
 [path, classe (Bibliothèque C++ Standard)](../standard-library/path-class.md)   
 [Navigation dans le système de fichiers (C++)](../standard-library/file-system-navigation.md)   
 [\<filesystem>](../standard-library/filesystem.md)

