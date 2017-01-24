---
title: "R&#233;sum&#233; des d&#233;clarations | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
ms.assetid: 53a5e9e5-1a33-40b5-9dea-7f669b479329
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# R&#233;sum&#233; des d&#233;clarations
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`declaration`:  
 *declaration\-specifiers attribute\-seq*  opt *init\-declarator\-list* opt**;**  
  
 \/\* *attribute\-seq* est spécifique de Microsoft \*\/  
  
 *declaration\-specifiers*:  
 *storage\-class\-specifier declaration\-specifiers* opt  
  
 *type\-specifier declaration\-specifiers* opt  
  
 *type\-qualifier declaration\-specifiers* opt  
  
 *attribute\-seq* :            \/\* *attribute\-seq* est propre à Microsoft \*\/  
 *attribute attribute\-seq* opt  
  
 *attribute* : un des éléments suivants :      \/\* Propre à Microsoft \*\/  
 ||||  
|-|-|-|  
|[\_\_asm](../assembler/inline/asm.md)|[\_\_clrcall](../cpp/clrcall.md)|[\_\_stdcall](../cpp/stdcall.md)|  
|[\_\_based](../cpp/based-grammar.md)|[\_\_fastcall](../cpp/fastcall.md)|[\_\_thiscall](../cpp/thiscall.md)|  
|[\_\_cdecl](../cpp/cdecl.md)|[\_\_inline](../misc/inline-inline-forceinline.md)|[\_\_vectorcall](../cpp/vectorcall.md)|  
  
 *init\-declarator\-list* :  
 *init\-declarator*  
  
 *init\-declarator\-list*  **,**  *init\-declarator*  
  
 *init\-declarator* :  
 *declarator*  
  
 *declarator*  **\=**  *initializer* \/\* pour l'initialisation scalaire \*\/  
  
 *storage\-class\-specifier*:  
 **auto**  
  
 **register**  
  
 **static**  
  
 **extern**  
  
 **typedef**  
  
 **\_\_declspec \(**  *extended\-decl\-modifier\-seq*  **\)** \/\* Propre à Microsoft \*\/  
  
 *type\-specifier*:  
 **void**  
  
 **char**  
  
 **short**  
  
 **int**  
  
 `__int8` \/\* Propre à Microsoft \*\/  
  
 `__int16` \/\* Propre à Microsoft \*\/  
  
 `__int32` \/\* Propre à Microsoft \*\/  
  
 `__int64` \/\* Propre à Microsoft \*\/  
  
 **long**  
  
 **float**  
  
 **double**  
  
 **signed**  
  
 **non signé**  
  
 *struct\-or\-union\-specifier*  
  
 *enum\-specifier*  
  
 *typedef\-name*  
  
 *type\-qualifier* :  
 **const**  
  
 `volatile`  
  
 `declarator`:  
 `pointer` opt *direct\-declarator*  
  
 *direct\-declarator* :  
 *identifier*  
  
 **\(**  *declarator*  **\)**  
  
 *direct\-declarator*  **\[**  *constant\-expression*  opt **\]**  
  
 *direct\-declarator*  **\(**  *parameter\-type\-list*  **\)** \/\* déclarateur de nouveau style \*\/  
  
 *direct\-declarator*  **\(**  *identifier\-list* option **\)**\/      \/\* déclarateur de style obsolète \*\/  
  
 `pointer`:  
 **\*** *type\-qualifier\-list* opt  
  
 **\*** *type\-qualifier\-list* opt `pointer`  
  
 *parameter\-type\-list* :                           \/\* La liste de paramètres \*\/  
 *parameter\-list*  
  
 *parameter\-list* **, ...**  
  
 *parameter\-list* :  
 *parameter\-declaration*  
  
 *parameter\-list*  **,**  *parameter\-declaration*  
  
 *type\-qualifier\-list* :  
 *type\-qualifier*  
  
 *type\-qualifier\-list type\-qualifier*  
  
 *enum\-specifier* :  
 **enum**  *identifier* opt **{** *enumerator\-list* **}**  
  
 **enum**  *identifier*  
  
 *enumerator\-list* :  
 *enumerator*  
  
 *enumerator\-list*  **,**  `enumerator`  
  
 `enumerator`:  
 *enumeration\-constant*  
  
 *enumeration\-constant*  **\=**  *constant\-expression*  
  
 *enumeration\-constant* :  
 *identifier*  
  
 *struct\-or\-union\-specifier* :  
 *struct\-or\-union identifier* opt **{** *struct\-declaration\-list* **}** *struct\-or\-union identifier*  
  
 *struct\-or\-union* :  
 **struct**  
  
 **union**  
  
 *struct\-declaration\-list* :  
 *struct\-declaration*  
  
 *struct\-declaration\-list struct\-declaration*  
  
 *struct\-declaration* :  
 *specifier\-qualifier\-list struct\-declarator\-list*  **;**  
  
 *specifier\-qualifier\-list* :  
 *type\-specifier specifier\-qualifier\-list* opt  
  
 *type\-qualifier specifier\-qualifier\-list* opt  
  
 *struct\-declarator\-list* :  
 *struct\-declarator struct\-declarator\-list*  **,**  *struct\-declarator*  
  
 *struct\-declarator* :  
 *declarator*  
  
 *type\-specifier declarator* opt **:** *constant\-expression*  
  
 *parameter\-declaration* :  
 *declaration\-specifiers declarator* \/\* Déclarateur nommé \*\/  
  
 *declaration\-specifiers abstract\-declarator* opt **\/\*** Déclarateur anonyme **\*\/**  
  
 *identifier\-list* : **\/\*** Pour le déclarateur de style ancien **\* \/**  
 *identifier*  
  
 *identifier\-list*  **,**  *identifier*  
  
 *abstract\-declarator* : **\/\*** Utilisé avec les déclarateurs anonymes **\*\/**  
 *pointer*  
  
 `pointer` opt *direct\-abstract\-declarator*  
  
 *direct\-abstract\-declarator* :  
 **\(**  *abstract\-declarator*  **\)**  
  
 *direct\-abstract\-declarator* opt **\[** *constant\-expression* opt **\]**  
  
 *direct\-abstract\-declarator* opt **\(** *parameter\-type\-list* opt **\)**  
  
 *initializer* :  
 *assignment\-expression*  
  
 **{**  *initializer\-list*  **}** \/\* Pour l'initialisation d'agrégats \*\/  
  
 **{**  *initializer\-list*  **, }**  
  
 *initializer\-list* :  
 *initializer*  
  
 *initializer\-list*  **,**  *initializer*  
  
 *type\-name* :  
 *specifier\-qualifier\-list abstract\-declarator* opt  
  
 *typedef\-name* :  
 *identifier*  
  
 *extended\-decl\-modifier\-seq* :\/\*    Propre à Microsoft \*\/  
 *extended\-decl\-modifier* opt  
  
 *extended\-decl\-modifier\-seq extended\-decl\-modifier*  
  
 *extended\-decl\-modifier* :   \/\* Propre à Microsoft \*\/  
 **thread**  
  
 **naked**  
  
 **dllimport**  
  
 `dllexport`  
  
## Voir aussi  
 [Conventions d'appel](../cpp/calling-conventions.md)   
 [Grammaire de la structure de la phrase](../c-language/phrase-structure-grammar.md)   
 [Conventions d'appel obsolètes](../cpp/obsolete-calling-conventions.md)