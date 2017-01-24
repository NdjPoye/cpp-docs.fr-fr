---
title: "&lt;filesystem&gt;, op&#233;rateurs | Microsoft Docs"
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
  - "FILESYSTEM/std::experimental::filesystem::v1::operator=="
  - "std::experimental::filesystem::v1::operator=="
  - "FILESYSTEM/std::experimental::filesystem::v1::operator!="
  - "std::experimental::filesystem::v1::operator!="
  - "FILESYSTEM/std::experimental::filesystem::v1::operator<"
  - "std::experimental::filesystem::v1::operator<"
  - "FILESYSTEM/std::experimental::filesystem::v1::operator<="
  - "std::experimental::filesystem::v1::operator<="
  - "FILESYSTEM/std::experimental::filesystem::v1::operator>"
  - "std::experimental::filesystem::v1::operator>"
  - "FILESYSTEM/std::experimental::filesystem::v1::operator>="
  - "std::experimental::filesystem::v1::operator>="
  - "FILESYSTEM/std::experimental::filesystem::v1::operator/"
  - "std::experimental::filesystem::v1::operator/"
  - "FILESYSTEM/std::experimental::filesystem::v1::operator<<"
  - "std::experimental::filesystem::v1::operator<<"
  - "FILESYSTEM/std::experimental::filesystem::v1::operator>>"
  - "std::experimental::filesystem::v1::operator>>"
dev_langs: 
  - "C++"
ms.assetid: 102c4833-aa3b-41a8-8998-f5003c546bfd
caps.latest.revision: 12
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;filesystem&gt;, op&#233;rateurs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les opérateurs exécutent une comparaison lexicale de deux chemins d'accès sous forme de chaînes. Utilisez la fonction **equivalent** pour déterminer si deux chemins d'accès \(par exemple, un chemin d'accès relatif et un chemin d'accès absolu\) font référence au même fichier ou répertoire sur le disque.  
  
```  
C:\root > D:\root: false  
C:\root > C:\root\sub: false  
C:\root > C:\roo: true  
  
```  
  
 Pour plus d'informations, consultez [Navigation dans le système de fichiers \(C\+\+\)](../standard-library/file-system-navigation.md).  
  
## operator\=\=  
  
```  
bool operator==(const path& left, const path& right) noexcept;  
```  
  
 La fonction retourne left.native\(\) \=\= right.native\(\).  
  
## \!\=, opérateur  
  
```  
bool operator!=(const path& left, const path& right) noexcept;  
```  
  
 La fonction retourne \!\(left \=\= right\).  
  
## \< \(opérateur\)  
  
```  
bool operator<(const path& left, const path& right) noexcept;  
```  
  
 La fonction retourne left.native\(\) \< right.native\(\).  
  
## \<\= \(opérateur\)  
  
```  
bool operator<=(const path& left, const path& right) noexcept;  
```  
  
 La fonction retourne \!\(right \< left\).  
  
## \> \(opérateur\)  
  
```  
bool operator>(const path& left, const path& right) noexcept;  
```  
  
 La fonction retourne right \< left.  
  
## \>\= \(opérateur\)  
  
```  
bool operator>=(const path& left, const path& right) noexcept;  
```  
  
 La fonction retourne \!\(left \< right\).  
  
## operator\/  
  
```  
path operator/(const path& left, const path& right);  
```  
  
 La fonction exécute :  
  
```  
basic_string<Elem, Traits> str;  
path ans = left;  
return (ans /= right);  
  
```  
  
## \<\<, opérateur  
  
```  
template<class Elem, class Traits>    basic_ostream<Elem, Traits>&    operator<<(basic_ostream<Elem, Traits>& os, const path& pval);  
```  
  
 La fonction retourne os \<\< pval.string\<Elem, Traits\>\(\).  
  
## \>\>, opérateur  
  
```  
template<class Elem, class Traits>    basic_istream<Elem, Traits>&    operator<<(basic_istream<Elem, Traits>& is, const path& pval);  
```  
  
 La fonction exécute :  
  
```  
basic_string<Elem, Traits> str;  
is >> str;  
pval = str;  
return (is);  
  
```  
  
## operator\=\=  
  
```  
bool operator==(const path& left, const path& right) noexcept;  
```  
  
 La fonction retourne left.native\(\) \=\= right.native\(\).  
  
## Voir aussi  
 [path, classe \(bibliothèque STL C\+\+\)](../standard-library/path-class-cpp-standard-template-library.md)   
 [Navigation dans le système de fichiers \(C\+\+\)](../standard-library/file-system-navigation.md)   
 [\<filesystem\>](../standard-library/filesystem.md)