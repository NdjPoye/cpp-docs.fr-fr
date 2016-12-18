---
title: "_variant_t (classe) | Microsoft Docs"
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
  - "Variant"
  - "_variant_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_variant_t (classe)"
  - "_variant_t (classe), fonctions membres"
  - "_variant_t (classe), opérateurs"
  - "VARIANT (objet)"
  - "VARIANT (objet), encapsulation COM"
ms.assetid: 6a3cbd4e-0ae8-425e-b4cf-ca0df894c93f
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _variant_t (classe)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Un objet `_variant_t` encapsule le type de données `VARIANT`.  La classe gère l'allocation des ressources et leur libération, et effectue des appels fonctionnels à **VariantInit** et à **VariantClear** de façon approprié.  
  
### Construction  
  
|||  
|-|-|  
|[\_variant\_t](../cpp/variant-t-variant-t.md)|Construit un objet `_variant_t`.|  
  
### Opérations  
  
|||  
|-|-|  
|[Attacher](../cpp/variant-t-attach.md)|Joint un objet **VARIANT** à l'objet `_variant_t`.|  
|[Clear](../cpp/variant-t-clear.md)|Efface l'objet encapsulé **VARIANT**.|  
|[ChangeType](../cpp/variant-t-changetype.md)|Change le type de l'objet `_variant_t` en le type indiqué **VARTYPE**.|  
|[Détacher](../cpp/variant-t-detach.md)|Détache l'objet encapsulé **VARIANT** de cet objet `_variant_t`.|  
|[SetString](../cpp/variant-t-setstring.md)|Assigne une chaîne à cet objet `_variant_t`.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[L'opérateur \=](../cpp/variant-t-operator-equal.md)|Assigne une nouvelle valeur à un objet `_variant_t` existant.|  
|[L'opérateur \=, \!\=](../cpp/variant-t-relational-operators.md)|Comparer deux objets `_variant_t` pour savoir s'ils sont égaux ou inégaux.|  
|[Extracteurs](../cpp/variant-t-extractors.md)|Extraire des données de l'objet encapsulé **VARIANT**.|  
  
## END Spécifique à Microsoft  
  
## Configuration requise  
 **En\-tête :** comutil.h  
  
 **Bibliothèque :** comsuppw.lib ou comsuppwd.lib \(consultez [\/Zc:wchar\_t \(wchar\_t est un type natif\)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) pour plus d'informations\)  
  
## Voir aussi  
 [Classes du support COM du compilateur](../cpp/compiler-com-support-classes.md)