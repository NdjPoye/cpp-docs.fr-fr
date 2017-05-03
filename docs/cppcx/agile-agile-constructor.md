---
title: "Agile::Agile, constructeur | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "agile/Platform::Agile::Agile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Agile::Agile"
ms.assetid: 33c1df82-f5db-4750-98cc-0daa03be4e59
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Agile::Agile, constructeur
Initialise une nouvelle instance de la classe Agile.  
  
## Syntaxe  
  
```cpp  
  
 Agile();  
  
Agile(T^ object);   
  
Agile(const Agile<T>& object);  
  
Agile(Agile<T>&& object);  
  
```  
  
#### Paramètres  
 `T`  
 Type spécifié par le paramètre de nom de type de modèle.  
  
 `object`  
 Dans la deuxième version de ce constructeur, objet utilisé pour initialiser une nouvelle instance Agile. Dans la troisième version, l'objet qui est copié vers la nouvelle instance Agile. Dans la quatrième version, objet qui est déplacé vers la nouvelle instance Agile.  
  
## Notes  
 La première version de ce constructeur est le constructeur par défaut. La deuxième version initialise la classe d'instance Agile de l'objet spécifié par le paramètre `object`. La troisième version est le constructeur de copie. La quatrième version est le constructeur de déplacement. Ce constructeur ne peut pas lever d'exceptions.  
  
## Configuration requise  
 **Client minimum pris en charge :** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Serveur minimum pris en charge :** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Espace de noms :** Platform  
  
 **En\-tête** : vccorlib.h  
  
## Voir aussi  
 [Platform::Agile, classe](../cppcx/platform-agile-class.md)