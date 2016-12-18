---
title: "_bstr_t::operator +=, + | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_bstr_t::operator+"
  - "_bstr_t::operator+="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "+ (opérateur), _bstr_t (objets)"
  - "+= (opérateur), ajouter des chaînes"
ms.assetid: d28316ce-c2c8-4a38-bdb3-44fa4e582c44
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _bstr_t::operator +=, +
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Ajoute des caractères à la fin de l'objet `_bstr_t` ou concatène deux chaînes.  
  
## Syntaxe  
  
```  
  
      _bstr_t& operator+=(  
   const _bstr_t& s1   
);  
_bstr_t operator+(  
   const _bstr_t& s1   
);  
friend _bstr_t operator+(  
   const char* s2,  
   const _bstr_t& s1   
);  
friend _bstr_t operator+(  
   const wchar_t* s3,  
   const _bstr_t& s1   
);  
```  
  
#### Paramètres  
 *s1*  
 Objet `_bstr_t`.  
  
 *s2*  
 Chaîne multioctet.  
  
 `s3`  
 Chaîne Unicode.  
  
## Notes  
 Ces opérateurs exécutent une concaténation de chaînes :  
  
-   **operator\+\=\(**  *s1*  **\)** Ajoute les caractères dans le `BSTR` encapsulé de *s1* à la fin du `BSTR` encapsulé de cet objet.  
  
-   **operator\+\(**  *s1*  **\)** Retourne le nouveau `_bstr_t` formé en concaténant le `BSTR` de cet objet avec celui de *s1*.  
  
-   **operator\+\(**  *s2*  **&#124;**  *s1*  **\)** Retourne un nouveau `_bstr_t` formé en concaténant une chaîne multioctets *s2*, convertie en Unicode, avec le `BSTR` encapsulé dans *s1*.  
  
-   **operator\+\(**  `s3` **,**  *s1*  **\)** Retourne un nouveau `_bstr_t` formé en concaténant une chaîne Unicode `s3` avec le `BSTR` encapsulé dans *s1*.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [\_bstr\_t, classe](../cpp/bstr-t-class.md)