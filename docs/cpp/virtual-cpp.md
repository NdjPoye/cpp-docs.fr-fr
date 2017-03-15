---
title: "virtual (C++) | Microsoft Docs"
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
  - "virtual_cpp"
  - "virtual"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "classes de base, virtuels"
  - "classes de base virtuelles, déclarer"
  - "fonctions virtuelles, déclarer"
  - "virtual (mot clé) (C++)"
ms.assetid: c2eb987d-6cf3-43b6-aa0c-29a6f561b1ae
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# virtual (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le mot clé `virtual` déclare une fonction virtuelle ou une classe de base virtuelle.  
  
## Syntaxe  
  
```  
virtual [type-specifiers] member-function-declarator  
virtual [access-specifier] base-class-name  
```  
  
#### Paramètres  
 `type-specifiers`  
 Spécifie le type de retour de la fonction membre virtuelle.  
  
 `member-function-declarator`  
 Déclare une fonction membre.  
  
 `access-specifier`  
 Définit le niveau d'accès à la classe de base, `public`, `protected` ou `private`.  Peut apparaître avant ou après le mot clé `virtual`.  
  
 `base-class-name`  
 Identifie un type de classe déclaré précédemment.  
  
## Notes  
 Pour plus d'informations, consultez [Fonctions virtuelles](../cpp/virtual-functions.md) et [Classes de base virtuelles](../misc/virtual-base-classes.md).  
  
 Consultez également les mots clés suivants : [class](../cpp/class-cpp.md), [private](../cpp/private-cpp.md), [public](../cpp/public-cpp.md) et [protected](../cpp/protected-cpp.md).  
  
## Voir aussi  
 [Mots clés C\+\+](../cpp/keywords-cpp.md)