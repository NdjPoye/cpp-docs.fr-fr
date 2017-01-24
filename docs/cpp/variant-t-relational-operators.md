---
title: "_variant_t, op&#233;rateurs relationnels | Microsoft Docs"
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
  - "_variant_t::operator=="
  - "_variant_t.operator!="
  - "_variant_t::operator!="
  - "_variant_t.operator=="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "!= (opérateur)"
  - "== (opérateur), avec des objets Visual C++ spécifiques"
  - "!= (opérateur), opérateurs relationnels"
  - "!= (opérateur), variante"
  - "== (opérateur), variante"
  - "!= (opérateur), opérateurs relationnels"
  - "!= (opérateur), variante"
  - "== (opérateur), variante"
  - "opérateurs relationnels, _variant_t (classe)"
ms.assetid: 141bacb8-41a2-44dd-b3c0-4ad1f884f4ea
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _variant_t, op&#233;rateurs relationnels
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Comparez deux objets `_variant_t` pour déterminer leur égalité ou inégalité.  
  
## Syntaxe  
  
```  
  
      bool operator==(  
   const VARIANT& varSrc   
) const;  
bool operator==(  
   const VARIANT* pSrc   
) const;  
bool operator!=(  
   const VARIANT& varSrc   
) const;  
bool operator!=(  
   const VARIANT* pSrc   
) const;  
```  
  
#### Paramètres  
 *varSrc*  
 **VARIANT** à comparer à l'objet `_variant_t`.  
  
 `pSrc`  
 Pointeur désignant le **VARIANT** à comparer à l'objet `_variant_t`.  
  
## Valeur de retour  
 Retourne **true** si la comparaison est vérifiée, **false** dans le cas contraire.  
  
## Notes  
 Compare un objet `_variant_t` à un **VARIANT**, afin de tester l'égalité ou l'inégalité.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [\_variant\_t \(classe\)](../cpp/variant-t-class.md)