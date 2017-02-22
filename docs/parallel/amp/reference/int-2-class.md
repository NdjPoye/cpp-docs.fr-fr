---
title: "int_2, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp_short_vectors/Concurrency::graphics::int_2::y"
  - "amp_short_vectors/Concurrency::graphics::int_2::set_x"
  - "amp_short_vectors/Concurrency::graphics::int_2::set_y"
  - "amp_short_vectors/Concurrency::graphics::int_2::get_yx"
  - "amp_short_vectors/Concurrency::graphics::int_2::operator++"
  - "amp_short_vectors/Concurrency::graphics::int_2::x"
  - "amp_short_vectors/Concurrency::graphics::int_2::set_yx"
  - "amp_short_vectors/Concurrency::graphics::int_2::operator/="
  - "amp_short_vectors/Concurrency::graphics::int_2::get_y"
  - "amp_short_vectors/Concurrency::graphics::int_2::gr"
  - "amp_short_vectors/Concurrency::graphics::int_2::operator*="
  - "amp_short_vectors/Concurrency::graphics::int_2::r"
  - "amp_short_vectors/Concurrency::graphics::int_2::get_xy"
  - "amp_short_vectors/Concurrency::graphics::int_2::operator="
  - "amp_short_vectors/Concurrency::graphics::int_2::g"
  - "amp_short_vectors/Concurrency::graphics::int_2::rg"
  - "amp_short_vectors/Concurrency::graphics::int_2::xy"
  - "amp_short_vectors/Concurrency::graphics::int_2::operator-="
  - "amp_short_vectors/Concurrency::graphics::int_2::get_x"
  - "amp_short_vectors/Concurrency::graphics::int_2::yx"
  - "amp_short_vectors/Concurrency::graphics::int_2"
  - "amp_short_vectors/Concurrency::graphics::int_2::operator-"
  - "amp_short_vectors/Concurrency::graphics::int_2::set_xy"
  - "amp_short_vectors/Concurrency::graphics::int_2::operator+="
  - "amp_short_vectors/Concurrency::graphics::int_2::operator--"
dev_langs: 
  - "C++"
ms.assetid: 258b02e9-f1ee-46c2-8edd-dc9f69184846
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# int_2, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Représente un vecteur court de deux entiers.  
  
## Syntaxe  
  
```  
class int_2;  
```  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`value_type`||  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[int\_2::int\_2, constructeur](../Topic/int_2::int_2%20Constructor.md)|Surchargé.  Le constructeur par défaut, initialise tous les éléments avec la valeur 0.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|Méthode int\_2::get\_x||  
|Méthode int\_2::get\_xy||  
|Méthode int\_2::get\_y||  
|Méthode int\_2::get\_yx||  
|méthode int\_2::ref\_g||  
|méthode int\_2::ref\_r||  
|méthode int\_2::ref\_x||  
|méthode int\_2::ref\_y||  
|Méthode int\_2::set\_x||  
|Méthode int\_2::set\_xy||  
|Méthode int\_2::set\_y||  
|Méthode int\_2::set\_yx||  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|Opérateur int\_2::operator\-||  
|Opérateur int\_2::operator\-\-||  
|Opérateur int\_2::operator%\=||  
|Opérateur int\_2::operator&\=||  
|Opérateur int\_2::operator\*\=||  
|Opérateur int\_2::operator\/\=||  
|Opérateur int\_2::operator^\=||  
|Opérateur int\_2::operator&#124;\=||  
|Opérateur int\_2::operator~||  
|Opérateur int\_2::operator\+\+||  
|Opérateur int\_2::operator\+\=||  
|Opérateur int\_2::operator\<\<\=||  
|Opérateur int\_2::operator\=||  
|Opérateur int\_2::operator\-\=||  
|Opérateur int\_2::operator\>\>\=||  
  
### Constantes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[int\_2::size, constante](../Topic/int_2::size%20Constant.md)||  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|Donnée membre int\_2::g||  
|Donnée membre int\_2::gr||  
|Donnée membre int\_2::r||  
|Donnée membre int\_2::rg||  
|Donnée membre int\_2::x||  
|Donnée membre int\_2::xy||  
|Donnée membre int\_2::y||  
|Donnée membre int\_2::yx||  
  
## Hiérarchie d'héritage  
 `int_2`  
  
## Configuration requise  
 **En\-tête :** amp\_short\_vectors.h  
  
 **Espace de noms :** Concurrency::graphics  
  
## Voir aussi  
 [Concurrency::graphics, espace de noms](../../../parallel/amp/reference/concurrency-graphics-namespace.md)