---
title: "filesystem_error, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "filesystem/std::tr2::sys::filesystem_error"
dev_langs: 
  - "C++"
ms.assetid: c53aac27-c1fa-43e4-8967-48ea8ba1f172
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# filesystem_error, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Classe de base pour toutes les exceptions qui sont levées pour signaler un dépassement de capacité du système de bas niveau.  
  
## Syntaxe  
  
```  
class filesystem_error    : public system_error;  
```  
  
## Notes  
 La classe sert de classe de base pour toutes les exceptions levées pour signaler une erreur dans des fonctions \<filesystem\>. Elle stocke un objet de type chaîne, appelé ici mymesg. Il stocke également les deux objets de type path, appelés mypval1 et mypval2.  
  
## filesystem\_error::filesystem\_error  
  
```  
filesystem_error(const string& what_arg, error_code ec);  
filesystem_error(const string& what_arg,  
    const path& pval1, error_code ec);  
filesystem_error(const string& what_arg,  
    const path& pval1, const path& pval2, error_code ec);  
```  
  
 Le premier constructeur construit son message à partir de what\_arg et ec. Le deuxième constructeur construit également son message à partir de pval1, qu’il stocke dans mypval1. Le troisième constructeur construit également son message à partir de pval1, qu’il stocke dans mypval1, et à partir de pval2, qu’il stocke dans mypval2.  
  
## filesystem\_error::path1  
  
```  
const path& path1() const noexcept;  
  
```  
  
 La fonction membre retourne mypval1.  
  
## filesystem\_error::path2  
  
```  
const path& path2() const noexcept;  
  
```  
  
 La fonction membre retourne mypval2.  
  
## filesystem\_error::what  
  
```  
const char *what() const noexcept;  
```  
  
 La fonction membre retourne un pointeur vers un NTBS, de préférence, composé à partir de runtime\_error::what\(\), system\_error::what\(\), mymesg, mypval1.native\_string\(\), and mypval2.native\_string\(\).  
  
## Configuration requise  
 **En\-tête :** filesystem  
  
 **Espace de noms :** std::tr2::sys  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [system\_error, classe](../standard-library/system-error-class.md)   
 [\<filesystem\>](../standard-library/filesystem.md)   
 [\<exception\>](../standard-library/exception.md)