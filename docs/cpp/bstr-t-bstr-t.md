---
title: "_bstr_t::_bstr_t | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_bstr_t::_bstr_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_bstr_t (classe)"
  - "_bstr_t (méthode)"
  - "BSTR (objet)"
ms.assetid: 116d994e-5a72-4351-afbe-866c80b4c165
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# _bstr_t::_bstr_t
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Construit un objet `_bstr_t`.  
  
## Syntaxe  
  
```  
_bstr_t( ) throw( );   
_bstr_t(  
   const _bstr_t& s1   
) throw( );  
_bstr_t(  
   const char* s2   
);  
_bstr_t(  
   const wchar_t* s3   
);  
_bstr_t(  
   const _variant_t& var   
);  
_bstr_t(  
   BSTR bstr,  
   bool fCopy   
);  
```  
  
#### Paramètres  
 `s1`  
 Objet `_bstr_t` à copier.  
  
 `s2`  
 Chaîne multioctet.  
  
 `s3`  
 Chaîne Unicode.  
  
 `var`  
 Objet [\_variant\_t](../cpp/variant-t-class.md).  
  
 `bstr`  
 Objet `BSTR` existant.  
  
 `fCopy`  
 Si la valeur est `false`, l'argument `bstr` est attaché au nouvel objet sans faire de copie en appelant `SysAllocString`.  
  
## Notes  
 Le tableau ci\-dessous décrit les constructeurs `_bstr_t`.  
  
|Constructeur|Description|  
|------------------|-----------------|  
|`_bstr_t( )`|Construit un objet `_bstr_t` par défaut qui encapsule un objet`BSTR` null.|  
|`_bstr_t( _bstr_t&`  `s1`  `)`|Construit un objet `_bstr_t` comme copie d'un autre.<br /><br /> Il s'agit d'une copie *superficielle*, qui incrémente le décompte de références de l'objet `BSTR` encapsulé au lieu d'en créer un nouveau.|  
|`_bstr_t( char*`  `s2`  `)`|Construit un objet `_bstr_t` en appelant `SysAllocString` pour créer un nouvel objet `BSTR`, puis l'encapsule.<br /><br /> Ce constructeur effectue en premier lieu une conversion de chaîne multioctet vers Unicode.|  
|`_bstr_t( wchar_t*`  `s3`  `)`|Construit un objet `_bstr_t` en appelant `SysAllocString` pour créer un nouvel objet `BSTR`, puis l'encapsule.|  
|`_bstr_t( _variant_t&`  `var`  `)`|Construit un objet `_bstr_t` à partir d'un objet `_variant_t` en extrayant d'abord un objet `BSTR` de l'objet VARIANT encapsulé.|  
|`_bstr_t( BSTR`  `bstr` `, bool`  `fCopy`  `)`|Construit un objet `_bstr_t` à partir d'un `BSTR` existant \(par opposition à une chaîne `wchar_t*`\).  Si `fCopy` a la valeur false, le `BSTR` fourni est attaché au nouvel objet sans qu'une nouvelle copie soit effectuée avec `SysAllocString`.<br /><br /> Ce constructeur est utilisé par les fonctions wrapper dans les en\-têtes de bibliothèque de types pour encapsuler et prendre possession d'un `BSTR` retourné par une méthode d'interface.|  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [\_bstr\_t, classe](../cpp/bstr-t-class.md)   
 [\_variant\_t \(classe\)](../cpp/variant-t-class.md)