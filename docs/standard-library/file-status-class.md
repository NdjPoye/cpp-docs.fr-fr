---
title: "file_status, classe | Microsoft Docs"
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
  - "filesystem/std::tr2::sys::file_status"
  - "filesystem/std::tr2::sys::file_status::perms"
  - "filesystem/std::tr2::sys::file_status::type"
dev_langs: 
  - "C++"
ms.assetid: 9781840e-ad22-44dd-ad79-0fabaa94bac4
caps.latest.revision: 15
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# file_status, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Encapsule un [file\_type](../Topic/file_type%20Enumeration.md).  
  
## Syntaxe  
  
```  
class file_status;  
```  
  
## file\_status::file\_status  
  
```  
explicit file_status(file_type ftype = file_type::none,    perms mask = perms::unknown) noexcept;file_status(const file_status&) noexcept = default;file_status(file_status&&) noexcept = default;  
```  
  
## file\_status::operator\=  
  
```  
file_status& operator=(const file_status&) noexcept = default;  
file_status& operator=(file_status&&) nexcept = default;  
```  
  
 Les opérateurs d’affectation de membre par défaut se comportent comme prévu.  
  
## type  
  
```  
file_type type() const noexcept  
void type(file_type _Ftype) noexcept  
```  
  
 Obtient ou définit le file\_type.  
  
## permissions  
  
```  
perms permissions() const noexcept  
void permissions(perms_Prms) noexcept   
```  
  
 Obtient ou définit les autorisations de fichiers.  
  
 Utilisez l’accesseur Set pour rendre un fichier accessible en lecture seule ou pour supprimer l’attribut de lecture seule.  
  
## Configuration requise  
 **En\-tête :** filesystem  
  
 **Espace de noms :** std::tr2::sys  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [path, classe \(bibliothèque STL C\+\+\)](../standard-library/path-class-cpp-standard-template-library.md)   
 [\<filesystem\>](../standard-library/filesystem.md)