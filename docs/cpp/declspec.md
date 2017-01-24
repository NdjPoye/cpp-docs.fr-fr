---
title: "__declspec | Microsoft Docs"
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
  - "__declspec_cpp"
  - "__declspec"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec (mot clé) (C++)"
ms.assetid: 832db681-e8e1-41ca-b78c-cd9d265cdb87
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# __declspec
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Section spécifique à Microsoft  
 La syntaxe à attributs étendus pour la spécification des informations de classe de stockage utilise le mot clé `__declspec`, ce qui indique qu'une instance d'un type donné doit être stockée avec un attribut de classe de stockage Microsoft répertorié ci\-dessous.  Parmi les exemples d'autres modificateurs de classe de stockage figurent les mots clés `static` et `extern`.  Toutefois, ces mots clés font partie de la spécification ANSI des langages C et C\+\+ et, en tant que tels, ne sont pas couverts par la syntaxe à attributs étendus.  La syntaxe à attributs étendus simplifie et normalise les extensions spécifiques à Microsoft pour les langages C et C\+\+.  
  
## Grammaire  
 *decl\-specifier*:  
 `__declspec (`  *extended\-decl\-modifier\-seq*  `)`  
  
 *extended\-decl\-modifier\-seq*:  
 *extended\-decl\-modifier* option  
  
 *extended\-decl\-modifier extended\-decl\-modifier\-seq*  
  
 *extended\-decl\-modifier*:  
 `align(` *\#* `)`  
  
 `allocate("` *segname* `")`  
  
 `appdomain`  
  
 `code_seg("` *segname* `")`  
  
 `deprecated`  
  
 `dllimport`  
  
 `dllexport`  
  
 `jitintrinsic`  
  
 `naked`  
  
 `noalias`  
  
 `noinline`  
  
 `noreturn`  
  
 `nothrow`  
  
 `novtable`  
  
 `process`  
  
 `property(`{`get=`*get\_func\_name*&#124;`,put=`*put\_func\_name*}`)`  
  
 `restrict`  
  
 `safebuffers`  
  
 `selectany`  
  
 `thread`  
  
 `uuid("` *ComObjectGUID* `")`  
  
 Un espace blanc sépare la séquence de modificateur de déclaration.  Des exemples sont donnés dans des sections ultérieures.  
  
 La grammaire des attributs étendus prend en charge les attributs de classe de stockage Microsoft suivants : [align](../cpp/align-cpp.md), [allocate](../cpp/allocate.md), [appdomain](../cpp/appdomain.md), [code\_seg](../cpp/code-seg-declspec.md), [deprecated](../cpp/deprecated-cpp.md), [dllexport](../cpp/dllexport-dllimport.md), [dllimport](../cpp/dllexport-dllimport.md), [jitintrinsic](../cpp/jitintrinsic.md), [naked](../cpp/naked-cpp.md), [noalias](../cpp/noalias.md), [noinline](../cpp/noinline.md), [noreturn](../cpp/noreturn.md), [nothrow](../cpp/nothrow-cpp.md), [novtable](../cpp/novtable.md), [process](../cpp/process.md), [restrict](../cpp/restrict.md), [safebuffers](../cpp/safebuffers.md), [selectany](../cpp/selectany.md) et [thread](../cpp/thread.md).  Elle prend également en charge les attributs d'objet COM suivants : [property](../cpp/property-cpp.md) et [uuid](../cpp/uuid-cpp.md).  
  
 Les attributs de classe de stockage `code_seg`, `dllexport`, `dllimport`, `naked`, `noalias`, `nothrow`, `property`, `restrict`, `selectany`, `thread` et `uuid` sont des propriétés uniquement de la déclaration de l'objet ou de la fonction à laquelle ils s'appliquent.  L'attribut `thread` affecte uniquement les données et les objets.  L'attribut `naked` affecte uniquement les fonctions.  Les attributs `dllimport` et `dllexport` affectent les fonctions, les données et les objets.  Les attributs `property`, `selectany` et `uuid` affectent les objets COM.  
  
 Les mots clés `__declspec` doivent être placés au début d'une déclaration simple.  Le compilateur ignore sans avertissement les mots clés `__declspec` placés après \* ou & et devant l'identificateur de variable dans une déclaration.  
  
 Un attribut `__declspec` spécifié au début d'une déclaration de type défini par l'utilisateur s'applique à la variable de ce type.  Par exemple :  
  
```  
__declspec(dllimport) class X {} varX;  
```  
  
 Dans ce cas, l'attribut s'applique à `varX`.  Un attribut `__declspec` placé après le mot clé `class` ou `struct` s'applique au type défini par l'utilisateur.  Par exemple :  
  
```  
class __declspec(dllimport) X {};  
```  
  
 Dans ce cas, l'attribut s'applique à `X`.  
  
 La recommandation générale en matière d'utilisation de l'attribut `__declspec` pour les déclarations simples est la suivante :  
  
```  
  
decl-specifier-seq declarator-list;  
```  
  
 *decl\-specifier\-seq* doit contenir notamment un type de base \(par exemple  `int`, `float`, `typedef` ou un nom de classe\), une classe de stockage \(par exemple  `static`, `extern`\), ou l'extension `__declspec`.  *init\-declarator\-list* doit contenir, entre autres, la partie relative au pointeur des déclarations.  Par exemple :  
  
```  
__declspec(selectany) int * pi1 = 0;   //OK, selectany & int both part of decl-specifier  
int __declspec(selectany) * pi2 = 0;   //OK, selectany & int both part of decl-specifier  
int * __declspec(selectany) pi3 = 0;   //ERROR, selectany is not part of a declarator  
```  
  
 Le code suivant déclare une variable locale de thread entière et lui affecte une valeur initiale :  
  
```  
// Example of the __declspec keyword  
__declspec( thread ) int tls_i = 1;  
```  
  
## FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [Mots clés C\+\+](../cpp/keywords-cpp.md)   
 [Attributs étendus de classe de stockage C](../c-language/c-extended-storage-class-attributes.md)