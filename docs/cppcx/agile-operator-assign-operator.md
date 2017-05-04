---
title: "Agile::operator=, op&#233;rateur | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "agile/Platform::Agile::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Agile::operator="
ms.assetid: 2c413bef-f103-4911-afb3-0dac5f6a760e
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Agile::operator=, op&#233;rateur
Assigne l'objet spécifié à l'objet Agile actuel.  
  
## Syntaxe  
  
```cpp  
  
   Agile<T> operator=(  
   T^ object  
) throw();  
  
   Agile<T> operator=(  
      const Agile<T>& object  
) throw();  
  
   Agile<T> operator=(  
      Agile<T>&& object  
) throw();  
  
   T^ operator=(  
      IUnknown* lp  
) throw();  
  
```  
  
#### Paramètres  
 `T`  
 Le type spécifié par le nom de type du modèle.  
  
 `object`  
 L'objet ou le handle vers un objet qui est copié ou déplacé vers l'objet Agile actuel.  
  
 `lp`  
 Le pointeur d'interface IUnknown d'un objet.  
  
## Valeur de retour  
 Handle d'un objet de type `T`  
  
## Notes  
 La première version de l'opérateur d'assignation copie un handle vers un type référence à l'objet Agile actuel. La deuxième version copie une référence à un type Agile dans l'objet Agile actuel. La troisième version déplace un type Agile vers l'objet Agile actuel. La quatrième version déplace un pointeur vers un objet COM de l'objet Agile actuel.  
  
 L'opération d'assignation applique automatiquement le contexte de l'objet Agile actuel.  
  
## Configuration requise  
 **Client minimum pris en charge :** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Serveur minimum pris en charge :** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Espace de noms :** Platform  
  
 **En\-tête** : vccorlib.h  
  
## Voir aussi  
 [Platform::Agile, classe](../cppcx/platform-agile-class.md)